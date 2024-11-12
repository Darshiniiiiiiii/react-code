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

