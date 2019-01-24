---
title: 'Vorgehensweise: Gruppieren von Elementen in einem ListView, in dem ein GridView implementiert ist'
ms.date: 03/30/2017
helpviewer_keywords:
- ListView controls [WPF], grouping items with GridViews
- grouping items in ListViews implementing GridViews [WPF]
- GridView controls [WPF], grouping items
ms.assetid: eebef25b-ddc6-424e-a66d-ea228d1bf33d
ms.openlocfilehash: 1570eab70dae690f508975162b7553de92be6f12
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54664355"
---
# <a name="how-to-group-items-in-a-listview-that-implements-a-gridview"></a>Vorgehensweise: Gruppieren von Elementen in einem ListView, in dem ein GridView implementiert ist
Dieses Beispiel zeigt die Vorgehensweise beim Anzeigen von Gruppen von Elementen auf der <xref:System.Windows.Controls.GridView> Ansichtsmodus des eine <xref:System.Windows.Controls.ListView> Steuerelement.  
  
## <a name="example"></a>Beispiel  
 Zum Anzeigen von Gruppen von Elementen auf einer <xref:System.Windows.Controls.ListView>, definieren Sie eine <xref:System.Windows.Data.CollectionViewSource>. Das folgende Beispiel zeigt eine <xref:System.Windows.Data.CollectionViewSource> -Datenelemente entsprechend dem Wert der Gruppen, denen die `Catalog` Feld "Daten".  
  
 [!code-xaml[GridViewWithGroups#GroupingCollectionViewSource](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GridViewWithGroups/CS/Window1.xaml#groupingcollectionviewsource)]  
  
 Im folgenden Beispiel wird die <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> für die <xref:System.Windows.Controls.ListView> auf die <xref:System.Windows.Data.CollectionViewSource> , die im vorherige Beispiel definiert. Im Beispiel definiert auch eine <xref:System.Windows.Controls.ItemsControl.GroupStyle%2A> , implementiert eine <xref:System.Windows.Controls.Expander> Steuerelement.  
  
 [!code-xaml[GridViewWithGroups#ListViewGroups](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GridViewWithGroups/CS/Window1.xaml#listviewgroups)]  
[!code-xaml[GridViewWithGroups#ListViewEnd](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GridViewWithGroups/CS/Window1.xaml#listviewend)]  
  
## <a name="see-also"></a>Siehe auch
- <xref:System.Windows.Controls.ListView>
- <xref:System.Windows.Controls.GridView>
- [Themen zu Vorgehensweisen](../../../../docs/framework/wpf/controls/listview-how-to-topics.md)
- [Übersicht über ListView](../../../../docs/framework/wpf/controls/listview-overview.md)
- [Übersicht über GridView](../../../../docs/framework/wpf/controls/gridview-overview.md)
