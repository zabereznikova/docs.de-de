---
title: 'Exemplarische Vorgehensweise: Datenfluss in einer Windows Forms-Anwendung verwenden'
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- TPL dataflow library, in Windows Forms
- Task Parallel Library, dataflows
- Windows Forms, and TPL
ms.assetid: 9c65cdf7-660c-409f-89ea-59d7ec8e127c
ms.openlocfilehash: 794253514edf63f02276e1ece21c60a85c534390
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/15/2020
ms.locfileid: "78159766"
---
# <a name="walkthrough-using-dataflow-in-a-windows-forms-application"></a>Exemplarische Vorgehensweise: Datenfluss in einer Windows Forms-Anwendung verwenden
Dieses Dokument veranschaulicht, wie ein Netzwerk von Datenflussblöcken erstellt wird, die eine Bildverarbeitung in einer Windows Forms-Anwendung durchführen.  
  
 In diesem Beispiel werden Bilddateien aus dem angegebenen Ordner geladen, es wird ein zusammengesetztes Bild erstellt und das Ergebnis wird angezeigt. Im Beispiel wird das Datenflussmodell verwendet, um Bilder durch das Netzwerk zu leiten. Im Datenflussmodell kommunizieren unabhängige Komponenten eines Programms durch Senden von Nachrichten miteinander. Wenn eine Komponente eine Nachricht empfängt, führt sie eine Aktion aus und übergibt dann das Ergebnis an eine andere Komponente. Dies ist vergleichbar mit dem Ablaufsteuerungsmodell, in dem eine Anwendung Steuerungsstrukturen wie bedingte Anweisungen, Schleifen usw.verwendet, um die Reihenfolge der Vorgänge in einem Programm zu steuern.  
  
## <a name="prerequisites"></a>Voraussetzungen  
 Lesen Sie das Thema [Datenfluss](../../../docs/standard/parallel-programming/dataflow-task-parallel-library.md), bevor Sie mit dieser exemplarischen Vorgehensweise beginnen.  

[!INCLUDE [tpl-install-instructions](../../../includes/tpl-install-instructions.md)]

## <a name="sections"></a>Abschnitte  
 Diese exemplarische Vorgehensweise enthält folgende Abschnitte:  
  
- [Erstellen der Windows Forms-Anwendung](#winforms)  
  
- [Erstellen des Datenflussnetzwerks](#network)  
  
- [Verbinden des Datenflussnetzwerks mit der Benutzeroberfläche](#ui)  
  
- [Vollständiges Beispiel](#complete)  
  
<a name="winforms"></a>
## <a name="creating-the-windows-forms-application"></a>Erstellen der Windows Forms-Anwendung  
 In diesem Abschnitt wird beschrieben, wie Sie die grundlegende Windows Forms-Anwendung erstellen und Steuerelemente zum Hauptformular hinzufügen.  
  
### <a name="to-create-the-windows-forms-application"></a>Erstellen der Windows Forms-Anwendung  
  
1. Erstellen Sie in Visual Studio ein Visual C#- oder Visual Basic-Projekt des Typs **Windows Forms-Anwendung**. In diesem Dokument hat das Projekt den Namen `CompositeImages`.  
  
2. Fügen Sie im Formulardesigner für das Hauptformular „Form1.cs“ („Form1.vb“ in Visual Basic) ein <xref:System.Windows.Forms.ToolStrip>-Steuerelement hinzu.  
  
3. Fügen Sie dem <xref:System.Windows.Forms.ToolStrip>-Steuerelement ein <xref:System.Windows.Forms.ToolStripButton>-Steuerelement hinzu. Legen Sie die <xref:System.Windows.Forms.ToolStripItem.DisplayStyle%2A>-Eigenschaft auf <xref:System.Windows.Forms.ToolStripItemDisplayStyle.Text> und die <xref:System.Windows.Forms.ToolStripItem.Text%2A>-Eigenschaft auf **Ordner auswählen** fest.  
  
4. Fügen Sie dem <xref:System.Windows.Forms.ToolStrip>-Steuerelement ein zweites <xref:System.Windows.Forms.ToolStripButton>-Steuerelement hinzu. Legen Sie die <xref:System.Windows.Forms.ToolStripItem.DisplayStyle%2A>-Eigenschaft auf <xref:System.Windows.Forms.ToolStripItemDisplayStyle.Text>, die <xref:System.Windows.Forms.ToolStripItem.Text%2A>-Eigenschaft auf **Abbrechen** und die <xref:System.Windows.Forms.ToolStripItem.Enabled%2A>-Eigenschaft auf `False` fest.  
  
5. Fügen Sie dem Hauptformular ein <xref:System.Windows.Forms.PictureBox>-Objekt hinzu. Legen Sie die <xref:System.Windows.Forms.Control.Dock%2A>-Eigenschaft auf <xref:System.Windows.Forms.DockStyle.Fill> fest.  
  
<a name="network"></a>
## <a name="creating-the-dataflow-network"></a>Erstellen des Datenflussnetzwerks  
 Dieser Abschnitt beschreibt das Erstellen eines Datenflussnetzwerks, das Bildverarbeitung durchführt.  
  
### <a name="to-create-the-dataflow-network"></a>Erstellen des Datenflussnetzwerks  
  
1. Fügen Sie Ihrem Projekt einen Verweis auf „System.Threading.Tasks.Dataflow.dll“ hinzu.  
  
2. Stellen Sie sicher, dass „Form1.cs“ („Form1.vb“ für Visual Basic) die folgenden `using`-Anweisungen (`Using` in Visual Basic) enthält:  
  
     [!code-csharp[TPLDataflow_CompositeImages#1](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_compositeimages/cs/compositeimages/form1.cs#1)]  
  
3. Fügen Sie der `Form1`-Klasse die folgenden Datenmember hinzu:  
  
     [!code-csharp[TPLDataflow_CompositeImages#2](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_compositeimages/cs/compositeimages/form1.cs#2)]  
  
4. Fügen Sie der `Form1`-Klasse die folgende `CreateImageProcessingNetwork`-Methode hinzu: Diese Methode erstellt das Bildverarbeitungsnetzwerk.  
  
     [!code-csharp[TPLDataflow_CompositeImages#3](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_compositeimages/cs/compositeimages/form1.cs#3)]  
  
5. Implementieren Sie die `LoadBitmaps`-Methode.  
  
     [!code-csharp[TPLDataflow_CompositeImages#4](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_compositeimages/cs/compositeimages/form1.cs#4)]  
  
6. Implementieren Sie die `CreateCompositeBitmap`-Methode.  
  
     [!code-csharp[TPLDataflow_CompositeImages#5](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_compositeimages/cs/compositeimages/form1.cs#5)]  
  
    > [!NOTE]
    > Die C#-Version der `CreateCompositeBitmap`-Methode verwendet Zeiger, um eine effiziente Verarbeitung der <xref:System.Drawing.Bitmap?displayProperty=nameWithType>-Objekte zu ermöglichen. Aus diesem Grund müssen Sie die Option **Unsicheren Code zulassen** in Ihrem Projekt aktivieren, um das [unsafe](../../csharp/language-reference/keywords/unsafe.md)-Schlüsselwort zu verwenden. Weitere Informationen zum Aktivieren von unsicheren Codes in einem Visual C#-Projekt finden Sie unter [Seite „Erstellen“, Projekt-Designer (C#)](/visualstudio/ide/reference/build-page-project-designer-csharp).  
  
 In der folgenden Tabelle werden die Member des Netzwerks beschrieben.  
  
|Member|Geben Sie Folgendes ein:|Beschreibung|  
|------------|----------|-----------------|  
|`loadBitmaps`|<xref:System.Threading.Tasks.Dataflow.TransformBlock%602>|Akzeptiert einen Ordnerpfad als Eingabe und erzeugt eine Auflistung von <xref:System.Drawing.Bitmap>-Objekten als Ausgabe.|  
|`createCompositeBitmap`|<xref:System.Threading.Tasks.Dataflow.TransformBlock%602>|Akzeptiert eine Auflistung von <xref:System.Drawing.Bitmap>-Objekten als Eingabe und erzeugt eine zusammengesetzte Bitmap als Ausgabe.|  
|`displayCompositeBitmap`|<xref:System.Threading.Tasks.Dataflow.ActionBlock%601>|Zeigt die zusammengesetzte Bitmap im Formular an.|  
|`operationCancelled`|<xref:System.Threading.Tasks.Dataflow.ActionBlock%601>|Zeigt ein Bild an, um anzugeben, dass der Vorgang abgebrochen wird, und ermöglicht es dem Benutzer, einen anderen Ordner auszuwählen.|  
  
 Um die Datenflussblöcke zu einem Netzwerk zu verbinden, wird in diesem Beispiel die <xref:System.Threading.Tasks.Dataflow.ISourceBlock%601.LinkTo%2A>-Methode verwendet. Die <xref:System.Threading.Tasks.Dataflow.ISourceBlock%601.LinkTo%2A>-Methode enthält eine überladene Version, die ein <xref:System.Predicate%601>-Objekt akzeptiert, das definiert, ob der Zielblock eine Nachricht akzeptiert oder ablehnt. Dieser Filtermechanismus aktiviert Nachrichtenblöcke so, dass sie nur bestimmte Werte empfangen. In diesem Beispiel kann das Netzwerk auf zwei Arten verzweigen. Die Hauptverzweigung lädt die Bilder vom Datenträger, erstellt das zusammengesetzte Bild und zeigt das Bild auf dem Formular an. Die alternative Verzweigung bricht den aktuellen Vorgang ab. Die <xref:System.Predicate%601>-Objekte aktivieren die Datenflussblöcke entlang der Hauptverzweigung, um zur alternativen Verzweigung zu wechseln, indem bestimmte Nachrichten zurückgewiesen werden. Wenn der Benutzer beispielsweise den Vorgang abbricht, erzeugt der Datenflussblock `createCompositeBitmap``null` (`Nothing` in Visual Basic) als Ausgabe. Der Datenflussblock `displayCompositeBitmap` lehnt `null`-Eingabewerte ab, und daher wird die Nachricht `operationCancelled` bereitgestellt. Der Datenflussblock `operationCancelled` akzeptiert alle Nachrichten und zeigt daher ein Bild an, um anzugeben, dass der Vorgang abgebrochen wird.  
  
 Die folgende Abbildung zeigt das Bildverarbeitungsnetzwerk:  
  
 ![Abbildung des Bildverarbeitungsnetzwerks](./media/walkthrough-using-dataflow-in-a-windows-forms-application/dataflow-winforms-image-processing.png)  
  
 Da die `displayCompositeBitmap`- und `operationCancelled`-Datenflussblöcke als Benutzeroberfläche agiert, ist es wichtig, dass diese Aktionen im Benutzeroberflächenthread erfolgen. Um dies zu erreichen, stellen diese Objekte während der Erstellung ein <xref:System.Threading.Tasks.Dataflow.ExecutionDataflowBlockOptions>-Objekt bereit, für das die <xref:System.Threading.Tasks.Dataflow.DataflowBlockOptions.TaskScheduler%2A>-Eigenschaft auf <xref:System.Threading.Tasks.TaskScheduler.FromCurrentSynchronizationContext%2A?displayProperty=nameWithType> festgelegt ist. Die <xref:System.Threading.Tasks.TaskScheduler.FromCurrentSynchronizationContext%2A?displayProperty=nameWithType>-Methode erstellt ein <xref:System.Threading.Tasks.TaskScheduler>-Objekt, das Arbeiten im aktuellen Synchronisierungskontext durchführt. Da die `CreateImageProcessingNetwork`-Methode vom Handler der Schaltfläche **Ordner auswählen** aufgerufen wird, die im Benutzeroberflächenthread ausgeführt wird, werden die Aktionen für den `displayCompositeBitmap`- und den `operationCancelled`-Datenflussblock ebenfalls im Benutzeroberflächenthread ausgeführt.  
  
 In diesem Beispiel wird ein gemeinsames Abbruchtoken verwendet, anstatt die <xref:System.Threading.Tasks.Dataflow.DataflowBlockOptions.CancellationToken%2A>-Eigenschaft festzulegen, da die <xref:System.Threading.Tasks.Dataflow.DataflowBlockOptions.CancellationToken%2A>-Eigenschaft die Ausführung des Datenflussblocks endgültig abbricht. Dank eines Abbruchtokens kann dieses Beispiel das gleiche Datenflussnetzwerk mehrmals wiederverwenden, und zwar selbst dann, wenn der Benutzer einen oder mehrere Vorgänge abbricht. Ein Beispiel für die Verwendung von <xref:System.Threading.Tasks.Dataflow.DataflowBlockOptions.CancellationToken%2A> für den endgültigen Abbruch der Ausführung des Datenflussblocks finden Sie unter [Gewusst wie: Abbrechen eines Datenflussblocks](../../../docs/standard/parallel-programming/how-to-cancel-a-dataflow-block.md).  
  
<a name="ui"></a>
## <a name="connecting-the-dataflow-network-to-the-user-interface"></a>Verbinden des Datenflussnetzwerks mit der Benutzeroberfläche  
 In diesem Abschnitt wird beschrieben, wie Sie das Datenflussnetzwerk mit der Benutzeroberfläche verbinden. Die Erstellung des zusammengesetzten Bildes und der Abbruch des Vorgangs werden über die Schaltflächen **Ordner auswählen** und **Abbrechen** initiiert. Wenn der Benutzer eine dieser Schaltflächen auswählt, wird die entsprechende Aktion auf asynchrone Weise initiiert.  
  
### <a name="to-connect-the-dataflow-network-to-the-user-interface"></a>Verbinden des Datenflussnetzwerks mit der Benutzeroberfläche  
  
1. Erstellen Sie im Formulardesigner für das Hauptformular einen Ereignishandler für das <xref:System.Windows.Forms.ToolStripItem.Click>-Ereignis der Schaltfläche **Ordner auswählen**.  
  
2. Implementieren Sie das <xref:System.Windows.Forms.ToolStripItem.Click>-Ereignis für die Schaltfläche **Ordner auswählen**.  
  
     [!code-csharp[TPLDataflow_CompositeImages#6](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_compositeimages/cs/compositeimages/form1.cs#6)]  
  
3. Erstellen Sie im Formulardesigner für das Hauptformular einen Ereignishandler für das <xref:System.Windows.Forms.ToolStripItem.Click>-Ereignis der Schaltfläche **Abbrechen**.  
  
4. Implementieren Sie das <xref:System.Windows.Forms.ToolStripItem.Click>-Ereignis für die Schaltfläche **Abbrechen**.  
  
     [!code-csharp[TPLDataflow_CompositeImages#7](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_compositeimages/cs/compositeimages/form1.cs#7)]  
  
<a name="complete"></a>
## <a name="the-complete-example"></a>Vollständiges Beispiel  
 Das folgende Beispiel enthält den vollständigen Code für diese exemplarische Vorgehensweise.  
  
 [!code-csharp[TPLDataflow_CompositeImages#100](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_compositeimages/cs/compositeimages/form1.cs#100)]  
  
 Die folgende Abbildung zeigt die normale Ausgabe für den gemeinsamen Ordner „\Sample Pictures\“.  
  
 ![Die Windows Forms-Anwendung](../../../docs/standard/parallel-programming/media/tpldataflow-compositeimages.gif "TPLDataflow_CompositeImages")  

## <a name="see-also"></a>Weitere Informationen

- [Dataflow (Datenfluss)](../../../docs/standard/parallel-programming/dataflow-task-parallel-library.md)
