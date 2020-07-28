---
title: Übersicht über ScrollViewer
description: Erfahren Sie mehr über das ScrollViewer-Steuerelement, das das Scrollen von Inhalten in Windows Presentation Foundation Anwendungen ermöglicht. Siehe Verwendungs Beispiele.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- controls [WPF], ScrollViewer
- ScrollViewer control [WPF], about ScrollViewer control
ms.assetid: 94a13b94-cfdf-4b12-a1aa-90cb50c6e9b9
ms.openlocfilehash: 1ef680bb004315a2b523814714d5533535d044e5
ms.sourcegitcommit: 87cfeb69226fef01acb17c56c86f978f4f4a13db
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/24/2020
ms.locfileid: "87164633"
---
# <a name="scrollviewer-overview"></a>Übersicht über ScrollViewer
Der Inhalt einer Benutzeroberfläche ist häufig größer als der Anzeigebereich eines Computerbildschirms. Das- <xref:System.Windows.Controls.ScrollViewer> Steuerelement bietet eine bequeme Möglichkeit, den Bildlauf von Inhalten in-Anwendungen zu ermöglichen [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] . In diesem Thema wird das <xref:System.Windows.Controls.ScrollViewer> -Element vorgestellt und einige Verwendungs Beispiele bereitstellt.  
  
<a name="what_is_a_scrollviewer_element"></a>
## <a name="the-scrollviewer-control"></a>Das ScrollViewer-Steuerelement  
 Es gibt zwei vordefinierte Elemente, die das Scrollen in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Anwendungen ermöglichen: <xref:System.Windows.Controls.Primitives.ScrollBar> und <xref:System.Windows.Controls.ScrollViewer> . Das- <xref:System.Windows.Controls.ScrollViewer> Steuerelement kapselt horizontale und vertikale <xref:System.Windows.Controls.Primitives.ScrollBar> Elemente und einen Inhalts Container (z. b. ein- <xref:System.Windows.Controls.Panel> Element), um andere sichtbare Elemente in einem scrollbaren Bereich anzuzeigen. Sie müssen ein benutzerdefiniertes-Objekt erstellen, um das- <xref:System.Windows.Controls.Primitives.ScrollBar> Element für das Scrollen von Inhalten zu verwenden. Allerdings können Sie das- <xref:System.Windows.Controls.ScrollViewer> Element allein verwenden, da es sich um ein zusammengesetztes Steuerelement handelt, das Funktionen kapselt <xref:System.Windows.Controls.Primitives.ScrollBar> .  
  
 Das <xref:System.Windows.Controls.ScrollViewer> -Steuerelement reagiert sowohl auf Maus-als auch auf Tastaturbefehle und definiert zahlreiche Methoden, mit denen der Inhalt durch vordefinierte Inkremente Scrollen kann. Sie können das- <xref:System.Windows.Controls.ScrollViewer.ScrollChanged> Ereignis verwenden, um eine Änderung in einem Zustand zu erkennen <xref:System.Windows.Controls.ScrollViewer> .  
  
 Ein <xref:System.Windows.Controls.ScrollViewer> kann nur ein untergeordnetes Element haben, in der Regel ein- <xref:System.Windows.Controls.Panel> Element, das eine Auflistung von-Elementen hosten kann <xref:System.Windows.Controls.Panel.Children%2A> Die- <xref:System.Windows.Controls.ContentPresenter.Content%2A> Eigenschaft definiert das einzige untergeordnete Element von <xref:System.Windows.Controls.ScrollViewer> .  
  
<a name="scrollviewer_physical_vs_logical"></a>
## <a name="physical-vs-logical-scrolling"></a>Physisches und logisches Scrollen  
 Das physische Scrollen wird zum Scrollen durch Inhalt anhand eines vordefinierten physischen Werts verwendet – in der Regel durch einen Wert in Pixel. Das logische Scrollen wird verwendet, um zum nächsten Element in einer logischen Struktur zu scrollen. Physischer Bildlauf ist das standardmäßige Scrollverhalten für die meisten- <xref:System.Windows.Controls.Panel> Elemente. [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]unterstützt beide Scrolltypen.  
  
#### <a name="the-iscrollinfo-interface"></a>Die IScrollInfo-Schnittstelle  
 Die- <xref:System.Windows.Controls.Primitives.IScrollInfo> Schnittstelle stellt den Hauptbild Laufbereich in einem <xref:System.Windows.Controls.ScrollViewer> abgeleiteten-Steuerelement oder einem Die-Schnittstelle definiert scrolleigenschaften und-Methoden, die von Elementen implementiert werden können <xref:System.Windows.Controls.Panel> , die einen Bildlauf durch eine logische Einheit erfordern, anstatt durch ein physisches Inkrement. Das Umwandeln einer Instanz von <xref:System.Windows.Controls.Primitives.IScrollInfo> in eine abgeleitete <xref:System.Windows.Controls.Panel> und anschließende Verwendung ihrer scrollmethoden bietet eine nützliche Möglichkeit, einen Bildlauf zur nächsten logischen Einheit in einer untergeordneten Auflistung statt nach Pixel Inkrement durchführen zu können. Standardmäßig unterstützt das-Steuerelement den Bildlauf <xref:System.Windows.Controls.ScrollViewer> nach physischen Einheiten.  
  
 <xref:System.Windows.Controls.StackPanel>und <xref:System.Windows.Controls.VirtualizingStackPanel> implementieren und <xref:System.Windows.Controls.Primitives.IScrollInfo> unterstützen das logische scrollen. Für Layoutsteuerelemente, die einen logischen Bildlauf nativ unterstützen, können Sie dennoch einen physischen Bildlauf durchführen, indem Sie das <xref:System.Windows.Controls.Panel> -Host Element in ein <xref:System.Windows.Controls.ScrollViewer> - <xref:System.Windows.Controls.ScrollViewer.CanContentScroll%2A> Objekt `false` umwickeln und  
  
 Im folgenden Codebeispiel wird veranschaulicht, wie eine Instanz von <xref:System.Windows.Controls.Primitives.IScrollInfo> in eine umgewandelt <xref:System.Windows.Controls.StackPanel> wird und wie <xref:System.Windows.Controls.Primitives.IScrollInfo.LineUp%2A> <xref:System.Windows.Controls.Primitives.IScrollInfo.LineDown%2A> von der-Schnittstelle definierte Inhalts scrollmethoden (und) verwendet werden.  
  
 [!code-csharp[IScrollInfoMethods#3](~/samples/snippets/csharp/VS_Snippets_Wpf/IScrollInfoMethods/CSharp/Window1.xaml.cs#3)]
 [!code-vb[IScrollInfoMethods#3](~/samples/snippets/visualbasic/VS_Snippets_Wpf/IScrollInfoMethods/VisualBasic/Window1.xaml.vb#3)]  
  
<a name="scrollviewer_markup_syntax_and_sample"></a>
## <a name="defining-and-using-a-scrollviewer-element"></a>Definieren und Verwenden eines ScrollViewer-Elements  
 Im folgenden Beispiel wird ein <xref:System.Windows.Controls.ScrollViewer> -Wert in einem Fenster erstellt, das Text und ein Rechteck enthält. <xref:System.Windows.Controls.Primitives.ScrollBar>Elemente werden nur angezeigt, wenn Sie erforderlich sind. Wenn Sie die Größe des Fensters ändern, werden die <xref:System.Windows.Controls.Primitives.ScrollBar> Elemente aufgrund von aktualisierten Werten der-Eigenschaft und der-Eigenschaft angezeigt und ausgeblendet <xref:System.Windows.Controls.ScrollViewer.ComputedHorizontalScrollBarVisibility%2A> <xref:System.Windows.Controls.ScrollViewer.ComputedVerticalScrollBarVisibility%2A> .  
  
 [!code-cpp[ScrollViewer#1](~/samples/snippets/cpp/VS_Snippets_Wpf/ScrollViewer/CPP/ScrollViewer_wcp.cpp#1)]
 [!code-csharp[ScrollViewer#1](~/samples/snippets/csharp/VS_Snippets_Wpf/ScrollViewer/CSharp/ScrollViewer_wcp.cs#1)]
 [!code-vb[ScrollViewer#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ScrollViewer/VisualBasic/ScrollViewer.vb#1)]
 [!code-xaml[ScrollViewer#1](~/samples/snippets/xaml/VS_Snippets_Wpf/ScrollViewer/XAML/Pane1.xaml#1)]  
  
<a name="scrollviewer_styling_scrollviewer"></a>
## <a name="styling-a-scrollviewer"></a>Formatieren eines ScrollViewer-Elements  
 Wie bei allen Steuerelementen in Windows Presentation Foundation kann der formatiert werden, um <xref:System.Windows.Controls.ScrollViewer> das standardmäßige Renderingverhalten des Steuer Elements zu ändern. Weitere Informationen zum Formatieren von Steuerelementen finden Sie unter [Erstellen von Formaten und Vorlagen](../../../desktop-wpf/fundamentals/styles-templates-overview.md).  
  
<a name="scrollviewer_scroll_vs_paginate"></a>
## <a name="paginating-documents"></a>Umbrechen von Dokumenten  
 Als Alternative zum Scrollen können Sie für Dokumentinhalte einen Dokumentcontainer auswählen, der Umbrechen unterstützt. <xref:System.Windows.Documents.FlowDocument>gilt für Dokumente, die in einem Anzeige Steuerelement gehostet werden sollen, wie z <xref:System.Windows.Controls.FlowDocumentPageViewer> . b., das das Paginieren von Inhalten über mehrere Seiten hinweg unterstützt, sodass der Bildlauf nicht erforderlich ist. <xref:System.Windows.Controls.DocumentViewer>stellt eine Projekt Mappe zum <xref:System.Windows.Documents.FixedDocument> Anzeigen von Inhalten bereit, in der das herkömmliche Scrollen verwendet wird, um Inhalte außerhalb des Bereichs des Anzeige Bereichs anzuzeigen.  
  
 Weitere Informationen zu Dokumentformaten und Präsentationsoptionen finden Sie unter [Dokumente in WPF](../advanced/documents-in-wpf.md).  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Windows.Controls.ScrollViewer>
- <xref:System.Windows.Controls.Primitives.ScrollBar>
- <xref:System.Windows.Controls.Primitives.IScrollInfo>
- [Gewusst wie: Erstellen eines ScrollViewers](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms752352(v=vs.90))
- [Dokumente in WPF](../advanced/documents-in-wpf.md)
- [ScrollBar-Stile und -Vorlagen](scrollbar-styles-and-templates.md)
- [Steuerelemente](../advanced/optimizing-performance-controls.md)
