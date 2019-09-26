---
title: 'Exemplarische Vorgehensweise: Erstellen einer Explorer-ähnlichen Schnittstelle mit dem ListView-Steuerelement und dem TreeView-Steuerelement im Designer'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Explorer-style applications [Windows Forms], walkthroughs
- TreeView control [Windows Forms], ListView controls used with
- ListView control [Windows Forms], TreeView controls used with
- Explorer-style applications
- TreeView control [Windows Forms], using for explorer-style interface
- ListView control [Windows Forms], explorer style interface
- ListView control [Windows Forms], explorer-style interface
ms.assetid: 9e5e7721-19e2-4890-b273-a43589fe99ff
ms.openlocfilehash: d80f8e3bc729689b274af520bc37fda8417b0407
ms.sourcegitcommit: 56f1d1203d0075a461a10a301459d3aa452f4f47
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/25/2019
ms.locfileid: "69658572"
---
# <a name="walkthrough-creating-an-explorer-style-interface-with-the-listview-and-treeview-controls-using-the-designer"></a>Exemplarische Vorgehensweise: Erstellen einer Explorer-ähnlichen Schnittstelle mit dem ListView-Steuerelement und dem TreeView-Steuerelement im Designer

Einer der Vorteile von Visual Studio ist die Möglichkeit, in einem kurzen Zeitraum professionell aussehende Windows Forms Anwendungen zu erstellen. Ein häufiges Szenario ist die Erstellung einer Benutzeroberfläche (UI) <xref:System.Windows.Forms.ListView> mit <xref:System.Windows.Forms.TreeView> -und-Steuerelementen, die der Windows-Explorer-Funktion von Windows-Betriebssystemen ähneln. Windows-Explorer zeigt eine hierarchische Struktur der Dateien und Ordner auf dem Computer eines Benutzers an.

### <a name="to-create-the-form-containing-a-listview-and-treeview-control"></a>So erstellen Sie das Formular mit einem ListView-und TreeView-Steuerelement

1. Zeigen Sie im Menü **Datei** auf **Neu**, und klicken Sie dann auf **Projekt**.

2. Führen Sie im Dialogfeld **Neues Projekt** die folgenden Schritte aus:

    1. Wählen Sie in den Kategorien entweder **Visual Basic** oder **Visualisierung C#** aus.

    2. Wählen Sie in der Liste der Vorlagen **Windows Forms Anwendung**aus.

3. Klicken Sie auf **OK**. Ein neues Windows Forms Projekt wird erstellt.

4. Fügen Sie <xref:System.Windows.Forms.SplitContainer> dem Formular ein Steuerelement hinzu, <xref:System.Windows.Forms.SplitContainer.Dock%2A> und legen <xref:System.Windows.Forms.DockStyle.Fill>Sie dessen-Eigenschaft auf fest.

5. Fügen Sie <xref:System.Windows.Forms.ImageList> dem `imageList1` Formular einen mit dem Namen hinzu, und verwenden Sie die Eigenschaftenfenster, um zwei Bilder hinzuzufügen: ein Ordner Image und ein Dokument Bild in dieser Reihenfolge.

6. Fügen Sie <xref:System.Windows.Forms.TreeView> dem Formular `treeview1` ein-Steuerelement mit dem Namen hinzu, und positionieren Sie es <xref:System.Windows.Forms.SplitContainer> auf der linken Seite des-Steuer Elements. Gehen Sie im Eigenschaftenfenster `treeView1` für wie folgt vor:

    1. Legen Sie die <xref:System.Windows.Forms.Control.Dock%2A> -Eigenschaft auf <xref:System.Windows.Forms.DockStyle.Fill>fest.

    2. Legen Sie die <xref:System.Windows.Forms.TreeView.ImageList%2A>-Eigenschaft auf `imagelist1.` fest.

7. Fügen Sie <xref:System.Windows.Forms.ListView> dem Formular `listView1` ein-Steuerelement mit dem Namen hinzu, und positionieren Sie es <xref:System.Windows.Forms.SplitContainer> auf der rechten Seite des-Steuer Elements. Gehen Sie im Eigenschaftenfenster `listview1` für wie folgt vor:

    1. Legen Sie die <xref:System.Windows.Forms.Control.Dock%2A> -Eigenschaft auf <xref:System.Windows.Forms.DockStyle.Fill>fest.

    2. Legen Sie die <xref:System.Windows.Forms.ListView.View%2A> -Eigenschaft auf <xref:System.Windows.Forms.View.Details>fest.

    3. Öffnen Sie den ColumnHeader-Auflistungs-Editor,![indem Sie in <xref:System.Windows.Forms.ListView.Columns%2A> der **-Eigenschaft auf** die Auslassungs Punkte (die Schaltfläche mit](./media/visual-studio-ellipsis-button.png)den Auslassungs Punkten (...) im Eigenschaftenfenster von Visual Studio klicken. Fügen Sie drei Spalten hinzu, <xref:System.Windows.Forms.ColumnHeader.Text%2A> und legen `Name`Sie `Type`die zugehörige-Eigenschaft auf, `Last Modified`bzw. fest. Klicken Sie auf **OK**, um das Dialogfeld zu schließen.

    4. Legen Sie die <xref:System.Windows.Forms.ListView.SmallImageList%2A>-Eigenschaft auf `imageList1.` fest.

8. Implementieren Sie den Code, um die <xref:System.Windows.Forms.TreeView> mit Knoten und untergeordneten Knoten aufzufüllen. Fügen Sie diesen Code zur `Form1`-Klasse hinzu.

     [!code-csharp[System.Windows.Forms.ExplorerStyleInterface#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ExplorerStyleInterface/CS/Form1.cs#1)]
     [!code-vb[System.Windows.Forms.ExplorerStyleInterface#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ExplorerStyleInterface/VB/Form1.vb#1)]

9. Da der vorherige Code den System.IO-Namespace verwendet, fügen Sie die entsprechende using-oder Import-Anweisung am Anfang des Formulars hinzu.

     [!code-csharp[System.Windows.Forms.ExplorerStyleInterface#4](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ExplorerStyleInterface/CS/Form1.cs#4)]
     [!code-vb[System.Windows.Forms.ExplorerStyleInterface#4](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ExplorerStyleInterface/VB/Form1.vb#4)]

10. Ruft die Setup Methode aus dem vorherigen Schritt im Konstruktor des Formulars oder <xref:System.Windows.Forms.Form.Load> der Ereignis Behandlungsmethode auf. Fügen Sie dem Formularkonstruktor den folgenden Code hinzu.

     [!code-csharp[System.Windows.Forms.ExplorerStyleInterface#2](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ExplorerStyleInterface/CS/Form1.cs#2)]
     [!code-vb[System.Windows.Forms.ExplorerStyleInterface#2](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ExplorerStyleInterface/VB/Form1.vb#2)]

11. Behandeln Sie <xref:System.Windows.Forms.TreeView.NodeMouseClick> das -Ereignis`treeview1`für **,** und implementieren Sie den Code, um den Inhalt eines Knotens aufzufüllen ,wennaufeinenKnotengeklickt`listview1` wird. Fügen Sie diesen Code zur `Form1`-Klasse hinzu.

     [!code-csharp[System.Windows.Forms.ExplorerStyleInterface#3](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ExplorerStyleInterface/CS/Form1.cs#3)]
     [!code-vb[System.Windows.Forms.ExplorerStyleInterface#3](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ExplorerStyleInterface/VB/Form1.vb#3)]

     Wenn Sie verwenden C#, stellen Sie sicher, dass das <xref:System.Windows.Forms.TreeView.NodeMouseClick> -Ereignis mit seiner Ereignis Behandlungsmethode verknüpft ist. Fügen Sie dem Formularkonstruktor den folgenden Code hinzu.

     [!code-csharp[System.Windows.Forms.ExplorerStyleInterface#5](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ExplorerStyleInterface/CS/Form1.cs#5)]

## <a name="testing-the-application"></a>Testen der Anwendung

Sie können das Formular jetzt testen, um sicherzustellen, dass das Verhalten wie erwartet ausfällt.

#### <a name="to-test-the-form"></a>So testen Sie das Formular

- Drücken Sie F5, um die Anwendung auszuführen.

     Sie sehen ein geteiltes Formular, das <xref:System.Windows.Forms.TreeView> ein Steuerelement enthält, das Ihr Projektverzeichnis auf der linken Seite <xref:System.Windows.Forms.ListView> anzeigt, und ein Steuerelement auf der rechten Seite mit drei Spalten. Sie können den <xref:System.Windows.Forms.TreeView> durchlaufen, indem Sie Verzeichnis Knoten auswählen <xref:System.Windows.Forms.ListView> , und wird mit dem Inhalt des ausgewählten Verzeichnisses aufgefüllt.

## <a name="next-steps"></a>Nächste Schritte

Diese Anwendung bietet ein Beispiel dafür, wie Sie und- <xref:System.Windows.Forms.TreeView> <xref:System.Windows.Forms.ListView> Steuerelemente gleichzeitig verwenden können. Weitere Informationen zu diesen Steuerelementen finden Sie in den folgenden Themen:

- [Vorgehensweise: Hinzufügen von benutzerdefinierten Informationen zu einem TreeView-oder ListView-Steuerelement (Windows Forms)](add-custom-information-to-a-treeview-or-listview-control-wf.md)

- [Vorgehensweise: Hinzufügen von Suchfunktionen zu einem ListView-Steuerelement](how-to-add-search-capabilities-to-a-listview-control.md)

- [Vorgehensweise: Anfügen eines Kontextmenüs an einen TreeView-Knoten](how-to-attach-a-shortcut-menu-to-a-treeview-node.md)

## <a name="see-also"></a>Siehe auch

- <xref:System.Windows.Forms.ListView>
- <xref:System.Windows.Forms.TreeView>
- [ListView-Steuerelement](listview-control-windows-forms.md)
- [Vorgehensweise: Hinzufügen und Entfernen von Knoten mit dem Windows Forms TreeView-Steuerelement](how-to-add-and-remove-nodes-with-the-windows-forms-treeview-control.md)
- [Vorgehensweise: Hinzufügen und Entfernen von Elementen mit dem Windows Forms ListView-Steuerelement](how-to-add-and-remove-items-with-the-windows-forms-listview-control.md)
- [Vorgehensweise: Hinzufügen von Spalten zum Windows Forms ListView-Steuerelement](how-to-add-columns-to-the-windows-forms-listview-control.md)
