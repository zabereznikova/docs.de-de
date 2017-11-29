---
title: Common Language Runtime-Integration in SQL Server
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c7a324c4-160d-44c2-b593-641af06eca61
caps.latest.revision: "4"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 3705db8b9d359ce83c6c47bef58de327745bed44
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="sql-server-common-language-runtime-integration"></a>Common Language Runtime-Integration in SQL Server
In SQL Server 2005 wurde die CLR-Komponente von .NET Framework für Microsoft Windows eingeführt. Daher können gespeicherte Prozeduren, Trigger, benutzerdefinierte Datentypen, Funktionen und Aggregate sowie Tabellenwertfunktionen mit kontinuierlichem Datenstream (STVF, Streaming Table-Valued Function) in jeder beliebigen .NET Framework-Sprache, z. B. Microsoft Visual Basic .NET oder Microsoft Visual C#, geschrieben werden. Der <xref:Microsoft.SqlServer.Server>-Namespace enthält eine Gruppe neuer Anwendungsprogrammierschnittstellen (APIs), die die Interaktion von verwaltetem Code mit der Microsoft SQL Server-Umgebung ermöglichen.  
  
 In diesem Abschnitt werden Funktionen und das Verhalten beschrieben, die bzw. das für die CLR-Integration in SQL Server und die in SQL Server integrierten Erweiterungen für ADO.NET spezifisch sind bzw. ist.  
  
 In diesem Abschnitt sollen die Informationen bereitgestellt werden, die für den Einstieg in das Programmieren mit der CLR-Integration in SQL Server erforderlich sind. Es ist nicht Ziel dieses Abschnitts, das Thema umfassend abzudecken. Weitere ausführliche Informationen finden Sie in der Onlinedokumentation zu SQL Server für die von Ihnen verwendete Version von SQL Server.  
  
 **SQL Server Books Online (SQL Server-Onlinedokumentation)**  
  
1.  [Common Language Runtime (CLR) Integration Programmierkonzepte](http://go.microsoft.com/fwlink/?LinkId=115240)  
  
## <a name="in-this-section"></a>In diesem Abschnitt  
 [Einführung in SQL Server-CLR-Integration](../../../../../docs/framework/data/adonet/sql/introduction-to-sql-server-clr-integration.md)  
 Stellt eine Einführung in die CLR-Integration in SQL Server bereit. Stellt Links für weitere Themen bereit.  
  
 [Benutzerdefinierte CLR-Funktionen](../../../../../docs/framework/data/adonet/sql/clr-user-defined-functions.md)  
 Beschreibt das Implementieren und Verwenden der verschiedenen Arten von CLR-Funktionen: Tabellenwertfunktionen, Skalarfunktionen und benutzerdefinierte Aggregatfunktionen.  
  
 [Benutzerdefinierte CLR-Typen](../../../../../docs/framework/data/adonet/sql/clr-user-defined-types.md)  
 Beschreibt das Implementieren und Verwenden von benutzerdefinierten CLR-Typen. Stellt Links für weitere Themen bereit.  
  
 [CLR-gespeicherte Prozeduren](../../../../../docs/framework/data/adonet/sql/clr-stored-procedures.md)  
 Beschreibt das Implementieren und Verwenden von gespeicherten CLR-Prozeduren. Stellt Links für weitere Themen bereit.  
  
 [CLR-Trigger](../../../../../docs/framework/data/adonet/sql/clr-triggers.md)  
 Beschreibt das Implementieren und Verwenden von CLR-Triggern. Stellt Links für weitere Themen bereit.  
  
 [Die Kontextverbindung](../../../../../docs/framework/data/adonet/sql/the-context-connection.md)  
 Beschreibt die Kontextverbindung.  
  
 [SQL Server In prozessinternes spezifisches Verhalten von ADO.NET](../../../../../docs/framework/data/adonet/sql/sql-server-in-process-specific-behavior-of-adonet.md)  
 Beschreibt die in SQL Server integrierten Erweiterungen für ADO.NET sowie den Verbindungskontext. Stellt Links für weitere Themen bereit.  
  
## <a name="see-also"></a>Siehe auch  
 [SQL Server und ADO.NET](../../../../../docs/framework/data/adonet/sql/index.md)  
 [Erstellen von SQL Server 2005-Objekte In verwaltetem Code](http://msdn.microsoft.com/en-us/5358a825-e19b-49aa-8214-674ce5fed1da)  
 [ADO.NET Managed Provider und DataSet Developer Center](http://go.microsoft.com/fwlink/?LinkId=217917)
