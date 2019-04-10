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
ms.openlocfilehash: 8192151aa7cd5eddd99d39adb485e460074fdb99
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/09/2019
ms.locfileid: "59332117"
---
# <a name="walkthrough-creating-an-explorer-style-interface-with-the-listview-and-treeview-controls-using-the-designer"></a>Exemplarische Vorgehensweise: Erstellen einer Explorer-ähnlichen Schnittstelle mit dem ListView-Steuerelement und dem TreeView-Steuerelement im Designer
Einer der Vorteile von Visual Studio ist die Fähigkeit zum Erstellen von professionell gestaltete Windows Forms-Anwendungen in eine Kurzform der Zeitspanne. Ein häufiges Szenario ist die Erstellung einer Benutzeroberfläche (UI) mit <xref:System.Windows.Forms.ListView> und <xref:System.Windows.Forms.TreeView> Steuerelemente, die die Windows-Explorer-Funktion von Windows-Betriebssystemen ähnelt. Windows-Explorer zeigt eine hierarchische Struktur der Dateien und Ordner auf dem Computer eines Benutzers an.  
  
> [!NOTE]
>  Je nach den aktiven Einstellungen oder der Version unterscheiden sich die Dialogfelder und Menübefehle auf Ihrem Bildschirm möglicherweise von den in der Hilfe beschriebenen. Klicken Sie im Menü **Extras** auf **Einstellungen importieren und exportieren** , um die Einstellungen zu ändern. Weitere Informationen finden Sie unter [Personalisieren von Visual Studio-IDE](/visualstudio/ide/personalizing-the-visual-studio-ide).  
  
### <a name="to-create-the-form-containing-a-listview-and-treeview-control"></a>Um das Formular mit einer ListView und TreeView-Steuerelement zu erstellen.  
  
1. Zeigen Sie im Menü **Datei** auf **Neu**, und klicken Sie dann auf **Projekt**.  
  
2. In der **neues Projekt** Dialogfeld Feld, gehen Sie folgendermaßen vor:  
  
    1.  Wählen Sie in die Kategorien entweder **Visual Basic** oder **Visual C#-**.  
  
    2.  Wählen Sie in der Liste der Vorlagen, **Windows Forms-Anwendung**.  
  
3. Klicken Sie auf **OK**. Ein neues Windows Forms-Projekt wird erstellt.  
  
4. Hinzufügen einer <xref:System.Windows.Forms.SplitContainer> -Steuerelement auf das Formular, und legen Sie dessen <xref:System.Windows.Forms.SplitContainer.Dock%2A> Eigenschaft <xref:System.Windows.Forms.DockStyle.Fill>.  
  
5. Hinzufügen einer <xref:System.Windows.Forms.ImageList> mit dem Namen `imageList1` auf das Formular und verwenden Sie das Fenster "Eigenschaften" zwei Bilder hinzu: ein Ordner-Image und eine Dokument-Image, in dieser Reihenfolge.  
  
6. Hinzufügen einer <xref:System.Windows.Forms.TreeView> Steuerelement mit dem Namen `treeview1` auf das Formular, und positionieren Sie sie auf der linken Seite von der <xref:System.Windows.Forms.SplitContainer> Steuerelement. Im Fenster "Eigenschaften" für `treeView1` gehen Sie folgendermaßen vor:  
  
    1.  Legen Sie die <xref:System.Windows.Forms.Control.Dock%2A> -Eigenschaft auf <xref:System.Windows.Forms.DockStyle.Fill>fest.  
  
    2.  Legen Sie die <xref:System.Windows.Forms.TreeView.ImageList%2A> Eigenschaft `imagelist1.`  
  
7. Hinzufügen einer <xref:System.Windows.Forms.ListView> Steuerelement mit dem Namen `listView1` auf das Formular, und positionieren Sie sie auf der rechten Seite von der <xref:System.Windows.Forms.SplitContainer> Steuerelement. Im Fenster "Eigenschaften" für `listview1` gehen Sie folgendermaßen vor:  
  
    1.  Legen Sie die <xref:System.Windows.Forms.Control.Dock%2A> -Eigenschaft auf <xref:System.Windows.Forms.DockStyle.Fill>fest.  
  
    2.  Legen Sie die <xref:System.Windows.Forms.ListView.View%2A> -Eigenschaft auf <xref:System.Windows.Forms.View.Details>fest.  
  
    3.  Öffnen Sie den ColumnHeader-Auflistungs-Editor, indem Sie auf die Auslassungspunkte (![VisualStudioEllipsesButton-bildschirmabbildung](../media/vbellipsesbutton.png "VbEllipsesButton")) in der <xref:System.Windows.Forms.ListView.Columns%2A> Eigenschaft **.** Fügen Sie drei Spalten hinzu, und legen Sie deren <xref:System.Windows.Forms.ColumnHeader.Text%2A> Eigenschaft `Name`, `Type`, und `Last Modified`bzw. Klicken Sie auf **OK**, um das Dialogfeld zu schließen.  
  
    4.  Legen Sie die <xref:System.Windows.Forms.ListView.SmallImageList%2A> Eigenschaft `imageList1.`  
  
8. Implementieren Sie den Code zum Auffüllen der <xref:System.Windows.Forms.TreeView> mit Knoten und die untergeordneten Knoten. Fügen Sie diesen Code zur `Form1`-Klasse hinzu.  
  
     [!code-csharp[System.Windows.Forms.ExplorerStyleInterface#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ExplorerStyleInterface/CS/Form1.cs#1)]
     [!code-vb[System.Windows.Forms.ExplorerStyleInterface#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ExplorerStyleInterface/VB/Form1.vb#1)]  
  
9. Da der vorherige Code den System.IO-Namespace verwendet, fügen Sie die entsprechende Verwendung oder import-Anweisung am oberen Rand des Formulars.  
  
     [!code-csharp[System.Windows.Forms.ExplorerStyleInterface#4](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ExplorerStyleInterface/CS/Form1.cs#4)]
     [!code-vb[System.Windows.Forms.ExplorerStyleInterface#4](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ExplorerStyleInterface/VB/Form1.vb#4)]  
  
10. Rufen Sie die Setup-Methode aus dem vorherigen Schritt in den Konstruktor des Formulars oder <xref:System.Windows.Forms.Form.Load> Ereignisbehandlungsmethode. Fügen Sie diesen Code zum Konstruktor Formulars.  
  
     [!code-csharp[System.Windows.Forms.ExplorerStyleInterface#2](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ExplorerStyleInterface/CS/Form1.cs#2)]
     [!code-vb[System.Windows.Forms.ExplorerStyleInterface#2](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ExplorerStyleInterface/VB/Form1.vb#2)]  
  
11. Behandeln der <xref:System.Windows.Forms.TreeView.NodeMouseClick> -Ereignis für `treeview1` **,** und implementieren Sie den Code zum Auffüllen `listview1` mit Inhalt eines Knotens, wenn Sie einen Knoten geklickt wird. Fügen Sie diesen Code zur `Form1`-Klasse hinzu.  
  
     [!code-csharp[System.Windows.Forms.ExplorerStyleInterface#3](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ExplorerStyleInterface/CS/Form1.cs#3)]
     [!code-vb[System.Windows.Forms.ExplorerStyleInterface#3](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ExplorerStyleInterface/VB/Form1.vb#3)]  
  
     Wenn Sie c# verwenden, stellen Sie sicher, dass die <xref:System.Windows.Forms.TreeView.NodeMouseClick> Ereignis mit seiner Ereignisbehandlungsmethode verknüpft ist. Fügen Sie diesen Code zum Konstruktor Formulars.  
  
     [!code-csharp[System.Windows.Forms.ExplorerStyleInterface#5](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ExplorerStyleInterface/CS/Form1.cs#5)]  
  
## <a name="testing-the-application"></a>Testen der Anwendung  
 Sie können das Formular jetzt testen, um sicherzustellen, dass das Verhalten wie erwartet ausfällt.  
  
#### <a name="to-test-the-form"></a>So testen Sie das Formular  
  
-   Drücken Sie F5, um die Anwendung auszuführen.  
  
     Sie sehen, dass ein Split-Formular mit einer <xref:System.Windows.Forms.TreeView> -Steuerelement, das Ihrem Projektverzeichnis auf der linken Seite angezeigt und eine <xref:System.Windows.Forms.ListView> Steuerelement auf der rechten Seite mit drei Spalten. Sie durchlaufen können die <xref:System.Windows.Forms.TreeView> durch Auswählen der Directory-Knoten, und die <xref:System.Windows.Forms.ListView> wird mit dem Inhalt des ausgewählten Verzeichnisses aufgefüllt.  
  
## <a name="next-steps"></a>Nächste Schritte  
 Diese Anwendung bietet Ihnen ein Beispiel für eine Möglichkeit, Sie können <xref:System.Windows.Forms.TreeView> und <xref:System.Windows.Forms.ListView> Steuerelement. Weitere Informationen zu diesen Steuerelementen finden Sie unter den folgenden Themen:  
  
-   [Vorgehensweise: Hinzufügen von benutzerdefinierten Daten zu einem TreeView- oder ListView-Steuerelement (Windows Forms)](add-custom-information-to-a-treeview-or-listview-control-wf.md)  
  
-   [Vorgehensweise: Hinzufügen von Suchfunktionen zu einem ListView-Steuerelement](how-to-add-search-capabilities-to-a-listview-control.md)  
  
-   [Vorgehensweise: Anfügen eines Kontextmenüs an einen Strukturansichtsknoten](how-to-attach-a-shortcut-menu-to-a-treeview-node.md)  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Windows.Forms.ListView>
- <xref:System.Windows.Forms.TreeView>
- [ListView-Steuerelement](listview-control-windows-forms.md)
- [Vorgehensweise: Hinzufügen oder Entfernen von Knoten mit dem TreeView-Steuerelement in Windows Forms](how-to-add-and-remove-nodes-with-the-windows-forms-treeview-control.md)
- [Vorgehensweise: Hinzufügen und Entfernen von Elementen mit dem ListView-Steuerelement in Windows Forms](how-to-add-and-remove-items-with-the-windows-forms-listview-control.md)
- [Vorgehensweise: Hinzufügen von Spalten zum ListView-Steuerelement in Windows Forms](how-to-add-columns-to-the-windows-forms-listview-control.md)
