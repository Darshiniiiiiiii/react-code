#App.js

import React from 'react';
import './App.css';
import Header from './components/Header';
import ListingCard from './components/ListingCard';

const App = () => {
    return (
        <div className="p-4">
            <Header />
            <div className="text-center text-gray-600 mb-4">
                Guests agree: these stays are highly rated for location, cleanliness and more.
            </div>
            <div className="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-4 gap-4">
                <ListingCard 
                    image="https://a0.muscache.com/im/pictures/hosting/Hosting-39049869/original/d05ca6dd-95ee-4d09-b347-3c9c9ca30cb5.jpeg?im_w=720"
                    title="Treehouse in Kotta..."
                    rating="4.97 (236)"
                    description="Duplex Riverside Treehouse-... Welcome to our simple living concept with nature and farm life style."
                    tag="Guest favourite"
                />
                <ListingCard 
                    image="https://a0.muscache.com/im/pictures/hosting/Hosting-39049869/original/d05ca6dd -95ee-4d09-b347-3c9c9ca30cb5.jpeg?im_w=720"
                    title="Tiny home in Ramam..."
                    rating="4.9 (135)"
                    description="Calm & Secluded Cottage w/... Listed as most gorgeous River view Villa by Cosmopolitan®India."
                    tag="Superhost"
                />
                <ListingCard 
                    image="https://a0.muscache.com/im/pictures/02a5f73e-9aa9-4eaa-acfa-6157327d7be3.jpg?im_w=720"
                    title="Holiday home in Ku..."
                    rating="4.95 (129)"
                    description="Little Chembaka- Private Villa with... We're all about bringing you closer to local life."
                    tag="Guest favourite"
                />
                <ListingCard 
                    image="https://a0.muscache.com/im/pictures/5a024f99-252d-450d-a92b-77ca7f762f96.jpg?im_w=720"
                    title="Farm stay in Kottay..."
                    rating="4.91 (163)"
                    description="Naturesque Independent Farm Villa... Located on the banks of the meenachil river."
                    tag="Guest favourite"
                />
            </div>
            <div className="mt-8">
                <h2 className="text-2xl font-bold">Holiday rentals for every style</h2>
                <p className="text-gray-600">Get the amount of space that is right for you</p>
            </div>
        </div>
    );
};

export default App;


#App.css

body {
  font-family: 'Roboto', sans-serif;
}

h2 {
  margin-top: 2rem;
}


#index.js

import React from 'react';
import ReactDOM from 'react-dom';
import App from './App';
import './index.css';

ReactDOM.render(<App />, document.getElementById('root'));

src,components<

#Header.js

import React from 'react';
import HeaderLogo from './HeaderLogo';

const Header = () => {
    return (
        <header className="flex justify-between items-center py-4">
            <HeaderLogo />
            <div className="flex items-center space-x-4">
                <a href="#" className="text-gray-700">Airbnb your place</a>
                <button className="bg-pink-500 text-white px-4 py-2 rounded-full">Start your search</button>
            </div>
        </header>
    );
};

export default Header;

#HeaderLogo.js

import React from 'react';

const HeaderLogo = () => {
    return (
        <div className="flex items-center">
            <img 
                src="https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcS6AVlUCGaNtnJ4BzDeTS0OWkoNfpSDvZ4Z3Q&s/5x5" 
                width="30" 
                height="20" 
                alt="Airbnb logo" 
                className="mr-2"
            />
            <span className="text-xl font-bold text-red-500">airbnb</span>
        </div>
    );
};

export default HeaderLogo;

#Listing.js

import React from 'react';

const Listing = ({ image, title, rating, description, tag }) => {
    return (
        <div className="relative bg-white rounded-lg shadow-lg overflow-hidden">
            <img src={image} alt={title} className="w-full h-48 object-cover" />
            {tag && <div className="absolute top-2 left-2 bg-white text-black px-2 py -1 rounded-full text-sm">{tag}</div>}
            <div className="p-4">
                <h3 className="text-lg font-bold">{title}</h3>
                <div className="flex items-center text-sm text-gray-600">
                    <span className="mr-1">★</span>
                    <span>{rating}</span>
                </div>
                <p className="text-sm text-gray-600 mt-2">{description}</p>
            </div>
        </div>
    );
};

export default Listing;

#ListingCard.js

// In ListingCard.js
import React from 'react';
import Rating from './Rating';

const ListingCard = ({ image, title, rating, description, tag }) => {
    return (
        <div className="relative bg-white rounded-lg shadow-lg overflow-hidden">
            <img 
                src={image} 
                alt={title} 
                style={{ width: '300px', height: '300px' }} 
            />
            {tag && <div className="absolute top-2 left-2 bg-white text-black px-2 py-1 rounded-full text-sm">{tag}</div>}
            <div className="p-4">
                <h3 className="text-lg font-bold">{title}</h3>
                <Rating rating={rating} />
                <p className="text-sm text-gray-600 mt-2">{description}</p>
            </div>
        </div>
    );
};

export default ListingCard;

#Rating.js

import React from 'react';

const Rating = ({ rating }) => {
    return (
        <div className="flex items-center text-sm text-gray-600">
            <span className="mr-1">★</span>
            <span>{rating}</span>
        </div>
    );
};

export default Rating;

/your-project-folder
|-- /src
|   |-- App.js
|   |-- App.css
|   |-- /components
|       |-- Header.js
|       |-- HeaderLogo.js
|       |-- Listing.js
|       |-- ListingCard.js
|       |-- Rating.js
|-- index.js


1. Props
Definition: Props (short for "properties") are a way to pass data from a parent component to a child component in React. They allow components to be dynamic and reusable by enabling them to receive different values.

Use Case: In the provided code, the ListingCard component receives several props: image, title, rating, description, and tag. These props are used to customize the content displayed by each ListingCard instance.

Example in Code:

javascript

Verify

Open In Editor
Edit
Copy code
<ListingCard 
    image="https://example.com/image.jpg"
    title="Treehouse in Kotta..."
    rating="4.97 (236)"
    description="Duplex Riverside Treehouse..."
    tag="Guest favourite"
/>
2. Components
Definition: Components are the building blocks of a React application. They are reusable pieces of UI that can be composed together to create complex interfaces. Components can be either class-based or functional.

Use Case: In the provided code, there are several components:

App: The main component that renders the application.
Header: A component for the header section of the app.
ListingCard: A component that displays information about a listing.
Example in Code:

javascript

Verify

Open In Editor
Edit
Copy code
const App = () => {
    return (
        <div className="p-4">
            <Header />
            {/* Other components and content */}
        </div>
    );
};
3. JSX
Definition: JSX (JavaScript XML) is a syntax extension for JavaScript that looks similar to HTML. It allows you to write HTML-like code within JavaScript, making it easier to create React elements.

Use Case: In the provided code, JSX is used throughout to define the structure of the components. For example, the App component uses JSX to render the Header and ListingCard components.

Example in Code:

javascript

Verify

Open In Editor
Edit
Copy code
return (
    <div className="p-4">
        <Header />
        <div className="text-center text-gray-600 mb-4">
            Guests agree: these stays are highly rated for location, cleanliness and more.
        </div>
        <div className="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-4 gap-4">
            <ListingCard 
                image="https://example.com/image.jpg"
                title="Treehouse in Kotta..."
                rating="4.97 (236)"
                description="Duplex Riverside Treehouse..."
                tag="Guest favourite"
            />
            {/* Other ListingCards */}
        </div>
    </div>
);
4. Header
Definition: The Header component is a specific part of the UI that typically contains navigation links, branding, or other introductory information.

Use Case: In the provided code, the Header component is used to display the application's header section. It is called within the App component.

Example in Code:

javascript

Verify

Open In Editor
Edit
Copy code
import Header from './components/Header';

const App = () => {
    return (
        <div className="p-4">
            <Header />
            {/* Other components and content */}
        </div>
    );
};
Summary of Their Usage in the Code
Props: Used in ListingCard to pass data like image, title, rating, description, and tag.
Components: App, Header, and ListingCard are defined as functional components.
JSX: Used throughout the code to define the structure and layout of the components.
Header: Specifically refers to the Header component, which is included in the App component to render the header section of the application.
These concepts work together to create a dynamic and modular React application. By using props, components can be customized and reused, while JSX provides a clear and expressive way to define the UI structure.

