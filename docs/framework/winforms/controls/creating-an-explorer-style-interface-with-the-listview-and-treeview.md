---
title: 'Exemplarische Vorgehensweise: Erstellen einer Explorer-ähnlichen Schnittstelle mit dem ListView-Steuerelement und dem TreeView-Steuerelement im Designer'
description: Erfahren Sie, wie Sie eine Explorer-stilschnittstelle mit den Windows Forms ListView-und TreeView-Steuerelementen mithilfe des Designers erstellen.
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
ms.openlocfilehash: 44d4db1ef3da85dbf411498f486882b86a05c140
ms.sourcegitcommit: cb27c01a8b0b4630148374638aff4e2221f90b22
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/09/2020
ms.locfileid: "86174626"
---
# <a name="walkthrough-creating-an-explorer-style-interface-with-the-listview-and-treeview-controls-using-the-designer"></a>Exemplarische Vorgehensweise: Erstellen einer Explorer-ähnlichen Schnittstelle mit dem ListView-Steuerelement und dem TreeView-Steuerelement im Designer

Einer der Vorteile von Visual Studio ist die Möglichkeit, in einem kurzen Zeitraum professionell aussehende Windows Forms Anwendungen zu erstellen. Ein häufiges Szenario ist die Erstellung einer Benutzeroberfläche (UI) mit <xref:System.Windows.Forms.ListView> -und-Steuer <xref:System.Windows.Forms.TreeView> Elementen, die der Windows-Explorer-Funktion von Windows-Betriebssystemen ähneln. Windows-Explorer zeigt eine hierarchische Struktur der Dateien und Ordner auf dem Computer eines Benutzers an.

### <a name="to-create-the-form-containing-a-listview-and-treeview-control"></a>So erstellen Sie das Formular mit einem ListView-und TreeView-Steuerelement

1. Zeigen Sie im Menü **Datei** auf **Neu**, und klicken Sie dann auf **Projekt**.

2. Führen Sie im Dialogfeld **Neues Projekt** folgende Schritte aus:

    1. Wählen Sie in den Kategorien entweder **Visual Basic** oder **Visual c#** aus.

    2. Wählen Sie in der Liste der Vorlagen **Windows Forms Anwendung**aus.

3. Klicken Sie auf **OK**. Ein neues Windows Forms Projekt wird erstellt.

4. Fügen Sie <xref:System.Windows.Forms.SplitContainer> dem Formular ein Steuerelement hinzu, und legen Sie dessen- <xref:System.Windows.Forms.SplitContainer.Dock%2A> Eigenschaft auf fest <xref:System.Windows.Forms.DockStyle.Fill> .

5. Fügen Sie <xref:System.Windows.Forms.ImageList> dem Formular einen mit dem Namen hinzu `imageList1` , und verwenden Sie die Eigenschaftenfenster, um zwei Bilder hinzuzufügen: ein Ordner Image und ein Dokument Bild in dieser Reihenfolge.

6. Fügen Sie <xref:System.Windows.Forms.TreeView> `treeview1` dem Formular ein-Steuerelement mit dem Namen hinzu, und positionieren Sie es auf der linken Seite des- <xref:System.Windows.Forms.SplitContainer> Steuer Elements. Gehen Sie im Eigenschaftenfenster für wie `treeView1` folgt vor:

    1. Legen Sie die <xref:System.Windows.Forms.Control.Dock%2A> -Eigenschaft auf <xref:System.Windows.Forms.DockStyle.Fill>fest.

    2. Legen Sie die <xref:System.Windows.Forms.TreeView.ImageList%2A>-Eigenschaft auf `imagelist1.` fest.

7. Fügen Sie <xref:System.Windows.Forms.ListView> `listView1` dem Formular ein-Steuerelement mit dem Namen hinzu, und positionieren Sie es auf der rechten Seite des- <xref:System.Windows.Forms.SplitContainer> Steuer Elements. Gehen Sie im Eigenschaftenfenster für wie `listview1` folgt vor:

    1. Legen Sie die <xref:System.Windows.Forms.Control.Dock%2A> -Eigenschaft auf <xref:System.Windows.Forms.DockStyle.Fill>fest.

    2. Legen Sie die <xref:System.Windows.Forms.ListView.View%2A> -Eigenschaft auf <xref:System.Windows.Forms.View.Details>fest.

    3. Öffnen Sie den ColumnHeader-Auflistungs-Editor, indem Sie in der-Eigenschaft auf die Auslassungs Punkte ( ![ die Schaltfläche mit den Auslassungs Punkten (...) im Eigenschaftenfenster von Visual Studio klicken. ](./media/visual-studio-ellipsis-button.png) <xref:System.Windows.Forms.ListView.Columns%2A> **.** Fügen Sie drei Spalten hinzu, und legen Sie die zugehörige- <xref:System.Windows.Forms.ColumnHeader.Text%2A> Eigenschaft auf `Name` , `Type` `Last Modified` bzw. fest. Klicken Sie auf **OK** , um das Dialogfeld zu schließen.

    4. Legen Sie die <xref:System.Windows.Forms.ListView.SmallImageList%2A>-Eigenschaft auf `imageList1.` fest.

8. Implementieren Sie den Code, um die <xref:System.Windows.Forms.TreeView> mit Knoten und untergeordneten Knoten aufzufüllen. Fügen Sie diesen Code zur `Form1`-Klasse hinzu.

     [!code-csharp[System.Windows.Forms.ExplorerStyleInterface#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ExplorerStyleInterface/CS/Form1.cs#1)]
     [!code-vb[System.Windows.Forms.ExplorerStyleInterface#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ExplorerStyleInterface/VB/Form1.vb#1)]

9. Da der vorherige Code den System.IO-Namespace verwendet, fügen Sie die entsprechende using-oder Import-Anweisung am Anfang des Formulars hinzu.

     [!code-csharp[System.Windows.Forms.ExplorerStyleInterface#4](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ExplorerStyleInterface/CS/Form1.cs#4)]
     [!code-vb[System.Windows.Forms.ExplorerStyleInterface#4](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ExplorerStyleInterface/VB/Form1.vb#4)]

10. Ruft die Setup Methode aus dem vorherigen Schritt im Konstruktor des Formulars oder der <xref:System.Windows.Forms.Form.Load> Ereignis Behandlungsmethode auf. Fügen Sie dem Formularkonstruktor den folgenden Code hinzu.

     [!code-csharp[System.Windows.Forms.ExplorerStyleInterface#2](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ExplorerStyleInterface/CS/Form1.cs#2)]
     [!code-vb[System.Windows.Forms.ExplorerStyleInterface#2](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ExplorerStyleInterface/VB/Form1.vb#2)]

11. Behandeln <xref:System.Windows.Forms.TreeView.NodeMouseClick> Sie das-Ereignis für `treeview1` **,** und implementieren Sie den Code, um den `listview1` Inhalt eines Knotens aufzufüllen, wenn auf einen Knoten geklickt wird. Fügen Sie diesen Code zur `Form1`-Klasse hinzu.

     [!code-csharp[System.Windows.Forms.ExplorerStyleInterface#3](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ExplorerStyleInterface/CS/Form1.cs#3)]
     [!code-vb[System.Windows.Forms.ExplorerStyleInterface#3](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ExplorerStyleInterface/VB/Form1.vb#3)]

     Wenn Sie c# verwenden, stellen Sie sicher, dass das- <xref:System.Windows.Forms.TreeView.NodeMouseClick> Ereignis mit seiner Ereignis Behandlungsmethode verknüpft ist. Fügen Sie dem Formularkonstruktor den folgenden Code hinzu.

     [!code-csharp[System.Windows.Forms.ExplorerStyleInterface#5](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ExplorerStyleInterface/CS/Form1.cs#5)]

## <a name="testing-the-application"></a>Testen der Anwendung

Sie können das Formular jetzt testen, um sicherzustellen, dass das Verhalten wie erwartet ausfällt.

#### <a name="to-test-the-form"></a>So testen Sie das Formular

- Drücken Sie die Taste F5, um die Anwendung auszuführen.

     Sie sehen ein geteiltes Formular, das ein Steuerelement enthält, <xref:System.Windows.Forms.TreeView> das Ihr Projektverzeichnis auf der linken Seite anzeigt, und ein <xref:System.Windows.Forms.ListView> Steuerelement auf der rechten Seite mit drei Spalten. Sie können den <xref:System.Windows.Forms.TreeView> durchlaufen, indem Sie Verzeichnis Knoten auswählen, und <xref:System.Windows.Forms.ListView> wird mit dem Inhalt des ausgewählten Verzeichnisses aufgefüllt.

## <a name="next-steps"></a>Nächste Schritte

Diese Anwendung bietet ein Beispiel dafür, wie Sie und-Steuerelemente gleichzeitig verwenden können <xref:System.Windows.Forms.TreeView> <xref:System.Windows.Forms.ListView> . Weitere Informationen zu diesen Steuerelementen finden Sie in den folgenden Themen:

- [Vorgehensweise: Hinzufügen von benutzerdefinierten Daten zu einem TreeView- oder ListView-Steuerelement (Windows Forms)](add-custom-information-to-a-treeview-or-listview-control-wf.md)

- [Vorgehensweise: Hinzufügen von Suchfunktionen zu einem ListView-Steuerelement](how-to-add-search-capabilities-to-a-listview-control.md)

- [Vorgehensweise: Anfügen eines Kontextmenüs an einen Strukturansichtsknoten](how-to-attach-a-shortcut-menu-to-a-treeview-node.md)

## <a name="see-also"></a>Weitere Informationen

- <xref:System.Windows.Forms.ListView>
- <xref:System.Windows.Forms.TreeView>
- [ListView-Steuerelement](listview-control-windows-forms.md)
- [Vorgehensweise: Hinzufügen oder Entfernen von Knoten mit dem TreeView-Steuerelement in Windows Forms](how-to-add-and-remove-nodes-with-the-windows-forms-treeview-control.md)
- [Vorgehensweise: Hinzufügen und Entfernen von Elementen mit dem ListView-Steuerelement in Windows Forms](how-to-add-and-remove-items-with-the-windows-forms-listview-control.md)
- [Vorgehensweise: Hinzufügen von Spalten zum ListView-Steuerelement in Windows Forms](how-to-add-columns-to-the-windows-forms-listview-control.md)
