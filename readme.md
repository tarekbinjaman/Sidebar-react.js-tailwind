# Creating sidebar using react.js and tailwind

Install react icon
~~~
npm install react-icons
~~~

## Sidebar Component

~~~
import { useState } from "react";
import { FaBars, FaTimes } from "react-icons/fa";

export default function Sidebar() {
  const [isOpen, setIsOpen] = useState(false);

  const toggleSidebar = () => {
    setIsOpen(!isOpen);
  };

  return (
    <div className="relative">
      {/* Hamburger Icon */}
      <button onClick={toggleSidebar} className="text-3xl m-4">
        <FaBars />
      </button>

      {/* Sidebar */}
      <div className={`fixed top-0 left-0 h-full w-64 bg-gray-800 text-white p-6 transform ${isOpen ? "translate-x-0" : "-translate-x-full"} transition-transform duration-300 ease-in-out`}>
        {/* Cross Icon */}
        <button onClick={toggleSidebar} className="text-3xl mb-8">
          <FaTimes />
        </button>

        {/* Sidebar Content */}
        <ul className="space-y-6 mt-10">
          <li className="hover:text-gray-400">Home</li>
          <li className="hover:text-gray-400">About</li>
          <li className="hover:text-gray-400">Services</li>
          <li className="hover:text-gray-400">Contact</li>
        </ul>
      </div>
    </div>
  );
}

~~~

## What's happening here:

FaBars = hamburger icon (opens sidebar)

FaTimes = cross (X) icon (closes sidebar)

useState is used to track whether the sidebar is open or closed.

Using Tailwind classes to slide the sidebar smoothly.