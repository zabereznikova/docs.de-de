---
title: 'Vorgehensweise: Gruppieren von Elementen in einem ListView-Steuerelement in Windows Forms'
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
ms.openlocfilehash: 3a070db6c580f0f3798e52b1afbe0ee36947aeb1
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59091537"
---
# <a name="how-to-group-items-in-a-windows-forms-listview-control"></a>Vorgehensweise: Gruppieren von Elementen in einem ListView-Steuerelement in Windows Forms
Mit der Grouping-Funktion von der <xref:System.Windows.Forms.ListView> -Steuerelement, können Sie verwandte Elemente in Gruppen anzeigen. Diese Gruppen werden auf dem Bildschirm durch horizontale Gruppenheader getrennt, die die Gruppentitel enthalten. Sie können <xref:System.Windows.Forms.ListView> Gruppen zum Navigieren in umfangreichen Listen einfacher durch Gruppieren von Elementen alphabetisch nach Datum oder eine beliebige andere logische Gruppierung. Die folgende Abbildung zeigt einige gruppierte Elemente.  
  
 ![ListView-Gruppen](./media/listviewgroups.gif "ListViewGroups")  
ListView in gruppierten Elementen  
  
 Aktivieren der Gruppierung, müssen Sie zunächst eine oder mehrere Gruppen im Designer oder programmgesteuert erstellen. Nachdem eine Gruppe definiert wurde, können Sie zuweisen <xref:System.Windows.Forms.ListView> Elemente, die Gruppen. Sie können auch Elemente aus einer Gruppe in eine andere programmgesteuert verschieben.  
  
> [!NOTE]
>  <xref:System.Windows.Forms.ListView> Gruppen stehen nur auf [!INCLUDE[WinXpFamily](../../../../includes/winxpfamily-md.md)] bei einem Aufruf der <xref:System.Windows.Forms.Application.EnableVisualStyles%2A?displayProperty=nameWithType> Methode. Unter früheren Betriebssystemen Code im Zusammenhang mit Gruppen hat keine Auswirkungen, und die Gruppen werden nicht angezeigt. Weitere Informationen finden Sie unter <xref:System.Windows.Forms.ListView.Groups%2A?displayProperty=nameWithType>.  
  
### <a name="to-add-groups"></a>Beim Hinzufügen von Gruppen  
  
1.  Verwenden Sie die <xref:System.Windows.Forms.ListViewGroupCollection.Add%2A> -Methode der <xref:System.Windows.Forms.ListView.Groups%2A> -Auflistung.  
  
     [!code-csharp[System.Windows.Forms.ListViewLegacyTopics#21](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/CS/Class1.cs#21)]
     [!code-vb[System.Windows.Forms.ListViewLegacyTopics#21](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/VB/Class1.vb#21)]  
  
### <a name="to-remove-groups"></a>Gruppen entfernen  
  
1.  Verwenden der <xref:System.Windows.Forms.ListViewGroupCollection.RemoveAt%2A> oder <xref:System.Windows.Forms.ListViewGroupCollection.Clear%2A> Methode der <xref:System.Windows.Forms.ListView.Groups%2A> Auflistung.  
  
     Die <xref:System.Windows.Forms.ListViewGroupCollection.RemoveAt%2A> Methode wird eine einzelne Gruppe entfernt; die <xref:System.Windows.Forms.ListViewGroupCollection.Clear%2A> -Methode entfernt alle Gruppen aus der Liste.  
  
    > [!NOTE]
    >  Eine Gruppe entfernen, wird die Elemente in dieser Gruppe nicht entfernt.  
  
     [!code-csharp[System.Windows.Forms.ListViewLegacyTopics#22](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/CS/Class1.cs#22)]
     [!code-vb[System.Windows.Forms.ListViewLegacyTopics#22](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/VB/Class1.vb#22)]  
  
### <a name="to-assign-items-to-groups-or-move-items-between-groups"></a>Zuweisen zu Gruppen von Elementen oder Elemente zwischen den Gruppen verschieben.  
  
1.  Legen Sie die <xref:System.Windows.Forms.ListViewItem.Group%2A?displayProperty=nameWithType> -Eigenschaft einzelner Elemente.  
  
     [!code-csharp[System.Windows.Forms.ListViewLegacyTopics#23](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/CS/Class1.cs#23)]
     [!code-vb[System.Windows.Forms.ListViewLegacyTopics#23](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/VB/Class1.vb#23)]  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Windows.Forms.ListView>
- <xref:System.Windows.Forms.ListView.Groups%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.ListViewGroup>
- [ListView-Steuerelement](listview-control-windows-forms.md)
- [Übersicht über das ListView-Steuerelement](listview-control-overview-windows-forms.md)
- [Vorgehensweise: Hinzufügen und Entfernen von Elementen mit dem ListView-Steuerelement in Windows Forms](how-to-add-and-remove-items-with-the-windows-forms-listview-control.md)
