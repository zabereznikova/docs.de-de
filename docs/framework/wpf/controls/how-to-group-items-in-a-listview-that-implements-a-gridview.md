---
title: 'Gewusst wie: Gruppieren von Elementen in einem ListView, in dem ein GridView implementiert ist'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- ListView controls [WPF], grouping items with GridViews
- grouping items in ListViews implementing GridViews [WPF]
- GridView controls [WPF], grouping items
ms.assetid: eebef25b-ddc6-424e-a66d-ea228d1bf33d
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 30808e8ee0223c31085a65ff025fb188c0132057
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-group-items-in-a-listview-that-implements-a-gridview"></a>Gewusst wie: Gruppieren von Elementen in einem ListView, in dem ein GridView implementiert ist
Dieses Beispiel zeigt die Vorgehensweise beim Anzeigen von Gruppen von Elementen in der <xref:System.Windows.Controls.GridView> Ansichtsmodus des ein <xref:System.Windows.Controls.ListView> Steuerelement.  
  
## <a name="example"></a>Beispiel  
 Zum Anzeigen von Gruppen von Elementen in einem <xref:System.Windows.Controls.ListView>, definieren eine <xref:System.Windows.Data.CollectionViewSource>. Das folgende Beispiel zeigt eine <xref:System.Windows.Data.CollectionViewSource> , die Datenelemente entsprechend dem Wert des gruppiert die `Catalog` Feld "Daten".  
  
 [!code-xaml[GridViewWithGroups#GroupingCollectionViewSource](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GridViewWithGroups/CS/Window1.xaml#groupingcollectionviewsource)]  
  
 Im folgenden Beispiel wird die <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> für die <xref:System.Windows.Controls.ListView> auf die <xref:System.Windows.Data.CollectionViewSource> , die im vorherigen Beispiel definiert. Im Beispiel definiert auch einen <xref:System.Windows.Controls.ItemsControl.GroupStyle%2A> implementiert, die eine <xref:System.Windows.Controls.Expander> Steuerelement.  
  
 [!code-xaml[GridViewWithGroups#ListViewGroups](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GridViewWithGroups/CS/Window1.xaml#listviewgroups)]  
[!code-xaml[GridViewWithGroups#ListViewEnd](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GridViewWithGroups/CS/Window1.xaml#listviewend)]  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Windows.Controls.ListView>  
 <xref:System.Windows.Controls.GridView>  
 [Themen zur Vorgehensweise](../../../../docs/framework/wpf/controls/listview-how-to-topics.md)  
 [Übersicht über ListView](../../../../docs/framework/wpf/controls/listview-overview.md)  
 [Übersicht über GridView](../../../../docs/framework/wpf/controls/gridview-overview.md)
