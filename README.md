# THE-STRAIT-OF-HORMUZ-
Exploring the intersection of global energy markets and economic stability. Currently developing a Python-based Strait of Hormuz Risk Simulator using real-world EU energy data to model supply chain shocks and sectorial impacts.


import pandas as pd

# 1. Load the real data from your Excel file
route = r"C:\Users\itbms01\Downloads\Weekly Oil Bulletin Weekly prices with Taxes - 2024-02-19.xlsx"
df = pd.read_excel(route)

# 2. Extract price for AUSTRIA (Row 1, Column 2 based on your previous output)
# Price is per 1000L (including taxes)
base_price_at = float(df.iloc[1, 2])
liter_price_at = base_price_at / 1000

print("⚠️ SCENARIO: TOTAL CLOSURE OF THE STRAIT OF HORMUZ (100%) ⚠️")
print(f"Current Price in Austria (from Excel): €{liter_price_at:.2f} per liter")
print("-" * 60)

# 3. Economic Shock Logic (100% Blockage)
# A total closure removes 21% of global crude. Historically, this triggers a 2x to 3x price multiplier.
shock_factor = 2.5  # Projected price multiplication due to market panic
new_price_at = liter_price_at * shock_factor

print(f"PROJECTED FUEL PRICE IN AUSTRIA: €{new_price_at:.2f} per liter")

# 4. SECTORIAL IMPACT ANALYSIS FOR AUSTRIA
print("\n--- DETAILED SECTORIAL IMPACT IN AUSTRIA ---")

sectors = {
    "Logistics & Freight": {
        "Effect": "Partial Paralysis.",
        "Detail": "Diesel accounts for 60% of oil use in AT. Freight costs would surge by ~150%."
    },
    "Manufacturing Industry": {
        "Effect": "40% Increase in Operational Costs.",
        "Detail": "Critical for Upper Austria's chemical/steel clusters. High risk of 'Kurzarbeit' (short-time work)."
    },
    "Agriculture": {
        "Effect": "Fertilizer & Harvest Crisis.",
        "Detail": "Food production costs spike due to agricultural diesel and gas-linked chemicals."
    },
    "Household Energy": {
        "Effect": "Energy Inflation.",
        "Detail": "Despite high hydropower, the Merit Order effect would drive electricity bills up."
    }
}

for sector, info in sectors.items():
    print(f"\n🔹 {sector}: {info['Effect']}")
    print(f"   {info['Detail']}")

# 5. National Risk Conclusion
print("\n" + "="*60)
print("EMERGENCY STATUS: CRITICAL")

print("Austria would activate strategic oil reserves (sufficient for ~90-100 days).")
print("Domino Effect: Estimated GDP drop of -3.5% within the first six months.")
print("="*60)

# Key Analysis Highlights:
The Price Spike: The code calculates a jump to roughly €4.00/liter. This is based on "inelastic demand," meaning people and companies can't stop buying fuel immediately, causing prices to explode.
The Austrian Context: Unlike coastal nations, Austria is a landlocked transit hub. If Hormuz closes, the cost of trucking goods from ports like Rotterdam or Trieste to Vienna would make local inflation much higher than the EU average.
Energy Reserves: It mentions the 90-day reserve, which is a legal requirement in Austria to prevent a total standstill during such geopolitical crises.
