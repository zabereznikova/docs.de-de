---
title: 'Gewusst wie: Gruppieren von Elementen in einem ListView-Steuerelement in Windows Forms'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
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
caps.latest.revision: "18"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: c22134513c2c6a3ff2bc621e68f546b7bcc93ba9
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-group-items-in-a-windows-forms-listview-control"></a>Gewusst wie: Gruppieren von Elementen in einem ListView-Steuerelement in Windows Forms
Mit der Grouping-Funktion von der <xref:System.Windows.Forms.ListView> -Steuerelement, Verwandte Gruppen von Elementen in Gruppen angezeigt werden können. Diese Gruppen werden auf dem Bildschirm durch horizontale Gruppenheader getrennt, die die Gruppentitel enthalten. Sie können <xref:System.Windows.Forms.ListView> Gruppen aus, um die Navigation in umfangreichen Listen einfacher durch Gruppieren Elemente alphabetisch nach Datum oder eine beliebige andere logische Gruppierung vornehmen. Die folgende Abbildung zeigt einige gruppierten Elemente.  
  
 ![ListView-Gruppen](../../../../docs/framework/winforms/controls/media/listviewgroups.gif "ListViewGroups")  
ListView Navigation in gruppierten Elementen  
  
 Um die Gruppierung zu aktivieren, müssen Sie zunächst eine oder mehrere Gruppen im Designer oder programmgesteuert erstellen. Nachdem eine Gruppe definiert wurde, können Sie zuweisen <xref:System.Windows.Forms.ListView> Elemente in Gruppen. Sie können auch Elemente aus einer Gruppe in eine andere programmgesteuert verschieben.  
  
> [!NOTE]
>  <xref:System.Windows.Forms.ListView>Gruppen stehen nur in [!INCLUDE[WinXpFamily](../../../../includes/winxpfamily-md.md)] bei einem Aufruf der <xref:System.Windows.Forms.Application.EnableVisualStyles%2A?displayProperty=nameWithType> Methode. Unter älteren Betriebssystemen Code in Zusammenhang mit Gruppen hat keine Auswirkungen, und die Gruppen werden nicht angezeigt. Weitere Informationen finden Sie unter <xref:System.Windows.Forms.ListView.Groups%2A?displayProperty=nameWithType>.  
  
### <a name="to-add-groups"></a>So fügen Sie Gruppen hinzu  
  
1.  Verwenden Sie die <xref:System.Windows.Forms.ListViewGroupCollection.Add%2A>-Methode der <xref:System.Windows.Forms.ListView.Groups%2A>-Auflistung.  
  
     [!code-csharp[System.Windows.Forms.ListViewLegacyTopics#21](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/CS/Class1.cs#21)]
     [!code-vb[System.Windows.Forms.ListViewLegacyTopics#21](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/VB/Class1.vb#21)]  
  
### <a name="to-remove-groups"></a>So entfernen Sie Gruppen  
  
1.  Verwenden der <xref:System.Windows.Forms.ListViewGroupCollection.RemoveAt%2A> oder <xref:System.Windows.Forms.ListViewGroupCollection.Clear%2A> Methode der <xref:System.Windows.Forms.ListView.Groups%2A> Auflistung.  
  
     Die <xref:System.Windows.Forms.ListViewGroupCollection.RemoveAt%2A> Methode wird eine einzelne Gruppe entfernt; das <xref:System.Windows.Forms.ListViewGroupCollection.Clear%2A> -Methode entfernt alle Gruppen aus der Liste.  
  
    > [!NOTE]
    >  Entfernen einer Gruppenstatus, die Elemente innerhalb dieser Gruppe nicht entfernt.  
  
     [!code-csharp[System.Windows.Forms.ListViewLegacyTopics#22](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/CS/Class1.cs#22)]
     [!code-vb[System.Windows.Forms.ListViewLegacyTopics#22](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/VB/Class1.vb#22)]  
  
### <a name="to-assign-items-to-groups-or-move-items-between-groups"></a>Zuweisen von Elementen zu Gruppen oder Elemente zwischen den Gruppen verschieben.  
  
1.  Legen Sie die <xref:System.Windows.Forms.ListViewItem.Group%2A?displayProperty=nameWithType> Eigenschaft einzelner Elemente.  
  
     [!code-csharp[System.Windows.Forms.ListViewLegacyTopics#23](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/CS/Class1.cs#23)]
     [!code-vb[System.Windows.Forms.ListViewLegacyTopics#23](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/VB/Class1.vb#23)]  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Windows.Forms.ListView>  
 <xref:System.Windows.Forms.ListView.Groups%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.ListViewGroup>  
 [ListView-Steuerelement](../../../../docs/framework/winforms/controls/listview-control-windows-forms.md)  
 [Übersicht über das ListView-Steuerelement](../../../../docs/framework/winforms/controls/listview-control-overview-windows-forms.md)  
 [Windows XP-Features und Windows Forms-Steuerelemente](http://msdn.microsoft.com/en-us/bc7fab94-fce9-4bf1-a8ad-a5837c91c3c0)  
 [Gewusst wie: Hinzufügen und Entfernen von Elementen mit dem ListView-Steuerelement in Windows Forms](../../../../docs/framework/winforms/controls/how-to-add-and-remove-items-with-the-windows-forms-listview-control.md)
