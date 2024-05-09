Travel DB Schema:

User(userID, name, email, phone_number)
	PK: userID

City(cityID, name)
	PK: cityID

Restaurant(restaurantID, name, address, price_point, rating, city)
	PK: restaurantID
	FK: city → City

Activity(activityID, name, location, price, rating, city)
	PK: activityID
	FK: city → City

Nightlife(nightlifeID, name, address, price_point, rating, city)
	PK: nightlifeID
	FK: city → City

UserTripRelation(relationID, restaurants (M2M), activities (M2M), nightlife (M2M), user, city)
	PK: relationID
	FK: user → User
	FK: city → City
	
*for restaurants, activities, nightlife, they refer back to their entities  (restaurants → Restaurant, activities → Activity, nightlife → Nightlife)

For example: 

UserTripRestaurants(relationID, user, restaurant)
	PK: relationID
	FK: user → User
	FK: restaurant → Restaurant

UserTripActivities(relationID, user, activity)
	PK: relationID
	FK: user → User
	FK: activities → Activity

UserTripNightlife(relationID, user, nightlife)
	PK: relationID
	FK: user → User
	FK: nightlife → Nightlife
