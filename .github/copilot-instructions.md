# Copilot Instructions for jasobrien.github.io

## Project Overview

This is a **single-file GitHub Pages application** for Australian property investment analysis. The entire application lives in `InvestorCalculator.html` — there are no separate JS/CSS files. It's deployed via GitHub Actions to GitHub Pages on push to `main`.

**Live URL:** https://jasobrien.github.io/InvestorCalculator.html

## Architecture Pattern: Single-File Application

**Everything is embedded in `InvestorCalculator.html`:**
- HTML structure (lines ~1-200)
- CSS in `<style>` tag (~15-40)
- JavaScript in `<script>` tag (~207-571)

**Why this matters:** When modifying functionality, styling, or calculations, you're always editing the same file. There are no imports, no bundlers, no build steps.

## Key Technical Components

### NSW Stamp Duty Calculation (`calcNSWDuty` function)
- Uses tiered band table (`nswDutyTable`) specific to NSW property transfers
- Each band has: `{min, max, base, ratePer100}`
- Always validate changes against NSW Revenue guidelines
- Example: $500k property = $17,990 duty

### Financial Calculations (`updateAll` function)
- **Loan repayment**: Uses exact amortization formula with monthly compounding
- **Annual interest**: Computed from first 12 months of amortization schedule (not simple interest × rate)
- **LMI estimation**: Heuristic only (0.5%-3% of loan) when deposit < 20%
- **Depreciation**: Division 43 (2.5% building value annually) + Division 40 (custom plant/equipment)
- All monetary values formatted with `fmt()` helper using `toLocaleString('en-AU')`

### Tax & Negative Gearing Module
- Tax refund = (loss + depreciation) × marginal tax rate
- Loss only counted if `netAfterInterest < 0`
- Depreciation checkbox (`include_depreciation`) must be ticked for new builds
- Three tax brackets: 30%, 37%, 45%

### Chart.js Integration
- Two charts: `cashflowChart` (bar) and `valueChart` (line for capital appreciation)
- Chart instances must be destroyed before redraw to prevent memory leaks
- `chartInstance` and `window.valueChartInstance` are global holders

## Development Workflow

### Local Testing
```bash
# Option 1: Python simple server
python3 -m http.server 8000

# Option 2: Any static file server
# Then open http://localhost:8000/InvestorCalculator.html
```

### Deployment
- **Automatic**: Push to `main` triggers `.github/workflows/static.yml`
- **Manual**: Workflow can be run manually from Actions tab
- **No build required**: Static files deployed as-is

### Testing Changes
1. Open `InvestorCalculator.html` directly in browser (file:// protocol works)
2. Test with known scenarios:
   - $500k @ 20% deposit → should show ~$17,990 stamp duty
   - Deposit < 20% → LMI checkbox auto-ticks
   - Negative cashflow → check tax refund calculation
3. Verify PDF export functionality with jsPDF

## Common Patterns & Conventions

### DOM Access
- Use `$()` helper: `const $ = id => document.getElementById(id)`
- Input values: `Number($('price').value) || 0` (always coerce and default)
- Output display: `$('out_upfront').innerText = '$' + fmt(value)`

### Event Handling
- All inputs auto-update via `input` and `change` events (wired at bottom)
- Three buttons: `calcBtn` (manual recalc), `pdfBtn` (export), `resetBtn` (restore defaults)
- Auto-calculate on load: `window.addEventListener('load', ()=>{ updateAll(); })`

### Conditional Features
- **LMI**: Auto-enable if deposit < 20%, calculated only if checkbox ticked
- **Depreciation**: Off by default, requires manual enable (assume older property)
- **Capital appreciation chart**: Separate panel below main app, 20-year projection

## File Structure Notes

- `index.html`: Empty (placeholder)
- `index.md`: Empty (placeholder)
- `README.md`: Documentation only, not part of deployed app
- `Readme.md`: Duplicate (case-insensitive filesystem issue)
- `pull/2`: PR artifact directory

## Adding Features

### New Input Field
1. Add HTML input in `.card` section (lines ~50-180)
2. Extract value in `updateAll()` with `Number($('new_field').value) || default`
3. Wire to auto-update (existing listener at bottom handles new inputs automatically)

### New Calculation Output
1. Add display element in results section (lines ~180-205)
2. Compute value in `updateAll()` after existing calculations
3. Update with `$('out_new_metric').innerText = '$' + fmt(value)`

### Modifying Tax Logic
- All tax code in lines ~400-430
- Depreciation toggle affects `totalDeduction` calculation
- Tax refund added to `afterTaxCashflow` and chart data

## External Dependencies

- **jsPDF 2.5.1**: PDF generation (CDN: cdnjs.cloudflare.com)
- **Chart.js 4.3.0**: Visualization (CDN: cdn.jsdelivr.net)
- **Google Fonts**: Inter typeface for UI
- All loaded via CDN in `<head>` — no package.json or npm

## Testing Scenarios

**Positive cashflow property:**
- $400k, $550/wk rent, 6% interest, 20% deposit
- Should yield positive `out_cashflow`

**Negative gearing scenario:**
- $600k, $400/wk rent, 6.5% interest, 10% deposit
- Should show LMI, negative cashflow, tax refund

**PDF Export:**
- Captures all inputs, metrics, and chart as PNG
- Includes disclaimer at bottom
- Saved as `property-summary.pdf`

## Avoiding Common Mistakes

1. **Don't create separate files**: Everything belongs in `InvestorCalculator.html`
2. **LMI calculation is heuristic**: Never present as exact (lender-dependent)
3. **Interest calculation**: Use amortization schedule, not `loan × rate`
4. **Chart cleanup**: Always destroy before redraw or memory leaks occur
5. **Depreciation defaults off**: Assume old stock unless user enables
6. **Currency formatting**: Always use `fmt()` for AUD display consistency
