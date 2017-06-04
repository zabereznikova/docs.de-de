---
title: "Verbinden mit einer Datenquelle in ADO.NET | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 9abc3f92-1be3-4e1a-b360-762dc689650e
caps.latest.revision: 3
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 3
---
# Verbinden mit einer Datenquelle in ADO.NET
In ADO.NET stellen Sie mithilfe eines **Connection**\-Objekts die Verbindung mit einer bestimmten Datenquelle her, indem Sie die erforderlichen Authentifizierungsinformationen in einer Verbindungszeichenfolge angeben.  Das von Ihnen verwendete **Connection**\-Objekt hängt vom Typ der Datenquelle ab.  
  
 Jeder in .NET Framework enthaltene .NET Framework\-Datenanbieter enthält ein <xref:System.Data.Common.DbConnection>\-Objekt: Der .NET Framework\-Datenanbieter für OLE DB enthält ein <xref:System.Data.OleDb.OleDbConnection>\-Objekt, der .NET Framework\-Datenanbieter für SQL Server enthält ein <xref:System.Data.SqlClient.SqlConnection>\-Objekt, der .NET Framework\-Datenanbieter für ODBC enthält ein <xref:System.Data.Odbc.OdbcConnection>\-Objekt, und der .NET Framework\-Datenanbieter für Oracle enthält ein <xref:System.Data.OracleClient.OracleConnection>\-Objekt.  
  
## In diesem Abschnitt  
 [Herstellen der Verbindung](../../../../docs/framework/data/adonet/establishing-the-connection.md)  
 Beschreibt die Verwendung eines **Connection**\-Objekts zum Herstellen einer Verbindung mit einer Datenquelle.  
  
 ['Connection'\-Ereignisse](../../../../docs/framework/data/adonet/connection-events.md)  
 Beschreibt die Verwendung eines **InfoMessage**\-Ereignisses zum Abrufen von Informationsmeldungen von einer Datenquelle.  
  
## Siehe auch  
 [Verbindungszeichenfolgen](../../../../docs/framework/data/adonet/connection-strings.md)   
 [Verbindungspooling](../../../../docs/framework/data/adonet/connection-pooling.md)   
 [Befehle und Parameter](../../../../docs/framework/data/adonet/commands-and-parameters.md)   
 [DataAdapter und DataReader](../../../../docs/framework/data/adonet/dataadapters-and-datareaders.md)   
 [Transaktionen und Parallelität](../../../../docs/framework/data/adonet/transactions-and-concurrency.md)   
 [ADO.NET Verwaltete Anbieter und DataSet\-Entwicklercenter](http://go.microsoft.com/fwlink/?LinkId=217917)