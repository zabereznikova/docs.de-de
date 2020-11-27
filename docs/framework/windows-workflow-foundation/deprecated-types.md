---
title: Veraltete Typen in Windows Workflow Foundation
ms.date: 03/30/2017
ms.assetid: 4aebe928-a964-4c1c-abf7-0dbbd3604b13
ms.openlocfilehash: 628963650d32237dedbb6ab2a0a2d9a79866af18
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96272871"
---
# <a name="deprecated-types-in-windows-workflow-foundation"></a>Veraltete Typen in Windows Workflow Foundation

In .NET 4 hat das Workflowteam eine neue Workflow-Engine im <xref:System.Activities>-Namespace eingeführt. Mit der Veröffentlichung von .NET Framework 4,5 Beta werden die meisten Typen in den Namespaces "WF 3" <xref:System.Workflow.Activities> , <xref:System.Workflow.ComponentModel> und  <xref:System.Workflow.Runtime> als veraltet markiert.

## <a name="obsolete-namespaces-and-tools"></a>Veraltete Namespaces und Tools

 Die folgenden Assemblys enthalten mindestens einen öffentlichen Typ, der veraltet sein wird:

- System.Workflow.Activities.dll

- System.Workflow.ComponentModel.dll

- System.Workflow.Runtime.dll

- System.WorkflowServices.dll

- Microsoft.Workflow.DebugController.dll

- Microsoft.Workflow.Compiler.exe

- Wfc.exe

 Daher werden bei Kunden, die veraltete WF3-APIs verwenden, Erstellungswarnungen mit einer Meldung angezeigt, die der folgenden ähnelt:

 **Warnung BC40000: X ist veraltet: WF 3-Typen sind veraltet. Verwenden Sie stattdessen WF 4.** In einem zukünftigen Release werden die Typen aus .NET Framework entfernt, doch der genaue Zeitpunkt hierfür steht noch nicht fest (nicht in 4.5). Dieser Schritt ermöglicht es uns, unseren Kunden unsere Pläne mitzuteilen und ihnen ausreichend Zeit zu geben, zum neuen WF4-Modell zu wechseln. Diese WF 3-Typen werden natürlich weiterhin unter der [Microsoft-Support Lifecycle-Richtlinie](/lifecycle/)unterstützt. Vorhandene WF3-Anwendungen können ohne Probleme auf .NET Framework 4,5 ausgeführt werden, und Visual Studio 2012 unterstützt neue und vorhandene WF3-basierte Lösungen.

 Regelbezogene Typen im <xref:System.Workflow.Activities.Rules>-Namespace, für die es in WF 4.5 keinen Ersatz gibt, wurden nicht als veraltet markiert.

 Kunden, die Ihre Anwendungen zu WF 4 migrieren möchten, finden Hilfe in der [Migrations Anleitung für Workflow 4](migration-guidance.md).
