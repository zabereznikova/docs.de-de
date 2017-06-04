---
title: "How to: Unlink Dataflow Blocks | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-standard"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "dataflow blocks, unlinking in TPL"
  - "Task Parallel Library, dataflows"
  - "TPL dataflow library, unlinking dataflow blocks"
ms.assetid: 40f0208d-4618-47f7-85cf-4913d07d2d7d
caps.latest.revision: 11
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 11
---
# How to: Unlink Dataflow Blocks
Dieses Dokument beschreibt, wie ein Zieldatenflussblock von der Quelle wird.  
  
> [!TIP]
>  Die TPL\-Datenflussbibliothek \(<xref:System.Threading.Tasks.Dataflow?displayProperty=fullName>\-Namespace\) ist nicht in [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] enthalten.  Öffnen Sie zum Installieren des <xref:System.Threading.Tasks.Dataflow>\-Namespace das Projekt in [!INCLUDE[vs_dev11_long](../../../includes/vs-dev11-long-md.md)], wählen Sie im Menü "Projekt" die Option **NuGet\-Pakete verwalten** aus, und suchen Sie online nach dem `Microsoft.Tpl.Dataflow`\-Paket.  
  
## Beispiel  
 Im folgenden Beispiel erstellt drei Objekte <xref:System.Threading.Tasks.Dataflow.TransformBlock%602>, das die `TrySolution`\-Methode aufgerufen wird, um einen Wert zu berechnen.  Dieses Beispiel erfordert nur das Ergebnis vom ersten Aufruf von `TrySolution` zu beenden.  
  
 [!code-csharp[TPLDataflow_ReceiveAny#1](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_receiveany/cs/dataflowreceiveany.cs#1)]
 [!code-vb[TPLDataflow_ReceiveAny#1](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_receiveany/vb/dataflowreceiveany.vb#1)]  
  
 Um den Wert der ersten <xref:System.Threading.Tasks.Dataflow.TransformBlock%602> empfangen wenden Sie ein Ende, dass dieses Beispiel die `ReceiveFromAny(T)`\-Methode definiert.  Die `ReceiveFromAny(T)`\-Methode akzeptiert ein Array Objekte <xref:System.Threading.Tasks.Dataflow.ISourceBlock%601> und verknüpft jedes dieser Objekte einem <xref:System.Threading.Tasks.Dataflow.WriteOnceBlock%601>\-Objekt.  Wenn Sie die <xref:System.Threading.Tasks.Dataflow.ISourceBlock%601.LinkTo%2A> methode verwenden, um einen Quelldatenflussblock einem Zielblock zu verknüpfen, die weitergegeben Quelle Meldungen zum Ziel, während Daten verfügbar werden.  Da die <xref:System.Threading.Tasks.Dataflow.WriteOnceBlock%601>\-Klasse nur die erste Nachricht akzeptiert, dass sie bereitgestellt wird, stellt die `ReceiveFromAny(T)`\-Methode sein Ergebnis, indem sie die <xref:System.Threading.Tasks.Dataflow.DataflowBlock.Receive%2A>\-Methode aufruft.  Dadurch wird die erste Nachricht, die vor dem <xref:System.Threading.Tasks.Dataflow.WriteOnceBlock%601>\-Objekt bereitgestellt wird.  Die <xref:System.Threading.Tasks.Dataflow.ISourceBlock%601.LinkTo%2A> methode hat eine überladene Version, die einen <xref:System.Boolean> akzeptiert Parameter, `unlinkAfterOne`, die, wenn er auf `True` festgelegt wird, den Quell\- anweist, um vom Ziel zu lösen, wenn das Ziel eine Meldung von der Quelle empfängt.  Es ist wichtig das <xref:System.Threading.Tasks.Dataflow.WriteOnceBlock%601>\-Objekt, aus den Quellen zu beheben, da die Beziehung zwischen dem Array von Quellen und dem <xref:System.Threading.Tasks.Dataflow.WriteOnceBlock%601>\-Objekt nicht mehr benötigt wird, nachdem das <xref:System.Threading.Tasks.Dataflow.WriteOnceBlock%601>\-Objekt eine Meldung empfängt.  
  
 So die verbleibenden Aufrufe `TrySolution` aktivieren, um zu beenden, nachdem eine davon Berechnungen ein Wert, die `TrySolution`\-Methode ein <xref:System.Threading.CancellationToken>\-Objekt akzeptiert, das abgebrochen wird, nachdem der Aufruf von `ReceiveFromAny(T)` zurückkehrt.  Die <xref:System.Threading.SpinWait.SpinUntil%2A>\-Methode wird zurückgegeben, wenn <xref:System.Threading.CancellationToken>\-Objekt abgebrochen wird.  
  
## Kompilieren des Codes  
 Kopieren Sie den Beispielcode und fügen Sie ihn in ein Visual Studio\-Projekt ein, oder fügen Sie ihn in eine Datei, die `DataflowReceiveAny.cs` \(`DataflowReceiveAny.vb` für [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)]\) trägt, und dann ausgeführt wird den folgenden Befehl in einem Visual Studio\-Eingabeaufforderungsfenster.  
  
 [!INCLUDE[csprcs](../../../includes/csprcs-md.md)]  
  
 **csc.exe \/r:System.Threading.Tasks.Dataflow.dll DataflowReceiveAny.cs**  
  
 [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)]  
  
 **vbc.exe \/r:System.Threading.Tasks.Dataflow.dll DataflowReceiveAny.vb**  
  
## Robuste Programmierung  
  
## Siehe auch  
 [Datenfluss](../../../docs/standard/parallel-programming/dataflow-task-parallel-library.md)