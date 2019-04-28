---
title: Common Language Runtime-Integration in SQL Server
ms.date: 03/30/2017
ms.assetid: c7a324c4-160d-44c2-b593-641af06eca61
ms.openlocfilehash: fd043aa6c7e5b9246a36146e000e5cba9e090d3e
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61876342"
---
# <a name="sql-server-common-language-runtime-integration"></a>Common Language Runtime-Integration in SQL Server
In SQL Server 2005 wurde die CLR-Komponente von .NET Framework für Microsoft Windows eingeführt. Daher können gespeicherte Prozeduren, Trigger, benutzerdefinierte Datentypen, Funktionen und Aggregate sowie Tabellenwertfunktionen mit kontinuierlichem Datenstream (STVF, Streaming Table-Valued Function) in jeder beliebigen .NET Framework-Sprache, z. B. Microsoft Visual Basic .NET oder Microsoft Visual C#, geschrieben werden. Der <xref:Microsoft.SqlServer.Server>-Namespace enthält eine Gruppe neuer Anwendungsprogrammierschnittstellen (APIs), die die Interaktion von verwaltetem Code mit der Microsoft SQL Server-Umgebung ermöglichen.  
  
 In diesem Abschnitt werden Funktionen und das Verhalten beschrieben, die bzw. das für die CLR-Integration in SQL Server und die in SQL Server integrierten Erweiterungen für ADO.NET spezifisch sind bzw. ist.  
  
 In diesem Abschnitt sollen die Informationen bereitgestellt werden, die für den Einstieg in das Programmieren mit der CLR-Integration in SQL Server erforderlich sind. Es ist nicht Ziel dieses Abschnitts, das Thema umfassend abzudecken. Weitere ausführliche Informationen finden Sie in der Onlinedokumentation zu SQL Server für die von Ihnen verwendete Version von SQL Server.  
  
 **SQL Server Books Online (SQL Server-Onlinedokumentation)**  
  
1. [Common Language Runtime (CLR)-Integration-Programmierkonzepte](https://go.microsoft.com/fwlink/?LinkId=115240)  
  
## <a name="in-this-section"></a>In diesem Abschnitt  
 [Einführung in die CLR-Integration in SQL Server](../../../../../docs/framework/data/adonet/sql/introduction-to-sql-server-clr-integration.md)  
 Stellt eine Einführung in die CLR-Integration in SQL Server bereit. Stellt Links für weitere Themen bereit.  
  
 [Benutzerdefinierte CLR-Funktionen](../../../../../docs/framework/data/adonet/sql/clr-user-defined-functions.md)  
 Beschreibt das Implementieren und Verwenden der verschiedenen Arten von CLR-Funktionen: Tabellenwertfunktionen, Skalarfunktionen und benutzerdefinierte Aggregatfunktionen.  
  
 [Benutzerdefinierte CLR-Typen](../../../../../docs/framework/data/adonet/sql/clr-user-defined-types.md)  
 Beschreibt das Implementieren und Verwenden von benutzerdefinierten CLR-Typen. Stellt Links für weitere Themen bereit.  
  
 [Gespeicherte CLR-Prozeduren](../../../../../docs/framework/data/adonet/sql/clr-stored-procedures.md)  
 Beschreibt das Implementieren und Verwenden von gespeicherten CLR-Prozeduren. Stellt Links für weitere Themen bereit.  
  
 [CLR-Auslöser](../../../../../docs/framework/data/adonet/sql/clr-triggers.md)  
 Beschreibt das Implementieren und Verwenden von CLR-Triggern. Stellt Links für weitere Themen bereit.  
  
 [Kontextverbindungen](../../../../../docs/framework/data/adonet/sql/the-context-connection.md)  
 Beschreibt die Kontextverbindung.  
  
 [Prozessinternes spezifisches Verhalten von ADO.NET in SQL Server](../../../../../docs/framework/data/adonet/sql/sql-server-in-process-specific-behavior-of-adonet.md)  
 Beschreibt die in SQL Server integrierten Erweiterungen für ADO.NET sowie den Verbindungskontext. Stellt Links für weitere Themen bereit.  
  
## <a name="see-also"></a>Siehe auch

- [SQL Server und ADO.NET](../../../../../docs/framework/data/adonet/sql/index.md)
- [ADO.NET Managed Provider und DataSet Developer Center](https://go.microsoft.com/fwlink/?LinkId=217917)
