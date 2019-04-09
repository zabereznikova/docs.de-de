---
title: Sichern von ADO.NET-Anwendungen
ms.date: 03/30/2017
ms.assetid: 005a1d43-6ee5-471e-ad98-1d30a44d49d5
ms.openlocfilehash: 32d3de15242aaf9cfacd9371289a5a0a675f884b
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59149382"
---
# <a name="securing-adonet-applications"></a>Sichern von ADO.NET-Anwendungen
Beim Schreiben von sicheren ADO.NET-Anwendungen gilt es nicht nur, häufige Fallstricke bei der Codierung zu umgehen, wie die Nichtvalidierung von Benutzereingaben. Eine Anwendung, die auf Daten zugreift, verfügt über viele mögliche Schwachstellen, über die ein Hacker vertrauliche Daten abrufen, manipulieren oder vernichten kann. Es ist daher unerlässlich, alle Sicherheitsaspekte zu verstehen, und zwar beginnend bei der Erstellung von Gefahrenmodellen während des Anwendungsentwurfs bis hin zur eigentlichen Bereitstellung der Anwendung und ihrem laufenden Betrieb.  
  
 .NET Framework bietet eine Reihe nützlicher Klassen, Dienste und Tools zum Sichern und Verwalten von Datenbankanwendungen. Die Common Language Runtime (CLR) bietet eine typsichere Umgebung für die Ausführung von Code mit Codezugriffssicherheit (Code Access Security, CAS), um die Berechtigungen für verwalteten Code weiter einzuschränken. Die Beachtung von Codierungspraktiken für einen sicheren Datenzugriff hilft, den Schaden zu begrenzen, den ein potenzieller Angreifer verursachen kann.  
  
 Das Schreiben von sicherem Code schützt jedoch nicht vor selbst zu verantwortenden Sicherheitslücken beim Arbeiten mit nicht verwalteten Ressourcen, wie Datenbanken. Die meisten Serverdatenbanken, wie SQL Server, verfügen über eigene Sicherheitssysteme, die bei korrekter Implementierung für mehr Sicherheit sorgen. Aber auch Datenquellen mit einem robusten Sicherheitssystem können zum Angriffsopfer werden, wenn sie nicht ordnungsgemäß konfiguriert werden.  
  
## <a name="in-this-section"></a>In diesem Abschnitt  
 [Übersicht über die Sicherheit](../../../../docs/framework/data/adonet/security-overview.md)  
 Enthält Empfehlungen für das Entwerfen sicherer ADO.NET-Anwendungen.  
  
 [Sicherer Datenzugriff](../../../../docs/framework/data/adonet/secure-data-access.md)  
 Beschreibt das Arbeiten mit Daten aus einer gesicherten Datenquelle.  
  
 [Sichere Clientanwendungen](../../../../docs/framework/data/adonet/secure-client-applications.md)  
 Enthält Überlegungen zum Thema Sicherheit für Clientanwendungen.  
  
 [Codezugriffssicherheit und ADO.NET](../../../../docs/framework/data/adonet/code-access-security.md)  
 Beschreibt, wie CAS zum Schutz von ADO.NET-Code beitragen kann. Erläutert außerdem das Arbeiten mit teilweiser Vertrauenswürdigkeit.  
  
 [Datenschutz und -sicherheit](../../../../docs/framework/data/adonet/privacy-and-data-security.md)  
 Beschreibt Verschlüsselungsmöglichkeiten für ADO.NET-Anwendungen.  
  
## <a name="related-sections"></a>Verwandte Abschnitte  
 [SQL Server-Sicherheit](../../../../docs/framework/data/adonet/sql/sql-server-security.md)  
 Beschreibt SQL Server-Sicherheitsfunktionen aus Entwicklersicht.  
  
 [Sicherheitsüberlegungen](../../../../docs/framework/data/adonet/ef/security-considerations.md)  
 Beschreibt Sicherheitsfunktionen für Entity Framework-Anwendungen.  
  
 [Sicherheit](../../../../docs/standard/security/index.md)  
 Enthält Links zu Themen, in denen alle Aspekte der Sicherheit in .NET beschrieben werden.  
  
 [Sicherheitstools](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2008/7w3fd0wb(v=vs.90))  
 .NET Framework-Tools zum Sichern und Verwalten von Sicherheitsrichtlinien.  
  
 [Ressourcen für das Erstellen sicherer Anwendungen](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/ms165101(v=vs.100))  
 Enthält Links zu Themen zum Erstellen sicherer Anwendungen.  
  
 [Sicherheitsbibliographie](/visualstudio/ide/security-bibliography)  
 Enthält Links zu externen Ressourcen, die online und in Druckversion verfügbar sind.  
  
## <a name="see-also"></a>Siehe auch

- [ADO.NET](../../../../docs/framework/data/adonet/index.md)
- [ADO.NET Managed Provider und DataSet Developer Center](https://go.microsoft.com/fwlink/?LinkId=217917)
