---
title: SQL Server Express-Sicherheit
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: cf9cf6d9-4b05-43e9-ac7b-6cefbfcd6d4e
caps.latest.revision: "6"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: 6593e075d1a9d672f414cfa0cd8652f760b084e1
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/17/2018
---
# <a name="sql-server-express-security"></a>SQL Server Express-Sicherheit
Microsoft SQL Server Express Edition (SQL Server Express) basiert auf Microsoft SQL Server und unterstützt die meisten Funktionen des Datenbankmoduls. Entbehrliche Funktionen und die Netzwerkkonnektivität sind standardmäßig deaktiviert. Auf diese Weise wird böswilligen Angreifern weniger Angriffsfläche geboten.  
  
 SQL Server Express wird in der Regel als benannte Instanz installiert. Der Standardname der Instanz lautet `SQLExpress`. Eine benannte Instanz wird durch den Netzwerknamen des Computers und den Instanznamen identifiziert, den Sie beim Installieren angeben.  
  
## <a name="network-access"></a>Netzwerkzugriff  
 Aus Sicherheitsgründen sind Netzwerkprotokolle in SQL Server Express standardmäßig deaktiviert. Dadurch werden Angriffe außenstehender Benutzer verhindert, die den Computer, der die SQL Server Express-Instanz hostet, gefährden könnten. Sie müssen die Netzwerkkonnektivität explizit aktivieren und den SQL Server-Browserdienst starten, um eine Verbindung mit einer SQL Server Express-Instanz auf einem anderen Computer herstellen zu können.  
  
 Nach Aktivierung der Netzwerkkonnektivität gelten für eine SQL Server Express-Instanz dieselben Sicherheitsanforderungen wie für die Instanzen anderer SQL Server-Editionen.  
  
## <a name="user-instances"></a>Benutzerinstanzen  
 Eine Benutzerinstanz ist eine separate Instanz des SQL Server Express-Datenbankmoduls, die von einer übergeordneten SQL Server Express-Instanz generiert wird. Die Hauptaufgabe einer Benutzerinstanz besteht darin, Benutzern, die Windows mit einem Konto der untersten Berechtigungsebene (LUA) ausführen, für die SQL Server Express-Instanz auf ihrem lokalen Computer Systemadministratorrechte (`sysadmin`) einzuräumen. Benutzerinstanzen sind nicht für Benutzer gedacht, die bereits Administratorberechtigungen für ihren Computer besitzen.  
  
 Benutzerinstanzen werden im Namen eines Benutzers aus einer primären SQL Server- oder SQL Server Express-Instanz generiert. Sie werden als Benutzerprozesse im Windows-Sicherheitskontext des Benutzers und nicht als Dienst ausgeführt. SQL Server-Anmeldungen sind nicht zugelassen, es werden nur Windows-Anmeldungen unterstützt. Auf diese Weise wird verhindert, dass Software, die auf einer Benutzerinstanz ausgeführt wird, systemweite Änderungen vornimmt, für die der Benutzer gar keine Berechtigung besitzt. Benutzerinstanzen werden auch als untergeordnete oder Clientinstanzen bezeichnet. Mitunter wird für deren Bezeichnung auch die Abkürzung RANU ("run as normal user") verwendet.  
  
 Jede Benutzerinstanz ist von ihrer übergeordneten Instanz und von anderen Benutzerinstanzen isoliert, die auf demselben Computer ausgeführt werden. Auf Benutzerinstanzen installierte Datenbanken werden nur im Einzelbenutzermodus geöffnet, sodass immer nur ein Benutzer mit der Datenbank verbunden sein kann. Replikation, verteilte Abfragen und Remoteverbindungen sind für Benutzerinstanzen deaktiviert. Bei Verbindung mit einer Benutzerinstanz besitzen die Benutzer keine besonderen Rechte für die übergeordnete SQL Server Express-Instanz.  
  
## <a name="external-resources"></a>Externe Ressourcen  
 Weitere Informationen zu SQL Server Express finden Sie in den folgenden Ressourcen:  
  
|||  
|-|-|  
|[SQL Server Books Online (SQL Server-Onlinedokumentation)](http://msdn.microsoft.com/library/bb543165.aspx)|Enthält die Dokumentation für SQL Server Express.|  
|[Herstellen einer Verbindung mit SQL Server Express](http://msdn.microsoft.com/library/ms165679.aspx) in SQL Server-Onlinedokumentation|Beschreibt die Verwendung von SQL Server Express Edition in einem Netzwerk.|  
|[Microsoft SQL Server 2005 Express Edition Books Online](http://msdn.microsoft.com/library/ms165706.aspx)|Enthält die vollständige Dokumentation zu SQL Server 2005 Express Edition.|  
|[Benutzerinstanzen für Nichtadministratoren](http://msdn.microsoft.com/library/ms143684.aspx) in SQL Server-Onlinedokumentation|Beschreibt das Erstellen und Bereitstellen von Benutzerinstanzen.|  
|[SQL Server Express-Benutzerinstanzen](../../../../../docs/framework/data/adonet/sql/sql-server-express-user-instances.md)|Beschreibt Benutzerinstanzfunktionen in einer ADO.NET-Anwendung. Enthält Informationen zum Aktivieren von Benutzerinstanzen, zum Herstellen einer Verbindung mit einer Benutzerinstanz über eine <xref:System.Data.SqlClient.SqlConnection>, zur Lebensdauer von Benutzerinstanzen und zu Benutzerinstanzszenarien.|  
  
## <a name="see-also"></a>Siehe auch  
 [SQL Server Security (SQL Server-Sicherheit)](../../../../../docs/framework/data/adonet/sql/sql-server-security.md)  
 [SQL Server Express-Benutzerinstanzen](../../../../../docs/framework/data/adonet/sql/sql-server-express-user-instances.md)  
 [ADO.NET Managed Provider und DataSet Developer Center](http://go.microsoft.com/fwlink/?LinkId=217917)
