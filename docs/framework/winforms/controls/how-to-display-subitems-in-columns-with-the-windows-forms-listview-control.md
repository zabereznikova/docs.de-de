---
title: 'Vorgehensweise: Anzeigen von Unterelementen in Spalten mit dem ListView-Steuerelement in Windows Forms'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- list items
- Details view
- ListView control [Windows Forms], adding ListSubItems
- subitems
ms.assetid: e465f044-cde7-4fd9-a687-788a73a0f554
ms.openlocfilehash: defa8aa736927c9076eb2410d6d914a8f7550d03
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59183715"
---
# <a name="how-to-display-subitems-in-columns-with-the-windows-forms-listview-control"></a>Vorgehensweise: Anzeigen von Unterelementen in Spalten mit dem ListView-Steuerelement in Windows Forms
Die Windows-Formulare <xref:System.Windows.Forms.ListView> Steuerelement kann zusätzliche Text oder Unterelemente, für jedes Element in der Ansicht anzeigen. Die erste Spalte zeigt den Elementtext, z. B. eine Mitarbeiternummer. Der zweite, dritte und die nachfolgenden Spalten anzeigen die erste, zweite und nachfolgende zugeordneten Unterelemente.  
  
### <a name="to-add-subitems-to-a-list-item"></a>Unterelemente für ein Listenelement hinzufügen  
  
1.  Fügen Sie alle benötigten Spalten hinzu. Da die erste Spalte des Elements anzeigt <xref:System.Windows.Forms.ListView.Text%2A> -Eigenschaft, benötigen Sie eine Spalte mehr als Unterelemente vorhanden sind. Weitere Informationen zum Hinzufügen von Spalten finden Sie unter [Vorgehensweise: Hinzufügen von Spalten, die Windows Forms-ListView-Steuerelement](how-to-add-columns-to-the-windows-forms-listview-control.md).  
  
2.  Rufen Sie die <xref:System.Windows.Forms.ListViewItem.ListViewSubItemCollection.Add%2A> -Methode der Auflistung zurückgegeben werden, indem die <xref:System.Windows.Forms.ListViewItem.SubItems%2A> Eigenschaft eines Elements. Das folgende Codebeispiel legt fest, der Employee Name "und" Department für ein Listenelement.  
  
     [!code-csharp[System.Windows.Forms.ListViewLegacyTopics#61](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/CS/Class1.cs#61)]
     [!code-vb[System.Windows.Forms.ListViewLegacyTopics#61](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/VB/Class1.vb#61)]  
  
## <a name="see-also"></a>Siehe auch

- [Übersicht über das ListView-Steuerelement](listview-control-overview-windows-forms.md)
- [Vorgehensweise: Hinzufügen und Entfernen von Elementen mit dem ListView-Steuerelement in Windows Forms](how-to-add-and-remove-items-with-the-windows-forms-listview-control.md)
- [Vorgehensweise: Hinzufügen von Spalten zum ListView-Steuerelement in Windows Forms](how-to-add-columns-to-the-windows-forms-listview-control.md)
- [Vorgehensweise: Anzeigen von Symbolen für das ListView-Steuerelement in Windows Forms](how-to-display-icons-for-the-windows-forms-listview-control.md)
- [Vorgehensweise: Hinzufügen von benutzerdefinierten Daten zu einem TreeView- oder ListView-Steuerelement (Windows Forms)](add-custom-information-to-a-treeview-or-listview-control-wf.md)
