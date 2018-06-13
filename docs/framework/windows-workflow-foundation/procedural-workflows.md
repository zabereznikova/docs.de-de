---
title: Verfahrensworkflows
ms.date: 03/30/2017
ms.assetid: 52401de9-9115-472d-8fd9-047af6a072b9
ms.openlocfilehash: 5cd97c8ccaae74e4275f809502ac0a4d3c2f042a
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33515228"
---
# <a name="procedural-workflows"></a>Verfahrensworkflows
Verfahrensworkflows verwenden Flusssteuerungsmethoden ähnlich jenen, die in verfahrensorientierten Sprachen verwendet werden. Hierzu zählen u. a. `While` und `If`. Diese Workflows können mit anderen Flusssteuerungsaktivitäten wie <xref:System.Activities.Statements.Flowchart> und <xref:System.Activities.Statements.Sequence> frei zusammengefasst werden.  
  
## <a name="controlling-execution-flow"></a>Steuern des Ausführungsflusses  
 Die Workflowaktivitätsbibliothek verfügt über Aktivitäten zum Modellieren der meisten Flusssteuerungsmethoden, die in verfahrensorientierten Sprachen verwendet werden. Dazu gehören:  
  
-   <xref:System.Activities.Statements.While>  
  
-   <xref:System.Activities.Statements.DoWhile>  
  
-   <xref:System.Activities.Statements.ForEach%601>  
  
-   <xref:System.Activities.Statements.Parallel>  
  
-   <xref:System.Activities.Statements.ParallelForEach%601>  
  
-   <xref:System.Activities.Statements.If>  
  
-   <xref:System.Activities.Statements.Switch%601>  
  
-   <xref:System.Activities.Statements.Pick>  
  
 Um Flusssteuerungsaktivitäten zu verwenden, Drag & drop aus der **Aktivität** Toolbox in eine zusammengesetzte Aktivität im Fenster Designers.  
  
> [!NOTE]
>  Wenn [!INCLUDE[dublin](../../../includes/dublin-md.md)] zum Hosten von Workflows in einer Webfarm verwendet wird, verschiebt AppFabric Instanzen zwischen unterschiedlichen AppFabric-Servern. Dies erfordert, dass die Ressourcen von allen Knoten gemeinsam genutzt werden können.  Keine der standardmäßigen .NET 4-Workflowaktivitäten enthalten Vorgänge, die auf lokale Ressourcen zugreifen. Da AppFabric keinen Mechanismus bietet, um einen Workflow als "nicht verschiebbar" zu markieren, darf ein Entwickler keine benutzerdefinierten Aktivitäten erstellen, die fehlschlagen, wenn ein Workflow verschoben wird.  
  
## <a name="see-also"></a>Siehe auch  
 [Flussdiagrammworkflows](../../../docs/framework/windows-workflow-foundation/flowchart-workflows.md)
