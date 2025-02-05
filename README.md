DATABASE NAME: project1
CREATE TABLE admin_maintenance (
    id INT(11) NOT NULL AUTO_INCREMENT,
    payment_duration VARCHAR(255) COLLATE utf8mb4_general_ci NOT NULL,
    start_date DATE DEFAULT NULL,
    end_date DATE DEFAULT NULL,
    maintenance_amount DECIMAL(10,2) DEFAULT NULL,
    total_amount DECIMAL(10,2) DEFAULT NULL,
    PRIMARY KEY (id)
);
CREATE TABLE admin_maintenance1 (
    id INT(11) NOT NULL AUTO_INCREMENT,
    payment_duration VARCHAR(255) COLLATE utf8mb4_general_ci NOT NULL,
    start_date DATE DEFAULT NULL,
    end_date DATE DEFAULT NULL,
    maintenance_amount DECIMAL(10,2) DEFAULT NULL,
    total_amount DECIMAL(10,2) DEFAULT NULL,
    PRIMARY KEY (id)
);

CREATE TABLE building (
    id INT(11) NOT NULL AUTO_INCREMENT,
    who ENUM('Owner', 'Rental') COLLATE utf8mb4_general_ci NOT NULL,
    floor INT(11) NOT NULL,
    flat VARCHAR(255) COLLATE utf8mb4_general_ci NOT NULL,
    purchaseDate DATE DEFAULT NULL,
    rentalDate DATE DEFAULT NULL,
    created_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP,
    PRIMARY KEY (id)
);
CREATE TABLE building_information (
    id INT(11) NOT NULL AUTO_INCREMENT,
    flat VARCHAR(10) COLLATE utf8mb4_general_ci DEFAULT NULL,
    residency_id INT(11) DEFAULT NULL,
    floor INT(11) NOT NULL,
    PRIMARY KEY (id),
    INDEX (residency_id)
);
CREATE TABLE commity (
    id INT(11) NOT NULL AUTO_INCREMENT,
    flat INT(255) NOT NULL,
    name VARCHAR(255) COLLATE utf8mb4_general_ci NOT NULL,
    email VARCHAR(255) COLLATE utf8mb4_general_ci NOT NULL,
    number BIGINT(20) NOT NULL,
    created_at TIMESTAMP NOT NULL DEFAULT CURRENT_TIMESTAMP ON UPDATE CURRENT_TIMESTAMP,
    ended_at DATETIME DEFAULT NULL,
    PRIMARY KEY (id)
);

CREATE TABLE maintenance (
    id INT(11) NOT NULL AUTO_INCREMENT,
    flat_no VARCHAR(50) COLLATE utf8mb4_general_ci NOT NULL,
    name VARCHAR(100) COLLATE utf8mb4_general_ci NOT NULL,
    phone VARCHAR(15) COLLATE utf8mb4_general_ci NOT NULL,
    email VARCHAR(100) COLLATE utf8mb4_general_ci NOT NULL,
    payment_duration ENUM('1-month', '3-months', '6-months', '1-year') COLLATE utf8mb4_general_ci NOT NULL,
    start_date DATE NOT NULL,
    amount DECIMAL(10,2) NOT NULL,
    end_date DATE DEFAULT NULL,
    payment_method ENUM('cash', 'online') COLLATE utf8mb4_general_ci NOT NULL,
    created_at TIMESTAMP NOT NULL DEFAULT CURRENT_TIMESTAMP,
    status ENUM('pending', 'approved', 'rejected') COLLATE utf8mb4_general_ci DEFAULT 'pending',
    PRIMARY KEY (id)
);

CREATE TABLE maintenance1 (
    id INT(11) NOT NULL AUTO_INCREMENT,
    flat_no VARCHAR(50) COLLATE utf8mb4_general_ci NOT NULL,
    name VARCHAR(100) COLLATE utf8mb4_general_ci NOT NULL,
    phone VARCHAR(15) COLLATE utf8mb4_general_ci NOT NULL,
    email VARCHAR(100) COLLATE utf8mb4_general_ci NOT NULL,
    payment_duration ENUM('1-month', '3-months', '6-months', '1-year') COLLATE utf8mb4_general_ci NOT NULL,
    start_date DATE NOT NULL,
    amount DECIMAL(10,2) NOT NULL,
    end_date DATE DEFAULT NULL,
    payment_method ENUM('cash', 'online') COLLATE utf8mb4_general_ci NOT NULL,
    created_at TIMESTAMP NOT NULL DEFAULT CURRENT_TIMESTAMP,
    status ENUM('pending', 'approved', 'rejected') COLLATE utf8mb4_general_ci DEFAULT 'pending',
    PRIMARY KEY (id)
);

CREATE TABLE president (
    id INT(11) NOT NULL AUTO_INCREMENT,
    flat INT(255) NOT NULL,
    name VARCHAR(255) COLLATE utf8mb4_general_ci NOT NULL,
    number BIGINT(20) NOT NULL,
    email VARCHAR(255) COLLATE utf8mb4_general_ci NOT NULL,
    created_at TIMESTAMP NOT NULL DEFAULT CURRENT_TIMESTAMP,
    PRIMARY KEY (id)
);

CREATE TABLE residency (
    id INT(11) NOT NULL AUTO_INCREMENT,
    residency_name VARCHAR(255) COLLATE utf8mb4_general_ci NOT NULL,
    number_of_floors INT(11) NOT NULL,
    flats_per_floor INT(11) NOT NULL,
    flat_sequence VARCHAR(255) COLLATE utf8mb4_general_ci NOT NULL,
    residency_address VARCHAR(255) COLLATE utf8mb4_general_ci NOT NULL,
    created_at TIMESTAMP NOT NULL DEFAULT CURRENT_TIMESTAMP,
    PRIMARY KEY (id)
);
CREATE TABLE secretory(
    id INT(11) NOT NULL AUTO_INCREMENT,
    flat INT(255) NOT NULL,
    name VARCHAR(255) COLLATE utf8mb4_general_ci NOT NULL,
    number BIGINT(11) NOT NULL,
    email VARCHAR(255) COLLATE utf8mb4_general_ci NOT NULL,
    created_at TIMESTAMP NOT NULL DEFAULT CURRENT_TIMESTAMP,
    PRIMARY KEY (id)
);
CREATE TABLE userlogin (
    id INT(11) NOT NULL AUTO_INCREMENT,
    name VARCHAR(255) COLLATE utf8mb4_general_ci DEFAULT NULL,
    number VARCHAR(255) COLLATE utf8mb4_general_ci DEFAULT NULL,
    email VARCHAR(255) COLLATE utf8mb4_general_ci DEFAULT NULL,
    acno VARCHAR(255) COLLATE utf8mb4_general_ci DEFAULT NULL,
    image_path VARCHAR(255) COLLATE utf8mb4_general_ci DEFAULT NULL,
    password VARCHAR(255) COLLATE utf8mb4_general_ci DEFAULT NULL,
    floor VARCHAR(255) COLLATE utf8mb4_general_ci DEFAULT NULL,
    flat VARCHAR(255) COLLATE utf8mb4_general_ci DEFAULT NULL,
    who VARCHAR(255) COLLATE utf8mb4_general_ci DEFAULT NULL,
    purchaseDate DATE DEFAULT NULL,
    rentalDate DATE DEFAULT NULL,
    status ENUM('pending', 'approved', 'rejected') COLLATE utf8mb4_general_ci DEFAULT 'pending',
    PRIMARY KEY (id)
);
CREATE TABLE userlogin1 (
    id INT(11) NOT NULL AUTO_INCREMENT,
    name VARCHAR(255) COLLATE utf8mb4_general_ci DEFAULT NULL,
    number VARCHAR(255) COLLATE utf8mb4_general_ci DEFAULT NULL,
    email VARCHAR(255) COLLATE utf8mb4_general_ci DEFAULT NULL,
    acno VARCHAR(255) COLLATE utf8mb4_general_ci DEFAULT NULL,
    image_path VARCHAR(255) COLLATE utf8mb4_general_ci DEFAULT NULL,
    password VARCHAR(255) COLLATE utf8mb4_general_ci DEFAULT NULL,
    floor VARCHAR(255) COLLATE utf8mb4_general_ci DEFAULT NULL,
    flat VARCHAR(255) COLLATE utf8mb4_general_ci DEFAULT NULL,
    who VARCHAR(255) COLLATE utf8mb4_general_ci DEFAULT NULL,
    purchaseDate DATE DEFAULT NULL,
    rentalDate DATE DEFAULT NULL,
    status ENUM('pending', 'approved', 'rejected') COLLATE utf8mb4_general_ci DEFAULT 'pending',
    PRIMARY KEY (id)
);
CREATE TABLE visesecretory (
    id INT(11) NOT NULL AUTO_INCREMENT,
    flat INT(255) NOT NULL,
    name VARCHAR(255) COLLATE utf8mb4_general_ci NOT NULL,
    number BIGINT(11) NOT NULL,
    email VARCHAR(255) COLLATE utf8mb4_general_ci NOT NULL,
    created_at TIMESTAMP NOT NULL DEFAULT CURRENT_TIMESTAMP,
    PRIMARY KEY (id)
);








