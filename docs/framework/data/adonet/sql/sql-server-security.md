---
title: SQL Server-Sicherheit
ms.date: 03/30/2017
ms.assetid: 9053724d-a1fb-4f0f-b9dc-7f6dd893e8ff
ms.openlocfilehash: 418dbd3e677619721b841736f5b4c1b423ada94b
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33364206"
---
# <a name="sql-server-security"></a>SQL Server-Sicherheit
SQL Server besitzt viele Funktionen, die das Erstellen sicherer Datenbankanwendungen unterstützen.  
  
 Allgemeine Sicherheitsfragen, wie der Schutz vor Datendiebstahl oder Vandalismus, bleiben jedoch ungeachtet der jeweils verwendeten SQL Server-Version immer aktuell. Die Datenintegrität sollte ebenfalls Bestandteil Ihrer Sicherheitsüberlegungen sein. Daten, die nicht geschützt werden, können wertlos werden, wenn Ad-hoc-Datenänderungen zugelassen sind und die Daten entweder unbeabsichtigt oder beabsichtigt durch falsche Werte ersetzt oder ganz gelöscht werden. Außerdem sind häufig gesetzliche Auflagen zu erfüllen, z. B. wenn es um die korrekte Aufbewahrung sicherheitsrelevanter Informationen geht. Je nach geltendem Recht ist das Speichern bestimmter Arten persönlicher Daten sogar ganz verboten.  
  
 Genau wie jede Windows-Version besitzt auch jede SQL Server-Version andere Sicherheitsfunktionen, wobei der Funktionsumfang in höheren Versionen dem Funktionsumfang früherer Versionen überlegen ist. Sie müssen sich aber bewusst sein, dass Sicherheitsfunktionen allein keine Garantie für eine sichere Datenbankanwendung sind. Jede Datenbankanwendung ist hinsichtlich ihrer Anforderungen, ihrer Ausführungsumgebung, ihres Bereitstellungsmodells, ihres physischen Speicherorts und ihres Benutzerkreises einzigartig. Einige Anwendungen, die nur lokal verwendet werden, benötigen vielleicht nur minimale Sicherheitsvorkehrungen, während andere lokale Anwendungen oder Anwendungen, die über das Internet bereitgestellt werden, strenge Sicherheitsmaßnahmen und eine kontinuierliche Überwachung und Auswertung erfordern.  
  
 Welche Sicherheitsanforderungen eine SQL Server-Datenbankanwendung erfüllen muss, sollte bereits in der Entwurfsphase geklärt werden. Wenn bereits zu einem frühen Zeitpunkt des Entwicklungszyklus eine Risikobewertung durchgeführt wird, können die potenziellen Auswirkungen der entdeckten Sicherheitsrisiken wirksam gemindert werden.  
  
 Selbst dann, wenn eine Anwendung zum Zeitpunkt ihrer Bereitstellung weitgehend sicher ist, können im Zuge der Weiterentwicklung des Systems neue Bedrohungen auftauchen. Bauen Sie um Ihre Datenbank mehrere Verteidigungslinien auf, um so die potenziellen Schäden infolge von Sicherheitsverletzungen so gering wie möglich zu halten. Die erste Verteidigungslinie sollte darin bestehen, die Angriffsfläche zu verringern. Gewähren Sie daher immer nur die Berechtigungen, die absolut notwendig sind.  
  
 In den Themen in diesem Abschnitt werden die für Entwickler relevanten Sicherheitsfunktionen in SQL Server kurz umrissen. Außerdem finden Sie hier Links zu entsprechenden Themen in der SQL Server-Onlinedokumentation und in anderen Ressourcen mit ausführlicheren Informationen.  
  
## <a name="in-this-section"></a>In diesem Abschnitt  
 [Übersicht über die SQL Server-Sicherheit](../../../../../docs/framework/data/adonet/sql/overview-of-sql-server-security.md)  
 Beschreibt die Architektur und Sicherheitsfunktionen in SQL Server.  
  
 [Anwendungssicherheitsszenarios in SQL Server](../../../../../docs/framework/data/adonet/sql/application-security-scenarios-in-sql-server.md)  
 Enthält Themen, in denen verschiedene Anwendungssicherheitsszenarios für ADO.NET- und SQL Server-Anwendungen erläutert werden.  
  
 [SQL Server Express-Sicherheit](../../../../../docs/framework/data/adonet/sql/sql-server-express-security.md)  
 Beschreibt Sicherheitsaspekte für SQL Server Express.  
  
## <a name="related-sections"></a>Verwandte Abschnitte  
[Sicherheitscenter für SQL Server-Datenbankmodul und Azure SQL-Datenbank](/sql/relational-databases/security/security-center-for-sql-server-database-engine-and-azure-sql-database)  
Beschreibt Sicherheitsaspekte für SQL Server und Azure SQL-Datenbank.

[Überlegungen zur Sicherheit bei SQL Server-Installationen](/sql/sql-server/install/security-considerations-for-a-sql-server-installation)  
Beschreibt die Sicherheitsrisiken vor der Installation von SQL Server.

## <a name="see-also"></a>Siehe auch  
 [Sichern von ADO.NET-Anwendungen](../../../../../docs/framework/data/adonet/securing-ado-net-applications.md)  
 [SQL Server und ADO.NET](../../../../../docs/framework/data/adonet/sql/index.md)  
