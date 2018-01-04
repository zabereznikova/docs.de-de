---
title: "Übersicht über ScrollViewer"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- controls [WPF], ScrollViewer
- ScrollViewer control [WPF], about ScrollViewer control
ms.assetid: 94a13b94-cfdf-4b12-a1aa-90cb50c6e9b9
caps.latest.revision: "19"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 0d060e0b511f17a68edb013ae7241e1accbc7dcf
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="scrollviewer-overview"></a>Übersicht über ScrollViewer
Der Inhalt einer Benutzeroberfläche ist häufig größer als der Anzeigebereich eines Computerbildschirms. Die <xref:System.Windows.Controls.ScrollViewer> Steuerelement stellt eine einfache Möglichkeit, aktivieren Sie Bildläufe von Inhalt in [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] Anwendungen. Dieses Thema enthält die <xref:System.Windows.Controls.ScrollViewer> Element sowie mehrere Beispiele für die Verwendung.  
  
<a name="what_is_a_scrollviewer_element"></a>   
## <a name="the-scrollviewer-control"></a>Das ScrollViewer-Steuerelement  
 Es gibt zwei vordefinierte Elemente, die es ermöglichen, Durchführen eines Bildlaufs [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Anwendungen: <xref:System.Windows.Controls.Primitives.ScrollBar> und <xref:System.Windows.Controls.ScrollViewer>. Die <xref:System.Windows.Controls.ScrollViewer> kapselt horizontalen und vertikalen <xref:System.Windows.Controls.Primitives.ScrollBar> Elemente und einen Content-Container (z. B. eine <xref:System.Windows.Controls.Panel> Element) um weitere sichtbare Elemente in einem bildlauffähigen Bereich anzuzeigen. Sie müssen ein benutzerdefiniertes Objekt erstellen, um verwenden die <xref:System.Windows.Controls.Primitives.ScrollBar> -Element für Inhalt durchführen eines Bildlaufs. Allerdings können Sie die <xref:System.Windows.Controls.ScrollViewer> Element selbst ist ein zusammengesetztes Steuerelement, das kapselt <xref:System.Windows.Controls.Primitives.ScrollBar> Funktionalität.  
  
 Die <xref:System.Windows.Controls.ScrollViewer> -Steuerelement reagiert auf Maus und Tastatur und zahlreiche Methoden, mit denen in festgelegten Schritten einen Bildlauf im Inhalt definiert. Können Sie die <xref:System.Windows.Controls.ScrollViewer.ScrollChanged> Ereignis, um eine Änderung erkennen einer <xref:System.Windows.Controls.ScrollViewer> Zustand.  
  
 Ein <xref:System.Windows.Controls.ScrollViewer> kann ein untergeordnetes Element nur in der Regel haben eine <xref:System.Windows.Controls.Panel> Element, das hosten kann eine <xref:System.Windows.Controls.Panel.Children%2A> Auflistung von Elementen. Die <xref:System.Windows.Controls.ContentPresenter.Content%2A> -Eigenschaft definiert das einzige untergeordnete Element von der <xref:System.Windows.Controls.ScrollViewer>.  
  
<a name="scrollviewer_physical_vs_logical"></a>   
## <a name="physical-vs-logical-scrolling"></a>Physische im Vergleich zu Logische Durchführen eines Bildlaufs  
 Das physische Scrollen wird zum Scrollen durch Inhalt anhand eines vordefinierten physischen Werts verwendet – in der Regel durch einen Wert in Pixel. Das logische Scrollen wird verwendet, um zum nächsten Element in einer logischen Struktur zu scrollen. Physische Bildlauf ist das Scroll-Standardverhalten für die meisten <xref:System.Windows.Controls.Panel> Elemente. [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]unterstützt beide Scrolltypen.  
  
#### <a name="the-iscrollinfo-interface"></a>Die IScrollInfo-Schnittstelle  
 Die <xref:System.Windows.Controls.Primitives.IScrollInfo> Schnittstelle darstellt, die wichtigsten Bildlaufbereich innerhalb einer <xref:System.Windows.Controls.ScrollViewer> oder abgeleiteten Steuerelements. Die Schnittstelle definiert, Durchführen eines Bildlaufs Eigenschaften und Methoden, die von implementiert werden können <xref:System.Windows.Controls.Panel> Elemente, die erfordern, Durchführen eines Bildlaufs durch die logische Einheit, anstatt mit einer physischen Erhöhung. Umwandeln einer Instanz von <xref:System.Windows.Controls.Primitives.IScrollInfo> zu einem abgeleiteten <xref:System.Windows.Controls.Panel> , und klicken Sie dann ihre fortlaufenden Methoden bietet eine gute Möglichkeit, führen Sie einen Bildlauf zur nächsten logischen Einheit in einer untergeordneten Sammlung. Wird standardmäßig die <xref:System.Windows.Controls.ScrollViewer> Steuerelement unterstützt das Durchführen eines Bildlaufs durch physische Einheiten.  
  
 <xref:System.Windows.Controls.StackPanel>und <xref:System.Windows.Controls.VirtualizingStackPanel> beide implementieren <xref:System.Windows.Controls.Primitives.IScrollInfo> und systemeigene Unterstützung für logische Durchführen eines Bildlaufs. Für Layout-Steuerelemente, systemintern Unterstützung logischer Bildläufe, Sie können dennoch erreichen physischen Durchführen eines Bildlaufs durch den Host wrapping <xref:System.Windows.Controls.Panel> Element in eine <xref:System.Windows.Controls.ScrollViewer> verwendet wird und die <xref:System.Windows.Controls.ScrollViewer.CanContentScroll%2A> Eigenschaft `false`.  
  
 Im folgenden Codebeispiel wird veranschaulicht, wie eine Instanz von umwandeln <xref:System.Windows.Controls.Primitives.IScrollInfo> zu einem <xref:System.Windows.Controls.StackPanel> und Durchführen eines Bildlaufs inhaltsmethoden verwenden (<xref:System.Windows.Controls.Primitives.IScrollInfo.LineUp%2A> und <xref:System.Windows.Controls.Primitives.IScrollInfo.LineDown%2A>) durch die Schnittstelle definiert.  
  
 [!code-csharp[IScrollInfoMethods#3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/IScrollInfoMethods/CSharp/Window1.xaml.cs#3)]
 [!code-vb[IScrollInfoMethods#3](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/IScrollInfoMethods/VisualBasic/Window1.xaml.vb#3)]  
  
<a name="scrollviewer_markup_syntax_and_sample"></a>   
## <a name="defining-and-using-a-scrollviewer-element"></a>Definieren und Verwenden eines ScrollViewer-Elements  
 Das folgende Beispiel erstellt eine <xref:System.Windows.Controls.ScrollViewer> in einem Fenster, die Text und ein Rechteck enthält. <xref:System.Windows.Controls.Primitives.ScrollBar>Elemente angezeigt werden, nur wenn diese erforderlich sind. Wenn Sie die Größe des Fensters die <xref:System.Windows.Controls.Primitives.ScrollBar> Elemente angezeigt werden und nicht mehr angezeigt, aufgrund der aktualisierten Werte der <xref:System.Windows.Controls.ScrollViewer.ComputedHorizontalScrollBarVisibility%2A> und <xref:System.Windows.Controls.ScrollViewer.ComputedVerticalScrollBarVisibility%2A> Eigenschaften.  
  
 [!code-cpp[ScrollViewer#1](../../../../samples/snippets/cpp/VS_Snippets_Wpf/ScrollViewer/CPP/ScrollViewer_wcp.cpp#1)]
 [!code-csharp[ScrollViewer#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ScrollViewer/CSharp/ScrollViewer_wcp.cs#1)]
 [!code-vb[ScrollViewer#1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ScrollViewer/VisualBasic/ScrollViewer.vb#1)]
 [!code-xaml[ScrollViewer#1](../../../../samples/snippets/xaml/VS_Snippets_Wpf/ScrollViewer/XAML/Pane1.xaml#1)]  
  
<a name="scrollviewer_styling_scrollviewer"></a>   
## <a name="styling-a-scrollviewer"></a>Formatieren eines ScrollViewer-Elements  
 Wie alle Steuerelemente in Windows Presentation Foundation, die <xref:System.Windows.Controls.ScrollViewer> formatiert werden können, um das Standardverhalten für die Darstellung des Steuerelements zu ändern. Weitere Informationen zum Formatieren von Steuerelementen finden Sie unter [Erstellen von Formaten und Vorlagen](../../../../docs/framework/wpf/controls/styling-and-templating.md).  
  
<a name="scrollviewer_scroll_vs_paginate"></a>   
## <a name="paginating-documents"></a>Umbrechen von Dokumenten  
 Als Alternative zum Scrollen können Sie für Dokumentinhalte einen Dokumentcontainer auswählen, der Umbrechen unterstützt. <xref:System.Windows.Documents.FlowDocument>ist für Dokumente, die entwickelt wurden, in einem Steuerelement anzeigen gehostet werden, z. B. <xref:System.Windows.Controls.FlowDocumentPageViewer>, Anzeigesteuerelements Inhalt über mehrere Seiten, entfällt die Notwendigkeit, Durchführen eines Bildlaufs unterstützt. <xref:System.Windows.Controls.DocumentViewer>bietet eine Lösung für die Anzeige <xref:System.Windows.Documents.FixedDocument> Inhalt, der mithilfe des herkömmlichen Bildlaufs außerhalb der Bereich neben dem Anzeigebereich angezeigt werden sollen.  
  
 Weitere Informationen zu Dokumentformaten und Präsentationsoptionen finden Sie unter [Dokumente in WPF](../../../../docs/framework/wpf/advanced/documents-in-wpf.md).  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Windows.Controls.ScrollViewer>  
 <xref:System.Windows.Controls.Primitives.ScrollBar>  
 <xref:System.Windows.Controls.Primitives.IScrollInfo>  
 [Erstellen Sie einen Bildlauf-Viewer](http://msdn.microsoft.com/en-us/c8e46af7-b417-441b-aa30-791cbdbd43ef)  
 [Dokumente in WPF](../../../../docs/framework/wpf/advanced/documents-in-wpf.md)  
 [ScrollBar-Stile und -Vorlagen](../../../../docs/framework/wpf/controls/scrollbar-styles-and-templates.md)  
 [Steuerelemente](../../../../docs/framework/wpf/advanced/optimizing-performance-controls.md)
