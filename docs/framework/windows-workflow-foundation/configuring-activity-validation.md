---
title: Konfigurieren der Aktivitätsvalidierung
ms.date: 03/30/2017
ms.assetid: 25a4eccb-b8fc-4857-a01d-2683b6341219
ms.openlocfilehash: c3e10fc096b16ef2cf7a6c7533ac9bad8c5ec205
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96288956"
---
# <a name="configuring-activity-validation"></a>Konfigurieren der Aktivitätsvalidierung

Die Aktivitätsvalidierung ermöglicht es Autoren und Benutzern von Aktivitäten, Fehler in der Konfiguration einer Aktivität vor der Ausführung zu identifizieren und zu melden. Windows Workflow Foundation (WF) stellt die folgenden drei Arten der Aktivitäts Validierung bereit:  
  
- `RequiredArgument`-Attribute und `OverloadGroup`-Attribute  
  
- Imperative codebasierte Validierung  
  
- Deklarative Einschränkungen  
  
 Das `RequiredArgument`-Attribut und das `OverloadGroup`-Attribut geben an, dass bestimmte Argumente für eine Aktivität erforderlich sind. Die imperative codebasierte Validierung stellt eine problemlose Möglichkeit für eine Aktivität dar, sich selbst zu validieren. Deklarative Einschränkungen ermöglichen die Validierung der Aktivität und ihrer Beziehung zum enthaltenden Workflow. Wenn eine Aktivität nicht ordnungsgemäß nach den Validierungsanforderungen konfiguriert wird, werden Validierungsfehler und -warnungen zurückgegeben. Wenn der enthaltende Workflow mit dem Workflow-Designer erstellt wird, werden alle Validierungsfehler und -warnungen im Designer angezeigt. Falls der Workflow außerhalb des Workflow-Designers erstellt wird, werden alle Validierungsfehler beim Aufrufen des Workflows zurückgegeben. Unabhängig von der Art der Erstellung des Workflows ist die Ausführung eines Workflows mit Validierungsfehlern nie zulässig. Dieser Abschnitt bietet eine Übersicht über diese Arten der Aktivitätsvalidierung und den Aufruf der Aktivitätsvalidierung.  
  
## <a name="in-this-section"></a>In diesem Abschnitt  

 [Erforderliche Argumente und Überladungsgruppen](required-arguments-and-overload-groups.md)  
 Beschreibt die Verwendung des `RequiredArgument`-Attributs und des `OverloadGroup`-Attributs zur Bereitstellung der Validierung.  
  
 [Imperative codebasierte Validierung](imperative-code-based-validation.md)  
 Beschreibt die Verwendung der codebasierten Validierung für Aktivitäten auf Grundlage von <xref:System.Activities.CodeActivity> und <xref:System.Activities.NativeActivity>.  
  
 [Deklarative Einschränkungen](declarative-constraints.md)  
 Beschreibt die Verwendung von deklarativen Einschränkungen für die Bereitstellung einer komplexen Aktivitätsvalidierung.  
  
 [Aufrufen der Aktivitätsvalidierung](invoking-activity-validation.md)  
 Erläutert, wann die Aktivitätsvalidierung automatisch aufgerufen wird und wie die Validierung explizit aufgerufen wird.  
  
## <a name="reference"></a>Referenz  
  
## <a name="related-sections"></a>Verwandte Abschnitte
