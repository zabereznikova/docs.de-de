---
title: Übersicht über ScrollViewer
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- controls [WPF], ScrollViewer
- ScrollViewer control [WPF], about ScrollViewer control
ms.assetid: 94a13b94-cfdf-4b12-a1aa-90cb50c6e9b9
ms.openlocfilehash: a3302d9c360b0918a1fce956af3e3aa14f29361b
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59212426"
---
# <a name="scrollviewer-overview"></a>Übersicht über ScrollViewer
Der Inhalt einer Benutzeroberfläche ist häufig größer als der Anzeigebereich eines Computerbildschirms. Die <xref:System.Windows.Controls.ScrollViewer> Steuerelement bietet eine bequeme Möglichkeit zum Scrollen durch Inhalte in [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] Anwendungen. In diesem Thema werden die <xref:System.Windows.Controls.ScrollViewer> Element und mehrere Verwendungsbeispiele vorgestellt.  
  
<a name="what_is_a_scrollviewer_element"></a>   
## <a name="the-scrollviewer-control"></a>Das ScrollViewer-Steuerelement  
 Es gibt zwei vordefinierte Elemente, mit denen ein Bildlauf [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Anwendungen: <xref:System.Windows.Controls.Primitives.ScrollBar> und <xref:System.Windows.Controls.ScrollViewer>. Die <xref:System.Windows.Controls.ScrollViewer> -Steuerelement kapselt horizontale und vertikale <xref:System.Windows.Controls.Primitives.ScrollBar> Elemente und einen Inhaltscontainer (z. B. eine <xref:System.Windows.Controls.Panel> Element) um andere sichtbare Elemente in einem durchscrollbaren Bereich anzuzeigen. Sie müssen ein benutzerdefiniertes Objekt erstellen, um verwenden die <xref:System.Windows.Controls.Primitives.ScrollBar> -Element für das Scrollen durch Inhalte. Sie können jedoch die <xref:System.Windows.Controls.ScrollViewer> Element selbst, da es ist ein zusammengesetztes Steuerelement handelt, kapselt <xref:System.Windows.Controls.Primitives.ScrollBar> Funktionalität.  
  
 Die <xref:System.Windows.Controls.ScrollViewer> Steuerelement reagiert auf sowohl auf Maus-als auch auf Tastaturbefehle und definiert zahlreiche Methoden, mit denen anhand vordefinierter Schritte Inhalt ein Bildlauf ausgeführt. Können Sie die <xref:System.Windows.Controls.ScrollViewer.ScrollChanged> Ereignis erkennt eine Änderung in einer <xref:System.Windows.Controls.ScrollViewer> Zustand.  
  
 Ein <xref:System.Windows.Controls.ScrollViewer> nur möglich, ein untergeordnetes Element in der Regel eine <xref:System.Windows.Controls.Panel> -Element, das Hosten einer <xref:System.Windows.Controls.Panel.Children%2A> Auflistung von Elementen. Die <xref:System.Windows.Controls.ContentPresenter.Content%2A> Eigenschaft definiert das einzige untergeordnete Element von der <xref:System.Windows.Controls.ScrollViewer>.  
  
<a name="scrollviewer_physical_vs_logical"></a>   
## <a name="physical-vs-logical-scrolling"></a>Physische im Vergleich zu Logisches Scrollen  
 Das physische Scrollen wird zum Scrollen durch Inhalt anhand eines vordefinierten physischen Werts verwendet – in der Regel durch einen Wert in Pixel. Das logische Scrollen wird verwendet, um zum nächsten Element in einer logischen Struktur zu scrollen. Das physische Scrollen ist das standardscrollverhalten für die meisten <xref:System.Windows.Controls.Panel> Elemente. [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]unterstützt beide Scrolltypen.  
  
#### <a name="the-iscrollinfo-interface"></a>Die IScrollInfo-Schnittstelle  
 Die <xref:System.Windows.Controls.Primitives.IScrollInfo> Schnittstelle darstellt, den wichtigsten scrollbereich innerhalb einer <xref:System.Windows.Controls.ScrollViewer> oder eines abgeleiteten Steuerelements. Die Schnittstelle definiert scrolleigenschaften und -Methoden, die von implementiert werden können, <xref:System.Windows.Controls.Panel> Elemente, die Elemente ein Bildlauf durchgeführt, um logische Einheit, anstatt eines physischen inkrementierten Werts. Umwandeln einer Instanz von <xref:System.Windows.Controls.Primitives.IScrollInfo> auf eine abgeleitete <xref:System.Windows.Controls.Panel> , und klicken Sie dann mit Scrollen ist eine gute Möglichkeit bis zum nächsten logischen Einheit in einer untergeordneten Auflistung scrollen. In der Standardeinstellung die <xref:System.Windows.Controls.ScrollViewer> -Steuerelement unterstützt das Scrollen durch physische Einheiten.  
  
 <xref:System.Windows.Controls.StackPanel> und <xref:System.Windows.Controls.VirtualizingStackPanel> beide implementieren <xref:System.Windows.Controls.Primitives.IScrollInfo> und nativ Unterstützung des logischen scrollens. Für Layoutsteuerelemente, nativ Unterstützung des logischen scrollens, immer noch erreichen Sie das physische Scrollen durch Umschließen des Hosts <xref:System.Windows.Controls.Panel> Element in eine <xref:System.Windows.Controls.ScrollViewer> und Einstellung der <xref:System.Windows.Controls.ScrollViewer.CanContentScroll%2A> Eigenschaft `false`.  
  
 Im folgenden Codebeispiel wird veranschaulicht, wie eine Instanz der umzuwandelnde <xref:System.Windows.Controls.Primitives.IScrollInfo> zu einem <xref:System.Windows.Controls.StackPanel> und Inhalt verwenden (<xref:System.Windows.Controls.Primitives.IScrollInfo.LineUp%2A> und <xref:System.Windows.Controls.Primitives.IScrollInfo.LineDown%2A>) von der Schnittstelle definiert.  
  
 [!code-csharp[IScrollInfoMethods#3](~/samples/snippets/csharp/VS_Snippets_Wpf/IScrollInfoMethods/CSharp/Window1.xaml.cs#3)]
 [!code-vb[IScrollInfoMethods#3](~/samples/snippets/visualbasic/VS_Snippets_Wpf/IScrollInfoMethods/VisualBasic/Window1.xaml.vb#3)]  
  
<a name="scrollviewer_markup_syntax_and_sample"></a>   
## <a name="defining-and-using-a-scrollviewer-element"></a>Definieren und Verwenden eines ScrollViewer-Elements  
 Das folgende Beispiel erstellt eine <xref:System.Windows.Controls.ScrollViewer> in einem Fenster, das Text und ein Rechteck enthält. <xref:System.Windows.Controls.Primitives.ScrollBar> Elemente angezeigt werden, nur wenn sie erforderlich sind. Beim Ändern der Fenstergröße, den <xref:System.Windows.Controls.Primitives.ScrollBar> Elemente angezeigt werden, und aufgrund der aktualisierten Werte der der <xref:System.Windows.Controls.ScrollViewer.ComputedHorizontalScrollBarVisibility%2A> und <xref:System.Windows.Controls.ScrollViewer.ComputedVerticalScrollBarVisibility%2A> Eigenschaften.  
  
 [!code-cpp[ScrollViewer#1](~/samples/snippets/cpp/VS_Snippets_Wpf/ScrollViewer/CPP/ScrollViewer_wcp.cpp#1)]
 [!code-csharp[ScrollViewer#1](~/samples/snippets/csharp/VS_Snippets_Wpf/ScrollViewer/CSharp/ScrollViewer_wcp.cs#1)]
 [!code-vb[ScrollViewer#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ScrollViewer/VisualBasic/ScrollViewer.vb#1)]
 [!code-xaml[ScrollViewer#1](~/samples/snippets/xaml/VS_Snippets_Wpf/ScrollViewer/XAML/Pane1.xaml#1)]  
  
<a name="scrollviewer_styling_scrollviewer"></a>   
## <a name="styling-a-scrollviewer"></a>Formatieren eines ScrollViewer-Elements  
 Wie alle Steuerelemente in Windows Presentation Foundation, die <xref:System.Windows.Controls.ScrollViewer> formatiert werden können, um das Standardrenderingverhalten des Steuerelements zu ändern. Weitere Informationen zum Formatieren von Steuerelementen finden Sie unter [Erstellen von Formaten und Vorlagen](styling-and-templating.md).  
  
<a name="scrollviewer_scroll_vs_paginate"></a>   
## <a name="paginating-documents"></a>Umbrechen von Dokumenten  
 Als Alternative zum Scrollen können Sie für Dokumentinhalte einen Dokumentcontainer auswählen, der Umbrechen unterstützt. <xref:System.Windows.Documents.FlowDocument> wird für Dokumente, die entwickelt wurden, innerhalb eines Steuerelements anzeigen gehostet werden, z. B. <xref:System.Windows.Controls.FlowDocumentPageViewer>, seitenübergreifende Umbrechen von Inhalt über mehrere Seiten, die keine Notwendigkeit für den Bildlauf unterstützt. <xref:System.Windows.Controls.DocumentViewer> bietet eine Lösung für die Anzeige <xref:System.Windows.Documents.FixedDocument> Inhalt, der zum Anzeigen von Inhalten außerhalb der Reichweite des Anzeigebereichs verwendet herkömmliche scrollen.  
  
 Weitere Informationen zu Dokumentformaten und Präsentationsoptionen finden Sie unter [Dokumente in WPF](../advanced/documents-in-wpf.md).  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Windows.Controls.ScrollViewer>
- <xref:System.Windows.Controls.Primitives.ScrollBar>
- <xref:System.Windows.Controls.Primitives.IScrollInfo>
- [Vorgehensweise: Erstellen Sie ein ScrollViewer](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms752352(v=vs.90))
- [Dokumente in WPF](../advanced/documents-in-wpf.md)
- [ScrollBar-Stile und -Vorlagen](scrollbar-styles-and-templates.md)
- [Steuerelemente](../advanced/optimizing-performance-controls.md)
