# MercuryBookingAPI

## 2023/10/03
### Attractions
  * Fixed an issue with CancellationPolicy datebands being offset by 1 hour in some cases because of Daylight saving time.

### Entertainments
  * Autocomplete now handles special characters better in case of EVENT and EVENT_PERFORMER categories.
  * Search now uses 24h time format for the Time of the performances.
  * Search does not display performances in the past even if StartDate is in the past.
  * Search now accepts LanguageCode which will be considered for localization of the results.
  * Search's ExtendedResults are not limited to 10 anymore.
  * GetPerformanceAvailabilites now returns working redirectlinks.
