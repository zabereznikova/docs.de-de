---
title: Typografie in WPF
ms.date: 03/30/2017
helpviewer_keywords:
- typography [WPF], about typography
ms.assetid: 06cbf17b-6eff-4fe5-949d-2dd533e4e1f4
ms.openlocfilehash: 0ba4e8ff639cdfbbec596da45a6e950fff921974
ms.sourcegitcommit: 22be09204266253d45ece46f51cc6f080f2b3fd6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/07/2019
ms.locfileid: "73740722"
---
# <a name="typography-in-wpf"></a>Typografie in WPF
In diesem Thema werden die wichtigsten typografischen Funktionen von [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] vorgestellt. Zu diesen Features gehören verbesserte Qualität und Leistung von Text Rendering, Unterstützung von OpenType-typografiken, erweiterter internationaler Text, verbesserte Schriftart Unterstützung und neue Text-Anwendungs Programmierschnittstellen (APIs).  
  
<a name="Improved_Quality_and_Performance_of_Text"></a>   
## <a name="improved-quality-and-performance-of-text"></a>Verbesserte Textqualität und -leistung  
 Text in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] wird mithilfe von Microsoft ClearType gerendert, wodurch die Übersichtlichkeit und Lesbarkeit von Text verbessert wird. ClearType ist eine von Microsoft entwickelte Softwaretechnologie, mit der die Lesbarkeit von Text auf vorhandenen LCDs (Liquid Crystal Displays), wie z. b. Laptop Bildschirmen, Pocket PC-Bildschirme und Flatpanel-Monitoren, verbessert wird. ClearType verwendet das Subpixel-Rendering, das es ermöglicht, Text mit einer größeren Genauigkeit als echte Form anzuzeigen, indem Zeichen an einem Bruchteil eines Pixels ausgerichtet werden. Die zusätzliche Auflösung verbessert die Schärfe der kleinen Details in der Textanzeige, was das Lesen über lange Zeiträume hinweg erleichtert. Eine weitere Verbesserung von ClearType in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] ist das Antialiasing in y-Richtung, das die Ober-und Unterstriche von flachen Kurven in Textzeichen glättet. Weitere Informationen zu ClearType-Features finden Sie unter [Übersicht über ClearType](cleartype-overview.md).  
  
 ![Text mit ClearType-Y-Richtung-Antialiasing](./media/typography-in-wpf/text-y-direction-antialiasing.gif)  
Text mit ClearType-Antialiasing in y-Richtung  
  
 Die gesamte Textrendering-Pipeline kann in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] hardwarebeschleunigt erfolgen, vorausgesetzt, dass Ihr Computer die Mindestanforderungen an die Hardware erfüllt. Rendering, das nicht mit der Hardware ausgeführt werden kann, wird als Softwarerendering ausgeführt. Die Hardware Beschleunigung wirkt sich auf alle Phasen der Textrenderingpipeline aus – von der Speicherung einzelner Symbole, der Komposition von Symbolen in Glyphe, dem Anwenden von Effekten bis zum Anwenden des ClearType-Mischungs Algorithmus auf die endgültige angezeigte Ausgabe. Weitere Informationen zur Hardware-Beschleunigung finden Sie unter [Renderingebenen für Grafiken](graphics-rendering-tiers.md).  
  
 ![Diagramm der Text-Rendering-Pipeline](./media/typography-in-wpf/text-rendering-pipeline.png)  
  
 Darüber hinaus nutzen Textanimation die durch [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] aktivierten Vorteile der Grafikhardwarefunktion mit Zeichen oder Glyphen voll aus. Das Ergebnis ist eine glatte Textanimation.  
  
<a name="Rich_Typography"></a>   
## <a name="rich-typography"></a>Umfangreiche Typografie  
 Das OpenType-Schriftformat ist eine Erweiterung des TrueType-® Schriftart Formats. Das OpenType-Schriftformat wurde von Microsoft und Adobe gemeinsam entwickelt und bietet eine umfangreiche Palette an erweiterten typografischen Features. Das <xref:System.Windows.Documents.Typography>-Objekt macht viele erweiterte Funktionen von OpenType-Schriftarten verfügbar, wie z. b. Stilvarianten und Swashes. Der Windows SDK bietet eine Reihe von OpenType-Beispiel Schriftarten, die mit umfangreichen Funktionen wie den Schriftarten "Pericles" und "Pescadero" entworfen wurden. Weitere Informationen finden Sie unter [OpenType-Beispielschriftartenpaket](sample-opentype-font-pack.md).  
  
 Die Schriftart "Pericles OpenType" enthält zusätzliche Symbole, die eine stilistische Alternative zum Standardsatz von Symbolen bereitstellen. Im folgenden Text werden Symbole im alternativen Stil gezeigt.  
  
 ![Text mit alternativen OpenType-Stilsymbolen](./media/typography-in-wpf/opentype-stylistic-alternate-glyphs.gif "Text mit alternativen OpenType-Stilsymbolen")  
  
 Schwungschrift besteht aus dekorativen Symbolen, deren reiche Verzierungen häufig mit Kalligraphie assoziiert werden. Im folgenden Text werden Standard- und Schwungsymbole für die Schriftart Pescadero gezeigt.  
  
 ![Text mit OpenType-Standard- und Ziersymbolen](./media/typography-in-wpf/opentype-standard-swash-glyphs.gif "Text mit OpenType-Standard- und Ziersymbolen")  
  
 Weitere Informationen zu OpenType-Funktionen finden Sie unter [OpenType-Schriftart Features](opentype-font-features.md).  
  
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
  
- Trennen Sie die Typen <xref:System.Windows.FontWeight>, <xref:System.Windows.FontStretch>und <xref:System.Windows.FontStyle> zum Definieren eines <xref:System.Windows.Media.FontFamily>. Dies bietet mehr Flexibilität gegenüber der Programmierung in [!INCLUDE[TLA#tla_win32](../../../../includes/tlasharptla-win32-md.md)], bei der boolesche Kombinationen aus Kursiv und Fett zum Definieren einer Schriftfamilie verwendet werden.  
  
- Die Schreibrichtung (horizontal oder vertikal) wird unabhängig von dem Schriftnamen behandelt.  
  
- Schriftart Verknüpfungen und Schriftart Fall Back in einer portablen XML-Datei mit zusammengesetzter Schriftart Technologie. Zusammengesetzte Schriftarten ermöglichen die Erstellung von vollständigen mehrsprachigen Schriftarten. Zusammengesetzte Schriftarten verfügen zudem über einen Mechanismus, der das Anzeigen fehlender Glyphen verhindert. Weitere Informationen finden Sie in den Hinweisen in der <xref:System.Windows.Media.FontFamily>-Klasse.  
  
- Erstellen internationaler Schriftarten aus zusammengesetzten Schriftarten mithilfe einer Gruppe an Einzelsprachenschriftarten. Dadurch werden Ressourcenkosten bei der Entwicklung von Schriftarten für mehrere Sprachen gespart.  
  
- In einem Dokument eingebettete zusammengesetzte Schriftarten für die Portierung von Dokumenten. Weitere Informationen finden Sie in den Hinweisen in der <xref:System.Windows.Media.FontFamily>-Klasse.  
  
<a name="New_Text_APIs"></a>   
## <a name="new-text-application-programming-interfaces-apis"></a>Standardisierte APIs (Application Programming Interface)  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] stellt mehrere Text-APIs bereit, die Entwickler verwenden können, wenn Sie Text in Ihre Anwendungen einschließen. Diese APIs sind in drei Kategorien unterteilt:  
  
- **Layout und Benutzeroberfläche**. Die allgemeinen Text Steuerelemente für die grafische Benutzeroberfläche (GUI).  
  
- **Einfache Textzeichnung**. Ermöglicht das direkte Zeichnen von Text auf Objekten.  
  
- **Erweiterte Textformatierung**. Ermöglicht Ihnen, eine benutzerdefinierte Text-Engine zu implementieren.  
  
### <a name="layout-and-user-interface"></a>Layout und Benutzeroberfläche  
 Auf der höchsten Ebene der Funktionalität bieten die Text-APIs allgemeine [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] Steuerelemente, z. b. <xref:System.Windows.Controls.Label>, <xref:System.Windows.Controls.TextBlock>und <xref:System.Windows.Controls.TextBox>. Diese Steuerelemente stellen innerhalb einer Anwendung die grundlegenden [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]-Elemente zur Verfügung und bieten eine einfache Möglichkeit, Text darzustellen und zu bearbeiten. Steuerelemente wie <xref:System.Windows.Controls.RichTextBox> und <xref:System.Windows.Controls.PasswordBox> ermöglichen erweiterte oder spezialisierte Text Behandlung. Klassen wie <xref:System.Windows.Documents.TextRange>, <xref:System.Windows.Documents.TextSelection>und <xref:System.Windows.Documents.TextPointer> ermöglichen eine sinnvolle Textbearbeitung. Diese [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] Steuerelemente bieten Eigenschaften wie <xref:System.Windows.Controls.Control.FontFamily%2A>, <xref:System.Windows.Controls.Control.FontSize%2A>und <xref:System.Windows.Controls.Control.FontStyle%2A>, mit denen Sie die Schriftart steuern können, die zum Rendering des Texts verwendet wird.  
  
#### <a name="using-bitmap-effects-transforms-and-text-effects"></a>Verwenden von Bitmapeffekten, Transformationen und Texteffekten  
 Mit [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] können Sie visuell interessante Texte mithilfe von Funktionen wie Bitmapeffekten, Transformationen und Texteffekten erstellen. Das folgende Beispiel zeigt einen typischen auf einen Text angewandten Schlagschatteneffekt.  
  
 ![Text Schatten mit Weichheit &#61; 0,25](./media/typography-in-wpf/drop-shadow-text-effect.jpg) 
  
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
  
 Ein <xref:System.Windows.Media.TextEffect>-Objekt ist ein Hilfsobjekt, das es Ihnen ermöglicht, Text als eine oder mehrere Gruppen von Zeichen in einer Text Zeichenfolge zu behandeln. Das folgende Beispiel zeigt ein einzelnes Zeichen, das gedreht wurde. Jedes Zeichen wird unabhängig in Intervallen von 1 Sekunde gedreht.  
  
 ![Bildschirmabbildung des Texteffekts zum Drehen von Text](./media/typography-in-wpf/rotating-text-effect.jpg) 
  
#### <a name="using-flow-documents"></a>Verwenden von Flussdokumenten  
 Zusätzlich zu den allgemeinen [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]-Steuerelementen bietet [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] ein Layoutsteuerelement für die Textdarstellung – das <xref:System.Windows.Documents.FlowDocument>-Element. Das <xref:System.Windows.Documents.FlowDocument>-Element stellt in Verbindung mit dem <xref:System.Windows.Controls.DocumentViewer>-Element ein Steuerelement für große Textmengen mit unterschiedlichen Layoutanforderungen bereit. Layoutsteuerelemente ermöglichen den Zugriff auf die erweiterte Typographie über das <xref:System.Windows.Documents.Typography> Objekt und die Schriftart bezogenen Eigenschaften anderer [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]-Steuerelemente.  
  
 Das folgende Beispiel zeigt Text Inhalt, der in einem <xref:System.Windows.Controls.FlowDocumentReader>gehostet wird, der die Unterstützung für die Suche, Navigation, Paginierung und Inhalts Skalierung bereitstellt.  
  
 ![Screenshot mit OpenType-Schriftarten.](./media/typography-in-wpf/typography-text-flowdocumentreader.png)
  
 Weitere Informationen finden Sie unter [Dokumente in WPF](documents-in-wpf.md).  
  
### <a name="lightweight-text-drawing"></a>Einfache Textzeichnung  
 Mit der <xref:System.Windows.Media.DrawingContext.DrawText%2A>-Methode des <xref:System.Windows.Media.DrawingContext>-Objekts können Sie Text direkt in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-Objekten zeichnen. Um diese Methode zu verwenden, erstellen Sie ein <xref:System.Windows.Media.FormattedText>-Objekt. Dieses Objekt ermöglicht das Zeichnen von mehrzeiligem Text, in dem jedes Zeichen einzeln formatiert werden kann. Die Funktionalität des <xref:System.Windows.Media.FormattedText> Objekts enthält einen Großteil der Funktionen der DrawText-Flags in der Windows-API. Außerdem enthält das <xref:System.Windows.Media.FormattedText> Objektfunktionen wie z. b. die Unterstützung von Auslassungs Zeichen, in denen eine Auslassungs Zeichen angezeigt werden, wenn Text die Begrenzungen überschreitet. Das folgende Beispiel zeigt Text auf den verschiedene Formatierungen angewendet wurden, wie z.B. einen linearen Farbverlauf auf dem zweiten und dritten Wort.  
  
 ![Mit dem FormattedText-Objekt angezeigter Text](./media/typography-in-wpf/text-formatted-linear-gradient.jpg) 
  
 Sie können formatierten Text in <xref:System.Windows.Media.Geometry> Objekte konvertieren, sodass Sie andere Arten von visuell interessantem Text erstellen können. Beispielsweise können Sie ein <xref:System.Windows.Media.Geometry>-Objekt auf Grundlage der Gliederung einer Text Zeichenfolge erstellen.  
  
 ![Textkontur mit einem linearen Farbverlaufspinsel](./media/typography-in-wpf/text-outline-linear-gradient.jpg)  
  
 Die folgenden Beispiele zeigen verschiedene Möglichkeiten zum Erstellen von visuell interessanten Effekten durch Ändern von Strich, Füllung und Hervorhebung des konvertierten Texts.  
  
 ![Text mit unterschiedlichen Farben für Füllung und Strich](./media/typography-in-wpf/fill-stroke-text-effect.jpg)  
  
 ![Text mit auf Strich angewendeten Bildpinsel](./media/typography-in-wpf/image-brush-application.jpg)
  
 ![Text mit angewendetem Bild Pinsel auf Strich und Hervorhebung](./media/typography-in-wpf/image-brush-text-application.jpg)
  
 Weitere Informationen zum <xref:System.Windows.Media.FormattedText>-Objekt finden Sie unter [Zeichnen von formatiertem Text](drawing-formatted-text.md).  
  
### <a name="advanced-text-formatting"></a>Erweiterte Textformatierung  
 Auf der fortschrittlichsten Ebene der Text-APIs bietet [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Ihnen die Möglichkeit, ein benutzerdefiniertes Text Layout zu erstellen, indem Sie das <xref:System.Windows.Media.TextFormatting.TextFormatter>-Objekt und andere Typen im <xref:System.Windows.Media.TextFormatting>-Namespace verwenden. Mit dem <xref:System.Windows.Media.TextFormatting.TextFormatter> und den zugehörigen Klassen können Sie ein benutzerdefiniertes Text Layout implementieren, das Ihre eigene Definition von Zeichenformaten, Absatz Stilen, Zeilenumbruch Regeln und anderen Layoutfunktionen für internationalen Text unterstützt. Es gibt nur sehr wenige Fälle, in denen es sinnvoll ist, die Standardimplementierung der [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-Textlayoutunterstützung zu überschreiben. Wenn Sie jedoch ein Steuerelement oder eine Anwendung erstellen, kann möglicherweise eine andere Implementierung als die standardmäßige [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-Implementierung benötigt werden.  
  
 Im Gegensatz zu einer herkömmlichen Text-API interagiert der <xref:System.Windows.Media.TextFormatting.TextFormatter> mithilfe eines Satzes von Rückruf Methoden mit einem Textlayoutclient. Der Client muss diese Methoden in einer Implementierung der <xref:System.Windows.Media.TextFormatting.TextSource>-Klasse bereitstellen. Das folgende Diagramm veranschaulicht die Text Layout-Interaktion zwischen der Client Anwendung und <xref:System.Windows.Media.TextFormatting.TextFormatter>.  
  
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
