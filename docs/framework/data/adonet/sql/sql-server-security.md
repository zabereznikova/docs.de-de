---
title: SQL Server-Sicherheit
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 9053724d-a1fb-4f0f-b9dc-7f6dd893e8ff
caps.latest.revision: "8"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: dotnet
ms.openlocfilehash: 4b8eafeedd03097488b1493b5654db360eab94fb
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="sql-server-security"></a>SQL Server-Sicherheit
[!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)] besitzt viele Funktionen, die das Erstellen sicherer Datenbankanwendungen unterstützen.  
  
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
 [Sicherheit und Schutz (Datenbankmodul)](http://msdn2.microsoft.com/library/bb510589\(SQL.100\).aspx.)  
 Sicherheitsthemen in der [!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)]-Onlinedokumentation.  
  
 [Überlegungen zur Sicherheit bei SQLServer](http://go.microsoft.com/fwlink/?LinkId=98587)  
 Sicherheitsthemen in der [!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)]-Onlinedokumentation.  
  
## <a name="see-also"></a>Siehe auch  
 [Sichern von ADO.NET-Anwendungen](../../../../../docs/framework/data/adonet/securing-ado-net-applications.md)  
 [SQL Server und ADO.NET](../../../../../docs/framework/data/adonet/sql/index.md)  
 [ADO.NET Managed Provider und DataSet Developer Center](http://go.microsoft.com/fwlink/?LinkId=217917)
