---
title: "CLR-Integration in SQL&#160;Server | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: c7a324c4-160d-44c2-b593-641af06eca61
caps.latest.revision: 4
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 4
---
# CLR-Integration in SQL&#160;Server
In SQL Server 2005 wurde die CLR\-Komponente von .NET Framework für Microsoft Windows eingeführt.  Daher können gespeicherte Prozeduren, Trigger, benutzerdefinierte Datentypen, Funktionen und Aggregate sowie Tabellenwertfunktionen mit kontinuierlichem Datenstream \(STVF, Streaming Table\-Valued Function\) in jeder beliebigen .NET Framework\-Sprache, z. B. Microsoft Visual Basic .NET oder Microsoft Visual C\#, geschrieben werden.  Der <xref:Microsoft.SqlServer.Server>\-Namespace enthält eine Gruppe neuer Anwendungsprogrammierschnittstellen \(APIs\), die die Interaktion von verwaltetem Code mit der Microsoft SQL Server\-Umgebung ermöglichen.  
  
 In diesem Abschnitt werden Funktionen und das Verhalten beschrieben, die bzw. das für die CLR\-Integration in SQL Server und die in SQL Server integrierten Erweiterungen für ADO.NET spezifisch sind bzw. ist.  
  
 In diesem Abschnitt sollen die Informationen bereitgestellt werden, die für den Einstieg in das Programmieren mit der CLR\-Integration in SQL Server erforderlich sind. Es ist nicht Ziel dieses Abschnitts, das Thema umfassend abzudecken.  Weitere ausführliche Informationen finden Sie in der Onlinedokumentation zu SQL Server für die von Ihnen verwendete Version von SQL Server.  
  
 **SQL Server\-Onlinedokumentation**  
  
1.  [Programmierkonzepte für die Common Language Runtime \(CLR\)\-Integration](http://go.microsoft.com/fwlink/?LinkId=115240)  
  
## In diesem Abschnitt  
 [Einführung in die CLR\-Integration für SQL Server](../../../../../docs/framework/data/adonet/sql/introduction-to-sql-server-clr-integration.md)  
 Stellt eine Einführung in die CLR\-Integration in SQL Server bereit.  Stellt Links für weitere Themen bereit.  
  
 [Benutzerdefinierte CLR\-Funktionen](../../../../../docs/framework/data/adonet/sql/clr-user-defined-functions.md)  
 Beschreibt das Implementieren und Verwenden der verschiedenen Arten von CLR\-Funktionen: Tabellenwertfunktionen, Skalarfunktionen und benutzerdefinierte Aggregatfunktionen.  
  
 [Benutzerdefinierte CLR\-Typen](../../../../../docs/framework/data/adonet/sql/clr-user-defined-types.md)  
 Beschreibt das Implementieren und Verwenden von benutzerdefinierten CLR\-Typen.  Stellt Links für weitere Themen bereit.  
  
 [Gespeicherte CLR\-Prozeduren](../../../../../docs/framework/data/adonet/sql/clr-stored-procedures.md)  
 Beschreibt das Implementieren und Verwenden von gespeicherten CLR\-Prozeduren.  Stellt Links für weitere Themen bereit.  
  
 [CLR\-Trigger](../../../../../docs/framework/data/adonet/sql/clr-triggers.md)  
 Beschreibt das Implementieren und Verwenden von CLR\-Triggern.  Stellt Links für weitere Themen bereit.  
  
 [Die Kontextverbindung](../../../../../docs/framework/data/adonet/sql/the-context-connection.md)  
 Beschreibt die Kontextverbindung.  
  
 [Prozessinternes spezifisches Verhalten von ADO.NET in SQL Server](../../../../../docs/framework/data/adonet/sql/sql-server-in-process-specific-behavior-of-adonet.md)  
 Beschreibt die in SQL Server integrierten Erweiterungen für ADO.NET sowie den Verbindungskontext.  Stellt Links für weitere Themen bereit.  
  
## Siehe auch  
 [SQL Server und ADO.NET](../../../../../docs/framework/data/adonet/sql/index.md)   
 [Creating SQL Server 2005 Objects In Managed Code](http://msdn.microsoft.com/de-de/5358a825-e19b-49aa-8214-674ce5fed1da)   
 [ADO.NET Verwaltete Anbieter und DataSet\-Entwicklercenter](http://go.microsoft.com/fwlink/?LinkId=217917)