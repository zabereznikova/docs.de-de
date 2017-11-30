---
title: "Gewusst wie: Einen Parallelitätsgrad in einem Datenflussblock angeben"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- dataflow block, specifying parallelism in TPL
- Task Parallel Library, dataflows
- TPL dataflow library, specifying parallelism
ms.assetid: e4088541-ee05-40db-95f5-147cfe62fde7
caps.latest.revision: "9"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: c1ccd64a9acbc75a30984719671af2dc7dda6922
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="how-to-specify-the-degree-of-parallelism-in-a-dataflow-block"></a>Gewusst wie: Einen Parallelitätsgrad in einem Datenflussblock angeben
In diesem Dokument wird beschrieben, wie die <xref:System.Threading.Tasks.Dataflow.ExecutionDataflowBlockOptions.MaxDegreeOfParallelism%2A?displayProperty=nameWithType>-Eigenschaft festgelegt wird, damit ein Ausführungsdatenflussblock mehrere Nachrichten gleichzeitig verarbeiten kann. Dies ist hilfreich, wenn ein Datenflussblock vorliegt, der eine lang andauernde Berechnung ausführt, und Sie von der parallelen Verarbeitung von Nachrichten profitieren können. In diesem Beispiel wird die <xref:System.Threading.Tasks.Dataflow.ActionBlock%601?displayProperty=nameWithType>-Klasse verwendet, um mehrere Datenflussvorgänge gleichzeitig auszuführen. Sie können den maximalen Grad an Parallelität jedoch in jedem der vordefinierten Ausführungsblocktypen angeben, die von der TPL-Datenflussbibliothek bereitgestellt werden: <xref:System.Threading.Tasks.Dataflow.ActionBlock%601>, <xref:System.Threading.Tasks.Dataflow.TransformBlock%602?displayProperty=nameWithType> und <xref:System.Threading.Tasks.Dataflow.TransformManyBlock%602?displayProperty=nameWithType>.  
  
> [!TIP]
>  Die TPL-Datenflussbibliothek (<xref:System.Threading.Tasks.Dataflow?displayProperty=nameWithType>-Namespace) wird nicht mit [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] ausgeliefert. Öffnen Sie zum Installieren des <xref:System.Threading.Tasks.Dataflow>-Namespace das Projekt in [!INCLUDE[vs_dev11_long](../../../includes/vs-dev11-long-md.md)], wählen Sie im Menü "Projekt" die Option **NuGet-Pakete verwalten** aus, und suchen Sie online nach dem `Microsoft.Tpl.Dataflow` -Paket.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel werden zwei Datenflussberechnungen ausgeführt und die für jede Berechnung erforderliche verstrichene Zeit ausgegeben. Die erste Berechnung gibt für den maximalen Grad an Parallelität den Wert 1 an, wobei es sich um den Standardwert handelt. Der Wert 1 für den maximalen Grad an Parallelität bewirkt, dass Nachrichten vom Datenflussblock seriell verarbeitet werden. Die zweite Berechnung ähnelt der ersten, sie gibt jedoch einen maximalen Grad an Parallelität an, der der Anzahl der verfügbaren Prozessoren entspricht. Dadurch kann der Datenflussblock mehrere Vorgänge parallel ausführen.  
  
 [!code-csharp[TPLDataflow_DegreeOfParallelism#1](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_degreeofparallelism/cs/dataflowdegreeofparallelism.cs#1)]
 [!code-vb[TPLDataflow_DegreeOfParallelism#1](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_degreeofparallelism/vb/dataflowdegreeofparallelism.vb#1)]  
  
## <a name="compiling-the-code"></a>Kompilieren des Codes  
 Kopieren Sie den Beispielcode, und fügen Sie ihn in ein Visual Studio-Projekt ein. Alternativ können Sie ihn auch in eine Datei mit dem Namen `DataflowDegreeOfParallelism.cs` (`DataflowDegreeOfParallelism.vb` für [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)]) einfügen und dann folgenden Befehl in einem Visual Studio-Eingabeaufforderungsfenster ausführen.  
  
 [!INCLUDE[csprcs](../../../includes/csprcs-md.md)]  
  
 **csc.exe /r:System.Threading.Tasks.Dataflow.dll DataflowDegreeOfParallelism.cs**  
  
 [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)]  
  
 **vbc.exe /r:System.Threading.Tasks.Dataflow.dll DataflowDegreeOfParallelism.vb**  
  
## <a name="robust-programming"></a>Stabile Programmierung  
 Standardmäßig gibt jeder vordefinierte Datenflussblock die Nachrichten in der Reihenfolge weiter, in der sie empfangen werden.  Obwohl mehrere Nachrichten gleichzeitig verarbeitet werden, wenn Sie einen maximalen Grad an Parallelität angeben, der größer als 1 ist, werden die Nachrichten möglicherweise weiterhin in der Reihenfolge weitergegeben, in der sie empfangen werden.  
  
 Da die <xref:System.Threading.Tasks.Dataflow.ExecutionDataflowBlockOptions.MaxDegreeOfParallelism%2A>-Eigenschaft den maximalen Grad an Parallelität darstellt, wird der Datenflussblock u. U. mit einem geringeren Grad an Parallelität ausgeführt als angegeben. Der Datenflussblock kann zum Erfüllen seiner Funktionsanforderungen oder aufgrund der Berücksichtigung eines Mangels an verfügbaren Systemressourcen einen geringeren Grad an Parallelität verwenden. Ein Datenflussblock wird nie mit einem höheren Grad an Parallelität ausgeführt als Sie angeben.  
  
## <a name="see-also"></a>Siehe auch  
 [Dataflow (Datenfluss)](../../../docs/standard/parallel-programming/dataflow-task-parallel-library.md)
