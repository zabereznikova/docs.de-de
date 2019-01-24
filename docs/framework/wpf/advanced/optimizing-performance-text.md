---
title: 'Optimieren der Leistung: Text'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- rendering text [WPF]
- hyperlinks [WPF]
- formatted text [WPF]
- text [WPF], performance
- glyphs [WPF]
ms.assetid: 66b1b9a7-8618-48db-b616-c57ea4327b98
ms.openlocfilehash: e233503ec6a31b28134afbdaef229901b11fbaa0
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54741690"
---
# <a name="optimizing-performance-text"></a>Optimieren der Leistung: Text
[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] bietet Unterstützung für die Präsentation von Textinhalt durch Verwendung von umfangreichen [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)]-Steuerelementen. Im Allgemeinen können Sie das Rendern von Text in drei Ebenen unterteilen:  
  
1.  Mithilfe der <xref:System.Windows.Documents.Glyphs> und <xref:System.Windows.Media.GlyphRun> -Objekte direkt.  
  
2.  Mithilfe der <xref:System.Windows.Media.FormattedText> Objekt.  
  
3.  Verwendung von übergeordneten Steuerelementen wie z. B. die <xref:System.Windows.Controls.TextBlock> und <xref:System.Windows.Documents.FlowDocument> Objekte.  
  
 In diesem Thema erhalten Sie Empfehlungen bezüglich des Renderns von Text.  
  
  
<a name="Glyph_Level"></a>   
## <a name="rendering-text-at-the-glyph-level"></a>Rendern von Text auf der Symbolebene  
 [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] bietet Unterstützung für erweiterten Text einschließlich Markup auf Symbolebene mit direktem Zugriff auf <xref:System.Windows.Documents.Glyphs> für Kunden, die abfangen und Text nach der Formatierung beibehalten werden soll. Diese Funktionen stellen wichtige Unterstützung für verschiedene Text-Rendering-Voraussetzungen in jedem der folgenden Szenarios bereit.  
  
-   Bildschirmanzeige von Dokumenten mit festem Format  
  
-   Druckszenarios  
  
    -   [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] als Druckersprache für Geräte  
  
    -   [!INCLUDE[TLA#tla_mxdw](../../../../includes/tlasharptla-mxdw-md.md)].  
  
    -   Vorherige Druckertreiber, Ausgabe von [!INCLUDE[TLA#tla_win32](../../../../includes/tlasharptla-win32-md.md)]-Anwendungen an das feste Format  
  
    -   Druckerspooler-Format  
  
-   Darstellung von Dokumenten mit festem Format, einschließlich Clients für vorherige Versionen von [!INCLUDE[TLA#tla_mswin](../../../../includes/tlasharptla-mswin-md.md)] und anderen Computergeräten  
  
> [!NOTE]
>  <xref:System.Windows.Documents.Glyphs> und <xref:System.Windows.Media.GlyphRun> sind für festem Format Dokumentpräsentation und Druckszenarios konzipiert. [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] Stellt etliche Elemente für allgemeine Layout- und [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] Szenarien, z. B. <xref:System.Windows.Controls.Label> und <xref:System.Windows.Controls.TextBlock>. Weitere Informationen zu Layout- und [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]-Szenarios finden Sie unter [Typografie in WPF](../../../../docs/framework/wpf/advanced/typography-in-wpf.md).  
  
 Die folgenden Beispiele zeigen, wie Eigenschaften für definiert eine <xref:System.Windows.Documents.Glyphs> im-Objekt [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]. Die <xref:System.Windows.Documents.Glyphs> Objekt darstellt, die Ausgabe des einen <xref:System.Windows.Media.GlyphRun> in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]. In den Beispielen wird davon ausgegangen, dass die Schriftarten Arial, Courier New und Times New Roman im Ordner **C:\WINDOWS\Fonts** auf dem lokalen Computer installiert sind.  
  
 [!code-xaml[GlyphsOvwSample1#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GlyphsOvwSample1/CS/default.xaml#1)]  
  
### <a name="using-drawglyphrun"></a>Verwenden von DrawGlyphRun  
 Wenn Sie benutzerdefiniertes Steuerelement verfügen und Symbole rendern, verwenden Sie möchten die <xref:System.Windows.Media.DrawingContext.DrawGlyphRun%2A> Methode.  
  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] bietet außerdem Dienste niedriger Ebene für benutzerdefinierte Formatierung durch die Verwendung von Text die <xref:System.Windows.Media.FormattedText> Objekt. Am effizientesten Rendern Sie Text in [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] ist, indem Sie Textinhalt auf das Symbol mit <xref:System.Windows.Documents.Glyphs> und <xref:System.Windows.Media.GlyphRun>. Die Kosten für diese Effizienz ist jedoch der Verlust der benutzerfreundliche rich-Text formatiert, die integrierten Funktionen sind von [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] Steuerelemente, z. B. <xref:System.Windows.Controls.TextBlock> und <xref:System.Windows.Documents.FlowDocument>.  
  
<a name="FormattedText_Object"></a>   
## <a name="formattedtext-object"></a>FormattedText-Objekt  
 Die <xref:System.Windows.Media.FormattedText> Objekt können Sie mehrzeiligen Text zu zeichnen, in dem jedes Zeichen im Text einzeln formatiert werden kann. Weitere Informationen finden Sie unter [Drawing Formatted Text (Zeichnen von formatiertem Text)](../../../../docs/framework/wpf/advanced/drawing-formatted-text.md).  
  
 Um formatierten Text erstellen möchten, rufen die <xref:System.Windows.Media.FormattedText.%23ctor%2A> Konstruktor zur Erstellung einer <xref:System.Windows.Media.FormattedText> Objekt. Nachdem Sie die Anfangszeichenfolge für formatierten Text erstellt haben, können Sie eine Reihe von Formatvorlagen anwenden. Wenn Ihre Anwendung ein eigenes Layout, implementiert die <xref:System.Windows.Media.FormattedText> Objekt ist die bessere Wahl als die Verwendung eines Steuerelements wie z. B. <xref:System.Windows.Controls.TextBlock>. Weitere Informationen zu den <xref:System.Windows.Media.FormattedText> Objekt, finden Sie unter [Drawing Formatted Text](../../../../docs/framework/wpf/advanced/drawing-formatted-text.md) .  
  
 Die <xref:System.Windows.Media.FormattedText> -Objekt stellt Textformatierungsfunktionen bereit. Sie können mehrere Formatvorlagen auf ein oder mehrere Zeichen anwenden. Sie können z. B. Aufrufen sowohl die <xref:System.Windows.Media.FormattedText.SetFontSize%2A> und <xref:System.Windows.Media.FormattedText.SetForegroundBrush%2A> Methoden zum Ändern der Formatierung der ersten fünf Zeichen im Text.  
  
 Das folgende Codebeispiel erstellt eine <xref:System.Windows.Media.FormattedText> Objekt und rendert ihn.  
  
 [!code-csharp[formattedtextsnippets#FormattedTextSnippets1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FormattedTextSnippets/CSharp/Window1.xaml.cs#formattedtextsnippets1)]
 [!code-vb[formattedtextsnippets#FormattedTextSnippets1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/FormattedTextSnippets/visualbasic/window1.xaml.vb#formattedtextsnippets1)]  
  
<a name="FlowDocument_TextBlock_Label"></a>   
## <a name="flowdocument-textblock-and-label-controls"></a>FlowDocument, TextBlock- und Label-Steuerelemente  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] enthält zahlreiche Steuerelemente für das Zeichnen von Text auf dem Bildschirm. Jedes Steuerelement dient einem anderen Szenario und verfügt über eine eigene Liste von Funktionen und Einschränkungen.  
  
### <a name="flowdocument-impacts-performance-more-than-textblock-or-label"></a>FlowDocument wirkt sich mehr auf die Leistung aus als TextBlock oder Label  
 Im Allgemeinen die <xref:System.Windows.Controls.TextBlock> Element sollte verwendet werden, wenn nur eingeschränkte Textelemente-Unterstützung erforderlich ist, z. B. einem kurzen Satz in einem [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)]. <xref:System.Windows.Controls.Label> kann verwendet werden, wenn nur minimale textunterstützung erforderlich ist. Die <xref:System.Windows.Documents.FlowDocument> Element ist ein Container für Inhaltspräsentationen Dokumente, die umfassende Unterstützung, und aus diesem Grund hat größere Auswirkungen auf die Leistung als die Verwendung der <xref:System.Windows.Controls.TextBlock> oder <xref:System.Windows.Controls.Label> Steuerelemente.  
  
 Weitere Informationen zu <xref:System.Windows.Documents.FlowDocument>, finden Sie unter [Übersicht über Flussdokumente](../../../../docs/framework/wpf/advanced/flow-document-overview.md).  
  
### <a name="avoid-using-textblock-in-flowdocument"></a>Vermeiden von TextBlock in FlowDocument  
 Die <xref:System.Windows.Controls.TextBlock> Element stammt aus <xref:System.Windows.UIElement>. Die <xref:System.Windows.Documents.Run> Element stammt aus <xref:System.Windows.Documents.TextElement>, d.h. kostengünstiger zu verwenden als ein <xref:System.Windows.UIElement>-abgeleitetes Objekt. Verwenden Sie nach Möglichkeit <xref:System.Windows.Documents.Run> statt <xref:System.Windows.Controls.TextBlock> zum Anzeigen von Textinhalt in einem <xref:System.Windows.Documents.FlowDocument>.  
  
 Das folgende Markup veranschaulicht zwei Möglichkeiten zum Festlegen von Textinhalt in einem <xref:System.Windows.Documents.FlowDocument>:  
  
 [!code-xaml[Performance#PerformanceSnippet13](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Performance/CSharp/FlowDocument.xaml#performancesnippet13)]  
  
### <a name="avoid-using-run-to-set-text-properties"></a>Vermeiden von Run zum Festlegen von Texteigenschaften  
 Im Allgemeinen ist die Verwendung einer <xref:System.Windows.Documents.Run> innerhalb einer <xref:System.Windows.Controls.TextBlock> ressourcenintensiver als die nicht mit einem expliziten <xref:System.Windows.Documents.Run> überhaupt Objekt. Bei Verwendung einer <xref:System.Windows.Documents.Run> um Texteigenschaften festzulegen, legen Sie diese Eigenschaften direkt auf die <xref:System.Windows.Controls.TextBlock> stattdessen.  
  
 Im folgenden Markupbeispiel wird veranschaulicht, diese beiden Methoden zum Festlegen einer Texteigenschaft, in diesem Fall die <xref:System.Windows.Controls.TextBlock.FontWeight%2A> Eigenschaft:  
  
 [!code-xaml[Performance#PerformanceSnippet12](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Performance/CSharp/Window1.xaml#performancesnippet12)]  
  
 Die folgende Tabelle zeigt die Kosten für die Anzeige von 1000 <xref:System.Windows.Controls.TextBlock> Objekte mit und ohne eine explizite <xref:System.Windows.Documents.Run>.  
  
|**TextBlock-Typ**|**Erstellungszeit (in ms)**|**Renderingzeit (in ms)**|  
|------------------------|------------------------------|----------------------------|  
|Run zum Festlegen von Texteigenschaften|146|540|  
|TextBlock zum Festlegen von Texteigenschaften|43|453|  
  
### <a name="avoid-databinding-to-the-labelcontent-property"></a>Vermeiden von Datenbindung an die Label.Content-Eigenschaft  
 Stellen Sie sich ein Szenario, in denen, eine <xref:System.Windows.Controls.Label> -Objekt, das häufig von aktualisiert wird eine <xref:System.String> Quelle. Wenn die Datenbindung der <xref:System.Windows.Controls.Label> des Elements <xref:System.Windows.Controls.ContentControl.Content%2A> Eigenschaft, um die <xref:System.String> Quellobjekt, treten unter Umständen eine schlechte Leistung. Jedes Mal, wenn die Quelle <xref:System.String> wird aktualisiert, die alte <xref:System.String> Objekts wird verworfen und ein neues <xref:System.String> wird neu erstellt – da ein <xref:System.String> -Objekt unveränderlich ist, kann nicht geändert werden. Dies wiederum führt dazu, dass die <xref:System.Windows.Controls.ContentPresenter> von der <xref:System.Windows.Controls.Label> Objekt, das den alten Inhalt verwirft und den neuen Inhalt der neuen anzuzeigenden generiert <xref:System.String>.  
  
 Die Lösung für dieses Problem ist einfach. Wenn die <xref:System.Windows.Controls.Label> ist nicht festgelegt, um eine benutzerdefinierte <xref:System.Windows.Controls.ContentControl.ContentTemplate%2A> -Wert, ersetzen Sie die <xref:System.Windows.Controls.Label> mit einer <xref:System.Windows.Controls.TextBlock> und Datenbindung der <xref:System.Windows.Controls.TextBlock.Text%2A> Eigenschaft, um die Quellzeichenfolge.  
  
|**Datengebundene Eigenschaft**|**Aktualisierungszeit (in ms)**|  
|-----------------------------|----------------------------|  
|Label.Content|835|  
|TextBlock.Text|242|  
  
<a name="Hyperlink"></a>   
## <a name="hyperlink"></a>Link  
 Die <xref:System.Windows.Documents.Hyperlink> Objekt ist ein fortlaufendes Inhaltselement, das Ihnen das Hosten von links im fortlaufenden Inhalt ermöglicht.  
  
### <a name="combine-hyperlinks-in-one-textblock-object"></a>Kombinieren von Links in einem TextBlock-Objekt  
 Sie können die Verwendung mehrerer optimieren <xref:System.Windows.Documents.Hyperlink> Elemente durch diese innerhalb desselben gruppieren <xref:System.Windows.Controls.TextBlock>. Dadurch wird die Anzahl der Objekte minimiert, die Sie in Ihrer Anwendung erstellen. Zum Beispiel kann es vorkommen, dass Sie mehrere Links wie folgt anzeigen möchten:  
  
 MSN Home &#124; My MSN  
  
 Im folgenden Markupbeispiel wird veranschaulicht, mehrere <xref:System.Windows.Controls.TextBlock> Elemente, die zum Anzeigen der Links verwendet:  
  
 [!code-xaml[Performance#PerformanceSnippet9](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Performance/CSharp/Hyperlink.xaml#performancesnippet9)]  
  
 Im folgenden Markupbeispiel wird gezeigt, eine effizientere Möglichkeit zum Anzeigen der Links, diesmal mit einer einzigen <xref:System.Windows.Controls.TextBlock>:  
  
 [!code-xaml[Performance#PerformanceSnippet10](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Performance/CSharp/Hyperlink.xaml#performancesnippet10)]  
  
### <a name="showing-underlines-on-hyperlinks-only-on-mouseenter-events"></a>Anzeigen der Unterstreichungen von Links nur bei MouseEnter-Ereignissen  
 Ein <xref:System.Windows.TextDecoration> Objekt ist eine visuelle Verzierung, die Sie Text hinzufügen können; sie kann jedoch ressourcenintensiv, instanziieren. Wenn Sie umfassenden Gebrauch von machen <xref:System.Windows.Documents.Hyperlink> Elemente könnten Sie eine Unterstreichung nur, wenn ein Ereignis auslösen, z. B. die <xref:System.Windows.ContentElement.MouseEnter> Ereignis. Weitere Informationen finden Sie unter [Specify Whether a Hyperlink is Underlined (Angeben, ob ein Link unterstrichen wird)](../../../../docs/framework/wpf/advanced/how-to-specify-whether-a-hyperlink-is-underlined.md).  
  
 ![Links mit TextDecorations](../../../../docs/framework/wpf/advanced/media/textdecoration03.png "TextDecoration03")  
Link-Anzeige bei MouseEnter-Ereignis  
  
 Das folgende Markup-Beispiel zeigt eine <xref:System.Windows.Documents.Hyperlink> mit und ohne Unterstreichung definiert:  
  
 [!code-xaml[Performance#PerformanceSnippet11](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Performance/CSharp/Hyperlink.xaml#performancesnippet11)]  
  
 Die folgende Tabelle zeigt die Kosten der Leistung zum Anzeigen von 1000 <xref:System.Windows.Documents.Hyperlink> -Elementen mit und ohne Unterstreichung.  
  
|**Link**|**Erstellungszeit (in ms)**|**Renderingzeit (in ms)**|  
|-------------------|------------------------------|----------------------------|  
|Mit Unterstreichung|289|1130|  
|Ohne Unterstreichung|299|776|  
  
<a name="Text_Formatting_Features"></a>   
## <a name="text-formatting-features"></a>Textformatierungsfunktionen  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] bietet umfangreiche Formatierungsdienste wie automatische Silbentrennung. Diese Dienste können die Leistung der Anwendung beeinträchtigen und sollten nur bei Bedarf verwendet werden.  
  
### <a name="avoid-unnecessary-use-of-hyphenation"></a>Vermeiden von unnötiger Silbentrennung  
 Automatische Silbentrennung findet Trennpunkte für Textzeilen und ermöglicht zusätzliche Trennpositionen für Zeilen in <xref:System.Windows.Controls.TextBlock> und <xref:System.Windows.Documents.FlowDocument> Objekte. In der Standardeinstellung ist die automatische Silbentrennung in diesen Objekten deaktiviert. Sie können diese Funktion aktivieren, indem Sie die IsHyphenationEnabled-Eigenschaft des Objekts auf `true` festlegen. Allerdings führt die Aktivierung dieser Funktion dazu, dass [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] [!INCLUDE[TLA#tla_com](../../../../includes/tlasharptla-com-md.md)]-Interoperabilität initiiert, was die Leistung der Anwendung beeinträchtigen kann. Es wird empfohlen, die automatische Silbentrennung nur bei Bedarf zu verwenden.  
  
### <a name="use-figures-carefully"></a>Vorsichtiges Verwenden von Figure-Elementen  
 Ein <xref:System.Windows.Documents.Figure> Element stellt einen Teil eines fortlaufenden Inhalt, der in einer Inhaltsseite absolut positioniert werden kann. In einigen Fällen eine <xref:System.Windows.Documents.Figure> kann dazu führen, dass eine ganze Seite automatisch neu formatiert wird, wenn seine Position mit Inhalt kollidiert, der bereits gelayoutet wurde. Sie können auch die Möglichkeit unnötiger neuformatierung von entweder Gruppierung Minimieren <xref:System.Windows.Documents.Figure> Elemente nebeneinander, oder deklarieren sie im oberen Bereich des Inhalts in einem Szenario mit Größe fixierten Seite.  
  
### <a name="optimal-paragraph"></a>Optimale Absatzformatierung  
 Die optimale absatzformatierung, der die <xref:System.Windows.Documents.FlowDocument> Objekt ordnet Absätze so, dass Leerzeichen möglichst gleichmäßig verteilt wird. In der Standardeinstellung ist die optimale Absatzformatierung deaktiviert. Sie können dieses Feature aktivieren, indem des Objekts des <xref:System.Windows.Documents.FlowDocument.IsOptimalParagraphEnabled%2A> Eigenschaft `true`. Allerdings beeinträchtigt die Aktivierung dieser Funktion die Leistung der Anwendung. Es wird empfohlen, die optimale Absatzformatierung nur bei Bedarf zu verwenden.  
  
## <a name="see-also"></a>Siehe auch
- [Optimieren der WPF-Anwendungsleistung](../../../../docs/framework/wpf/advanced/optimizing-wpf-application-performance.md)
- [Planen der Anwendungsleistung](../../../../docs/framework/wpf/advanced/planning-for-application-performance.md)
- [Vorteile der Hardware nutzen](../../../../docs/framework/wpf/advanced/optimizing-performance-taking-advantage-of-hardware.md)
- [Layout und Entwurf](../../../../docs/framework/wpf/advanced/optimizing-performance-layout-and-design.md)
- [2D-Grafiken und Bildverarbeitung](../../../../docs/framework/wpf/advanced/optimizing-performance-2d-graphics-and-imaging.md)
- [Objektverhalten](../../../../docs/framework/wpf/advanced/optimizing-performance-object-behavior.md)
- [Anwendungsressourcen](../../../../docs/framework/wpf/advanced/optimizing-performance-application-resources.md)
- [Datenbindung](../../../../docs/framework/wpf/advanced/optimizing-performance-data-binding.md)
- [Weitere Leistungsempfehlungen](../../../../docs/framework/wpf/advanced/optimizing-performance-other-recommendations.md)
