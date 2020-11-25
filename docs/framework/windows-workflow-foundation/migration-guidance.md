---
title: Migrationsanleitung
ms.date: 03/30/2017
ms.assetid: cb65c132-58c9-4028-b3d4-1efc71d5e60e
ms.openlocfilehash: b9b90aedc06fb4a4564596d61aa0ac2dc4c6143f
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95733593"
---
# <a name="migration-guidance"></a>Migrationsanleitung

In der .NET Framework 4 veröffentlicht Microsoft die zweite Hauptversion von Windows Workflow Foundation (WF). [!INCLUDE[wf1](../../../includes/wf1-md.md)] wurde in WinFX veröffentlicht (dies enthielt die Typen in System. Workflow. \* Namespaces, die jetzt als WF3 bezeichnet werden) und wurde in .NET Framework 3,5 erweitert. WF3 ist auch Teil des .NET Framework 4, aber es ist dort neben neuer Workflow Technologie vorhanden (die Typen in System. Activities. \* Namespaces, die als WF4 bezeichnet werden). Beim Erwägen des Zeitpunkts für die Umstellung auf WF4 sollten Sie zuerst bedenken, dass Sie allein den zeitlichen Ablauf steuern können.

- WF3 ist ein vollständig unterstützter Teil der .NET Framework 4.

- WF3-Anwendungen können ohne Änderung auf dem .NET Framework 4 ausgeführt werden und werden weiterhin vollständig unterstützt.

- Neue WF3-Anwendungen können erstellt werden, und vorhandene Anwendungen können in Visual Studio 2012 bearbeitet werden und werden vollständig unterstützt.

 Daher ist die Entscheidung, die .NET Framework 4 zu übernehmen, von ihrer Entscheidung, zu WF4 (System. Activities. \* ) von WF3 (System. Workflow.) zu wechseln, entkoppelt. \* Dieses Thema enthält Links zu WF-Migrationsanleitungen mit Informationen zum Arbeiten mit WF3 und WF4.

## <a name="wf-migration-white-papers-and-cookbooks"></a>Whitepaper und Cookbooks für die WF-Migration

 Das Thema Übersicht über die [WF-Migration](/previous-versions/appfabric/ff383417(v=azure.10)) bietet eine umfassende Übersicht über die Beziehung zwischen WF3 und WF4 und Migrationsstrategien. Speziellere Themenbereiche werden in Begleitthemen behandelt.

 [Übersicht der WF-Migration](/previous-versions/appfabric/ff383417(v=azure.10)) Beschreibt die Beziehung zwischen WF3 und WF4 und den Optionen, die Sie als Benutzer oder einen potenziellen Benutzer der Workflow Technologie in .NET Framework 4 haben.

 [WF-Migration: bewährte Methoden für die WF3-Entwicklung](/previous-versions/appfabric/ff383417(v=azure.10)) Erläutert, wie WF3-Artefakte entworfen werden, damit Sie leichter zu WF4 migriert werden können.

 [WF-Anleitung: Regeln](/previous-versions/appfabric/ff383417(v=azure.10)) Erläutert, wie Sie Regel bezogene Investitionen in .NET Framework 4-Lösungen einbringen können.

 [WF-Leitfaden: Zustands Automat](/previous-versions/appfabric/ff383417(v=azure.10)) Erläutert die WF4-Ablauf Steuerungs Modellierung, wenn keine State-Machine-Aktivität vorhanden ist.

 Beachten Sie, dass diese Anleitung nur für Workflowprojekte gilt, die .NET Framework 4 als Zielframework verwenden. Zustandsautomatworkflows wurden in .NET Framework 4.0.1 mit der Veröffentlichung von Platform Update 1 hinzugefügt und waren als Teil von .NET Framework 4,5 enthalten. Weitere Informationen zu Zustandsautomatworkflows in .NET Framework 4.0.1-4.0.3 und .NET Framework 4,5 finden Sie unter [Update 4.0.1 for Microsoft .NET Framework 4 Features](/previous-versions/dotnet/netframework-4.0/hh290669(v=vs.100)) und [State Machine Workflows](state-machine-workflows.md).

 [Cookbook zur WF-Migration: benutzerdefinierte Aktivitäten](/previous-versions/appfabric/ff383417(v=azure.10)) Enthält Beispiele und Anweisungen zum erneuten Entwerfen von benutzerdefinierten Aktivitäten WF3 auf WF4.

 [Cookbook zur WF-Migration: Erweiterte benutzerdefinierte Aktivitäten](/previous-versions/appfabric/ff383417(v=azure.10)) Enthält Anleitungen zum umgestalten erweiterter WF3 benutzerdefinierter Aktivitäten, die WF3-Warteschlangen verwenden und untergeordnete Aktivitäten als benutzerdefinierte Aktivitäten von WF4 planen.

 [Cookbook zur WF-Migration: Workflows](/previous-versions/appfabric/ff383417(v=azure.10)) Enthält Beispiele und Anweisungen zum Neuentwerfen von WF3-Workflows auf WF4.

 [Cookbook zur WF-Migration: Workflow Hosting](/previous-versions/appfabric/ff383417(v=azure.10)) Enthält Anleitungen zum umgestalten von WF3-Hostingcode als WF4-Hostingcode. Damit sollen die wesentlichen Unterschiede beim Workflowhosting zwischen WF3 und WF4 veranschaulicht werden.

 [Cookbook zur WF-Migration: Workflow Nachverfolgung](/previous-versions/appfabric/ff383417(v=azure.10)) Enthält Anleitungen zum Neuentwerfen von WF3-nach Verfolgungs Code und-Konfiguration mithilfe eines entsprechenden WF4-nach Verfolgungs Codes und der Konfiguration

 [WF-Anleitung: Workflow Dienste](/previous-versions/appfabric/ff383417(v=azure.10)) Enthält Beispiel orientierte Schritt-für-Schritt-Anleitungen zum Neuentwerfen von Workflows, die Windows Communication Foundation (WCF)-Webdienste implementieren (häufig als Workflow Dienste bezeichnet), die in WF3 erstellt wurden, um WF4 für gängige Szenarien zu verwenden.

## <a name="see-also"></a>Weitere Informationen

- <xref:System.Activities.Statements.Interop>
