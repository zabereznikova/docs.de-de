---
title: 'Gewusst wie: Formatieren einer Zeile in einem ListView-Steuer Punkt, der eine GridView verwendet'
ms.date: 03/30/2017
helpviewer_keywords:
- GridView controls [WPF], styling rows
- styling rows in ListViews implementing GridViews [WPF]
- ListView controls [WPF], styling rows with GridViews
ms.assetid: 2e406ba2-70a0-4e62-841f-0934859de76e
ms.openlocfilehash: 4b8b8e2f1b2d7207a37205d981bf2dab3f65122e
ms.sourcegitcommit: e0803b8975d3eb12e735a5d07637020dd6dac5ef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/01/2020
ms.locfileid: "89271944"
---
# <a name="how-to-style-a-row-in-a-listview-that-implements-a-gridview"></a>Gewusst wie: Formatieren einer Zeile in einem ListView, in dem ein GridView implementiert ist
Dieses Beispiel zeigt, wie eine Zeile in einem-Steuerelement formatieren wird <xref:System.Windows.Controls.ListView> , das einen- <xref:System.Windows.Controls.GridView> <xref:System.Windows.Controls.ListView.View%2A> Modus verwendet.  
  
## <a name="example"></a>Beispiel  
 Sie können eine Zeile in einem-Steuerelement formatieren, <xref:System.Windows.Controls.ListView> indem Sie ein <xref:System.Windows.Controls.ItemsControl.ItemContainerStyle%2A> für das-Steuerelement festlegen <xref:System.Windows.Controls.ListView> . Legen Sie den Stil für die Elemente fest, die als-Objekte dargestellt werden <xref:System.Windows.Controls.ListViewItem> . Der <xref:System.Windows.Controls.ItemsControl.ItemContainerStyle%2A> verweist <xref:System.Windows.Controls.ControlTemplate> auf die Objekte, die zum Anzeigen des Zeilen Inhalts verwendet werden.  
  
 Das komplette Beispiel, aus dem die folgenden Beispiele extrahiert werden, zeigt eine Auflistung von Songinformationen an, die in einer XML-Datenbank gespeichert sind. Jeder Titel in der Datenbank verfügt über ein Bewertungsfeld, und der Wert dieses Felds gibt an, wie eine Zeile mit den zugehörigen Informationen angezeigt werden soll.  
  
 Im folgenden Beispiel wird gezeigt, wie <xref:System.Windows.Controls.ItemsControl.ItemContainerStyle%2A> für die-Objekte definiert wird <xref:System.Windows.Controls.ListViewItem> , die die-Lieder in der Song-Auflistung darstellen. Die <xref:System.Windows.Controls.ItemsControl.ItemContainerStyle%2A> verweist <xref:System.Windows.Controls.ControlTemplate> auf-Objekte, die angeben, wie eine Zeile mit Songinformationen angezeigt werden soll.  
  
 [!code-xaml[ListViewItemStyleSnippet#ItemContainerStyle](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewItemStyleSnippet/CS/Window1.xaml#itemcontainerstyle)]  
  
 Das folgende Beispiel zeigt einen <xref:System.Windows.Controls.ControlTemplate> , der die Text Zeichenfolge der `"Strongly Recommended"` Zeile hinzufügt. Auf diese Vorlage wird im verwiesen, <xref:System.Windows.Controls.ItemsControl.ItemContainerStyle%2A> und wird angezeigt, wenn die Bewertung des Titels den Wert 5 (fünf) aufweist. <xref:System.Windows.Controls.ControlTemplate>Enthält ein- <xref:System.Windows.Controls.GridViewRowPresenter> Objekt, das den Inhalt der Zeile in Spalten festlegt, wie im <xref:System.Windows.Controls.GridView> Ansichtsmodus definiert.  
  
 [!code-xaml[ListViewItemStyleSnippet#ControlTemplate](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewItemStyleSnippet/CS/Window1.xaml#controltemplate)]  
  
 Im folgenden Beispiel wird definiert <xref:System.Windows.Controls.GridView> .  
  
 [!code-xaml[ListViewItemStyleSnippet#GridView](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewItemStyleSnippet/CS/Window1.xaml#gridview)]  
  
## <a name="see-also"></a>Weitere Informationen

- <xref:System.Windows.Controls.ListView>
- <xref:System.Windows.Controls.GridView>
- [Artikel zu Vorgehensweisen](listview-how-to-topics.md)
- [Übersicht über ListView](listview-overview.md)
- [Erstellen von Formaten und Vorlagen](../../../desktop-wpf/fundamentals/styles-templates-overview.md)
