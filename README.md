# jasobrien.github.io

Personal GitHub Pages site featuring a comprehensive Australian Property Investment Calculator.

[![GitHub Pages](https://img.shields.io/badge/GitHub%20Pages-Live-brightgreen)](https://jasobrien.github.io/)

---

## 📖 Overview

This repository hosts a personal GitHub Pages website that provides tools for analyzing Australian property investment opportunities. The main feature is a sophisticated, browser-based property investment calculator designed for investors assessing residential property purchases in New South Wales.

---

## 🚀 Features

### Property Investment Calculator

A comprehensive, single-page application (`InvestorCalculator.html`) that helps investors analyze property investment scenarios with detailed financial modeling.

#### **Input Capabilities**

The calculator accepts the following property and loan parameters:

- **Property Details:**
  - Purchase price
  - Weekly rental income
  - Quarterly strata fees
  - Property management percentage
  - Annual maintenance allowance

- **Loan Parameters:**
  - Deposit percentage (5-80%)
  - Interest rate (annual %)
  - Loan term (1-50 years)
  - Loan application and valuation fees

- **Upfront Costs:**
  - Conveyancing/legal fees
  - Building and pest inspection fees
  - Lender's Mortgage Insurance (LMI) estimation
  
- **Depreciation (Investment Properties):**
  - Division 43 (building/capital depreciation)
  - Division 40 (plant & equipment)
  
- **Tax Information:**
  - Selectable tax brackets (30%, 37%, 45%)

---

#### **Automatic Calculations**

The calculator performs comprehensive financial analysis including:

**Upfront Costs Analysis:**
- Deposit amount
- NSW stamp duty (using tiered band structure)
- Transfer and registration fees
- LMI estimates (when deposit < 20%)
- Total upfront capital required

**Loan & Cashflow Analysis:**
- Loan amount and LVR (Loan-to-Value Ratio)
- Monthly principal + interest repayments
- Annual interest costs (first-year amortization)
- Gross rental yield
- Net rental yield (before interest)
- Annual operating costs (strata, council, water, insurance, management fees)
- Net cashflow (before and after interest)

**Tax & Depreciation Module:**
- Annual depreciation calculations (Division 43 + Division 40)
- Tax-deductible losses
- Estimated tax refunds based on selected bracket
- After-tax cashflow projections

**Additional Analytics:**
- Minimum weekly rent calculation for cashflow-positive scenarios
- Interactive visual charts showing income vs. expenses breakdown
- 20-year capital appreciation projection with adjustable growth rates

---

#### **Interactive Features**

- **Real-time Updates:** All calculations update automatically as inputs change
- **Scenario Modeling:** Adjust interest rates, deposit amounts, and expenses to compare scenarios
- **Visual Analytics:** 
  - Bar charts for cashflow breakdown
  - Line charts for property value appreciation over time
- **PDF Export:** Generate comprehensive investment reports with all calculations and charts
- **Responsive Design:** Works on desktop, tablet, and mobile devices
- **Smart Validation:** Automatic LMI checkbox when deposit is below 20%

---

## 🗂️ Repository Structure

```
jasobrien.github.io/
├── InvestorCalculator.html    # Main property calculator (self-contained)
├── index.html                  # Homepage (placeholder)
├── index.md                    # Homepage markdown (placeholder)
├── README.md                   # This file
└── .gitignore                  # Git ignore rules
```

**Note:** The `InvestorCalculator.html` file is completely self-contained with embedded CSS, JavaScript, and all functionality. There are no separate `script.js` or `styles.css` files.

---

## 🌐 Deployment

This site is deployed using GitHub Pages and is automatically available at:

**https://jasobrien.github.io/**

### How GitHub Pages Works

- The repository name `jasobrien.github.io` automatically enables GitHub Pages
- Content is served directly from the repository
- Changes pushed to the main branch are automatically deployed
- The calculator is accessible at: `https://jasobrien.github.io/InvestorCalculator.html`

---

## 💻 Local Development

No build process or dependencies are required. To run locally:

1. **Clone the repository:**
   ```bash
   git clone https://github.com/jasobrien/jasobrien.github.io.git
   cd jasobrien.github.io
   ```

2. **Open in browser:**
   ```bash
   # Using Python 3
   python -m http.server 8000
   
   # Or simply open the file directly
   open InvestorCalculator.html
   ```

3. **Access the calculator:**
   - Navigate to `http://localhost:8000/InvestorCalculator.html`
   - Or open the file directly in any modern web browser

---

## 🔧 Technologies Used

- **HTML5** - Semantic markup and structure
- **CSS3** - Modern styling with custom properties and responsive design
- **Vanilla JavaScript** - No frameworks, pure ES6+ JavaScript
- **Chart.js** - Interactive data visualization
- **jsPDF** - Client-side PDF generation
- **Google Fonts** - Inter font family

---

## 📚 Usage Guide

### Basic Workflow

1. **Open the Calculator:** Navigate to `InvestorCalculator.html`
2. **Enter Property Details:** Fill in purchase price, rent, and property expenses
3. **Configure Loan Parameters:** Set deposit percentage, interest rate, and loan term
4. **Review Calculations:** Instant calculation of all metrics
5. **Analyze Results:** Review cashflow, yields, and tax implications
6. **Export Report:** Download a PDF summary of the analysis

### Advanced Features

- **Capital Appreciation Modeling:** Adjust the expected annual capital gain percentage to see 20-year property value projections
- **Tax Optimization:** Toggle depreciation on/off to compare new vs. established property investments
- **Scenario Comparison:** Use the reset button to restore defaults and compare multiple properties

---

## 🔮 Future Enhancements

The following features are planned for future development:

### High Priority

- [ ] **Multi-Property Comparison**
  - Side-by-side comparison interface
  - Comparison matrix with key metrics
  - Save/load multiple scenarios
  
- [ ] **Enhanced Cash Flow Projections**
  - Detailed year-by-year cashflow tables (5, 10, 20 years)
  - Rent growth modeling with adjustable rates
  - Expense inflation modeling
  - Complete loan amortization schedules
  
- [ ] **Advanced Tax Features**
  - Capital Gains Tax (CGT) calculator
  - 50% CGT discount for assets held > 12 months
  - Detailed depreciation schedules over property lifetime
  - Medicare levy calculations

### Medium Priority

- [ ] **Loan Feature Enhancements**
  - Interest-only period modeling
  - Offset account impact calculations
  - Redraw facility considerations
  - Split loan scenarios (fixed + variable)
  - Extra repayment impact analysis
  
- [ ] **Data Persistence**
  - Local storage for saving calculations
  - Export/import scenarios as JSON
  - Browser-based calculation history
  
- [ ] **Multi-State Support**
  - Victoria stamp duty calculations
  - Queensland stamp duty calculations
  - Other Australian states/territories
  - First Home Buyer concessions by state

### Low Priority

- [ ] **UI/UX Improvements**
  - Dark mode toggle
  - Enhanced mobile responsive design
  - Collapsible sections for better organization
  - Tooltips with explanations for each field
  - Keyboard shortcuts
  
- [ ] **Additional Features**
  - Currency exchange rates for international investors
  - Rental vacancy rate modeling
  - Property maintenance cost estimator
  - Insurance comparison tools
  - Integration with property listing APIs

### Research & Exploration

- [ ] **Analytics & Insights**
  - Investment score/rating system
  - Comparison against market benchmarks
  - Risk assessment metrics
  - Break-even analysis charts
  
- [ ] **Automation**
  - Automatic stamp duty updates
  - Interest rate trend data integration
  - Property price index integration

---

## ⚠️ Disclaimer

This calculator is provided for **informational and educational purposes only** and does not constitute financial, legal, tax, or investment advice. 

**Important Notes:**
- Always consult with qualified professionals (financial advisors, accountants, solicitors) before making investment decisions
- Stamp duty calculations are estimates based on NSW tiered bands and may not reflect actual amounts
- Tax calculations are simplified and may not account for all individual circumstances
- LMI estimates are approximate and actual costs vary by lender
- Interest rates, property values, and rental yields can fluctuate
- Past performance is not indicative of future results

---

## 🤝 Contributing

Contributions, issues, and feature requests are welcome!

### How to Contribute

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/AmazingFeature`)
3. Commit your changes (`git commit -m 'Add some AmazingFeature'`)
4. Push to the branch (`git push origin feature/AmazingFeature`)
5. Open a Pull Request

### Reporting Issues

If you find a bug or have a suggestion, please [open an issue](https://github.com/jasobrien/jasobrien.github.io/issues).

---

## 📄 License

This project is open source and available under the [MIT License](LICENSE).

---

## 📧 Contact

**Jason O'Brien**
- GitHub: [@jasobrien](https://github.com/jasobrien)
- Website: [https://jasobrien.github.io](https://jasobrien.github.io)

---

## 🙏 Acknowledgments

- Built with vanilla JavaScript for maximum compatibility and performance
- Chart.js for data visualization
- jsPDF for report generation
- NSW Revenue for stamp duty calculation reference

---

*Last Updated: December 2025*
