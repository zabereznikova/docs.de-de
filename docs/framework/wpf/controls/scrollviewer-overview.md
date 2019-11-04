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
ms.openlocfilehash: 993f3c861cbead88df3503eb01f18e5d1f69e2d8
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/03/2019
ms.locfileid: "73458439"
---
# <a name="scrollviewer-overview"></a>Übersicht über ScrollViewer
Der Inhalt einer Benutzeroberfläche ist häufig größer als der Anzeigebereich eines Computerbildschirms. Das <xref:System.Windows.Controls.ScrollViewer> Steuerelement bietet eine bequeme Möglichkeit, den Bildlauf von Inhalten in [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] Anwendungen zu ermöglichen. In diesem Thema wird das <xref:System.Windows.Controls.ScrollViewer>-Element vorgestellt und einige Verwendungs Beispiele bereitstellt.  
  
<a name="what_is_a_scrollviewer_element"></a>   
## <a name="the-scrollviewer-control"></a>Das ScrollViewer-Steuerelement  
 Es gibt zwei vordefinierte Elemente, die das Scrollen in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Anwendungen ermöglichen: <xref:System.Windows.Controls.Primitives.ScrollBar> und <xref:System.Windows.Controls.ScrollViewer>. Das <xref:System.Windows.Controls.ScrollViewer>-Steuerelement kapselt horizontale und vertikale <xref:System.Windows.Controls.Primitives.ScrollBar> Elemente und einen Inhalts Container (z. b. ein <xref:System.Windows.Controls.Panel>-Element), um andere sichtbare Elemente in einem scrollbaren Bereich anzuzeigen. Sie müssen ein benutzerdefiniertes-Objekt erstellen, um das <xref:System.Windows.Controls.Primitives.ScrollBar>-Element für das Scrollen von Inhalten zu verwenden. Allerdings können Sie das <xref:System.Windows.Controls.ScrollViewer>-Element eigenständig verwenden, da es sich um ein zusammengesetztes Steuerelement handelt, das <xref:System.Windows.Controls.Primitives.ScrollBar> Funktionalität kapselt.  
  
 Das <xref:System.Windows.Controls.ScrollViewer>-Steuerelement reagiert sowohl auf Maus-als auch auf Tastaturbefehle und definiert zahlreiche Methoden, mit denen der Inhalt durch vordefinierte Inkremente Scrollen kann. Sie können das <xref:System.Windows.Controls.ScrollViewer.ScrollChanged>-Ereignis verwenden, um eine Änderung in einem <xref:System.Windows.Controls.ScrollViewer> Zustand zu erkennen.  
  
 Eine <xref:System.Windows.Controls.ScrollViewer> kann nur ein untergeordnetes Element haben, in der Regel ein <xref:System.Windows.Controls.Panel> Element, das eine <xref:System.Windows.Controls.Panel.Children%2A> Auflistung von Elementen hosten kann. Die <xref:System.Windows.Controls.ContentPresenter.Content%2A>-Eigenschaft definiert das einzige untergeordnete Element des <xref:System.Windows.Controls.ScrollViewer>.  
  
<a name="scrollviewer_physical_vs_logical"></a>   
## <a name="physical-vs-logical-scrolling"></a>Physisches und logisches Scrollen  
 Das physische Scrollen wird zum Scrollen durch Inhalt anhand eines vordefinierten physischen Werts verwendet – in der Regel durch einen Wert in Pixel. Das logische Scrollen wird verwendet, um zum nächsten Element in einer logischen Struktur zu scrollen. Physischer Bildlauf ist das Standardbild Laufverhalten für die meisten <xref:System.Windows.Controls.Panel> Elemente. [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]unterstützt beide Scrolltypen.  
  
#### <a name="the-iscrollinfo-interface"></a>Die IScrollInfo-Schnittstelle  
 Die <xref:System.Windows.Controls.Primitives.IScrollInfo>-Schnittstelle stellt den hauptscrollbereich in einem <xref:System.Windows.Controls.ScrollViewer> oder abgeleiteten Steuerelement dar. Die-Schnittstelle definiert scrolleigenschaften und-Methoden, die von <xref:System.Windows.Controls.Panel> Elementen implementiert werden können, die einen Bildlauf durch eine logische Einheit erfordern, anstatt durch ein physisches Inkrement. Das Umwandeln einer Instanz von <xref:System.Windows.Controls.Primitives.IScrollInfo> in eine abgeleitete <xref:System.Windows.Controls.Panel> und die anschließende Verwendung der scrollmethoden bietet eine hilfreiche Möglichkeit, einen Bildlauf zur nächsten logischen Einheit in einer untergeordneten Auflistung statt nach Pixel Inkrement durchführen zu können. Standardmäßig unterstützt das <xref:System.Windows.Controls.ScrollViewer>-Steuerelement den Bildlauf nach physischen Einheiten.  
  
 <xref:System.Windows.Controls.StackPanel> und <xref:System.Windows.Controls.VirtualizingStackPanel> implementieren beide <xref:System.Windows.Controls.Primitives.IScrollInfo> und unterstützen das logische scrollen. Für Layoutsteuerelemente, die einen logischen Bildlauf unterstützen, können Sie dennoch einen physischen Bildlauf durchführen, indem Sie den Host <xref:System.Windows.Controls.Panel> Element in ein <xref:System.Windows.Controls.ScrollViewer> umwickeln und die <xref:System.Windows.Controls.ScrollViewer.CanContentScroll%2A>-Eigenschaft auf `false`festlegen.  
  
 Im folgenden Codebeispiel wird veranschaulicht, wie Sie eine Instanz von <xref:System.Windows.Controls.Primitives.IScrollInfo> in eine <xref:System.Windows.Controls.StackPanel> umwandeln und Inhalts scrollmethoden (<xref:System.Windows.Controls.Primitives.IScrollInfo.LineUp%2A> und <xref:System.Windows.Controls.Primitives.IScrollInfo.LineDown%2A>) verwenden, die von der-Schnittstelle definiert werden.  
  
 [!code-csharp[IScrollInfoMethods#3](~/samples/snippets/csharp/VS_Snippets_Wpf/IScrollInfoMethods/CSharp/Window1.xaml.cs#3)]
 [!code-vb[IScrollInfoMethods#3](~/samples/snippets/visualbasic/VS_Snippets_Wpf/IScrollInfoMethods/VisualBasic/Window1.xaml.vb#3)]  
  
<a name="scrollviewer_markup_syntax_and_sample"></a>   
## <a name="defining-and-using-a-scrollviewer-element"></a>Definieren und Verwenden eines ScrollViewer-Elements  
 Im folgenden Beispiel wird ein <xref:System.Windows.Controls.ScrollViewer> in einem Fenster erstellt, das Text und ein Rechteck enthält. <xref:System.Windows.Controls.Primitives.ScrollBar> Elemente werden nur angezeigt, wenn Sie erforderlich sind. Wenn Sie die Größe des Fensters ändern, werden die <xref:System.Windows.Controls.Primitives.ScrollBar> Elemente aufgrund aktualisierter Werte der Eigenschaften <xref:System.Windows.Controls.ScrollViewer.ComputedHorizontalScrollBarVisibility%2A> und <xref:System.Windows.Controls.ScrollViewer.ComputedVerticalScrollBarVisibility%2A> angezeigt und ausgeblendet.  
  
 [!code-cpp[ScrollViewer#1](~/samples/snippets/cpp/VS_Snippets_Wpf/ScrollViewer/CPP/ScrollViewer_wcp.cpp#1)]
 [!code-csharp[ScrollViewer#1](~/samples/snippets/csharp/VS_Snippets_Wpf/ScrollViewer/CSharp/ScrollViewer_wcp.cs#1)]
 [!code-vb[ScrollViewer#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ScrollViewer/VisualBasic/ScrollViewer.vb#1)]
 [!code-xaml[ScrollViewer#1](~/samples/snippets/xaml/VS_Snippets_Wpf/ScrollViewer/XAML/Pane1.xaml#1)]  
  
<a name="scrollviewer_styling_scrollviewer"></a>   
## <a name="styling-a-scrollviewer"></a>Formatieren eines ScrollViewer-Elements  
 Wie alle Steuerelemente in Windows Presentation Foundation können die <xref:System.Windows.Controls.ScrollViewer> formatiert werden, um das standardmäßige Renderingverhalten des Steuer Elements zu ändern. Weitere Informationen zum Formatieren von Steuerelementen finden Sie unter [Erstellen von Formaten und Vorlagen](../../../desktop-wpf/fundamentals/styles-templates-overview.md).  
  
<a name="scrollviewer_scroll_vs_paginate"></a>   
## <a name="paginating-documents"></a>Umbrechen von Dokumenten  
 Als Alternative zum Scrollen können Sie für Dokumentinhalte einen Dokumentcontainer auswählen, der Umbrechen unterstützt. <xref:System.Windows.Documents.FlowDocument> gilt für Dokumente, die in einem Anzeige Steuerelement gehostet werden sollen, z. b. <xref:System.Windows.Controls.FlowDocumentPageViewer>, das das Paginieren von Inhalten über mehrere Seiten hinweg unterstützt, sodass kein Bildlauf notwendig ist. <xref:System.Windows.Controls.DocumentViewer> stellt eine Projekt Mappe zum Anzeigen <xref:System.Windows.Documents.FixedDocument> Inhalts bereit, in dem herkömmliches Scrollen verwendet wird, um Inhalte außerhalb des Bereichs des Anzeige Bereichs anzuzeigen.  
  
 Weitere Informationen zu Dokumentformaten und Präsentationsoptionen finden Sie unter [Dokumente in WPF](../advanced/documents-in-wpf.md).  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Windows.Controls.ScrollViewer>
- <xref:System.Windows.Controls.Primitives.ScrollBar>
- <xref:System.Windows.Controls.Primitives.IScrollInfo>
- [Gewusst wie: Erstellen eines ScrollViewers](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms752352(v=vs.90))
- [Dokumente in WPF](../advanced/documents-in-wpf.md)
- [ScrollBar-Stile und -Vorlagen](scrollbar-styles-and-templates.md)
- [Steuerelemente](../advanced/optimizing-performance-controls.md)
