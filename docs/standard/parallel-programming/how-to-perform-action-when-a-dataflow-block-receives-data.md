---
title: "How to: Perform Action When a Dataflow Block Receives Data | Microsoft Docs"
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
  - "TPL dataflow library, receiving data"
ms.assetid: fc2585dc-965e-4632-ace7-73dd02684ed3
caps.latest.revision: 11
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 11
---
# How to: Perform Action When a Dataflow Block Receives Data
*Ausführungsdatenfluss\-Blocks* typen rufen einen vom Benutzer bereitgestellten Delegaten auf, wenn sie Daten empfangen.  <xref:System.Threading.Tasks.Dataflow.ActionBlock%601?displayProperty=fullName>, <xref:System.Threading.Tasks.Dataflow.TransformBlock%602?displayProperty=fullName> und <xref:System.Threading.Tasks.Dataflow.TransformManyBlock%602?displayProperty=fullName>\-Klassen sind Ausführungsdatenfluss\-Blockstypen.  Sie können das Schlüsselwort `delegate` \(`Sub` in [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)]\), <xref:System.Action%601>, <xref:System.Func%602> oder einen Lambda\-Ausdruck verwenden, um eine Arbeitsfunktion an einem Ausführungsdatenflussblock bereitstellen.  In diesem Dokument wird beschrieben, wie <xref:System.Func%602> und Lambda\-Ausdrücke verwendet, um in den Ausführungsblöcken Aktion auszuführen.  
  
> [!TIP]
>  Die TPL\-Datenflussbibliothek \(<xref:System.Threading.Tasks.Dataflow?displayProperty=fullName>\-Namespace\) ist nicht in [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] enthalten.  Öffnen Sie zum Installieren des <xref:System.Threading.Tasks.Dataflow>\-Namespace das Projekt in [!INCLUDE[vs_dev11_long](../../../includes/vs-dev11-long-md.md)], wählen Sie im Menü "Projekt" die Option **NuGet\-Pakete verwalten** aus, und suchen Sie online nach dem `Microsoft.Tpl.Dataflow`\-Paket.  
  
## Beispiel  
 Im folgenden Beispiel verwendet Datenfluss, um eine Datei von der Festplatte lesen und berechnet die Anzahl Bytes in der Datei, die gleich Null sind.  Es wird <xref:System.Threading.Tasks.Dataflow.TransformBlock%602> verwendet, um die Datei zu lesen und die Anzahl von nullbytes ableiten und <xref:System.Threading.Tasks.Dataflow.ActionBlock%601>, um die Anzahl von nullbytes auf der Konsole auszugeben.  Das Objekt <xref:System.Threading.Tasks.Dataflow.TransformBlock%602> gibt ein <xref:System.Func%602>\-Objekt, um Arbeit auszuführen, wenn die Blöcke Daten empfangen.  Das <xref:System.Threading.Tasks.Dataflow.ActionBlock%601>\-Objekt verwendet einen Lambda\-Ausdruck, um der Konsole die Anzahl von nullbytes zu drucken, die verwendet werden.  
  
 [!code-csharp[TPLDataflow_ExecutionBlocks#1](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_executionblocks/cs/dataflowexecutionblocks.cs#1)]
 [!code-vb[TPLDataflow_ExecutionBlocks#1](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_executionblocks/vb/dataflowexecutionblocks.vb#1)]  
  
 Obwohl Sie einen Lambda\-Ausdruck an ein <xref:System.Threading.Tasks.Dataflow.TransformBlock%602>\-Objekt bereitstellen können, dem <xref:System.Func%602> dieses Beispiels, anderen Code zu aktivieren, um die `CountBytes`\-Methode zu verwenden.  Das <xref:System.Threading.Tasks.Dataflow.ActionBlock%601>\-Objekt verwendet einen Lambda\-Ausdruck, da die auszuführende Arbeit zu dieser Aufgabe festgelegt ist und nicht wahrscheinlich, von anderem Code hilfreich.  Weitere Informationen dazu, wie Sie Lambda\-Ausdrücke in der Task Parallel Library arbeiten, finden Sie unter [Lambda Expressions in PLINQ and TPL](../../../docs/standard/parallel-programming/lambda-expressions-in-plinq-and-tpl.md).  
  
 Die Zusammenfassung von Abschnitt Delegattypen im Dokument [Datenfluss](../../../docs/standard/parallel-programming/dataflow-task-parallel-library.md) werden die Delegattypen zusammengefasst, die Sie in <xref:System.Threading.Tasks.Dataflow.ActionBlock%601>, <xref:System.Threading.Tasks.Dataflow.TransformBlock%602> und zu <xref:System.Threading.Tasks.Dataflow.TransformManyBlock%602>\-Objekten bereitstellen können.  Die Tabelle gibt auch an, ob der Delegattyp synchron oder asynchron funktioniert.  
  
## Kompilieren des Codes  
 Kopieren Sie den Beispielcode und fügen Sie ihn in ein Visual Studio\-Projekt ein, oder fügen Sie ihn in eine Datei, die `DataflowExecutionBlocks.cs` \(`DataflowExecutionBlocks.vb` für [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)]\) trägt, und dann ausgeführt wird den folgenden Befehl in einem Visual Studio\-Eingabeaufforderungsfenster.  
  
 [!INCLUDE[csprcs](../../../includes/csprcs-md.md)]  
  
 **csc.exe \/r:System.Threading.Tasks.Dataflow.dll DataflowExecutionBlocks.cs**  
  
 [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)]  
  
 **vbc.exe \/r:System.Threading.Tasks.Dataflow.dll DataflowExecutionBlocks.vb**  
  
## Robuste Programmierung  
 Dieses Beispiel stellt einen Delegaten vom Typ <xref:System.Func%602> z <xref:System.Threading.Tasks.Dataflow.TransformBlock%602>\-Objekt bereit, um die Aufgabe des Datenflussblocks synchron auszuführen.  Um den Datenflussblock sich asynchron zu verhalten, erstellen Sie einen Delegaten vom Typ <xref:System.Func%601> zum Datenflussblock bereit.  Wenn ein Datenflussblock sich asynchron verhält, ist die Aufgabe des Datenflussblocks nur dann abgeschlossen, wenn das zurückgegebene <xref:System.Threading.Tasks.Task%601>\-Objekt beendet.  Im folgenden Beispiel ändert die `CountBytes`\-Methode und verwendet [asynchron](../Topic/async%20\(C%23%20Reference\).md) und [Sie erwarten](../Topic/await%20\(C%23%20Reference\).md)\-Operatoren \([Asynchrone](../Topic/Async%20\(Visual%20Basic\).md) und [Rechnen Sie](../Topic/Await%20Operator%20\(Visual%20Basic\).md) in [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)]\) auf die Gesamtzahl der Bytes asynchron zu berechnen, die sind, stellen in die bereitgestellte Datei auf Null ein.  Die <xref:System.IO.FileStream.ReadAsync%2A>\-Methode führt Dateilesevorgänge asynchron ausgeführt.  
  
 [!code-csharp[TPLDataflow_ExecutionBlocks#2](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_executionblocks/cs/dataflowexecutionblocks.cs#2)]
 [!code-vb[TPLDataflow_ExecutionBlocks#2](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_executionblocks/vb/dataflowexecutionblocks.vb#2)]  
  
 Sie können asynchrone Lambda\-Ausdrücke auch verwenden, um in einem Ausführungsdatenflussblock Aktion auszuführen.  Im folgenden Beispiel ändert das <xref:System.Threading.Tasks.Dataflow.TransformBlock%602>\-Objekt, das im vorherigen Beispiel verwendet wird, sodass einem Lambda\-Ausdruck verwendet, um die Arbeit asynchron auszuführen.  
  
 [!code-csharp[TPLDataflow_ExecutionBlocks#3](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_executionblocks/cs/dataflowexecutionblocks.cs#3)]
 [!code-vb[TPLDataflow_ExecutionBlocks#3](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_executionblocks/vb/dataflowexecutionblocks.vb#3)]  
  
## Siehe auch  
 [Datenfluss](../../../docs/standard/parallel-programming/dataflow-task-parallel-library.md)