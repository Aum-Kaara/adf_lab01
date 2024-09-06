# How to Load JSON into Azure SQL Table
Azure Data Factory call API and insert data in Blob Storage
## Create Resource group

Create a resource group 
![image](https://github.com/user-attachments/assets/ec5a7fe3-7faf-4fa5-b35e-eccd793d97cf)

## Create Azure Data Factory

![image](https://github.com/user-attachments/assets/76b0ba1a-7696-42b2-ae22-e2c2817f2faf)

## Create Storage Account

![image](https://github.com/user-attachments/assets/71dc3a17-1a42-4d25-bf7c-26493139e0b5)

## Create SQL Server and Database

![image](https://github.com/user-attachments/assets/0183ca95-61a8-4437-83ba-eb007ec6eca2)

### Change network settings to allow login from your IP Address 

![image](https://github.com/user-attachments/assets/5189e299-0c01-4b93-aa09-abc8dbf10796)

## Create Table using Azure portal 

![image](https://github.com/user-attachments/assets/c1feda42-43a9-4212-ab52-749ee7fd3e79)

use below SQL script to create Table book 

``
CREATE TABLE [dbo].[book](
[author] [nchar](50) NULL,
[isbn] [nchar](20) NULL,
[price] [decimal](18, 0) NULL,
[category] [nchar](20) NULL,
[id] [smallint] IDENTITY(1,1) NOT NULL,
CONSTRAINT [PK_book] PRIMARY KEY CLUSTERED 
(
[id] ASC
)WITH (PAD_INDEX = OFF, STATISTICS_NORECOMPUTE = OFF, IGNORE_DUP_KEY = OFF, ALLOW_ROW_LOCKS = ON, 
ALLOW_PAGE_LOCKS = ON) ON [PRIMARY]
) ON [PRIMARY]
GO
``
### Create New linked service for Azure storage Account

![image](https://github.com/user-attachments/assets/a917a9f7-635f-4e0c-8421-0fe27d53c1c6)
![image](https://github.com/user-attachments/assets/085d202a-1d63-4724-844d-6ca41671c423)

### Create New Linked service for SQL Server Database

![image](https://github.com/user-attachments/assets/5e63b2f6-b812-45a2-bbb6-9ab933e8240e)
![image](https://github.com/user-attachments/assets/475bc1e1-b71a-453d-883d-e1d562272a7b)

### Create Dataset for inbound

![image](https://github.com/user-attachments/assets/e099fbac-df6f-44d3-8b17-6c1ee6189fff)
![image](https://github.com/user-attachments/assets/faaf8883-8ac0-4b12-8517-6f1d54554e6a)

### Create Dataset for outbound SQL Table

![image](https://github.com/user-attachments/assets/a1a22aef-36ed-4364-acad-777b07e0d04d)

### Create Pipeline with copy data activity 

![image](https://github.com/user-attachments/assets/f09ce2ed-37d2-4c7f-9bc5-7d2bc328bc97)

Mapping Settings 

![image](https://github.com/user-attachments/assets/20051619-a636-4fb8-9a5b-945918f273fb)

Use below json to upload into container 
``
{ "store": {
"book": [
{ "category": "reference",
"author": "Nigel Rees",
"title": "Sayings of the Century",
"price": 8.95
},
{ "category": "fiction",
"author": "Evelyn Waugh",
"title": "Sword of Honour",
"price": 12.99
},
{ "category": "fiction",
"author": "Herman Melville",
"title": "Moby Dick",
"isbn": "0-553-21311-3",
"price": 8.99
},
{ "category": "fiction",
"author": "J. R. R. Tolkien",
"title": "The Lord of the Rings",
"isbn": "0-395-19395-8",
"price": 22.99
}
],
"bicycle": {
"color": "red",
"price": 19.95
}
}
}
``
