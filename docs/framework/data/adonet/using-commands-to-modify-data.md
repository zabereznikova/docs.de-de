---
title: "Verwenden von Befehlen zum &#196;ndern von Daten | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: f4160389-b9ff-4b74-b655-437c76dcd586
caps.latest.revision: 4
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 4
---
# Verwenden von Befehlen zum &#196;ndern von Daten
Mit einem .NET Framework\-Datenanbieter können gespeicherte Prozeduren oder Datendefinitionssprachen\-Anweisungen \(z. B. CREATE TABLE und ALTER COLUMN\) ausgeführt werden, um eine Schemabearbeitung an einer Datenbank oder einem Katalog vorzunehmen.  Bei diesen Befehlen werden keine Zeilen zurückgegeben, wie es bei einer Abfrage der Fall wäre. Daher stellt das **Command**\-Objekt eine **ExecuteNonQuery** für die Verarbeitung bereit.  
  
 Mit der **ExecuteNonQuery**\-Methode können Sie sowohl ein Schema ändern, als auch SQL\-Anweisungen verarbeiten, die Daten ändern, aber keine Zeilen zurückgeben, z. B. INSERT, UPDATE und DELETE.  
  
 Obwohl von der **ExecuteNonQuery**\-Methode keine Zeilen zurückgegeben werden, können Eingabeparameter, Ausgabeparameter und Rückgabewerte übergeben und über die **Parameters**\-Auflistung des **Command**\-Objekts zurückgegeben werden.  
  
## In diesem Abschnitt  
 [Aktualisieren von Daten in einer Datenquelle](../../../../docs/framework/data/adonet/updating-data-in-a-data-source.md)  
 Beschreibt das Ausführen von Befehlen oder gespeicherten Prozeduren, mit denen Daten in einer Datenbank geändert werden.  
  
 [Ausführen von Katalogoperationen](../../../../docs/framework/data/adonet/performing-catalog-operations.md)  
 Beschreibt das Ausführen von Befehlen, mit denen ein Datenbankschema geändert wird.  
  
## Siehe auch  
 [Abrufen und Ändern von Daten in ADO.NET](../../../../docs/framework/data/adonet/retrieving-and-modifying-data.md)   
 [Befehle und Parameter](../../../../docs/framework/data/adonet/commands-and-parameters.md)   
 [ADO.NET Verwaltete Anbieter und DataSet\-Entwicklercenter](http://go.microsoft.com/fwlink/?LinkId=217917)