---
title: "Gewusst wie: Anzeigen von Symbolen f&#252;r das ListView-Steuerelement in Windows&#160;Forms | Microsoft Docs"
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
  - "Symbole, Anzeigen für ListView-Steuerelemente"
  - "ImageList-Komponente [Windows Forms], Mit ListView-Steuerelement"
  - "Listenansichten, Anzeigen von Symbolen"
  - "Listen, Anzeigen von Symbolen"
  - "ListView-Steuerelement [Windows Forms], Anzeigen von Symbolen"
ms.assetid: 9d577542-8595-429b-99e5-078770ec9d35
caps.latest.revision: 15
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 15
---
# Gewusst wie: Anzeigen von Symbolen f&#252;r das ListView-Steuerelement in Windows&#160;Forms
Mit dem <xref:System.Windows.Forms.ListView>\-Steuerelement in Windows Forms können Symbole aus drei Bildlisten angezeigt werden.  In den Ansichten List, Details und Smalllcon werden Bilder aus der in der <xref:System.Windows.Forms.ListView.SmallImageList%2A>\-Eigenschaft angegebenen Bildliste angezeigt.  In der LargeIcon\-Ansicht werden Bilder aus der Bildliste angezeigt, die in der <xref:System.Windows.Forms.ListView.LargeImageList%2A>\-Eigenschaft angegeben ist.  In einer Listenansicht kann neben den großen oder kleinen Symbolen außerdem ein zusätzlicher Satz von Symbolen angezeigt werden, der in der <xref:System.Windows.Forms.ListView.StateImageList%2A>\-Eigenschaft festgelegt ist.  Weitere Informationen über Bildlisten finden Sie unter [ImageList\-Komponente](../../../../docs/framework/winforms/controls/imagelist-component-windows-forms.md) und [Gewusst wie: Hinzufügen oder Entfernen von Bildern mit der ImageList\-Komponente in Windows Forms](../../../../docs/framework/winforms/controls/how-to-add-or-remove-images-with-the-windows-forms-imagelist-component.md).  
  
### So zeigen Sie Bilder in einer Listenansicht an  
  
1.  Legen Sie für die geeignete Eigenschaft – <xref:System.Windows.Forms.ListView.SmallImageList%2A>, <xref:System.Windows.Forms.ListView.LargeImageList%2A> oder <xref:System.Windows.Forms.ListView.StateImageList%2A> – die vorhandene <xref:System.Windows.Forms.ImageList>\-Komponente fest, die Sie verwenden möchten.  
  
     Diese Eigenschaften können entweder im Eigenschaftenfenster des Designers oder programmgesteuert festgelegt werden.  
  
     [!code-csharp[System.Windows.Forms.ListViewLegacyTopics#41](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/CS/Class1.cs#41)]
     [!code-vb[System.Windows.Forms.ListViewLegacyTopics#41](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/VB/Class1.vb#41)]  
  
2.  Legen Sie die Eigenschaft <xref:System.Windows.Forms.ListViewItem.ImageIndex%2A> oder <xref:System.Windows.Forms.ListViewItem.StateImageIndex%2A> für jedes Listenelement fest, das mit einem Symbol verknüpft ist.  
  
     Diese Eigenschaften können entweder programmgesteuert oder innerhalb des **ListViewItem\-Auflistungs\-Editors** festgelegt werden.  Klicken Sie im **Eigenschaftenfenster** neben der <xref:System.Windows.Forms.ListView.Items%2A>\-Eigenschaft auf die Schaltfläche mit den drei Punkten \(![VisualStudioEllipsesButton&#45;Bildschirmabbildung](../../../../docs/framework/winforms/media/vbellipsesbutton.png "vbEllipsesButton")\), um den **ListViewItem\-Auflistungs\-Editors** zu öffnen.  
  
     [!code-csharp[System.Windows.Forms.ListViewLegacyTopics#42](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/CS/Class1.cs#42)]
     [!code-vb[System.Windows.Forms.ListViewLegacyTopics#42](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/VB/Class1.vb#42)]  
  
## Siehe auch  
 [Übersicht über das ListView\-Steuerelement](../../../../docs/framework/winforms/controls/listview-control-overview-windows-forms.md)   
 [Gewusst wie: Hinzufügen und Entfernen von Elementen mit dem ListView\-Steuerelement in Windows Forms](../../../../docs/framework/winforms/controls/how-to-add-and-remove-items-with-the-windows-forms-listview-control.md)   
 [Gewusst wie: Hinzufügen von Spalten zum ListView\-Steuerelement in Windows Forms](../../../../docs/framework/winforms/controls/how-to-add-columns-to-the-windows-forms-listview-control.md)   
 [Gewusst wie: Hinzufügen von benutzerdefinierten Daten zu einem TreeView\- oder ListView\-Steuerelement \(Windows Forms\)](../../../../docs/framework/winforms/controls/add-custom-information-to-a-treeview-or-listview-control-wf.md)   
 [ImageList\-Komponente](../../../../docs/framework/winforms/controls/imagelist-component-windows-forms.md)