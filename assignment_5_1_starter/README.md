# Will a customer Accept the Coupon?

The goal of this study is to use the survey data collected from UCI Machine Learning repository and help determine characteristics
for driver to accept certain coupons


# Getting Started

### Dependencies

* Juypyter note book.
* Data Description
    * 1. User attributes
        *  Gender: male, female
        *  Age: below 21, 21 to 25, 26 to 30, etc.
        *  Marital Status: single, married partner, unmarried partner, or widowed
        *  Number of children: 0, 1, or more than 1
        *  Education: high school, bachelors degree, associates degree, or graduate degree
        *  Occupation: architecture & engineering, business & financial, etc.
        *  Annual income: less than \\$12500, \\$12500 - \\$24999, \\$25000 - \\$37499, etc.
        *  Number of times that he/she goes to a bar: 0, less than 1, 1 to 3, 4 to 8 or greater than 8
        *  Number of times that he/she buys takeaway food: 0, less than 1, 1 to 3, 4 to 8 or greater
        than 8
        *  Number of times that he/she goes to a coffee house: 0, less than 1, 1 to 3, 4 to 8 or
        greater than 8
        *  Number of times that he/she eats at a restaurant with average expense less than \\$20 per
        person: 0, less than 1, 1 to 3, 4 to 8 or greater than 8
        *  Number of times that he/she goes to a bar: 0, less than 1, 1 to 3, 4 to 8 or greater than 8
        

    2. Contextual attributes
        * Driving destination: home, work, or no urgent destination
        * Location of user, coupon and destination: we provide a map to show the geographical
        location of the user, destination, and the venue, and we mark the distance between each
        two places with time of driving. The user can see whether the venue is in the same
        direction as the destination.
        * Weather: sunny, rainy, or snowy
        * Temperature: 30F, 55F, or 80F
        * Time: 10AM, 2PM, or 6PM
        * Passenger: alone, partner, kid(s), or friend(s)


    3. Coupon attributes
        - time before it expires: 2 hours or one day


### Analysis
#### Coupon acceptance for Bar
* Bar acceptance rate: Compare potential features against bar coupon acceptance rate
    * The data itself is not proportionally balanced which is exactly that we are observing 41% of driver accepted the coupon vs 59% of those who ignore the coupon
    * In the anlaysis, we evaluate a couple features that might contribute to Bar coupon acceptance rate such as Temperature, Social drinker vs Occasional drinkder, different set of cohort of people who visit bar at least once a month, feature with kids, occupation. etc
    * For folks who visit the bar at least 3 times, it is clearly shows that they are more likely to accept a bar Coupon (73% vs 37%)
    * For folks age 25 or above and visit bar at least once a month shows a slightly difference (61% vs 54%)
    * For folk with 1 or more passenger to the bar with no kid and occupation other than Farming also show a difference (62% vs 55%)


#### Coupon acceptance for Carry out & Take away
* Carry out & Take away acceptance rate: Compare potential features against carry out coupon acceptance rate
    * Passenger: the difference is non-noticeable while passenger with Friends are more likely to accept the coupon (75%)
    * Weather: Under sunny weather, more people intend to accept the coupon (76%). This might also due to more travler on the road
    * Expiration: it seems like the soon they reponse to the coupon, they more likely they accepted the coupon (78%)
    * Marital Status: Widow are more likely to accept take away coupon and they (84%)
    * Occupation: This is an interesting one, while the total sample of each occupation can play huge factors. Building & Grounds cleansing mainteance, construction & Extraction, protective service are the 3 highest occupation with take out coupon acceptance rate



## Authors

Contributors names and contact info

ex. Mark Peng

