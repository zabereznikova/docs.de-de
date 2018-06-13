---
title: Migrationsanleitung
ms.date: 03/30/2017
ms.assetid: cb65c132-58c9-4028-b3d4-1efc71d5e60e
ms.openlocfilehash: 562ee0913f657b349d88fe7be1627ecd9469f317
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33516681"
---
# <a name="migration-guidance"></a>Migrationsanleitung
In der [!INCLUDE[netfx40_short](../../../includes/netfx40-short-md.md)], veröffentlicht Microsoft die zweite Hauptversion von Windows Workflow Foundation (WF). [!INCLUDE[wf1](../../../includes/wf1-md.md)] wurde unter [!INCLUDE[vstecwinfx](../../../includes/vstecwinfx-md.md)] veröffentlicht (enthält auch die Typen in den System.Workflow.*-Namespaces, jetzt als WF3 bezeichnet) und unter [!INCLUDE[netfx35_short](../../../includes/netfx35-short-md.md)] erweitert. WF3 ist auch Teil der [!INCLUDE[netfx40_short](../../../includes/netfx40-short-md.md)], aber neben einer neuen workflowtechnologie (Typen in den System.Activities.\* Namespaces; als WF4 bezeichnet). Beim Erwägen des Zeitpunkts für die Umstellung auf WF4 sollten Sie zuerst bedenken, dass Sie allein den zeitlichen Ablauf steuern können.  
  
-   WF3 ist ein vollständig unterstützter Teil von [!INCLUDE[netfx40_short](../../../includes/netfx40-short-md.md)].  
  
-   WF3-Anwendungen werden unter [!INCLUDE[netfx40_short](../../../includes/netfx40-short-md.md)] ohne Änderung ausgeführt und weiterhin voll unterstützt.  
  
-   Sie können neue WF3-Anwendungen erstellen, und Ihre bestehenden Anwendungen können in [!INCLUDE[vs_current_long](../../../includes/vs-current-long-md.md)] bearbeitet werden und werden vollständig unterstützt.  
  
 Daher wird die Entscheidung über den .NET Framework 4 nicht von der Entscheidung zur verschieben in WF4 entkoppelt (System.Activities) von WF3 (System.Workflow.\*). Dieses Thema enthält Links zu WF-Migrationsanleitungen mit Informationen zum Arbeiten mit WF3 und WF4.  
  
## <a name="wf-migration-whitepapers-and-cookbooks"></a>Whitepaper und Cookbooks zur WF-Migration  
 Die [Übersicht über die WF-Migration](http://go.microsoft.com/fwlink/?LinkId=153873) Thema bietet einen umfassenden Überblick über die Beziehung zwischen WF3 und WF4 und Migrationsstrategien. Speziellere Themenbereiche werden in Begleitthemen behandelt.  
  
 [Übersicht über die WF-Migration](http://go.microsoft.com/fwlink/?LinkId=153873)  
 Beschreibt die Beziehung zwischen WF3 und WF4 sowie die Optionen, die Sie als Benutzer oder potenzieller Benutzer der Workflowtechnologie unter .NET 4 haben.  
  
 [WF-Migration: Bewährte Methoden für WF3-Entwicklung](http://go.microsoft.com/fwlink/?LinkId=153852)  
 Beschreibt, wie Sie WF3-Artefakte so entwerfen, dass diese einfacher nach WF4 migriert werden können.  
  
 [WF-Anleitung: Regeln](http://go.microsoft.com/fwlink/?LinkId=153854)  
 Erläutert, wie Sie regelbezogene Investitionen in [!INCLUDE[netfx40_short](../../../includes/netfx40-short-md.md)]-Projektmappen umsetzen.  
  
 [WF-Anleitung: Zustandsautomat](http://go.microsoft.com/fwlink/?LinkId=153855)  
 Erläutert die WF4-Ablaufsteuerungsmodellierung bei Nichtvorhandensein einer Zustandsautomataktivität (State Machine).  
  
 Beachten Sie, dass diese Anleitung nur für Workflowprojekte gilt, die .NET Framework 4 als Zielframework verwenden. Zustandsautomatworkflows wurden in .NET 4.0.1 mit dem Plattform Update 1 hinzugefügt und in .NET Framework 4.5 beibehalten. Weitere Informationen zu Zustandsautomatworkflows in .NET 4.0.1 - 4.0.3 und .NET Framework 4.5 finden Sie unter [Update 4.0.1 für Microsoft .NET Framework 4-Funktionen](http://msdn.microsoft.com/library/de3297bd-c3e1-4126-95be-2ed7fe2a98fc) und [Zustandsautomatworkflows](../../../docs/framework/windows-workflow-foundation/state-machine-workflows.md).  
  
 [Rezeptbuch für WF-Migration: Benutzerdefinierte Aktivitäten](http://go.microsoft.com/fwlink/?LinkId=153856)  
 Enthält Beispiele und Anweisungen zum Umgestalten von benutzerdefinierten WF3-Aktivitäten unter WF4.  
  
 [Cookbook für WF-Migration: Erweiterte benutzerdefinierte Aktivitäten](http://go.microsoft.com/fwlink/?LinkId=275560)  
 Stellt eine Anleitung zur Neuentwicklung erweiterter benutzerdefinierter WF3-Aktivitäten bereit, die WF3-Warteschlangen verwenden und untergeordnete Aktivitäten als benutzerdefinierte WF4-Aktivitäten planen.  
  
 [Cookbook für WF-Migration: Workflows](http://go.microsoft.com/fwlink/?LinkId=153858)  
 Enthält Beispiele und Anleitungen zum Umgestalten von WF3-Workflows unter WF4.  
  
 [Cookbook für WF-Migration: Workflowhosting](http://go.microsoft.com/fwlink/?LinkId=275561)  
 Stellt eine Anleitung zur Umgestaltung des WF3-Hostingcodes als WF4-Hostingcode bereit. Damit sollen die wesentlichen Unterschiede beim Workflowhosting zwischen WF3 und WF4 veranschaulicht werden.  
  
 [Cookbook für WF-Migration: Workflownachverfolgung](http://go.microsoft.com/fwlink/?LinkId=275562)  
 Bietet Hilfestellung bei der Umgestaltung von WF3-Nachverfolgungscode und -Konfiguration mithilfe eines äquivalenten Nachverfolgungscodes und einer äquivalenten Konfiguration auf der Basis von WF4.  
  
 [WF-Anleitung: Workflowdienste](http://go.microsoft.com/fwlink/?LinkId=275564)  
 Stellt anhand eines Beispiels schrittweise Anweisungen zur Neuentwicklung von Workflows bereit, die in WF3 erstellte Windows Communication Foundation (WCF)-Webdienste (auch als Workflowdienste bezeichnet) für die Verwendung allgemeiner, vordefinierter Aktivitäten in WF4 implementieren.  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Activities.Statements.Interop>
