---
title: "Walkthrough: Creating a Custom Dataflow Block Type | Microsoft Docs"
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
  - "TPL dataflow library, creating custom dataflow blocks"
  - "dataflow blocks, creating custom in TPL"
ms.assetid: a6147146-0a6a-4d9b-ab0f-237b3c1ac691
caps.latest.revision: 8
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 8
---
# Walkthrough: Creating a Custom Dataflow Block Type
Obwohl die TPL\-Datenfluss\-Bibliothek einige Datenflussblockstypen bereitstellt, die eine Vielzahl von Funktionen aktivieren, können Sie benutzerdefinierte Blockstypen auch erstellen.  Dieses Dokument beschreibt, wie einen Datenfluss Nachrichtenblocktyp erstellt, der benutzerdefinierte Verhalten implementiert.  
  
## Vorbereitungsmaßnahmen  
 Lesen [Datenfluss](../../../docs/standard/parallel-programming/dataflow-task-parallel-library.md), bevor Sie dieses Dokument lesen.  
  
> [!TIP]
>  Die TPL\-Datenflussbibliothek \(<xref:System.Threading.Tasks.Dataflow?displayProperty=fullName>\-Namespace\) ist nicht in [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] enthalten.  Öffnen Sie zum Installieren des <xref:System.Threading.Tasks.Dataflow>\-Namespace das Projekt in [!INCLUDE[vs_dev11_long](../../../includes/vs-dev11-long-md.md)], wählen Sie im Menü "Projekt" die Option **NuGet\-Pakete verwalten** aus, und suchen Sie online nach dem `Microsoft.Tpl.Dataflow`\-Paket.  
  
## Definieren des Datenfluss\-Blocks gleitenden des Fensters  
 Erwägen Sie eine Datenfluss\-Anwendung, die erfordert, dass Eingabewerte gepuffert werden und dann in einer Art des Fensters gleitenden ausgeben.  Beispielsweise für die Eingabewerte {0, 1, 2, 3, 4, 5} und eine von Fenstergröße drei, erzeugt ein Datenflussblock gleitenden des Fensters die Ausgabearrays {0, 1, 2}, {1, 2, 3}, {2, 3, 4}, {und 3, 4, 5}.  In den folgenden Abschnitten werden zwei Möglichkeiten, einen eigenen Datenfluss zu erstellen, der diesem benutzerdefinierten Verhalten implementiert.  Die erste Methode verwendet die <xref:System.Threading.Tasks.Dataflow.DataflowBlock.Encapsulate%2A> methode, um die Funktionalität eines <xref:System.Threading.Tasks.Dataflow.ISourceBlock%601>\-Objekts und des <xref:System.Threading.Tasks.Dataflow.ITargetBlock%601>\-Objekts in einen Weitergabeblock zu kombinieren.  Die zweite Methode definiert eine Klasse, die von <xref:System.Threading.Tasks.Dataflow.IPropagatorBlock%602> abgeleitet und vorhandene Funktionen kombiniert, um benutzerdefiniertes Verhalten auszuführen.  
  
## Verwenden der kapselns\-Methode, um den Datenfluss\-Blocks gleitenden des Fensters definieren  
 Im folgenden Beispiel wird die <xref:System.Threading.Tasks.Dataflow.DataflowBlock.Encapsulate%2A> methode, um einen Weitergabeblock eines Ziels und von einer Quelle zu erstellen.  Ein Weitergabeblock aktiviert Verknüpfung eines Quellnachrichtenblocks und einem Zielblock, um als Empfänger und ein Absender von Daten fungiert.  
  
 Diese Methode ist hilfreich, wenn Sie benutzerdefinierte Datenflussfunktionalität benötigen, aber Sie keinen Typ benötigen, der zusätzliche Methoden, Eigenschaften oder Felder bietet.  
  
 [!code-csharp[TPLDataflow_SlidingWindowBlock#1](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_slidingwindowblock/cs/slidingwindowblock.cs#1)]
 [!code-vb[TPLDataflow_SlidingWindowBlock#1](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_slidingwindowblock/vb/slidingwindowblock.vb#1)]  
  
## Ableiten von IPropagatorBlock, um den Datenfluss\-Blocks gleitenden des Fensters definieren  
 Das folgende Beispiel zeigt die `SlidingWindowBlock`\-Klasse.  Diese Klasse wird von <xref:System.Threading.Tasks.Dataflow.IPropagatorBlock%602>, sodass diese als Datenquelle und ein Ziel von Daten auftreten kann.  Wie im vorherigen Beispiel, wird die Klasse `SlidingWindowBlock` auf vorhandenen Datenflussblockstypen erstellt.  Allerdings implementiert die `SlidingWindowBlock`\-Klasse auch Methoden, die von <xref:System.Threading.Tasks.Dataflow.ISourceBlock%601>, <xref:System.Threading.Tasks.Dataflow.ITargetBlock%601> und <xref:System.Threading.Tasks.Dataflow.IDataflowBlock>\-Schnittstellen benötigt werden.  Diese Arbeit leiten alle Methoden an die Blockformatmember des vordefinierten Datenflusses weiter.  Beispielsweise überträgt die `Post`\-Methode Arbeiten am `m_target` Datenmember, der auch ein <xref:System.Threading.Tasks.Dataflow.ITargetBlock%601>\-Objekt ist.  
  
 Diese Methode ist hilfreich, wenn Sie benutzerdefinierte Datenflussfunktionalität benötigen, und erfordert auch einen Typ, der zusätzliche Methoden, Eigenschaften oder Felder bietet.  Beispielsweise berechnet die `SlidingWindowBlock`\-Klasse auch von <xref:System.Threading.Tasks.Dataflow.IReceivableSourceBlock%601>, sodass die <xref:System.Threading.Tasks.Dataflow.IReceivableSourceBlock%601.TryReceive%2A> und <xref:System.Threading.Tasks.Dataflow.IReceivableSourceBlock%601.TryReceiveAll%2A>\-Methoden bereitstellen kann.  Die `SlidingWindowBlock`\-Klasse wird auch Erweiterbarkeit, mithilfe der `WindowSize`\-Eigenschaft bereitstellt, die die Anzahl der Elemente im gleitende Fenster abrufen.  
  
 [!code-csharp[TPLDataflow_SlidingWindowBlock#2](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_slidingwindowblock/cs/slidingwindowblock.cs#2)]
 [!code-vb[TPLDataflow_SlidingWindowBlock#2](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_slidingwindowblock/vb/slidingwindowblock.vb#2)]  
  
## Vollständiges Beispiel  
 Im folgenden Beispiel wird der vollständige Code für diese exemplarische Vorgehensweise angezeigt.  Es zeigt auch, wie die Blöcke des gleitenden Fensters in einer Methode verwendet, die auf den Block schreibt, davon liest und die Ergebnisse an die Konsole ausgibt.  
  
 [!code-csharp[TPLDataflow_SlidingWindowBlock#100](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_slidingwindowblock/cs/slidingwindowblock.cs#100)]
 [!code-vb[TPLDataflow_SlidingWindowBlock#100](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_slidingwindowblock/vb/slidingwindowblock.vb#100)]  
  
## Kompilieren des Codes  
 Kopieren Sie den Beispielcode und fügen Sie ihn in ein Visual Studio\-Projekt ein, oder fügen Sie ihn in eine Datei, die `SlidingWindowBlock.cs` \(`SlidingWindowBlock.vb` für [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)]\) trägt und dann folgenden Befehl in einem Visual Studio\-Eingabeaufforderung ausgeführt.  
  
 [!INCLUDE[csprcs](../../../includes/csprcs-md.md)]  
  
 **csc.exe \/r:System.Threading.Tasks.Dataflow.dll SlidingWindowBlock.cs**  
  
 [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)]  
  
 **vbc.exe \/r:System.Threading.Tasks.Dataflow.dll SlidingWindowBlock.vb**  
  
## Nächste Schritte  
  
## Siehe auch  
 [Datenfluss](../../../docs/standard/parallel-programming/dataflow-task-parallel-library.md)