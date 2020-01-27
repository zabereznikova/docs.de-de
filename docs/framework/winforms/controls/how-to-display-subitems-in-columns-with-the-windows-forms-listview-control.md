---
title: Anzeigen von unter Elementen in Spalten mit dem ListView-Steuerelement
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
ms.openlocfilehash: 5c6d807410ad4ee0198d6334844bd65b148edff4
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/24/2020
ms.locfileid: "76745542"
---
# <a name="how-to-display-subitems-in-columns-with-the-windows-forms-listview-control"></a>Gewusst wie: Anzeigen von Unterelementen in Spalten mit dem ListView-Steuerelement in Windows Forms
Das Windows Forms <xref:System.Windows.Forms.ListView>-Steuerelement kann für jedes Element in der Detailansicht zusätzlichen Text oder unter Elemente anzeigen. In der ersten Spalte wird der Element Text angezeigt, z. b. eine Mitarbeiternummer. In den zweiten, dritten und nachfolgenden Spalten werden das erste, zweite und nachfolgende zugehörige Unterelement angezeigt.  
  
### <a name="to-add-subitems-to-a-list-item"></a>So fügen Sie einem Listenelement unter Elemente hinzu  
  
1. Fügen Sie alle benötigten Spalten hinzu. Da in der ersten Spalte die <xref:System.Windows.Forms.ListView.Text%2A>-Eigenschaft des Elements angezeigt wird, benötigen Sie eine weitere Spalte, als untergeordnete Elemente vorhanden sind. Weitere Informationen zum Hinzufügen von Spalten finden Sie unter Gewusst [wie: Hinzufügen von Spalten zum Windows Forms ListView-Steuer](how-to-add-columns-to-the-windows-forms-listview-control.md)Element.  
  
2. Ruft die <xref:System.Windows.Forms.ListViewItem.ListViewSubItemCollection.Add%2A>-Methode der Auflistung auf, die von der <xref:System.Windows.Forms.ListViewItem.SubItems%2A>-Eigenschaft eines Elements zurückgegeben wird. Im folgenden Codebeispiel werden der Mitarbeiter Name und die Abteilung für ein Listenelement festgelegt.  
  
     [!code-csharp[System.Windows.Forms.ListViewLegacyTopics#61](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/CS/Class1.cs#61)]
     [!code-vb[System.Windows.Forms.ListViewLegacyTopics#61](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/VB/Class1.vb#61)]  
  
## <a name="see-also"></a>Siehe auch

- [Übersicht über das ListView-Steuerelement](listview-control-overview-windows-forms.md)
- [Gewusst wie: Hinzufügen und Entfernen von Elementen mit dem ListView-Steuerelement in Windows Forms](how-to-add-and-remove-items-with-the-windows-forms-listview-control.md)
- [Gewusst wie: Hinzufügen von Spalten zum ListView-Steuerelement in Windows Forms](how-to-add-columns-to-the-windows-forms-listview-control.md)
- [Gewusst wie: Anzeigen von Symbolen für das ListView-Steuerelement in Windows Forms](how-to-display-icons-for-the-windows-forms-listview-control.md)
- [Gewusst wie: Hinzufügen von benutzerdefinierten Daten zu einem TreeView- oder ListView-Steuerelement (Windows Forms)](add-custom-information-to-a-treeview-or-listview-control-wf.md)
