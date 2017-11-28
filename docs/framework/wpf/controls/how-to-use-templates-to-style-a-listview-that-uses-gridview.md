---
title: 'Gewusst wie: Formatieren eines ListView-Steuerelements mit einem GridView mithilfe von Vorlagen'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: ListView controls [WPF], styling
ms.assetid: 94bf964b-96c8-4bdf-a0c3-f5271b7cb565
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 246c144a18d7c1014096a6e37ad09b6eec5ad932
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-use-templates-to-style-a-listview-that-uses-gridview"></a>Gewusst wie: Formatieren eines ListView-Steuerelements mit einem GridView mithilfe von Vorlagen
Dieses Beispiel zeigt, wie die <xref:System.Windows.DataTemplate> und <xref:System.Windows.Style> Objekte an, die Darstellung des eine <xref:System.Windows.Controls.ListView> -Steuerelements, verwendet eine <xref:System.Windows.Controls.GridView> Ansichtsmodus.  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel zeigt <xref:System.Windows.Style> und <xref:System.Windows.DataTemplate> Objekte, die einen Spaltenheader für die Darstellung anpassen einer <xref:System.Windows.Controls.GridViewColumn>.  
  
 [!code-xaml[ListViewTemplate#GridViewHeaderStyle](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewTemplate/CS/window1.xaml#gridviewheaderstyle)]  
  
 [!code-xaml[ListViewTemplate#GridViewHeaderTemplate](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewTemplate/CS/window1.xaml#gridviewheadertemplate)]  
  
 Das folgende Beispiel zeigt, wie diese <xref:System.Windows.Style> und <xref:System.Windows.DataTemplate> Objekte Festlegen der <xref:System.Windows.Controls.GridViewColumn.HeaderContainerStyle%2A> und <xref:System.Windows.Controls.GridViewColumn.HeaderTemplate%2A> Eigenschaften einer <xref:System.Windows.Controls.GridViewColumn>. Die <xref:System.Windows.Controls.GridViewColumn.DisplayMemberBinding%2A> -Eigenschaft definiert den Inhalt der Spaltenzellen.  
  
 [!code-xaml[ListViewTemplate#GridViewColumnTemplate](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewTemplate/CS/window1.xaml#gridviewcolumntemplate)]  
  
 Die <xref:System.Windows.Controls.GridViewColumn.HeaderContainerStyle%2A> und <xref:System.Windows.Controls.GridViewColumn.HeaderTemplate%2A> sind nur zwei verschiedene Eigenschaften, die Sie, zum Anpassen der Darstellung eines Spaltenheaders für verwenden können eine <xref:System.Windows.Controls.GridView> Steuerelement. Weitere Informationen finden Sie unter [Übersicht über GridView-Spaltenheaderstile und -Spaltenheadervorlagen](../../../../docs/framework/wpf/controls/gridview-column-header-styles-and-templates-overview.md).  
  
 Das folgende Beispiel zeigt, wie Sie definieren eine <xref:System.Windows.DataTemplate> , die passt der Darstellung der Zellen in einer <xref:System.Windows.Controls.GridViewColumn>.  
  
 [!code-xaml[ListViewTemplate#GridViewCellTemplate](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewTemplate/CS/window1.xaml#gridviewcelltemplate)]  
  
 Das folgende Beispiel zeigt die Verwendung dieses <xref:System.Windows.DataTemplate> zum Definieren des Inhalts von einem <xref:System.Windows.Controls.GridViewColumn> Zelle. Diese Vorlage dient dazu, statt die <xref:System.Windows.Controls.GridViewColumn.DisplayMemberBinding%2A> -Eigenschaft, die in der vorherigen angezeigt wird <xref:System.Windows.Controls.GridViewColumn> Beispiel.  
  
 [!code-xaml[ListViewTemplate#CellTemplateProperty](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewTemplate/CS/window1.xaml#celltemplateproperty)]  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Windows.Controls.ListView>  
 <xref:System.Windows.Controls.GridView>  
 [Übersicht über GridView](../../../../docs/framework/wpf/controls/gridview-overview.md)  
 [Themen zur Vorgehensweise](../../../../docs/framework/wpf/controls/listview-how-to-topics.md)  
 [Übersicht über ListView](../../../../docs/framework/wpf/controls/listview-overview.md)
