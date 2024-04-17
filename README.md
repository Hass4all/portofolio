Project Name: Taxibook

Introduction Taxibook is a convenient taxi booking application that allows users to easily book rides to their desired destinations. Visit our deployed site https://tinyurl.com/Taxibookuk experience seamless taxi booking. http://127.0.0.1:5500/index.html#

Final Project Blog Article Read our final project blog article [here] to learn more about the development process and key features of Taxibook.

Author(s) LinkedIn Connect with the authors on LinkedIn: Author 1[ https://www.linkedin.com/in/hassan-rami-chalf-105165304?lipi=urn%3Ali%3Apage%3Ad_flagship3_profile_view_base_contact_details%3BgIzV3%2Fn3Tu6agHIylQm%2FaA%3D%3D [Author 2](Amer Joutey) https://www.linkedin.com/in/amer-t-87666224a?lipi=urn%3Ali%3Apage%3Ad_flagship3_profile_view_base_contact_details%3Blz%2BpRI6ZQKSksN1JgRVs5Q%3D%3D

Installation To install Taxibook, follow these steps:

Clone the repository to your local machine.
Install the necessary dependencies using npm install.
Configure your environment variables.
Start the application with npm start.
Usage With Taxibook, users can:

Easily book a taxi by entering their pickup and drop-off locations.
View real-time updates on the driver's location and estimated time of arrival.
Rate and provide feedback on their ride experience.
Contributing We welcome contributions from the community. Please refer to our Contribution Guidelines for more information on how to get involved.

Related Projects Explore other projects by our team:

RideShare - A carpooling application for daily commuters.
DeliveryNow - An on-demand delivery service platform.
Licensing Taxibook is licensed under the Mdc corporation.UK(LICENSE).

Screenshot Taxibook Screenshot(taxibook.png)

15-04-2024
Taxibook App project

Passenger App Screen Flow Splash Screen

The screen will show the passenger for a few seconds, wherein the background app will check if there is a constant internet connection and also GPS of the devices is on. If either one is off, the app raises a popup message insisting the user turn on both.

Sign in

The application will ask the passenger to Sign in with email ID/Phone number and a password. Upon successful login, the passenger will navigate directly to the App landing screen “Book a Cab” screen.

Forgot Password The screen will allow the passenger to generate a new password when the passenger doesn’t remember the password. Below will be the flow: Click on Forgot Password The passenger is asked to enter the phone number A 6 digit code will be sent to the entered phone number using Twilio via SMS The passenger is asked to enter the received code on the verification screen. Once the code is verified, the passenger is navigated to the next screen in the flow, to generate a new password and confirm it. Clicking on submit will generate a new password for that phone number. Passenger will be taken back to Sign-in Screen to Sign in with Phone number and new password.

Registration ( Need passenger to add bank card at this stage)

If the passenger is using the app for the first time. Below will be the flow:

The passenger will enter the phone number on the Sign-In screen, the system will check the phone number is already registered or not. If the phone number is already registered the passenger will be asked the password for his/her respective account. If the phone number is not registered in the system, the system will send 6 digit code to the phone number for verification using Twilio via SMS. The passenger has to enter the 6 digit code in the phone number verification screen. Once the phone number is successfully verified. The app will ask Passenger’s First Name & Last Name. The next screen will be to enable Touch ID/Face ID (for iOS app) or Fingerprint (for Android app). Enabling it will allow the passenger to login via configure Touch ID/Face ID or Fingerprint. Add bank Card here The above step is optional in the flow. After the successful registration of the passenger, the landing screen of the app will be shown. Landing Screen for Passenger This screen is the home screen for the passenger from where they can Book a Cab and access the different modules of the app. Below are the main elements of the Landing Screen Google Map Integration Google Maps has to take the entire screen edge to edge. If the location service is not enabled in the device, a message will be shown to the passenger “To find your pickup location automatically, turn on location services”. After clicking on the message, the app will navigate the passenger to turn on the location services of the mobile device. Opening the app again, the passenger will see their current location on the Google map.

Choose a destination Input Field Clicking on the input field will take the user to a pop-out window, with the current location of the passenger picked up automatically as the pickup location and the destination user can type in where suggestion will be shown as part of Google Places API. Once the destination is filled in passengers can click ok to finalize the destination address. The passenger has an option also to edit his/her pickup location from this screen.

Side Panel Menus Passenger Name with the profile pic. Default image if the user has not provided an image. My Journeys Addresses Manage Cards Profile Help & Support
Logout

Book a Taxi Flow The passenger will not be able to make booking until a card is added from Manage Cards section.

Passenger selects Destination from the landing screen As soon passenger selects the destination the next screen will show the google map with Pickup and Dropoff location of the user, in the first half of the screen The passenger can change the Pickup or Dropoff location from this screen itself by simply taping the anyone of the location And next half will allow the passenger to select from Cab Type, 5-Seater, 6-Seater, or 6-Seater electric. Once the Cab type selected, passenger can select from payment type, In-App Payment Cash User can see the Fares details by clicking on the Fares access link from this section itself, the fare detail will open the webview with the link . ETA will be shown to passengers in the same section, which will be the time to reach for Driver at Passenger’s location. Passenger have two option Book Now, if Passenger is booking the cab now Pre-Book Now, If Passenger is booking the cab for later.

Book Now Flow

Once the Passenger selects Book now, system will search for nearby drivers within the radius of 0.5 miles (This radius is manageable from Admin). The proposed search algorithm will create a pool of top 10 nearby drivers to Passengers location. Each driver will get the Job and has wait time to accept the job is 10 secs. If the driver is not accepting the job in 10 secs the job will be sent to next driver in the nearby list pool. The passenger will have wait time of 1 mins per booking. If the driver is not found in the 1 mins limit, the app should show the passenger that “No Driver Found!” Transition to show the process of contacting nearby drivers. Passenger can cancel the booking from this screen. Cancelling the booking, passenger will ask from below options: Took a Taxi from the street Changed my mind Cancel Taxi too far away There can be more reasonable, which we need to show in a dynamic scroll. If the Passenger cancels the job after Driver accepts the job he will be charged 3 GBP as cancellation charges. The Cancellation window for passenger is 1-2 mins. If the driver is allocated to the passenger, the screen will show the following information Google Map with Driver’s Location Section to show: Driver Name Taxi Number Contact icon to call Driver. Estimated time to reach at Pickup location Cancel button to cancel the booking. Cancelling the taxi will ask passenger about Each time this screen is visited the Driver’s location is refreshed and ETA as well. So that Passenger will access to the recent information of Driver’s whereabouts always. Once the trip is completed, for In-App payment or Cash, the passenger will see the amount in the screen that he need to pay. If its Cash, he can directly share the cash with driver.

Pre-Book Flow (To be decided during execution)

After confirming the destination and Cab Type. When Passenger selects Pre-Book, he/she is asked to select the future date and time for the ride. After confirming the dates, system sends the request to drivers for the ride. Question: Please confirm the algorithm for searching the drivers, Is it same as of Book Now? If there is no driver found around the location, User will get a message No Driver Found. Transition to show the process of contacting nearby drivers. Passenger can cancel the booking from this screen. Canceling the booking, passenger will ask from below options: Took a Taxi from the street Changed my mind Cancel If the driver is allocated to passenger, the screen will show following information Google Map with Driver’s Location Section to show: Driver Name Taxi Number Contact icon to call Driver. Estimated time to reach at Pickup location Cancel button to cancel the booking. Cancelling the taxi will ask passenger about Each time this screen is visited the Driver’s location is refreshed and ETA as well. So that Passenger will access to the recent information of Driver’s whereabouts always. The passenger can book maximum 2 Pre-book jobs

My Journeys Flow Passenger can access to his/her past bookings and upcoming booking from this screen Pre Book-Rides List of Rides that are upcoming will be able to access by simply clicking on Pre-Book Tab List screen will have following information of each Pre-Book rides. Drop-off Location Trip Date Trip Time Status – Cancelled by Passenger, Completed, No Show, Cancelled by Driver Pre-Book Ride Description screen The screen can be accessed by Passenger by simply clicking any one of the Pre-Book ride from the list. Following information can be accessed from the details screen Cab/Taxi Type Fare Distance Time Pickup Location Dropoff Location Driver Name Payment Mode Payment Status Download/View Receipt

Instant Rides (Past Journeys) List of Rides that are booked as part of Book Now flow will be able to access by simply clicking on Pre-Book Tab List screen will have following information of each Book Now rides. Drop-off Location Trip Date Trip Time Status – Cancelled by Passenger, Completed, No Show, Cancelled by Driver

Book Now Description screen The screen can be accessed by Passenger by simply clicking any one of the Book Now ride from the list. Following information can be accessed from the details screen Cab/Taxi Type Fare Distance Time Pickup Location Dropoff Location Driver Name Payment Mode Payment Status Download/View Receipt

My Addresses The screen will allow user to save the addresses to easily locate while adding the destination while Booking for a Taxi. If there is no address added, screen will show “No Saved address found, Please Add an address”. User can click “Plus” icon to add an address. Add an address screen will have following fields to save an address: Place Name – A simple input field to add a name to your address. e.g. Home, Work Search Address – Input field using which you can search for an address using Google Map API Save Button – Will add the Address to List.

Push to Book The passenger would be able to book a cab in once click which will have a default destination already configured from Settings Push to book configuration Also the passenger can configure the default payment from setting for push to book.

Manage Cards User has an ability to save the credit cards for In-App Payments All the credit card information is saved via Stripe https://stripe.com/docs/payments/save-card-without-authentication Simply click on Add card button to add a card. Add a card screen will allow user to add a card by simply scanning the credit card information or user can manually add the information using form controls. Scanning of Card will be done using Stripe SDK for Scanning cards https://stripe.dev/stripe-ios/docs/#card-scanning-beta User can manually add card as well using following fields Card Holder Name Card Number Card Expiry (MM/YY) CVV All the above information will be process at server side using Stripe. Multiple cards can be added for In-App payment Stripe will hold 5 GBP whenever user make a card default in the manage cards section. Need a discussion with Stripe for the same.

Profile The screen will allow user to change the following information of user First Name Last Name Profile Image Phone number – Changing the phone number will ask the user new phone number and OTP will be sent to that new number before changing it. Password Enable or Disable TouchID/Face ID or Fingerprint scanner

Help and Support Email – Send queries to support Privacy policy Term & Conditions Q & A Tell a Friend News

Logout Hide the Logout under Profile Side menu

Once the code is verified, the driver is navigated to the next screen in the flow, to generate a new password and confirm it. Clicking on submit will generate a new password for that phone number. driver will be taken back to Sign-in Screen to Sign in with Phone number and new password. Taxibook App Admin Panel This Is the main admin panel of Taxi app or Control panel of all the modules of the Taxi app system. This section will be used by a single Admin using a user id and password. Following are the modules of the Admin panel we are proposing: Dashboard View Following are the section of Dashboard view: Total Count of Section Active Passengers Active Drivers Trial Period Drivers Trips Corporates Institution Revenue Pre-Book Rides

Google Map View to show Active Trips Available Drivers Overlay counts to show: Total Trips today Cancelled by passenger Cancelled by Drivers Booking Failed

Create a Test Job Admin can dispatch a test job from backend to a single driver from the list. Following are the information Admin have to enter: Pickup location Drop-off location Passenger Name Passenger Contact Select Date/Time (If Pre-Booked Job) Assign Driver button Clicking on Assign Driver button will allow Admin to search the driver by just entering the name and hit search. Clicking on the driver from search result will send this Test Job
