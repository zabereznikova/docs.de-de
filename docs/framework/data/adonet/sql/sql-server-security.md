---
title: SQL Server-Sicherheit
ms.date: 03/30/2017
ms.assetid: 9053724d-a1fb-4f0f-b9dc-7f6dd893e8ff
ms.openlocfilehash: c5fd9cc82a3b1e4ffa217d65c542376fe067db06
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/07/2019
ms.locfileid: "70791623"
---
# <a name="sql-server-security"></a>SQL Server-Sicherheit
SQL Server besitzt viele Funktionen, die das Erstellen sicherer Datenbankanwendungen unterstützen.  
  
 Allgemeine Sicherheitsfragen, wie der Schutz vor Datendiebstahl oder Vandalismus, bleiben jedoch ungeachtet der jeweils verwendeten SQL Server-Version immer aktuell. Die Datenintegrität sollte ebenfalls Bestandteil Ihrer Sicherheitsüberlegungen sein. Daten, die nicht geschützt werden, können wertlos werden, wenn Ad-hoc-Datenänderungen zugelassen sind und die Daten entweder unbeabsichtigt oder beabsichtigt durch falsche Werte ersetzt oder ganz gelöscht werden. Außerdem sind häufig gesetzliche Auflagen zu erfüllen, z. B. wenn es um die korrekte Aufbewahrung sicherheitsrelevanter Informationen geht. Je nach geltendem Recht ist das Speichern bestimmter Arten persönlicher Daten sogar ganz verboten.  
  
 Genau wie jede Windows-Version besitzt auch jede SQL Server-Version andere Sicherheitsfunktionen, wobei der Funktionsumfang in höheren Versionen dem Funktionsumfang früherer Versionen überlegen ist. Sie müssen sich aber bewusst sein, dass Sicherheitsfunktionen allein keine Garantie für eine sichere Datenbankanwendung sind. Jede Datenbankanwendung ist hinsichtlich ihrer Anforderungen, ihrer Ausführungsumgebung, ihres Bereitstellungsmodells, ihres physischen Speicherorts und ihres Benutzerkreises einzigartig. Einige Anwendungen, die nur lokal verwendet werden, benötigen vielleicht nur minimale Sicherheitsvorkehrungen, während andere lokale Anwendungen oder Anwendungen, die über das Internet bereitgestellt werden, strenge Sicherheitsmaßnahmen und eine kontinuierliche Überwachung und Auswertung erfordern.  
  
 Welche Sicherheitsanforderungen eine SQL Server-Datenbankanwendung erfüllen muss, sollte bereits in der Entwurfsphase geklärt werden. Wenn bereits zu einem frühen Zeitpunkt des Entwicklungszyklus eine Risikobewertung durchgeführt wird, können die potenziellen Auswirkungen der entdeckten Sicherheitsrisiken wirksam gemindert werden.  
  
 Selbst dann, wenn eine Anwendung zum Zeitpunkt ihrer Bereitstellung weitgehend sicher ist, können im Zuge der Weiterentwicklung des Systems neue Bedrohungen auftauchen. Bauen Sie um Ihre Datenbank mehrere Verteidigungslinien auf, um so die potenziellen Schäden infolge von Sicherheitsverletzungen so gering wie möglich zu halten. Die erste Verteidigungslinie sollte darin bestehen, die Angriffsfläche zu verringern. Gewähren Sie daher immer nur die Berechtigungen, die absolut notwendig sind.  
  
 In den Themen in diesem Abschnitt werden die für Entwickler relevanten Sicherheitsfunktionen in SQL Server kurz umrissen. Außerdem finden Sie hier Links zu entsprechenden Themen in der SQL Server-Onlinedokumentation und in anderen Ressourcen mit ausführlicheren Informationen.  
  
## <a name="in-this-section"></a>In diesem Abschnitt  
 [Übersicht über die SQL Server-Sicherheit](overview-of-sql-server-security.md)  
 Beschreibt die Architektur und Sicherheitsfunktionen in SQL Server.  
  
 [Anwendungssicherheitsszenarios in SQL Server](application-security-scenarios-in-sql-server.md)  
 Enthält Themen, in denen verschiedene Anwendungssicherheitsszenarios für ADO.NET- und SQL Server-Anwendungen erläutert werden.  
  
 [SQL Server Express-Sicherheit](sql-server-express-security.md)  
 Beschreibt Sicherheitsüberlegungen für SQL Server Express.  
  
## <a name="related-sections"></a>Verwandte Abschnitte  
[Sicherheitscenter für SQL Server-Datenbank-Engine und Azure SQL-Datenbank](/sql/relational-databases/security/security-center-for-sql-server-database-engine-and-azure-sql-database)  
Beschreibt Sicherheitsüberlegungen für SQL Server und Azure SQL-Datenbank.

[Sicherheitsüberlegungen für eine SQL Server Installation](/sql/sql-server/install/security-considerations-for-a-sql-server-installation)  
Beschreibt Sicherheitsbedenken, die vor der Installation von SQL Server zu berücksichtigen sind.

## <a name="see-also"></a>Siehe auch

- [Sichern von ADO.NET-Anwendungen](../securing-ado-net-applications.md)
- [SQL Server und ADO.NET](index.md)
