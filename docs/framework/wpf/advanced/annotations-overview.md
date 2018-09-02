---
title: Übersicht über Anmerkungen
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- highlights [WPF]
- documents [WPF], annotations
- sticky notes [WPF]
ms.assetid: 716bf474-29bd-4c74-84a4-8e0744bdad62
ms.openlocfilehash: 690ec5f2bca7c10aba291cdde6e8bc455e7fd43a
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/02/2018
ms.locfileid: "43463966"
---
# <a name="annotations-overview"></a>Übersicht über Anmerkungen
Das Schreiben von Notizen oder Kommentare auf Papierdokumenten ist solch eine verbreitete Aktivität, dass wir sie als selbstverständlich erachten. Diese Notizen oder Kommentare sind „Anmerkungen“, die wir einem Dokument hinzufügen, um Informationen zu kennzeichnen oder um interessante Elemente für einen späteren Zeitpunkt zu markieren. Obwohl das Schreiben von Notizen auf gedruckte Dokumente einfach und üblich ist, ist die Möglichkeit, persönliche Kommentare auf elektronischen Dokumenten hinzuzufügen, in der Regel nur sehr eingeschränkt, falls diese Möglichkeit überhaupt verfügbar ist.  
  
 In diesem Thema werden mehrere allgemeine Typen von Anmerkungen, insbesondere Kurznotizen und Markierungen, und veranschaulicht, wie die [!INCLUDE[TLA#tla_caf](../../../../includes/tlasharptla-caf-md.md)] erleichtert diese Typen von Anmerkungen in Anwendungen, die durch das Windows Presentation Foundation (WPF)-Dokument Steuerelemente für das anzeigen.  [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] Steuerelemente für das Dokument anzeigen, die Anmerkungen unterstützen enthalten <xref:System.Windows.Controls.FlowDocumentReader> und <xref:System.Windows.Controls.FlowDocumentScrollViewer>sowie Steuerelemente abgeleitet <xref:System.Windows.Controls.Primitives.DocumentViewerBase> wie z. B. <xref:System.Windows.Controls.DocumentViewer> und <xref:System.Windows.Controls.FlowDocumentPageViewer>.  
  
  
<a name="caf1_type_stickynotes"></a>   
## <a name="sticky-notes"></a>Kurznotizen  
 Eine normale Kurznotiz enthält Informationen, die auf ein kleines Stück farbiges Papier geschrieben werden, das dann auf ein Dokument „geklebt“ wird. Digitale Kurznotizen bieten ähnliche Funktionen für elektronische Dokumente, jedoch mit der zusätzlichen Flexibilität, viele andere Inhaltstypen wie eingegebenen Text, handschriftliche Notizen (z.B. [!INCLUDE[TLA#tla_tpc](../../../../includes/tlasharptla-tpc-md.md)]-Freihandeingabestriche), oder Weblinks einzuschließen.  
  
 Die folgende Abbildung zeigt einige Beispiele von Hervorhebungen, Kurznotizen und Freihandnotizanmerkungen.  
  
 ![Textmarker-, Text- und Freihandnotizanmerkungen](../../../../docs/framework/wpf/advanced/media/caf-stickynote.jpg "CAF_StickyNote")  
  
 Das folgende Beispiel zeigt die Methode, die Sie zum Aktivieren der Unterstützung von Kommentaren in der Anwendung verwenden können.  
  
 [!code-csharp[DocViewerAnnotationsXml#DocViewXmlStartAnnotations](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DocViewerAnnotationsXml/CSharp/Window1.xaml.cs#docviewxmlstartannotations)]
 [!code-vb[DocViewerAnnotationsXml#DocViewXmlStartAnnotations](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DocViewerAnnotationsXml/visualbasic/window1.xaml.vb#docviewxmlstartannotations)]  
  
<a name="caf1_type_callouts"></a>   
## <a name="highlights"></a>Markierungen  
 Personen, die kreative Methoden verwenden, können Aufmerksamkeit auf Elemente ziehen, wenn Sie ein Papierdokument beschreiben, z.B. Wörter in einem Satz unterstreichen, markieren, einkreisen oder Markierungen oder Notationen am Rand hinzufügen.  Das markieren von Anmerkungen in [!INCLUDE[TLA#tla_caf](../../../../includes/tlasharptla-caf-md.md)] bietet eine ähnliche Funktion zum Markieren von Informationen, die in Steuerelementen für das Anzeigen des [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]-Dokuments angezeigt wird.  
  
 In der folgenden Abbildung ist ein Beispiel einer markierten Anmerkung dargestellt:  
  
 ![Anmerkung hervorheben](../../../../docs/framework/wpf/advanced/media/caf-callouts.png "CAF_Callouts")  
  
 Benutzer erstellen Anmerkungen in der Regel von der ersten Auswahl von Text oder ein Element von Interesse sind, und klicken Sie dann mit der rechten Maustaste, um anzuzeigen einer <xref:System.Windows.Controls.ContextMenu> einer Anmerkungsoption.  Das folgende Beispiel zeigt die [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] können Sie Sie deklarieren eine <xref:System.Windows.Controls.ContextMenu> mit weitergeleiteten Befehlen, die Benutzer zugreifen können, zum Erstellen und Verwalten von Anmerkungen.  
  
 [!code-xaml[DocViewerAnnotationsXps#CreateDeleteAnnotations](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DocViewerAnnotationsXps/CSharp/Window1.xaml#createdeleteannotations)]  
  
<a name="caf1_framework_data_anchoring"></a>   
## <a name="data-anchoring"></a>Verankerung von Daten  
 Durch [!INCLUDE[TLA2#tla_caf](../../../../includes/tla2sharptla-caf-md.md)] werden Anmerkungen an Daten gebunden, die der Benutzer auswählt, und nicht nur an eine Position auf der dargestellten Anzeige. Deshalb bleibt die Anmerkung bei der Datenauswahl, an die sie gebunden ist, wenn der Benutzer das Anzeigefenster nach oben oder unten verschiebt oder die Größe ändert, wenn sich die Dokumentansicht ändert. Die folgende Abbildung zeigt z.B. eine Anmerkung, die der Benutzer für einen Textausschnitt erstellt hat. Wenn sich die Dokumentansicht ändert (durch Bildlauf, Größenänderung, Skalierung usw.), wird die hervorgehobene Anmerkung mit den ausgewählten Daten verschoben.  
  
 ![Anmerkungsdaten-Verankerung](../../../../docs/framework/wpf/advanced/media/caf-dataanchoring.png "CAF_DataAnchoring")  
  
<a name="matching_annotations_with_annotated_objects"></a>   
## <a name="matching-annotations-with-annotated-objects"></a>Abgleichen von Anmerkung mit Objekten mit Anmerkungen  
 Sie können Anmerkungen den entsprechenden kommentierten Objekten zuordnen. Betrachten Sie beispielsweise eine einfache Dokumentleseranwendung, die über einen Kommentarbereich verfügt. Der Kommentarbereich ist möglicherweise ein Listenfeld, das den Text aus einer Liste von Anmerkungen anzeigt, die mit einem Dokument verankert sind. Wenn der Benutzer ein Element im Listenfeld auswählt, zeigt die Anwendung den Abschnitt im Dokument, mit dem das entsprechende Anmerkungsobjekt verankert ist.  
  
 Im folgenden Beispiel wird veranschaulicht, wie der Ereignishandler eines solchen Listenfelds, das als Kommentarbereich dient, implementiert wird.  
  
 [!code-csharp[FlowDocumentAnnotatedViewer#Handler](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FlowDocumentAnnotatedViewer/CSharp/Window1.xaml.cs#handler)]
 [!code-vb[FlowDocumentAnnotatedViewer#Handler](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/FlowDocumentAnnotatedViewer/visualbasic/window1.xaml.vb#handler)]  
  
 Ein weiteres Beispielszenario umfasst Anwendungen, die den Austausch von Anmerkungen und Kurznotizen zwischen Lesern von Dokument per e-Mail ermöglichen. Diese Funktion ermöglicht diesen Programmen, den Leser zu der Seite zu navigieren, die die Anmerkung enthält, die gerade ausgetauscht wird.  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Windows.Controls.Primitives.DocumentViewerBase>  
 <xref:System.Windows.Controls.DocumentViewer>  
 <xref:System.Windows.Controls.FlowDocumentPageViewer>  
 <xref:System.Windows.Controls.FlowDocumentScrollViewer>  
 <xref:System.Windows.Controls.FlowDocumentReader>  
 <xref:System.Windows.Annotations.IAnchorInfo>  
 [Annotations-Schema](../../../../docs/framework/wpf/advanced/annotations-schema.md)  
 [Übersicht über ContextMenu](../../../../docs/framework/wpf/controls/contextmenu-overview.md)  
 [Befehlsübersicht](../../../../docs/framework/wpf/advanced/commanding-overview.md)  
 [Übersicht über Flussdokumente](../../../../docs/framework/wpf/advanced/flow-document-overview.md)  
 [How to: Add a Command to a MenuItem (Vorgehensweise: Hinzufügen eines Befehls zu einem MenuItem)](https://msdn.microsoft.com/library/013d68a0-5373-4a68-bd91-5de574307370)
