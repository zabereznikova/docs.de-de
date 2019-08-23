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
ms.openlocfilehash: 318972c20f6461489226e19b3e517ba0ac069b28
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69933362"
---
# <a name="optimizing-performance-text"></a>Optimieren der Leistung: Text

[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] bietet Unterstützung für die Präsentation von Textinhalt durch Verwendung von umfangreichen [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)]-Steuerelementen. Im Allgemeinen können Sie das Rendern von Text in drei Ebenen unterteilen:

1. Direkte Verwendung <xref:System.Windows.Documents.Glyphs> des <xref:System.Windows.Media.GlyphRun> -Objekts und des-Objekts.

2. Verwenden des <xref:System.Windows.Media.FormattedText> -Objekts.

3. Verwenden von Steuerelementen auf hoher Ebene, z <xref:System.Windows.Controls.TextBlock> . <xref:System.Windows.Documents.FlowDocument> b. die Objekte und.

In diesem Thema erhalten Sie Empfehlungen bezüglich des Renderns von Text.

<a name="Glyph_Level"></a>

## <a name="rendering-text-at-the-glyph-level"></a>Rendern von Text auf der Symbolebene

[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]bietet erweiterte Unterstützung für Text, einschließlich Markup auf Symbolebene mit direktem <xref:System.Windows.Documents.Glyphs> Zugriff auf für Kunden, die Text nach der Formatierung abfangen und beibehalten möchten. Diese Funktionen stellen wichtige Unterstützung für verschiedene Text-Rendering-Voraussetzungen in jedem der folgenden Szenarios bereit.

- Bildschirmanzeige von Dokumenten mit festem Format

- Druckszenarios

  - [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] als Druckersprache für Geräte

  - Microsoft XPS-Dokumentwriter.

  - Vorherige Druckertreiber, Ausgabe von [!INCLUDE[TLA#tla_win32](../../../../includes/tlasharptla-win32-md.md)]-Anwendungen an das feste Format

  - Druckerspooler-Format

- Dokument Darstellung mit festem Format, einschließlich Clients für frühere Versionen von Windows und anderen Computergeräten.

> [!NOTE]
> <xref:System.Windows.Documents.Glyphs>und <xref:System.Windows.Media.GlyphRun> sind für Dokument Präsentations-und Druck Szenarien mit festem Format konzipiert. [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]bietet mehrere-Elemente für allgemeines Layout [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] und Szenarios <xref:System.Windows.Controls.Label> wie <xref:System.Windows.Controls.TextBlock>und. Weitere Informationen zu Layout- und [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]-Szenarios finden Sie unter [Typografie in WPF](typography-in-wpf.md).

In den folgenden Beispielen wird gezeigt, wie Eigenschaften für <xref:System.Windows.Documents.Glyphs> ein- [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]Objekt in definiert werden. Das <xref:System.Windows.Documents.Glyphs> -Objekt stellt die Ausgabe <xref:System.Windows.Media.GlyphRun> eines in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]dar. In den Beispielen wird davon ausgegangen, dass die Schriftarten Arial, Courier New und Times New Roman im Ordner **C:\WINDOWS\Fonts** auf dem lokalen Computer installiert sind.

[!code-xaml[GlyphsOvwSample1#1](~/samples/snippets/csharp/VS_Snippets_Wpf/GlyphsOvwSample1/CS/default.xaml#1)]

### <a name="using-drawglyphrun"></a>Verwenden von DrawGlyphRun

Wenn Sie über ein benutzerdefiniertes Steuerelement verfügen und Symbole darstellen möchten, <xref:System.Windows.Media.DrawingContext.DrawGlyphRun%2A> verwenden Sie die-Methode.

[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]bietet auch Dienste auf niedrigerer Ebene für die benutzerdefinierte Textformatierung durch die <xref:System.Windows.Media.FormattedText> Verwendung des-Objekts. Die effizienteste Methode zum Rendern von Text [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] in besteht darin, Text Inhalt mithilfe <xref:System.Windows.Documents.Glyphs> von und <xref:System.Windows.Media.GlyphRun>auf der Symbolebene zu erstellen. Die Kosten für diese Effizienz sind jedoch der Verlust einer leicht zu verwendenden Rich-Text-Formatierung, bei der es sich um [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] integrierte Funktionen von Steuer <xref:System.Windows.Controls.TextBlock> Elementen <xref:System.Windows.Documents.FlowDocument>handelt, wie z. b. und.

<a name="FormattedText_Object"></a>

## <a name="formattedtext-object"></a>FormattedText-Objekt

Das <xref:System.Windows.Media.FormattedText> -Objekt ermöglicht das Zeichnen von mehrzeiligen Text, in dem jedes Zeichen im Text einzeln formatiert werden kann. Weitere Informationen finden Sie unter [Drawing Formatted Text (Zeichnen von formatiertem Text)](drawing-formatted-text.md).

Um formatierten Text zu erstellen, <xref:System.Windows.Media.FormattedText.%23ctor%2A> rufen Sie den-Konstruktor zum Erstellen eines <xref:System.Windows.Media.FormattedText> -Objekts auf. Nachdem Sie die Anfangszeichenfolge für formatierten Text erstellt haben, können Sie eine Reihe von Formatvorlagen anwenden. Wenn Ihre Anwendung ein eigenes Layout implementieren möchte, ist das- <xref:System.Windows.Media.FormattedText> Objekt besser geeignet als die Verwendung eines-Steuer Elements, <xref:System.Windows.Controls.TextBlock>z. b. Weitere Informationen zum- <xref:System.Windows.Media.FormattedText> Objekt finden Sie unter [Zeichnen von formatiertem Text](drawing-formatted-text.md) .

Das <xref:System.Windows.Media.FormattedText> -Objekt stellt Text Formatierungsfunktionen auf niedriger Ebene bereit. Sie können mehrere Formatvorlagen auf ein oder mehrere Zeichen anwenden. Beispielsweise können Sie sowohl die <xref:System.Windows.Media.FormattedText.SetFontSize%2A> -Methode als auch die- <xref:System.Windows.Media.FormattedText.SetForegroundBrush%2A> Methode aufzurufen, um die Formatierung der ersten fünf Zeichen im Text zu ändern.

Im folgenden Codebeispiel wird ein <xref:System.Windows.Media.FormattedText> -Objekt erstellt und gerendert.

[!code-csharp[formattedtextsnippets#FormattedTextSnippets1](~/samples/snippets/csharp/VS_Snippets_Wpf/FormattedTextSnippets/CSharp/Window1.xaml.cs#formattedtextsnippets1)]
[!code-vb[formattedtextsnippets#FormattedTextSnippets1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/FormattedTextSnippets/visualbasic/window1.xaml.vb#formattedtextsnippets1)]

<a name="FlowDocument_TextBlock_Label"></a>

## <a name="flowdocument-textblock-and-label-controls"></a>FlowDocument, TextBlock- und Label-Steuerelemente

[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] enthält zahlreiche Steuerelemente für das Zeichnen von Text auf dem Bildschirm. Jedes Steuerelement dient einem anderen Szenario und verfügt über eine eigene Liste von Funktionen und Einschränkungen.

### <a name="flowdocument-impacts-performance-more-than-textblock-or-label"></a>FlowDocument wirkt sich mehr auf die Leistung aus als TextBlock oder Label

Im Allgemeinen sollte das <xref:System.Windows.Controls.TextBlock> -Element verwendet werden, wenn eingeschränkte Textunterstützung erforderlich ist, z. b. ein kurzer [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)]Satz in einer. <xref:System.Windows.Controls.Label>kann verwendet werden, wenn nur minimale Textunterstützung erforderlich ist. Das <xref:System.Windows.Documents.FlowDocument> -Element ist ein Container für erneut flowable-Dokumente, die eine umfangreiche Präsentation von Inhalten unterstützen und somit eine höhere Leistung als die <xref:System.Windows.Controls.TextBlock> Verwendung <xref:System.Windows.Controls.Label> der-oder-Steuerelemente haben.

Weitere Informationen zu finden <xref:System.Windows.Documents.FlowDocument>Sie unter [Übersicht über Fluss Dokumente](flow-document-overview.md).

### <a name="avoid-using-textblock-in-flowdocument"></a>Vermeiden von TextBlock in FlowDocument

Das <xref:System.Windows.Controls.TextBlock> -Element wird von <xref:System.Windows.UIElement>abgeleitet. Das <xref:System.Windows.Documents.Run> -Element wird von <xref:System.Windows.Documents.TextElement>abgeleitet. Dies ist weniger kostspielig als ein <xref:System.Windows.UIElement>von abgeleitetes Objekt. Verwenden <xref:System.Windows.Documents.Run> Sie <xref:System.Windows.Controls.TextBlock> nach Möglichkeit anstelle von, um Textinhalte in einem <xref:System.Windows.Documents.FlowDocument>anzuzeigen.

Im folgenden Markup Beispiel werden zwei Möglichkeiten zum Festlegen von Text Inhalt in <xref:System.Windows.Documents.FlowDocument>einem veranschaulicht:

[!code-xaml[Performance#PerformanceSnippet13](~/samples/snippets/csharp/VS_Snippets_Wpf/Performance/CSharp/FlowDocument.xaml#performancesnippet13)]

### <a name="avoid-using-run-to-set-text-properties"></a>Vermeiden von Run zum Festlegen von Texteigenschaften

Im Allgemeinen ist die Verwendung <xref:System.Windows.Documents.Run> von innerhalb <xref:System.Windows.Controls.TextBlock> einer Leistungs intensiver als die Verwendung eines expliziten <xref:System.Windows.Documents.Run> Objekts. Wenn Sie verwenden <xref:System.Windows.Documents.Run> , um Texteigenschaften festzulegen, legen Sie diese Eigenschaften <xref:System.Windows.Controls.TextBlock> stattdessen direkt auf fest.

Im folgenden Markup Beispiel werden diese beiden Methoden zum Festlegen einer Text Eigenschaft (in diesem Fall die <xref:System.Windows.Controls.TextBlock.FontWeight%2A> -Eigenschaft) veranschaulicht:

[!code-xaml[Performance#PerformanceSnippet12](~/samples/snippets/csharp/VS_Snippets_Wpf/Performance/CSharp/Window1.xaml#performancesnippet12)]

Die folgende Tabelle zeigt die Kosten für die Anzeige <xref:System.Windows.Controls.TextBlock> von 1000-Objekten mit und <xref:System.Windows.Documents.Run>ohne explizite.

|**TextBlock-Typ**|**Erstellungszeit (in ms)**|**Renderingzeit (in ms)**|
|------------------------|------------------------------|----------------------------|
|Run zum Festlegen von Texteigenschaften|146|540|
|TextBlock zum Festlegen von Texteigenschaften|43|453|

### <a name="avoid-databinding-to-the-labelcontent-property"></a>Vermeiden von Datenbindung an die Label.Content-Eigenschaft

Stellen Sie sich ein Szenario vor, <xref:System.Windows.Controls.Label> in dem Sie über ein-Objekt <xref:System.String> verfügen, das häufig von einer Quelle aktualisiert wird Bei der Datenbindung <xref:System.Windows.Controls.Label> der- <xref:System.Windows.Controls.ContentControl.Content%2A> Eigenschaft des Elements <xref:System.String> an das Quell Objekt kann eine schlechte Leistung auftreten. Jedes Mal, wenn <xref:System.String> die Quelle aktualisiert wird, <xref:System.String> wird das alte Objekt verworfen und <xref:System.String> ein neuer neu erstellt – da <xref:System.String> ein-Objekt unveränderlich ist, kann es nicht geändert werden. Dies bewirkt wiederum, dass der <xref:System.Windows.Controls.ContentPresenter> <xref:System.Windows.Controls.Label> des-Objekts seinen alten Inhalt verwerfen und den neuen Inhalt neu generiert, um die neue <xref:System.String>anzuzeigen.

Die Lösung für dieses Problem ist einfach. Wenn der <xref:System.Windows.Controls.Label> nicht auf einen benutzerdefinierten <xref:System.Windows.Controls.ContentControl.ContentTemplate%2A> Wert festgelegt ist, <xref:System.Windows.Controls.Label> ersetzen Sie <xref:System.Windows.Controls.TextBlock> den durch einen, <xref:System.Windows.Controls.TextBlock.Text%2A> und binden Sie seine-Eigenschaft an die Quell Zeichenfolge.

|**Datengebundene Eigenschaft**|**Aktualisierungszeit (in ms)**|
|-----------------------------|----------------------------|
|Label.Content|835|
|TextBlock.Text|242|

<a name="Hyperlink"></a>

## <a name="hyperlink"></a>Link

Das <xref:System.Windows.Documents.Hyperlink> -Objekt ist ein fortlaufendes Inhalts Element auf Inline Ebene, mit dem Sie Hyperlinks innerhalb des fortlaufenden Inhalts hosten können.

### <a name="combine-hyperlinks-in-one-textblock-object"></a>Kombinieren von Links in einem TextBlock-Objekt

Sie können die Verwendung mehrerer <xref:System.Windows.Documents.Hyperlink> Elemente optimieren, indem Sie Sie innerhalb desselben <xref:System.Windows.Controls.TextBlock>gruppieren. Dadurch wird die Anzahl der Objekte minimiert, die Sie in Ihrer Anwendung erstellen. Zum Beispiel kann es vorkommen, dass Sie mehrere Links wie folgt anzeigen möchten:

MSN Home &#124; My MSN

Das folgende Markup Beispiel zeigt mehrere <xref:System.Windows.Controls.TextBlock> Elemente, die zum Anzeigen der Hyperlinks verwendet werden:

[!code-xaml[Performance#PerformanceSnippet9](~/samples/snippets/csharp/VS_Snippets_Wpf/Performance/CSharp/Hyperlink.xaml#performancesnippet9)]

Im folgenden Markup Beispiel wird ein effizienteres Verfahren zum Anzeigen der Hyperlinks gezeigt, diesmal mit einem einzelnen <xref:System.Windows.Controls.TextBlock>:

[!code-xaml[Performance#PerformanceSnippet10](~/samples/snippets/csharp/VS_Snippets_Wpf/Performance/CSharp/Hyperlink.xaml#performancesnippet10)]

### <a name="showing-underlines-on-hyperlinks-only-on-mouseenter-events"></a>Anzeigen der Unterstreichungen von Links nur bei MouseEnter-Ereignissen

Bei <xref:System.Windows.TextDecoration> einem-Objekt handelt es sich um eine visuelle Verzierung, die Sie Text hinzufügen können. es kann jedoch eine Leistungs intensive instanziieren sein. Wenn Sie <xref:System.Windows.Documents.Hyperlink> Elemente umfassend verwenden, sollten Sie eine Unterstreichung nur beim Auslösen eines Ereignisses, z. b. <xref:System.Windows.ContentElement.MouseEnter> dem-Ereignis, in Erwägung gezogen. Weitere Informationen finden Sie unter [Specify Whether a Hyperlink is Underlined (Angeben, ob ein Link unterstrichen wird)](how-to-specify-whether-a-hyperlink-is-underlined.md).

Die folgende Abbildung zeigt, wie das mouposienter-Ereignis den unterstrichenen Hyperlink auslöst:

![Links mit TextDecorations](./media/how-to-specify-whether-a-hyperlink-is-underlined/text-decorations-hyperlinks.png)

Das folgende Markup Beispiel zeigt einen <xref:System.Windows.Documents.Hyperlink> , der mit und ohne Unterstreichung definiert ist:

[!code-xaml[Performance#PerformanceSnippet11](~/samples/snippets/csharp/VS_Snippets_Wpf/Performance/CSharp/Hyperlink.xaml#performancesnippet11)]

In der folgenden Tabelle werden die Leistungseinbußen der Anzeige <xref:System.Windows.Documents.Hyperlink> von 1000 Elementen mit und ohne Unterstreichung aufgeführt.

|**Link**|**Erstellungszeit (in ms)**|**Renderingzeit (in ms)**|
|-------------------|------------------------------|----------------------------|
|Mit Unterstreichung|289|1130|
|Ohne Unterstreichung|299|776|

<a name="Text_Formatting_Features"></a>

## <a name="text-formatting-features"></a>Textformatierungsfunktionen

[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] bietet umfangreiche Formatierungsdienste wie automatische Silbentrennung. Diese Dienste können die Leistung der Anwendung beeinträchtigen und sollten nur bei Bedarf verwendet werden.

### <a name="avoid-unnecessary-use-of-hyphenation"></a>Vermeiden von unnötiger Silbentrennung

Die automatische Silben Trennung findet Bindestriche für Textzeilen und ermöglicht zusätzliche Breakpoints für Linien in <xref:System.Windows.Controls.TextBlock> -und- <xref:System.Windows.Documents.FlowDocument> Objekten. In der Standardeinstellung ist die automatische Silbentrennung in diesen Objekten deaktiviert. Sie können diese Funktion aktivieren, indem Sie die IsHyphenationEnabled-Eigenschaft des Objekts auf `true` festlegen. Das Aktivieren dieses Features bewirkt [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] jedoch, dass die Interoperabilität von Component Object Model (com) initiiert wird, was sich auf die Leistung der Anwendung auswirken kann. Es wird empfohlen, die automatische Silbentrennung nur bei Bedarf zu verwenden.

### <a name="use-figures-carefully"></a>Vorsichtiges Verwenden von Figure-Elementen

Ein <xref:System.Windows.Documents.Figure> -Element stellt einen Teil des fortlaufenden Inhalts dar, der in einer Inhaltsseite absolut positioniert werden kann. In einigen Fällen kann ein <xref:System.Windows.Documents.Figure> bewirken, dass eine gesamte Seite automatisch neu formatiert wird, wenn die Position mit Inhalt, der bereits angelegt wurde, in Konflikt steht. Sie können die Möglichkeit der unnötigen Neuformatierung minimieren, indem Sie <xref:System.Windows.Documents.Figure> Elemente nebeneinander gruppieren oder Sie in einem Szenario mit fester Seitengröße am oberen Rand des Inhalts deklarieren.

### <a name="optimal-paragraph"></a>Optimale Absatzformatierung

Mit der optimalen Absatz Funktion des <xref:System.Windows.Documents.FlowDocument> -Objekts werden Absätze angelegt, sodass Leerraum so gleichmäßig wie möglich verteilt wird. In der Standardeinstellung ist die optimale Absatzformatierung deaktiviert. Sie können diese Funktion aktivieren, indem Sie die- <xref:System.Windows.Documents.FlowDocument.IsOptimalParagraphEnabled%2A> Eigenschaft des `true`-Objekts auf festlegen. Allerdings beeinträchtigt die Aktivierung dieser Funktion die Leistung der Anwendung. Es wird empfohlen, die optimale Absatzformatierung nur bei Bedarf zu verwenden.

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
