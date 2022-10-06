# database-gestiune-vanzari
create database 'gestiune vanzari';
CREATE TABLE `clienti` (
  `id_clienti` int(7) NOT NULL,
  `nume_clienti` varchar(50) NOT NULL,
  `prenume_clienti` varchar(50) NOT NULL,
  `varsta_clienti` varchar(50) NOT NULL,
  `telefon_clienti` char(10) NOT NULL,
  `email_clienti` varchar(50) NOT NULL,
  `oras_clienti` varchar(50) NOT NULL,
  `judet_clienti` varchar(50) NOT NULL
) ENGINE=InnoDB DEFAULT CHARSET=utf8mb4;

--
-- Dumping data for table `clienti`
--

INSERT INTO `clienti` (`id_clienti`, `nume_clienti`, `prenume_clienti`, `varsta_clienti`, `telefon_clienti`, `email_clienti`, `oras_clienti`, `judet_clienti`) VALUES
(1, 'Popescu', 'Alexandru', '27', '0765221489', 'popescualexandru99@yahoo.com', 'Slatina', 'Olt'),
(2, 'Eremencu', 'Ioana', '36', '0754886532', 'ioanaeremencu98@yahoo.com', 'Bucuresti', 'Bucuresti'),
(3, 'Andronache', 'Daniel', '34', '0721368597', 'andrdaniel78@yahoo.com', 'Timisoara', 'Timis'),
(4, 'Ionescu', 'George', '33', '0721356987', 'ionescugeorge@yahoo.com', 'Constanta', 'Constanta'),
(5, 'Constantinescu', 'Mihaela', '44', '0756913288', 'constantinescumihaela@yahoo.com', 'Craiova', 'Dolj'),
(6, 'Radulescu', 'Emilia', '42', '0761322589', 'radulescuemilia@yahoo.com', 'Brasov', 'Brasov'),
(7, 'Lica', 'Monica', '25', '0762328741', 'licamonica96@yahoo.com', 'Sibiu', 'Sibiu'),
(8, 'Raduica', 'Alexandru', '26', '0765231897', 'raduicaalex99@yahoo.com', 'Buzau', 'Buzau'),
(9, 'Iordache', 'Simona', '31', '0763214798', 'simonaiordache95@yahoo.com', 'Cluj-Napoca', 'Cluj'),
(10, 'Stoica', 'Rares', '28', '0762371134', 'raresstoica92@yahoo.com', 'Slatina', 'Olt');

-- --------------------------------------------------------

--
-- Table structure for table `comenzi_clienti`
--

CREATE TABLE `comenzi_clienti` (
  `id_comenzi` int(7) NOT NULL,
  `id_clienti` int(7) NOT NULL,
  `data_comenzi` date NOT NULL,
  `modplata_comanda` varchar(50) NOT NULL
) ENGINE=InnoDB DEFAULT CHARSET=utf8mb4;

--
-- Dumping data for table `comenzi_clienti`
--

INSERT INTO `comenzi_clienti` (`id_comenzi`, `id_clienti`, `data_comenzi`, `modplata_comanda`) VALUES
(1, 1, '2022-03-22', 'cash'),
(2, 2, '2022-01-18', 'cash'),
(3, 3, '2021-12-14', 'card'),
(4, 4, '2022-05-22', 'card'),
(5, 5, '2022-03-08', 'cash'),
(6, 6, '2022-04-20', 'cash'),
(7, 7, '2021-11-16', 'cash'),
(8, 8, '2021-06-23', 'card'),
(9, 9, '2022-02-28', 'cash'),
(10, 10, '2021-10-20', 'cash');

-- --------------------------------------------------------

--
-- Table structure for table `comenzi_produse`
--

CREATE TABLE `comenzi_produse` (
  `id_comanda` int(7) NOT NULL,
  `id_comenzi` int(7) NOT NULL,
  `id_produse` int(7) NOT NULL
) ENGINE=InnoDB DEFAULT CHARSET=utf8mb4;

-- --------------------------------------------------------

--
-- Table structure for table `furnizori`
--

CREATE TABLE `furnizori` (
  `id_furnizori` int(7) NOT NULL,
  `nume_furnizori` varchar(50) NOT NULL,
  `oras_furnizori` varchar(50) NOT NULL,
  `judet_furnizori` varchar(50) NOT NULL
) ENGINE=InnoDB DEFAULT CHARSET=utf8mb4;

--
-- Dumping data for table `furnizori`
--

INSERT INTO `furnizori` (`id_furnizori`, `nume_furnizori`, `oras_furnizori`, `judet_furnizori`) VALUES
(1, 'Jacobs', 'Bucuresti', 'Bucuresti'),
(2, 'Milka', 'Bucuresti', 'Bucuresti'),
(3, 'Julius Meinl', 'Sibiu', 'Sibiu'),
(4, 'Coca-Cola', 'Bucuresti', 'Bucuresti'),
(5, 'Coco Rico', 'Brasov', 'Brasov'),
(6, 'Napolact', 'Cluj-Napoca', 'Cluj'),
(7, 'Fanta', 'Bucuresti', 'Bucuresti'),
(8, 'Lays', 'Bucuresti', 'Bucuresti'),
(9, 'Tchibo', 'Bucuresti', 'Bucuresti'),
(10, 'Orbit', 'Bucuresti', 'Bucuresti');

-- --------------------------------------------------------

--
-- Table structure for table `produse`
--

CREATE TABLE `produse` (
  `id_produse` int(7) NOT NULL,
  `id_furnizori` int(7) NOT NULL,
  `descriere_produse` text NOT NULL,
  `pret_produse` int(7) NOT NULL
) ENGINE=InnoDB DEFAULT CHARSET=utf8mb4;

--
-- Dumping data for table `produse`
--

INSERT INTO `produse` (`id_produse`, `id_furnizori`, `descriere_produse`, `pret_produse`) VALUES
(1, 1, 'cafea Jacobs macinata sau boabe', 80),
(2, 2, 'Ciocolata Milka cu nuci,amaruie,ciocolata alba,cu diverse arome cum ar fi capsuni,fragi,mure', 15),
(3, 3, 'zahar brun sau alb', 25),
(4, 4, 'Coca Cola cu lamaie sau diverse arome la 2L sau 1L', 9),
(5, 5, 'pui fraged de tara Coco-Rico la 2kg', 45),
(6, 6, 'Napolact branza proaspata de vaca', 58),
(7, 7, 'Fanta de portocale la 2L', 9),
(8, 8, 'Lays chipsuri cu cascaval,sare', 7),
(9, 9, 'cafea macinata sau boabe', 98),
(10, 10, 'guma de mestecat cu diverse arome Orbit', 4);

--
-- Indexes for dumped tables
--

--
-- Indexes for table `clienti`
--
ALTER TABLE `clienti`
  ADD PRIMARY KEY (`id_clienti`);

--
-- Indexes for table `comenzi_clienti`
--
ALTER TABLE `comenzi_clienti`
  ADD PRIMARY KEY (`id_comenzi`),
  ADD KEY `id_clienti` (`id_clienti`);

--
-- Indexes for table `comenzi_produse`
--
ALTER TABLE `comenzi_produse`
  ADD PRIMARY KEY (`id_comanda`),
  ADD KEY `id_comenzi` (`id_comenzi`),
  ADD KEY `id_produse` (`id_produse`);

--
-- Indexes for table `furnizori`
--
ALTER TABLE `furnizori`
  ADD PRIMARY KEY (`id_furnizori`);

--
-- Indexes for table `produse`
--
ALTER TABLE `produse`
  ADD PRIMARY KEY (`id_produse`),
  ADD KEY `id_furnizori` (`id_furnizori`);

--
-- AUTO_INCREMENT for dumped tables
--

--
-- AUTO_INCREMENT for table `clienti`
--
ALTER TABLE `clienti`
  MODIFY `id_clienti` int(7) NOT NULL AUTO_INCREMENT, AUTO_INCREMENT=11;

--
-- AUTO_INCREMENT for table `comenzi_clienti`
--
ALTER TABLE `comenzi_clienti`
  MODIFY `id_comenzi` int(7) NOT NULL AUTO_INCREMENT, AUTO_INCREMENT=11;

--
-- AUTO_INCREMENT for table `comenzi_produse`
--
ALTER TABLE `comenzi_produse`
  MODIFY `id_comanda` int(7) NOT NULL AUTO_INCREMENT, AUTO_INCREMENT=2;

--
-- AUTO_INCREMENT for table `furnizori`
--
ALTER TABLE `furnizori`
  MODIFY `id_furnizori` int(7) NOT NULL AUTO_INCREMENT, AUTO_INCREMENT=11;

--
-- AUTO_INCREMENT for table `produse`
--
ALTER TABLE `produse`
  MODIFY `id_produse` int(7) NOT NULL AUTO_INCREMENT, AUTO_INCREMENT=11;

--
-- Constraints for dumped tables
--

--
-- Constraints for table `comenzi_clienti`
--
ALTER TABLE `comenzi_clienti`
  ADD CONSTRAINT `comenzi_clienti_ibfk_1` FOREIGN KEY (`id_clienti`) REFERENCES `clienti` (`id_clienti`);

--
-- Constraints for table `comenzi_produse`
--
ALTER TABLE `comenzi_produse`
  ADD CONSTRAINT `comenzi_produse_ibfk_1` FOREIGN KEY (`id_comenzi`) REFERENCES `comenzi_clienti` (`id_comenzi`),
  ADD CONSTRAINT `comenzi_produse_ibfk_2` FOREIGN KEY (`id_produse`) REFERENCES `produse` (`id_produse`);

--
-- Constraints for table `produse`
--
ALTER TABLE `produse`
  ADD CONSTRAINT `produse_ibfk_1` FOREIGN KEY (`id_furnizori`) REFERENCES `furnizori` (`id_furnizori`);
COMMIT;
