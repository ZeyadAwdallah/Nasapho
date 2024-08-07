### Nasapho

#### Overview

Nasapho is a simple React application that fetches and displays the NASA Astronomy Picture of the Day `(APOD)` using the NASA API. The application caches the data in `localStorage` to avoid redundant API calls and improve performance. Users can view the picture of the day along with its title and explanation, and access additional details through a modal sidebar.

#### Application Structure

The application consists of the following components:

1. **App**: The main component that fetches the APOD data, manages the state, and renders `Main`, `Footer`, and `SideBar` components.
2. **Main**: A component that displays the APOD image.
3. **Footer**: A component that shows the project title and a button to toggle the sidebar.
4. **SideBar**: A modal component that provides detailed information about the APOD.

#### Components

##### 1. App Component

The `App` component is the entry point of the application. It handles data fetching, state management, and conditionally renders other components based on the state.

- **State Management**: Uses the `useState` hook to manage `data` (APOD data) and `showModal` (modal visibility).
- **Data Fetching**: Uses the `useEffect` hook to fetch data from the NASA API. It checks `localStorage` for cached data and fetches new data if not available.
- **Handlers**: Provides a function to toggle the visibility of the sidebar modal.

##### 2. Main Component

The `Main` component displays the APOD image.

- **Props**: Receives `data` (APOD data) as a prop.
- **Functionality**: Renders the APOD image with a fallback alt text.

##### 3. Footer Component

The `Footer` component shows the project title, APOD title, and a button to toggle the sidebar.

- **Props**: Receives `data` (APOD data) and `handleToggleModal` (function to toggle modal visibility) as props.
- **Functionality**: Displays the project title and APOD title, and includes a button to open the sidebar modal.

##### 4. SideBar Component

The `SideBar` component is a modal that displays detailed information about the APOD.

- **Props**: Receives `data` (APOD data) and `handleToggleModal` (function to toggle modal visibility) as props.
- **Functionality**: Shows the APOD title, date, and explanation. Provides a button to close the modal.

#### Usage

1. **Fetching Data**: The application fetches the APOD data when it first loads. It checks `localStorage` for cached data from the current day to avoid unnecessary API calls.
2. **Viewing the Image**: The main page displays the APOD image. 
3. **Accessing Details**: Click the information button in the footer to open the sidebar modal, which provides detailed information about the APOD.
4. **Closing the Modal**: Click the arrow button in the sidebar to close the modal.

#### Local Storage

The application uses `localStorage` to cache the APOD data for the current day. This ensures that the data is only fetched from the API once per day, improving performance and reducing API usage.

#### Key Features

- **Responsive Design**: The application layout adjusts based on the screen size for an optimal user experience on different devices.
- **User-Friendly Interface**: Clean and simple UI with an image display and easy access to additional information.
- **State Persistence**: Uses `localStorage` to save and load APOD data, ensuring efficient data management and performance.
