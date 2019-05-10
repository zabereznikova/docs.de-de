---
title: Konfigurieren der Aktivitätsvalidierung
ms.date: 03/30/2017
ms.assetid: 25a4eccb-b8fc-4857-a01d-2683b6341219
ms.openlocfilehash: 6c971b56e269fbb330bd9ad0a551a9fb9ca01196
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/28/2019
ms.locfileid: "64655111"
---
# <a name="configuring-activity-validation"></a>Konfigurieren der Aktivitätsvalidierung
Die Aktivitätsvalidierung ermöglicht es Autoren und Benutzern von Aktivitäten, Fehler in der Konfiguration einer Aktivität vor der Ausführung zu identifizieren und zu melden. Windows Workflow Foundation (WF) stellt die folgenden drei Arten von aktivitätsvalidierung bereit:  
  
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
