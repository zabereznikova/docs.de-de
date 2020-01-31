---
title: Hinzufügen und Entfernen von Elementen mit ListView-Steuerelement
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ListView control [Windows Forms], populating
- list views [Windows Forms], adding list items
- ListView control [Windows Forms], adding list items
ms.assetid: 1b35a80a-edd8-495f-a807-a28c4aae52c6
ms.openlocfilehash: bbfe99db857ebe3a80bf99926f3ce0bec38a1f3f
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/24/2020
ms.locfileid: "76743142"
---
# <a name="how-to-add-and-remove-items-with-the-windows-forms-listview-control"></a>Gewusst wie: Hinzufügen und Entfernen von Elementen mit dem ListView-Steuerelement in Windows Forms
Das Hinzufügen eines Elements zu einem Windows Forms <xref:System.Windows.Forms.ListView> Steuerelement besteht hauptsächlich darin, das Element anzugeben und ihm Eigenschaften zuzuweisen. Das Hinzufügen oder Entfernen von Listenelementen ist jederzeit möglich.  
  
### <a name="to-add-items-programmatically"></a>So fügen Sie Elemente Programm gesteuert hinzu  
  
1. Verwenden Sie die <xref:System.Windows.Forms.ListView.ListViewItemCollection.Add%2A>-Methode der <xref:System.Windows.Forms.ListView.Items%2A>-Eigenschaft.  
  
     [!code-csharp[System.Windows.Forms.ListViewLegacyTopics#11](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/CS/Class1.cs#11)]
     [!code-vb[System.Windows.Forms.ListViewLegacyTopics#11](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/VB/Class1.vb#11)]  
  
### <a name="to-remove-items-programmatically"></a>So entfernen Sie Elemente Programm gesteuert  
  
1. Verwenden Sie die <xref:System.Windows.Forms.ListView.ListViewItemCollection.RemoveAt%2A>-oder <xref:System.Windows.Forms.ListView.ListViewItemCollection.Clear%2A>-Methode der <xref:System.Windows.Forms.ListView.Items%2A>-Eigenschaft. Die <xref:System.Windows.Forms.ListView.ListViewItemCollection.RemoveAt%2A>-Methode entfernt ein einzelnes Element. mit der <xref:System.Windows.Forms.ListView.ListViewItemCollection.Clear%2A>-Methode werden alle Elemente aus der Liste entfernt.  
  
     [!code-csharp[System.Windows.Forms.ListViewLegacyTopics#12](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/CS/Class1.cs#12)]
     [!code-vb[System.Windows.Forms.ListViewLegacyTopics#12](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/VB/Class1.vb#12)]  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Windows.Forms.ListView>
- [ListView-Steuerelement](listview-control-windows-forms.md)
- [Übersicht über das ListView-Steuerelement](listview-control-overview-windows-forms.md)
