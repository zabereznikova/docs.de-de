---
title: "How to: Use JoinBlock to Read Data From Multiple Sources | Microsoft Docs"
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
  - "Task Parallel Library, dataflows"
  - "TPL dataflow library, joining blocks in"
  - "dataflow blocks, joining in TPL"
ms.assetid: e9c1ada4-ac57-4704-87cb-2f5117f8151d
caps.latest.revision: 7
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 7
---
# How to: Use JoinBlock to Read Data From Multiple Sources
In diesem Dokument wird erläutert, wie die <xref:System.Threading.Tasks.Dataflow.JoinBlock%602>\-Klasse verwendet, um eine Operation auszuführen, Daten aus mehreren Quellen verfügbar sind.  Außerdem wird veranschaulicht, wie nicht gierigen Modus verwendet wird, um mehrere Joinblöcke zu ermöglichen, eine Datenquelle effizienter freizugeben.  
  
> [!TIP]
>  Die TPL\-Datenflussbibliothek \(<xref:System.Threading.Tasks.Dataflow?displayProperty=fullName>\-Namespace\) ist nicht in [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] enthalten.  Öffnen Sie zum Installieren des <xref:System.Threading.Tasks.Dataflow>\-Namespace das Projekt in [!INCLUDE[vs_dev11_long](../../../includes/vs-dev11-long-md.md)], wählen Sie im Menü "Projekt" die Option **NuGet\-Pakete verwalten** aus, und suchen Sie online nach dem `Microsoft.Tpl.Dataflow`\-Paket.  
  
## Beispiel  
 Das folgende Beispiel definiert drei Ressourcentypen, `NetworkResource`, `FileResource` und `MemoryResource` und scrollt Vorgänge aus, wenn Ressourcen verfügbar sind.  Dieses Beispiel erfordert ein Paar `NetworkResource` und `MemoryResource`, um den ersten Vorgang und ein `FileResource` und `MemoryResource` auszuführen Paar, den zweiten Vorgang auszuführen.  Um diese Operationen ermöglichen, fungiert, wenn alle erforderlichen Ressourcen verfügbar sind, verwenden dieses Beispiels die Klasse <xref:System.Threading.Tasks.Dataflow.JoinBlock%602>.  Wenn ein <xref:System.Threading.Tasks.Dataflow.JoinBlock%602>\-Objekt Daten aller Quellen empfängt, überträgt diese Daten an das Ziel, in diesem Beispiel ein <xref:System.Threading.Tasks.Dataflow.ActionBlock%601>\-Objekt ist.  Lesen beider <xref:System.Threading.Tasks.Dataflow.JoinBlock%602>\-Objekte über einen gemeinsamen Pool von `MemoryResource`\-Objekten.  
  
 [!code-csharp[TPLDataflow_NonGreedyJoin#1](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_nongreedyjoin/cs/nongreedyjoin.cs#1)]
 [!code-vb[TPLDataflow_NonGreedyJoin#1](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_nongreedyjoin/vb/nongreedyjoin.vb#1)]  
  
 Um effizienten Verwendung des gemeinsamen Pool von `MemoryResource`\-Objekten zu aktivieren, gibt dieses Beispiel ein <xref:System.Threading.Tasks.Dataflow.GroupingDataflowBlockOptions>\-Objekt an das die <xref:System.Threading.Tasks.Dataflow.GroupingDataflowBlockOptions.Greedy%2A>\-Eigenschaft auf `False` festgelegt ist um <xref:System.Threading.Tasks.Dataflow.JoinBlock%602>\-Objekten erstellen die in nicht gierigen Modus reagieren.  Ein nicht gieriger Joinblock schiebt alle eingehenden Nachrichten verschoben, bis eines von jeder Quelle verfügbar ist.  Wenn eine der hinausgeschobenen Meldungen wurden von einem anderen Block, die Joinblocksneustarts der Prozess akzeptiert.  Nicht gieriger Modus ermöglicht Joinblöcke, die eine oder mehrere Quellblöcken freigeben, um Fortschritte als andere Blöcke zu machen Daten warten.  In diesem Beispiel ein `MemoryResource`\-Objekt dem `memoryResources` Pool hinzugefügt wird, kann der erste Joinblock, um der zweiten Datenquelle zu empfangen Fortschritte machen.  Wenn dieses Beispiel, gierigen Modus verwenden waren, Standard, wartet möglicherweise ein Joinblock das `MemoryResource`\-Objekt erstellen und auf der zweiten Ressource, die verfügbar wird.  Wenn der Joinblock andere seine verfügbare zweite Datenquelle verfügt, kann er Fortschritt nicht ausführen, da das `MemoryResource`\-Objekt vom anderen Joinblock erstellt wurde.  
  
## Kompilieren des Codes  
 Kopieren Sie den Beispielcode und fügen Sie ihn in ein Visual Studio\-Projekt ein, oder fügen Sie ihn in eine Datei, die `DataflowNonGreedyJoin.cs` \(`DataflowNonGreedyJoin.vb` für [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)]\) trägt, und dann ausgeführt wird den folgenden Befehl in einem Visual Studio\-Eingabeaufforderungsfenster.  
  
 [!INCLUDE[csprcs](../../../includes/csprcs-md.md)]  
  
 **csc.exe \/r:System.Threading.Tasks.Dataflow.dll DataflowNonGreedyJoin.cs**  
  
 [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)]  
  
 **vbc.exe \/r:System.Threading.Tasks.Dataflow.dll DataflowNonGreedyJoin.vb**  
  
## Robuste Programmierung  
 Der Verwendung nicht gieriger Joins können Sie auch leichter, Deadlocks in der Anwendung verhindern.  In einer Softwareanwendung tritt ein *Deadlock* auf, wenn mindestens zwei Prozesse jeweils über eine Ressource verfügen und warten, bis von einem anderen Prozess eine weitere Ressource freigegeben wird.  Nehmen Sie eine Anwendung, die zwei <xref:System.Threading.Tasks.Dataflow.JoinBlock%602>\-Objekte definiert.  Beide Objekte jede statt von zwei angegebenen Quellblöcken frei.  Im Modus gierigen wenn ein Joinblock aus der ersten Quelle liest und der zweite Joinblock vom Zweitlieferanten liest, dass die Anwendung möglicherweise einen Deadlock, da beide Blöcken warten gegenseitig auf den anderen, um die Ressourcen freizugeben verknüpfen.  Im Modus nicht gierigen liest jeder Joinblock aus den Quellen, wenn alle Daten verfügbar sind, und daher, wird das Risiko von Deadlocks beseitigt.  
  
## Siehe auch  
 [Datenfluss](../../../docs/standard/parallel-programming/dataflow-task-parallel-library.md)