---
title: Veraltete Typen in Windows Workflow Foundation
ms.date: 03/30/2017
ms.assetid: 4aebe928-a964-4c1c-abf7-0dbbd3604b13
ms.openlocfilehash: 899d21f23c0500a1df01916d1da210b2f9bea95b
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33512426"
---
# <a name="deprecated-types-in-windows-workflow-foundation"></a>Veraltete Typen in Windows Workflow Foundation
In .NET 4 hat das Workflowteam ein neues Workflowmodul im <xref:System.Activities>-Namespace eingeführt. Mit der Version von .NET 4.5 Beta werden wir die meisten Typen in den "WF3" markieren <xref:System.Workflow.Activities>, <xref:System.Workflow.ComponentModel>, und <xref:System.Workflow.Runtime> Namespaces als veraltet gekennzeichnet.  
  
## <a name="obsolete-namespaces-and-tools"></a>Veraltete Namespaces und Tools  
 Die folgenden Assemblys enthalten mindestens einen öffentlichen Typ, der veraltet sein wird:  
  
-   System.Workflow.Activities.dll  
  
-   System.Workflow.ComponentModel.dll  
  
-   System.Workflow.Runtime.dll  
  
-   System.WorkflowServices.dll  
  
-   Microsoft.Workflow.DebugController.dll  
  
-   Microsoft.Workflow.Compiler.exe  
  
-   Wfc.exe  
  
 Daher werden bei Kunden, die veraltete WF3-APIs verwenden, Erstellungswarnungen mit einer Meldung angezeigt, die der folgenden ähnelt:  
  
 **Warnung: BC40000 "X" ist veraltet: wf3-Typen sind veraltet. Verwenden Sie stattdessen wf4.** In einem zukünftigen Release werden die Typen aus .NET Framework entfernt, doch der genaue Zeitpunkt hierfür steht noch nicht fest (nicht in 4.5). Dieser Schritt ermöglicht es uns, unseren Kunden unsere Pläne mitzuteilen und ihnen ausreichend Zeit zu geben, zum neuen WF4-Modell zu wechseln. Wir werden natürlich weiterhin für die WF 3 unter Unterstützung der [Microsoft Support Lifecycle-Richtlinie](http://aka.ms/MicrosoftSupportLifecycle). Vorhandene WF3-Anwendungen können ohne Probleme unter .NET 4.5 ausgeführt werden. [!INCLUDE[vs_current_long](../../../includes/vs-current-long-md.md)] unterstützt neue und vorhandene WF3-basierte Lösungen.  
  
 Regelbezogene Typen im <xref:System.Workflow.Activities.Rules>-Namespace, für die es in WF 4.5 keinen Ersatz gibt, wurden nicht als veraltet markiert.  
  
 Kunden, die ihre Anwendungen zu wf4 migrieren möchten, findet in der Hilfe der [Workflow 4 Migrationsanleitung](migration-guidance.md).
