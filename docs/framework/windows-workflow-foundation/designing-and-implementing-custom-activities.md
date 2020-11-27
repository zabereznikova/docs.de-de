---
title: Entwerfen und Implementieren von benutzerdefinierten Aktivitäten
description: Dieser Artikel enthält Ressourcen zum Erstellen benutzerdefinierter Aktivitäten in Workflow Foundation, indem Sie zusammengesetzte Aktivitäten erstellen oder neue Aktivitätstypen erstellen.
ms.date: 03/30/2017
ms.assetid: 4e30e63d-6e33-4842-a7a4-ce807cef1fad
ms.openlocfilehash: cb6e189cf5f59630ce8d89610eb0c2fc2acc92a7
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96280389"
---
# <a name="designing-and-implementing-custom-activities"></a>Entwerfen und Implementieren von benutzerdefinierten Aktivitäten

Benutzerdefinierte Aktivitäten in [!INCLUDE[netfx_current_long](../../../includes/netfx-current-long-md.md)] werden erstellt, indem entweder vom System bereitgestellte Aktivitäten zu zusammengesetzten Aktivitäten zusammengefasst oder indem neue Typen erstellt werden, die von <xref:System.Activities.CodeActivity>, <xref:System.Activities.AsyncCodeActivity> oder <xref:System.Activities.NativeActivity> abgeleitet werden. In diesem Abschnitt wird beschrieben, wie benutzerdefinierte Aktivitäten mit diesen beiden Methoden erstellt werden.  
  
> [!IMPORTANT]
> Benutzerdefinierte Aktivitäten werden im Workflow-Designer standardmäßig als einfaches Rechteck mit dem Namen der Aktivität angezeigt. Um eine benutzerdefinierte grafische Darstellung der Aktivität im Workflow-Designer bereitzustellen, müssen Sie auch einen benutzerdefinierten Designer erstellen. Weitere Informationen finden Sie unter [Verwenden von benutzerdefinierten Aktivitäts Designern und Vorlagen](using-custom-activity-designers-and-templates.md).  
  
## <a name="in-this-section"></a>In diesem Abschnitt  

 [Aktivitätserstellungsoptionen](activity-authoring-options-in-wf.md)  
 Erläutert die in [!INCLUDE[netfx_current_long](../../../includes/netfx-current-long-md.md)] verfügbaren Erstellungsformate.  
  
 [Verwenden einer benutzerdefinierten Aktivität](using-a-custom-activity.md)  
 Beschreibt, wie einem Workflowprojekt eine benutzerdefinierte Aktivität hinzufügt wird.  
  
  [Erstellen von asynchronen Aktivitäten](creating-asynchronous-activities-in-wf.md)  
 Beschreibt die Erstellung asynchroner Aktivitäten.  
  
 [Konfigurieren der Aktivitätsvalidierung](configuring-activity-validation.md)  
 Beschreibt, wie die Aktivitätsvalidierung verwendet werden kann, um Fehler in der Konfiguration einer Aktivität vor der Ausführung zu identifizieren und zu melden.  
  
 [Erstellen einer Aktivität zur Laufzeit](creating-an-activity-at-runtime-with-dynamicactivity.md)  
 Erläutert, wie Aktivitäten zur Laufzeit mithilfe von <xref:System.Activities.DynamicActivity> erstellt werden.  
  
 [Eigenschaften der Workflowausführung](workflow-execution-properties.md)  
 Beschreibt, wie die Eigenschaften der Workflowausführung verwendet werden, um der Umgebung einer Aktivität kontextspezifische Eigenschaften hinzuzufügen.  
  
 [Verwenden von Aktivitätsdelegaten](using-activity-delegates.md)  
 Erläutert, wie Aktivitäten erstellt und verwendet werden, die Aktivitätsdelegaten enthalten.
  
 [Verwenden von Aktivitätserweiterungen](using-activity-extensions.md)  
 Beschreibt, wie Aktivitätserweiterungen erstellt und verwendet werden.  
  
 [Verarbeiten von OData-Feeds eines Workflows](consuming-odata-feeds-from-a-workflow.md)  
 Beschreibt verschiedene Möglichkeiten zum Aufrufen eines WCF Data Service aus einem Workflow.  
  
 [Bereichsauswahl und Sichtbarkeit der Aktivitätsdefinition](activity-definition-scoping-and-visibility.md)  
 Beschreibt die Optionen und Regeln zum Definieren von Datenbereichen sowie der Membersichtbarkeit für Aktivitäten.
