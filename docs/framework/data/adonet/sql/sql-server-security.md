---
title: SQL Server-Sicherheit
ms.date: 03/30/2017
ms.assetid: 9053724d-a1fb-4f0f-b9dc-7f6dd893e8ff
ms.openlocfilehash: 5db14e681b5a9445c034be60993661a61a038e08
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91177305"
---
# <a name="sql-server-security"></a>SQL Server-Sicherheit

SQL Server besitzt viele Funktionen, die das Erstellen sicherer Datenbankanwendungen unterstützen.  
  
 Allgemeine Sicherheitsfragen, wie der Schutz vor Datendiebstahl oder Vandalismus, bleiben jedoch ungeachtet der jeweils verwendeten SQL Server-Version immer aktuell. Datenintegrität muss auch als Sicherheitsaspekt berücksichtigt werden. Wenn Daten nicht geschützt sind, können sie möglicherweise wertlos werden, sobald eine Ad-hoc-Manipulation von Daten erlaubt ist und die Daten versehentlich oder böswillig mit falschen Werten versehen oder ganz gelöscht werden. Darüber hinaus gibt es häufig gesetzliche Bestimmungen, die eingehalten werden müssen, wie z. B. die ordnungsgemäße Speicherung vertraulicher Informationen. Die Speicherung einiger Arten personenbezogener Daten ist je nach den in einem bestimmten Rechtsraum geltenden Gesetzen gänzlich verboten.  
  
 Genau wie jede Windows-Version besitzt auch jede SQL Server-Version andere Sicherheitsfunktionen, wobei der Funktionsumfang in höheren Versionen dem früherer Versionen überlegen ist. Wichtig ist zu verstehen, dass Sicherheitsvorkehrungen allein keine sichere Datenbankanwendung garantieren können. Jede Datenbankanwendung ist hinsichtlich ihrer Anforderungen, der Ausführungsumgebung, des Bereitstellungsmodells, des physischen Standorts und der Benutzergruppe einzigartig. Einige Anwendungen, die lokal begrenzt sind, benötigen nur minimale Sicherheit, während andere lokale Anwendungen oder Anwendungen, die über das Internet bereitgestellt werden, möglicherweise strenge Sicherheitsvorkehrungen und eine ständige Überwachung und Einschätzung erfordern.  
  
 Welche Sicherheitsanforderungen eine SQL Server-Datenbankanwendung erfüllen muss, sollte bereits in der Entwurfsphase geklärt werden. Die Einschätzung von Bedrohungen in einem frühen Stadium des Entwicklungszyklus gibt Ihnen die Möglichkeit, potenzielle Schäden einzudämmen, wo auch immer ein Sicherheitsrisiko entdeckt wird.  
  
 Selbst wenn der anfängliche Entwurf einer Anwendung einwandfrei ist, können bei der Weiterentwicklung des Systems neue Bedrohungen auftauchen. Durch die Schaffung mehrerer Verteidigungslinien rund um Ihre Datenbank können Sie den durch eine Sicherheitsverletzung verursachten Schaden minimieren. Ihre erste Verteidigungslinie besteht darin, die Angriffsfläche zu reduzieren, indem Sie auf keinen Fall mehr Berechtigungen als unbedingt notwendig erteilen.  
  
 In den Themen in diesem Abschnitt werden die für Entwickler relevanten Sicherheitsfunktionen in SQL Server kurz umrissen. Außerdem finden Sie hier Links zu entsprechenden Themen in der SQL Server-Onlinedokumentation und anderen Ressourcen mit ausführlicheren Informationen.  
  
## <a name="in-this-section"></a>In diesem Abschnitt  

 [Übersicht über die SQL Server-Sicherheit](overview-of-sql-server-security.md)  
 Beschreibt die Architektur und Sicherheitsfunktionen in SQL Server.  
  
 [Anwendungssicherheitsszenarios in SQL Server](application-security-scenarios-in-sql-server.md)  
 Enthält Themen, in denen verschiedene Anwendungssicherheitsszenarien für ADO.NET- und SQL Server-Anwendungen erläutert werden.  
  
 [SQL Server Express Sicherheit](sql-server-express-security.md)  
 Beschreibt Sicherheitsüberlegungen für SQL Server Express.  
  
## <a name="related-sections"></a>Verwandte Abschnitte  

[Sicherheitscenter für SQL Server-Datenbank-Engine und Azure SQL-Datenbank](/sql/relational-databases/security/security-center-for-sql-server-database-engine-and-azure-sql-database)  
Beschreibt Sicherheitsüberlegungen für SQL Server und Azure SQL-Datenbank.

[Überlegungen zur Sicherheit bei SQL Server-Installationen](/sql/sql-server/install/security-considerations-for-a-sql-server-installation)  
Erörtert Sicherheitsbedenken, die vor der Installation von SQL Server zu berücksichtigen sind.

## <a name="see-also"></a>Weitere Informationen

- [Sichern von ADO.NET-Anwendungen](../securing-ado-net-applications.md)
- [SQL Server und ADO.NET](index.md)
