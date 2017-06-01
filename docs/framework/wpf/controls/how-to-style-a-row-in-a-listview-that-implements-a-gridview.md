---
title: "Gewusst wie: Formatieren einer Zeile in einem ListView, in dem ein GridView implementiert ist | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-wpf"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "GridView-Steuerelemente, Stile Zeilen"
  - "Formatieren von Zeilen in ListViews, die GridViews implementieren"
  - "ListView-Steuerelemente, Stile Zeilen mit GridViews"
ms.assetid: 2e406ba2-70a0-4e62-841f-0934859de76e
caps.latest.revision: 12
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 12
---
# Gewusst wie: Formatieren einer Zeile in einem ListView, in dem ein GridView implementiert ist
In diesem Beispiel wird gezeigt, wie so formatieren Sie eine Zeile in einer <xref:System.Windows.Controls.ListView> -Steuerelement, implementiert eine <xref:System.Windows.Controls.GridView><xref:System.Windows.Controls.ListView.View%2A> Modus.  
  
## <a name="example"></a>Beispiel  
 Können Sie eine Zeile in Formatieren einer <xref:System.Windows.Controls.ListView> -Steuerelement durch Festlegen einer <xref:System.Windows.Controls.ItemsControl.ItemContainerStyle%2A> auf der <xref:System.Windows.Controls.ListView> Steuerelement. Legen Sie den Stil für die enthaltenen Elemente, die als dargestellt werden <xref:System.Windows.Controls.ListViewItem> Objekte. Die <xref:System.Windows.Controls.ItemsControl.ItemContainerStyle%2A> Verweise der <xref:System.Windows.Controls.ControlTemplate> Objekte, die zum Anzeigen des Zeileninhalts verwendet werden.  
  
 Das vollständige Beispiel, in dem die folgenden Beispiele stammen, zeigt eine Auflistung von Song-Informationen, die in gespeichert ist ein [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] Datenbank. Jeder Titel in der Datenbank verfügt über ein Bewertungsfeld, und der Wert dieses Felds gibt an, wie Sie eine Zeile von Song-Informationen anzeigen.  
  
 Das folgende Beispiel zeigt, wie Sie definieren <xref:System.Windows.Controls.ItemsControl.ItemContainerStyle%2A> für die <xref:System.Windows.Controls.ListViewItem> Objekte, die die Titel in der Auflistung Song darstellen. Die <xref:System.Windows.Controls.ItemsControl.ItemContainerStyle%2A> Verweise <xref:System.Windows.Controls.ControlTemplate> Objekte, die angeben, wie Sie eine Zeile von Song-Informationen anzeigen.  
  
 [!code-xml[ListViewItemStyleSnippet#ItemContainerStyle](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewItemStyleSnippet/CS/Window1.xaml#itemcontainerstyle)]  
  
 Das folgende Beispiel zeigt eine <xref:System.Windows.Controls.ControlTemplate> , addiert die Zeichenfolge `"Strongly Recommended"` in die Zeile. Diese Vorlage bezieht sich auf die <xref:System.Windows.Controls.ItemsControl.ItemContainerStyle%2A> und angezeigt, wenn der Titel Bewertung der Wert 5 (5) hat. Die <xref:System.Windows.Controls.ControlTemplate> enthält eine <xref:System.Windows.Controls.GridViewRowPresenter> -Objekt, das den Inhalt der Zeile in Spalten angeordnet, gemäß der <xref:System.Windows.Controls.GridView> Anzeigemodus.  
  
 [!code-xml[ListViewItemStyleSnippet#ControlTemplate](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewItemStyleSnippet/CS/Window1.xaml#controltemplate)]  
  
 Das folgende Beispiel definiert <xref:System.Windows.Controls.GridView>.  
  
 [!code-xml[ListViewItemStyleSnippet#GridView](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewItemStyleSnippet/CS/Window1.xaml#gridview)]  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Windows.Controls.ListView>   
 <xref:System.Windows.Controls.GridView>   
 [Gewusst-wie-Themen](../../../../docs/framework/wpf/controls/listview-how-to-topics.md)   
 [Übersicht über ListView](../../../../docs/framework/wpf/controls/listview-overview.md)   
 [Von Formaten und Vorlagen](../../../../docs/framework/wpf/controls/styling-and-templating.md)