For using thhis website u can download above files and you can clone below mysql code for backend tables:



-- phpMyAdmin SQL Dump
-- version 5.0.3
-- https://www.phpmyadmin.net/
--
-- Host: 127.0.0.1
-- Generation Time: Feb 17, 2021 at 04:35 PM
-- Server version: 10.4.14-MariaDB
-- PHP Version: 7.4.11

SET SQL_MODE = "NO_AUTO_VALUE_ON_ZERO";
START TRANSACTION;
SET time_zone = "+00:00";


/*!40101 SET @OLD_CHARACTER_SET_CLIENT=@@CHARACTER_SET_CLIENT */;
/*!40101 SET @OLD_CHARACTER_SET_RESULTS=@@CHARACTER_SET_RESULTS */;
/*!40101 SET @OLD_COLLATION_CONNECTION=@@COLLATION_CONNECTION */;
/*!40101 SET NAMES utf8mb4 */;

--
-- Database: `agriculture_farmer`
--

-- --------------------------------------------------------

--
-- Table structure for table `adminlogin`
--

CREATE TABLE `adminlogin` (
  `testerid` varchar(30) NOT NULL,
  `password` varchar(30) NOT NULL
) ENGINE=InnoDB DEFAULT CHARSET=utf8mb4;

--
-- Dumping data for table `adminlogin`
--

INSERT INTO `adminlogin` (`testerid`, `password`) VALUES
('vaishnav28', '19228'),
('varshit03', '19203'),
('prashanth18', '19218'),
('krishna26', '19226');

-- --------------------------------------------------------

--
-- Table structure for table `area`
--

CREATE TABLE `area` (
  `area_id` varchar(5) NOT NULL,
  `area_name` varchar(20) NOT NULL,
  `season` varchar(20) NOT NULL,
  `fall_percentage` int(11) NOT NULL,
  `high_temp` int(11) NOT NULL,
  `low_temp` int(11) NOT NULL,
  `town_id` int(11) NOT NULL
) ENGINE=InnoDB DEFAULT CHARSET=utf8mb4;

--
-- Dumping data for table `area`
--

INSERT INTO `area` (`area_id`, `area_name`, `season`, `fall_percentage`, `high_temp`, `low_temp`, `town_id`) VALUES
('301', 'Ram nagar', 'winter', 45, 30, 20, 201),
('302', 'Krishna nagar', 'Winter', 39, 32, 25, 202),
('303', 'Sai nagar', 'Winter', 25, 38, 21, 203),
('304', 'Gandhi nagar', 'Winter', 45, 30, 19, 204),
('305', 'Amrutha nagar', 'Winter', 65, 27, 21, 205),
('306', 'Srinivas nagar', 'Winter', 39, 36, 19, 206),
('307', 'sbi colony', 'Winter', 22, 39, 29, 207),
('308', 'Madhapur', 'winter', 20, 33, 28, 208),
('309', 'Ymr colony', 'Winter', 48, 33, 29, 209),
('310', 'Sanjeev nagar', 'Winter', 68, 28, 22, 210);

-- --------------------------------------------------------

--
-- Table structure for table `district`
--

CREATE TABLE `district` (
  `district_id` int(11) NOT NULL,
  `district_name` varchar(20) NOT NULL,
  `agri_area` int(11) NOT NULL,
  `no_of_towns` int(11) NOT NULL
) ENGINE=InnoDB DEFAULT CHARSET=utf8mb4;

--
-- Dumping data for table `district`
--

INSERT INTO `district` (`district_id`, `district_name`, `agri_area`, `no_of_towns`) VALUES
(101, 'Ananthapur', 30, 1),
(102, 'Coimbature', 50, 1),
(103, 'Erode', 45, 1),
(104, 'ernakulam', 60, 1),
(105, 'Nellore', 25, 1),
(106, 'Kurnool', 30, 1),
(107, 'Thrissur', 30, 1),
(108, 'Kadapa', 30, 1),
(109, 'Thiruvananathapuram', 30, 1),
(110, 'Vizag', 70, 1);

-- --------------------------------------------------------

--
-- Table structure for table `farmer`
--

CREATE TABLE `farmer` (
  `farmer_id` bigint(12) NOT NULL,
  `soil_id` int(11) NOT NULL,
  `farmer_name` varchar(50) NOT NULL,
  `phone_number` bigint(10) NOT NULL,
  `address` varchar(100) NOT NULL,
  `district` varchar(50) NOT NULL,
  `town` varchar(50) NOT NULL,
  `area` varchar(50) NOT NULL,
  `Date` date NOT NULL
) ENGINE=InnoDB DEFAULT CHARSET=utf8mb4;

--
-- Dumping data for table `farmer`
--

INSERT INTO `farmer` (`farmer_id`, `soil_id`, `farmer_name`, `phone_number`, `address`, `district`, `town`, `area`, `Date`) VALUES
(1234567890, 18, 'vaish', 7816087189, 'nandyal rramanath reddy nagar', 'kurnool', 'nandyal', 'srinivas nagar', '2020-11-29'),
(102938475612, 19, 'sathwik', 9876543212, 'nandyal ramanath reddy nagar', 'kurnool', 'Nandyal', 'Srinivas nagar', '2020-11-29'),
(879098849312, 20, 'vaishnav', 7816087189, 'ramanath reddy nagar', 'kurnool', 'hyderabad', 'Srinivas nagar', '2020-11-30'),
(781608718912, 21, 'surya', 7816087189, 'h-no:25', 'kurnool', 'hyderabad', 'Srinivas nagar', '2020-11-30'),
(9849542874, 22, 'ramu', 1234567890, 'buo', 'kurnool', 'hyderabad', 'Srinivas nagar', '2020-12-23');

-- --------------------------------------------------------

--
-- Table structure for table `fertiliser`
--

CREATE TABLE `fertiliser` (
  `fertiliser_id` int(11) NOT NULL,
  `fertiliser_name` varchar(50) NOT NULL,
  `nutrient_id` int(11) NOT NULL,
  `nutrient_percentage` int(11) NOT NULL
) ENGINE=InnoDB DEFAULT CHARSET=utf8mb4;

--
-- Dumping data for table `fertiliser`
--

INSERT INTO `fertiliser` (`fertiliser_id`, `fertiliser_name`, `nutrient_id`, `nutrient_percentage`) VALUES
(901, 'Boron', 1638, 20),
(902, 'Ammonium Sulphate', 1638, 40),
(903, 'Ammonium Chloride', 1638, 60),
(904, 'Diammonium Phosphate', 1638, 80),
(905, 'Boric Acid', 5131, 20),
(906, ' Ferrous Sulphate ', 5131, 40),
(907, ' Nitrophosphate with', 5131, 60),
(908, 'Alluminium', 5131, 80);

-- --------------------------------------------------------

--
-- Table structure for table `nutrient`
--

CREATE TABLE `nutrient` (
  `nutrient_id` int(11) NOT NULL
) ENGINE=InnoDB DEFAULT CHARSET=utf8mb4;

--
-- Dumping data for table `nutrient`
--

INSERT INTO `nutrient` (`nutrient_id`) VALUES
(1638),
(5131);

-- --------------------------------------------------------

--
-- Table structure for table `nutrient_farmer`
--

CREATE TABLE `nutrient_farmer` (
  `nutrient_id` int(11) NOT NULL,
  `nutrient_name` varchar(20) DEFAULT NULL,
  `crop_name` varchar(20) DEFAULT NULL,
  `nutrient_percentage` int(11) NOT NULL
) ENGINE=InnoDB DEFAULT CHARSET=utf8mb4;

--
-- Dumping data for table `nutrient_farmer`
--

INSERT INTO `nutrient_farmer` (`nutrient_id`, `nutrient_name`, `crop_name`, `nutrient_percentage`) VALUES
(1638, 'Potassium', 'Soya beans', 20),
(1638, 'Potassium', 'Sweet Corn', 40),
(1638, 'Potassium', 'Wheat', 60),
(1638, 'Potassium', 'Bajra', 80),
(5131, 'Nitrogen', 'Jowar', 20),
(5131, 'Nitrogen', 'Millets', 40),
(5131, 'Nitrogen', 'Peanuts', 60),
(5131, 'Nitrogen', 'Rice', 80);

-- --------------------------------------------------------

--
-- Table structure for table `soil`
--

CREATE TABLE `soil` (
  `record_id` int(11) NOT NULL,
  `soil_id` int(11) NOT NULL,
  `nutrient_id` int(11) NOT NULL,
  `soil_type` varchar(20) NOT NULL,
  `nutrient_percentage` int(11) NOT NULL
) ENGINE=InnoDB DEFAULT CHARSET=utf8mb4;

--
-- Dumping data for table `soil`
--

INSERT INTO `soil` (`record_id`, `soil_id`, `nutrient_id`, `soil_type`, `nutrient_percentage`) VALUES
(13, 18, 1638, 'fertile', 20),
(14, 19, 1638, 'fertile', 20),
(15, 20, 5131, 'moderate', 60),
(16, 21, 1638, 'fertile', 60),
(17, 22, 1638, 'fertile', 10),
(18, 22, 1638, 'fertile', 10);

-- --------------------------------------------------------

--
-- Table structure for table `ss`
--

CREATE TABLE `ss` (
  `fall_percentage` int(11) NOT NULL,
  `farmer_id` bigint(12) NOT NULL,
  `soil_id` int(11) NOT NULL,
  `record_id` int(11) NOT NULL DEFAULT 0,
  `nutrient_name` varchar(20) DEFAULT NULL,
  `soil_type` varchar(20) NOT NULL,
  `technique_name` varchar(20) NOT NULL,
  `nutrient_percentage` int(11) DEFAULT NULL,
  `crop_name` varchar(20) DEFAULT NULL,
  `fertiliser_name` varchar(20) NOT NULL
) ENGINE=InnoDB DEFAULT CHARSET=utf8mb4;

--
-- Dumping data for table `ss`
--

INSERT INTO `ss` (`fall_percentage`, `farmer_id`, `soil_id`, `record_id`, `nutrient_name`, `soil_type`, `technique_name`, `nutrient_percentage`, `crop_name`, `fertiliser_name`) VALUES
(45, 111111111111, 1, 1, 'x', 'sdfds', 'a', 10, 'hfgdhf', 'dsfds');

-- --------------------------------------------------------

--
-- Table structure for table `technique`
--

CREATE TABLE `technique` (
  `technique_id` int(11) NOT NULL,
  `technique_name` varchar(50) NOT NULL,
  `nutrient_id` int(11) NOT NULL,
  `nutrient_percentage` int(11) NOT NULL
) ENGINE=InnoDB DEFAULT CHARSET=utf8mb4;

--
-- Dumping data for table `technique`
--

INSERT INTO `technique` (`technique_id`, `technique_name`, `nutrient_id`, `nutrient_percentage`) VALUES
(1235, 'Genetic manipulation', 1638, 20),
(1236, 'Intensive tillage', 1638, 40),
(1237, 'Monoculture', 1638, 60),
(1238, 'chemical pest contro', 1638, 80),
(1239, 'Use of synthetic fer', 5131, 20),
(1240, 'Natural pest predato', 5131, 40),
(1241, 'Bio-intensive Integr', 5131, 60),
(1242, 'Crop rotation', 5131, 80);

-- --------------------------------------------------------

--
-- Table structure for table `town_farmer`
--

CREATE TABLE `town_farmer` (
  `town_id` int(11) NOT NULL,
  `town_name` varchar(20) DEFAULT NULL,
  `no_of_areas` int(11) DEFAULT NULL,
  `dist_id` int(11) DEFAULT NULL
) ENGINE=InnoDB DEFAULT CHARSET=utf8mb4;

--
-- Dumping data for table `town_farmer`
--

INSERT INTO `town_farmer` (`town_id`, `town_name`, `no_of_areas`, `dist_id`) VALUES
(201, 'dhone', 1, 101),
(202, 'valparai', 1, 102),
(203, 'Lakkampatti', 1, 103),
(204, 'Kochi', 1, 104),
(205, 'Krishnapatnam', 1, 105),
(206, 'Nandyal', 1, 106),
(207, 'Annamanada', 1, 107),
(208, 'Proddatur', 1, 108),
(209, 'Kaniyapuram', 1, 109),
(210, 'Bheemili', 1, 110);

--
-- Indexes for dumped tables
--

--
-- Indexes for table `area`
--
ALTER TABLE `area`
  ADD PRIMARY KEY (`area_id`),
  ADD KEY `town_id` (`town_id`);

--
-- Indexes for table `district`
--
ALTER TABLE `district`
  ADD PRIMARY KEY (`district_id`);

--
-- Indexes for table `farmer`
--
ALTER TABLE `farmer`
  ADD PRIMARY KEY (`soil_id`),
  ADD UNIQUE KEY `farmer_id` (`farmer_id`);

--
-- Indexes for table `fertiliser`
--
ALTER TABLE `fertiliser`
  ADD PRIMARY KEY (`fertiliser_id`),
  ADD KEY `fk_nutrient_id` (`nutrient_id`);

--
-- Indexes for table `nutrient`
--
ALTER TABLE `nutrient`
  ADD PRIMARY KEY (`nutrient_id`);

--
-- Indexes for table `nutrient_farmer`
--
ALTER TABLE `nutrient_farmer`
  ADD PRIMARY KEY (`nutrient_id`,`nutrient_percentage`);

--
-- Indexes for table `soil`
--
ALTER TABLE `soil`
  ADD PRIMARY KEY (`record_id`),
  ADD KEY `fk_soil_id` (`soil_id`);

--
-- Indexes for table `technique`
--
ALTER TABLE `technique`
  ADD PRIMARY KEY (`technique_id`);

--
-- Indexes for table `town_farmer`
--
ALTER TABLE `town_farmer`
  ADD PRIMARY KEY (`town_id`),
  ADD KEY `dist_id` (`dist_id`);

--
-- AUTO_INCREMENT for dumped tables
--

--
-- AUTO_INCREMENT for table `farmer`
--
ALTER TABLE `farmer`
  MODIFY `soil_id` int(11) NOT NULL AUTO_INCREMENT, AUTO_INCREMENT=23;

--
-- AUTO_INCREMENT for table `fertiliser`
--
ALTER TABLE `fertiliser`
  MODIFY `fertiliser_id` int(11) NOT NULL AUTO_INCREMENT, AUTO_INCREMENT=909;

--
-- AUTO_INCREMENT for table `soil`
--
ALTER TABLE `soil`
  MODIFY `record_id` int(11) NOT NULL AUTO_INCREMENT, AUTO_INCREMENT=19;

--
-- AUTO_INCREMENT for table `technique`
--
ALTER TABLE `technique`
  MODIFY `technique_id` int(11) NOT NULL AUTO_INCREMENT, AUTO_INCREMENT=1243;

--
-- Constraints for dumped tables
--

--
-- Constraints for table `area`
--
ALTER TABLE `area`
  ADD CONSTRAINT `area_ibfk_1` FOREIGN KEY (`town_id`) REFERENCES `town_farmer` (`town_id`);

--
-- Constraints for table `district`
--
ALTER TABLE `district`
  ADD CONSTRAINT `district_ibfk_1` FOREIGN KEY (`town_id`) REFERENCES `town` (`town_id`);

--
-- Constraints for table `fertiliser`
--
ALTER TABLE `fertiliser`
  ADD CONSTRAINT `fk_nutrient_id` FOREIGN KEY (`nutrient_id`) REFERENCES `nutrient` (`nutrient_id`);

--
-- Constraints for table `soil`
--
ALTER TABLE `soil`
  ADD CONSTRAINT `fk_soil_id` FOREIGN KEY (`soil_id`) REFERENCES `farmer` (`soil_id`);

--
-- Constraints for table `town_farmer`
--
ALTER TABLE `town_farmer`
  ADD CONSTRAINT `town_farmer_ibfk_1` FOREIGN KEY (`dist_id`) REFERENCES `district` (`district_id`);
COMMIT;

/*!40101 SET CHARACTER_SET_CLIENT=@OLD_CHARACTER_SET_CLIENT */;
/*!40101 SET CHARACTER_SET_RESULTS=@OLD_CHARACTER_SET_RESULTS */;
/*!40101 SET COLLATION_CONNECTION=@OLD_COLLATION_CONNECTION */;

