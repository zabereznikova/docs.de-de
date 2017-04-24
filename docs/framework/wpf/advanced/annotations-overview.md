---
title: "&#220;bersicht &#252;ber Anmerkungen | Microsoft Docs"
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
  - "Dokumente, Anmerkungen"
  - "Markierungen"
  - "Kurznotizen"
ms.assetid: 716bf474-29bd-4c74-84a4-8e0744bdad62
caps.latest.revision: 17
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 16
---
# &#220;bersicht &#252;ber Anmerkungen
Das Niederschreiben von Notizen und Kommentaren auf Papierdokumenten ist eine so häufige Tätigkeit, dass sie als selbstverständlich vorausgesetzt wird.  Bei diesen Notizen und Kommentaren handelt es sich um "Anmerkungen", die Dokumenten zur Markierung von Informationen oder zur Kennzeichnung wichtiger Elemente hinzugefügt werden.  Im Gegensatz zum Schreiben von Notizen auf gedruckte Dokumente ist das Hinzufügen von Notizen in elektronischen Dokumenten oft nur sehr eingeschränkt oder nicht möglich.  
  
 Dieses Thema bietet eine Übersicht über verschiedene häufig verwendete Anmerkungstypen, insbesondere Kurznotizen und Hervorhebungen, und zeigt, wie [!INCLUDE[TLA#tla_caf](../../../../includes/tlasharptla-caf-md.md)] diese Anmerkungstypen in Anwendungen über die [!INCLUDE[TLA#tla_wpf](../../../../includes/tlasharptla-wpf-md.md)]\-Dokumentanzeigesteuerelemente ermöglicht.  Zu den [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]\-Dokumentanzeigesteuerelementen, die Anmerkungen unterstützen, gehören die Elemente <xref:System.Windows.Controls.FlowDocumentReader> und <xref:System.Windows.Controls.FlowDocumentScrollViewer> sowie von <xref:System.Windows.Controls.Primitives.DocumentViewerBase> abgeleitete Steuerelemente wie <xref:System.Windows.Controls.DocumentViewer> und <xref:System.Windows.Controls.FlowDocumentPageViewer>.  
  
   
  
<a name="caf1_type_stickynotes"></a>   
## Kurznotizen  
 Eine typische Haftnotiz ist ein kleines Stück farbiges Papier mit Informationen, das auf ein Dokument geklebt werden kann.  Digitale Kurznotizen bieten eine ähnliche Funktion für elektronische Dokumente, mit der zusätzlichen Flexibilität, viele andere Inhaltstypen zu verwenden, wie über die Tastatur eingegebenen Text, handschriftliche Notizen \(z. B. [!INCLUDE[TLA#tla_tpc](../../../../includes/tlasharptla-tpc-md.md)]\-Freihandeingaben\) und Weblinks.  
  
 Die folgende Abbildung zeigt einige Beispiele für Hervorhebungen, Kurznotizen mit Text und Kurznotizen mit Freihandeingabe.  
  
 ![Textmarker&#45;, Text&#45; und Freihandnotizanmerkungen](../../../../docs/framework/wpf/advanced/media/caf-stickynote.jpg "CAF\_StickyNote")  
  
 Das folgende Beispiel zeigt die Methode, mit der Sie die Unterstützung von Anmerkungen in Ihrer Anwendung aktivieren können.  
  
 [!code-csharp[DocViewerAnnotationsXml#DocViewXmlStartAnnotations](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DocViewerAnnotationsXml/CSharp/Window1.xaml.cs#docviewxmlstartannotations)]
 [!code-vb[DocViewerAnnotationsXml#DocViewXmlStartAnnotations](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DocViewerAnnotationsXml/visualbasic/window1.xaml.vb#docviewxmlstartannotations)]  
  
<a name="caf1_type_callouts"></a>   
## Hervorhebungen  
 Auf Papierdokumenten sind Ihrer Kreativität bei der Markierung von Elementen keine Grenzen gesetzt: Sie können Informationen unterstreichen, mit einem Textmarker hervorheben, Wörter in einem Satz einkreisen, Zeichen und Notizen am Rand hinzufügen usw.  Die Hervorhebungen in [!INCLUDE[TLA#tla_caf](../../../../includes/tlasharptla-caf-md.md)] bieten eine ähnliche Funktion zur Markierung von Informationen in [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]\-Dokumentanzeigesteuerelementen.  
  
 Die folgende Abbildung zeigt ein Beispiel für eine Hervorhebung.  
  
 ![Anmerkung hervorheben](../../../../docs/framework/wpf/advanced/media/caf-callouts.png "CAF\_Callouts")  
  
 In der Regel erstellen Benutzer Anmerkungen, indem sie zunächst einen Textbereich oder ein Element auswählen und dann mit der rechten Maustaste klicken, um ein <xref:System.Windows.Controls.ContextMenu> mit Anmerkungsoptionen anzuzeigen.  Das folgende Beispiel zeigt, wie Sie mit [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] ein <xref:System.Windows.Controls.ContextMenu>\-Element mit Routingbefehlen deklarieren, auf die Benutzer zugreifen können, um Anmerkungen zu erstellen und zu verwalten.  
  
 [!code-xml[DocViewerAnnotationsXps#CreateDeleteAnnotations](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DocViewerAnnotationsXps/CSharp/Window1.xaml#createdeleteannotations)]  
  
<a name="caf1_framework_data_anchoring"></a>   
## Verankerung mit Daten  
 [!INCLUDE[TLA2#tla_caf](../../../../includes/tla2sharptla-caf-md.md)] bindet Anmerkungen an die vom Benutzer ausgewählten Daten, nicht nur an die Position in der Anzeige.  Wenn der Benutzer die Dokumentansicht durch Scrollen oder Zoomen ändert, verbleibt die Anmerkung mit den Daten, an die sie gebunden ist.  Die folgende Abbildung zeigt eine Anmerkung, die ein Benutzer für einen Textausschnitt erstellt hat.  Bei Änderung der Dokumentansicht bewegt sich die Hervorhebung mit den ausgewählten Daten.  
  
 ![Anmerkungsdaten&#45;Verankerung](../../../../docs/framework/wpf/advanced/media/caf-dataanchoring.png "CAF\_DataAnchoring")  
  
<a name="matching_annotations_with_annotated_objects"></a>   
## Zuordnen von Anmerkungen zu Objekten  
 Sie können Anmerkungen den entsprechenden Objekten zuordnen.  Nehmen Sie an, Sie haben eine einfache Anwendung zum Lesen von Dokumenten, die über einen Kommentarbereich verfügt.  Der Kommentarbereich kann ein Listenfeld sein, in dem der Text in Form einer Liste von Anmerkungen dargestellt wird, die in einem Dokument verankert sind.  Wenn ein Element im Listenfeld vom Benutzer ausgewählt wird, zeigt die Anwendung den Abschnitt im Dokument an, an dem das entsprechende Anmerkungsobjekt verankert ist.  
  
 Im folgenden Beispiel wird veranschaulicht, wie der Ereignishandler eines solchen Listenfelds implementiert wird, das als Kommentarbereich dient.  
  
 [!code-csharp[FlowDocumentAnnotatedViewer#Handler](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FlowDocumentAnnotatedViewer/CSharp/Window1.xaml.cs#handler)]
 [!code-vb[FlowDocumentAnnotatedViewer#Handler](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/FlowDocumentAnnotatedViewer/visualbasic/window1.xaml.vb#handler)]  
  
 Ein weiteres Beispiel sind Anwendungen, die den Austausch von Anmerkungen und Kurznotizen zwischen Dokument\-Readern per E\-Mail ermöglichen.  Diese Funktion ermöglicht den Anwendungen, im Reader zu der Seite zu navigieren, die die ausgetauschte Anmerkung enthält.  
  
## Siehe auch  
 <xref:System.Windows.Controls.Primitives.DocumentViewerBase>   
 <xref:System.Windows.Controls.DocumentViewer>   
 <xref:System.Windows.Controls.FlowDocumentPageViewer>   
 <xref:System.Windows.Controls.FlowDocumentScrollViewer>   
 <xref:System.Windows.Controls.FlowDocumentReader>   
 <xref:System.Windows.Annotations.IAnchorInfo>   
 [Annotations\-Schema](../../../../docs/framework/wpf/advanced/annotations-schema.md)   
 [Übersicht über ContextMenu](../../../../docs/framework/wpf/controls/contextmenu-overview.md)   
 [Befehlsübersicht](../../../../docs/framework/wpf/advanced/commanding-overview.md)   
 [Übersicht über Flussdokumente](../../../../docs/framework/wpf/advanced/flow-document-overview.md)   
 [How to: Add a Command to a MenuItem](http://msdn.microsoft.com/de-de/013d68a0-5373-4a68-bd91-5de574307370)