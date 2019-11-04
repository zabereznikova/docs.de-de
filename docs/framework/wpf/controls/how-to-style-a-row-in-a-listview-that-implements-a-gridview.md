---
title: 'Gewusst wie: Formatieren einer Zeile in einem ListView, in dem ein GridView implementiert ist'
ms.date: 03/30/2017
helpviewer_keywords:
- GridView controls [WPF], styling rows
- styling rows in ListViews implementing GridViews [WPF]
- ListView controls [WPF], styling rows with GridViews
ms.assetid: 2e406ba2-70a0-4e62-841f-0934859de76e
ms.openlocfilehash: 150988aab368e3ffef0107d29bea5ebc53163946
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/03/2019
ms.locfileid: "73459323"
---
# <a name="how-to-style-a-row-in-a-listview-that-implements-a-gridview"></a>Gewusst wie: Formatieren einer Zeile in einem ListView, in dem ein GridView implementiert ist
In diesem Beispiel wird gezeigt, wie eine Zeile in einem <xref:System.Windows.Controls.ListView>-Steuerelement formatieren wird, das einen <xref:System.Windows.Controls.GridView><xref:System.Windows.Controls.ListView.View%2A> Modus implementiert.  
  
## <a name="example"></a>Beispiel  
 Sie können eine Zeile in einem <xref:System.Windows.Controls.ListView>-Steuerelement formatieren, indem Sie eine <xref:System.Windows.Controls.ItemsControl.ItemContainerStyle%2A> auf dem <xref:System.Windows.Controls.ListView>-Steuerelement festlegen. Legen Sie den Stil für die Elemente fest, die als <xref:System.Windows.Controls.ListViewItem>-Objekte dargestellt werden. Der <xref:System.Windows.Controls.ItemsControl.ItemContainerStyle%2A> verweist auf die <xref:System.Windows.Controls.ControlTemplate> Objekte, die verwendet werden, um den Zeilen Inhalt anzuzeigen.  
  
 Das vollständige Beispiel, aus dem die folgenden Beispiele stammen, zeigt eine Auflistung von Informationen zu Musiktiteln, die in einer [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)]-Datenbank gespeichert sind. Jeder Titel in der Datenbank verfügt über ein Bewertungsfeld, und der Wert dieses Felds gibt an, wie eine Zeile mit den zugehörigen Informationen angezeigt werden soll.  
  
 Im folgenden Beispiel wird gezeigt, wie <xref:System.Windows.Controls.ItemsControl.ItemContainerStyle%2A> für die <xref:System.Windows.Controls.ListViewItem>-Objekte definiert werden, die die-Lieder in der Song-Auflistung darstellen. Der <xref:System.Windows.Controls.ItemsControl.ItemContainerStyle%2A> verweist auf <xref:System.Windows.Controls.ControlTemplate> Objekte, die angeben, wie eine Zeile mit den Songinformationen angezeigt werden soll.  
  
 [!code-xaml[ListViewItemStyleSnippet#ItemContainerStyle](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewItemStyleSnippet/CS/Window1.xaml#itemcontainerstyle)]  
  
 Das folgende Beispiel zeigt eine <xref:System.Windows.Controls.ControlTemplate>, die der Zeile die Text Zeichenfolge `"Strongly Recommended"` hinzufügt. Auf diese Vorlage wird im <xref:System.Windows.Controls.ItemsControl.ItemContainerStyle%2A> verwiesen und angezeigt, wenn die Titel Bewertung den Wert 5 (fünf) aufweist. Die <xref:System.Windows.Controls.ControlTemplate> enthält ein <xref:System.Windows.Controls.GridViewRowPresenter> Objekt, das den Inhalt der Zeile in Spalten festlegt, wie im <xref:System.Windows.Controls.GridView> Ansichtsmodus definiert.  
  
 [!code-xaml[ListViewItemStyleSnippet#ControlTemplate](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewItemStyleSnippet/CS/Window1.xaml#controltemplate)]  
  
 Im folgenden Beispiel wird <xref:System.Windows.Controls.GridView>definiert.  
  
 [!code-xaml[ListViewItemStyleSnippet#GridView](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewItemStyleSnippet/CS/Window1.xaml#gridview)]  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Windows.Controls.ListView>
- <xref:System.Windows.Controls.GridView>
- [Themen zu Vorgehensweisen](listview-how-to-topics.md)
- [Übersicht über ListView](listview-overview.md)
- [Erstellen von Formaten und Vorlagen](../../../desktop-wpf/fundamentals/styles-templates-overview.md)
