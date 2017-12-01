---
title: "Exemplarische Vorgehensweise: Erstellen einer Explorer-ähnlichen Schnittstelle mit dem ListView-Steuerelement und dem TreeView-Steuerelement im Designer"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
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
caps.latest.revision: "19"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: a4a16ee1ca39ffb0eb170e206467d612cb707e5a
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="walkthrough-creating-an-explorer-style-interface-with-the-listview-and-treeview-controls-using-the-designer"></a>Exemplarische Vorgehensweise: Erstellen einer Explorer-ähnlichen Schnittstelle mit dem ListView-Steuerelement und dem TreeView-Steuerelement im Designer
Einer der Vorteile von Visual Studio ist die Fähigkeit zum Erstellen von professionell gestalteten Windows Forms-Anwendungen in kurzer Zeit. Ein häufiges Szenario ist eine Benutzeroberfläche (UI) erstellen, mit <xref:System.Windows.Forms.ListView> und <xref:System.Windows.Forms.TreeView> Steuerelemente, die Windows Explorer-Features von Windows-Betriebssystemen ähnelt. Windows-Explorer zeigt eine hierarchische Struktur der Dateien und Ordner auf dem Computer eines Benutzers an.  
  
> [!NOTE]
>  Je nach den aktiven Einstellungen oder der Version unterscheiden sich die Dialogfelder und Menübefehle auf Ihrem Bildschirm möglicherweise von den in der Hilfe beschriebenen. Klicken Sie im Menü **Extras** auf **Einstellungen importieren und exportieren** , um die Einstellungen zu ändern. Weitere Informationen finden Sie unter [Anpassen der Entwicklungseinstellungen in Visual Studio](http://msdn.microsoft.com/en-us/22c4debb-4e31-47a8-8f19-16f328d7dcd3).  
  
### <a name="to-create-the-form-containing-a-listview-and-treeview-control"></a>Zum Erstellen des Formulars, das ein ListView-Steuerelement und TreeView-Steuerelement  
  
1.  Zeigen Sie im Menü **Datei** auf **Neu**, und klicken Sie dann auf **Projekt**.  
  
2.  In der **neues Projekt** Dialogfeld Feld, gehen Sie folgendermaßen vor:  
  
    1.  Wählen Sie in den Kategorien entweder **Visual Basic** oder **Visual C#-**.  
  
    2.  Wählen Sie in der Liste der Vorlagen, **Windows Forms-Anwendung**.  
  
3.  Klicken Sie auf **OK**. Ein neues Windows Forms-Projekt wird erstellt.  
  
4.  Hinzufügen einer <xref:System.Windows.Forms.SplitContainer> -Steuerelement auf das Formular, und legen Sie dessen <xref:System.Windows.Forms.SplitContainer.Dock%2A> Eigenschaft <xref:System.Windows.Forms.DockStyle.Fill>.  
  
5.  Hinzufügen einer <xref:System.Windows.Forms.ImageList> mit dem Namen `imageList1` auf das Formular und mit dem Eigenschaftenfenster zwei Bilder hinzu: ein Ordner-Image und eine Dokument-Image in dieser Reihenfolge.  
  
6.  Hinzufügen einer <xref:System.Windows.Forms.TreeView> Steuerelement namens `treeview1` auf das Formular, und positionieren Sie es auf der linken Seite des der <xref:System.Windows.Forms.SplitContainer> Steuerelement. Im Fenster "Eigenschaften" für `treeView1` gehen Sie folgendermaßen vor:  
  
    1.  Legen Sie die <xref:System.Windows.Forms.Control.Dock%2A>-Eigenschaft auf <xref:System.Windows.Forms.DockStyle.Fill> fest.  
  
    2.  Legen Sie die <xref:System.Windows.Forms.TreeView.ImageList%2A>-Eigenschaft auf `imagelist1.` fest.  
  
7.  Hinzufügen einer <xref:System.Windows.Forms.ListView> Steuerelement namens `listView1` auf das Formular, und positionieren Sie es auf der rechten Seite des der <xref:System.Windows.Forms.SplitContainer> Steuerelement. Im Fenster "Eigenschaften" für `listview1` gehen Sie folgendermaßen vor:  
  
    1.  Legen Sie die <xref:System.Windows.Forms.Control.Dock%2A>-Eigenschaft auf <xref:System.Windows.Forms.DockStyle.Fill> fest.  
  
    2.  Legen Sie die <xref:System.Windows.Forms.ListView.View%2A>-Eigenschaft auf <xref:System.Windows.Forms.View.Details> fest.  
  
    3.  Öffnen Sie den ColumnHeader-Auflistungs-Editor, indem Sie auf die Auslassungspunkte (![von VisualStudioEllipsesButton](../../../../docs/framework/winforms/media/vbellipsesbutton.png "VbEllipsesButton")) in der <xref:System.Windows.Forms.ListView.Columns%2A> Eigenschaft**.** Fügen Sie drei Spalten hinzu, und legen Sie deren <xref:System.Windows.Forms.ColumnHeader.Text%2A> Eigenschaft `Name`, `Type`, und `Last Modified`bzw.. Klicken Sie auf **OK**, um das Dialogfeld zu schließen.  
  
    4.  Legen Sie die <xref:System.Windows.Forms.ListView.SmallImageList%2A>-Eigenschaft auf `imageList1.` fest.  
  
8.  Implementieren Sie den Code zum Auffüllen der <xref:System.Windows.Forms.TreeView> mit Knoten und untergeordneten Knoten. Fügen Sie diesen Code zur `Form1`-Klasse hinzu.  
  
     [!code-csharp[System.Windows.Forms.ExplorerStyleInterface#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ExplorerStyleInterface/CS/Form1.cs#1)]
     [!code-vb[System.Windows.Forms.ExplorerStyleInterface#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ExplorerStyleInterface/VB/Form1.vb#1)]  
  
9. Seit der vorherigen Code System.IO-Namespace verwendet, die entsprechende using- oder import-Anweisung am oberen Rand des Formulars.  
  
     [!code-csharp[System.Windows.Forms.ExplorerStyleInterface#4](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ExplorerStyleInterface/CS/Form1.cs#4)]
     [!code-vb[System.Windows.Forms.ExplorerStyleInterface#4](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ExplorerStyleInterface/VB/Form1.vb#4)]  
  
10. Rufen Sie die Setup-Methode aus dem vorherigen Schritt in den Konstruktor des Formulars oder <xref:System.Windows.Forms.Form.Load> Ereignisbehandlungsmethode. Fügen Sie diesen Code an den Formularkonstruktor.  
  
     [!code-csharp[System.Windows.Forms.ExplorerStyleInterface#2](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ExplorerStyleInterface/CS/Form1.cs#2)]
     [!code-vb[System.Windows.Forms.ExplorerStyleInterface#2](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ExplorerStyleInterface/VB/Form1.vb#2)]  
  
11. Behandeln der <xref:System.Windows.Forms.TreeView.NodeMouseClick> -Ereignis für `treeview1` **,** und implementieren Sie den Code zum Auffüllen `listview1` mit Inhalt des Knotens, wenn auf ein Knoten geklickt wird. Fügen Sie diesen Code zur `Form1`-Klasse hinzu.  
  
     [!code-csharp[System.Windows.Forms.ExplorerStyleInterface#3](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ExplorerStyleInterface/CS/Form1.cs#3)]
     [!code-vb[System.Windows.Forms.ExplorerStyleInterface#3](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ExplorerStyleInterface/VB/Form1.vb#3)]  
  
     Wenn Sie c# verwenden, stellen Sie sicher, dass die <xref:System.Windows.Forms.TreeView.NodeMouseClick> Ereignis mit seiner Ereignisbehandlungsmethode verknüpft ist. Fügen Sie diesen Code an den Formularkonstruktor.  
  
     [!code-csharp[System.Windows.Forms.ExplorerStyleInterface#5](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ExplorerStyleInterface/CS/Form1.cs#5)]  
  
## <a name="testing-the-application"></a>Testen der Anwendung  
 Sie können das Formular jetzt testen, um sicherzustellen, dass das Verhalten wie erwartet ausfällt.  
  
#### <a name="to-test-the-form"></a>So testen Sie das Formular  
  
-   Drücken Sie F5, um die Anwendung auszuführen.  
  
     Sehen Sie ein Formular mit Teilen einer <xref:System.Windows.Forms.TreeView> Steuerelement, das Projektverzeichnis auf der linken Seite anzeigt und eine <xref:System.Windows.Forms.ListView> Steuerelement auf der rechten Seite mit drei Spalten. Können Sie durchlaufen die <xref:System.Windows.Forms.TreeView> durch Auswahl der Directory-Knoten, und die <xref:System.Windows.Forms.ListView> wird mit dem Inhalt des ausgewählten Verzeichnisses aufgefüllt.  
  
## <a name="next-steps"></a>Nächste Schritte  
 Diese Anwendung bietet Ihnen eine Möglichkeit, Sie können, ein Beispiel für <xref:System.Windows.Forms.TreeView> und <xref:System.Windows.Forms.ListView> zusammen steuert. Weitere Informationen zu diesen Steuerelementen finden Sie unter den folgenden Themen:  
  
-   [Gewusst wie: Hinzufügen von benutzerdefinierten Daten zu einem TreeView- oder ListView-Steuerelement (Windows Forms)](../../../../docs/framework/winforms/controls/add-custom-information-to-a-treeview-or-listview-control-wf.md)  
  
-   [Gewusst wie: Hinzufügen von Suchfunktionen zu einem ListView-Steuerelement](../../../../docs/framework/winforms/controls/how-to-add-search-capabilities-to-a-listview-control.md)  
  
-   [Gewusst wie: Anfügen eines Kontextmenüs an einen Strukturansichtsknoten](../../../../docs/framework/winforms/controls/how-to-attach-a-shortcut-menu-to-a-treeview-node.md)  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Windows.Forms.ListView>  
 <xref:System.Windows.Forms.TreeView>  
 [ListView-Steuerelement](../../../../docs/framework/winforms/controls/listview-control-windows-forms.md)  
 [Gewusst wie: Hinzufügen oder Entfernen von Knoten mit dem TreeView-Steuerelement in Windows Forms](../../../../docs/framework/winforms/controls/how-to-add-and-remove-nodes-with-the-windows-forms-treeview-control.md)  
 [Gewusst wie: Hinzufügen und Entfernen von Elementen mit dem ListView-Steuerelement in Windows Forms](../../../../docs/framework/winforms/controls/how-to-add-and-remove-items-with-the-windows-forms-listview-control.md)  
 [Gewusst wie: Hinzufügen von Spalten zum ListView-Steuerelement in Windows Forms](../../../../docs/framework/winforms/controls/how-to-add-columns-to-the-windows-forms-listview-control.md)
