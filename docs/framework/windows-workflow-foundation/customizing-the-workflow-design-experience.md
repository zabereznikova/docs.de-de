---
title: Anpassen des Workflowentwurfsvorgangs
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: extending [WF], Workflow Designer
ms.assetid: 98135077-0f5d-4d16-9337-01094e843537
caps.latest.revision: "13"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 9916e30812e167e108a1ca9b958aa6d15fbd1f41
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="customizing-the-workflow-design-experience"></a>Anpassen des Workflowentwurfsvorgangs
Die Szenarien zum Entwerfen von benutzerdefinierten Aktivitäten und zum erneuten Hosten von [!INCLUDE[wfd1](../../../includes/wfd1-md.md)] wurden in [!INCLUDE[netfx40_short](../../../includes/netfx40-short-md.md)] deutlich vereinfacht. Die Entwicklung und Bereitstellung sind jetzt einfacher sowie flexibler. Die wichtigste Änderung besteht darin, dass das neue Aktivitätsdesigner-Programmiermodell auf [!INCLUDE[avalon1](../../../includes/avalon1-md.md)] aufbaut. Dies ermöglicht Ihnen, Aktivitätsdesigner deklarativ zu definieren und den [!INCLUDE[wfd2](../../../includes/wfd2-md.md)] in anderen Anwendungen vergleichsweise einfach erneut zu hosten. Beim erneuten Hosten kann ein benutzerdefinierter Ausdrucks-Editor entwickelt werden, um IntelliSense oder eine vereinfachte Ausdrucksdomäne zu unterstützen. Die Integration in [!INCLUDE[indigo1](../../../includes/indigo1-md.md)] ist durch die Verwendung von Workflowdiensten nahtloser geworden. Benutzerdefinierte Aktivitätsdesigner und die Modellelementstruktur können verwendet werden, um die Entwurfszeiterfahrung in neu gehosteten Workflowdesignern zu verbessern.  
  
## <a name="in-this-section"></a>In diesem Abschnitt  
 [Verwenden benutzerdefinierter Aktivitätsdesigner und Vorlagen](../../../docs/framework/windows-workflow-foundation/using-custom-activity-designers-and-templates.md)  
 Beschreibt die Erstellung eines neuen benutzerdefinierten Aktivitätsdesigners und von Vorlagen.  
  
 [Erneutes Hosten des Workflow-Designers](../../../docs/framework/windows-workflow-foundation/rehosting-the-workflow-designer.md)  
 Beschreibt das erneute Hosten von [!INCLUDE[wfd1](../../../includes/wfd1-md.md)] außerhalb von [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] und wie Validierungsfehler angezeigt werden.  
  
 [Verwenden eines benutzerdefinierten Ausdrucks-Editors](../../../docs/framework/windows-workflow-foundation/using-a-custom-expression-editor.md)  
 Beschreibt die Implementierung eines benutzerdefinierten Ausdrucks-Editors zur Verwendung von Workflowdesignern, die außerhalb von [!INCLUDE[vs2010](../../../includes/vs2010-md.md)] erneut gehostet werden.  
  
## <a name="reference"></a>Verweis  
 <xref:System.Activities.Presentation.ActivityDesigner>  
  
## <a name="see-also"></a>Siehe auch  
 [Erweitern der Windows Workflow Foundation](../../../docs/framework/windows-workflow-foundation/extend.md)  
 [Designer](../../../docs/framework/windows-workflow-foundation/samples/designer.md)  
 [Benutzerdefinierte Aktivitätsdesigner](../../../docs/framework/windows-workflow-foundation/samples/custom-activity-designers.md)  
 [Hosten von Designern](../../../docs/framework/windows-workflow-foundation/samples/designer-rehosting.md)
