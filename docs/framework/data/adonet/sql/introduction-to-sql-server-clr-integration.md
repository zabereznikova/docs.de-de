---
title: Einführung in die CLR-Integration in SQL Server
ms.date: 03/30/2017
ms.assetid: 551d2290-ed80-49be-b377-44b32444da1c
ms.openlocfilehash: dc7d19bf361ed5fcda1fd5edf64eeb5e4ce15a71
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59336810"
---
# <a name="introduction-to-sql-server-clr-integration"></a>Einführung in die CLR-Integration in SQL Server
Die CLR-Komponente (Common Language Runtime) bildet das Kernstück von Microsoft .NET Framework und stellt die Ausführungsumgebung für den gesamten Code in .NET Framework bereit. In der CLR ausgeführter Code wird als verwalteter Code bezeichnet. Die CLR stellt verschiedene Funktionen und Dienste bereit, die für die Programmausführung erforderlich sind. Hierzu zählen z. B. JIT-Kompilierung (Just-In-Time), Zuordnung und Verwaltung des Arbeitsspeichers, Erzwingen von Typsicherheit, Ausnahmebehandlung, Threadverwaltung und Sicherheit.  
  
 Durch das Einbetten der CLR-Komponente in Microsoft SQL Server (CLR-Integration) besteht nun die Möglichkeit, gespeicherte Prozeduren, Trigger, benutzerdefinierte Funktionen, benutzerdefinierte Typen und benutzerdefinierte Aggregate in verwaltetem Code zu erstellen. Da verwalteter Code vor der Ausführung in nativen Code kompiliert wird, können Sie in einigen Szenarien deutliche Leistungssteigerungen erzielen.  
  
 Verwalteter Code kann mithilfe von Codezugriffssicherheit (CAS – Code Access Security), Codelinks und Anwendungsdomänen verhindern, dass Assemblys bestimmte Vorgänge ausführen. In SQL Server trägt die Verwendung der Codezugriffssicherheit zur Sicherung des verwalteten Codes und zum Schutz des Betriebssystems und des Datenbankservers vor schädigenden Eingriffen bei.  
  
 In diesem Abschnitt sollen die Informationen bereitgestellt werden, die für den Einstieg in das Programmieren mit der CLR-Integration in SQL Server erforderlich sind. Es ist nicht Ziel dieses Abschnitts, das Thema umfassend abzudecken. Weitere ausführliche Informationen finden Sie in der Onlinedokumentation zu SQL Server für die von Ihnen verwendete Version von SQL Server.  
  
 **SQL Server Books Online (SQL Server-Onlinedokumentation)**  
  
-   [Übersicht über Common Language Runtime (CLR)-Integration](https://go.microsoft.com/fwlink/?LinkId=115242)  
  
## <a name="enabling-clr-integration"></a>Aktivieren der CLR-Integration  
 Die Funktion zur Integration der Common Language Runtime (CLR) ist in Microsoft SQL-Server in der Standardeinstellung deaktiviert und muss aktiviert werden, damit die mithilfe der CLR-Integration implementierten Objekte verwendet werden können. Um die CLR-Integration mit Transact-SQL zu aktivieren, verwenden Sie Option `clr enabled` der gespeicherten Prozedur `sp_configure` wie folgt:  
  
```  
sp_configure 'clr enabled', 1  
GO  
RECONFIGURE  
GO  
```  
  
 Sie können die CLR-Integration deaktivieren, indem Sie für die `clr enabled`-Option 0 festlegen. Wenn Sie die CLR-Integration deaktivieren, stoppt SQL Server die Ausführung aller CLR-Routinen und entlädt alle Anwendungsdomänen.  
  
 Weitere ausführliche Informationen finden Sie in der Onlinedokumentation zu SQL Server für die von Ihnen verwendete Version von SQL Server.  
  
 **SQL Server Books Online (SQL Server-Onlinedokumentation)**  
  
-   [Aktivieren der Clrintegration](https://go.microsoft.com/fwlink/?LinkId=115230)  
  
## <a name="deploying-a-clr-assembly"></a>Bereitstellen einer CLR-Assembly  
 Sobald die CLR-Methoden auf dem Testserver getestet und verifiziert wurden, können sie mit einem Bereitstellungsskript auf die Produktionsserver verteilt werden. Das Bereitstellungsskript kann manuell oder mit SQL Server Management Studio generiert werden. Weitere ausführliche Informationen finden Sie in der Onlinedokumentation zu SQL Server für die von Ihnen verwendete Version von SQL Server.  
  
 **SQL Server Books Online (SQL Server-Onlinedokumentation)**  
  
1. [Bereitstellen von CLR-Datenbankobjekten](https://go.microsoft.com/fwlink/?LinkId=115232)  
  
## <a name="clr-integration-security"></a>Sicherheit bei der CLR-Integration  
 Das Sicherheitsmodell der Microsoft SQL Server-Integration in der Common Language Runtime (CLR) von Microsoft .NET Framework verwaltet und sichert den Zugriff zwischen verschiedenen Typen von CLR-Objekten und Nicht-CLR-Objekten, die in SQL Server ausgeführt werden. Diese Objekte können durch eine Transact-SQL-Anweisung oder durch ein anderes, auf dem Server ausgeführtes CLR-Objekt aufgerufen werden.  
  
 Weitere ausführliche Informationen finden Sie in der Onlinedokumentation zu SQL Server für die von Ihnen verwendete Version von SQL Server.  
  
 **SQL Server Books Online (SQL Server-Onlinedokumentation)**  
  
-   [Sicherheit der CLR-Integration](https://go.microsoft.com/fwlink/?LinkId=115234)  
  
## <a name="debugging-a-clr-assembly"></a>Debuggen einer CLR-Assembly  
 Microsoft SQL Server stellt Unterstützung für das Debuggen von Transact-SQL und CLR-Objekten (Common Language Runtime) in der Datenbank bereit. Das Debuggen funktioniert sprachübergreifend. Benutzer können problemlos von Transact-SQL zu CLR-Objekten wechseln und umgekehrt.  
  
 Weitere ausführliche Informationen finden Sie in der Onlinedokumentation zu SQL Server für die von Ihnen verwendete Version von SQL Server.  
  
 **SQL Server Books Online (SQL Server-Onlinedokumentation)**  
  
-   [Debuggen von CLR-Datenbankobjekten](https://go.microsoft.com/fwlink/?LinkId=115236)  
  
## <a name="see-also"></a>Siehe auch

- [Codezugriffssicherheit und ADO.NET](../../../../../docs/framework/data/adonet/code-access-security.md)
- [ADO.NET Managed Provider und DataSet Developer Center](https://go.microsoft.com/fwlink/?LinkId=217917)
