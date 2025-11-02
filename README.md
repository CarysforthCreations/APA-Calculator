[README.md](https://github.com/user-attachments/files/23291565/README.md)
# APA Calculator (Universal Credit Housing Costs)

A lightweight client-side web app that helps housing staff diagnose why an Alternative Payment Arrangement (APA) to a landlord
is **less than the rent** by matching the *exact* Universal Credit **Housing Costs Element (HCE)** amount.

## Key rules implemented
- **Monthly average uses 52 weeks minus rent-free weeks** (UC does not recognise 53-week years).
- **Penny-perfect** matching. The calculator only lists scenarios that exactly match the APA amount you received.
- Calculates all combinations of:
  - This year vs last year rent
  - Spare room deduction (0%, 14%, 25%)
  - Liability share (100%, 50%, optional 33.3%)
  - Non-dependant Housing Cost Contributions (HCC): 0..N people, testing both old & new monthly rates

> ⚠️ Update HCC monthly rates in **Settings** each April.

## How it works
1. Enter **weekly rent last year/this year**, **rent-free weeks**, and the **APA amount received (monthly)**.
2. The app computes monthly rent as `weekly × (52 − rent-free weeks) ÷ 12`.
3. It tests each scenario and lists only those whose HCE equals the APA **to the penny** (after stepwise rounding to 2dp).
   - Rounding is applied **after each step** in pence (liability → spare room deduction → HCC subtraction).

## Run locally
Open `index.html` in your browser. No build step needed.

## Deploy to GitHub Pages
Create a repo, upload the files, and enable **Settings → Pages** for the root.

---

**Updated:** 2025-11-02
