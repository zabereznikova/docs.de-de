---
title: 'Gewusst wie: Formatieren einer Zeile in einem ListView, in dem ein GridView implementiert ist'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- GridView controls [WPF], styling rows
- styling rows in ListViews implementing GridViews [WPF]
- ListView controls [WPF], styling rows with GridViews
ms.assetid: 2e406ba2-70a0-4e62-841f-0934859de76e
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: c51f6cc5c35200267aa84960655fd734a937a7c5
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-style-a-row-in-a-listview-that-implements-a-gridview"></a>Gewusst wie: Formatieren einer Zeile in einem ListView, in dem ein GridView implementiert ist
In diesem Beispiel wird gezeigt, wie so formatieren Sie eine Zeile in einer <xref:System.Windows.Controls.ListView> -Steuerelement, implementiert eine <xref:System.Windows.Controls.GridView> <xref:System.Windows.Controls.ListView.View%2A> Modus.  
  
## <a name="example"></a>Beispiel  
 Können Sie eine Zeile in Formatieren einer <xref:System.Windows.Controls.ListView> Steuerelement durch Festlegen einer <xref:System.Windows.Controls.ItemsControl.ItemContainerStyle%2A> auf die <xref:System.Windows.Controls.ListView> Steuerelement. Festlegen des Formats für die Elemente, die als Werte dargestellt werden <xref:System.Windows.Controls.ListViewItem> Objekte. Die <xref:System.Windows.Controls.ItemsControl.ItemContainerStyle%2A> Verweise der <xref:System.Windows.Controls.ControlTemplate> Objekte, die verwendet werden, um den Zeileninhalt anzuzeigen.  
  
 Das vollständige Beispiel, aus dem die folgenden Beispiele stammen, zeigt eine Auflistung von Informationen zu Musiktiteln, die in einer [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)]-Datenbank gespeichert sind. Jeder Titel in der Datenbank verfügt über ein Bewertungsfeld, und der Wert dieses Felds gibt an, wie eine Zeile mit den zugehörigen Informationen angezeigt werden soll.  
  
 Das folgende Beispiel zeigt, wie definiert <xref:System.Windows.Controls.ItemsControl.ItemContainerStyle%2A> für die <xref:System.Windows.Controls.ListViewItem> Objekte, die die Titel in der Auflistung Musiktitel darstellen. Die <xref:System.Windows.Controls.ItemsControl.ItemContainerStyle%2A> Verweise <xref:System.Windows.Controls.ControlTemplate> Objekte, die angeben, wie eine Zeile mit Titelinformationen angezeigt.  
  
 [!code-xaml[ListViewItemStyleSnippet#ItemContainerStyle](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewItemStyleSnippet/CS/Window1.xaml#itemcontainerstyle)]  
  
 Das folgende Beispiel zeigt eine <xref:System.Windows.Controls.ControlTemplate> , addiert der Textzeichenfolge `"Strongly Recommended"` auf die Zeile. Diese Vorlage verwiesen wird, der <xref:System.Windows.Controls.ItemsControl.ItemContainerStyle%2A> und zeigt an, wenn der Titel Bewertung den Wert 5 (5) aufweist. Die <xref:System.Windows.Controls.ControlTemplate> enthält eine <xref:System.Windows.Controls.GridViewRowPresenter> -Objekt, das den Inhalt der Zeile in den Spalten angeordnet, gemäß der Definition von der <xref:System.Windows.Controls.GridView> sichtmodus befinden.  
  
 [!code-xaml[ListViewItemStyleSnippet#ControlTemplate](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewItemStyleSnippet/CS/Window1.xaml#controltemplate)]  
  
 Das folgende Beispiel definiert <xref:System.Windows.Controls.GridView>.  
  
 [!code-xaml[ListViewItemStyleSnippet#GridView](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewItemStyleSnippet/CS/Window1.xaml#gridview)]  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Windows.Controls.ListView>  
 <xref:System.Windows.Controls.GridView>  
 [Themen zur Vorgehensweise](../../../../docs/framework/wpf/controls/listview-how-to-topics.md)  
 [Übersicht über ListView](../../../../docs/framework/wpf/controls/listview-overview.md)  
 [Erstellen von Formaten und Vorlagen](../../../../docs/framework/wpf/controls/styling-and-templating.md)
