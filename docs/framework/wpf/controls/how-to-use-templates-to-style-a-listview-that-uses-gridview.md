---
title: 'Vorgehensweise: Formatieren eines ListView-Steuerelements mit einem GridView mithilfe von Vorlagen'
ms.date: 03/30/2017
helpviewer_keywords:
- ListView controls [WPF], styling
ms.assetid: 94bf964b-96c8-4bdf-a0c3-f5271b7cb565
ms.openlocfilehash: f1ff608f03c7e9acdba49ca7f76938caec527285
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54664394"
---
# <a name="how-to-use-templates-to-style-a-listview-that-uses-gridview"></a>Vorgehensweise: Formatieren eines ListView-Steuerelements mit einem GridView mithilfe von Vorlagen
Dieses Beispiel zeigt, wie Sie mit der <xref:System.Windows.DataTemplate> und <xref:System.Windows.Style> Objekte an die Darstellung des eine <xref:System.Windows.Controls.ListView> -Steuerelement, das verwendet eine <xref:System.Windows.Controls.GridView> sichtmodus befinden.  
  
## <a name="example"></a>Beispiel  
 Die folgenden Beispiele zeigen <xref:System.Windows.Style> und <xref:System.Windows.DataTemplate> Objekte, die eine Spaltenüberschrift für die Darstellung anpassen einer <xref:System.Windows.Controls.GridViewColumn>.  
  
 [!code-xaml[ListViewTemplate#GridViewHeaderStyle](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewTemplate/CS/window1.xaml#gridviewheaderstyle)]  
  
 [!code-xaml[ListViewTemplate#GridViewHeaderTemplate](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewTemplate/CS/window1.xaml#gridviewheadertemplate)]  
  
 Das folgende Beispiel zeigt, wie diese <xref:System.Windows.Style> und <xref:System.Windows.DataTemplate> Objekte Festlegen der <xref:System.Windows.Controls.GridViewColumn.HeaderContainerStyle%2A> und <xref:System.Windows.Controls.GridViewColumn.HeaderTemplate%2A> Eigenschaften eine <xref:System.Windows.Controls.GridViewColumn>. Die <xref:System.Windows.Controls.GridViewColumn.DisplayMemberBinding%2A> Eigenschaft definiert den Inhalt, der die Zellen der Spalte.  
  
 [!code-xaml[ListViewTemplate#GridViewColumnTemplate](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewTemplate/CS/window1.xaml#gridviewcolumntemplate)]  
  
 Die <xref:System.Windows.Controls.GridViewColumn.HeaderContainerStyle%2A> und <xref:System.Windows.Controls.GridViewColumn.HeaderTemplate%2A> sind nur zwei verschiedene Eigenschaften, die Sie, zum Anpassen der Darstellung eines Spaltenheaders für verwenden können eine <xref:System.Windows.Controls.GridView> Steuerelement. Weitere Informationen finden Sie unter [Übersicht über GridView-Spaltenheaderstile und -Spaltenheadervorlagen](../../../../docs/framework/wpf/controls/gridview-column-header-styles-and-templates-overview.md).  
  
 Das folgende Beispiel zeigt, wie Sie definieren eine <xref:System.Windows.DataTemplate> passt die, die die Darstellung der Zellen in einem <xref:System.Windows.Controls.GridViewColumn>.  
  
 [!code-xaml[ListViewTemplate#GridViewCellTemplate](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewTemplate/CS/window1.xaml#gridviewcelltemplate)]  
  
 Das folgende Beispiel zeigt die Verwendung dieses <xref:System.Windows.DataTemplate> zum Definieren des Inhalts von einem <xref:System.Windows.Controls.GridViewColumn> Zelle. Diese Vorlage wird verwendet, statt die <xref:System.Windows.Controls.GridViewColumn.DisplayMemberBinding%2A> -Eigenschaft, die in der vorherigen angezeigt wird <xref:System.Windows.Controls.GridViewColumn> Beispiel.  
  
 [!code-xaml[ListViewTemplate#CellTemplateProperty](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewTemplate/CS/window1.xaml#celltemplateproperty)]  
  
## <a name="see-also"></a>Siehe auch
- <xref:System.Windows.Controls.ListView>
- <xref:System.Windows.Controls.GridView>
- [Übersicht über GridView](../../../../docs/framework/wpf/controls/gridview-overview.md)
- [Themen zu Vorgehensweisen](../../../../docs/framework/wpf/controls/listview-how-to-topics.md)
- [Übersicht über ListView](../../../../docs/framework/wpf/controls/listview-overview.md)
