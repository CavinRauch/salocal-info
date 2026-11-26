South African fuel price forecast data
======================================

Published by SA Local Info: https://salocal.info/fuel-price-data/
Updated: 2026-11-26 20:33 SAST. New figures are added on most weekdays.
Licence: CC BY 4.0 (https://creativecommons.org/licenses/by/4.0/). Please credit "SA Local Info (salocal.info)" and link to
https://salocal.info/fuel-price-data/

Units
-----
All prices and changes are in South African cents per litre (100c = R1).
Change columns use the price direction: NEGATIVE = expected to get CHEAPER,
POSITIVE = expected to get DEARER.

Petrol figures are pump prices. Diesel and paraffin figures are wholesale
prices (the price filling stations pay); pump prices for diesel are not
regulated, but they move by about the same amount.

Inland = Gauteng (zone 9C). Coastal = coastal zone 1A (e.g. Cape Town, Durban,
Gqeberha). Other zones differ by a fixed transport cost and move by the same
amount.


1. sa-fuel-price-forecast-daily.csv
   One row per Central Energy Fund (CEF) daily report, 2026-03-12 to 2026-11-25.
   It is the running average for the current monthly window: how much each
   fuel is expected to change on the next adjustment date if nothing else
   changes. It is a forecast, not an official price.

  date
  petrol_93_expected_change_c
  petrol_95_expected_change_c
  diesel_500ppm_expected_change_c
  diesel_50ppm_expected_change_c
  paraffin_expected_change_c
  petrol_93_from_product_prices_c
  petrol_95_from_product_prices_c
  diesel_500ppm_from_product_prices_c
  diesel_50ppm_from_product_prices_c
  paraffin_from_product_prices_c
  petrol_93_from_exchange_rate_c
  petrol_95_from_exchange_rate_c
  diesel_500ppm_from_exchange_rate_c
  diesel_50ppm_from_exchange_rate_c
  paraffin_from_exchange_rate_c
  rand_per_us_dollar
  window_start
  window_end
  current_prices_effective
  change_expected_on
  cef_source_file

   *_expected_change_c      expected change, cents per litre
   *_from_product_prices_c  part caused by international product prices
   *_from_exchange_rate_c   part caused by the rand/US dollar exchange rate
                            (the two parts add up to the expected change)
   rand_per_us_dollar       average rand/dollar rate CEF used for the window
   window_start/window_end  the days CEF averaged
   current_prices_effective the official prices the forecast starts from
   change_expected_on       the next adjustment (first Wednesday of the month)
   cef_source_file          the CEF report the row was read from

2. sa-official-fuel-prices.csv
   Official prices set by the Department of Mineral and Petroleum Resources,
   one row per adjustment date and region, from 2026-08-05.

  effective_date
  region
  zone
  petrol_93_c
  petrol_95_c
  diesel_500ppm_c
  diesel_50ppm_c
  paraffin_c

3. sa-fuel-price-forecast-latest.json
   The latest forecast in one JSON file: current and expected prices for
   inland and coastal, the expected change and its two causes.

How the forecast works
----------------------
Every month the department compares what fuel costs to import (international
product prices, converted at the rand/dollar rate) with the price built into
the current pump price. CEF publishes the running daily average of that
difference (the over-recovery or under-recovery). Over-recovery means fuel is
priced higher than it costs, so the price is expected to drop by about that
amount; under-recovery means it is expected to rise. The official change can
differ because of levies, taxes, margins and slate adjustments, which this
data does not include.

Sources
-------
- Central Energy Fund (CEF), daily fuel price data: https://cefgroup.co.za
- Department of Mineral and Petroleum Resources (DMPR), fuel prices:
  https://www.dmpr.gov.za/Branches/Petroleum-Resources/Fuel-Prices
These organisations do not endorse SA Local Info. Figures are read from their
published files automatically and checked before publishing (the two causes
must add up, and CEF's starting prices must match the official prices).
Spotted an error? https://salocal.info/contact/
