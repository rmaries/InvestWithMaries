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
            <div class="input-header">
                <label for="sip-monthly-num">Monthly Investment</label>
                <div class="input-number-container">
                    <span class="currency-prefix">₹</span>
                    <input type="number" id="sip-monthly-num" min="500" max="100000" step="500" value="5000" oninput="syncInput('sip-monthly', this.value, 'range'); calculateSIP();">
                </div>
            </div>
            <input type="range" id="sip-monthly" min="500" max="100000" step="500" value="5000" oninput="syncInput('sip-monthly-num', this.value, 'number'); calculateSIP();">
        </div>
        <div class="input-group">
            <div class="input-header">
                <label for="sip-rate-num">Expected Return Rate (p.a)</label>
                <div class="input-number-container">
                    <input type="number" id="sip-rate-num" min="1" max="30" step="0.5" value="12" oninput="syncInput('sip-rate', this.value, 'range'); calculateSIP();">
                    <span class="suffix">%</span>
                </div>
            </div>
            <input type="range" id="sip-rate" min="1" max="30" step="0.5" value="12" oninput="syncInput('sip-rate-num', this.value, 'number'); calculateSIP();">
        </div>
        <div class="input-group">
            <div class="input-header">
                <label for="sip-period-num">Investment Period (Years)</label>
                <div class="input-number-container">
                    <input type="number" id="sip-period-num" min="1" max="40" value="10" oninput="syncInput('sip-period', this.value, 'range'); calculateSIP();">
                    <span class="suffix">Yr</span>
                </div>
            </div>
            <input type="range" id="sip-period" min="1" max="40" value="10" oninput="syncInput('sip-period-num', this.value, 'number'); calculateSIP();">
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
            <div class="input-header">
                <label for="step-monthly-num">Initial Monthly SIP</label>
                <div class="input-number-container">
                    <span class="currency-prefix">₹</span>
                    <input type="number" id="step-monthly-num" min="500" max="100000" step="500" value="5000" oninput="syncInput('step-monthly', this.value, 'range'); calculateStepUp();">
                </div>
            </div>
            <input type="range" id="step-monthly" min="500" max="100000" step="500" value="5000" oninput="syncInput('step-monthly-num', this.value, 'number'); calculateStepUp();">
        </div>
        <div class="input-group">
            <div class="input-header">
                <label for="step-up-num">Annual Step-up</label>
                <div class="input-number-container">
                    <input type="number" id="step-up-num" min="1" max="50" value="10" oninput="syncInput('step-up', this.value, 'range'); calculateStepUp();">
                    <span class="suffix">%</span>
                </div>
            </div>
            <input type="range" id="step-up" min="1" max="50" value="10" oninput="syncInput('step-up-num', this.value, 'number'); calculateStepUp();">
        </div>
        <div class="input-group">
            <div class="input-header">
                <label for="step-rate-num">Expected Return Rate (p.a)</label>
                <div class="input-number-container">
                    <input type="number" id="step-rate-num" min="1" max="30" step="0.5" value="12" oninput="syncInput('step-rate', this.value, 'range'); calculateStepUp();">
                    <span class="suffix">%</span>
                </div>
            </div>
            <input type="range" id="step-rate" min="1" max="30" step="0.5" value="12" oninput="syncInput('step-rate-num', this.value, 'number'); calculateStepUp();">
        </div>
        <div class="input-group">
            <div class="input-header">
                <label for="step-period-num">Investment Period (Years)</label>
                <div class="input-number-container">
                    <input type="number" id="step-period-num" min="1" max="40" value="10" oninput="syncInput('step-period', this.value, 'range'); calculateStepUp();">
                    <span class="suffix">Yr</span>
                </div>
            </div>
            <input type="range" id="step-period" min="1" max="40" value="10" oninput="syncInput('step-period-num', this.value, 'number'); calculateStepUp();">
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
            <div class="input-header">
                <label for="lump-investment-num">Total Investment</label>
                <div class="input-number-container">
                    <span class="currency-prefix">₹</span>
                    <input type="number" id="lump-investment-num" min="5000" max="1000000" step="5000" value="50000" oninput="syncInput('lump-investment', this.value, 'range'); calculateLumpsum();">
                </div>
            </div>
            <input type="range" id="lump-investment" min="5000" max="1000000" step="5000" value="50000" oninput="syncInput('lump-investment-num', this.value, 'number'); calculateLumpsum();">
        </div>
        <div class="input-group">
            <div class="input-header">
                <label for="lump-rate-num">Expected Return Rate (p.a)</label>
                <div class="input-number-container">
                    <input type="number" id="lump-rate-num" min="1" max="30" step="0.5" value="12" oninput="syncInput('lump-rate', this.value, 'range'); calculateLumpsum();">
                    <span class="suffix">%</span>
                </div>
            </div>
            <input type="range" id="lump-rate" min="1" max="30" step="0.5" value="12" oninput="syncInput('lump-rate-num', this.value, 'number'); calculateLumpsum();">
        </div>
        <div class="input-group">
            <div class="input-header">
                <label for="lump-period-num">Investment Period (Years)</label>
                <div class="input-number-container">
                    <input type="number" id="lump-period-num" min="1" max="40" value="10" oninput="syncInput('lump-period', this.value, 'range'); calculateLumpsum();">
                    <span class="suffix">Yr</span>
                </div>
            </div>
            <input type="range" id="lump-period" min="1" max="40" value="10" oninput="syncInput('lump-period-num', this.value, 'number'); calculateLumpsum();">
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

function syncInput(targetId, sourceValue, type) {
    const targetEl = document.getElementById(targetId);
    if (!targetEl) return;

    if (type === 'range') {
        const numVal = parseFloat(sourceValue);
        if (!isNaN(numVal)) {
            const min = parseFloat(targetEl.min);
            const max = parseFloat(targetEl.max);
            targetEl.value = Math.min(Math.max(numVal, min), max);
        }
    } else {
        targetEl.value = sourceValue;
    }
}

function calculateSIP() {
    const P = parseFloat(document.getElementById('sip-monthly-num').value) || 0;
    const r = parseFloat(document.getElementById('sip-rate-num').value) / 12 / 100;
    const n = parseFloat(document.getElementById('sip-period-num').value) * 12;

    let totalValue = 0;
    if (r === 0) {
        totalValue = P * n;
    } else {
        totalValue = P * ((Math.pow(1 + r, n) - 1) / r) * (1 + r);
    }
    const invested = P * n;
    
    document.getElementById('sip-invested').innerText = formatCurrency(invested);
    document.getElementById('sip-returns').innerText = formatCurrency(totalValue - invested);
    document.getElementById('sip-total').innerText = formatCurrency(totalValue);
}

function calculateLumpsum() {
    const P = parseFloat(document.getElementById('lump-investment-num').value) || 0;
    const r = parseFloat(document.getElementById('lump-rate-num').value) / 100;
    const n = parseFloat(document.getElementById('lump-period-num').value) || 0;

    const totalValue = P * Math.pow(1 + r, n);
    
    document.getElementById('lump-invested').innerText = formatCurrency(P);
    document.getElementById('lump-returns').innerText = formatCurrency(totalValue - P);
    document.getElementById('lump-total-res').innerText = formatCurrency(totalValue);
}

function calculateStepUp() {
    const P = parseFloat(document.getElementById('step-monthly-num').value) || 0;
    const stepUp = parseFloat(document.getElementById('step-up-num').value) / 100;
    const r = parseFloat(document.getElementById('step-rate-num').value) / 100;
    const n = parseInt(document.getElementById('step-period-num').value) || 0;

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
