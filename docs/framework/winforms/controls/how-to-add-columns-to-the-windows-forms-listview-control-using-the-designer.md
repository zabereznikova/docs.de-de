---
title: "Gewusst wie: Hinzuf&#252;gen von Spalten zum ListView-Steuerelement in Windows&#160;Forms mithilfe des Designers | Microsoft Docs"
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
  - "Spalten [Windows Forms], Hinzufügen zu ListView-Steuerelementen"
  - "ListView-Steuerelement [Windows Forms], Hinzufügen von Spaltenkopfzeilen"
ms.assetid: 5b1a8b4d-587e-479a-95c1-f9b90884f13a
caps.latest.revision: 6
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 6
---
# Gewusst wie: Hinzuf&#252;gen von Spalten zum ListView-Steuerelement in Windows&#160;Forms mithilfe des Designers
Mit dem <xref:System.Windows.Forms.ListView>\-Steuerelement in Windows Forms können für jedes Listenelement mehrere Spalten angezeigt werden, sofern die **Detailansicht** aktiviert ist.  Unter Verwendung der Spalten können verschiedene Arten von Informationen über jedes Listenelement angezeigt werden.  So können in einer Dateiliste beispielsweise der Dateiname, der Dateityp, die Größe und das Datum der letzten Dateiänderung aufgenommen werden.  Weitere Informationen dazu, wie Sie Spalten nach dem Erstellen auffüllen, finden Sie unter [Gewusst wie: Anzeigen von Unterelementen in Spalten mit dem ListView\-Steuerelement in Windows Forms](../../../../docs/framework/winforms/controls/how-to-display-subitems-in-columns-with-the-windows-forms-listview-control.md).  
  
 Für das folgende Verfahren wird ein Projekt vom Typ **Windows\-Anwendung** mit einem Formular benötigt, das ein <xref:System.Windows.Forms.ListView>\-Steuerelement enthält.  Weitere Informationen zum Einrichten eines solchen Projekts finden Sie unter [How to: Create a Windows Application Project](http://msdn.microsoft.com/de-de/b2f93fed-c635-4705-8d0e-cf079a264efa) und [Gewusst wie: Hinzufügen von Steuerelementen zu Windows Forms](../../../../docs/framework/winforms/controls/how-to-add-controls-to-windows-forms.md).  
  
> [!NOTE]
>  Je nach den aktiven Einstellungen oder der Version unterscheiden sich die Dialogfelder und Menübefehle auf Ihrem Bildschirm möglicherweise von den in der Hilfe beschriebenen.  Wählen Sie im Menü **Extras** die Option **Einstellungen importieren und exportieren** aus, um die Einstellungen zu ändern.  Weitere Informationen finden Sie unter [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/de-de/22c4debb-4e31-47a8-8f19-16f328d7dcd3).  
  
### So fügen Sie im Designer Spalten hinzu  
  
1.  Legen Sie im **Eigenschaftenfenster** die <xref:System.Windows.Forms.ListView.View%2A>\-Eigenschaft des Steuerelements auf <xref:System.Windows.Forms.View> fest.  
  
2.  Klicken Sie im **Eigenschaftenfenster** auf die Schaltfläche mit dem **Auslassungszeichen** \(![VisualStudioEllipsesButton&#45;Bildschirmabbildung](../../../../docs/framework/winforms/media/vbellipsesbutton.png "vbEllipsesButton")\), die sich neben der <xref:System.Windows.Forms.ListView.Columns%2A>\-Eigenschaft befindet.  
  
     Der **ColumnHeader\-Auflistungs\-Editor** wird angezeigt.  
  
3.  Verwenden Sie die Schaltfläche **Hinzufügen**, um neue Spalten hinzuzufügen.  Anschließend können Sie den Spaltenheader auswählen und den Text \(die Spaltenbeschriftung\) sowie die Textausrichtung und die Breite festlegen.  
  
## Siehe auch  
 [Übersicht über das ListView\-Steuerelement](../../../../docs/framework/winforms/controls/listview-control-overview-windows-forms.md)   
 [Gewusst wie: Hinzufügen und Entfernen von Elementen mit dem ListView\-Steuerelement in Windows Forms](../../../../docs/framework/winforms/controls/how-to-add-and-remove-items-with-the-windows-forms-listview-control.md)   
 [Gewusst wie: Anzeigen von Unterelementen in Spalten mit dem ListView\-Steuerelement in Windows Forms](../../../../docs/framework/winforms/controls/how-to-display-subitems-in-columns-with-the-windows-forms-listview-control.md)   
 [Gewusst wie: Anzeigen von Symbolen für das ListView\-Steuerelement in Windows Forms](../../../../docs/framework/winforms/controls/how-to-display-icons-for-the-windows-forms-listview-control.md)   
 [Gewusst wie: Hinzufügen von benutzerdefinierten Daten zu einem TreeView\- oder ListView\-Steuerelement \(Windows Forms\)](../../../../docs/framework/winforms/controls/add-custom-information-to-a-treeview-or-listview-control-wf.md)