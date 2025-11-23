# Property Investment Calculator

A browser-based calculator for analysing Australian property investment scenarios. Enter property details, financial assumptions, and mortgage parameters to automatically compute:

- Upfront purchase costs
- Mortgage repayment amounts
- Cashflow impacts
- Custom scenarios via adjustable interest rates and deposit sizes
- Tax and depreciation effects
- Export of results to PDF

This project is ideal for investors assessing the viability of residential property purchases.

---

## 🚀 Current Functionality

### **1. Property & Loan Input Form**

The web interface includes fields for entering:

- Purchase price
- Weekly rent
- Strata fees
- Stamp duty assumptions
- Deposit amount
- Interest rate
- Loan term
- Other expenses (council, insurance, maintenance, management fees)
- Depreciation (Div 43 & Div 40)
- Tax bracket selection

---

### **2. Automatic Calculations**

Based on the provided values, the calculator computes:

#### **Upfront Costs**

- Deposit
- Stamp duty
- Transfer fees
- Mortgage registration fees
- LMI estimate (if deposit < 20%)
- Total upfront cost required

#### **Loan & Holding Costs**

- Loan principal and LVR
- Annual interest cost (first-year amortisation)
- Loan repayment estimate
- Gross rental yield
- Net rental yield
- Cashflow before and after expenses

#### **Tax & Depreciation**

- Annual depreciation (Div 43 + Div 40)
- Tax-deductible loss
- Tax refund at selected rate
- After-tax cashflow

---

### **3. Adjustable Parameters**

You can dynamically modify:

- Deposit amount (percentage)
- Interest rate (e.g., 5%–8%)
- Loan term (years)
- Expenses (strata, maintenance, council, management)
- Depreciation values
- Tax bracket

This supports scenario modelling for interest-rate changes, different borrowing strategies, and tax outcomes.

---

### **4. PDF Export**

Users can export the calculated results to a formatted PDF report, including:

- All input fields
- Summary of costs
- Cashflow tables
- Key metrics (yield, cashflow, total upfront)
- Tax and depreciation summary

---

## 🧑‍💻 Project Structure

- `InvestorCalculator.html` – Main UI form and layout
- `script.js` – Calculation logic & PDF generation
- `styles.css` – Basic styling

(Actual filenames may vary based on your implementation.)

---

## 📦 Installation & Usage

No build steps required.

1. Download all project files
2. Open `index.html` in any modern browser
3. Enter property details
4. View instant calculations
5. Export report as PDF if desired

---

## 🔮 Planned / Future Enhancements

The following features are planned:

### **1. Multi-Year Cashflow Projections**

- 5, 10, and 20 year forecasts
- Capital growth assumptions
- Rent growth assumptions
- Compounding expenses
- Loan amortisation tables

---

### **2. Tax Modelling & Negative Gearing Analysis**

- Tax deduction estimation
- After-tax cashflow
- Depreciation schedules (plant & building)
- Investor-tier marginal tax bracket support

---

### **3. Advanced Loan Features**

- Interest-only period modelling
- Offset account impact
- Variable vs fixed split loans

---

### **4. Save & Load Scenarios**

- Local storage persistence
- Ability to compare multiple properties side-by-side

---

### **5. UI Enhancements**

- Dark mode
- Graphs (cashflow vs years)
- Mobile-friendly improvements

---

## 🤝 Contributions

Feature requests and enhancements are welcome.

---

## 📄 License

MIT License (modify as needed).
