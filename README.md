# CS-360-15554-M01-Mobile-Architect-Programming-2024-C-5-Sep---Oct-

# Inventory Mobile App - README

## App Overview

The **Inventory Mobile App** was developed to enable users to efficiently manage an inventory system. The primary goal of the app was to allow users to log in, add, update, delete, and view inventory items stored in an SQLite database. Designed for simplicity and utility, this app addresses the needs of users who require a straightforward way to manage items, such as small business owners or individuals with personal inventories. By providing core features like item management, SMS notifications for low stock alerts, and persistent data storage, the app meets user demands for organization, accessibility, and real-time notifications.

## Screens and Features

### Login and Registration Screens
- **Login Screen**: Allows users to log in with a username and password. The app checks credentials against the database, ensuring that only authorized users access the inventory.
- **Registration Screen**: Enables new users to create a username and password, which are saved in the database for future logins.

### Main Inventory Management Screens
- **Inventory Display Screen**: Displays inventory items in a grid format, providing an overview of item names, quantities, and dates. Users can add, update, or delete items from this screen.
- **Add Item Screen**: Allows users to input a new item’s details, including name, quantity, and date. This screen was designed to be simple and intuitive, with prompts to guide the user.
- **Edit Item Screen**: Users can update the details of an existing item, including modifying the quantity or date information.

### Settings Screen
- **Settings Screen**: Includes options for adjusting SMS notification settings and setting a low-stock threshold. The UI displays the current state of SMS permissions and allows users to enable or disable SMS alerts at startup. This helps users stay informed when items reach critical low-stock levels.

The UI design kept users in mind by maintaining a clean and minimal interface, with straightforward text fields, buttons, and navigational cues. Each screen was designed to limit distractions and prioritize functionality, helping users accomplish tasks efficiently. The success of this design is reflected in the app’s ease of navigation and intuitive layout.

## Development Approach and Coding Techniques

The coding approach focused on modularity and clear structure. Each functionality was broken down into individual classes and methods, with a particular focus on:
- **Database Management**: A dedicated `DatabaseHelper` class was created to handle all SQLite interactions, including CRUD operations.
- **SMS Notifications**: The `SMSHelper` class was used to manage SMS alerts. By isolating SMS functionality, it was easier to manage permission-based responses and ensure the app’s core functionality remains intact if SMS permissions are denied.
- **Event-Driven UI Updates**: To ensure the inventory display was always up-to-date, methods were added to refresh the screen when data was modified, allowing real-time feedback to the user.

These strategies proved effective, and isolating each functional component allowed for organized, efficient code development. This modular approach can be applied to future projects, enabling clear separation of concerns and easier debugging.

## Testing and Validation

Testing was conducted throughout development using the Android Emulator. Each feature was tested for functionality, including:
- **Login/Registration Verification**: Ensured user credentials were saved correctly and authenticated properly.
- **Inventory Management Operations**: Confirmed that items could be added, updated, and deleted without data loss, and verified the database's persistence.
- **Permission Handling**: Tested the SMS feature by both allowing and denying permissions to verify that the app behaves correctly in both cases.

Testing not only validated that the app met functional requirements but also revealed edge cases, such as empty input handling and data validation. This process was essential for identifying and resolving issues early, ensuring a stable, user-friendly application.

## Challenges and Innovative Solutions

One significant challenge was ensuring the settings, particularly the low-stock threshold and SMS toggle, would immediately affect the main inventory display without requiring additional user input. To overcome this, I implemented an `onResume` method in the display activity to refresh data whenever users returned from the settings screen. This solution ensures that settings changes are immediately reflected across the app, improving usability.

Another challenge involved managing SQLite data persistence across different app screens while minimizing data refresh times. This was addressed by optimizing database calls and caching frequently accessed data within the display screen, balancing real-time updates with efficient performance.

## Demonstrated Knowledge and Skills

The **Settings and Inventory Management Integration** component best demonstrates my skills and knowledge. By combining real-time data updates, SMS permissions, and persistent data storage, I effectively showcased my ability to build an interactive, responsive application. The UI’s seamless interaction with backend data functions highlights both the technical and design aspects of the app, creating a cohesive and functional user experience.
