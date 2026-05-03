# 🌌 VGM Risk Engine & Synergy Allocator (Thin Client)

[![License: Dual](https://img.shields.io/badge/License-Dual-blue.svg)](LICENSE)
[![Python 3.10](https://img.shields.io/badge/Python-3.10-blue.svg)](https://python.org)
[![Zenodo DOI](https://img.shields.io/badge/DOI-10.5281%2Fzenodo.19959346-blue.svg)](https://zenodo.org/records/19959346)
[![API Status](https://img.shields.io/badge/API-Beta_Access-orange.svg)]()

> **🚀 May 2026 Update: Transition to Enterprise SaaS Architecture**  
> Due to overwhelming public interest (480+ clones in 7 days) and the integration of our proprietary Deep Learning models (VGMNet), the core risk-scoring engine has been securely migrated to a cloud-based API infrastructure. 
> 
> This repository now serves as the **Thin Client Integration** for Freqtrade, MT5, and custom trading bots.

---

## 🛰️ From Spacecraft Anomaly Detection to Crypto Markets

The **VGM Risk Engine** is not a standard trading bot. It is a mathematically grounded **Risk Firewall**. 

The system utilizes **ORAC-NT**—a template-free anomaly detection algorithm originally designed to identify thermal system failures in spacecraft and gravitational wave bursts. By applying the physics of Shannon Entropy ($H$) and Signal Energy ($E$), VGM detects structural regime shifts (market crashes) *before* standard indicators like RSI or MACD even react.

### The Synergy Formula (Patent Pending)
The Coordinator dynamically controls bot capital allocation using the following thermodynamic-inspired efficiency formula:

$$W = Q \cdot D - (T_{base} + \alpha \cdot H_{ORAC})$$

Where:
*   **Q** = Signal Quality (Win rate / Sharpe)
*   **D** = Diversification factor
*   **T_base** = Base threshold for entry
*   **H_ORAC** = Real-time systemic market entropy (The Chaos Factor)

When market entropy ($H$) spikes due to manipulation, flash crashes, or structural shifts, the $W$-score turns negative. The VGM API triggers an immediate **KILL-SWITCH** (`/stopbuy`), flattening your bot's risk exposure to **0%**.

---

## ⚙️ How It Works Now (The Thin Client)

To ensure ultra-low latency and protect the proprietary ONNX Deep Learning models, the heavy computational lifting (GARCH volatility forecasting, Hidden Markov Models, and ORAC-NT entropy calculation) is now handled entirely by our private cloud infrastructure.

Your local bot (e.g., Freqtrade) only needs a few lines of code to query the API before executing a trade:
```python
# Example: Freqtrade API Integration
def confirm_trade_entry(self, pair, order_type, amount, rate, **kwargs):
    payload = {"closes": self.get_closes(pair), "volumes": self.get_volumes(pair)}
    
    # Query the VGM Cloud Firewall
    response = requests.post(
        "[https://vgm-risk-engine.onrender.com/predict](https://vgm-risk-engine.onrender.com/predict)",
        json=payload,
        headers={"X-API-Key": "your-personal-api-key"}
    )
    
    result = response.json()
    
    # VGM acts as the ultimate gatekeeper
    if result["action"] == "BLOCK" or result["risk"] > 0.65:
        return False # Trade blocked, high entropy detected!
        
    return True # Clear skies, execute trade.
	
	 API Subscription TiersVGM Risk Engine operates on a "Thin Client" architecture. Your local trading bots execute the trades, while our Cloud API handles the complex mathematical risk scoring.TierPriceBest ForFeatures IncludedFree Beta$0Solo Devs / Testing60 req/min limit, Standard Risk Scoring (BUY/BLOCK), Basic HMM Regime Detection.PRO$25 / moRetail Algo TradersUnlimited requests, Dynamic Synergy Allocator, Freqtrade/MT5 Scripts, Low-latency execution.Premium$150 / moProp Firms / WhalesEverything in PRO + Pump & Dump protection, Per-symbol calibration, Priority Support.EnterpriseCustom (Starts at $1k/mo)Hedge Funds / InstitutionsPrivate Server Instance, 99.9% SLA, Custom Internal Integrations, NDA, Dedicated Quant Engineer.Note: We DO NOT sell the core source code (ONNX models, GARCH/ORAC backend). The proprietary engine remains securely hosted on our cloud infrastructure.🔑 How to Get API Access (Closed Beta)We are currently onboarding a select group of quantitative developers, algorithmic traders, and fund managers to test the API.If you want to protect your automated trading systems with aerospace-grade anomaly detection, please reach out to request an X-API-Key or a Free Beta Trial:📫 Contact the Developer:Email: kretski1@gmail.comTelegram: regdred 
	 Academic Citation & ResearchIf you are using concepts from the VGM Risk Engine in your own academic research, please cite our official preprint:Фрагмент от код@software{kretski_vgm_2026,
  author  = {Kretski, Dimitar},
  title   = {VGM Risk Engine: Real-Time Market Risk Scoring and Synergy Allocation},
  year    = {2026},
  publisher = {Zenodo},
  doi     = {10.5281/zenodo.19959346},
  url     = {[https://doi.org/10.5281/zenodo.19959346](https://doi.org/10.5281/zenodo.19959346)}
}
⚠️ DisclaimerTHIS SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND. VGM does NOT guarantee trading profits. All algorithmic trading involves severe financial risk. This is a risk management analysis tool, not financial advice. The author is not liable for any financial losses.


kretski1@gmail.com
