---
title: Typografie in WPF
ms.date: 03/30/2017
helpviewer_keywords:
- typography [WPF], about typography
ms.assetid: 06cbf17b-6eff-4fe5-949d-2dd533e4e1f4
ms.openlocfilehash: 743b9ec45c138053fcfcb5cbb1ea9c8490ba919e
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/30/2019
ms.locfileid: "68629918"
---
# <a name="typography-in-wpf"></a>Typografie in WPF
In diesem Thema werden die wichtigsten typografischen Funktionen von [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] vorgestellt. Diese Funktionen umfassen die verbesserte Qualität und Leistung beim Textrendering, die Unterstützung von [!INCLUDE[TLA#tla_opentype](../../../../includes/tlasharptla-opentype-md.md)]-Typografie, einen verbesserten internationalen Text, eine verbesserte Unterstützung für Schriftarten sowie neue Text-Anwendungsprogrammierschnittstellen (APIs).  
  
<a name="Improved_Quality_and_Performance_of_Text"></a>   
## <a name="improved-quality-and-performance-of-text"></a>Verbesserte Textqualität und -leistung  
 Text in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] wird mithilfe von Microsoft ClearType gerendert, wodurch die Übersichtlichkeit und Lesbarkeit von Text verbessert wird. ClearType ist eine von entwickelte Softwaretechnologie [!INCLUDE[TLA#tla_ms](../../../../includes/tlasharptla-ms-md.md)] , mit der die Lesbarkeit von Text auf vorhandenen LCDs (Liquid Crystal Displays), wie z. b. Laptop Bildschirmen, Pocket PC-Bildschirme und Flatpanel-Monitoren, verbessert wird. ClearType verwendet das Subpixel-Rendering, das es ermöglicht, Text mit einer größeren Genauigkeit als echte Form anzuzeigen, indem Zeichen an einem Bruchteil eines Pixels ausgerichtet werden. Die zusätzliche Auflösung verbessert die Schärfe der kleinen Details in der Textanzeige, was das Lesen über lange Zeiträume hinweg erleichtert. Eine weitere Verbesserung von ClearType [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] in ist das Antialiasing in y-Richtung, bei dem die Ober-und Unterstriche von flachen Kurven in Textzeichen glättet werden. Weitere Informationen zu ClearType-Features finden Sie unter [Übersicht über ClearType](cleartype-overview.md).  
  
 ![Text mit ClearType-Y-Richtung-Antialiasing](./media/typography-in-wpf/text-y-direction-antialiasing.gif)  
Text mit ClearType-Antialiasing auf der y-Achse  
  
 Die gesamte Textrendering-Pipeline kann in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] hardwarebeschleunigt erfolgen, vorausgesetzt, dass Ihr Computer die Mindestanforderungen an die Hardware erfüllt. Rendering, das nicht mit der Hardware ausgeführt werden kann, wird als Softwarerendering ausgeführt. Die Hardware Beschleunigung wirkt sich auf alle Phasen der Textrenderingpipeline aus – von der Speicherung einzelner Symbole, der Komposition von Symbolen in Glyphe, dem Anwenden von Effekten bis zum Anwenden des ClearType-Mischungs Algorithmus auf die endgültige angezeigte Ausgabe. Weitere Informationen zur Hardware-Beschleunigung finden Sie unter [Renderingebenen für Grafiken](graphics-rendering-tiers.md).  
  
 ![Diagramm der Text-Rendering-Pipeline](./media/typography-in-wpf/text-rendering-pipeline.png)  
  
 Darüber hinaus nutzen Textanimation die durch [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] aktivierten Vorteile der Grafikhardwarefunktion mit Zeichen oder Glyphen voll aus. Das Ergebnis ist eine glatte Textanimation.  
  
<a name="Rich_Typography"></a>   
## <a name="rich-typography"></a>Umfangreiche Typografie  
 Das [!INCLUDE[TLA2#tla_opentype](../../../../includes/tla2sharptla-opentype-md.md)]-Schriftartformat ist eine Erweiterung des [!INCLUDE[TLA#tla_truetype](../../../../includes/tlasharptla-truetype-md.md)]-Schriftartformats. Das [!INCLUDE[TLA2#tla_opentype](../../../../includes/tla2sharptla-opentype-md.md)]-Schriftartformat wurde gemeinsam von [!INCLUDE[TLA#tla_ms](../../../../includes/tlasharptla-ms-md.md)] und Adobe entwickelt und bietet eine umfangreiche Auswahl an erweiterten typografischen Funktionen. Das <xref:System.Windows.Documents.Typography> -Objekt macht viele erweiterte Funktionen von [!INCLUDE[TLA2#tla_opentype](../../../../includes/tla2sharptla-opentype-md.md)] Schriftarten verfügbar, wie z. b. Stilvarianten und Swashes. Das [!INCLUDE[TLA2#tla_lhsdk](../../../../includes/tla2sharptla-lhsdk-md.md)] bietet eine Reihe von [!INCLUDE[TLA2#tla_opentype](../../../../includes/tla2sharptla-opentype-md.md)]-Schriftarten, die umfassende Funktionen enthalten,wie z.B. die Schriftarten Pericles und Pescadero. Weitere Informationen finden Sie unter [OpenType-Beispielschriftartenpaket](sample-opentype-font-pack.md).  
  
 Die [!INCLUDE[TLA2#tla_opentype](../../../../includes/tla2sharptla-opentype-md.md)]-Schriftart Pericles enthält zusätzliche Glyphen, die alternative Stile für den Standardsatz von Glyphen bieten. Im folgenden Text werden Symbole im alternativen Stil gezeigt.  
  
 ![Text mit alternativen OpenType] -Symbolen (./media/typography-in-wpf/opentype-stylistic-alternate-glyphs.gif "Text mit alternativen OpenType") -Symbolen  
  
 Schwungschrift besteht aus dekorativen Symbolen, deren reiche Verzierungen häufig mit Kalligraphie assoziiert werden. Im folgenden Text werden Standard- und Schwungsymbole für die Schriftart Pescadero gezeigt.  
  
 ![Text mit OpenType-Standard-und Swash-] Symbolen (./media/typography-in-wpf/opentype-standard-swash-glyphs.gif "Text mit OpenType-Standard-und Swash-") Symbolen  
  
 Weitere Informationen zu [!INCLUDE[TLA2#tla_opentype](../../../../includes/tla2sharptla-opentype-md.md)]-Funktionen finden Sie unter [OpenType-Schriftarteigenschaften](opentype-font-features.md).  
  
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
  
- Separate <xref:System.Windows.FontWeight>Typen <xref:System.Windows.FontStretch>vom Typ <xref:System.Windows.FontStyle> ,<xref:System.Windows.Media.FontFamily>und zum Definieren von. Dies bietet mehr Flexibilität gegenüber der Programmierung in [!INCLUDE[TLA#tla_win32](../../../../includes/tlasharptla-win32-md.md)], bei der boolesche Kombinationen aus Kursiv und Fett zum Definieren einer Schriftfamilie verwendet werden.  
  
- Die Schreibrichtung (horizontal oder vertikal) wird unabhängig von dem Schriftnamen behandelt.  
  
- Verknüpfung von Schriftart und alternativer Schriftart (Fallback) in einer tragbaren [!INCLUDE[TLA#tla_xml](../../../../includes/tlasharptla-xml-md.md)]-Datei mithilfe der Technologie für zusammengesetzte Schriftarten. Zusammengesetzte Schriftarten ermöglichen die Erstellung von vollständigen mehrsprachigen Schriftarten. Zusammengesetzte Schriftarten verfügen zudem über einen Mechanismus, der das Anzeigen fehlender Glyphen verhindert. Weitere Informationen finden Sie in den Hinweisen in der <xref:System.Windows.Media.FontFamily> -Klasse.  
  
- Erstellen internationaler Schriftarten aus zusammengesetzten Schriftarten mithilfe einer Gruppe an Einzelsprachenschriftarten. Dadurch werden Ressourcenkosten bei der Entwicklung von Schriftarten für mehrere Sprachen gespart.  
  
- In einem Dokument eingebettete zusammengesetzte Schriftarten für die Portierung von Dokumenten. Weitere Informationen finden Sie in den Hinweisen in der <xref:System.Windows.Media.FontFamily> -Klasse.  
  
<a name="New_Text_APIs"></a>   
## <a name="new-text-application-programming-interfaces-apis"></a>Standardisierte APIs (Application Programming Interface)  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]stellt verschiedene Text-APIs bereit, die Entwickler verwenden können, wenn Sie Text in Ihre Anwendungen einschließen. Diese APIs sind in drei Kategorien unterteilt:  
  
- **Layout und Benutzeroberfläche**. Die allgemeinen Textsteuerelemente für die [!INCLUDE[TLA#tla_gui](../../../../includes/tlasharptla-gui-md.md)].  
  
- **Einfache Textzeichnung**. Ermöglicht das direkte Zeichnen von Text auf Objekten.  
  
- **Erweiterte Textformatierung**. Ermöglicht Ihnen, eine benutzerdefinierte Text-Engine zu implementieren.  
  
### <a name="layout-and-user-interface"></a>Layout und Benutzeroberfläche  
 Auf der höchsten Ebene der Funktionalität bieten die Text-APIs allgemeine [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] Steuerelemente, <xref:System.Windows.Controls.Label>wie <xref:System.Windows.Controls.TextBlock>z. <xref:System.Windows.Controls.TextBox>b., und. Diese Steuerelemente stellen innerhalb einer Anwendung die grundlegenden [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]-Elemente zur Verfügung und bieten eine einfache Möglichkeit, Text darzustellen und zu bearbeiten. Steuerelemente wie <xref:System.Windows.Controls.RichTextBox> und <xref:System.Windows.Controls.PasswordBox> ermöglichen erweiterte oder spezialisierte Text Behandlung. -Und-Klassen <xref:System.Windows.Documents.TextRange>wie <xref:System.Windows.Documents.TextSelection>, und <xref:System.Windows.Documents.TextPointer> ermöglichen eine hilfreiche Textbearbeitung. Diese [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] Steuerelemente stellen Eigenschaften <xref:System.Windows.Controls.Control.FontFamily%2A>wie, <xref:System.Windows.Controls.Control.FontSize%2A>und <xref:System.Windows.Controls.Control.FontStyle%2A>bereit, mit denen Sie die Schriftart steuern können, die zum Rendering des Texts verwendet wird.  
  
#### <a name="using-bitmap-effects-transforms-and-text-effects"></a>Verwenden von Bitmapeffekten, Transformationen und Texteffekten  
 Mit [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] können Sie visuell interessante Texte mithilfe von Funktionen wie Bitmapeffekten, Transformationen und Texteffekten erstellen. Das folgende Beispiel zeigt einen typischen auf einen Text angewandten Schlagschatteneffekt.  
  
 ![Text Schatten mit Weichheit &#61; 0,25](./media/typography-in-wpf/drop-shadow-text-effect.jpg) 
  
 Das folgende Beispiel zeigt einen Text mit Schlagschatteneffekt und Rauschen.  
  
 ![Textschatten mit Rauschen](./media/typography-in-wpf/drop-shadow-noise-text.jpg) 
  
 Das folgende Beispiel zeigt einen Text mit dem Effekt Schein nach außen (Outer Glow).  
  
 ![Textschatten mit einem OuterGlowBitmapEffect](./media/typography-in-wpf/text-shadow-glow-effect.jpg)
  
 Das folgende Beispiel zeigt einen auf einen Text angewendeten Weichzeichnereffekt.  
  
 ![Textschatten mit einem BlurBitmapEffect](./media/typography-in-wpf/text-shadow-blur-effect.jpg)  

 Das folgende Beispiel zeigt die zweite Textzeile, die um 150 % entlang der X-Achse skaliert ist, und die dritte Textzeile, die um 150 % entlang der Y-Achse skaliert ist.  
  
 ![Skalierter Text mithilfe einer ScaleTransform](./media/typography-in-wpf/scaled-text-scaletransform.jpg) 
  
 Das folgende Beispiel zeigt einen entlang der X-Achse geneigten Text.  
  
 ![Geneigter Text mithilfe einer SkewTransform](./media/typography-in-wpf/skewed-transformed-text.jpg)
  
 Ein <xref:System.Windows.Media.TextEffect> -Objekt ist ein Hilfsobjekt, das es Ihnen ermöglicht, Text als eine oder mehrere Gruppen von Zeichen in einer Text Zeichenfolge zu behandeln. Das folgende Beispiel zeigt ein einzelnes Zeichen, das gedreht wurde. Jedes Zeichen wird unabhängig in Intervallen von 1 Sekunde gedreht.  
  
 ![Bildschirmabbildung des Texteffekts zum Drehen von Text](./media/typography-in-wpf/rotating-text-effect.jpg) 
  
#### <a name="using-flow-documents"></a>Verwenden von Flussdokumenten  
 Zusätzlich zu den allgemeinen [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] Steuer [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Elementen bietet ein Layoutsteuerelement für die Textdarstellung <xref:System.Windows.Documents.FlowDocument> – das-Element. Das <xref:System.Windows.Documents.FlowDocument> -Element stellt in Verbindung mit <xref:System.Windows.Controls.DocumentViewer> dem-Element ein Steuerelement für große Textmengen mit unterschiedlichen Layoutanforderungen bereit. Layoutsteuerelemente ermöglichen den Zugriff auf die <xref:System.Windows.Documents.Typography> erweiterte Typografie durch die Objekt-und Schriftart [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] bezogenen Eigenschaften anderer Steuerelemente.  
  
 Das folgende Beispiel zeigt Text Inhalt, der in <xref:System.Windows.Controls.FlowDocumentReader>einem gehostet wird, der die Unterstützung für die Suche, Navigation, Paginierung und Inhalts Skalierung bereitstellt.  
  
 ![Screenshot mit OpenType-Schriftarten.](./media/typography-in-wpf/typography-text-flowdocumentreader.png)
  
 Weitere Informationen finden Sie unter [Dokumente in WPF](documents-in-wpf.md).  
  
### <a name="lightweight-text-drawing"></a>Einfache Textzeichnung  
 Mithilfe der [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.Media.DrawingContext.DrawText%2A> -Methode des <xref:System.Windows.Media.DrawingContext> -Objekts können Sie Text direkt in-Objekte zeichnen. Um diese Methode zu verwenden, erstellen Sie <xref:System.Windows.Media.FormattedText> ein-Objekt. Dieses Objekt ermöglicht das Zeichnen von mehrzeiligem Text, in dem jedes Zeichen einzeln formatiert werden kann. Die Funktionalität des <xref:System.Windows.Media.FormattedText> -Objekts enthält einen Großteil der Funktionen der DrawText-Flags in der Windows-API. Außerdem enthält das- <xref:System.Windows.Media.FormattedText> Objektfunktionen, wie z. b. die Unterstützung von Auslassungs Zeichen, in der Auslassungs Zeichen angezeigt werden, wenn Text die Begrenzungen überschreitet. Das folgende Beispiel zeigt Text auf den verschiedene Formatierungen angewendet wurden, wie z.B. einen linearen Farbverlauf auf dem zweiten und dritten Wort.  
  
 ![Mit dem FormattedText-Objekt angezeigter Text](./media/typography-in-wpf/text-formatted-linear-gradient.jpg) 
  
 Sie können formatierten Text in <xref:System.Windows.Media.Geometry> -Objekte konvertieren, sodass Sie andere Arten von visuell interessantem Text erstellen können. Beispielsweise können Sie ein <xref:System.Windows.Media.Geometry> -Objekt auf Grundlage der Gliederung einer Text Zeichenfolge erstellen.  
  
 ![Textkontur mit einem linearen Farbverlaufspinsel](./media/typography-in-wpf/text-outline-linear-gradient.jpg)  
  
 Die folgenden Beispiele zeigen verschiedene Möglichkeiten zum Erstellen von visuell interessanten Effekten durch Ändern von Strich, Füllung und Hervorhebung des konvertierten Texts.  
  
 ![Text mit unterschiedlichen Farben für Füllung und Strich](./media/typography-in-wpf/fill-stroke-text-effect.jpg)  
  
 ![Text mit auf Strich angewendeten Bildpinsel](./media/typography-in-wpf/image-brush-application.jpg)
  
 ![Text mit angewendetem Bild Pinsel auf Strich und Hervorhebung](./media/typography-in-wpf/image-brush-text-application.jpg)
  
 Weitere Informationen zum- <xref:System.Windows.Media.FormattedText> Objekt finden Sie unter [Zeichnen von formatiertem Text](drawing-formatted-text.md).  
  
### <a name="advanced-text-formatting"></a>Erweiterte Textformatierung  
 Auf der fortschrittlichsten Ebene der Text [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.Media.TextFormatting> -APIs bietet Ihnen die Möglichkeit, ein benutzerdefiniertes Text Layout zu erstellen, <xref:System.Windows.Media.TextFormatting.TextFormatter> indem Sie das-Objekt und andere Typen im-Namespace verwenden. Die <xref:System.Windows.Media.TextFormatting.TextFormatter> zugeordneten Klassen und ermöglichen Ihnen die Implementierung eines benutzerdefinierten Textlayouts, das Ihre eigene Definition von Zeichenformaten, Absatz Stilen, Zeilenumbruch Regeln und anderen Layoutfunktionen für internationalen Text unterstützt. Es gibt nur sehr wenige Fälle, in denen es sinnvoll ist, die Standardimplementierung der [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-Textlayoutunterstützung zu überschreiben. Wenn Sie jedoch ein Steuerelement oder eine Anwendung erstellen, kann möglicherweise eine andere Implementierung als die standardmäßige [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-Implementierung benötigt werden.  
  
 Im Gegensatz zu einer herkömmlichen Text- <xref:System.Windows.Media.TextFormatting.TextFormatter> API interagiert die mit einem Textlayoutclient über einen Satz von Rückruf Methoden. Der Client muss diese Methoden in einer Implementierung der <xref:System.Windows.Media.TextFormatting.TextSource> -Klasse bereitstellen. Das folgende Diagramm veranschaulicht die Text Layout-Interaktion zwischen der Client Anwendung <xref:System.Windows.Media.TextFormatting.TextFormatter>und.  
  
 ![Diagramm des Textlayout-Clients und TextFormatter](./media/typography-in-wpf/text-layout-text-formatter-interaction.png)  
  
 Weitere Informationen zum Erstellen von benutzerdefinierten Textlayouts finden Sie unter [Advanced Text Formatting](advanced-text-formatting.md).  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Windows.Media.FormattedText>
- <xref:System.Windows.Media.TextFormatting.TextFormatter>
- [Übersicht über ClearType](cleartype-overview.md)
- [Features für OpenType-Schriftarten](opentype-font-features.md)
- [Zeichnen von formatiertem Text](drawing-formatted-text.md)
- [Erweiterte Textformatierung](advanced-text-formatting.md)
- [Text](optimizing-performance-text.md)
- [Microsoft-Typografie](https://docs.microsoft.com/typography/)
