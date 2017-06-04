---
title: "Exemplarische Vorgehensweise: Erstellen einer Explorer-&#228;hnlichen Schnittstelle mit dem ListView-Steuerelement und dem TreeView-Steuerelement im Designer | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "Explorer-ähnliche Anwendungen"
  - "Explorer-ähnliche Anwendungen, Exemplarische Vorgehensweisen"
  - "ListView-Steuerelement [Windows Forms], Explorer-ähnliche Schnittstelle"
  - "ListView-Steuerelement [Windows Forms], Explorer-style-Schnittstelle"
  - "ListView-Steuerelement [Windows Forms], TreeView-Steuerelemente verwendet mit"
  - "TreeView-Steuerelement [Windows Forms], ListView-Steuerelemente verwendet mit"
  - "TreeView-Steuerelement [Windows Forms], Verwenden für Explorer-ähnliche Schnittstelle"
ms.assetid: 9e5e7721-19e2-4890-b273-a43589fe99ff
caps.latest.revision: 19
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 19
---
# Exemplarische Vorgehensweise: Erstellen einer Explorer-&#228;hnlichen Schnittstelle mit dem ListView-Steuerelement und dem TreeView-Steuerelement im Designer
Einer der Vorteile von Visual Studio ist die Möglichkeit, in kurzer Zeit professionell aussehende Windows Forms\-Anwendungen zu erstellen.  Ein häufiges Szenario ist die Erstellung einer Benutzeroberfläche \(UI\) mit dem <xref:System.Windows.Forms.ListView>\-Steuerelement und dem <xref:System.Windows.Forms.TreeView>\-Steuerelement, die vergleichbar ist mit dem Windows Explorer\-Feature von Windows\-Betriebssystemen.  Windows Explorer zeigt auf dem Computer eines Benutzers eine hierarchische Struktur der Dateien und Ordner an.  
  
> [!NOTE]
>  Je nach den aktiven Einstellungen oder der Version unterscheiden sich die Dialogfelder und Menübefehle auf Ihrem Bildschirm möglicherweise von den in der Hilfe beschriebenen.  Wählen Sie im Menü **Extras** die Option **Einstellungen importieren und exportieren** aus, um die Einstellungen zu ändern.  Weitere Informationen finden Sie unter [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/de-de/22c4debb-4e31-47a8-8f19-16f328d7dcd3).  
  
### So erstellen Sie das Formular, das ein ListView\-Steuerelement und ein TreeView\-Steuerelement enthält  
  
1.  Zeigen Sie im Menü **Datei** auf **Neu**, und klicken Sie dann auf **Projekt**.  
  
2.  Gehen Sie im Dialogfeld **Neues Projekt** wie folgt vor:  
  
    1.  Wählen Sie in den Kategorien **Visual Basic** oder **Visual C\#** aus.  
  
    2.  Wählen Sie in der Liste der Vorlagen **Windows Forms\-Anwendung** aus.  
  
3.  Klicken Sie auf **OK**.  Ein neues Windows Forms\-Projekt wird erstellt.  
  
4.  Fügen Sie dem Formular ein <xref:System.Windows.Forms.SplitContainer>\-Steuerelement hinzu, und legen Sie seine <xref:System.Windows.Forms.SplitContainer.Dock%2A>\-Eigenschaft auf <xref:System.Windows.Forms.DockStyle> fest.  
  
5.  Fügen Sie dem Formular ein <xref:System.Windows.Forms.ImageList>\-Element mit dem Namen `imageList1` hinzu, und fügen Sie mit dem Eigenschaftenfenster zwei Bilder hinzu: ein Ordnerbild und ein Dokumentbild.  
  
6.  Fügen Sie dem Formular ein <xref:System.Windows.Forms.TreeView>\-Steuerelement mit dem Namen `treeview1` hinzu, und positionieren Sie es auf der linken Seite des <xref:System.Windows.Forms.SplitContainer>\-Steuerelements.  Führen Sie im Eigenschaftenfenster für `treeView1` folgende Aktionen aus:  
  
    1.  Legen Sie die <xref:System.Windows.Forms.Control.Dock%2A>\-Eigenschaft auf <xref:System.Windows.Forms.DockStyle> fest.  
  
    2.  Legen Sie die <xref:System.Windows.Forms.TreeView.ImageList%2A>\-Eigenschaft auf `imagelist1.` fest.  
  
7.  Fügen Sie dem Formular ein <xref:System.Windows.Forms.ListView>\-Steuerelement mit dem Namen `listView1` hinzu, und positionieren Sie es auf der rechten Seite des <xref:System.Windows.Forms.SplitContainer>\-Steuerelements.  Führen Sie im Eigenschaftenfenster für `listview1` folgende Aktionen aus:  
  
    1.  Legen Sie die <xref:System.Windows.Forms.Control.Dock%2A>\-Eigenschaft auf <xref:System.Windows.Forms.DockStyle> fest.  
  
    2.  Legen Sie die <xref:System.Windows.Forms.ListView.View%2A>\-Eigenschaft auf <xref:System.Windows.Forms.View> fest.  
  
    3.  Öffnen Sie den ColumnHeader\-Auflistungs\-Editor, indem Sie auf die Auslassungszeichen \(![VisualStudioEllipsesButton&#45;Bildschirmabbildung](../../../../docs/framework/winforms/media/vbellipsesbutton.png "vbEllipsesButton")\) in der <xref:System.Windows.Forms.ListView.Columns%2A>\-Eigenschaft klicken. Fügen Sie drei Spalten hinzu, und legen Sie ihre <xref:System.Windows.Forms.ColumnHeader.Text%2A>\-Eigenschaft auf `Name`, `Type` bzw. `Last Modified` fest.  Klicken Sie auf **OK**, um das Dialogfeld zu schließen.  
  
    4.  Legen Sie die <xref:System.Windows.Forms.ListView.SmallImageList%2A>\-Eigenschaft auf `imageList1.` fest.  
  
8.  Implementieren Sie den Code, um die <xref:System.Windows.Forms.TreeView> mit Knoten und untergeordneten Knoten zu füllen.  Fügen Sie diesen Code zur `Form1`\-Klasse hinzu.  
  
     [!code-csharp[System.Windows.Forms.ExplorerStyleInterface#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ExplorerStyleInterface/CS/Form1.cs#1)]
     [!code-vb[System.Windows.Forms.ExplorerStyleInterface#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ExplorerStyleInterface/VB/Form1.vb#1)]  
  
9. Da vom vorherigen Code der Namespace System.IO verwendet wird, muss die entsprechende using\- oder import\-Anweisung an den Anfang des Formulars eingefügt werden.  
  
     [!code-csharp[System.Windows.Forms.ExplorerStyleInterface#4](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ExplorerStyleInterface/CS/Form1.cs#4)]
     [!code-vb[System.Windows.Forms.ExplorerStyleInterface#4](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ExplorerStyleInterface/VB/Form1.vb#4)]  
  
10. Rufen Sie die Einrichtungsmethode aus dem vorherigen Schritt im Konstruktor oder in der <xref:System.Windows.Forms.Form.Load>\-Ereignisbehandlungsmethode des Formulars auf.  Fügen Sie diesen Code zum Formularkonstruktor hinzu.  
  
     [!code-csharp[System.Windows.Forms.ExplorerStyleInterface#2](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ExplorerStyleInterface/CS/Form1.cs#2)]
     [!code-vb[System.Windows.Forms.ExplorerStyleInterface#2](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ExplorerStyleInterface/VB/Form1.vb#2)]  
  
11. Behandeln Sie das <xref:System.Windows.Forms.TreeView.NodeMouseClick>\-Ereignis für `treeview1`**,** und implementieren Sie den Code, um`listview1`mit dem Inhalt eines Knotenszu füllen, sobald auf einen Knoten geklickt wird.  Fügen Sie diesen Code zur `Form1`\-Klasse hinzu.  
  
     [!code-csharp[System.Windows.Forms.ExplorerStyleInterface#3](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ExplorerStyleInterface/CS/Form1.cs#3)]
     [!code-vb[System.Windows.Forms.ExplorerStyleInterface#3](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ExplorerStyleInterface/VB/Form1.vb#3)]  
  
     Stellen Sie beim Verwenden von C\# sicher, dass Sie das <xref:System.Windows.Forms.TreeView.NodeMouseClick>\-Ereignis mit der entsprechenden Ereignisbehandlungsmethode verknüpft haben.  Fügen Sie diesen Code zum Formularkonstruktor hinzu.  
  
     [!code-csharp[System.Windows.Forms.ExplorerStyleInterface#5](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ExplorerStyleInterface/CS/Form1.cs#5)]  
  
## Testen der Anwendung  
 Sie können das Formular jetzt testen und prüfen, ob es sich wie wie erwartet verhält.  
  
#### So testen Sie das Formular  
  
-   Drücken Sie F5, um die Anwendung auszuführen.  
  
     Sie erhalten ein getrenntes Formular mit einem <xref:System.Windows.Forms.TreeView>\-Steuerelement, das Ihr Projektverzeichnis auf der linken Seite und ein <xref:System.Windows.Forms.ListView>\-Steuerelement auf der rechten Seite sowie drei Spalten anzeigt.  Sie können durch das <xref:System.Windows.Forms.TreeView>\-Element navigieren, indem Sie Verzeichnisknoten auswählen. Dabei wird das <xref:System.Windows.Forms.ListView>\-Element mit dem Inhalt des ausgewählten Verzeichnisses gefüllt.  
  
## Nächste Schritte  
 Diese Anwendung ist ein Beispiel dafür, wie Sie das <xref:System.Windows.Forms.TreeView>\-Steuerelement und das <xref:System.Windows.Forms.ListView>\-Steuerelement zusammen verwenden können.  Weitere Informationen über diese Steuerelemente finden Sie unter den folgenden Themen:  
  
-   [Gewusst wie: Hinzufügen von benutzerdefinierten Daten zu einem TreeView\- oder ListView\-Steuerelement \(Windows Forms\)](../../../../docs/framework/winforms/controls/add-custom-information-to-a-treeview-or-listview-control-wf.md)  
  
-   [Gewusst wie: Hinzufügen von Suchfunktionen zu einem ListView\-Steuerelement](../../../../docs/framework/winforms/controls/how-to-add-search-capabilities-to-a-listview-control.md)  
  
-   [Gewusst wie: Anfügen eines Kontextmenüs an einen Strukturansichtsknoten](../../../../docs/framework/winforms/controls/how-to-attach-a-shortcut-menu-to-a-treeview-node.md)  
  
## Siehe auch  
 <xref:System.Windows.Forms.ListView>   
 <xref:System.Windows.Forms.TreeView>   
 [ListView\-Steuerelement](../../../../docs/framework/winforms/controls/listview-control-windows-forms.md)   
 [Gewusst wie: Hinzufügen oder Entfernen von Knoten mit dem TreeView\-Steuerelement in Windows Forms](../../../../docs/framework/winforms/controls/how-to-add-and-remove-nodes-with-the-windows-forms-treeview-control.md)   
 [Gewusst wie: Hinzufügen und Entfernen von Elementen mit dem ListView\-Steuerelement in Windows Forms](../../../../docs/framework/winforms/controls/how-to-add-and-remove-items-with-the-windows-forms-listview-control.md)   
 [Gewusst wie: Hinzufügen von Spalten zum ListView\-Steuerelement in Windows Forms](../../../../docs/framework/winforms/controls/how-to-add-columns-to-the-windows-forms-listview-control.md)