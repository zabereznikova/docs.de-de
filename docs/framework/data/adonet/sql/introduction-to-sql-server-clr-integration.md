---
title: Einführung in die CLR-Integration in SQL Server
ms.date: 03/30/2017
ms.assetid: 551d2290-ed80-49be-b377-44b32444da1c
ms.openlocfilehash: 41dd89af4f45c673cf6b7283fc39aaf91fd9963c
ms.sourcegitcommit: 700ea803fb06c5ce98de017c7f76463ba33ff4a9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/19/2020
ms.locfileid: "77452408"
---
# <a name="introduction-to-sql-server-clr-integration"></a>Einführung in die CLR-Integration in SQL Server
CLR (Common Language Runtime) steht im Mittelpunkt von Microsoft .NET Framework und stellt die Ausführungsumgebung für sämtlichen .NET Framework-Code bereit. In CLR geschriebener Code wird als verwalteter Code bezeichnet. CLR stellt verschiedene Funktionen und Dienste für die Programmausführung bereit, unter anderem Just-In-Time-Kompilierung (JIT), Speicherzuordnung und -verwaltung, Erzwingen der Typsicherheit, Ausnahmebehandlung, Threadverwaltung und Sicherheit.  
  
 Mit der von Microsoft SQL Server gehosteten CLR ("CLR-Integration" genannt) können Sie gespeicherte Prozeduren, Trigger, benutzerdefinierte Funktionen, benutzerdefinierte Typen (UDT) und benutzerdefinierte Aggregate in verwaltetem Code erstellen. Da verwalteter Code vor der Ausführung in systemeigenen Code kompiliert wird, können Sie in manchen Fällen einen erheblichen Leistungsanstieg erreichen.  
  
 Verwalteter Code kann mithilfe von Codezugriffssicherheit (CAS – Code Access Security), Codelinks und Anwendungsdomänen verhindern, dass Assemblys bestimmte Vorgänge ausführen. In SQL Server trägt die Verwendung der Codezugriffssicherheit zur Sicherung des verwalteten Codes und zum Schutz des Betriebssystems und des Datenbankservers vor schädigenden Eingriffen bei.  
  
 In diesem Abschnitt sollen die Informationen bereitgestellt werden, die für den Einstieg in das Programmieren mit der CLR-Integration in SQL Server erforderlich sind. Es ist nicht Ziel dieses Abschnitts, das Thema umfassend abzudecken. Weitere ausführliche Informationen finden Sie in der Onlinedokumentation zu SQL Server für die von Ihnen verwendete Version von SQL Server.  
  
 **SQL Server-Dokumentation**  
  
- [Übersicht über die CLR-Integration (Common Language Runtime)](/sql/relational-databases/clr-integration/common-language-runtime-integration-overview)  
  
## <a name="enabling-clr-integration"></a>Aktivieren der CLR-Integration  
 Die Funktion zur Integration der Common Language Runtime (CLR) ist in Microsoft SQL-Server in der Standardeinstellung deaktiviert und muss aktiviert werden, damit die mithilfe der CLR-Integration implementierten Objekte verwendet werden können. Um die CLR-Integration mit Transact-SQL zu aktivieren, verwenden Sie Option `clr enabled` der gespeicherten Prozedur `sp_configure` wie folgt:  
  
```sql  
sp_configure 'clr enabled', 1  
GO  
RECONFIGURE  
GO  
```  
  
 Sie können die CLR-Integration deaktivieren, indem Sie für die `clr enabled`-Option 0 festlegen. Wenn Sie die CLR-Integration deaktivieren, stoppt SQL Server die Ausführung aller CLR-Routinen und entlädt alle Anwendungsdomänen.  
  
 Weitere ausführliche Informationen finden Sie in der Onlinedokumentation zu SQL Server für die von Ihnen verwendete Version von SQL Server.  
  
 **SQL Server-Dokumentation**  
  
- [Aktivieren der CLR-Integration](/sql/relational-databases/clr-integration/clr-integration-enabling)  
  
## <a name="deploying-a-clr-assembly"></a>Bereitstellen einer CLR-Assembly  
 Sobald die CLR-Methoden auf dem Testserver getestet und verifiziert wurden, können sie mit einem Bereitstellungsskript auf die Produktionsserver verteilt werden. Das Bereitstellungsskript kann manuell oder mit SQL Server Management Studio generiert werden. Ausführlichere Informationen finden Sie in der-Version SQL Server Dokumentation für die verwendete Version von SQL Server.  
  
 **SQL Server-Dokumentation**  
  
1. [Bereitstellen von CLR-Datenbankobjekten](/sql/relational-databases/clr-integration/deploying-clr-database-objects)  
  
## <a name="clr-integration-security"></a>Sicherheit der CLR-Integration  
 Das Sicherheitsmodell der Microsoft SQL Server-Integration in der Common Language Runtime (CLR) von Microsoft .NET Framework verwaltet und sichert den Zugriff zwischen verschiedenen Typen von CLR-Objekten und Nicht-CLR-Objekten, die in SQL Server ausgeführt werden. Diese Objekte können durch eine Transact-SQL-Anweisung oder durch ein anderes, auf dem Server ausgeführtes CLR-Objekt aufgerufen werden.  
  
 Weitere ausführliche Informationen finden Sie in der Onlinedokumentation zu SQL Server für die von Ihnen verwendete Version von SQL Server.  
  
 **SQL Server-Dokumentation**  
  
- [Sicherheit der CLR-Integration](/sql/relational-databases/clr-integration/security/clr-integration-security)  
  
## <a name="debugging-a-clr-assembly"></a>Debuggen einer CLR-Assembly  
 Microsoft SQL Server stellt Unterstützung für das Debuggen von Transact-SQL und CLR-Objekten (Common Language Runtime) in der Datenbank bereit. Das Debuggen funktioniert sprachübergreifend. Benutzer können problemlos von Transact-SQL zu CLR-Objekten wechseln und umgekehrt.  
  
 Weitere ausführliche Informationen finden Sie in der Onlinedokumentation zu SQL Server für die von Ihnen verwendete Version von SQL Server.  
  
 **SQL Server-Dokumentation**  
  
- [Debuggen von CLR-Datenbankobjekten](/sql/relational-databases/clr-integration/debugging-clr-database-objects)  
  
## <a name="see-also"></a>Siehe auch

- [Codezugriffssicherheit und ADO.NET](../code-access-security.md)
- [Übersicht über ADO.NET](../ado-net-overview.md)
