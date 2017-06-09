---
title: "How to: Cancel a Dataflow Block | Microsoft Docs"
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
  - "dataflow blocks, canceling in TPL"
  - "TPL dataflow library,canceling dataflow blocks"
ms.assetid: fbddda0d-da3b-4ec8-a1d6-67ab8573fcd7
caps.latest.revision: 9
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 7
---
# How to: Cancel a Dataflow Block
Dieses Dokument veranschaulicht, wie Abbrüche in der Anwendung aktiviert.  Dieses Beispiel verwendet Windows Forms, um zu verdeutlichen, wo Arbeitsaufgaben in einer Datenflusspipeline und auch in die Auswirkungen des Abbruchs aktiv sind.  
  
> [!TIP]
>  Die TPL\-Datenflussbibliothek \(<xref:System.Threading.Tasks.Dataflow?displayProperty=fullName>\-Namespace\) ist nicht in [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] enthalten.  Öffnen Sie zum Installieren des <xref:System.Threading.Tasks.Dataflow>\-Namespace das Projekt in [!INCLUDE[vs_dev11_long](../../../includes/vs-dev11-long-md.md)], wählen Sie im Menü "Projekt" die Option **NuGet\-Pakete verwalten** aus, und suchen Sie online nach dem `Microsoft.Tpl.Dataflow`\-Paket.  
  
### So fügen Sie die Windows Forms\-Anwendung erstellen  
  
1.  Erstellen Sie ein Projekt C\# oder Visual Basic **Windows Forms\-Anwendung**.  In den folgenden Schritten wird das Projekt `CancellationWinForms`.  
  
2.  Klicken Sie im Formular\-Designer zum Hauptformular fügen Form1.vb, Form1.cs \(für [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)]\), ein <xref:System.Windows.Forms.ToolStrip>\-Steuerelement hinzu.  
  
3.  Fügen Sie ein <xref:System.Windows.Forms.ToolStripButton>\-Steuerelement dem <xref:System.Windows.Forms.ToolStrip>\-Steuerelement hinzu.  Legen Sie die Eigenschaft <xref:System.Windows.Forms.ToolStripItem.DisplayStyle%2A> auf <xref:System.Windows.Forms.ToolStripItemDisplayStyle> und die Eigenschaft <xref:System.Windows.Forms.ToolStripItem.Text%2A> fest, um Arbeitsaufgaben hinzuzufügen.  
  
4.  Fügen Sie ein <xref:System.Windows.Forms.ToolStripButton>\-Steuerelement Sekunden das <xref:System.Windows.Forms.ToolStrip>\-Steuerelement hinzu.  Legen Sie die Eigenschaft <xref:System.Windows.Forms.ToolStripItem.DisplayStyle%2A> auf <xref:System.Windows.Forms.ToolStripItemDisplayStyle>, die <xref:System.Windows.Forms.ToolStripItem.Text%2A>\-Eigenschaft auf Abbrechen und die Eigenschaft <xref:System.Windows.Forms.ToolStripItem.Enabled%2A> auf `False` fest.  
  
5.  Fügen Sie vier <xref:> System.Windows.Forms.ToolStripProgressBar?qualifyHint=False&autoUpgrade=True\-Objekten zum <xref:System.Windows.Forms.ToolStrip>\-Steuerelement hinzu.  
  
## Erstellen der Datenfluss\-Pipeline  
 Dieser Abschnitt beschreibt, wie die Datenflusspipeline erstellt, die Arbeitsaufgaben und verarbeitet die Statusanzeigen aktualisiert.  
  
#### Um die Datenfluss\-Pipeline erstellen  
  
1.  In Fügen Sie im Projekt einen Verweis auf System.Threading.Tasks.Dataflow.dll hinzu.  
  
2.  Stellen Sie sicher, dass Form1.cs Form1.vb \(für [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)]\) die folgenden `using`\-Anweisungen \(`Imports` in [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)]\) enthält.  
  
     [!code-csharp[TPLDataflow_CancellationWinForms#1](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_cancellationwinforms/cs/cancellationwinforms/form1.cs#1)]
     [!code-vb[TPLDataflow_CancellationWinForms#1](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_cancellationwinforms/vb/cancellationwinforms/form1.vb#1)]  
  
3.  Fügen Sie der `WorkItem`\-Klasse als innerer Typ `Form1`\-Klasse hinzu.  
  
     [!code-csharp[TPLDataflow_CancellationWinForms#2](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_cancellationwinforms/cs/cancellationwinforms/form1.cs#2)]
     [!code-vb[TPLDataflow_CancellationWinForms#2](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_cancellationwinforms/vb/cancellationwinforms/form1.vb#2)]  
  
4.  Fügen Sie der `Form1`\-Klasse die folgenden Datenmember hinzu.  
  
     [!code-csharp[TPLDataflow_CancellationWinForms#3](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_cancellationwinforms/cs/cancellationwinforms/form1.cs#3)]
     [!code-vb[TPLDataflow_CancellationWinForms#3](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_cancellationwinforms/vb/cancellationwinforms/form1.vb#3)]  
  
5.  Fügen Sie die folgende Methode, `CreatePipeline`, der `Form1`\-Klasse hinzu.  
  
     [!code-csharp[TPLDataflow_CancellationWinForms#4](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_cancellationwinforms/cs/cancellationwinforms/form1.cs#4)]
     [!code-vb[TPLDataflow_CancellationWinForms#4](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_cancellationwinforms/vb/cancellationwinforms/form1.vb#4)]  
  
 Da die `incrementProgress` und `decrementProgress` Datenflussblöcke nach der Benutzeroberfläche handeln, ist es wichtig, dass diese Aktionen auf dem Benutzeroberflächenthread auftreten.  Um dieses, während der Konstruktion Zweck liefern diese Objekte jedes ein <xref:System.Threading.Tasks.Dataflow.ExecutionDataflowBlockOptions>\-Objekt das den <xref:System.Threading.Tasks.Dataflow.DataflowBlockOptions.TaskScheduler%2A>\-Eigenschaft auf <xref:System.Threading.Tasks.TaskScheduler.FromCurrentSynchronizationContext%2A?displayProperty=fullName> festgelegt ist.  Die <xref:System.Threading.Tasks.TaskScheduler.FromCurrentSynchronizationContext%2A?displayProperty=fullName>\-Methode erstellt ein <xref:System.Threading.Tasks.TaskScheduler>\-Objekt, das Aufgaben im aktuellen Synchronisierungskontext ausführt.  Da der `Form1`\-Konstruktor aus dem Benutzeroberflächenthread aufgerufen wird, werden die Aktionen für die `incrementProgress` und `decrementProgress` Datenflussblöcke auch für den Benutzeroberflächenthread ausgeführt.  
  
 In diesem Beispiel wird die Eigenschaft <xref:System.Threading.Tasks.Dataflow.DataflowBlockOptions.CancellationToken%2A> fest, wenn die Member der Pipeline erstellt.  Da die <xref:System.Threading.Tasks.Dataflow.DataflowBlockOptions.CancellationToken%2A>\-Eigenschaft Datenflussblocksausführung dauerhaft abbricht, muss die Ganzpipeline neu erstellt werden, nachdem der Benutzer den Vorgang abbricht und dann weitere Arbeitsaufgaben der Pipeline hinzufügen möchte.  Ein Beispiel dafür eine alternative Möglichkeit, einen Datenflussblock abzubrechen, damit andere Arbeit ausgeführt werden kann, nachdem ein Vorgang abgebrochen wird, finden Sie unter [Walkthrough: Using Dataflow in a Windows Forms Application](../../../docs/standard/parallel-programming/walkthrough-using-dataflow-in-a-windows-forms-application.md).  
  
## Verbindung der Datenfluss\-Pipeline an die Benutzeroberfläche  
 Dieser Abschnitt beschreibt, wie die Datenflusspipeline an die Benutzeroberfläche herstellt.  , die Pipeline erstellen und Arbeitsaufgaben der Pipeline hinzufügen, werden im Ereignishandler für die Hinzufügens\-Arbeitsaufgabenschaltfläche gesteuert.  Abbruch wird durch die Abbruchschaltfläche initiiert.  Wenn der Benutzer auf eine dieser Schaltflächen klickt, werden die entsprechenden Schritte in einer asynchronen Art initiiert.  
  
#### Um die Datenfluss\-Pipeline an die Benutzeroberfläche herstellen  
  
1.  Klicken Sie im Formular\-Designer zum Hauptformular, erstellen Sie einen Ereignishandler für das <xref:System.Windows.Forms.ToolStripItem.Click>\-Ereignis für die Hinzufügens\-Arbeitsaufgabenschaltfläche erstellt.  
  
2.  Implementieren Sie das <xref:System.Windows.Forms.ToolStripItem.Click>\-Ereignis für die Hinzufügens\-Arbeitsaufgabenschaltfläche.  
  
     [!code-csharp[TPLDataflow_CancellationWinForms#5](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_cancellationwinforms/cs/cancellationwinforms/form1.cs#5)]
     [!code-vb[TPLDataflow_CancellationWinForms#5](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_cancellationwinforms/vb/cancellationwinforms/form1.vb#5)]  
  
3.  Klicken Sie im Formular\-Designer zum Hauptformular, erstellen Sie einen Ereignishandler für den <xref:System.Windows.Forms.ToolStripItem.Click>\-Ereignishandler für die Schaltfläche Abbrechen erstellt.  
  
4.  Implementieren Sie den <xref:System.Windows.Forms.ToolStripItem.Click>\-Ereignishandler für die Schaltfläche Abbrechen.  
  
     [!code-csharp[TPLDataflow_CancellationWinForms#6](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_cancellationwinforms/cs/cancellationwinforms/form1.cs#6)]
     [!code-vb[TPLDataflow_CancellationWinForms#6](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_cancellationwinforms/vb/cancellationwinforms/form1.vb#6)]  
  
## Beispiel  
 Im folgenden Beispiel wird der vollständige Code für Form1.cs an \(Form1.vb für [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)]\).  
  
 [!code-csharp[TPLDataflow_CancellationWinForms#100](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_cancellationwinforms/cs/cancellationwinforms/form1.cs#100)]
 [!code-vb[TPLDataflow_CancellationWinForms#100](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_cancellationwinforms/vb/cancellationwinforms/form1.vb#100)]  
  
 Die folgende Abbildung zeigt die ausgeführte Anwendung.  
  
 ![Die Windows Forms&#45;Anwendung](../../../docs/standard/parallel-programming/media/tpldataflow-cancellation.png "TPLDataflow\_Cancellation")  
  
## Robuste Programmierung  
  
## Siehe auch  
 [Datenfluss](../../../docs/standard/parallel-programming/dataflow-task-parallel-library.md)