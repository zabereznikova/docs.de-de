---
title: "Deprecated types in Windows Workflow Foundation | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 4aebe928-a964-4c1c-abf7-0dbbd3604b13
caps.latest.revision: 2
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 2
---
# Deprecated types in Windows Workflow Foundation
In .NET 4 hat das Workflowteam ein neues Workflowmodul im <xref:System.Activities>\-Namespace eingeführt.  Ab .NET 4.5 Beta werden die meisten Typen in den "WF3"\-Namespaces <xref:System.Workflow.Activities>, <xref:System.Workflow.ComponentModel> und <xref:System.Workflow.Runtime> als veraltet gekennzeichnet.  
  
## Veraltete Namespaces und Tools  
 Die folgenden Assemblys enthalten mindestens einen öffentlichen Typ, der veraltet sein wird:  
  
-   System.Workflow.Activities.dll  
  
-   System.Workflow.ComponentModel.dll  
  
-   System.Workflow.Runtime.dll  
  
-   System.WorkflowServices.dll  
  
-   Microsoft.Workflow.DebugController.dll  
  
-   Microsoft.Workflow.Compiler.exe  
  
-   Wfc.exe  
  
 Daher werden bei Kunden, die veraltete WF3\-APIs verwenden, Erstellungswarnungen mit einer Meldung angezeigt, die der folgenden ähnelt:  
  
  **Warnung: BC40000 X ist veraltet: WF3\-Typen sind veraltet.  Verwenden Sie stattdessen WF4.**  In einer zukünftigen Version werden die Typen aus .NET Framework entfernt, doch der genaue Zeitpunkt hierfür steht noch nicht fest \(nicht in 4.5\).  Dieser Schritt ermöglicht es uns, unseren Kunden unsere Pläne mitzuteilen und ihnen ausreichend Zeit zu geben, zum neuen WF4\-Modell zu wechseln.  Die WF3\-Typen werden natürlich weiterhin unter der [Microsoft Support Lifecycle\-Richtlinie](http://aka.ms/MicrosoftSupportLifecycle) unterstützt.  Vorhandene WF3\-Anwendungen können ohne Probleme unter .NET 4.5 ausgeführt werden. [!INCLUDE[vs_current_long](../../../includes/vs-current-long-md.md)] unterstützt neue und vorhandene WF3\-basierte Lösungen.  
  
 Regelbezogene Typen im <xref:System.Workflow.Activities.Rules>\-Namespace, für die es in WF 4.5 keinen Ersatz gibt, wurden nicht als veraltet markiert.  
  
 Kunden, die ihre Anwendungen zu WF4 migrieren möchten, finden hilfreiche Informationen in den MSDN\-Artikeln für die [Anleitung zur WF4\-Migration](http://aka.ms/WF4MigrationGuidance) und im [WF4\-Migrationskit](http://aka.ms/WF4MigrationKit) auf der Website [WF Codeplex](http://aka.ms/WFCodeplex).