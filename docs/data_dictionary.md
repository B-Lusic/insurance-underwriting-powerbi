# Data Dictionary - Insurance Underwriting Data Model

## Table: `FactPolicy`
Primary fact table storing policy issuance details.

| Column Name | Data Type | Key Type | Description |
|---|---|---|---|
| `PolicyID` | Integer | Primary Key | Unique identifier for each policy |
| `CustomerID` | Integer | Foreign Key | Links to `DimCustomer` |
| `PolicyTypeID` | Integer | Foreign Key | Links to `DimPolicyType` |
| `EffectiveDate` | Date | Foreign Key | Links to `DimDate` |
| `WrittenPremium` | Currency | Measure | Total premium bound on the policy |
| `EarnedPremium` | Currency | Measure | Premium recognized as revenue over time |

## Table: `FactClaims`
Fact table recording reported claim events.

| Column Name | Data Type | Key Type | Description |
|---|---|---|---|
| `ClaimID` | Integer | Primary Key | Unique identifier for each claim event |
| `PolicyID` | Integer | Foreign Key | Links to `FactPolicy` |
| `ClaimDate` | Date | Foreign Key | Date claim was filed |
| `ClaimAmount` | Currency | Measure | Total dollar value of settled or reserved claim |
| `ClaimStatus` | Text | Dimension | Status (`Open`, `Closed`, `In Review`) |
