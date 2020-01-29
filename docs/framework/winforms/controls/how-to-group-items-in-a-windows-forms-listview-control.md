---
title: Gruppieren von Elementen im ListView-Steuerelement
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
ms.openlocfilehash: 45846751780f433c29b186fe8b9a908f5d295ab3
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/24/2020
ms.locfileid: "76736625"
---
# <a name="how-to-group-items-in-a-windows-forms-listview-control"></a>Gewusst wie: Gruppieren von Elementen in einem ListView-Steuerelement in Windows Forms
Mit der Gruppierungs Funktion des <xref:System.Windows.Forms.ListView>-Steuer Elements können Sie Verwandte Gruppen von Elementen in Gruppen anzeigen. Diese Gruppen werden auf dem Bildschirm durch horizontale Gruppen Kopfzeilen getrennt, die die Gruppentitel enthalten. Sie können <xref:System.Windows.Forms.ListView> Gruppen verwenden, um die Navigation durch große Listen zu vereinfachen, indem Sie Elemente alphabetisch, nach Datum oder nach einer anderen logischen Gruppierung gruppieren. Die folgende Abbildung zeigt einige gruppierte Elemente.  
  
 ![Screenshot von ungeraden und geraden ListView-Gruppen.](./media/how-to-group-items-in-a-windows-forms-listview-control-using-the-designer/odd-even-list-view-groups.gif)  
   
 Um die Gruppierung zu aktivieren, müssen Sie zuerst eine oder mehrere Gruppen entweder im Designer oder Programm gesteuert erstellen. Nachdem eine Gruppe definiert wurde, können Sie <xref:System.Windows.Forms.ListView> Elemente Gruppen zuweisen. Sie können Elemente auch Programm gesteuert aus einer Gruppe in eine andere verschieben.  
  
### <a name="to-add-groups"></a>So fügen Sie Gruppen hinzu  
  
1. Verwenden Sie die <xref:System.Windows.Forms.ListViewGroupCollection.Add%2A> -Methode der <xref:System.Windows.Forms.ListView.Groups%2A> -Auflistung.  
  
     [!code-csharp[System.Windows.Forms.ListViewLegacyTopics#21](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/CS/Class1.cs#21)]
     [!code-vb[System.Windows.Forms.ListViewLegacyTopics#21](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/VB/Class1.vb#21)]  
  
### <a name="to-remove-groups"></a>So entfernen Sie Gruppen  
  
1. Verwenden Sie die <xref:System.Windows.Forms.ListViewGroupCollection.RemoveAt%2A>-oder <xref:System.Windows.Forms.ListViewGroupCollection.Clear%2A>-Methode der <xref:System.Windows.Forms.ListView.Groups%2A> Auflistung.  
  
     Mit der <xref:System.Windows.Forms.ListViewGroupCollection.RemoveAt%2A>-Methode wird eine einzelne Gruppe entfernt. mit der <xref:System.Windows.Forms.ListViewGroupCollection.Clear%2A>-Methode werden alle Gruppen aus der Liste entfernt.  
  
    > [!NOTE]
    > Durch das Entfernen einer Gruppe werden die Elemente in dieser Gruppe nicht entfernt.  
  
     [!code-csharp[System.Windows.Forms.ListViewLegacyTopics#22](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/CS/Class1.cs#22)]
     [!code-vb[System.Windows.Forms.ListViewLegacyTopics#22](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/VB/Class1.vb#22)]  
  
### <a name="to-assign-items-to-groups-or-move-items-between-groups"></a>So weisen Sie Gruppenelemente zu oder Verschieben Elemente zwischen Gruppen  
  
1. Legen Sie die <xref:System.Windows.Forms.ListViewItem.Group%2A?displayProperty=nameWithType>-Eigenschaft einzelner Elemente fest.  
  
     [!code-csharp[System.Windows.Forms.ListViewLegacyTopics#23](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/CS/Class1.cs#23)]
     [!code-vb[System.Windows.Forms.ListViewLegacyTopics#23](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/VB/Class1.vb#23)]  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Windows.Forms.ListView>
- <xref:System.Windows.Forms.ListView.Groups%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.ListViewGroup>
- [ListView-Steuerelement](listview-control-windows-forms.md)
- [Übersicht über das ListView-Steuerelement](listview-control-overview-windows-forms.md)
- [Gewusst wie: Hinzufügen und Entfernen von Elementen mit dem ListView-Steuerelement in Windows Forms](how-to-add-and-remove-items-with-the-windows-forms-listview-control.md)
