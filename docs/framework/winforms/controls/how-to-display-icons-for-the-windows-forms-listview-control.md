---
title: 'Vorgehensweise: Anzeigen von Symbolen für das ListView-Steuerelement in Windows Forms'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ListView control [Windows Forms], displaying icons
- icons [Windows Forms], displaying for ListView controls
- lists [Windows Forms], displaying icons
- ImageList component [Windows Forms], with ListView control
- list views [Windows Forms], displaying icons
ms.assetid: 9d577542-8595-429b-99e5-078770ec9d35
ms.openlocfilehash: 80a827a88ac92008c7fe2a642d1d4b59a18f89da
ms.sourcegitcommit: c4e9d05644c9cb89de5ce6002723de107ea2e2c4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/19/2019
ms.locfileid: "65880406"
---
# <a name="how-to-display-icons-for-the-windows-forms-listview-control"></a>Vorgehensweise: Anzeigen von Symbolen für das ListView-Steuerelement in Windows Forms
Die Windows-Formulare <xref:System.Windows.Forms.ListView> Steuerelement kann Symbole aus einer Bildliste drei anzeigen. Die Liste, Details und SmallIcon Ansichten anzeigen von Bildern aus der Liste der Bilder in angegebenen die <xref:System.Windows.Forms.ListView.SmallImageList%2A> Eigenschaft. Die LargeIcon zeigt Bilder aus der Liste der Bilder in angegebenen die <xref:System.Windows.Forms.ListView.LargeImageList%2A> Eigenschaft. Eine Listenansicht kann auch einen zusätzlichen Satz von Symbolen, legen Sie im Anzeigen der <xref:System.Windows.Forms.ListView.StateImageList%2A> neben den großen oder kleinen Symbolen-Eigenschaft. Weitere Informationen zu Bildlisten, finden Sie unter [ImageList-Komponente](imagelist-component-windows-forms.md) und [Vorgehensweise: Hinzufügen oder Entfernen von Bildern mit der Windows Forms ImageList-Komponente](how-to-add-or-remove-images-with-the-windows-forms-imagelist-component.md).  
  
### <a name="to-display-images-in-a-list-view"></a>Zum Anzeigen von Bildern in einer Listenansicht  
  
1. Legen Sie die entsprechende Eigenschaft –<xref:System.Windows.Forms.ListView.SmallImageList%2A>, <xref:System.Windows.Forms.ListView.LargeImageList%2A>, oder <xref:System.Windows.Forms.ListView.StateImageList%2A>– mit dem vorhandenen <xref:System.Windows.Forms.ImageList> Komponente, die Sie verwenden möchten.  
  
     Diese Eigenschaften können im Designer mit dem Fenster "Eigenschaften" oder im Code festgelegt werden.  
  
     [!code-csharp[System.Windows.Forms.ListViewLegacyTopics#41](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/CS/Class1.cs#41)]
     [!code-vb[System.Windows.Forms.ListViewLegacyTopics#41](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/VB/Class1.vb#41)]  
  
2. Legen Sie die <xref:System.Windows.Forms.ListViewItem.ImageIndex%2A> oder <xref:System.Windows.Forms.ListViewItem.StateImageIndex%2A> -Eigenschaft für jedes Listenelement, das ein zugeordnetes Symbol verfügt.  
  
     Diese Eigenschaften können festgelegt werden, im Code oder in der **ListViewItem Auflistungs-Editor**. Zum Öffnen der **ListViewItem Auflistungs-Editor**, klicken Sie auf die Schaltfläche mit den Auslassungspunkten (![die Auslassungszeichen (...) im Eigenschaftenfenster von Visual Studio](./media/visual-studio-ellipsis-button.png)) neben der <xref:System.Windows.Forms.ListView.Items%2A> Eigenschaft für die **Eigenschaften** Fenster.  
  
     [!code-csharp[System.Windows.Forms.ListViewLegacyTopics#42](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/CS/Class1.cs#42)]
     [!code-vb[System.Windows.Forms.ListViewLegacyTopics#42](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/VB/Class1.vb#42)]  
  
## <a name="see-also"></a>Siehe auch

- [Übersicht über das ListView-Steuerelement](listview-control-overview-windows-forms.md)
- [Vorgehensweise: Hinzufügen und Entfernen von Elementen mit dem ListView-Steuerelement in Windows Forms](how-to-add-and-remove-items-with-the-windows-forms-listview-control.md)
- [Vorgehensweise: Hinzufügen von Spalten zu dem ListView-Steuerelement in Windows Forms](how-to-add-columns-to-the-windows-forms-listview-control.md)
- [Vorgehensweise: Hinzufügen von benutzerdefinierten Daten zu einem TreeView- oder ListView-Steuerelement (Windows Forms)](add-custom-information-to-a-treeview-or-listview-control-wf.md)
- [ImageList-Komponente](imagelist-component-windows-forms.md)
