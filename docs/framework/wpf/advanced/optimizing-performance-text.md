---
title: "Optimieren der Leistung: Text | Microsoft Docs"
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
  - "Rendern von Text"
  - "Links"
  - "Formatierter Text [WPF]"
  - "Text, Leistung"
  - "Symbole"
ms.assetid: 66b1b9a7-8618-48db-b616-c57ea4327b98
caps.latest.revision: 10
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 9
---
# Optimieren der Leistung: Text
[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]bietet Unterstützung für die Präsentation des Textinhalts durch die Verwendung von umfangreichen [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] Steuerelemente. Im Allgemeinen können Sie das Rendern von Text in drei Ebenen unterteilen:  
  
1.  Mithilfe der <xref:System.Windows.Documents.Glyphs> und <xref:System.Windows.Media.GlyphRun> -Objekte direkt verwenden.  
  
2.  Mithilfe der <xref:System.Windows.Media.FormattedText> Objekt.  
  
3.  Verwenden von übergeordneten Steuerelementen, z. B. die <xref:System.Windows.Controls.TextBlock> und <xref:System.Windows.Documents.FlowDocument> Objekte.  
  
 Dieses Thema enthält Text leistungsempfehlungen gerendert.  
  
   
  
<a name="Glyph_Level"></a>   
## <a name="rendering-text-at-the-glyph-level"></a>Rendern von Text auf der Symbolebene  
 [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]bietet Unterstützung für erweiterte Text einschließlich Glyph-Level-Markup mit direktem Zugriff auf <xref:System.Windows.Documents.Glyphs> für Kunden abfangen und Beibehalten von Text nach dem formatieren möchten. Diese Funktionen unterstützen für den anderen Text Rendern Anforderungen in jeder der folgenden Szenarien.  
  
-   Anzeige von Dokumenten mit festem Format.  
  
-   Drucken Sie Szenarien.  
  
    -   [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]als Gerät Druckersprache.  
  
    -   [!INCLUDE[TLA#tla_mxdw](../../../../includes/tlasharptla-mxdw-md.md)].  
  
    -   Zuvor installierte Druckertreiber, die Ausgabe von [!INCLUDE[TLA#tla_win32](../../../../includes/tlasharptla-win32-md.md)] zu festen Format.  
  
    -   Druckserver-Format.  
  
-   Dokument-Format Darstellung, einschließlich der Clients für frühere Versionen von [!INCLUDE[TLA#tla_mswin](../../../../includes/tlasharptla-mswin-md.md)] und andere Geräte.  
  
> [!NOTE]
>  <xref:System.Windows.Documents.Glyphs> und <xref:System.Windows.Media.GlyphRun> sind für die Darstellung von Dokumenten mit festem Format und Druckszenarios konzipiert. [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]Stellt etliche Elemente für allgemeine Layout- und [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] Szenarien, z. B. <xref:System.Windows.Controls.Label> und <xref:System.Windows.Controls.TextBlock>. Weitere Informationen zum Layout und [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] finden Sie Beispielszenarien, die [Typografie in WPF](../../../../docs/framework/wpf/advanced/typography-in-wpf.md).  
  
 Die folgenden Beispiele zeigen, wie Eigenschaften für definiert eine <xref:System.Windows.Documents.Glyphs> -Objekt in [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]. Die <xref:System.Windows.Documents.Glyphs> Objekt darstellt, die Ausgabe des einen <xref:System.Windows.Media.GlyphRun> in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]. In den Beispielen wird davon ausgegangen, dass die Schriftarten Arial, Courier New und Times New Roman in installiert sind die **C:\WINDOWS\Fonts** Ordner auf dem lokalen Computer.  
  
 [!code-xml[GlyphsOvwSample1#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GlyphsOvwSample1/CS/default.xaml#1)]  
  
### <a name="using-drawglyphrun"></a>Verwenden von DrawGlyphRun  
 Wenn Sie benutzerdefiniertes Steuerelement verfügen und Symbole rendern, verwendet werden soll die <xref:System.Windows.Media.DrawingContext.DrawGlyphRun%2A> Methode.  
  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]bietet außerdem Low-Level-Dienste für benutzerdefinierte Formatierung durch die Verwendung von Text die <xref:System.Windows.Media.FormattedText> Objekt. Die effizienteste Rendern von Text in [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] ist, indem Sie den Textinhalt an der Glyphe Ebene mit generieren <xref:System.Windows.Documents.Glyphs> und <xref:System.Windows.Media.GlyphRun>. Die Kosten für diese Effizienz ist jedoch den Verlust von benutzerfreundlichen rich Text-Formatierung, die integrierten Funktionen sind von [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] Steuerelemente, z. B. <xref:System.Windows.Controls.TextBlock> und <xref:System.Windows.Documents.FlowDocument>.  
  
<a name="FormattedText_Object"></a>   
## <a name="formattedtext-object"></a>FormattedText-Objekt  
 Die <xref:System.Windows.Media.FormattedText> Objekt können Sie mehrzeilige Zeichnen von Text, in dem jedes Zeichen einzeln formatiert werden kann. Weitere Informationen finden Sie unter [Drawing Formatted Text](../../../../docs/framework/wpf/advanced/drawing-formatted-text.md).  
  
 Um formatierten Text zu erstellen, rufen Sie die <xref:System.Windows.Media.FormattedText.%23ctor%2A> -Konstruktors zum Erstellen einer <xref:System.Windows.Media.FormattedText> Objekt. Nachdem Sie die erste formatierte Zeichenfolge erstellt haben, können Sie einen Bereich von Formatvorlagen anwenden. Wenn Ihre Anwendung ein eigenen Layout implementiert die <xref:System.Windows.Media.FormattedText> Objekt ist besser als mit einem Steuerelement, z. B. <xref:System.Windows.Controls.TextBlock>. Weitere Informationen zu den <xref:System.Windows.Media.FormattedText> Objekt, finden Sie unter [Drawing Formatted Text](../../../../docs/framework/wpf/advanced/drawing-formatted-text.md) .  
  
 Die <xref:System.Windows.Media.FormattedText> -Objekt stellt Textformatierungsfunktionen bereit. Sie können mehrere Formatvorlagen auf ein oder mehrere Zeichen anwenden. Sie könnten z. B. Aufrufen von der <xref:System.Windows.Media.FormattedText.SetFontSize%2A> und <xref:System.Windows.Media.FormattedText.SetForegroundBrush%2A> Methoden, um die Formatierung der ersten fünf Zeichen im Text zu ändern.  
  
 Der folgende Code erstellt ein <xref:System.Windows.Media.FormattedText> -Objekt und rendert ihn.  
  
 [!code-csharp[formattedtextsnippets#FormattedTextSnippets1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FormattedTextSnippets/CSharp/Window1.xaml.cs#formattedtextsnippets1)]
 [!code-vb[formattedtextsnippets#FormattedTextSnippets1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/FormattedTextSnippets/visualbasic/window1.xaml.vb#formattedtextsnippets1)]  
  
<a name="FlowDocument_TextBlock_Label"></a>   
## <a name="flowdocument-textblock-and-label-controls"></a>FlowDocument, TextBlock- und Label-Steuerelemente  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]enthält mehrere Steuerelemente, die zum Zeichnen von Text auf dem Bildschirm. Jedes Steuerelement zu einem anderen Szenario richtet und verfügt über eine eigene Liste von Funktionen und Einschränkungen.  
  
### <a name="flowdocument-impacts-performance-more-than-textblock-or-label"></a>FlowDocument wirkt sich mehr als TextBlock oder Label auf die Leistung  
 Im Allgemeinen die <xref:System.Windows.Controls.TextBlock> Element sollte verwendet werden, wenn beschränkt Text-Unterstützung erforderlich ist, z. B. einen kurzen Satz in einem [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)]. <xref:System.Windows.Controls.Label> kann verwendet werden, wenn wenig Text-Unterstützung erforderlich ist. Die <xref:System.Windows.Documents.FlowDocument> Element ist ein Container für Flussdokumente Inhaltspräsentationen, die umfangreiche unterstützen, und daher wirkt sich mehr Leistung als die Verwendung der <xref:System.Windows.Controls.TextBlock> oder <xref:System.Windows.Controls.Label> Steuerelemente.  
  
 Weitere Informationen zu <xref:System.Windows.Documents.FlowDocument>, finden Sie unter [Flow Document Overview](../../../../docs/framework/wpf/advanced/flow-document-overview.md).  
  
### <a name="avoid-using-textblock-in-flowdocument"></a>Vermeiden Sie die Verwendung von TextBlock in FlowDocument  
 Die <xref:System.Windows.Controls.TextBlock> Element abgeleitet ist <xref:System.Windows.UIElement>. Die <xref:System.Windows.Documents.Run> Element abgeleitet ist <xref:System.Windows.Documents.TextElement>, also weniger Aufwand als verwendet eine <xref:System.Windows.UIElement>-abgeleitetes Objekt. Verwenden Sie nach Möglichkeit <xref:System.Windows.Documents.Run> statt <xref:System.Windows.Controls.TextBlock> für die Anzeige von Textinhalt in einem <xref:System.Windows.Documents.FlowDocument>.  
  
 Das folgende Markup veranschaulicht zwei Möglichkeiten zum Festlegen von Textinhalt in einem <xref:System.Windows.Documents.FlowDocument>:  
  
 [!code-xml[Performance#PerformanceSnippet13](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Performance/CSharp/FlowDocument.xaml#performancesnippet13)]  
  
### <a name="avoid-using-run-to-set-text-properties"></a>Vermeiden Sie die Verwendung von ausführen, Text-Eigenschaften  
 Im Allgemeinen ist die Verwendung eine <xref:System.Windows.Documents.Run> innerhalb einer <xref:System.Windows.Controls.TextBlock> ressourcenintensiver als die nicht mit einem expliziten <xref:System.Windows.Documents.Run> Objekt überhaupt. Bei Verwendung einer <xref:System.Windows.Documents.Run> um Texteigenschaften festzulegen, legen Sie diese Eigenschaften direkt auf die <xref:System.Windows.Controls.TextBlock> stattdessen.  
  
 Das folgende Markup veranschaulicht diese beiden Methoden zum Festlegen einer Texteigenschaft in diesem Fall die <xref:System.Windows.Controls.TextBlock.FontWeight%2A> Eigenschaft:  
  
 [!code-xml[Performance#PerformanceSnippet12](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Performance/CSharp/Window1.xaml#performancesnippet12)]  
  
 Die folgende Tabelle zeigt die für das Anzeigen von 1000 <xref:System.Windows.Controls.TextBlock> Objekte mit und ohne explizite <xref:System.Windows.Documents.Run>.  
  
|**TextBlock-Typ**|**Zeitpunkt der Erstellung (ms)**|**Rendering-Zeit (ms)**|  
|------------------------|------------------------------|----------------------------|  
|Festlegen von Texteigenschaften ausführen|146|540|  
|Festlegen von Texteigenschaften TextBlock|43|453|  
  
### <a name="avoid-databinding-to-the-labelcontent-property"></a>Vermeiden Sie Databinding der Label.Content-Eigenschaft  
 Stellen Sie ein Szenario, in dem Sie sich vor einem <xref:System.Windows.Controls.Label> -Objekt, das häufig von aktualisiert wird ein <xref:System.String> Quelle. Beim Binden von Daten der <xref:System.Windows.Controls.Label> des Elements <xref:System.Windows.Controls.ContentControl.Content%2A> -Eigenschaft auf die <xref:System.String> Quelle-Objekt Leistungseinbußen auftreten. Jedes Mal, wenn die Quelle <xref:System.String> aktualisiert wird, den alten <xref:System.String> Objekts wird verworfen und ein neues <xref:System.String> wird neu erstellt – da eine <xref:System.String> -Objekt unveränderlich ist, kann nicht geändert werden. Dies wiederum führt die <xref:System.Windows.Controls.ContentPresenter> von der <xref:System.Windows.Controls.Label> Objekt, das den alten Inhalt verwirft und den neuen Inhalt anzeigen der neuen generiert <xref:System.String>.  
  
 Die Lösung für dieses Problem ist einfach. Wenn der <xref:System.Windows.Controls.Label> ist nicht festgelegt, um eine benutzerdefinierte <xref:System.Windows.Controls.ContentControl.ContentTemplate%2A> -Wert, ersetzen Sie die <xref:System.Windows.Controls.Label> mit einer <xref:System.Windows.Controls.TextBlock> und Binden von Daten seine <xref:System.Windows.Controls.TextBlock.Text%2A> Eigenschaft, um die Quellzeichenfolge.  
  
|**Datengebundene Eigenschaft**|**Update-Zeit (ms)**|  
|-----------------------------|----------------------------|  
|Label.Content|835|  
|TextBlock.Text|242|  
  
<a name="Hyperlink"></a>   
## <a name="hyperlink"></a>Link  
 Die <xref:System.Windows.Documents.Hyperlink> Objekt ist ein Inline-Level-Inhaltselement, das Ihnen das Hosten von links im fortlaufenden Inhalt ermöglicht.  
  
### <a name="combine-hyperlinks-in-one-textblock-object"></a>Kombinieren von links in einem TextBlock-Objekt  
 Sie können die Verwendung mehrerer optimieren <xref:System.Windows.Documents.Hyperlink> Elemente innerhalb derselben gruppieren <xref:System.Windows.Controls.TextBlock>. Dadurch wird um die Anzahl der Objekte zu minimieren, die Sie in Ihrer Anwendung zu erstellen. Zum Beispiel: Sie möchten mehrere Links wie die folgende angezeigt:  
  
 MSN-Startseite | My MSN  
  
 Das folgende Markupbeispiel zeigt mehrere <xref:System.Windows.Controls.TextBlock> Elemente, die zur Anzeige der Links verwendet:  
  
 [!code-xml[Performance#PerformanceSnippet9](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Performance/CSharp/Hyperlink.xaml#performancesnippet9)]  
  
 Das folgende Markupbeispiel zeigt einen effizienteren Anzeige der Links, dieses Mal mit einer einzelnen <xref:System.Windows.Controls.TextBlock>:  
  
 [!code-xml[Performance#PerformanceSnippet10](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Performance/CSharp/Hyperlink.xaml#performancesnippet10)]  
  
### <a name="showing-underlines-on-hyperlinks-only-on-mouseenter-events"></a>Anzeigen von unterstrichenen Links nur für MouseEnter-Ereignisse  
 Ein <xref:System.Windows.TextDecoration> Objekt ist eine visuelle Verzierung, die Text hinzugefügt werden können, es kann jedoch ressourcenintensiv instanziieren. Wenn Sie einsetzen <xref:System.Windows.Documents.Hyperlink> Elemente, sollten Sie einen Unterstrich nur, wenn ein Ereignis auslösen, z. B. Anzeigen der <xref:System.Windows.ContentElement.MouseEnter> Ereignis. Weitere Informationen finden Sie unter [angeben, ob ein Hyperlink unterstrichen wird](../../../../docs/framework/wpf/advanced/how-to-specify-whether-a-hyperlink-is-underlined.md).  
  
 ![Links mit TextDecorations](../../../../docs/framework/wpf/advanced/media/textdecoration03.png "TextDecoration03")  
Link-Anzeige bei MouseEnter-Ereignis  
  
 Das folgende Markup-Beispiel zeigt einen <xref:System.Windows.Documents.Hyperlink> mit und ohne Unterstreichung definiert:  
  
 [!code-xml[Performance#PerformanceSnippet11](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Performance/CSharp/Hyperlink.xaml#performancesnippet11)]  
  
 Die folgende Tabelle zeigt die Leistungseinbußen für das Anzeigen von 1000 <xref:System.Windows.Documents.Hyperlink> Elemente mit und ohne Unterstreichung.  
  
|**Hyperlink**|**Zeitpunkt der Erstellung (ms)**|**Rendering-Zeit (ms)**|  
|-------------------|------------------------------|----------------------------|  
|Mit Unterstreichung|289|1130|  
|Ohne Unterstreichung|299|776|  
  
<a name="Text_Formatting_Features"></a>   
## <a name="text-formatting-features"></a>Formatieren von Text-Features  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]bietet Dienste, z. B. automatische Silbentrennungen Formatierung rich-Text. Diese Dienste können die Leistung der Anwendung auswirken und sollte nur bei Bedarf verwendet werden.  
  
### <a name="avoid-unnecessary-use-of-hyphenation"></a>Vermeiden Sie unnötigen Verwendung der Silbentrennung  
 Automatische Silbentrennung Textzeilen findet und ermöglicht zusätzliche Trennpositionen in <xref:System.Windows.Controls.TextBlock> und <xref:System.Windows.Documents.FlowDocument> Objekte. Standardmäßig ist die automatische Silbentrennung in diesen Objekten deaktiviert. Sie können dieses Feature aktivieren, indem Sie die IsHyphenationEnabled-Eigenschaft des Objekts auf `true`. Allerdings wird die Aktivierung dieser Funktion [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] initiieren [!INCLUDE[TLA#tla_com](../../../../includes/tlasharptla-com-md.md)] Interoperabilität, die Leistung der Anwendung auswirken kann. Es wird empfohlen, keine automatische Silbentrennung verwenden, es sei denn, Sie benötigen.  
  
### <a name="use-figures-carefully"></a>Verwenden Sie Zahlen mit Vorsicht  
 Ein <xref:System.Windows.Documents.Figure> -Element stellt einen Teil eines fortlaufenden Inhalts, der in einer Inhaltsseite absolut positioniert werden kann. In einigen Fällen eine <xref:System.Windows.Documents.Figure> kann dazu führen, dass eine ganze Seite automatisch neu formatiert, wenn seine Position mit Inhalt kollidiert, der bereits Layout wurde. Können Sie die Möglichkeit, dass unnötige Neuformatieren von entweder Gruppierung Minimieren <xref:System.Windows.Documents.Figure> Elemente nebeneinander, oder sie am Anfang der Inhalt in einem Szenario mit Seite fester Größe zu deklarieren.  
  
### <a name="optimal-paragraph"></a>Optimale  
 Mit dem Feature für die optimale der <xref:System.Windows.Documents.FlowDocument> Objekt auf Absätze angeordnet, sodass Leerräume möglichst gleichmäßig verteilt werden. Standardmäßig ist die optimale Funktion deaktiviert. Sie können dieses Feature aktivieren, indem des Objekts <xref:System.Windows.Documents.FlowDocument.IsOptimalParagraphEnabled%2A> -Eigenschaft `true`. Allerdings wirkt sich auf die Aktivierung dieser Funktion Leistung der Anwendung. Es wird empfohlen, dass Sie die optimale Funktion nicht verwenden, es sei denn, Sie benötigen.  
  
## <a name="see-also"></a>Siehe auch  
 [Optimieren der Leistung der WPF-Anwendung](../../../../docs/framework/wpf/advanced/optimizing-wpf-application-performance.md)   
 [Planen der Leistung der Anwendung](../../../../docs/framework/wpf/advanced/planning-for-application-performance.md)   
 [Vorteile der Hardware](../../../../docs/framework/wpf/advanced/optimizing-performance-taking-advantage-of-hardware.md)   
 [Layout und Entwurf](../../../../docs/framework/wpf/advanced/optimizing-performance-layout-and-design.md)   
 [2D-Grafiken und Bildverarbeitung](../../../../docs/framework/wpf/advanced/optimizing-performance-2d-graphics-and-imaging.md)   
 [Objektverhalten](../../../../docs/framework/wpf/advanced/optimizing-performance-object-behavior.md)   
 [Anwendungsressourcen](../../../../docs/framework/wpf/advanced/optimizing-performance-application-resources.md)   
 [Datenbindung](../../../../docs/framework/wpf/advanced/optimizing-performance-data-binding.md)   
 [Weitere Leistungsempfehlungen](../../../../docs/framework/wpf/advanced/optimizing-performance-other-recommendations.md)