---
title: "&#220;bersicht &#252;ber die SQL Server-Sicherheit | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: ae66dd75-5c16-4cc0-9e12-774dd26d3fb9
caps.latest.revision: 5
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 5
---
# &#220;bersicht &#252;ber die SQL Server-Sicherheit
Sicherheitsbedrohungen können Sie am besten mit einer tiefgestaffelten Verteidigungsstrategie mit sich überschneidenden Sicherheitsebenen begegnen.  SQL Server bietet eine Sicherheitsarchitektur, die es Datenbankadministratoren und Entwicklern erlaubt, sichere Datenbankanwendungen zu erstellen und ihre Anwendungen vor Sicherheitsrisiken zu schützen.  Jede neue SQL Server\-Version ist durch die Einführung neuer Funktionen und Funktionalität besser als die vorherige Version.  Aber Sicherheit gibt es nicht einfach ab Fabrik.  Jede Anwendung hat ihre eigenen Sicherheitsanforderungen.  Entwickler müssen ein klares Bild davon haben, welche Kombination aus Funktionen und Funktionalität sich zur Abwehr der bekannten Risiken am besten eignet, und sie müssen zukünftig auftretende Risiken vorhersehen können.  
  
 Eine SQL Server\-Instanz enthält, angefangen mit dem Server, eine hierarchisch strukturierte Sammlung von Entitäten.  Auf jedem Server befinden sich mehrere Datenbanken, und jede Datenbank enthält eine Sammlung sicherungsfähiger Objekte.  Jedem sicherungsfähigen SQL Server\-Objekt sind *Berechtigungen* zugeordnet, die einem *Prinzipal* gewährt werden können. Ein Prinzipal ist eine Einzelperson, eine Gruppe oder ein Prozess, der bzw. dem der Zugriff auf SQL Server gewährt wird.  Das SQL Server\-Sicherheitsframework verwendet zur Verwaltung des Zugriffs auf die sicherungsfähigen Entitäten *Authentifizierung* und *Autorisierung*.  
  
-   Die Authentifizierung ist der Prozess der Anmeldung bei SQL Server. Ein Prinzipal fordert dabei unter Angabe seiner Anmeldeinformationen, die vom Server ausgewertet werden, den Zugriff an.  Die Authentifizierung stellt die Identität des Benutzers oder Prozesses her, der authentifiziert wird.  
  
-   Bei der Autorisierung wird ermittelt, auf welche sicherungsfähigen Ressourcen ein Prinzipal zugreifen kann und welche Vorgänge für diese Ressourcen erlaubt sind.  
  
 Die Themen in diesem Abschnitt enthalten grundlegende Informationen zur SQL Server\-Sicherheit sowie Links zur jeweiligen vollständigen SQL Server\-Onlinedokumentation.  
  
## In diesem Abschnitt  
 [Authentifizierung in SQL Server](../../../../../docs/framework/data/adonet/sql/authentication-in-sql-server.md)  
 Beschreibt die Anmeldungen und die Authentifizierung in SQL Server und enthält Links zu weiteren Ressourcen.  
  
 [Server\- und Datenbankrollen in SQL Server](../../../../../docs/framework/data/adonet/sql/server-and-database-roles-in-sql-server.md)  
 Beschreibt feste Serverrollen und Datenbankrollen, benutzerdefinierte Datenbankrollen sowie integrierte Konten und enthält Links zu weiteren Ressourcen.  
  
 [Objektbesitz und Trennung von Benutzer und Schema in SQL Server](../../../../../docs/framework/data/adonet/sql/ownership-and-user-schema-separation-in-sql-server.md)  
 Beschreibt die Trennung von Objektbesitz und Benutzerschema und enthält Links zu weiteren Ressourcen.  
  
 [Autorisierung und Berechtigungen in SQL Server](../../../../../docs/framework/data/adonet/sql/authorization-and-permissions-in-sql-server.md)  
 Beschreibt, wie Berechtigungen nach dem Prinzip der minimalen Rechtegewährung gewährt werden können, und enthält Links zu weiteren Ressourcen.  
  
 [Datenverschlüsselung in SQL Server](../../../../../docs/framework/data/adonet/sql/data-encryption-in-sql-server.md)  
 Beschreibt die Datenverschlüsselungsoptionen in SQL Server und enthält Links zu weiteren Ressourcen.  
  
 [Sicherheit bei der CLR\-Integration in SQL Server](../../../../../docs/framework/data/adonet/sql/clr-integration-security-in-sql-server.md)  
 Enthält Links zu Ressourcen zum Thema CLR\-Integrationssicherheit.  
  
## Siehe auch  
 [Sichern von ADO.NET\-Anwendungen](../../../../../docs/framework/data/adonet/securing-ado-net-applications.md)   
 [SQL Server\-Sicherheit](../../../../../docs/framework/data/adonet/sql/sql-server-security.md)   
 [Anwendungssicherheitsszenarios in SQL Server](../../../../../docs/framework/data/adonet/sql/application-security-scenarios-in-sql-server.md)   
 [ADO.NET Verwaltete Anbieter und DataSet\-Entwicklercenter](http://go.microsoft.com/fwlink/?LinkId=217917)