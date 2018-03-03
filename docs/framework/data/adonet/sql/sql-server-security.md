---
title: SQL Server-Sicherheit
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 9053724d-a1fb-4f0f-b9dc-7f6dd893e8ff
caps.latest.revision: 
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload:
- dotnet
ms.openlocfilehash: c186b25aeaa42b7285316d7bc9de913dd7b89af7
ms.sourcegitcommit: ba765893e3efcece67d99fd6d5ce0074b050d1d9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/02/2018
---
# <a name="sql-server-security"></a>SQL Server-Sicherheit
[!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)] besitzt viele Funktionen, die das Erstellen sicherer datenbankanwendungen unterstützt.  
  
 Allgemeine Sicherheitsfragen, wie der Schutz vor Datendiebstahl oder Vandalismus, bleiben jedoch ungeachtet der jeweils verwendeten [!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)]-Version immer aktuell. Die Datenintegrität sollte ebenfalls Bestandteil Ihrer Sicherheitsüberlegungen sein. Daten, die nicht geschützt werden, können wertlos werden, wenn Ad-hoc-Datenänderungen zugelassen sind und die Daten entweder unbeabsichtigt oder beabsichtigt durch falsche Werte ersetzt oder ganz gelöscht werden. Außerdem sind häufig gesetzliche Auflagen zu erfüllen, z. B. wenn es um die korrekte Aufbewahrung sicherheitsrelevanter Informationen geht. Je nach geltendem Recht ist das Speichern bestimmter Arten persönlicher Daten sogar ganz verboten.  
  
 Genau wie jede Windows-Version besitzt auch jede [!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)]-Version andere Sicherheitsfunktionen, wobei der Funktionsumfang in höheren Versionen dem früherer Versionen überlegen ist. Sie müssen sich aber bewusst sein, dass Sicherheitsfunktionen allein keine Garantie für eine sichere Datenbankanwendung sind. Jede Datenbankanwendung ist hinsichtlich ihrer Anforderungen, ihrer Ausführungsumgebung, ihres Bereitstellungsmodells, ihres physischen Speicherorts und ihres Benutzerkreises einzigartig. Einige Anwendungen, die nur lokal verwendet werden, benötigen vielleicht nur minimale Sicherheitsvorkehrungen, während andere lokale Anwendungen oder Anwendungen, die über das Internet bereitgestellt werden, strenge Sicherheitsmaßnahmen und eine kontinuierliche Überwachung und Auswertung erfordern.  
  
 Welche Sicherheitsanforderungen eine [!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)]-Datenbankanwendung erfüllen muss, sollte bereits in der Entwurfsphase geklärt werden. Wenn bereits zu einem frühen Zeitpunkt des Entwicklungszyklus eine Risikobewertung durchgeführt wird, können die potenziellen Auswirkungen der entdeckten Sicherheitsrisiken wirksam gemindert werden.  
  
 Selbst dann, wenn eine Anwendung zum Zeitpunkt ihrer Bereitstellung weitgehend sicher ist, können im Zuge der Weiterentwicklung des Systems neue Bedrohungen auftauchen. Bauen Sie um Ihre Datenbank mehrere Verteidigungslinien auf, um so die potenziellen Schäden infolge von Sicherheitsverletzungen so gering wie möglich zu halten. Die erste Verteidigungslinie sollte darin bestehen, die Angriffsfläche zu verringern. Gewähren Sie daher immer nur die Berechtigungen, die absolut notwendig sind.  
  
 In den Themen in diesem Abschnitt werden die für Entwickler relevanten Sicherheitsfunktionen in [!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)] kurz umrissen. Außerdem finden Sie hier Links zu entsprechenden Themen in der [!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)]-Onlinedokumentation und anderen Ressourcen mit ausführlicheren Informationen.  
  
## <a name="in-this-section"></a>In diesem Abschnitt  
 [Übersicht über die SQL Server-Sicherheit](../../../../../docs/framework/data/adonet/sql/overview-of-sql-server-security.md)  
 Beschreibt die Architektur und Sicherheitsfunktionen in [!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)].  
  
 [Anwendungssicherheitsszenarios in SQL Server](../../../../../docs/framework/data/adonet/sql/application-security-scenarios-in-sql-server.md)  
 Enthält Themen, in denen verschiedene Anwendungssicherheitsszenarien für ADO.NET- und [!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)]-Anwendungen erläutert werden.  
  
 [SQL Server Express-Sicherheit](../../../../../docs/framework/data/adonet/sql/sql-server-express-security.md)  
 Enthält Sicherheitsüberlegungen zu [!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)] Express.  
  
## <a name="related-sections"></a>Verwandte Abschnitte  
[Sicherheitscenter für SQL Server-Datenbankmodul und Azure SQL-Datenbank](/sql/relational-databases/security/security-center-for-sql-server-database-engine-and-azure-sql-database)  
Beschreibt Sicherheitsaspekte für SQL Server und Azure SQL-Datenbank.

[Überlegungen zur Sicherheit bei SQL Server-Installationen](/sql/sql-server/install/security-considerations-for-a-sql-server-installation)  
Beschreibt die Sicherheitsrisiken vor der Installation von SQL Server.

## <a name="see-also"></a>Siehe auch  
 [Sichern von ADO.NET-Anwendungen](../../../../../docs/framework/data/adonet/securing-ado-net-applications.md)  
 [SQL Server und ADO.NET](../../../../../docs/framework/data/adonet/sql/index.md)  
