---
title: Common Language Runtime-Integration in SQL Server
ms.date: 03/30/2017
ms.assetid: c7a324c4-160d-44c2-b593-641af06eca61
ms.openlocfilehash: 12ae15d72644e314aa694f8d169bc8f45fa284a2
ms.sourcegitcommit: 700ea803fb06c5ce98de017c7f76463ba33ff4a9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/19/2020
ms.locfileid: "77452343"
---
# <a name="sql-server-common-language-runtime-integration"></a>Common Language Runtime-Integration in SQL Server
In SQL Server 2005 wurde die CLR-Komponente von .NET Framework für Microsoft Windows eingeführt. Daher können gespeicherte Prozeduren, Trigger, benutzerdefinierte Datentypen, Funktionen und Aggregate sowie Tabellenwertfunktionen mit kontinuierlichem Datenstream (STVF, Streaming Table-Valued Function) in jeder beliebigen .NET Framework-Sprache, z. B. Microsoft Visual Basic .NET oder Microsoft Visual C#, geschrieben werden. Der <xref:Microsoft.SqlServer.Server>-Namespace enthält eine Gruppe neuer Anwendungsprogrammierschnittstellen (APIs), die die Interaktion von verwaltetem Code mit der Microsoft SQL Server-Umgebung ermöglichen.  
  
 In diesem Abschnitt werden Funktionen und das Verhalten beschrieben, die bzw. das für die CLR-Integration in SQL Server und die in SQL Server integrierten Erweiterungen für ADO.NET spezifisch sind bzw. ist.  
  
 In diesem Abschnitt sollen die Informationen bereitgestellt werden, die für den Einstieg in das Programmieren mit der CLR-Integration in SQL Server erforderlich sind. Es ist nicht Ziel dieses Abschnitts, das Thema umfassend abzudecken. Weitere ausführliche Informationen finden Sie in der Onlinedokumentation zu SQL Server für die von Ihnen verwendete Version von SQL Server.  
  
 **SQL Server-Dokumentation**  
  
1. [Programmierkonzepte für die Common Language Runtime (CLR)-Integration](/sql/relational-databases/clr-integration/common-language-runtime-clr-integration-programming-concepts)  
  
## <a name="in-this-section"></a>In diesem Abschnitt  
 [Einführung in die CLR-Integration in SQL Server](introduction-to-sql-server-clr-integration.md)  
 Stellt eine Einführung in die CLR-Integration in SQL Server bereit. Stellt Links für weitere Themen bereit.  
  
 [CLR-benutzerdefinierte Funktionen](clr-user-defined-functions.md)  
 Beschreibt die Implementierung und Verwendung der unterschiedlichen CLR-Funktionstypen: Tabellenwertfunktionen, Skalarfunktionen und benutzerdefinierte Aggregatfunktionen.  
  
 [Benutzerdefinierte CLR-Typen](clr-user-defined-types.md)  
 Beschreibt die Implementierung und Verwendung von CLR-benutzerdefinierten Typen. Stellt Links für weitere Themen bereit.  
  
 [CLR-gespeicherte Prozeduren](clr-stored-procedures.md)  
 Beschreibt die Implementierung und Verwendung von CLR-gespeicherten Prozeduren. Stellt Links für weitere Themen bereit.  
  
 [CLR-Trigger](clr-triggers.md)  
 Beschreibt die Implementierung und Verwendung von CLR-Triggern. Stellt Links für weitere Themen bereit.  
  
 [Kontextverbindungen](the-context-connection.md)  
 Beschreibt die Kontextverbindung.  
  
 [Prozessinternes spezifisches Verhalten von ADO.NET in SQL Server](sql-server-in-process-specific-behavior-of-adonet.md)  
 Beschreibt die in SQL Server integrierten Erweiterungen für ADO.NET sowie den Verbindungskontext. Stellt Links für weitere Themen bereit.  
  
## <a name="see-also"></a>Siehe auch

- [SQL Server und ADO.NET](index.md)
- [Übersicht über ADO.NET](../ado-net-overview.md)
