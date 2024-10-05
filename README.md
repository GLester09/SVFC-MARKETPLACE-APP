# SVFC-MARKETPLACE-APP

# SVFC-Marketplace

# A. Introduction

### The SVFC Marketplace App is a student-focused platform where SVFC students can buy, sell, or exchange used items, including textbooks, electronics, and dorm supplies. The app fosters a sustainable and collaborative marketplace within the SVFC community, offering students a convenient platform for peer-to-peer transactions. The app is strictly for SVFC students and is not open to the public.
________________________________________
# B. Project Features and Characteristics

## 1.	User Registration and Login
Only SVFC students can register using their school credentials, ensuring that only authorized users can access the platform.
## 2.	Listing Items for Sale or Exchange
Users can list items by uploading images, setting prices, and providing descriptions. All listings will be moderated before going live.
## 3.	Browsing and Searching
Students can browse items by categories (textbooks, electronics, dorm supplies, etc.) and use filters such as condition, price range, and more.
## 4.	Messaging System with Notifications
The app includes a messaging system for buyer-seller communication, with notifications to keep users informed about new messages or updates on their listings.
## 5.	Payment Integration
To facilitate secure transactions, payment options such as PayPal or credit card processing will be integrated. This allows students to make payments within the app.
## 6.	Moderation and Reporting System
Listings will be reviewed by moderators before being posted, and users can report inappropriate listings or messages.
## 7.	User Ratings and Reviews
After completing a transaction, students can rate and review each other to ensure a trustworthy environment.
________________________________________
# C. Project Scope

### The SVFC Marketplace App will serve only the students of SVFC. The scope includes managing listings, providing secure payment integration, facilitating communication between users, and implementing moderation to ensure the safety and integrity of the platform. Expansion beyond the SVFC community is not part of the initial project.
________________________________________
# D. Work Breakdown Structure

## 1.	Planning and Research
- Identify core student needs for a marketplace app.
- Establish essential app features and requirements.
## 2.	UI/UX Design
- Design wireframes and user interfaces in Figma or similar tools.
- Ensure intuitive design for easy navigation.
## 3.	Development
- Front-End Development: Use Angular or React to build the front-end user interface.
- Back-End Development: Build APIs for user authentication, listings, and transactions.
## 4.	Payment Integration
- Research and integrate PayPal or Stripe API for secure payments.
## 5.	Database Design
- Define data models for users, listings, transactions, and messages.
## 6.	Testing
- Perform unit, system, and acceptance testing.
## 7.	Deployment and Maintenance
- Deploy on Render.com or another cloud service for continuous delivery.
________________________________________
# E. Functional Requirements

## 1. User Requirements

•	Users must register and log in using valid school credentials.

•	Users can list items, including photos, price, and item descriptions.

•	Users can search for items, browse by category, and filter search results.

•	A messaging system with notifications will allow buyers and sellers to communicate.

•	Secure payment options will be integrated, and transactions will be completed within the app.

•	Listings will be reviewed before being made visible on the platform.

•	Users will be able to report any issues or inappropriate content.

## 2. Use Case
   
## Use Case 1: Registering and Logging In
- Actor: Student
- Description: The user registers and logs in with their school email and password.
- Precondition: The user must be a registered SVFC student.
- Postcondition: The user can access the platform to create listings or make purchases.

## Use Case 2: Listing an Item
- Actor: Student
- Description: The user creates a new listing by uploading images, adding a description, and setting a price. The listing is sent for review.
- Precondition: The user is logged in.
- Postcondition: The listing goes live after moderator approval.
  
## Use Case 3: Completing a Transaction
- Actor: Buyer and Seller
- Description: A buyer chooses an item, pays using the integrated payment method (PayPal/Stripe), and completes the transaction.
- Precondition: The buyer has funds available in their PayPal account or credit card.
- Postcondition: The payment is processed, and the seller ships the item.
________________________________________
# F. Database Architecture

## 1. Data Dictionary


![image](https://github.com/user-attachments/assets/105e7ee9-11aa-4f34-9438-4ca592f41802)
![image](https://github.com/user-attachments/assets/871d3b61-da8c-4d4b-b02b-bdfbe2be08fe)

## 2. Entity Relationship Diagram (ERD)
- Users:
Represents SVFC students who use the platform. Each user can create multiple listings, make purchases, and receive notifications.
- Listings:
Represents the items for sale or exchange. Each listing is linked to a user and can have many transactions.
- Transactions:
Represents the transactions between buyers and sellers. Each transaction is linked to one listing and involves two users (buyer and seller).
- Messages:
Represents communication between users. Each message is linked to a transaction or listing and involves two users.
- Moderators:
Represents system moderators who review and approve listings before they go live. Each listing is reviewed by one or more moderators.
- Reports:
Represents user reports of inappropriate content. Each report is linked to a listing and reviewed by a moderator.
________________________________________
# ERD Structure
## 1.	Users (user_id, name, email, password)
- One-to-Many with Listings
- One-to-Many with Messages
- One-to-Many with Transactions
  
## 2.	Listings (listing_id, user_id, item_name, category, price, description, status)
- Many-to-One with Users
- One-to-Many with Transactions
- One-to-Many with Reports
- One-to-Many with Moderators
  
## 3.	Transactions (transaction_id, listing_id, buyer_id, seller_id, amount, status)
- Many-to-One with Listings
- Many-to-One with Users (buyer_id and seller_id)
  
## 4.	Messages (message_id, transaction_id, sender_id, receiver_id, content, timestamp)
- Many-to-One with Transactions
- Many-to-One with Users (sender_id and receiver_id)
  
## 5.	Moderators (moderator_id, name, email)
- One-to-Many with Listings
- One-to-Many with Reports

## 6.	Reports (report_id, listing_id, reporter_id, reason, timestamp, status)
- Many-to-One with Listings
- Many-to-One with Users (reporter_id)
- Many-to-One with Moderators (reviewed by)

## ERD Diagram
Here’s a visual description of the entities:

![image](https://github.com/user-attachments/assets/910405bc-4999-4a77-aa00-285811553e62)


-	Users → (One-to-Many) → Listings
-	Users → (One-to-Many) → Messages
-	Users → (One-to-Many) → Transactions
-	Listings → (Many-to-One) → Users
-	Listings → (One-to-Many) → Transactions
-	Listings → (One-to-Many) → Reports
-	Listings → (One-to-Many) → Moderators
-	Transactions → (Many-to-One) → Listings
-	Transactions → (Many-to-One) → Users
-	Messages → (Many-to-One) → Transactions
-	Moderators → (One-to-Many) → Listings
-	Moderators → (One-to-Many) → Reports
