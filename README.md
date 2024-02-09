# MercuryBookingAPI

## 2024/02/09
### Entertainment
  * EventInfoResponse entities now contain AttributeIds.
  * PerformanceResults in Search and SearchPagination responses now contain the AttributeIds of the relevant event.

## 2024/01/30
### Entertainment
  * Added performers to EventInfo endpoint's response.
  * Updated import and mapping for tengroup supplier to support the display of multiple TicketTypes.
  * Added SendMethod and DefaultSendMethod to GetPerformanceAvailabilitiesResponse's SupplierPerformanceAvailability. These provide further details about the send methods if options are provided by the supplier. (Currently only supported by ingresso.)

## 2023/11/21
### Entertainment
  * FromPrice and PromoCode has been added to GetPerformanceAvailabilitiesResponse's SupplierPerformanceAvailability.
  * TotalPrice has been added to ReserveTicketsResponse.
  * Fixed an issue for GetPerformances where Events with a long duration would not return all Performances. (e.g. EventId 182850)

## 2023/11/17
### Entertainment
  * EventInfo, VenueInfo, PerformerInfo endpoints now take a list of Ids.
  * EventDetails extended with Description and Venue's StaticSeatmapUrl.

## 2023/11/13
### Entertainment
  * Added SearchEvents endpoint.
  * TicketsAvailable is now nullable in GetPerformanceAvailabilitiesResponse, **null indicating unlimited** amount of tickets available for the Priceband. (SupplierPerformanceAvailabilities/AvailabilityDetails/TicketTypes/PriceBands/TicketsAvailable)

### BookingFlow
  * BookingDetails has been extended with EntertainmentProductOptions for entertainment specific details. (BookingDetailsResponseItems/BookingComponentDetails/EntertainmentProductOptions)

### Dining
  * First version of Autocomplete and VenueAvailability endpoints.

## 2023/10/20
### Entertainments
  * Search now applies SearchCategory filtering for all type of search (not just Location).
  * When Searching by EventId, ExtendedResults may now contain performances from the same Venue when better matches are not found.
  * When Searching by PerformerId, ExtendedResults may now contain performances regardless of location.
  * Fixed an issue which caused Search to sporadically fail.

## 2023/10/13
### Entertainments
  * Search now accepts a list of SearchCategories. Empty list of SearchCategories apply no filtering on the resultset. Multiple SearchCategories in the list returns performances that belong to any of the provided categories ('OR' relationship).
  * Refreshed imported data from suppliers.

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
