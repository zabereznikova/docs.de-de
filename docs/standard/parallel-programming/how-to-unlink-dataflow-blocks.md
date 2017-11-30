---
title: "Gewusst wie: Verknüpfungen für Datenflussblöcke aufheben"
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
- dataflow blocks, unlinking in TPL
- Task Parallel Library, dataflows
- TPL dataflow library, unlinking dataflow blocks
ms.assetid: 40f0208d-4618-47f7-85cf-4913d07d2d7d
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 41f1b83fab6ff44e69ac2f010f70e6e254341f5e
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="how-to-unlink-dataflow-blocks"></a><span data-ttu-id="634bf-102">Gewusst wie: Verknüpfungen für Datenflussblöcke aufheben</span><span class="sxs-lookup"><span data-stu-id="634bf-102">How to: Unlink Dataflow Blocks</span></span>
<span data-ttu-id="634bf-103">Dieses Dokument beschreibt, wie Verknüpfung zwischen einen Datenfluss Zielblock und der zugehörigen Quelle aufgelöst wird.</span><span class="sxs-lookup"><span data-stu-id="634bf-103">This document describes how to unlink a target dataflow block from its source.</span></span>  
  
> [!TIP]
>  <span data-ttu-id="634bf-104">Die TPL-Datenflussbibliothek (<xref:System.Threading.Tasks.Dataflow?displayProperty=nameWithType>-Namespace) ist nicht in [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] enthalten.</span><span class="sxs-lookup"><span data-stu-id="634bf-104">The TPL Dataflow Library (<xref:System.Threading.Tasks.Dataflow?displayProperty=nameWithType> namespace) is not distributed with the [!INCLUDE[net_v45](../../../includes/net-v45-md.md)].</span></span> <span data-ttu-id="634bf-105">Öffnen Sie zum Installieren des <xref:System.Threading.Tasks.Dataflow>-Namespace das Projekt in [!INCLUDE[vs_dev11_long](../../../includes/vs-dev11-long-md.md)], wählen Sie im Menü "Projekt" die Option **NuGet-Pakete verwalten** aus, und suchen Sie online nach dem `Microsoft.Tpl.Dataflow` -Paket.</span><span class="sxs-lookup"><span data-stu-id="634bf-105">To install the <xref:System.Threading.Tasks.Dataflow> namespace, open your project in [!INCLUDE[vs_dev11_long](../../../includes/vs-dev11-long-md.md)], choose **Manage NuGet Packages** from the Project menu, and search online for the `Microsoft.Tpl.Dataflow` package.</span></span>  
  
## <a name="example"></a><span data-ttu-id="634bf-106">Beispiel</span><span class="sxs-lookup"><span data-stu-id="634bf-106">Example</span></span>  
 <span data-ttu-id="634bf-107">Das folgende Beispiel erstellt drei <xref:System.Threading.Tasks.Dataflow.TransformBlock%602> Objekte, die jeweils die Aufrufe der `TrySolution` Methode, um einen Wert zu berechnen.</span><span class="sxs-lookup"><span data-stu-id="634bf-107">The following example creates three <xref:System.Threading.Tasks.Dataflow.TransformBlock%602> objects, each of which calls the `TrySolution` method to compute a value.</span></span> <span data-ttu-id="634bf-108">Dieses Beispiel benötigen Sie nur das Ergebnis aus dem ersten Aufruf `TrySolution` um den Vorgang abzuschließen.</span><span class="sxs-lookup"><span data-stu-id="634bf-108">This example requires only the result from the first call to `TrySolution` to finish.</span></span>  
  
 [!code-csharp[TPLDataflow_ReceiveAny#1](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_receiveany/cs/dataflowreceiveany.cs#1)]
 [!code-vb[TPLDataflow_ReceiveAny#1](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_receiveany/vb/dataflowreceiveany.vb#1)]  
  
 <span data-ttu-id="634bf-109">Empfangen Sie den Wert aus dem ersten <xref:System.Threading.Tasks.Dataflow.TransformBlock%602> Objekt, das abgeschlossen ist, in diesem Beispiel definiert die `ReceiveFromAny(T)` Methode.</span><span class="sxs-lookup"><span data-stu-id="634bf-109">To receive the value from the first <xref:System.Threading.Tasks.Dataflow.TransformBlock%602> object that finishes, this example defines the `ReceiveFromAny(T)` method.</span></span> <span data-ttu-id="634bf-110">Die `ReceiveFromAny(T)` Methode nimmt ein Array aus <xref:System.Threading.Tasks.Dataflow.ISourceBlock%601> Objekte und verknüpft Sie jedes dieser Objekte zu einer <xref:System.Threading.Tasks.Dataflow.WriteOnceBlock%601> Objekt.</span><span class="sxs-lookup"><span data-stu-id="634bf-110">The `ReceiveFromAny(T)` method accepts an array of <xref:System.Threading.Tasks.Dataflow.ISourceBlock%601> objects and links each of these objects to a <xref:System.Threading.Tasks.Dataflow.WriteOnceBlock%601> object.</span></span> <span data-ttu-id="634bf-111">Bei Verwendung der <xref:System.Threading.Tasks.Dataflow.ISourceBlock%601.LinkTo%2A> verknüpft einen quelldatenflussblock mit einem Zielblock, der die Quelle Nachrichten an das Ziel weitergegeben, sobald Daten verfügbar werden.</span><span class="sxs-lookup"><span data-stu-id="634bf-111">When you use the <xref:System.Threading.Tasks.Dataflow.ISourceBlock%601.LinkTo%2A> method to link a source dataflow block to a target block, the source propagates messages to the target as data becomes available.</span></span> <span data-ttu-id="634bf-112">Da die <xref:System.Threading.Tasks.Dataflow.WriteOnceBlock%601> Klasse akzeptiert nur die erste Nachricht, die sie bereitgestellt werden, die `ReceiveFromAny(T)` Methode erzeugt das Ergebnis durch Aufrufen der <xref:System.Threading.Tasks.Dataflow.DataflowBlock.Receive%2A> Methode.</span><span class="sxs-lookup"><span data-stu-id="634bf-112">Because the <xref:System.Threading.Tasks.Dataflow.WriteOnceBlock%601> class accepts only the first message that it is offered, the `ReceiveFromAny(T)` method produces its result by calling the <xref:System.Threading.Tasks.Dataflow.DataflowBlock.Receive%2A> method.</span></span> <span data-ttu-id="634bf-113">Die erste Nachricht, die angeboten wird hierdurch die <xref:System.Threading.Tasks.Dataflow.WriteOnceBlock%601> Objekt.</span><span class="sxs-lookup"><span data-stu-id="634bf-113">This produces the first message that is offered to the <xref:System.Threading.Tasks.Dataflow.WriteOnceBlock%601> object.</span></span> <span data-ttu-id="634bf-114">Der <xref:System.Threading.Tasks.Dataflow.ISourceBlock%601.LinkTo%2A> Methode verfügt über eine überladene Version, die akzeptiert eine <xref:System.Boolean> Parameter `unlinkAfterOne` , wenn er auf festgelegt ist `True`, weist den Quellblock an das Ziel aufheben, nachdem das Ziel eine Nachricht aus der Quelle empfangen hat.</span><span class="sxs-lookup"><span data-stu-id="634bf-114">The <xref:System.Threading.Tasks.Dataflow.ISourceBlock%601.LinkTo%2A> method has an overloaded version that takes a <xref:System.Boolean> parameter, `unlinkAfterOne` that, when it is set to `True`, instructs the source block to unlink from the target after the target receives one message from the source.</span></span> <span data-ttu-id="634bf-115">Es ist wichtig für die <xref:System.Threading.Tasks.Dataflow.WriteOnceBlock%601> -Objekt, dessen Quellen aufheben können, da die Beziehung zwischen dem Array von Quellen und die <xref:System.Threading.Tasks.Dataflow.WriteOnceBlock%601> Objekt ist nicht mehr erforderlich ist, nach der <xref:System.Threading.Tasks.Dataflow.WriteOnceBlock%601> -Objekt eine Nachricht empfängt.</span><span class="sxs-lookup"><span data-stu-id="634bf-115">It is important for the <xref:System.Threading.Tasks.Dataflow.WriteOnceBlock%601> object to unlink from its sources because the relationship between the array of sources and the <xref:System.Threading.Tasks.Dataflow.WriteOnceBlock%601> object is no longer required after the <xref:System.Threading.Tasks.Dataflow.WriteOnceBlock%601> object receives a message.</span></span>  
  
 <span data-ttu-id="634bf-116">So aktivieren Sie die übrigen Aufrufe `TrySolution` , endet, wenn eine von ihnen einen Wert berechnet die `TrySolution` -Methode übernimmt ein <xref:System.Threading.CancellationToken> -Objekt, das nach dem Aufruf von abgebrochen wird `ReceiveFromAny(T)` zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="634bf-116">To enable the remaining calls to `TrySolution` to end after one of them computes a value, the `TrySolution` method takes a <xref:System.Threading.CancellationToken> object that is canceled after the call to `ReceiveFromAny(T)` returns.</span></span> <span data-ttu-id="634bf-117">Die <xref:System.Threading.SpinWait.SpinUntil%2A> Methode gibt zurück, wenn dies <xref:System.Threading.CancellationToken> -Objekt abgebrochen wird.</span><span class="sxs-lookup"><span data-stu-id="634bf-117">The <xref:System.Threading.SpinWait.SpinUntil%2A> method returns when this <xref:System.Threading.CancellationToken> object is canceled.</span></span>  
  
## <a name="compiling-the-code"></a><span data-ttu-id="634bf-118">Kompilieren des Codes</span><span class="sxs-lookup"><span data-stu-id="634bf-118">Compiling the Code</span></span>  
 <span data-ttu-id="634bf-119">Kopieren Sie den Beispielcode, und fügen Sie ihn in ein Visual Studio-Projekt ein. Alternativ können Sie ihn auch in eine Datei mit dem Namen `DataflowReceiveAny.cs` (`DataflowReceiveAny.vb` für [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)]) einfügen und dann folgenden Befehl in einem Visual Studio-Eingabeaufforderungsfenster ausführen.</span><span class="sxs-lookup"><span data-stu-id="634bf-119">Copy the example code and paste it in a Visual Studio project, or paste it in a file that is named `DataflowReceiveAny.cs` (`DataflowReceiveAny.vb` for [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)]), and then run the following command in a Visual Studio Command Prompt window.</span></span>  
  
 [!INCLUDE[csprcs](../../../includes/csprcs-md.md)]  
  
 <span data-ttu-id="634bf-120">**csc.exe /r:System.Threading.Tasks.Dataflow.dll DataflowReceiveAny.cs**</span><span class="sxs-lookup"><span data-stu-id="634bf-120">**csc.exe /r:System.Threading.Tasks.Dataflow.dll DataflowReceiveAny.cs**</span></span>  
  
 [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)]  
  
 <span data-ttu-id="634bf-121">**vbc.exe /r:System.Threading.Tasks.Dataflow.dll DataflowReceiveAny.vb**</span><span class="sxs-lookup"><span data-stu-id="634bf-121">**vbc.exe /r:System.Threading.Tasks.Dataflow.dll DataflowReceiveAny.vb**</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="634bf-122">Stabile Programmierung</span><span class="sxs-lookup"><span data-stu-id="634bf-122">Robust Programming</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="634bf-123">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="634bf-123">See Also</span></span>  
 [<span data-ttu-id="634bf-124">Dataflow (Datenfluss)</span><span class="sxs-lookup"><span data-stu-id="634bf-124">Dataflow</span></span>](../../../docs/standard/parallel-programming/dataflow-task-parallel-library.md)
