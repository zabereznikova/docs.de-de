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
ms.openlocfilehash: 2ff0f134ea3174f7f034d47446aab782e2141916
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79186986"
---
# <a name="scrollviewer-overview"></a>Übersicht über ScrollViewer
Der Inhalt einer Benutzeroberfläche ist häufig größer als der Anzeigebereich eines Computerbildschirms. Das <xref:System.Windows.Controls.ScrollViewer> Steuerelement bietet eine bequeme Möglichkeit, [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] das Scrollen von Inhalten in Anwendungen zu aktivieren. In diesem <xref:System.Windows.Controls.ScrollViewer> Thema wird das Element vorgestellt und mehrere Anwendungsbeispiele vorgestellt.  
  
<a name="what_is_a_scrollviewer_element"></a>
## <a name="the-scrollviewer-control"></a>Das ScrollViewer-Steuerelement  
 Es gibt zwei vordefinierte Elemente, [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] die <xref:System.Windows.Controls.Primitives.ScrollBar> <xref:System.Windows.Controls.ScrollViewer>das Scrollen in Anwendungen ermöglichen: und . Das <xref:System.Windows.Controls.ScrollViewer> Steuerelement kapselt horizontale <xref:System.Windows.Controls.Primitives.ScrollBar> und vertikale Elemente und einen <xref:System.Windows.Controls.Panel> Inhaltscontainer (z. B. ein Element), um andere sichtbare Elemente in einem scrollbaren Bereich anzuzeigen. Sie müssen ein benutzerdefiniertes Objekt <xref:System.Windows.Controls.Primitives.ScrollBar> erstellen, um das Element für das Scrollen von Inhalten verwenden zu können. Sie können das <xref:System.Windows.Controls.ScrollViewer> Element jedoch selbst verwenden, da es sich <xref:System.Windows.Controls.Primitives.ScrollBar> um ein zusammengesetztes Steuerelement handelt, das Funktionen kapselt.  
  
 Das <xref:System.Windows.Controls.ScrollViewer> Steuerelement reagiert sowohl auf Maus- als auch auf Tastaturbefehle und definiert zahlreiche Methoden, mit denen Inhalte durch vorgegebene Inkremente gescrollt werden können. Sie können <xref:System.Windows.Controls.ScrollViewer.ScrollChanged> das Ereignis verwenden, <xref:System.Windows.Controls.ScrollViewer> um eine Änderung in einem Zustand zu erkennen.  
  
 A <xref:System.Windows.Controls.ScrollViewer> kann nur ein untergeordnetes Element haben, in der Regel ein <xref:System.Windows.Controls.Panel> Element, das eine <xref:System.Windows.Controls.Panel.Children%2A> Auflistung von Elementen hosten kann. Die <xref:System.Windows.Controls.ContentPresenter.Content%2A> Eigenschaft definiert das einzige <xref:System.Windows.Controls.ScrollViewer>untergeordnete Element der .  
  
<a name="scrollviewer_physical_vs_logical"></a>
## <a name="physical-vs-logical-scrolling"></a>Physisches vs. logisches Scrollen  
 Das physische Scrollen wird zum Scrollen durch Inhalt anhand eines vordefinierten physischen Werts verwendet – in der Regel durch einen Wert in Pixel. Das logische Scrollen wird verwendet, um zum nächsten Element in einer logischen Struktur zu scrollen. Physisches Scrollen ist das <xref:System.Windows.Controls.Panel> standardstandardmäßige Bildlaufverhalten für die meisten Elemente. [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]unterstützt beide Scrolltypen.  
  
#### <a name="the-iscrollinfo-interface"></a>Die IScrollInfo-Schnittstelle  
 Die <xref:System.Windows.Controls.Primitives.IScrollInfo> Schnittstelle stellt den Hauptbildlaufbereich innerhalb eines <xref:System.Windows.Controls.ScrollViewer> oder abgeleiteten Steuerelements dar. Die Schnittstelle definiert Bildlaufeigenschaften und -methoden, die von <xref:System.Windows.Controls.Panel> Elementen implementiert werden können, die einen Bildlauf nach logischer Einheit und nicht durch ein physisches Inkrement erfordern. Das Umstellen <xref:System.Windows.Controls.Primitives.IScrollInfo> einer <xref:System.Windows.Controls.Panel> Instanz in eine abgeleitete und anschließende Verwendung der Bildlaufmethoden bietet eine nützliche Möglichkeit, zur nächsten logischen Einheit in einer untergeordneten Auflistung zu scrollen, anstatt nach Pixelinkrement. Standardmäßig unterstützt <xref:System.Windows.Controls.ScrollViewer> das Steuerelement das Scrollen nach physischen Einheiten.  
  
 <xref:System.Windows.Controls.StackPanel>und <xref:System.Windows.Controls.VirtualizingStackPanel> sowohl <xref:System.Windows.Controls.Primitives.IScrollInfo> implementieren als auch nativ logisches Scrollen unterstützen. Bei Layoutsteuerelementen, die das logische Scrollen nativ unterstützen, <xref:System.Windows.Controls.Panel> können Sie <xref:System.Windows.Controls.ScrollViewer> weiterhin <xref:System.Windows.Controls.ScrollViewer.CanContentScroll%2A> ein `false`physisches Scrollen erzielen, indem Sie das Hostelement in ein umschließen und die Eigenschaft auf festlegen.  
  
 Im folgenden Codebeispiel wird veranschaulicht, <xref:System.Windows.Controls.Primitives.IScrollInfo> wie <xref:System.Windows.Controls.StackPanel> sie eine Instanz<xref:System.Windows.Controls.Primitives.IScrollInfo.LineUp%2A> von <xref:System.Windows.Controls.Primitives.IScrollInfo.LineDown%2A>in eine umsiebund inhaltsbildlwickende Methoden ( und ) verwendet, die von der Schnittstelle definiert werden.  
  
 [!code-csharp[IScrollInfoMethods#3](~/samples/snippets/csharp/VS_Snippets_Wpf/IScrollInfoMethods/CSharp/Window1.xaml.cs#3)]
 [!code-vb[IScrollInfoMethods#3](~/samples/snippets/visualbasic/VS_Snippets_Wpf/IScrollInfoMethods/VisualBasic/Window1.xaml.vb#3)]  
  
<a name="scrollviewer_markup_syntax_and_sample"></a>
## <a name="defining-and-using-a-scrollviewer-element"></a>Definieren und Verwenden eines ScrollViewer-Elements  
 Im folgenden Beispiel <xref:System.Windows.Controls.ScrollViewer> wird ein in einem Fenster erstellt, das Text und ein Rechteck enthält. <xref:System.Windows.Controls.Primitives.ScrollBar>Elemente werden nur angezeigt, wenn sie erforderlich sind. Wenn Sie die Größe <xref:System.Windows.Controls.Primitives.ScrollBar> des Fensters ändern, werden die <xref:System.Windows.Controls.ScrollViewer.ComputedHorizontalScrollBarVisibility%2A> <xref:System.Windows.Controls.ScrollViewer.ComputedVerticalScrollBarVisibility%2A> Elemente aufgrund aktualisierter Werte der und-Eigenschaften angezeigt und ausgeblendet.  
  
 [!code-cpp[ScrollViewer#1](~/samples/snippets/cpp/VS_Snippets_Wpf/ScrollViewer/CPP/ScrollViewer_wcp.cpp#1)]
 [!code-csharp[ScrollViewer#1](~/samples/snippets/csharp/VS_Snippets_Wpf/ScrollViewer/CSharp/ScrollViewer_wcp.cs#1)]
 [!code-vb[ScrollViewer#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ScrollViewer/VisualBasic/ScrollViewer.vb#1)]
 [!code-xaml[ScrollViewer#1](~/samples/snippets/xaml/VS_Snippets_Wpf/ScrollViewer/XAML/Pane1.xaml#1)]  
  
<a name="scrollviewer_styling_scrollviewer"></a>
## <a name="styling-a-scrollviewer"></a>Formatieren eines ScrollViewer-Elements  
 Wie alle Steuerelemente in <xref:System.Windows.Controls.ScrollViewer> Windows Presentation Foundation kann der formatiert werden, um das Standardmäßige Renderingverhalten des Steuerelements zu ändern. Weitere Informationen zum Formatieren von Steuerelementen finden Sie unter [Erstellen von Formaten und Vorlagen](../../../desktop-wpf/fundamentals/styles-templates-overview.md).  
  
<a name="scrollviewer_scroll_vs_paginate"></a>
## <a name="paginating-documents"></a>Umbrechen von Dokumenten  
 Als Alternative zum Scrollen können Sie für Dokumentinhalte einen Dokumentcontainer auswählen, der Umbrechen unterstützt. <xref:System.Windows.Documents.FlowDocument>ist für Dokumente gedacht, die für das Gehostetwerden in einem Anzeigesteuerelement konzipiert sind, z. <xref:System.Windows.Controls.FlowDocumentPageViewer>B. , das das Paginieren von Inhalten über mehrere Seiten hinweg unterstützt und so verhindert, dass ein Bildlauf erforderlich ist. <xref:System.Windows.Controls.DocumentViewer>bietet eine Lösung <xref:System.Windows.Documents.FixedDocument> zum Anzeigen von Inhalten, bei der herkömmliches Scrollen verwendet wird, um Inhalte außerhalb des Bereichs des Anzeigebereichs anzuzeigen.  
  
 Weitere Informationen zu Dokumentformaten und Präsentationsoptionen finden Sie unter [Dokumente in WPF](../advanced/documents-in-wpf.md).  
  
## <a name="see-also"></a>Weitere Informationen

- <xref:System.Windows.Controls.ScrollViewer>
- <xref:System.Windows.Controls.Primitives.ScrollBar>
- <xref:System.Windows.Controls.Primitives.IScrollInfo>
- [Gewusst wie: Erstellen eines Scroll-Viewers](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms752352(v=vs.90))
- [Dokumente in WPF](../advanced/documents-in-wpf.md)
- [ScrollBar-Stile und -Vorlagen](scrollbar-styles-and-templates.md)
- [Kontrollen](../advanced/optimizing-performance-controls.md)
