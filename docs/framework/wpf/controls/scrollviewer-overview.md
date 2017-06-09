---
title: "&#220;bersicht &#252;ber ScrollViewer | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-wpf"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "Steuerelemente, ScrollViewer"
  - "ScrollViewer-Steuerelement, Informationen über das ScrollViewer-Steuerelement"
ms.assetid: 94a13b94-cfdf-4b12-a1aa-90cb50c6e9b9
caps.latest.revision: 19
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 17
---
# &#220;bersicht &#252;ber ScrollViewer
Der Inhalt innerhalb einer Benutzeroberfläche ist oft umfangreicher als der Anzeigebereich eines Computerbildschirms.  Das <xref:System.Windows.Controls.ScrollViewer>\-Steuerelement bietet eine komfortable Möglichkeit, den Bildlauf für Inhalt in [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]\-Anwendungen zu ermöglichen.  In diesem Thema wird das <xref:System.Windows.Controls.ScrollViewer>\-Element eingeführt. Außerdem werden mehrere Verwendungsbeispiele bereitgestellt.  
  
 Dieses Thema enthält folgende Abschnitte:  
  
<a name="autoTopLevelSectionsOUTLINE0"></a>   
-   [Das ScrollViewer-Steuerelement](#what_is_a_scrollviewer_element)  
  
-   [Physischer Bildlauf im Vergleich zulogischem Bildlauf](#scrollviewer_physical_vs_logical)  
  
-   [Definieren und Verwenden eines ScrollViewer-Elements](#scrollviewer_markup_syntax_and_sample)  
  
-   [Formatieren eines ScrollViewer](#scrollviewer_styling_scrollviewer)  
  
-   [Paginieren von Dokumenten](#scrollviewer_scroll_vs_paginate)  
  
-   [Related Topics](#seeAlsoToggle)  
  
<a name="what_is_a_scrollviewer_element"></a>   
## Das ScrollViewer\-Steuerelement  
 Es gibt zwei vordefinierte Elemente, die einen Bildlauf in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]\-Anwendungen ermöglichen: <xref:System.Windows.Controls.Primitives.ScrollBar> und <xref:System.Windows.Controls.ScrollViewer>.  Das <xref:System.Windows.Controls.ScrollViewer>\-Steuerelement kapselt horizontale und vertikale <xref:System.Windows.Controls.Primitives.ScrollBar>\-Elemente sowie einen Inhaltscontainer \(wie zum Beispiel ein <xref:System.Windows.Controls.Panel>\-Element\), um andere sichtbare Elemente in einem bildlauffähigen Bereich anzuzeigen.  Sie müssen ein benutzerdefiniertes Objekt erstellen, um das <xref:System.Windows.Controls.Primitives.ScrollBar>\-Element für den Bildlauf durch Inhalte zu verwenden.  Sie können jedoch das <xref:System.Windows.Controls.ScrollViewer>\-Element allein verwenden, da es sich um ein zusammengesetztes Steuerelement handelt, das <xref:System.Windows.Controls.Primitives.ScrollBar>\-Funktionalitäten kapselt.  
  
 Das <xref:System.Windows.Controls.ScrollViewer>\-Steuerelement reagiert auf Maus\- und Tastaturbefehle und definiert zahlreiche Methoden, mit denen ein Bildlauf von Inhalten anhand vordefinierter Schritte durchgeführt werden kann.  Sie können das <xref:System.Windows.Controls.ScrollViewer.ScrollChanged>\-Ereignis verwenden, um eine Änderung eines <xref:System.Windows.Controls.ScrollViewer>\-Zustands zu erkennen.  
  
 Ein <xref:System.Windows.Controls.ScrollViewer> kann lediglich ein einzelnes untergeordnetes Element besitzen. Hierbei handelt es sich üblicherweise um ein <xref:System.Windows.Controls.Panel>\-Element, von dem eine <xref:System.Windows.Controls.Panel.Children%2A>\-Auflistung von Elementen gehostet werden kann.  Die <xref:System.Windows.Controls.ContentPresenter.Content%2A>\-Eigenschaft definiert das einzige untergeordnete Element von <xref:System.Windows.Controls.ScrollViewer>.  
  
<a name="scrollviewer_physical_vs_logical"></a>   
## Physischer Bildlauf im Vergleich zulogischem Bildlauf  
 Ein physischer Bildlauf wird verwendet, um Inhalte mit einer vordefinierten physischen Schrittweite zu bewegen, typischerweise durch einen in Pixel festgelegten Wert.  Ein logischer Bildlauf wird verwendet, um zum nächsten Element in der logischen Struktur zu gelangen.  Der physische Bildlauf stellt das Standardbildlaufverhalten für die meisten <xref:System.Windows.Controls.Panel>\-Elemente dar.  Von [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] werden beide Bildlaufarten unterstützt.  
  
#### Die IScrollInfo\-Schnittstelle  
 Die <xref:System.Windows.Controls.Primitives.IScrollInfo>\-Schnittstelle stellt den Hauptbildlaufbereich innerhalb eines <xref:System.Windows.Controls.ScrollViewer>\-Steuerelements oder eines abgeleiteten Steuerelements dar.  Die Schnittstelle definiert Eigenschaften und Methoden für den Bildlauf, die von <xref:System.Windows.Controls.Panel> \-Elementen implementiert werden können, die eher einen Bildlauf auf Basis logischer Einheiten statt physischer Schrittweiten erfordern.  Das Umwandeln einer Instanz von <xref:System.Windows.Controls.Primitives.IScrollInfo> zu einem abgeleiteten <xref:System.Windows.Controls.Panel> und die anschließende Verwendung der zugehörigen Bildlaufmethoden bieten eine praktische Möglichkeit, um einen Bildlauf zur nächsten logischen Einheit in einer untergeordneten Auflistung durchzuführen. Dieses Vorgehen ist besser als die Verwendung von Pixelschritten.  Standardmäßig unterstützt das <xref:System.Windows.Controls.ScrollViewer>\-Steuerelement den Bildlauf auf Basis physischer Einheiten.  
  
 <xref:System.Windows.Controls.StackPanel> und <xref:System.Windows.Controls.VirtualizingStackPanel> implementieren beide <xref:System.Windows.Controls.Primitives.IScrollInfo> und unterstützen direkt einen logischen Bildlauf.  Für Layoutsteuerelemente, die einen logischen Bildlauf direkt unterstützen, können Sie dennoch einen physischen Bildlauf erreichen, indem Sie das <xref:System.Windows.Controls.Panel>\-Hostelement mit einem <xref:System.Windows.Controls.ScrollViewer>\-Element umschließen und die <xref:System.Windows.Controls.ScrollViewer.CanContentScroll%2A>\-Eigenschaft auf `false` festlegen.  
  
 Das folgende Codebeispiel zeigt das Umwandeln einer Instanz von <xref:System.Windows.Controls.Primitives.IScrollInfo> in ein <xref:System.Windows.Controls.StackPanel> und die Verwendung der von der Schnittstelle definierten Bildlaufmethoden \(<xref:System.Windows.Controls.Primitives.IScrollInfo.LineUp%2A> und <xref:System.Windows.Controls.Primitives.IScrollInfo.LineDown%2A>\) für den Inhalt.  
  
 [!code-csharp[IScrollInfoMethods#3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/IScrollInfoMethods/CSharp/Window1.xaml.cs#3)]
 [!code-vb[IScrollInfoMethods#3](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/IScrollInfoMethods/VisualBasic/Window1.xaml.vb#3)]  
  
<a name="scrollviewer_markup_syntax_and_sample"></a>   
## Definieren und Verwenden eines ScrollViewer\-Elements  
 Im folgenden Beispiel wird ein <xref:System.Windows.Controls.ScrollViewer>\-Fenster erstellt, das etwas Text und ein Rechteck enthält.  <xref:System.Windows.Controls.Primitives.ScrollBar>\-Elemente werden nur angezeigt, wenn sie notwendig sind.  Beim Ändern der Fenstergröße werden die <xref:System.Windows.Controls.Primitives.ScrollBar>\-Elemente ein\- oder ausgeblendet, abhängig von den aktualisierten Werten der Eigenschaften <xref:System.Windows.Controls.ScrollViewer.ComputedHorizontalScrollBarVisibility%2A> und <xref:System.Windows.Controls.ScrollViewer.ComputedVerticalScrollBarVisibility%2A>.  
  
 [!code-cpp[ScrollViewer#1](../../../../samples/snippets/cpp/VS_Snippets_Wpf/ScrollViewer/CPP/ScrollViewer_wcp.cpp#1)]
 [!code-csharp[ScrollViewer#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ScrollViewer/CSharp/ScrollViewer_wcp.cs#1)]
 [!code-vb[ScrollViewer#1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ScrollViewer/VisualBasic/ScrollViewer.vb#1)]
 [!code-xml[ScrollViewer#1](../../../../samples/snippets/xaml/VS_Snippets_Wpf/ScrollViewer/XAML/Pane1.xaml#1)]  
  
<a name="scrollviewer_styling_scrollviewer"></a>   
## Formatieren eines ScrollViewer  
 Wie alle Steuerelemente in Windows Presentation Foundation kann <xref:System.Windows.Controls.ScrollViewer> formatiert werden, um das Standardrenderverhalten des Steuerelements zu ändern.  Weitere Informationen zum Formatieren von Steuerelementen finden Sie unter [Erstellen von Formaten und Vorlagen](../../../../docs/framework/wpf/controls/styling-and-templating.md).  
  
<a name="scrollviewer_scroll_vs_paginate"></a>   
## Paginieren von Dokumenten  
 Für Dokumenteninhalte kann als Alternative zum Bildlauf ein Dokumentcontainer ausgewählt werden, der Paginierung unterstützt.  <xref:System.Windows.Documents.FlowDocument> ist für Dokumente gedacht, die innerhalb eines Anzeigesteuerelements \(beispielsweise <xref:System.Windows.Controls.FlowDocumentPageViewer>\) gehostet werden sollen, von dem die Aufteilung des Inhalts auf mehrere Seiten unterstützt und der Bildlauf überflüssig gemacht wird.  Bei <xref:System.Windows.Controls.DocumentViewer> handelt es sich um eine Lösung zum Anzeigen von <xref:System.Windows.Documents.FixedDocument>\-Inhalt, bei der Inhalt außerhalb des Anzeigebereichs mithilfe des herkömmlichen Bildlaufs angezeigt wird.  
  
 Weitere Informationen über Dokumentformate und Präsentationsoptionen finden Sie unter [Dokumente in WPF](../../../../docs/framework/wpf/advanced/documents-in-wpf.md).  
  
## Siehe auch  
 <xref:System.Windows.Controls.ScrollViewer>   
 <xref:System.Windows.Controls.Primitives.ScrollBar>   
 <xref:System.Windows.Controls.Primitives.IScrollInfo>   
 [Create a Scroll Viewer](http://msdn.microsoft.com/de-de/c8e46af7-b417-441b-aa30-791cbdbd43ef)   
 [Dokumente in WPF](../../../../docs/framework/wpf/advanced/documents-in-wpf.md)   
 [ScrollBar\-Stile und \-Vorlagen](../../../../docs/framework/wpf/controls/scrollbar-styles-and-templates.md)   
 [Steuerelemente](../../../../docs/framework/wpf/advanced/optimizing-performance-controls.md)