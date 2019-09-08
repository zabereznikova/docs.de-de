---
title: Übersicht über die SQL Server-Sicherheit
ms.date: 03/30/2017
ms.assetid: ae66dd75-5c16-4cc0-9e12-774dd26d3fb9
ms.openlocfilehash: adc1ce661d49c468de09552ea36a2cd58d6343f1
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/07/2019
ms.locfileid: "70780936"
---
# <a name="overview-of-sql-server-security"></a>Übersicht über die SQL Server-Sicherheit
Sicherheitsbedrohungen können Sie am besten mit einer tiefgestaffelten Verteidigungsstrategie mit sich überschneidenden Sicherheitsebenen begegnen. SQL Server bietet eine Sicherheitsarchitektur, die es Datenbankadministratoren und Entwicklern erlaubt, sichere Datenbankanwendungen zu erstellen und ihre Anwendungen vor Sicherheitsrisiken zu schützen. Jede neue SQL Server-Version ist durch die Einführung neuer Funktionen und Funktionalität besser als die vorherige Version. Aber Sicherheit gibt es nicht einfach ab Fabrik. Jede Anwendung hat ihre eigenen Sicherheitsanforderungen. Entwickler müssen ein klares Bild davon haben, welche Kombination aus Funktionen und Funktionalität sich zur Abwehr der bekannten Risiken am besten eignet, und sie müssen zukünftig auftretende Risiken vorhersehen können.  
  
 Eine SQL Server-Instanz enthält, angefangen mit dem Server, eine hierarchisch strukturierte Sammlung von Entitäten. Auf jedem Server befinden sich mehrere Datenbanken, und jede Datenbank enthält eine Sammlung sicherungsfähiger Objekte. Jedes SQL Server Sicherungs fähigen Element verfügt über zugeordnete *Berechtigungen* , die einem *Prinzipal*erteilt werden können. dabei handelt es sich um eine Einzelperson, Gruppe oder Prozess, die Zugriff auf SQL Server gewährt. Das SQL Server-Sicherheits Framework verwaltet den Zugriff auf Sicherungs fähige Entitäten durch *Authentifizierung* und *Autorisierung*.  
  
- Die Authentifizierung ist der Prozess der Anmeldung bei SQL Server. Ein Prinzipal fordert dabei unter Angabe seiner Anmeldeinformationen, die vom Server ausgewertet werden, den Zugriff an. Die Authentifizierung stellt die Identität des Benutzers oder Prozesses her, der authentifiziert wird.  
  
- Bei der Autorisierung wird ermittelt, auf welche sicherungsfähigen Ressourcen ein Prinzipal zugreifen kann und welche Vorgänge für diese Ressourcen erlaubt sind.  
  
 Die Themen in diesem Abschnitt enthalten grundlegende Informationen zur SQL Server-Sicherheit sowie Links zur jeweiligen vollständigen SQL Server-Onlinedokumentation.  
  
## <a name="in-this-section"></a>In diesem Abschnitt  
 [Authentifizierung in SQL Server](authentication-in-sql-server.md)  
 Beschreibt die Anmeldungen und die Authentifizierung in SQL Server und enthält Links zu weiteren Ressourcen.  
  
 [Server- und Datenbankrollen in SQL Server](server-and-database-roles-in-sql-server.md)  
 Beschreibt feste Serverrollen und Datenbankrollen, benutzerdefinierte Datenbankrollen sowie integrierte Konten und enthält Links zu weiteren Ressourcen.  
  
 [Objektbesitz und Trennung von Benutzer und Schema in SQL Server](ownership-and-user-schema-separation-in-sql-server.md)  
 Beschreibt die Trennung von Objektbesitz und Benutzerschema und enthält Links zu weiteren Ressourcen.  
  
 [Autorisierung und Berechtigungen in SQL Server](authorization-and-permissions-in-sql-server.md)  
 Beschreibt, wie Berechtigungen nach dem Prinzip der minimalen Rechtegewährung gewährt werden können, und enthält Links zu weiteren Ressourcen.  
  
 [Datenverschlüsselung in SQL Server](data-encryption-in-sql-server.md)  
 Beschreibt die Datenverschlüsselungsoptionen in SQL Server und enthält Links zu weiteren Ressourcen.  
  
 [CLR-Integrationssicherheit in SQL Server](clr-integration-security-in-sql-server.md)  
 Enthält Links zu Ressourcen zum Thema CLR-Integrationssicherheit.  
  
## <a name="see-also"></a>Siehe auch

- [Sichern von ADO.NET-Anwendungen](../securing-ado-net-applications.md)
- [SQL Server Security (SQL Server-Sicherheit)](sql-server-security.md)
- [Anwendungssicherheitsszenarios in SQL Server](application-security-scenarios-in-sql-server.md)
- [Übersicht über ADO.NET](../ado-net-overview.md)
