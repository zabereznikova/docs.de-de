---
title: 'Vorgehensweise: Formatieren einer Zeile in einem ListView, in dem ein GridView implementiert ist'
ms.date: 03/30/2017
helpviewer_keywords:
- GridView controls [WPF], styling rows
- styling rows in ListViews implementing GridViews [WPF]
- ListView controls [WPF], styling rows with GridViews
ms.assetid: 2e406ba2-70a0-4e62-841f-0934859de76e
ms.openlocfilehash: 39801af88d3e64b92aa7e99ff794c3d7e7239df5
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54680230"
---
# <a name="how-to-style-a-row-in-a-listview-that-implements-a-gridview"></a>Vorgehensweise: Formatieren einer Zeile in einem ListView, in dem ein GridView implementiert ist
In diesem Beispiel wird gezeigt, wie zum Formatieren einer Zeile in einer <xref:System.Windows.Controls.ListView> -Steuerelement, implementiert eine <xref:System.Windows.Controls.GridView> <xref:System.Windows.Controls.ListView.View%2A> Modus.  
  
## <a name="example"></a>Beispiel  
 Können Sie eine Zeile in Formatieren einer <xref:System.Windows.Controls.ListView> Steuerelement durch Festlegen einer <xref:System.Windows.Controls.ItemsControl.ItemContainerStyle%2A> auf die <xref:System.Windows.Controls.ListView> Steuerelement. Legen Sie den Stil für die enthaltenen Elemente, die als dargestellt werden <xref:System.Windows.Controls.ListViewItem> Objekte. Die <xref:System.Windows.Controls.ItemsControl.ItemContainerStyle%2A> Verweise der <xref:System.Windows.Controls.ControlTemplate> Objekte, die zum Anzeigen des Zeileninhalts verwendet werden.  
  
 Das vollständige Beispiel, aus dem die folgenden Beispiele stammen, zeigt eine Auflistung von Informationen zu Musiktiteln, die in einer [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)]-Datenbank gespeichert sind. Jeder Titel in der Datenbank verfügt über ein Bewertungsfeld, und der Wert dieses Felds gibt an, wie eine Zeile mit den zugehörigen Informationen angezeigt werden soll.  
  
 Das folgende Beispiel zeigt, wie Sie definieren <xref:System.Windows.Controls.ItemsControl.ItemContainerStyle%2A> für die <xref:System.Windows.Controls.ListViewItem> Objekte, die die Titel in der Auflistung darstellen. Die <xref:System.Windows.Controls.ItemsControl.ItemContainerStyle%2A> Verweise <xref:System.Windows.Controls.ControlTemplate> Objekte, die angeben, wie eine Zeile mit Titelinformationen angezeigt.  
  
 [!code-xaml[ListViewItemStyleSnippet#ItemContainerStyle](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewItemStyleSnippet/CS/Window1.xaml#itemcontainerstyle)]  
  
 Das folgende Beispiel zeigt eine <xref:System.Windows.Controls.ControlTemplate> , addiert die Textzeichenfolge `"Strongly Recommended"` auf die Zeile. Diese Vorlage verwiesen wird, der <xref:System.Windows.Controls.ItemsControl.ItemContainerStyle%2A> und zeigt an, wenn der Titel mit dem Wert 5 (fünf) hat. Die <xref:System.Windows.Controls.ControlTemplate> enthält eine <xref:System.Windows.Controls.GridViewRowPresenter> -Objekt, das den Inhalt der Zeile Spalten angelegt, gemäß der <xref:System.Windows.Controls.GridView> sichtmodus befinden.  
  
 [!code-xaml[ListViewItemStyleSnippet#ControlTemplate](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewItemStyleSnippet/CS/Window1.xaml#controltemplate)]  
  
 Das folgende Beispiel definiert <xref:System.Windows.Controls.GridView>.  
  
 [!code-xaml[ListViewItemStyleSnippet#GridView](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewItemStyleSnippet/CS/Window1.xaml#gridview)]  
  
## <a name="see-also"></a>Siehe auch
- <xref:System.Windows.Controls.ListView>
- <xref:System.Windows.Controls.GridView>
- [Themen zu Vorgehensweisen](../../../../docs/framework/wpf/controls/listview-how-to-topics.md)
- [Übersicht über ListView](../../../../docs/framework/wpf/controls/listview-overview.md)
- [Erstellen von Formaten und Vorlagen](../../../../docs/framework/wpf/controls/styling-and-templating.md)
