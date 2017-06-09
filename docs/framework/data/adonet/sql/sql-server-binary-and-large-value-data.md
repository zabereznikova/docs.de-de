---
title: "Bin&#228;re Daten und Daten mit umfangreichen Werten in SQL Server | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: e00827b3-7511-4b2d-91d7-851ca86cc6b5
caps.latest.revision: 5
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 5
---
# Bin&#228;re Daten und Daten mit umfangreichen Werten in SQL Server
SQL Server umfasst den `max`\-Bezeichner, der die Speicherkapazität für die Datentypen `varchar`, `nvarchar` und `varbinary` erhöht.  `varchar(max)`, `nvarchar(max)` und `varbinary(max)` werden zusammenfassend als *Datentypen mit umfangreichen Werten* bezeichnet.  Sie können die Datentypen mit umfangreichen Werten zum Speichern von bis zu 2^31\-1 Bytes an Daten verwenden.  
  
 In SQL Server 2008 wird das FILESTREAM\-Attribut eingeführt. Es ist kein Datentyp, sondern eher ein Attribut, das für eine Spalte definiert werden kann, damit Daten mit umfangreichen Werten im Dateisystem statt in der Datenbank gespeichert werden können.  
  
## In diesem Abschnitt  
 [Ändern von Daten mit umfangreichen Werten \(max\) in ADO.NET](../../../../../docs/framework/data/adonet/sql/modifying-large-value-max-data.md)  
 Beschreibt das Arbeiten mit Datentypen für hohe Werte.  
  
 [FILESTREAM\-Daten](../../../../../docs/framework/data/adonet/sql/filestream-data.md)  
 Beschreibt die Verwendung von Datentypen für große Werte, die mit dem FILESTREAM\-Attribut in SQL Server 2008 gespeichert wurden.  
  
## Siehe auch  
 [SQL Server\-Datentypen und ADO.NET](../../../../../docs/framework/data/adonet/sql/sql-server-data-types.md)   
 [SQL Server\-Datenoperationen in ADO.NET](../../../../../docs/framework/data/adonet/sql/sql-server-data-operations.md)   
 [Abrufen und Ändern von Daten in ADO.NET](../../../../../docs/framework/data/adonet/retrieving-and-modifying-data.md)   
 [ADO.NET Verwaltete Anbieter und DataSet\-Entwicklercenter](http://go.microsoft.com/fwlink/?LinkId=217917)