---
title: Gruppieren von Elementen in ListView Control
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ListView control [Windows Forms], grouping items
- lists [Windows Forms], grouping items
- grouping
- list views [Windows Forms], grouping items
- groups
- groups [Windows Forms], in Windows Forms controls
ms.assetid: 610416a1-8da4-436c-af19-5f19e654769b
ms.openlocfilehash: a1754d10de2bbb5895ae861cd17f4af1f18810e2
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79141990"
---
# <a name="how-to-group-items-in-a-windows-forms-listview-control"></a>Gewusst wie: Gruppieren von Elementen in einem ListView-Steuerelement in Windows Forms
Mit der Gruppierungsfunktion <xref:System.Windows.Forms.ListView> des Steuerelements können Sie verwandte Elementesätze in Gruppen anzeigen. Diese Gruppen werden auf dem Bildschirm durch horizontale Gruppenüberschriften getrennt, die die Gruppentitel enthalten. Sie können <xref:System.Windows.Forms.ListView> Gruppen verwenden, um das Navigieren in großen Listen zu vereinfachen, indem Sie Elemente alphabetisch, nach Datum oder nach anderen logischen Gruppierungen gruppieren. Die folgende Abbildung zeigt einige gruppierte Elemente.  
  
 ![Screenshot von ungeraden und sogar ListView-Gruppen.](./media/how-to-group-items-in-a-windows-forms-listview-control-using-the-designer/odd-even-list-view-groups.gif)  

 Um die Gruppierung zu aktivieren, müssen Sie zunächst eine oder mehrere Gruppen entweder im Designer oder programmgesteuert erstellen. Nachdem eine Gruppe definiert wurde, <xref:System.Windows.Forms.ListView> können Sie Gruppen Artikel zuweisen. Sie können Elemente auch programmgesteuert von einer Gruppe in eine andere verschieben.  
  
### <a name="to-add-groups"></a>So fügen Sie Gruppen hinzu  
  
1. Verwenden Sie die <xref:System.Windows.Forms.ListViewGroupCollection.Add%2A> -Methode der <xref:System.Windows.Forms.ListView.Groups%2A> -Auflistung.  
  
     [!code-csharp[System.Windows.Forms.ListViewLegacyTopics#21](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/CS/Class1.cs#21)]
     [!code-vb[System.Windows.Forms.ListViewLegacyTopics#21](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/VB/Class1.vb#21)]  
  
### <a name="to-remove-groups"></a>So entfernen Sie Gruppen  
  
1. Verwenden <xref:System.Windows.Forms.ListViewGroupCollection.RemoveAt%2A> Sie <xref:System.Windows.Forms.ListViewGroupCollection.Clear%2A> die <xref:System.Windows.Forms.ListView.Groups%2A> oder-Methode der Auflistung.  
  
     Die <xref:System.Windows.Forms.ListViewGroupCollection.RemoveAt%2A> Methode entfernt eine einzelne Gruppe. Die <xref:System.Windows.Forms.ListViewGroupCollection.Clear%2A> Methode entfernt alle Gruppen aus der Liste.  
  
    > [!NOTE]
    > Durch das Entfernen einer Gruppe werden die Elemente innerhalb dieser Gruppe nicht entfernt.  
  
     [!code-csharp[System.Windows.Forms.ListViewLegacyTopics#22](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/CS/Class1.cs#22)]
     [!code-vb[System.Windows.Forms.ListViewLegacyTopics#22](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/VB/Class1.vb#22)]  
  
### <a name="to-assign-items-to-groups-or-move-items-between-groups"></a>So weisen Sie Gruppen Elemente zu oder verschieben Elemente zwischen Gruppen  
  
1. Legen <xref:System.Windows.Forms.ListViewItem.Group%2A?displayProperty=nameWithType> Sie die Eigenschaft einzelner Elemente fest.  
  
     [!code-csharp[System.Windows.Forms.ListViewLegacyTopics#23](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/CS/Class1.cs#23)]
     [!code-vb[System.Windows.Forms.ListViewLegacyTopics#23](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/VB/Class1.vb#23)]  
  
## <a name="see-also"></a>Weitere Informationen

- <xref:System.Windows.Forms.ListView>
- <xref:System.Windows.Forms.ListView.Groups%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.ListViewGroup>
- [ListView-Steuerelement](listview-control-windows-forms.md)
- [Übersicht über das ListView-Steuerelement](listview-control-overview-windows-forms.md)
- [Gewusst wie: Hinzufügen und Entfernen von Elementen mit dem ListView-Steuerelement in Windows Forms](how-to-add-and-remove-items-with-the-windows-forms-listview-control.md)
