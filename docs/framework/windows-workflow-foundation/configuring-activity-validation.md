---
title: "Konfigurieren der Aktivitätsvalidierung"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 25a4eccb-b8fc-4857-a01d-2683b6341219
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: d75f03a9af5caa5569cbfd4d1d09cda8936f6562
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="configuring-activity-validation"></a>Konfigurieren der Aktivitätsvalidierung
Die Aktivitätsvalidierung ermöglicht es Autoren und Benutzern von Aktivitäten, Fehler in der Konfiguration einer Aktivität vor der Ausführung zu identifizieren und zu melden. [!INCLUDE[wf](../../../includes/wf-md.md)] stellt die folgenden drei Arten von Aktivitätsvalidierung bereit:  
  
-   `RequiredArgument`-Attribute und `OverloadGroup`-Attribute  
  
-   Imperative codebasierte Validierung  
  
-   Deklarative Einschränkungen  
  
 Das `RequiredArgument`-Attribut und das `OverloadGroup`-Attribut geben an, dass bestimmte Argumente für eine Aktivität erforderlich sind. Die imperative codebasierte Validierung stellt eine problemlose Möglichkeit für eine Aktivität dar, sich selbst zu validieren. Deklarative Einschränkungen ermöglichen die Validierung der Aktivität und ihrer Beziehung zum enthaltenden Workflow. Wenn eine Aktivität nicht ordnungsgemäß nach den Validierungsanforderungen konfiguriert wird, werden Validierungsfehler und -warnungen zurückgegeben. Wenn der enthaltende Workflow mit dem Workflow-Designer erstellt wird, werden alle Validierungsfehler und -warnungen im Designer angezeigt. Falls der Workflow außerhalb des Workflow-Designers erstellt wird, werden alle Validierungsfehler beim Aufrufen des Workflows zurückgegeben. Unabhängig von der Art der Erstellung des Workflows ist die Ausführung eines Workflows mit Validierungsfehlern nie zulässig. Dieser Abschnitt bietet eine Übersicht über diese Arten der Aktivitätsvalidierung und den Aufruf der Aktivitätsvalidierung.  
  
## <a name="in-this-section"></a>In diesem Abschnitt  
 [Erforderliche Argumente und Überladungsgruppen](../../../docs/framework/windows-workflow-foundation/required-arguments-and-overload-groups.md)  
 Beschreibt die Verwendung des `RequiredArgument`-Attributs und des `OverloadGroup`-Attributs zur Bereitstellung der Validierung.  
  
 [Imperative codebasierte Validierung](../../../docs/framework/windows-workflow-foundation/imperative-code-based-validation.md)  
 Beschreibt die Verwendung der codebasierten Validierung für Aktivitäten auf Grundlage von <xref:System.Activities.CodeActivity> und <xref:System.Activities.NativeActivity>.  
  
 [Deklarative Einschränkungen](../../../docs/framework/windows-workflow-foundation/declarative-constraints.md)  
 Beschreibt die Verwendung von deklarativen Einschränkungen für die Bereitstellung einer komplexen Aktivitätsvalidierung.  
  
 [Aufrufen der Aktivitätsvalidierung](../../../docs/framework/windows-workflow-foundation/invoking-activity-validation.md)  
 Erläutert, wann die Aktivitätsvalidierung automatisch aufgerufen wird und wie die Validierung explizit aufgerufen wird.  
  
## <a name="reference"></a>Verweis  
  
## <a name="related-sections"></a>Verwandte Abschnitte
