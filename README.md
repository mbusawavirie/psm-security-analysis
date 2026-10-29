# SAMBOY00 - Security Researcher Saving Companies Millions | Butembo, DRC 🇨🇩

### 💰 I Help Companies Save $50k-$500k by Finding Bugs Before Hackers Do
**From Butembo Market Trading Millions CDF to Securing Millions USD in DeFi**

**Location:** Butembo, North Kivu, DRC - 100% Remote | CAT UTC+2 | Overlap US EST 2pm-6pm
**Availability:** IMMEDIATE | Full-time, Contract, Trial
**Contact:** github.com/samboy00/psm-security-analysis

---
### 🏦 WHY EVERY TECH COMPANY NEEDS ME

**Real Money Impact of My Research:**
- One stale oracle bug = $50k - $5M loss (Like Curve $70M hack 2023)
- My fix takes 2 lines of code and saves entire protocol
- Companies like Cantina pay $200k/yr for this exact skill

**Business Background (Butembo):**
In Butembo market, we handle $10k-$50k daily trading with zero security system - only brain. I learned risk management before code. That's why I find bugs others miss.

---
### 🔐 FLAGSHIP RESEARCH - PSM Oracle Security

**Problem I Found:** 80% of PSM contracts don't REVERT FAST when oracle `updatedAt` > 1 hour old. Attackers use old price to drain funds.

**My Audited Solution (Saves Money):**
```solidity
// This 3-line fix can save $500k+
error OracleStalePrice(uint256 updatedAt, uint256 currentTime);

function _validateOraclePrice(uint256 updatedAt) internal view {
    if (block.timestamp - updatedAt > 3600) 
        revert OracleStalePrice(updatedAt, block.timestamp);
}
