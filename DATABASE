CREATE DATABASE SWP391
GO 
USE SWP391
GO
-----------------------------------------------------------------------------------------------------------
CREATE TABLE ADMIN
(
	adminID int primary key NOT NULL,
	username varchar(30) unique, 
	password varchar(32) not null check(len(password)>=8)
)
go
-----------------------------------------------------------------------------------------------------------
CREATE TABLE STAFF_USER
(
	staffID int primary key NOT NULL,
	username varchar(30) unique, 
	password varchar(32) not null check(len(password)>=8),
	adminID int foreign key references ADMIN(adminID)
)
go

CREATE TABLE CUSTOMER
(
	cID int primary key NOT NULL, 
	cname nvarchar(30) not null,
	cphone varchar(30), 
	cAddress nvarchar(100), 
	username varchar(30) not null unique,
	password varchar(32) not null check(len(password)>=8), 
	staffID int foreign key references STAFF_USER(staffID)
)
go

CREATE TABLE CONTRACTS
(
	[id] [bigint] NOT NULL,
	[status] [tinyint] NOT NULL,
	[user_id] [int] NOT NULL,
	[user_name] [varchar](50) NOT NULL,
	[user_email] [varchar](50) NOT NULL,
	[user_phone] [varchar](20) NOT NULL,
	[amount] [decimal](15, 4) NOT NULL,
	[payment] [varchar](32) NOT NULL,
	[payment_info] [text] NOT NULL,
	[security] [varchar](16) NOT NULL,
	[created] [int] NOT NULL,
	staffID int foreign key references STAFF_USER(staffID)
) 
GO
-----------------------------------------------------------------------------------------------------------
CREATE TABLE CUSTOMER_User
(
	customerID int primary key NOT NULL,
	name varchar(50),
	gender varchar(6),
	dateofbirth datetime,
	identity_number int,
	email varchar(50),
	phone varchar(15),
	address varchar(128),
	password varchar(40),
	adminID int foreign key references ADMIN(adminID),
	status bit default 1
)
go

CREATE TABLE HISTORY(
    [id] int primary key NOT NULL,
	[username] varchar(32) NOT NULL,
	[name] nvarchar(500) NOT NULL,
	[type_history] nvarchar(100) NOT NULL,
	customerID int foreign key references CUSTOMER_USER(customerID)
)
go

CREATE TABLE PAYMENTHISTORY(
    [user_id] int primary key NOT NULL,
	[user_name] varchar(32) NOT NULL,
	[name] nvarchar(500) NOT NULL,
	[user_phone] varchar(20) NOT NULL,
	[amount] decimal(15, 4) NOT NULL,
	[date] datetime NOT NULL,
	[payment_info] text,
	[status] nvarchar NOT NULL,
	id int foreign key references HISTORY(id)
)
go

CREATE TABLE COMPENSATIONHISTORY(
    [user_id] int primary key NOT NULL,
	[user_name] varchar(32) NOT NULL,
	[name] nvarchar(500) NOT NULL,
	[user_phone] varchar(20) NOT NULL,
	[amount] decimal(15, 4) NOT NULL,
	[date] datetime NOT NULL,
	[compensation_info] text,
	[status] nvarchar NOT NULL,
	id int foreign key references HISTORY(id)
)
go

CREATE TABLE PUNISHMENTHISTORY(
    [user_id] int primary key NOT NULL,
	[user_name] varchar(32) NOT NULL,
	[name] nvarchar(500) NOT NULL,
	[user_phone] varchar(20) NOT NULL,
	[amount] decimal(15, 4) NOT NULL,
	[date] datetime NOT NULL,
	[punishment_info] text,
	[status] nvarchar NOT NULL,
	id int foreign key references HISTORY(id)
)
go

CREATE TABLE ACCIDENTHISTORY(
    [user_id] int primary key NOT NULL,
	[user_name] varchar(32) NOT NULL,
	[name] nvarchar(500) NOT NULL,
	[user_phone] varchar(20) NOT NULL,
	[amount] decimal(15, 4) NOT NULL,
	[date] datetime NOT NULL,
	[accident_info] text,
	[status] nvarchar NOT NULL,
	id int foreign key references HISTORY(id)
)
go

CREATE TABLE [dbo].[CONTRACT]
(
	[id] [bigint] NOT NULL,
	[status] [tinyint] NOT NULL,
	[user_id] [int] NOT NULL,
	[user_name] [varchar](50) NOT NULL,
	[user_email] [varchar](50) NOT NULL,
	[user_phone] [varchar](20) NOT NULL,
	[amount] [decimal](15, 4) NOT NULL,
	[payment] [varchar](32) NOT NULL,
	[payment_info] [text] NOT NULL,
	[security] [varchar](16) NOT NULL,
	[created] [int] NOT NULL,
    customerID int foreign key references CUSTOMER_USER(customerID)
) 
go
-------------------------------------------------------------------------------------------------------------------
INSERT INTO STAFF_USER VALUES
(01,'daodung','99999999',1),
(02,'xuanhung','99999999',1),
(03,'bacuong','99999999',1),
(04,'minhhoang','99999999',1),
(05,'ductrung','99999999',1),
(06,'hoanghieu','99999999',1)

INSERT INTO CUSTOMER_User VALUES
(01,'teamswp','nam',22/05/2021,'0274151532','abc@gmail.com','0912576811','hanoi','99999999',1,1)






