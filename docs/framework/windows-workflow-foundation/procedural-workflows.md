---
title: Verfahrensworkflows
description: In Workflow Foundation verwenden prozedurale Workflows Fluss Steuerungsmethoden, die denen in prozeduralen Sprachen ähneln.
ms.date: 03/30/2017
ms.assetid: 52401de9-9115-472d-8fd9-047af6a072b9
ms.openlocfilehash: 13d1b5e55b84687e2a78db1a94317b8b1e33328c
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96246029"
---
# <a name="procedural-workflows"></a>Verfahrensworkflows

Verfahrensworkflows verwenden Flusssteuerungsmethoden ähnlich jenen, die in verfahrensorientierten Sprachen verwendet werden. Hierzu zählen u. a. `While` und `If`. Diese Workflows können mit anderen Flusssteuerungsaktivitäten wie <xref:System.Activities.Statements.Flowchart> und <xref:System.Activities.Statements.Sequence> frei zusammengefasst werden.  
  
## <a name="controlling-execution-flow"></a>Steuern des Ausführungsflusses  

 Die Workflowaktivitätsbibliothek verfügt über Aktivitäten zum Modellieren der meisten Flusssteuerungsmethoden, die in verfahrensorientierten Sprachen verwendet werden. Dazu gehören:  
  
- <xref:System.Activities.Statements.While>  
  
- <xref:System.Activities.Statements.DoWhile>  
  
- <xref:System.Activities.Statements.ForEach%601>  
  
- <xref:System.Activities.Statements.Parallel>  
  
- <xref:System.Activities.Statements.ParallelForEach%601>  
  
- <xref:System.Activities.Statements.If>  
  
- <xref:System.Activities.Statements.Switch%601>  
  
- <xref:System.Activities.Statements.Pick>  
  
 Wenn Sie Fluss Steuerungsaktivitäten verwenden möchten, ziehen Sie diese per Drag & amp; Drop aus der **Aktivitäts** Toolbox in eine zusammengesetzte Aktivität innerhalb des Designer Fensters.  
  
> [!NOTE]
> Wenn die Hostingfunktionen von Windows Server AppFabric zum Hosten von Workflows in einer Webfarm verwendet werden, verschiebt AppFabric Instanzen zwischen verschiedenen AppFabric-Servern. Dies erfordert, dass die Ressourcen von allen Knoten gemeinsam genutzt werden können.  Keine der standardmäßigen .NET 4-Workflowaktivitäten enthalten Vorgänge, die auf lokale Ressourcen zugreifen. Da AppFabric keinen Mechanismus bietet, um einen Workflow als "nicht verschiebbar" zu markieren, darf ein Entwickler keine benutzerdefinierten Aktivitäten erstellen, die fehlschlagen, wenn ein Workflow verschoben wird.  
  
## <a name="see-also"></a>Weitere Informationen

- [Flussdiagrammworkflows](flowchart-workflows.md)
