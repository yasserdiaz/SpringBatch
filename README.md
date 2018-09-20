# SpringBatch

Crear base de datos ERPAPPBATCH y la siguiente Tabla

CREATE TABLE [dbo].[REPORT](
	[ID] [bigint] IDENTITY(1,1) NOT NULL,
	[SALES] [decimal](18, 0) NULL,
	[QUANTITY] [int] NULL,
	[STAFF] [varchar](max) NULL,
	[CREATED_ON] [datetime2](7) NULL
) ON [PRIMARY] TEXTIMAGE_ON [PRIMARY]

En el archivo /src/main/resources/spring/batch/config/spring-datasource.xml

Descomentar para generar la estructura de Spring Batch a nivel de base de datos.

<jdbc:initialize-database data-source="dataSource">
	<jdbc:script location="org/springframework/batch/core/schema-drop-sqlserver.sql" />
	<jdbc:script location="org/springframework/batch/core/schema-sqlserver.sql" />
</jdbc:initialize-database>
    
Luego volver a comentar para no perder los datos.

Ejecutar siempre como "Java Application"
