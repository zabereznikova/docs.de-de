---
title: SQL Server Express-Sicherheit
ms.date: 03/30/2017
ms.assetid: cf9cf6d9-4b05-43e9-ac7b-6cefbfcd6d4e
ms.openlocfilehash: f4291de89b397f60aedd35b89d6aa3130d348be5
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59174550"
---
# <a name="sql-server-express-security"></a>SQL Server Express-Sicherheit
Microsoft SQL Server Express Edition (SQL Server Express) basiert auf Microsoft SQL Server und unterstützt die meisten Funktionen der Datenbank-Engine. Entbehrliche Funktionen und die Netzwerkkonnektivität sind standardmäßig deaktiviert. Auf diese Weise wird böswilligen Angreifern weniger Angriffsfläche geboten.  
  
 SQL Server Express wird in der Regel als benannte Instanz installiert. Der Standardname der Instanz lautet `SQLExpress`. Eine benannte Instanz wird durch den Netzwerknamen des Computers und den Instanznamen identifiziert, den Sie beim Installieren angeben.  
  
## <a name="network-access"></a>Netzwerkzugriff  
 Aus Sicherheitsgründen sind Netzwerkprotokolle in SQL Server Express standardmäßig deaktiviert. Dadurch werden Angriffe außenstehender Benutzer verhindert, die den Computer, der die SQL Server Express-Instanz hostet, gefährden könnten. Sie müssen die Netzwerkkonnektivität explizit aktivieren und den SQL Server-Browserdienst starten, um eine Verbindung mit einer SQL Server Express-Instanz auf einem anderen Computer herstellen zu können.  
  
 Nach Aktivierung der Netzwerkkonnektivität gelten für eine SQL Server Express-Instanz dieselben Sicherheitsanforderungen wie für die Instanzen anderer SQL Server-Editionen.  
  
## <a name="user-instances"></a>Benutzerinstanzen  
 Eine Benutzerinstanz ist eine separate Instanz der SQL Server Express-Datenbank-Engine, die von einer übergeordneten SQL Server Express-Instanz generiert wird. Die Hauptaufgabe einer Benutzerinstanz besteht darin, Benutzern, die Windows mit einem Konto der untersten Berechtigungsebene (LUA) ausführen, für die SQL Server Express-Instanz auf ihrem lokalen Computer Systemadministratorrechte (`sysadmin`) einzuräumen. Benutzerinstanzen sind nicht für Benutzer gedacht, die bereits Administratorberechtigungen für ihren Computer besitzen.  
  
 Benutzerinstanzen werden im Namen eines Benutzers aus einer primären SQL Server- oder SQL Server Express-Instanz generiert. Sie werden als Benutzerprozesse im Windows-Sicherheitskontext des Benutzers und nicht als Dienst ausgeführt. SQL Server-Anmeldungen sind nicht zugelassen, es werden nur Windows-Anmeldungen unterstützt. Auf diese Weise wird verhindert, dass Software, die auf einer Benutzerinstanz ausgeführt wird, systemweite Änderungen vornimmt, für die der Benutzer gar keine Berechtigung besitzt. Benutzerinstanzen werden auch als untergeordnete oder Clientinstanzen bezeichnet. Mitunter wird für deren Bezeichnung auch die Abkürzung RANU ("run as normal user") verwendet.  
  
 Jede Benutzerinstanz ist von ihrer übergeordneten Instanz und von anderen Benutzerinstanzen isoliert, die auf demselben Computer ausgeführt werden. Auf Benutzerinstanzen installierte Datenbanken werden nur im Einzelbenutzermodus geöffnet, sodass immer nur ein Benutzer mit der Datenbank verbunden sein kann. Replikation, verteilte Abfragen und Remoteverbindungen sind für Benutzerinstanzen deaktiviert. Bei Verbindung mit einer Benutzerinstanz besitzen die Benutzer keine besonderen Rechte für die übergeordnete SQL Server Express-Instanz.  
  
## <a name="external-resources"></a>Externe Ressourcen  
 Weitere Informationen zu SQL Server Express finden Sie in den folgenden Ressourcen:  
  
|||  
|-|-|  
|[Microsoft SQL Server 2005 Express Edition Books Online](https://docs.microsoft.com/previous-versions/sql/sql-server-2005/ms165706(v=sql.90))|Enthält die vollständige Dokumentation zu SQL Server 2005 Express Edition.|  
|[Benutzerinstanzen für Nichtadministratoren](https://docs.microsoft.com/previous-versions/sql/sql-server-2008/ms143684(v=sql.100)) in SQL Server-Onlinedokumentation|Beschreibt das Erstellen und Bereitstellen von Benutzerinstanzen.|  
|[SQL Server Express-Benutzerinstanzen](../../../../../docs/framework/data/adonet/sql/sql-server-express-user-instances.md)|Beschreibt Benutzerinstanzfunktionen in einer ADO.NET-Anwendung. Enthält Informationen zum Aktivieren von Benutzerinstanzen, zum Herstellen einer Verbindung mit einer Benutzerinstanz über eine <xref:System.Data.SqlClient.SqlConnection>, zur Lebensdauer von Benutzerinstanzen und zu Benutzerinstanzszenarien.|  
  
## <a name="see-also"></a>Siehe auch

- [SQL Server Security (SQL Server-Sicherheit)](../../../../../docs/framework/data/adonet/sql/sql-server-security.md)
- [SQL Server Express-Benutzerinstanzen](../../../../../docs/framework/data/adonet/sql/sql-server-express-user-instances.md)
- [ADO.NET Managed Provider und DataSet Developer Center](https://go.microsoft.com/fwlink/?LinkId=217917)
