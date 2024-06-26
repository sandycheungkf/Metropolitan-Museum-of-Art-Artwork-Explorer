### Vercel App (Deployed) Link : https://web-as06-kfc.vercel.app/


### Project overview 

This project is a Next.js application that allows users to explore artwork from the Metropolitan Museum of Art. It includes features like searching for artwork, viewing details of specific pieces, adding favorites, viewing search history, and enhanced usability for mobile navigation. Additionally, it involves creating a User API using Node/Express, securing it with JWT authentication, and integrating it with the Next.js application to manage user registration, authentication, and data persistence.

### Prerequisites
- Node.js 
- npm 

### Installation

#### Next.js Application

1. **Create a New Directory:**
2. **Create a New Next.js App:**
3. **Install Required Modules:**
4. **Import Bootstrap CSS:**
5. **Clear Default CSS:**

#### User API (Node/Express)

1. **Database Setup on MongoDB Atlas**
2. **Environment Variables Setup**
   - Create a `.env` file in the root directory of the User API project.

3. **Installing Dependencies**
   - Run `npm install` to install all required dependencies.

4. **Starting the Server**
   - Run `npm start` to start the server. 

### Deployment

#### Deploying User API to Cyclic

1. **Setup on Cyclic**
   - Create a new application on Cyclic.
   - Configure environment variables (`JWT_SECRET` and `MONGO_URL`) in Cyclic's dashboard.

2. **Deploying**
   - Push your code to Cyclic using their deployment mechanism.
   - Verify deployment status and ensure environment variables are correctly set.

#### Deploying Next.js Application to Vercel

1. **Environment Variables**
   - Create a `.env.local` file in the root directory of your Next.js application.

2. **Deploy to Vercel**

### Project Structure

#### Next.js Application

- **Components:**
  - **MainNav (`components/MainNav.js`):** Displays a fixed-top navigation bar with the student name, links to Home, Advanced Search, Favourites, and Search History pages, and a search form for quick artwork searches. Automatically hides the expanded navbar on mobile devices when a link is clicked or a search is performed.
  - **Layout (`components/Layout.js`):** Wraps the main layout with the navigation bar and content container.
  - **ArtworkCard (`components/ArtworkCard.js`):** Displays a card with artwork details fetched using SWR. Includes an image, title, date, classification, medium, and a link to detailed view.
  - **ArtworkCardDetail (`components/ArtworkCardDetail.js`):** Displays detailed information about a specific artwork, including an image, artist name, credit line, and dimensions. Allows users to add or remove the artwork from their favourites.
  - **Favourites (`pages/favourites.js`):** Displays a list of favourite artworks added by the user. Shows a message if no favourites are added.
  - **History (`pages/history.js`):** Displays a list of previous search queries. Allows users to re-run or delete previous searches.

- **Pages:**
  - **Home (`pages/index.js`):** Displays an image of the Metropolitan Museum of Art and a description with a link to the Wikipedia entry.
  - **Artwork (`pages/artwork/index.js`):** Allows users to search and explore artwork. Filters search results to exclude invalid object IDs. Implements pagination for browsing through multiple artworks.
  - **ArtworkById (`pages/artwork/[objectID].js`):** Displays detailed information about a specific artwork.
  - **AdvancedSearch (`pages/search.js`):** Provides a form for advanced search options. Adds the search query to the search history.

#### User API

- **Endpoints:**
  - **User Registration and Authentication:** Secure routes for user favorites and history using JWT authentication.
  - **User Favourites and Search History:** CRUD operations for managing user favorites and search history.

### Usage

1. **Start the Development Server:**

2. **Open Your Browser:**

   Navigate to [http://localhost:3000](http://localhost:3000) to view the application.

3. **Navigation:**

   - Use the navigation bar to access the Home, Advanced Search, Favourites, and Search History pages.
   - Use the search form in the navigation bar for quick searches.

4. **Search and Explore:**

   - Enter keywords or use advanced search options to find specific artworks.
   - Click on artwork cards to view detailed information.
   - Add artworks to favourites and view them on the Favourites page.
   - View and manage previous search queries on the Search History page.

### Jotai Store

Create a `store.js` file in the root of your application:

### Automatically Hiding the Expanded Navbar

1. **Set an `isExpanded` Value:**
2. **Update the `<Navbar>` Component:**
3. **Toggle `isExpanded` on `<Navbar.Toggle>` Click:**
4. **Close Navbar on Link Click:**

### Favourites Functionality

1. **ArtworkCardDetail Component:**

   - Import `useAtom` and `favouritesAtom`.
   - Add a `showAdded` state to control button display.
   - Add a `favouritesClicked` function to add/remove artwork from favourites.

2. **Favourites Page:**

   - Get a reference to `favouritesList` from `favouritesAtom`.
   - Render the list of favourite artworks.

3. **Update MainNav Component:**

   - Add a `NavDropdown` for the user with a link to the Favourites page.

### Search History Functionality

1. **Add Search History to Store:**
   - In `store.js`, add `searchHistoryAtom`.

2. **Update Advanced Search:**
   - Add search queries to `searchHistory`.

3. **Update MainNav Search:**
   - Add search queries to `searchHistory`.

4. **History Page:**
   - Display and manage the list of previous searches.
   - Add CSS for hover effect on history items.

5. **Update MainNav Component:**
   - Add a link to the Search History page in the user dropdown.

### Highlighting Navbar Items

Ensure each `<Nav.Link>` and `<NavDropdown.Item>` in the `MainNav` component sets the `active` attribute based on the current path:

