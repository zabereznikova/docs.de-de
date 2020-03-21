---
title: Typografie
ms.date: 03/30/2017
helpviewer_keywords:
- typography [WPF], about typography
ms.assetid: 06cbf17b-6eff-4fe5-949d-2dd533e4e1f4
ms.openlocfilehash: 501a4221c99d405484a2fb908641d27d1f38f266
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79187350"
---
# <a name="typography-in-wpf"></a>Typografie in WPF
In diesem Thema werden die wichtigsten typografischen Funktionen von [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] vorgestellt. Zu diesen Funktionen gehören eine verbesserte Qualität und Leistung des Textrenderings, OpenType-Typografieunterstützung, verbesserter internationaler Text, verbesserte Schriftartunterstützung und neue APIs (Text Application Programming Interfaces).  
  
<a name="Improved_Quality_and_Performance_of_Text"></a>
## <a name="improved-quality-and-performance-of-text"></a>Verbesserte Textqualität und -leistung  
 Text [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] in wird mit Microsoft ClearType gerendert, was die Klarheit und Lesbarkeit von Text verbessert. ClearType ist eine von Microsoft entwickelte Softwaretechnologie, die die Lesbarkeit von Text auf vorhandenen LCDs (Liquid Crystal Displays) wie Laptop-Bildschirmen, Pocket-PC-Bildschirmen und Flachbildschirmen verbessert. ClearType verwendet Subpixel-Rendering, das es ermöglicht, Text mit einer größeren Genauigkeit zu seiner tatsächlichen Form anzuzeigen, indem Zeichen auf einem Bruchteil eines Pixels ausgerichtet werden. Die zusätzliche Auflösung verbessert die Schärfe der kleinen Details in der Textanzeige, was das Lesen über lange Zeiträume hinweg erleichtert. Eine weitere Verbesserung [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] von ClearType in ist y-Richtung Anti-Aliasing, die die Ober- und Unterteile der flachen Kurven in Textzeichen glättet. Weitere Informationen zu ClearType-Features finden Sie unter [ClearType Overview](cleartype-overview.md).  
  
 ![Text mit ClearType-Y-Richtung-Antialiasing](./media/typography-in-wpf/text-y-direction-antialiasing.gif)  
Text mit ClearType-Antialiasing auf der y-Achse  
  
 Die gesamte Textrendering-Pipeline kann in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] hardwarebeschleunigt erfolgen, vorausgesetzt, dass Ihr Computer die Mindestanforderungen an die Hardware erfüllt. Rendering, das nicht mit der Hardware ausgeführt werden kann, wird als Softwarerendering ausgeführt. Die Hardwarebeschleunigung wirkt sich auf alle Phasen der Textrenderingpipeline aus – vom Speichern einzelner Glyphen, dem Kompositieren von Glyphen in Glyphenläufen, dem Anwenden von Effekten bis hin zur Anwendung des ClearType-Mischalgorithmus auf die endgültige angezeigte Ausgabe. Weitere Informationen zur Hardware-Beschleunigung finden Sie unter [Renderingebenen für Grafiken](graphics-rendering-tiers.md).  
  
 ![Diagramm der Text-Rendering-Pipeline](./media/typography-in-wpf/text-rendering-pipeline.png)  
  
 Darüber hinaus nutzen Textanimation die durch [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] aktivierten Vorteile der Grafikhardwarefunktion mit Zeichen oder Glyphen voll aus. Das Ergebnis ist eine glatte Textanimation.  
  
<a name="Rich_Typography"></a>
## <a name="rich-typography"></a>Umfangreiche Typografie  
 Das OpenType-Schriftartformat ist eine Erweiterung des TrueType®-Schriftformats. Das OpenType-Schriftartformat wurde gemeinsam von Microsoft und Adobe entwickelt und bietet eine breite Palette erweiterter typografischer Funktionen. Das <xref:System.Windows.Documents.Typography> Objekt macht viele der erweiterten Funktionen von OpenType-Schriftarten verfügbar, z. B. stilistische Alternativen und Swashes. Das Windows SDK bietet eine Reihe von OpenType-Beispielschriftarten, die mit umfangreichen Features wie den Schriftarten Pericles und Pescadero entwickelt wurden. Weitere Informationen finden Sie unter [Beispiel OpenType Font Pack](sample-opentype-font-pack.md).  
  
 Die Pericles OpenType-Schriftart enthält zusätzliche Glyphen, die stilistische Alternativen zum Standardsatz von Glyphen bieten. Im folgenden Text werden Symbole im alternativen Stil gezeigt.  
  
 ![Text mit alternativen OpenType-Stilsymbolen](./media/typography-in-wpf/opentype-stylistic-alternate-glyphs.gif "Text mit alternativen OpenType-Stilsymbolen")  
  
 Schwungschrift besteht aus dekorativen Symbolen, deren ausgefeilte Verzierung häufig mit Kalligraphie assoziiert wird. Im folgenden Text werden Standard- und Schwungsymbole für die Schriftart Pescadero gezeigt.  
  
 ![Text mit OpenType-Standard- und Ziersymbolen](./media/typography-in-wpf/opentype-standard-swash-glyphs.gif "Text mit OpenType-Standard- und Ziersymbolen")  
  
 Weitere Informationen zu OpenType-Features finden Sie unter [OpenType-Schriftart-Features](opentype-font-features.md).  
  
<a name="Enhanced_International_Text_Support"></a>
## <a name="enhanced-international-text-support"></a>Verbesserte Unterstützung für internationalen Text  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] bietet durch die folgenden Funktionen eine verbesserte Unterstützung für internationalen Text:  
  
- Automatischer Zeilenabstand in allen Schriftsystem mithilfe adaptiver Maßeinheiten.  
  
- Umfassende Unterstützung für internationalen Text. Weitere Informationen finden Sie unter [Globalisierung für WPF](globalization-for-wpf.md).  
  
- An der Sprache orientierter Zeilenumbruch, Silbentrennung und Ausrichtung.  
  
<a name="Enhanced_Font_Support"></a>
## <a name="enhanced-font-support"></a>Verbesserte Unterstützung für Schriftarten  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] bietet durch die folgenden Funktionen eine verbesserte Unterstützung für Schriftarten:  
  
- Unicode für den jeden Text. Für Schriftartverhalten und -auswahl wird Charset oder Codepage nicht mehr benötigt.  
  
- Von globalen Einstellungen unabhängige Schriftartverhalten, z.B. Systemgebietsschema.  
  
- Separate <xref:System.Windows.FontWeight> <xref:System.Windows.FontStretch>, <xref:System.Windows.FontStyle> und Typen <xref:System.Windows.Media.FontFamily>zum Definieren einer . Dies bietet eine größere Flexibilität als bei der Win32-Programmierung, bei der boolesche Kombinationen aus Kursiv schriftverbindung und Fettfett verwendet werden, um eine Schriftfamilie zu definieren.  
  
- Die Schreibrichtung (horizontal oder vertikal) wird unabhängig von dem Schriftnamen behandelt.  
  
- Font-Linking und Schriftart-Fallback in einer portablen XML-Datei mithilfe der Zusammengesetzten Schriftarttechnologie. Zusammengesetzte Schriftarten ermöglichen die Erstellung von vollständigen mehrsprachigen Schriftarten. Zusammengesetzte Schriftarten verfügen zudem über einen Mechanismus, der das Anzeigen fehlender Glyphen verhindert. Weitere Informationen finden Sie in <xref:System.Windows.Media.FontFamily> den Anmerkungen in der Klasse.  
  
- Erstellen internationaler Schriftarten aus zusammengesetzten Schriftarten mithilfe einer Gruppe an Einzelsprachenschriftarten. Dadurch werden Ressourcenkosten bei der Entwicklung von Schriftarten für mehrere Sprachen gespart.  
  
- In einem Dokument eingebettete zusammengesetzte Schriftarten für die Portierung von Dokumenten. Weitere Informationen finden Sie in <xref:System.Windows.Media.FontFamily> den Anmerkungen in der Klasse.  
  
<a name="New_Text_APIs"></a>
## <a name="new-text-application-programming-interfaces-apis"></a>Standardisierte APIs (Application Programming Interface)  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]bietet mehrere Text-APIs, die Entwickler verwenden können, wenn text in ihre Anwendungen eingeteilt wird. Diese APIs sind in drei Kategorien eingeteilt:  
  
- **Layout und Benutzeroberfläche**. Die allgemeinen Textsteuerelemente für die grafische Benutzeroberfläche (GUI).  
  
- **Leichte Textzeichnung**. Ermöglicht das direkte Zeichnen von Text auf Objekten.  
  
- **Erweiterte Textformatierung**. Ermöglicht Ihnen, eine benutzerdefinierte Text-Engine zu implementieren.  
  
### <a name="layout-and-user-interface"></a>Layout und Benutzeroberfläche  
 Auf [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] höchster Funktionalität stellen die Text-APIs allgemeine <xref:System.Windows.Controls.Label> <xref:System.Windows.Controls.TextBlock>Steuerelemente <xref:System.Windows.Controls.TextBox>wie , und . Diese Steuerelemente stellen innerhalb einer Anwendung die grundlegenden [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]-Elemente zur Verfügung und bieten eine einfache Möglichkeit, Text darzustellen und zu bearbeiten. Steuerelemente <xref:System.Windows.Controls.RichTextBox> wie <xref:System.Windows.Controls.PasswordBox> und ermöglichen eine erweiterte oder spezialisiertetextbezogene Textverarbeitung. Und Klassen <xref:System.Windows.Documents.TextRange>wie <xref:System.Windows.Documents.TextSelection>, <xref:System.Windows.Documents.TextPointer> und aktivieren nützliche Textbearbeitung. Diese [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] Steuerelemente stellen <xref:System.Windows.Controls.Control.FontFamily%2A> <xref:System.Windows.Controls.Control.FontSize%2A>Eigenschaften <xref:System.Windows.Controls.Control.FontStyle%2A>wie , und , bereit, mit denen Sie die Schriftart steuern können, die zum Rendern des Textes verwendet wird.  
  
#### <a name="using-bitmap-effects-transforms-and-text-effects"></a>Verwenden von Bitmapeffekten, Transformationen und Texteffekten  
 Mit [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] können Sie visuell interessante Texte mithilfe von Funktionen wie Bitmapeffekten, Transformationen und Texteffekten erstellen. Das folgende Beispiel zeigt einen typischen auf einen Text angewandten Schlagschatteneffekt.  
  
 ![Textschatten mit Weichheit &#61; 0,25](./media/typography-in-wpf/drop-shadow-text-effect.jpg)
  
 Das folgende Beispiel zeigt einen Text mit Schlagschatteneffekt und Rauschen.  
  
 ![Textschatten mit Rauschen](./media/typography-in-wpf/drop-shadow-noise-text.jpg)
  
 Das folgende Beispiel zeigt einen Text mit dem Effekt Schein nach außen (Outer Glow).  
  
 ![Textschatten mit einem OuterGlowBitmapEffect](./media/typography-in-wpf/text-shadow-glow-effect.jpg)
  
 Das folgende Beispiel zeigt einen Text mit Weichzeichnereffekt.  
  
 ![Textschatten mit einem BlurBitmapEffect](./media/typography-in-wpf/text-shadow-blur-effect.jpg)  

 Das folgende Beispiel zeigt die zweite Textzeile, die um 150 % entlang der X-Achse skaliert ist, und die dritte Textzeile, die um 150 % entlang der Y-Achse skaliert ist.  
  
 ![Skalierter Text mithilfe einer ScaleTransform](./media/typography-in-wpf/scaled-text-scaletransform.jpg)
  
 Das folgende Beispiel zeigt einen entlang der X-Achse geneigten Text.  
  
 ![Geneigter Text mithilfe einer SkewTransform](./media/typography-in-wpf/skewed-transformed-text.jpg)
  
 Ein <xref:System.Windows.Media.TextEffect> Objekt ist ein Hilfsobjekt, mit dem Sie Text als eine oder mehrere Gruppen von Zeichen in einer Textzeichenfolge behandeln können. Das folgende Beispiel zeigt ein einzelnes Zeichen, das gedreht wurde. Jedes Zeichen wird unabhängig in Intervallen von 1 Sekunde gedreht.  
  
 ![Bildschirmabbildung des Texteffekts zum Drehen von Text](./media/typography-in-wpf/rotating-text-effect.jpg)
  
#### <a name="using-flow-documents"></a>Verwenden von Flussdokumenten  
 Zusätzlich zu den [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] allgemeinen [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Steuerelementen bietet ein Layoutsteuerelement für die Textpräsentation – das <xref:System.Windows.Documents.FlowDocument> Element. Das <xref:System.Windows.Documents.FlowDocument> Element stellt in <xref:System.Windows.Controls.DocumentViewer> Verbindung mit dem Element ein Steuerelement für große Textmengen mit unterschiedlichen Layoutanforderungen bereit. Layoutsteuerelemente ermöglichen den Zugriff <xref:System.Windows.Documents.Typography> auf erweiterte Typografie über [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] die objekt- und schriftartbezogenen Eigenschaften anderer Steuerelemente.  
  
 Das folgende Beispiel zeigt Textinhalte, die in einer <xref:System.Windows.Controls.FlowDocumentReader>gehostet werden, die Unterstützung bei der Suche, Navigation, Paginierung und Inhaltsskalierung bietet.  
  
 ![Screenshot, der OpenType-Schriftarten zeigt.](./media/typography-in-wpf/typography-text-flowdocumentreader.png)
  
 Weitere Informationen finden Sie unter [Dokumente in WPF](documents-in-wpf.md).  
  
### <a name="lightweight-text-drawing"></a>Einfache Textzeichnung  
 Sie können Text [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] direkt in <xref:System.Windows.Media.DrawingContext.DrawText%2A> Objekte zeichnen, indem Sie die Methode des <xref:System.Windows.Media.DrawingContext> Objekts verwenden. Um diese Methode zu <xref:System.Windows.Media.FormattedText> verwenden, erstellen Sie ein Objekt. Dieses Objekt ermöglicht das Zeichnen von mehrzeiligem Text, in dem jedes Zeichen einzeln formatiert werden kann. Die Funktionalität <xref:System.Windows.Media.FormattedText> des Objekts enthält einen Großteil der Funktionalität der DrawText-Flags in der Windows-API. Darüber hinaus <xref:System.Windows.Media.FormattedText> enthält das Objekt Funktionen wie die Ellipsenunterstützung, bei der eine Auslassung angezeigt wird, wenn Text seine Grenzen überschreitet. Das folgende Beispiel zeigt Text auf den verschiedene Formatierungen angewendet wurden, wie z.B. einen linearen Farbverlauf auf dem zweiten und dritten Wort.  
  
 ![Mit dem FormattedText-Objekt angezeigter Text](./media/typography-in-wpf/text-formatted-linear-gradient.jpg)
  
 Sie können formatierten <xref:System.Windows.Media.Geometry> Text in Objekte konvertieren, sodass Sie andere Arten von visuell interessantem Text erstellen können. Sie können z. <xref:System.Windows.Media.Geometry> B. ein Objekt basierend auf der Gliederung einer Textzeichenfolge erstellen.  
  
 ![Textkontur mit einem linearen Farbverlaufspinsel](./media/typography-in-wpf/text-outline-linear-gradient.jpg)  
  
 Die folgenden Beispiele zeigen verschiedene Möglichkeiten zum Erstellen von visuell interessanten Effekten durch Ändern von Strich, Füllung und Hervorhebung des konvertierten Texts.  
  
 ![Text mit unterschiedlichen Farben für Füllung und Strich](./media/typography-in-wpf/fill-stroke-text-effect.jpg)  
  
 ![Text mit auf Strich angewendeten Bildpinsel](./media/typography-in-wpf/image-brush-application.jpg)
  
 ![Text mit Bildpinsel, der auf Strich und Hervorhebung angewendet wird](./media/typography-in-wpf/image-brush-text-application.jpg)
  
 Weitere Informationen zum <xref:System.Windows.Media.FormattedText> Objekt finden Sie unter [Zeichnungsformatierter Text](drawing-formatted-text.md).  
  
### <a name="advanced-text-formatting"></a>Erweiterte Textformatierung  
 Auf der fortschrittlichsten Ebene der [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Text-APIs bietet Ihnen die Möglichkeit, benutzerdefiniertes Textlayout zu erstellen, indem Sie das <xref:System.Windows.Media.TextFormatting.TextFormatter> Objekt und andere Typen im <xref:System.Windows.Media.TextFormatting> Namespace verwenden. Mit <xref:System.Windows.Media.TextFormatting.TextFormatter> den zugehörigen Klassen können Sie benutzerdefiniertes Textlayout implementieren, das Ihre eigene Definition von Zeichenformaten, Absatzformaten, Zeilenumbruchregeln und anderen Layoutfeatures für internationalen Text unterstützt. Es gibt nur sehr wenige Fälle, in denen es sinnvoll ist, die Standardimplementierung der [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-Textlayoutunterstützung zu überschreiben. Wenn Sie jedoch ein Steuerelement oder eine Anwendung erstellen, kann möglicherweise eine andere Implementierung als die standardmäßige [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-Implementierung benötigt werden.  
  
 Im Gegensatz zu einer <xref:System.Windows.Media.TextFormatting.TextFormatter> herkömmlichen Text-API interagiert der mit einem Textlayoutclient über eine Reihe von Rückrufmethoden. Der Client muss diese Methoden in einer <xref:System.Windows.Media.TextFormatting.TextSource> Implementierung der Klasse bereitstellen. Das folgende Diagramm veranschaulicht die Textlayoutinteraktion <xref:System.Windows.Media.TextFormatting.TextFormatter>zwischen der Clientanwendung und .  
  
 ![Diagramm des Textlayout-Clients und TextFormatter](./media/typography-in-wpf/text-layout-text-formatter-interaction.png)  
  
 Weitere Informationen zum Erstellen von benutzerdefinierten Textlayouts finden Sie unter [Advanced Text Formatting](advanced-text-formatting.md).  
  
## <a name="see-also"></a>Weitere Informationen

- <xref:System.Windows.Media.FormattedText>
- <xref:System.Windows.Media.TextFormatting.TextFormatter>
- [Übersicht über ClearType](cleartype-overview.md)
- [Features für OpenType-Schriftarten](opentype-font-features.md)
- [Zeichnen von formatiertem Text](drawing-formatted-text.md)
- [Erweiterte Textformatierung](advanced-text-formatting.md)
- [Text](optimizing-performance-text.md)
- [Microsoft-Typografie](https://docs.microsoft.com/typography/)
