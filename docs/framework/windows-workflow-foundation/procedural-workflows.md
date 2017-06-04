---
title: "Verfahrensworkflows | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 52401de9-9115-472d-8fd9-047af6a072b9
caps.latest.revision: 17
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 17
---
# Verfahrensworkflows
Verfahrensworkflows verwenden Flusssteuerungsmethoden ähnlich jenen, die in verfahrensorientierten Sprachen verwendet werden.Hierzu zählen u. a. `While` und `If`.Diese Workflows können mit anderen Flusssteuerungsaktivitäten wie <xref:System.Activities.Statements.Flowchart> und <xref:System.Activities.Statements.Sequence> frei zusammengefasst werden.  
  
## Steuern des Ausführungsflusses  
 Die Workflowaktivitätsbibliothek verfügt über Aktivitäten zum Modellieren der meisten Flusssteuerungsmethoden, die in verfahrensorientierten Sprachen verwendet werden.Dazu gehören:  
  
-   <xref:System.Activities.Statements.While>  
  
-   <xref:System.Activities.Statements.DoWhile>  
  
-   <xref:System.Activities.Statements.ForEach>  
  
-   <xref:System.Activities.Statements.Parallel>  
  
-   <xref:System.Activities.Statements.ParallelForEach>  
  
-   <xref:System.Activities.Statements.If>  
  
-   <xref:System.Activities.Statements.Switch>  
  
-   <xref:System.Activities.Statements.Pick>  
  
 Um Flusssteuerungsaktivitäten zu verwenden, ziehen sie diese aus der Toolbox **Aktivitäten** in eine zusammengesetzte Aktivität im Fenster des Designers, und legen Sie sie dort ab.  
  
> [!NOTE]
>  Wenn [!INCLUDE[dublin](../../../includes/dublin-md.md)] zum Hosten von Workflow in einer Webfarm verwendet wird, verschiebt AppFabric Instanzen zwischen unterschiedlichen AppFabric\-Servern.Dies erfordert, dass die Ressourcen von allen Knoten gemeinsam genutzt werden können.Keine der standardmäßigen .NET 4\-Workflowaktivitäten enthalten Vorgänge, die auf lokale Ressourcen zugreifen.Da AppFabric keinen Mechanismus bietet, um einen Workflow als "nicht verschiebbar" zu markieren, darf ein Entwickler keine benutzerdefinierten Aktivitäten erstellen, die fehlschlagen, wenn ein Workflow verschoben wird.  
  
## Siehe auch  
 [Flussdiagrammworkflows](../../../docs/framework/windows-workflow-foundation//flowchart-workflows.md)