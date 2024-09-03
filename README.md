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
