# Power Query ETL Transformation Summary

1. **Source Data Connection:** Connected to raw transactional Excel/CSV extracts.
2. **Data Cleansing:**
   - Applied `Text.Trim` and `Text.Clean` to all categorical string fields (`PolicyType`, `State`).
   - Replaced empty values in `ClaimAmount` with `0`.
3. **Data Type Enforcement:**
   - Converted all monetary fields to `Currency` (`Fixed Decimal Number`).
   - Converted date fields explicitly to `Date`.
4. **Dimension Table Extraction:**
   - Created `DimDate` dimension using custom M logic to cover all transaction dates continuously.
   - Merged geography lookup tables to standardize state abbreviations.
