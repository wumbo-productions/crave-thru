# Crave Thru

## Table of Contents
1. [Overview](#Overview)
2. [Product Spec](#Product-Spec)
3. [Wireframes](#Wireframes)
4. [Schema](#Schema)

## Overview
### Description
This application will help users find a place to eat by presenting a random restaurant in their area. The user will be allowed to swipe in order to discard or save restaurants that they would be interested in visiting. Details like location, reviews, menu, and best sellers will be presented under the details of the restaurant. Ideally, users will be able to show what they ate, give feedback, see special events, and separate restaurants by category.

### App Evaluation
- **Category:** Food and Travel
- **Mobile:** 
    - Accessible
    - Efficiency for food search
    - Tools: Maps, Location | Bonus: Camera, Push Not.
- **Story:** 
    - Value: Most people have a hard time deciding where to eat, especially when visting a different city. There exists a need for an application that tailors a taste profile to identify possible eateries in there area. 
    - Friend/Peer responses:
        - "It would help discover new restaurants." - Anonymous
        - "Sounds so romantic." - Anonymous
        - "Nice. I would like that." - Beast
- **Market:**
    - Large market
    - User base: Large size (thousands)
    - Niche Group: Millenials/Gen-Z
    - Well-def. aud.: College aged adults (19 - 25)
- **Habit:**
    - Habit-forming app
    - 1 or 2 times a day
    - Consume app
- **Scope:**
    - Well-formed of scope? Realistic! We can finish it.
    - Technical challenging? Reasonable, yet a challenge.
    - Stripped-down version still interesting to build? Yes.
    - Clearly defined of product? Yes.

## Product Spec

### 1. User Stories (Required and Optional)

**Required Must-have Stories**

* New user registers for an account
* User logs in to new account
* User is recommended a random restaurant
* User taps image to see expanded details
* User accepts recomendation and it is stored in favorites
* User views favorites to choose a variety of restaurants to their liking
* User clicks on a restaurant
* User views best sellers and entire menu
* User copies address and inputs it into preferred navigation tool

**Optional Nice-to-have Stories**

* User can upload and rate the pricing/quality of the food they had eaten
* User can categorize their restaurants to eventful days such as Taco Tuesdays, Vegan, American, Mexican, etc.
* Best Sellers
* Users can add photos of the food they are eating


### 2. Screen Archetypes

* ##### Login / Register
   * User and password and submit
* ##### Image Carousel
   * Random nearby restaurant shown
* ##### Navigation Screen
   * Set up area to locate nearby restaurants
* ##### Expanded Details Page
    * User can view details regarding name, directions, menu, and more info 
   

### 3. Navigation

**Tab Navigation** (Tab to Screen)

* Favorited / Saved Restaurants
* Image Carousel
* List of Restaurants

**Flow Navigation** (Screen to Screen)

* #### Login
   * Image Carousel
* #### Image Carousel
   * Navigation Screen
   * Expanded Details

## Wireframes
### [BONUS] Digital Wireframes & Mockups
<img src="https://github.com/wumbo-productions/crave-thru/blob/master/wireframes.png" width=600>

### [BONUS] Interactive Prototype
<img src="https://github.com/wumbo-productions/crave-thru/blob/master/Crave-Thru.gif" width=182 height=408>

### Milestone 1
<img src="https://i.imgur.com/1ppo0SE.gif" width=182 height=408>

## Schema 
### Models
#### User
| Property  | Type | Description  |
| :---      |     :---:           |          ---: |
| userId    | int       | unique id for position in database  |
| username  | String    | unique username for login  |
| password  | String    | password for  login |
| image     | file      | app icon  |
| createdAt | DateTime  | date when created account  |
| visited_cities    | String ArrayList | cities user visited with restaurants they favorited  |

#### User Favorites
| Property  | Type | Description  |
| :---         |     :---:      |          ---: |
| userId            | int     | unique id for position in database  |
| restaurantName    | String  |  |
| image             | file    | restaurant icon/logo/food reference  |
| index             | int     | position in list  |
| location          | string  | used to know where restaurant is located  |
| typeOfFood        | String  | most known food  |
| distance          | int     | how far away from location  |

#### Carousel Favorites
| Property  | Type | Description  |
| :---         |     :---:      |          ---: |
| userId            | String  | unique id for position in database  |
| restaurantName    | String  |  |
| image             | file    | restaurant icon/logo/food reference  |
| index             | int     | position in list |

### Networking
- Home Screen
    - (Read/GET) Query all restaurants around current location
    - (Create/POST) Add restaurant to City Restaurant Favorites
    - (Create/POST) Add restaurant to "Favorite List" in "All Restaurants" tab to show favorited restaurants so far
    - (Read/GET) Get restaurant menu and "Customer Stories"
- Profile Screen
    - (Read/GET) Get City -> Restaurant Favorites 
    - (Read/GET) Profile information -> Username, Date Joined, Profile image
- All Restaurants Screen
    - (Read/GET) Query all restaurants around current location
- Maps Screen
    - (Read/GET) Get all restaurants within current location
