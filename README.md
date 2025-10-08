
---


# Online Blood Donor Management System

This is a web-based application designed to manage blood donor information and connect individuals in need of blood with willing donors. The system provides a platform for users to register as donors, search for donors based on blood group and location, and for administrators to manage the overall system.

## 🌟 Features

The application is divided into two main modules: the User/Donor module and the Admin module.

### User/Donor Features
*   **User-friendly Interface**: Clean and simple interface for easy navigation.
*   **Donor Registration**: A detailed form for new donors to register their information (name, blood group, contact, location, etc.).
*   **Donor Login**: Secure login for registered donors to manage their profiles.
*   **Search Donors**: Ability to search for available donors by blood group and city.
*   **Request Blood**: A form for individuals to post a request for blood, specifying the required blood group, hospital details, and contact information.
*   **View Blood Requests**: A public page listing all active blood requests.

### Admin Features
*   **Secure Admin Panel**: A separate, password-protected dashboard for administrators.
*   **Dashboard**: An overview of system statistics, such as the total number of donors and requests.
*   **Manage Donors**: View, update, and delete donor records.
*   **Manage Blood Requests**: View and delete blood donation requests.
*   **Manage Queries**: View and respond to user queries submitted through the contact form.

## 💻 Technology Stack

*   **Frontend**: HTML, CSS, Bootstrap
*   **Backend**: PHP
*   **Database**: MySQL

## 🛠️ Installation and Setup

To get this project running on your local machine, follow these steps:

### 1. Prerequisites
*   A local server environment like [XAMPP](https://www.apachefriends.org/index.html) or [WAMP](https://www.wampserver.com/en/).
*   A web browser like Chrome, Firefox, or Edge.
*   A code editor like VS Code, Sublime Text, or Atom.

### 2. Clone the Repository
Open your terminal or command prompt and clone the repository into your local server's web directory (e.g., `htdocs` for XAMPP).
```sh
git clone https://github.com/Dheya0/Online-Blood-Donor-.git
```

### 3. Database Setup
The repository does not include a `.sql` file, so you will need to create the database and tables manually.

1.  Start your **Apache** and **MySQL** services from your XAMPP/WAMP control panel.
2.  Open your web browser and go to `http://localhost/phpmyadmin/`.
3.  Create a new database and name it `obd`.
4.  Select the `obd` database and go to the **SQL** tab.
5.  Copy and execute the following SQL queries to create the necessary tables:

```sql
-- Table structure for `admin`
CREATE TABLE `admin` (
  `id` int(11) NOT NULL AUTO_INCREMENT,
  `username` varchar(50) NOT NULL,
  `password` varchar(50) NOT NULL,
  PRIMARY KEY (`id`)
) ENGINE=InnoDB DEFAULT CHARSET=utf8mb4;

-- Dumping data for `admin`
INSERT INTO `admin` (`username`, `password`) VALUES
('admin', 'admin123');


-- Table structure for `donors`
CREATE TABLE `donors` (
  `id` int(11) NOT NULL AUTO_INCREMENT,
  `name` varchar(100) NOT NULL,
  `guardian_name` varchar(100) NOT NULL,
  `gender` varchar(10) NOT NULL,
  `dob` date NOT NULL,
  `weight` int(11) NOT NULL,
  `blood_group` varchar(5) NOT NULL,
  `email` varchar(100) NOT NULL,
  `contact` varchar(20) NOT NULL,
  `address` text NOT NULL,
  `city` varchar(100) NOT NULL,
  `username` varchar(50) NOT NULL,
  `password` varchar(255) NOT NULL,
  PRIMARY KEY (`id`),
  UNIQUE KEY `username` (`username`)
) ENGINE=InnoDB DEFAULT CHARSET=utf8mb4;


-- Table structure for `requests`
CREATE TABLE `requests` (
  `id` int(11) NOT NULL AUTO_INCREMENT,
  `name` varchar(100) NOT NULL,
  `gender` varchar(10) NOT NULL,
  `blood_group` varchar(5) NOT NULL,
  `unit` int(11) NOT NULL,
  `hospital` varchar(255) NOT NULL,
  `city` varchar(100) NOT NULL,
  `pincode` varchar(10) NOT NULL,
  `doctor_name` varchar(100) NOT NULL,
  `request_date` date NOT NULL,
  `contact_name` varchar(100) NOT NULL,
  `email` varchar(100) NOT NULL,
  `contact` varchar(20) NOT NULL,
  `reason` text NOT NULL,
  PRIMARY KEY (`id`)
) ENGINE=InnoDB DEFAULT CHARSET=utf8mb4;


-- Table structure for `queries`
CREATE TABLE `queries` (
  `id` int(11) NOT NULL AUTO_INCREMENT,
  `name` varchar(100) NOT NULL,
  `email` varchar(100) NOT NULL,
  `contact` varchar(20) NOT NULL,
  `message` text NOT NULL,
  `posted_date` timestamp NOT NULL DEFAULT current_timestamp(),
  PRIMARY KEY (`id`)
) ENGINE=InnoDB DEFAULT CHARSET=utf8mb4;

```

### 4. Run the Application
1.  Place the cloned `Online-Blood-Donor-` folder inside your `htdocs` (for XAMPP) or `www` (for WAMP) directory.
2.  Open your web browser and navigate to:
    ```
    http://localhost/Online-Blood-Donor-/
    ```
3.  To access the admin panel, navigate to:
    ```
    http://localhost/Online-Blood-Donor-/admin/
    ```
    *   **Admin Username**: `admin`
    *   **Admin Password**: `admin123`

You should now be able to see the application running!

## 🤝 Contributing

Contributions are welcome! If you would like to contribute to this project, please follow these steps:

1.  Fork the repository.
2.  Create a new branch (`git checkout -b feature/your-feature-name`).
3.  Make your changes.
4.  Commit your changes (`git commit -m 'Add some feature'`).
5.  Push to the branch (`git push origin feature/your-feature-name`).
6.  Open a Pull Request.

