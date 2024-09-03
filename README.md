# How to Load JSON into Azure SQL Table
Azure Data Factory call API and insert data in Blob Storage

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
