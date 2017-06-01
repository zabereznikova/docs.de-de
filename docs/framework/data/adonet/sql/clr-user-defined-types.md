---
title: "Benutzerdefinierte CLR-Typen | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 9f70e0b0-3a0d-4eb1-b914-07a5d0c167c2
caps.latest.revision: 6
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 6
---
# Benutzerdefinierte CLR-Typen
Microsoft SQL Server bietet Unterstützung für benutzerdefinierte Typen \(User\-Defined Types, UDTs\), die mit der CLR \(Common Language Runtime\) von Microsoft .NET Framework implementiert werden.  Durch die Integration der CLR in SQL Server verfügen Sie über einen Mechanismus, mit dessen Hilfe Sie das Typsystem der Datenbank erweitern können.  UDTs ermöglichen neben der Erweiterbarkeit des SQL Server\-Datentypsystems durch Benutzer auch das Definieren komplexer strukturierter Typen.  
  
 UDTs bieten im Hinblick auf die Anwendungsarchitektur zwei wesentliche Vorteile:  
  
-   Starke Kapselung von internem Zustand gegenüber externen Verhaltensweisen \(sowohl auf dem Client als auch auf dem Server\).  
  
-   Enge Integration mit anderen verwandten Serverfunktionen.  Nachdem Sie einen eigenen UDT definiert haben, kann dieser in den gleichen Kontexten verwendet werden wie ein Systemtyp von SQL Server, so u. a. als Spaltendefinitionen, Variablen, Parameter, Funktionsergebnisse, Cursor, Trigger und bei der Replikation.  
  
 Weitere ausführliche Informationen finden Sie in der Onlinedokumentation zu SQL Server für die von Ihnen verwendete Version von SQL Server.  
  
 **SQL Server\-Onlinedokumentation**  
  
1.  [Benutzerdefinierte Typen in der CLR](http://go.microsoft.com/fwlink/?LinkId=98366)  
  
## Siehe auch  
 [Creating SQL Server 2005 Objects In Managed Code](http://msdn.microsoft.com/de-de/5358a825-e19b-49aa-8214-674ce5fed1da)   
 [ADO.NET Verwaltete Anbieter und DataSet\-Entwicklercenter](http://go.microsoft.com/fwlink/?LinkId=217917)