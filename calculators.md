---
layout: page
title: Financial Calculators
permalink: /calculators/
---

Plan your financial future with our suite of disciplined investment tools. These calculators help you visualize the power of compounding and the impact of consistent investing.

<div class="calculators-container">
    <!-- SIP Calculator -->
    <div class="calc-card">
        <h2>SIP Calculator</h2>
        <div class="input-group">
            <label>Monthly Investment <span>₹<span id="sip-monthly-val">5000</span></span></label>
            <input type="range" id="sip-monthly" min="500" max="100000" step="500" value="5000" oninput="calculateSIP()">
        </div>
        <div class="input-group">
            <label>Expected Return Rate (p.a) <span><span id="sip-rate-val">12</span>%</span></label>
            <input type="range" id="sip-rate" min="1" max="30" step="0.5" value="12" oninput="calculateSIP()">
        </div>
        <div class="input-group">
            <label>Investment Period <span><span id="sip-period-val">10</span> Yr</span></label>
            <input type="range" id="sip-period" min="1" max="40" value="10" oninput="calculateSIP()">
        </div>
        <div class="calc-results">
            <div class="result-item"><span>Invested Amount</span> <span id="sip-invested">₹0</span></div>
            <div class="result-item"><span>Estimated Returns</span> <span id="sip-returns">₹0</span></div>
            <div class="result-item"><span>Total Value</span> <span id="sip-total">₹0</span></div>
        </div>
    </div>

    <!-- Step-up SIP Calculator -->
    <div class="calc-card">
        <h2>Step-up SIP Calculator</h2>
        <div class="input-group">
            <label>Initial Monthly SIP <span>₹<span id="step-monthly-val">5000</span></span></label>
            <input type="range" id="step-monthly" min="500" max="100000" step="500" value="5000" oninput="calculateStepUp()">
        </div>
        <div class="input-group">
            <label>Annual Step-up (%) <span><span id="step-up-val">10</span>%</span></label>
            <input type="range" id="step-up" min="1" max="50" value="10" oninput="calculateStepUp()">
        </div>
        <div class="input-group">
            <label>Expected Return Rate (p.a) <span><span id="step-rate-val">12</span>%</span></label>
            <input type="range" id="step-rate" min="1" max="30" step="0.5" value="12" oninput="calculateStepUp()">
        </div>
        <div class="input-group">
            <label>Investment Period <span><span id="step-period-val">10</span> Yr</span></label>
            <input type="range" id="step-period" min="1" max="40" value="10" oninput="calculateStepUp()">
        </div>
        <div class="calc-results">
            <div class="result-item"><span>Invested Amount</span> <span id="step-invested">₹0</span></div>
            <div class="result-item"><span>Estimated Returns</span> <span id="step-returns">₹0</span></div>
            <div class="result-item"><span>Total Value</span> <span id="step-total">₹0</span></div>
        </div>
    </div>

    <!-- Lumpsum Calculator -->
    <div class="calc-card">
        <h2>Lumpsum Calculator</h2>
        <div class="input-group">
            <label>Total Investment <span>₹<span id="lump-total-val">50000</span></span></label>
            <input type="range" id="lump-investment" min="5000" max="1000000" step="5000" value="50000" oninput="calculateLumpsum()">
        </div>
        <div class="input-group">
            <label>Expected Return Rate (p.a) <span><span id="lump-rate-val">12</span>%</span></label>
            <input type="range" id="lump-rate" min="1" max="30" step="0.5" value="12" oninput="calculateLumpsum()">
        </div>
        <div class="input-group">
            <label>Investment Period <span><span id="lump-period-val">10</span> Yr</span></label>
            <input type="range" id="lump-period" min="1" max="40" value="10" oninput="calculateLumpsum()">
        </div>
        <div class="calc-results">
            <div class="result-item"><span>Invested Amount</span> <span id="lump-invested">₹0</span></div>
            <div class="result-item"><span>Estimated Returns</span> <span id="lump-returns">₹0</span></div>
            <div class="result-item"><span>Total Value</span> <span id="lump-total-res">₹0</span></div>
        </div>
    </div>
</div>

<script>
function formatCurrency(num) {
    return "₹" + Math.round(num).toLocaleString('en-IN');
}

function calculateSIP() {
    const P = parseFloat(document.getElementById('sip-monthly').value);
    const r = parseFloat(document.getElementById('sip-rate').value) / 12 / 100;
    const n = parseFloat(document.getElementById('sip-period').value) * 12;

    document.getElementById('sip-monthly-val').innerText = P;
    document.getElementById('sip-rate-val').innerText = document.getElementById('sip-rate').value;
    document.getElementById('sip-period-val').innerText = document.getElementById('sip-period').value;

    const totalValue = P * ((Math.pow(1 + r, n) - 1) / r) * (1 + r);
    const invested = P * n;
    
    document.getElementById('sip-invested').innerText = formatCurrency(invested);
    document.getElementById('sip-returns').innerText = formatCurrency(totalValue - invested);
    document.getElementById('sip-total').innerText = formatCurrency(totalValue);
}

function calculateLumpsum() {
    const P = parseFloat(document.getElementById('lump-investment').value);
    const r = parseFloat(document.getElementById('lump-rate').value) / 100;
    const n = parseFloat(document.getElementById('lump-period').value);

    document.getElementById('lump-total-val').innerText = P;
    document.getElementById('lump-rate-val').innerText = document.getElementById('lump-rate').value;
    document.getElementById('lump-period-val').innerText = document.getElementById('lump-period').value;

    const totalValue = P * Math.pow(1 + r, n);
    
    document.getElementById('lump-invested').innerText = formatCurrency(P);
    document.getElementById('lump-returns').innerText = formatCurrency(totalValue - P);
    document.getElementById('lump-total-res').innerText = formatCurrency(totalValue);
}

function calculateStepUp() {
    const P = parseFloat(document.getElementById('step-monthly').value);
    const stepUp = parseFloat(document.getElementById('step-up').value) / 100;
    const r = parseFloat(document.getElementById('step-rate').value) / 100;
    const n = parseInt(document.getElementById('step-period').value);

    document.getElementById('step-monthly-val').innerText = P;
    document.getElementById('step-up-val').innerText = document.getElementById('step-up').value;
    document.getElementById('step-rate-val').innerText = document.getElementById('step-rate').value;
    document.getElementById('step-period-val').innerText = n;

    let totalValue = 0;
    let totalInvested = 0;
    let currentSIP = P;
    const monthlyRate = r / 12;

    for (let year = 1; year <= n; year++) {
        for (let month = 1; month <= 12; month++) {
            totalInvested += currentSIP;
            // Compound monthly
            totalValue = (totalValue + currentSIP) * (1 + monthlyRate);
        }
        currentSIP = currentSIP * (1 + stepUp);
    }

    document.getElementById('step-invested').innerText = formatCurrency(totalInvested);
    document.getElementById('step-returns').innerText = formatCurrency(totalValue - totalInvested);
    document.getElementById('step-total').innerText = formatCurrency(totalValue);
}

// Initial calculations
calculateSIP();
calculateLumpsum();
calculateStepUp();
</script>
