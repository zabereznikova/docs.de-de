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
ms.openlocfilehash: 3e729458538353499f27f95ea2ca37fea1335238
ms.sourcegitcommit: 9a97c76e141333394676bc5d264c6624b6f45bcf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/08/2020
ms.locfileid: "75740344"
---
# <a name="optimizing-performance-text"></a>Optimieren der Leistung: Text

[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] bietet Unterstützung für die Präsentation von Textinhalt durch Verwendung von umfangreichen [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)]-Steuerelementen. Im Allgemeinen können Sie das Rendern von Text in drei Ebenen unterteilen:

1. Direktes verwenden der <xref:System.Windows.Documents.Glyphs>-und <xref:System.Windows.Media.GlyphRun>-Objekte.

2. Verwenden des <xref:System.Windows.Media.FormattedText> Objekts.

3. Verwenden von Steuerelementen auf hoher Ebene, z. b. das <xref:System.Windows.Controls.TextBlock>-und <xref:System.Windows.Documents.FlowDocument>-Objekt.

In diesem Thema erhalten Sie Empfehlungen bezüglich des Renderns von Text.

<a name="Glyph_Level"></a>

## <a name="rendering-text-at-the-glyph-level"></a>Rendern von Text auf der Symbolebene

[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] bietet erweiterte Textunterstützung einschließlich Markup auf Symbolebene mit direktem Zugriff auf <xref:System.Windows.Documents.Glyphs> für Kunden, die Text nach der Formatierung abfangen und beibehalten möchten. Diese Funktionen stellen wichtige Unterstützung für verschiedene Text-Rendering-Voraussetzungen in jedem der folgenden Szenarios bereit.

- Bildschirmanzeige von Dokumenten mit festem Format

- Druckszenarios

  - [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] als Druckersprache für Geräte

  - Microsoft XPS-Dokumentwriter.

  - Vorherige Druckertreiber, Ausgabe von Win32-Anwendungen im Fixed-Format.

  - Druckerspooler-Format

- Dokument Darstellung mit festem Format, einschließlich Clients für frühere Versionen von Windows und anderen Computergeräten.

> [!NOTE]
> <xref:System.Windows.Documents.Glyphs> und <xref:System.Windows.Media.GlyphRun> sind für Dokument Präsentations-und Druck Szenarien mit festem Format konzipiert. [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] bietet mehrere Elemente für allgemeine Layouts und [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] Szenarien wie <xref:System.Windows.Controls.Label> und <xref:System.Windows.Controls.TextBlock>. Weitere Informationen zu Layout- und [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]-Szenarios finden Sie unter [Typografie in WPF](typography-in-wpf.md).

In den folgenden Beispielen wird gezeigt, wie Eigenschaften für ein <xref:System.Windows.Documents.Glyphs> Objekt in [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]definiert werden. Das <xref:System.Windows.Documents.Glyphs>-Objekt stellt die Ausgabe eines <xref:System.Windows.Media.GlyphRun> in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]dar. In den Beispielen wird davon ausgegangen, dass die Schriftarten Arial, Courier New und Times New Roman im Ordner **C:\WINDOWS\Fonts** auf dem lokalen Computer installiert sind.

[!code-xaml[GlyphsOvwSample1#1](~/samples/snippets/csharp/VS_Snippets_Wpf/GlyphsOvwSample1/CS/default.xaml#1)]

### <a name="using-drawglyphrun"></a>Verwenden von DrawGlyphRun

Wenn Sie über ein benutzerdefiniertes Steuerelement verfügen und Symbole darstellen möchten, verwenden Sie die <xref:System.Windows.Media.DrawingContext.DrawGlyphRun%2A>-Methode.

[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] bietet auch Dienste auf niedrigerer Ebene für die benutzerdefinierte Textformatierung durch die Verwendung des <xref:System.Windows.Media.FormattedText> Objekts. Das effizienteste Verfahren zum Rendern von Text in [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] besteht darin, Text Inhalt auf der Symbolebene mithilfe von <xref:System.Windows.Documents.Glyphs> und <xref:System.Windows.Media.GlyphRun>zu erzeugen. Die Kosten für diese Effizienz sind jedoch der Verlust der leicht zu verwendenden Rich-Text-Formatierung, die integrierte Features von [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] Steuerelementen wie <xref:System.Windows.Controls.TextBlock> und <xref:System.Windows.Documents.FlowDocument>sind.

<a name="FormattedText_Object"></a>

## <a name="formattedtext-object"></a>FormattedText-Objekt

Das <xref:System.Windows.Media.FormattedText>-Objekt ermöglicht das Zeichnen von mehrzeiligen Text, in dem jedes Zeichen im Text einzeln formatiert werden kann. Weitere Informationen finden Sie unter [Drawing Formatted Text (Zeichnen von formatiertem Text)](drawing-formatted-text.md).

Um formatierten Text zu erstellen, rufen Sie den <xref:System.Windows.Media.FormattedText.%23ctor%2A>-Konstruktor auf, um ein <xref:System.Windows.Media.FormattedText> Objekt zu erstellen. Nachdem Sie die Anfangszeichenfolge für formatierten Text erstellt haben, können Sie eine Reihe von Formatvorlagen anwenden. Wenn Ihre Anwendung ein eigenes Layout implementieren möchte, ist das <xref:System.Windows.Media.FormattedText> Objekt besser geeignet als die Verwendung eines Steuer Elements, z. b. <xref:System.Windows.Controls.TextBlock>. Weitere Informationen zum <xref:System.Windows.Media.FormattedText>-Objekt finden Sie unter [Zeichnen von formatiertem Text](drawing-formatted-text.md) .

Das <xref:System.Windows.Media.FormattedText>-Objekt bietet Text Formatierungsfunktionen auf niedriger Ebene. Sie können mehrere Formatvorlagen auf ein oder mehrere Zeichen anwenden. Beispielsweise können Sie die Methoden <xref:System.Windows.Media.FormattedText.SetFontSize%2A> und <xref:System.Windows.Media.FormattedText.SetForegroundBrush%2A> aufzurufen, um die Formatierung der ersten fünf Zeichen im Text zu ändern.

Im folgenden Codebeispiel wird ein <xref:System.Windows.Media.FormattedText>-Objekt erstellt und gerendert.

[!code-csharp[formattedtextsnippets#FormattedTextSnippets1](~/samples/snippets/csharp/VS_Snippets_Wpf/FormattedTextSnippets/CSharp/Window1.xaml.cs#formattedtextsnippets1)]
[!code-vb[formattedtextsnippets#FormattedTextSnippets1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/FormattedTextSnippets/visualbasic/window1.xaml.vb#formattedtextsnippets1)]

<a name="FlowDocument_TextBlock_Label"></a>

## <a name="flowdocument-textblock-and-label-controls"></a>FlowDocument, TextBlock- und Label-Steuerelemente

[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] enthält zahlreiche Steuerelemente zum Zeichnen von Text auf dem Bildschirm. Jedes Steuerelement ist einem bestimmten Szenario zugeordnet und besitzt eine eigene Liste von Funktionen und Einschränkungen.

### <a name="flowdocument-impacts-performance-more-than-textblock-or-label"></a>FlowDocument wirkt sich mehr auf die Leistung aus als TextBlock oder Label

Im Allgemeinen sollte das <xref:System.Windows.Controls.TextBlock>-Element verwendet werden, wenn eingeschränkte Textunterstützung erforderlich ist, z. b. ein kurzer Satz in einer [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)]. <xref:System.Windows.Controls.Label> kann verwendet werden, wenn nur minimale Textunterstützung erforderlich ist. Das <xref:System.Windows.Documents.FlowDocument>-Element ist ein Container für neuflowfähige Dokumente, die eine umfangreiche Darstellung von Inhalten unterstützen und somit eine größere Auswirkung auf die Leistung als die Verwendung der <xref:System.Windows.Controls.TextBlock>-oder <xref:System.Windows.Controls.Label>-Steuerelemente haben.

Weitere Informationen zu <xref:System.Windows.Documents.FlowDocument>finden Sie unter [Übersicht über Fluss Dokumente](flow-document-overview.md).

### <a name="avoid-using-textblock-in-flowdocument"></a>Vermeiden von TextBlock in FlowDocument

Das <xref:System.Windows.Controls.TextBlock>-Element wird von <xref:System.Windows.UIElement>abgeleitet. Das <xref:System.Windows.Documents.Run> Element wird von <xref:System.Windows.Documents.TextElement>abgeleitet, das weniger kostspielig als ein von <xref:System.Windows.UIElement>abgeleitetes Objekt ist. Verwenden Sie nach Möglichkeit <xref:System.Windows.Documents.Run> anstelle von <xref:System.Windows.Controls.TextBlock>, um Textinhalte in einem <xref:System.Windows.Documents.FlowDocument>anzuzeigen.

Im folgenden Markup Beispiel werden zwei Möglichkeiten zum Festlegen von Text Inhalt in einem <xref:System.Windows.Documents.FlowDocument>veranschaulicht:

[!code-xaml[Performance#PerformanceSnippet13](~/samples/snippets/csharp/VS_Snippets_Wpf/Performance/CSharp/FlowDocument.xaml#performancesnippet13)]

### <a name="avoid-using-run-to-set-text-properties"></a>Vermeiden von Run zum Festlegen von Texteigenschaften

Im Allgemeinen ist die Verwendung einer <xref:System.Windows.Documents.Run> in einer <xref:System.Windows.Controls.TextBlock> Leistungs intensiver als die Verwendung eines expliziten <xref:System.Windows.Documents.Run> Objekts. Wenn Sie eine <xref:System.Windows.Documents.Run> verwenden, um Texteigenschaften festzulegen, legen Sie diese Eigenschaften stattdessen direkt auf der <xref:System.Windows.Controls.TextBlock> fest.

Im folgenden Markup Beispiel werden diese beiden Methoden zum Festlegen einer Text Eigenschaft veranschaulicht, in diesem Fall die <xref:System.Windows.Controls.TextBlock.FontWeight%2A>-Eigenschaft:

[!code-xaml[Performance#PerformanceSnippet12](~/samples/snippets/csharp/VS_Snippets_Wpf/Performance/CSharp/Window1.xaml#performancesnippet12)]

In der folgenden Tabelle werden die Kosten für die Anzeige von 1000 <xref:System.Windows.Controls.TextBlock>-Objekten mit und ohne explizites <xref:System.Windows.Documents.Run>gezeigt.

|**TextBlock-Typ**|**Erstellungszeit (in ms)**|**Renderingzeit (in ms)**|
|------------------------|------------------------------|----------------------------|
|Run zum Festlegen von Texteigenschaften|146|540|
|TextBlock zum Festlegen von Texteigenschaften|43|453|

### <a name="avoid-databinding-to-the-labelcontent-property"></a>Vermeiden von Datenbindung an die Label.Content-Eigenschaft

Stellen Sie sich ein Szenario vor, in dem Sie über ein <xref:System.Windows.Controls.Label> Objekt verfügen, das häufig von einer <xref:System.String> Quelle aktualisiert wird. Wenn die Daten an die <xref:System.Windows.Controls.ContentControl.Content%2A>-Eigenschaft des <xref:System.Windows.Controls.Label> Elements an das <xref:System.String> Quell Objekt gebunden werden, kann die Leistung beeinträchtigt werden. Jedes Mal, wenn die Quell <xref:System.String> aktualisiert wird, wird das alte <xref:System.String> Objekt verworfen und ein neuer <xref:System.String> neu erstellt – da ein <xref:System.String> Objekt unveränderlich ist, kann es nicht geändert werden. Dies bewirkt wiederum, dass die <xref:System.Windows.Controls.ContentPresenter> des <xref:System.Windows.Controls.Label> Objekts den alten Inhalt verwerfen und den neuen Inhalt neu generieren, um die neue <xref:System.String>anzuzeigen.

Die Lösung für dieses Problem ist einfach. Wenn die <xref:System.Windows.Controls.Label> nicht auf einen benutzerdefinierten <xref:System.Windows.Controls.ContentControl.ContentTemplate%2A> Wert festgelegt ist, ersetzen Sie die <xref:System.Windows.Controls.Label> durch eine <xref:System.Windows.Controls.TextBlock>, und binden Sie die <xref:System.Windows.Controls.TextBlock.Text%2A>-Eigenschaft an die Quell Zeichenfolge.

|**Datengebundene Eigenschaft**|**Aktualisierungszeit (in ms)**|
|-----------------------------|----------------------------|
|Label.Content|835|
|TextBlock.Text|242|

<a name="Hyperlink"></a>

## <a name="hyperlink"></a>Link

Das <xref:System.Windows.Documents.Hyperlink>-Objekt ist ein fortlaufendes Inhalts Element auf Inline Ebene, mit dem Sie Hyperlinks innerhalb des fortlaufenden Inhalts hosten können.

### <a name="combine-hyperlinks-in-one-textblock-object"></a>Kombinieren von Links in einem TextBlock-Objekt

Sie können die Verwendung mehrerer <xref:System.Windows.Documents.Hyperlink> Elemente optimieren, indem Sie Sie innerhalb desselben <xref:System.Windows.Controls.TextBlock>gruppieren. Dadurch wird die Anzahl der Objekte minimiert, die Sie in Ihrer Anwendung erstellen. Zum Beispiel kann es vorkommen, dass Sie mehrere Links wie folgt anzeigen möchten:

MSN Home &#124; My MSN

Das folgende Markup Beispiel zeigt mehrere <xref:System.Windows.Controls.TextBlock> Elemente, die zum Anzeigen der Hyperlinks verwendet werden:

[!code-xaml[Performance#PerformanceSnippet9](~/samples/snippets/csharp/VS_Snippets_Wpf/Performance/CSharp/Hyperlink.xaml#performancesnippet9)]

Im folgenden Markup Beispiel wird ein effizienteres Verfahren zum Anzeigen der Hyperlinks veranschaulicht. dieses Mal wird eine einzelne <xref:System.Windows.Controls.TextBlock>verwendet:

[!code-xaml[Performance#PerformanceSnippet10](~/samples/snippets/csharp/VS_Snippets_Wpf/Performance/CSharp/Hyperlink.xaml#performancesnippet10)]

### <a name="showing-underlines-on-hyperlinks-only-on-mouseenter-events"></a>Anzeigen der Unterstreichungen von Links nur bei MouseEnter-Ereignissen

Ein <xref:System.Windows.TextDecoration> Objekt ist eine visuelle Verzierung, die Sie Text hinzufügen können. Allerdings kann es für die instanziieren sehr Leistungs intensiv sein. Wenn Sie <xref:System.Windows.Documents.Hyperlink> Elemente umfassend verwenden, sollten Sie eine Unterstreichung nur beim Auslösen eines Ereignisses, z. b. des <xref:System.Windows.ContentElement.MouseEnter> Ereignisses, in Erwägung gezogen. Weitere Informationen finden Sie unter [Specify Whether a Hyperlink is Underlined (Angeben, ob ein Link unterstrichen wird)](how-to-specify-whether-a-hyperlink-is-underlined.md).

Die folgende Abbildung zeigt, wie das mouposienter-Ereignis den unterstrichenen Hyperlink auslöst:

![Links mit TextDecorations](./media/how-to-specify-whether-a-hyperlink-is-underlined/text-decorations-hyperlinks.png)

Das folgende Markup Beispiel zeigt eine <xref:System.Windows.Documents.Hyperlink>, die mit und ohne Unterstreichung definiert ist:

[!code-xaml[Performance#PerformanceSnippet11](~/samples/snippets/csharp/VS_Snippets_Wpf/Performance/CSharp/Hyperlink.xaml#performancesnippet11)]

In der folgenden Tabelle werden die Leistungseinbußen beim Anzeigen von 1000 <xref:System.Windows.Documents.Hyperlink>-Elementen mit und ohne Unterstreichung aufgeführt.

|**Link**|**Erstellungszeit (in ms)**|**Renderingzeit (in ms)**|
|-------------------|------------------------------|----------------------------|
|Mit Unterstreichung|289|1130|
|Ohne Unterstreichung|299|776|

<a name="Text_Formatting_Features"></a>

## <a name="text-formatting-features"></a>Textformatierungsfunktionen

[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] bietet umfangreiche Formatierungsdienste wie automatische Silbentrennung. Diese Dienste können die Leistung der Anwendung beeinträchtigen und sollten nur bei Bedarf verwendet werden.

### <a name="avoid-unnecessary-use-of-hyphenation"></a>Vermeiden von unnötiger Silbentrennung

Die automatische Silben Trennung findet Bindestriche für Textzeilen und ermöglicht zusätzliche Breakpoints für Linien in <xref:System.Windows.Controls.TextBlock>-und <xref:System.Windows.Documents.FlowDocument>-Objekten. In der Standardeinstellung ist die automatische Silbentrennung in diesen Objekten deaktiviert. Sie können diese Funktion aktivieren, indem Sie die IsHyphenationEnabled-Eigenschaft des Objekts auf `true` festlegen. Das Aktivieren dieses Features bewirkt jedoch, dass [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] die Component Object Model (com)-Interoperabilität initiiert, was sich auf die Leistung der Anwendung auswirken kann. Es wird empfohlen, die automatische Silbentrennung nur bei Bedarf zu verwenden.

### <a name="use-figures-carefully"></a>Vorsichtiges Verwenden von Figure-Elementen

Ein <xref:System.Windows.Documents.Figure>-Element stellt einen Teil des fortlaufenden Inhalts dar, der in einer Inhaltsseite absolut positioniert werden kann. In einigen Fällen kann eine <xref:System.Windows.Documents.Figure> bewirken, dass eine gesamte Seite automatisch neu formatiert wird, wenn die Position mit Inhalt, der bereits angelegt wurde, in Konflikt steht. Sie können die Möglichkeit der unnötigen Neuformatierung minimieren, indem Sie entweder <xref:System.Windows.Documents.Figure> Elemente nebeneinander gruppieren oder Sie in einem Szenario mit fester Seitengröße am oberen Rand des Inhalts deklarieren.

### <a name="optimal-paragraph"></a>Optimale Absatzformatierung

Die optimale Absatz Funktion des <xref:System.Windows.Documents.FlowDocument> Objekts bildet Absätze, sodass Leerraum so gleichmäßig wie möglich verteilt wird. In der Standardeinstellung ist die optimale Absatzformatierung deaktiviert. Sie können diese Funktion aktivieren, indem Sie die <xref:System.Windows.Documents.FlowDocument.IsOptimalParagraphEnabled%2A>-Eigenschaft des Objekts auf `true`festlegen. Allerdings beeinträchtigt die Aktivierung dieser Funktion die Leistung der Anwendung. Es wird empfohlen, die optimale Absatzformatierung nur bei Bedarf zu verwenden.

## <a name="see-also"></a>Siehe auch

- [Optimieren der WPF-Anwendungsleistung](optimizing-wpf-application-performance.md)
- [Planen der Anwendungsleistung](planning-for-application-performance.md)
- [Vorteile der Hardware nutzen](optimizing-performance-taking-advantage-of-hardware.md)
- [Layout und Entwurf](optimizing-performance-layout-and-design.md)
- [2D-Grafiken und Bildverarbeitung](optimizing-performance-2d-graphics-and-imaging.md)
- [Objektverhalten](optimizing-performance-object-behavior.md)
- [Anwendungsressourcen](optimizing-performance-application-resources.md)
- [Datenbindung](optimizing-performance-data-binding.md)
- [Weitere Leistungsempfehlungen](optimizing-performance-other-recommendations.md)
