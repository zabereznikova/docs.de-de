---
title: Leitfaden zur Migration
ms.date: 03/30/2017
ms.assetid: cb65c132-58c9-4028-b3d4-1efc71d5e60e
ms.openlocfilehash: f0c21d32b745a51bada9133230dd0c87be9c915e
ms.sourcegitcommit: 7e2128d4a4c45b4274bea3b8e5760d4694569ca1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/14/2020
ms.locfileid: "75937967"
---
# <a name="migration-guidance"></a>Leitfaden zur Migration

In der .NET Framework 4 veröffentlicht Microsoft die zweite Hauptversion von Windows Workflow Foundation (WF). [!INCLUDE[wf1](../../../includes/wf1-md.md)] wurde in WinFX veröffentlicht (dies enthielt die Typen in den System. Workflow.\*-Namespaces, die jetzt als WF3 bezeichnet werden) und wurde in .NET Framework 3,5 erweitert. WF3 ist auch Bestandteil des .NET Framework 4, aber es besteht neben neuer Workflow Technologie (die Typen in den System. Activities.\*-Namespaces, die als WF4 bezeichnet werden). Beim Erwägen des Zeitpunkts für die Umstellung auf WF4 sollten Sie zuerst bedenken, dass Sie allein den zeitlichen Ablauf steuern können.  
  
- WF3 ist ein vollständig unterstützter Teil der .NET Framework 4.  
  
- WF3-Anwendungen können ohne Änderung auf dem .NET Framework 4 ausgeführt werden und werden weiterhin vollständig unterstützt.  
  
- Neue WF3-Anwendungen können erstellt werden, und vorhandene Anwendungen können in Visual Studio 2012 bearbeitet werden und werden vollständig unterstützt.  
  
 Daher ist die Entscheidung, die .NET Framework 4 zu übernehmen, von ihrer Entscheidung getrennt, zu WF4 (System. Activities.\*) von WF3 (System. Workflow.\*) zu wechseln. Dieses Thema enthält Links zu WF-Migrationsanleitungen mit Informationen zum Arbeiten mit WF3 und WF4.  
  
## <a name="wf-migration-white-papers-and-cookbooks"></a>Whitepaper und Cookbooks für die WF-Migration

 Das Thema Übersicht über die [WF-Migration](https://docs.microsoft.com/previous-versions/appfabric/ff383417(v=azure.10)) bietet eine umfassende Übersicht über die Beziehung zwischen WF3 und WF4 und Migrationsstrategien. Speziellere Themenbereiche werden in Begleitthemen behandelt.  
  
 [Übersicht der WF-Migration](https://docs.microsoft.com/previous-versions/appfabric/ff383417(v=azure.10))  
 Beschreibt die Beziehung zwischen WF3 und WF4 sowie die Optionen, die Sie als Benutzer oder potenzieller Benutzer der Workflowtechnologie unter .NET 4 haben.  
  
 [WF-Migration: bewährte Methoden für die WF3-Entwicklung](https://docs.microsoft.com/previous-versions/appfabric/ff383417(v=azure.10))  
 Beschreibt, wie Sie WF3-Artefakte so entwerfen, dass diese einfacher nach WF4 migriert werden können.  
  
 [WF-Anleitung: Regeln](https://docs.microsoft.com/previous-versions/appfabric/ff383417(v=azure.10))  
 Erläutert, wie Sie Regel bezogene Investitionen in .NET Framework 4-Lösungen einbringen können.  
  
 [WF-Leitfaden: Zustands Automat](https://docs.microsoft.com/previous-versions/appfabric/ff383417(v=azure.10))  
 Erläutert die WF4-Ablaufsteuerungsmodellierung bei Nichtvorhandensein einer Zustandsautomataktivität (State Machine).  
  
 Beachten Sie, dass diese Anleitung nur für Workflowprojekte gilt, die .NET Framework 4 als Zielframework verwenden. Zustandsautomatworkflows wurden in .NET 4.0.1 mit dem Plattform Update 1 hinzugefügt und in .NET Framework 4.5 beibehalten. Weitere Informationen zu Zustandsautomatworkflows in .NET 4.0.1-4.0.3 und .NET Framework 4,5 finden Sie unter [Update 4.0.1 for Microsoft .NET Framework 4 Features](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/hh290669(v=vs.100)) und [State Machine Workflows](state-machine-workflows.md).  
  
 [Cookbook zur WF-Migration: benutzerdefinierte Aktivitäten](https://docs.microsoft.com/previous-versions/appfabric/ff383417(v=azure.10))  
 Enthält Beispiele und Anweisungen zum Umgestalten von benutzerdefinierten WF3-Aktivitäten unter WF4.  
  
 [Cookbook zur WF-Migration: Erweiterte benutzerdefinierte Aktivitäten](https://docs.microsoft.com/previous-versions/appfabric/ff383417(v=azure.10))  
 Stellt eine Anleitung zur Neuentwicklung erweiterter benutzerdefinierter WF3-Aktivitäten bereit, die WF3-Warteschlangen verwenden und untergeordnete Aktivitäten als benutzerdefinierte WF4-Aktivitäten planen.  
  
 [Cookbook zur WF-Migration: Workflows](https://docs.microsoft.com/previous-versions/appfabric/ff383417(v=azure.10))  
 Enthält Beispiele und Anleitungen zum Umgestalten von WF3-Workflows unter WF4.  
  
 [Cookbook zur WF-Migration: Workflow Hosting](https://docs.microsoft.com/previous-versions/appfabric/ff383417(v=azure.10))  
 Stellt eine Anleitung zur Umgestaltung des WF3-Hostingcodes als WF4-Hostingcode bereit. Damit sollen die wesentlichen Unterschiede beim Workflowhosting zwischen WF3 und WF4 veranschaulicht werden.  
  
 [Cookbook zur WF-Migration: Workflow Nachverfolgung](https://docs.microsoft.com/previous-versions/appfabric/ff383417(v=azure.10))  
 Bietet Hilfestellung bei der Umgestaltung von WF3-Nachverfolgungscode und -Konfiguration mithilfe eines äquivalenten Nachverfolgungscodes und einer äquivalenten Konfiguration auf der Basis von WF4.  
  
 [WF-Anleitung: Workflow Dienste](https://docs.microsoft.com/previous-versions/appfabric/ff383417(v=azure.10))  
 Stellt anhand eines Beispiels schrittweise Anweisungen zur Neuentwicklung von Workflows bereit, die in WF3 erstellte Windows Communication Foundation (WCF)-Webdienste (auch als Workflowdienste bezeichnet) für die Verwendung allgemeiner, vordefinierter Aktivitäten in WF4 implementieren.  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Activities.Statements.Interop>
