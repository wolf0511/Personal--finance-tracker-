// JavaScript for saving data, generating charts, etc.

// Function to save the financial data to LocalStorage
function saveData() {
    let salary = document.getElementById("salary").value;
    let otherIncome = document.getElementById("other-income").value;
    let fuelCost = document.getElementById("fuel-cost").value;
    let shopping = document.getElementById("shopping").value;
    let houseRent = document.getElementById("house-rent").value;
    let otherCosts = document.getElementById("other-costs").value;
    let _401k = document.getElementById("401k").value;
    let stockInvestments = document.getElementById("stock-investments").value;
    let hsa = document.getElementById("hsa").value;
    let extraSavings = document.getElementById("extra-savings").value;

    let data = {
        salary,
        otherIncome,
        fuelCost,
        shopping,
        houseRent,
        otherCosts,
        _401k,
        stockInvestments,
        hsa,
        extraSavings
    };

    localStorage.setItem("financeData", JSON.stringify(data));

    // Calculate and display the net balance
    let netBalance = parseFloat(salary) + parseFloat(otherIncome) - (parseFloat(fuelCost) + parseFloat(shopping) + parseFloat(houseRent) + parseFloat(otherCosts));
    document.getElementById("net-balance").innerText = `$${netBalance.toFixed(2)}`;

    // Update charts (you'll need to define chart generation functions)
    updateCharts(data);
}

// Example function to update charts
function updateCharts(data) {
    // You can create your chart logic here using Chart.js
    console.log(data); // For testing
}

// Export data to CSV (example function)
function exportData() {
    let data = localStorage.getItem("financeData");
    if (!data) {
        alert("No data to export!");
        return;
    }

    data = JSON.parse(data);
    let csvContent = "Salary, Other Income, Fuel Cost, Shopping, House Rent, Other Costs, 401k, Stock Investments, HSA, Extra Savings\n";
    csvContent += `${data.salary}, ${data.otherIncome}, ${data.fuelCost}, ${data.shopping}, ${data.houseRent}, ${data.otherCosts}, ${data._401k}, ${data.stockInvestments}, ${data.hsa}, ${data.extraSavings}`;

    let blob = new Blob([csvContent], { type: "text/csv;charset=utf-8;" });
    let link = document.createElement("a");
    link.href = URL.createObjectURL(blob);
    link.download = "finance_data.csv";
    link.click();
}
