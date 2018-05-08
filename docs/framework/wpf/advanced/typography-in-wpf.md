---
title: Typografie in WPF
ms.date: 03/30/2017
helpviewer_keywords:
- typography [WPF], about typography
ms.assetid: 06cbf17b-6eff-4fe5-949d-2dd533e4e1f4
ms.openlocfilehash: 45f74a4dd2164f332314ad79a18eab49efb520d6
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="typography-in-wpf"></a>Typografie in WPF
In diesem Thema werden die wichtigsten typografischen Funktionen von [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] vorgestellt. Diese Funktionen umfassen die verbesserte Qualität und Leistung beim Textrendering, die Unterstützung von [!INCLUDE[TLA#tla_opentype](../../../../includes/tlasharptla-opentype-md.md)]-Typografie, einen verbesserten internationalen Text, eine verbesserte Unterstützung für Schriftarten sowie neue Text-Anwendungsprogrammierschnittstellen (APIs).  
  

  
<a name="Improved_Quality_and_Performance_of_Text"></a>   
## <a name="improved-quality-and-performance-of-text"></a>Verbesserte Textqualität und -leistung  
 Text in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] wird mit [!INCLUDE[TLA#tla_ct](../../../../includes/tlasharptla-ct-md.md)] gerendert , was die Übersichtlichkeit und Lesbarkeit von Text verbessert. [!INCLUDE[TLA2#tla_ct](../../../../includes/tla2sharptla-ct-md.md)] ist eine von [!INCLUDE[TLA#tla_ms](../../../../includes/tlasharptla-ms-md.md)] entwickelte Softwaretechnologie, mit der die Lesbarkeit von Text auf vorhandenen LCDs (Liquid Crystal Displays), z.B. auf Laptopbildschirmen, Pocket PC-Bildschirmen und Flachbildschirmen, optimiert wird. [!INCLUDE[TLA2#tla_ct](../../../../includes/tla2sharptla-ct-md.md)] verwendet Sub-Pixel-Rendering, das durch das Ausrichten von Zeichen an Bruchteilen eines Pixels eine Textdarstellung mit größerer Genauigkeit und Wiedergabetreue ermöglicht. Die zusätzliche Auflösung verbessert die Schärfe der kleinen Details in der Textanzeige, was das Lesen über lange Zeiträume hinweg erleichtert. Eine weitere Verbesserung von [!INCLUDE[TLA2#tla_ct](../../../../includes/tla2sharptla-ct-md.md)] in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] ist das Antialiasing in y-Richtung, das flache Kurven von Textzeichen oben und unten glättet. Weitere Informationen zu [!INCLUDE[TLA2#tla_ct](../../../../includes/tla2sharptla-ct-md.md)]-Funktionen finden Sie unter [Übersicht über ClearType](../../../../docs/framework/wpf/advanced/cleartype-overview.md).  
  
 ![Text mit ClearType-y&#45;Richtung anti-&#45;Aliasing](../../../../docs/framework/wpf/advanced/media/typographyinwpf02.gif "TypographyInWPF02")  
Text mit ClearType-Antialiasing auf der y-Achse  
  
 Die gesamte Textrendering-Pipeline kann in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] hardwarebeschleunigt erfolgen, vorausgesetzt, dass Ihr Computer die Mindestanforderungen an die Hardware erfüllt. Rendering, das nicht mit der Hardware ausgeführt werden kann, wird als Softwarerendering ausgeführt. Die Hardwarebeschleunigung beeinflusst alle Phasen der Textrendering-Pipeline – vom Speichern einzelner Glyphen, über die Zusammensetzung von Glyphenreihen und das Anwenden von Effekten bis hin zum Anwenden des [!INCLUDE[TLA2#tla_ct](../../../../includes/tla2sharptla-ct-md.md)]-Blendingalgorithmus auf die angezeigte Endausgabe. Weitere Informationen zur Hardware-Beschleunigung finden Sie unter [Renderingebenen für Grafiken](../../../../docs/framework/wpf/advanced/graphics-rendering-tiers.md).  
  
 ![Diagramm der Text-Rendering-Pipeline](../../../../docs/framework/wpf/advanced/media/typographyinwpf01.png "TypographyInWPF01")  
Diagramm der Text-Rendering-Pipeline  
  
 Darüber hinaus nutzen Textanimation die durch [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] aktivierten Vorteile der Grafikhardwarefunktion mit Zeichen oder Glyphen voll aus. Das Ergebnis ist eine glatte Textanimation.  
  
<a name="Rich_Typography"></a>   
## <a name="rich-typography"></a>Umfangreiche Typografie  
 Das [!INCLUDE[TLA2#tla_opentype](../../../../includes/tla2sharptla-opentype-md.md)]-Schriftartformat ist eine Erweiterung des [!INCLUDE[TLA#tla_truetype](../../../../includes/tlasharptla-truetype-md.md)]-Schriftartformats. Das [!INCLUDE[TLA2#tla_opentype](../../../../includes/tla2sharptla-opentype-md.md)]-Schriftartformat wurde gemeinsam von [!INCLUDE[TLA#tla_ms](../../../../includes/tlasharptla-ms-md.md)] und Adobe entwickelt und bietet eine umfangreiche Auswahl an erweiterten typografischen Funktionen. Die <xref:System.Windows.Documents.Typography> Objekt macht viele der erweiterten Funktionen von [!INCLUDE[TLA2#tla_opentype](../../../../includes/tla2sharptla-opentype-md.md)] Schriftarten, z. B. stilistischer Varianten und Schwungschrift. Das [!INCLUDE[TLA2#tla_lhsdk](../../../../includes/tla2sharptla-lhsdk-md.md)] bietet eine Reihe von [!INCLUDE[TLA2#tla_opentype](../../../../includes/tla2sharptla-opentype-md.md)]-Schriftarten, die umfassende Funktionen enthalten,wie z.B. die Schriftarten Pericles und Pescadero. Weitere Informationen finden Sie unter [OpenType-Beispielschriftartenpaket](../../../../docs/framework/wpf/advanced/sample-opentype-font-pack.md).  
  
 Die [!INCLUDE[TLA2#tla_opentype](../../../../includes/tla2sharptla-opentype-md.md)]-Schriftart Pericles enthält zusätzliche Glyphen, die alternative Stile für den Standardsatz von Glyphen bieten. Im folgenden Text werden Symbole im alternativen Stil gezeigt.  
  
 ![Text mit alternativen OpenType-Stilsymbolen](../../../../docs/framework/wpf/advanced/media/opentypefont02.gif "opentypefont02")  
Text mit alternativen OpenType-Stilsymbolen  
  
 Schwungschrift besteht aus dekorativen Symbolen, deren ausgefeilte Verzierung häufig mit Kalligraphie assoziiert wird. Im folgenden Text werden Standard- und Schwungsymbole für die Schriftart Pescadero gezeigt.  
  
 ![Text mit OpenType-Standard- und Ziersymbolen](../../../../docs/framework/wpf/advanced/media/opentypefont08.gif "opentypefont08")  
Text mit OpenType-Standard- und Ziersymbolen  
  
 Weitere Informationen zu [!INCLUDE[TLA2#tla_opentype](../../../../includes/tla2sharptla-opentype-md.md)]-Funktionen finden Sie unter [OpenType-Schriftarteigenschaften](../../../../docs/framework/wpf/advanced/opentype-font-features.md).  
  
<a name="Enhanced_International_Text_Support"></a>   
## <a name="enhanced-international-text-support"></a>Verbesserte Unterstützung für internationalen Text  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] bietet durch die folgenden Funktionen eine verbesserte Unterstützung für internationalen Text:  
  
-   Automatischer Zeilenabstand in allen Schriftsystem mithilfe adaptiver Maßeinheiten.  
  
-   Umfassende Unterstützung für internationalen Text. Weitere Informationen finden Sie unter [Globalisierung für WPF](../../../../docs/framework/wpf/advanced/globalization-for-wpf.md).  
  
-   An der Sprache orientierter Zeilenumbruch, Silbentrennung und Ausrichtung.  
  
<a name="Enhanced_Font_Support"></a>   
## <a name="enhanced-font-support"></a>Verbesserte Unterstützung für Schriftarten  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] bietet durch die folgenden Funktionen eine verbesserte Unterstützung für Schriftarten:  
  
-   Unicode für den jeden Text. Für Schriftartverhalten und -auswahl wird Charset oder Codepage nicht mehr benötigt.  
  
-   Von globalen Einstellungen unabhängige Schriftartverhalten, z.B. Systemgebietsschema.  
  
-   Separate <xref:System.Windows.FontWeight>, <xref:System.Windows.FontStretch>, und <xref:System.Windows.FontStyle> Typen zum Definieren einer <xref:System.Windows.Media.FontFamily>. Dies bietet mehr Flexibilität gegenüber der Programmierung in [!INCLUDE[TLA#tla_win32](../../../../includes/tlasharptla-win32-md.md)], bei der boolesche Kombinationen aus Kursiv und Fett zum Definieren einer Schriftfamilie verwendet werden.  
  
-   Die Schreibrichtung (horizontal oder vertikal) wird unabhängig von dem Schriftnamen behandelt.  
  
-   Verknüpfung von Schriftart und alternativer Schriftart (Fallback) in einer tragbaren [!INCLUDE[TLA#tla_xml](../../../../includes/tlasharptla-xml-md.md)]-Datei mithilfe der Technologie für zusammengesetzte Schriftarten. Zusammengesetzte Schriftarten ermöglichen die Erstellung von vollständigen mehrsprachigen Schriftarten. Zusammengesetzte Schriftarten verfügen zudem über einen Mechanismus, der das Anzeigen fehlender Glyphen verhindert. Weitere Informationen finden Sie unter den Hinweisen in der <xref:System.Windows.Media.FontFamily> Klasse.  
  
-   Erstellen internationaler Schriftarten aus zusammengesetzten Schriftarten mithilfe einer Gruppe an Einzelsprachenschriftarten. Dadurch werden Ressourcenkosten bei der Entwicklung von Schriftarten für mehrere Sprachen gespart.  
  
-   In einem Dokument eingebettete zusammengesetzte Schriftarten für die Portierung von Dokumenten. Weitere Informationen finden Sie unter den Hinweisen in der <xref:System.Windows.Media.FontFamily> Klasse.  
  
<a name="New_Text_APIs"></a>   
## <a name="new-text-application-programming-interfaces-apis"></a>Standardisierte APIs (Application Programming Interface)  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] bietet Entwicklern mehrere Text-[!INCLUDE[TLA2#tla_api#plural](../../../../includes/tla2sharptla-apisharpplural-md.md)] für zum Einfügen in ihre Anwendungen. Diese [!INCLUDE[TLA2#tla_api#plural](../../../../includes/tla2sharptla-apisharpplural-md.md)] werden in drei Kategorien unterteilt:  
  
-   **Layout und Benutzeroberfläche**. Die allgemeinen Textsteuerelemente für die [!INCLUDE[TLA#tla_gui](../../../../includes/tlasharptla-gui-md.md)].  
  
-   **Einfache Textzeichnung**. Ermöglicht das direkte Zeichnen von Text auf Objekten.  
  
-   **Erweiterte Textformatierung**. Ermöglicht Ihnen, ein benutzerdefiniertes Textmodul zu implementieren.  
  
### <a name="layout-and-user-interface"></a>Layout und Benutzeroberfläche  
 Auf der höchsten Ebene von Funktionen, die Text [!INCLUDE[TLA2#tla_api#plural](../../../../includes/tla2sharptla-apisharpplural-md.md)] bieten allgemeine [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] Steuerelemente wie z. B. <xref:System.Windows.Controls.Label>, <xref:System.Windows.Controls.TextBlock>, und <xref:System.Windows.Controls.TextBox>. Diese Steuerelemente stellen innerhalb einer Anwendung die grundlegenden [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]-Elemente zur Verfügung und bieten eine einfache Möglichkeit, Text darzustellen und zu bearbeiten. Steuert, wie z. B. <xref:System.Windows.Controls.RichTextBox> und <xref:System.Windows.Controls.PasswordBox> aktivieren mehr erweiterte oder Textbehandlung spezialisiert. Klassen wie <xref:System.Windows.Documents.TextRange>, <xref:System.Windows.Documents.TextSelection>, und <xref:System.Windows.Documents.TextPointer> nützlich zur textmanipulation zu aktivieren. Diese [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] Steuerelemente stellen Eigenschaften bereit, z. B. <xref:System.Windows.Controls.Control.FontFamily%2A>, <xref:System.Windows.Controls.Control.FontSize%2A>, und <xref:System.Windows.Controls.Control.FontStyle%2A>, die ermöglichen es Ihnen, die Schriftart zu steuern, die zum Rendern von Text verwendet wird.  
  
#### <a name="using-bitmap-effects-transforms-and-text-effects"></a>Verwenden von Bitmapeffekten, Transformationen und Texteffekten  
 Mit [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] können Sie visuell interessante Texte mithilfe von Funktionen wie Bitmapeffekten, Transformationen und Texteffekten erstellen. Das folgende Beispiel zeigt einen typischen auf einen Text angewandten Schlagschatteneffekt.  
  
 ![Textschatten mit Weichheit &#61; 0,25](../../../../docs/framework/wpf/advanced/media/shadowtext01.jpg "ShadowText01")  
Text mit einem Schlagschatten  
  
 Das folgende Beispiel zeigt einen Text mit Schlagschatteneffekt und Rauschen.  
  
 ![Textschatten mit Rauschen](../../../../docs/framework/wpf/advanced/media/shadowtext04.jpg "ShadowText04")  
Text mit Schlagschatten und Rauschen  
  
 Das folgende Beispiel zeigt einen Text mit dem Effekt Schein nach außen (Outer Glow).  
  
 ![Textschatten mit einem OuterGlowBitmapEffect](../../../../docs/framework/wpf/advanced/media/shadowtext05.jpg "ShadowText05")  
Text mit dem Effekt Schein nach außen  
  
 Das folgende Beispiel zeigt einen auf einen Text angewendeten Weichzeichnereffekt.  
  
 ![Textschatten mit einem BlurBitmapEffect](../../../../docs/framework/wpf/advanced/media/shadowtext06.jpg "ShadowText06")  
Text mit einem Weichzeichnereffekt  
  
 Das folgende Beispiel zeigt die zweite Textzeile, die um 150 % entlang der X-Achse skaliert ist, und die dritte Textzeile, die um 150 % entlang der Y-Achse skaliert ist.  
  
 ![Text mithilfe einer ScaleTransform](../../../../docs/framework/wpf/advanced/media/transformedtext02.jpg "TransformedText02")  
Mithilfe einer ScaleTransform skalierter Text  
  
 Das folgende Beispiel zeigt einen entlang der X-Achse geneigten Text.  
  
 ![Geneigter Text mithilfe einer SkewTransform](../../../../docs/framework/wpf/advanced/media/transformedtext03.jpg "TransformedText03")  
Geneigter Text mithilfe einer SkewTransform  
  
 Ein <xref:System.Windows.Media.TextEffect> Objekt ist Hilfsobjekt, das Ihnen ermöglicht, die Text als eine oder mehrere Gruppen von Zeichen in einer Textzeichenfolge zu behandeln. Das folgende Beispiel zeigt ein einzelnes Zeichen, das gedreht wurde. Jedes Zeichen wird unabhängig in Intervallen von 1 Sekunde gedreht.  
  
 ![Bildschirmabbildung des Texteffekts zum Drehen von Text](../../../../docs/framework/wpf/advanced/media/texteffect01.jpg "TextEffect01")  
Beispiel für eine sich drehende Texteffektanimation  
  
#### <a name="using-flow-documents"></a>Verwenden von Flussdokumenten  
 Zusätzlich zu den allgemeinen [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] Steuerelemente [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] bietet eine Layout-Steuerelement für die Textdarstellung – der <xref:System.Windows.Documents.FlowDocument> Element. Die <xref:System.Windows.Documents.FlowDocument> Elements in Verbindung mit der <xref:System.Windows.Controls.DocumentViewer> Element stellt ein Steuerelement für große Mengen von Text mit unterschiedlichen Layout Anforderungen bereit. Formularlayout-Steuerelemente bieten Zugriff auf erweiterte Typografie durch die <xref:System.Windows.Documents.Typography> Objekt und Eigenschaften anderer schriftartbezogene [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] Steuerelemente.  
  
 Das folgende Beispiel zeigt den Textinhalt in gehosteten eine <xref:System.Windows.Controls.FlowDocumentReader>, Suche, Navigation, Paginierung und Inhalte, die Unterstützung für die Skalierung bietet.  
  
 ![Mit OpenType-Schriftarten Beispiel Screenshot](../../../../docs/framework/wpf/advanced/media/typographyinwpf-03.png "TypographyInWPF_03")  
In einem FlowDocumentReader gehosteter Text  
  
 Weitere Informationen finden Sie unter [Dokumente in WPF](../../../../docs/framework/wpf/advanced/documents-in-wpf.md).  
  
### <a name="lightweight-text-drawing"></a>Einfache Textzeichnung  
 Sie können Text direkt zu zeichnen [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Objekte mithilfe der <xref:System.Windows.Media.DrawingContext.DrawText%2A> Methode der <xref:System.Windows.Media.DrawingContext> Objekt. Wenn diese Methode verwenden möchten, erstellen Sie eine <xref:System.Windows.Media.FormattedText> Objekt. Dieses Objekt ermöglicht das Zeichnen von mehrzeiligem Text, in dem jedes Zeichen einzeln formatiert werden kann. Die Funktionalität der <xref:System.Windows.Media.FormattedText> Objekt enthält viele Funktionen der DrawText-Flags in der Win32-API. Darüber hinaus die <xref:System.Windows.Media.FormattedText> Objekt enthält Funktionen, z. B. mit den Auslassungspunkten-Unterstützung, in dem ein Auslassungszeichen angezeigt wird, wenn Text seiner Grenzen überschreitet. Das folgende Beispiel zeigt Text auf den verschiedene Formatierungen angewendet wurden, wie z.B. einen linearen Farbverlauf auf dem zweiten und dritten Wort.  
  
 ![Mit dem FormattedText-Objekt angezeigter Text](../../../../docs/framework/wpf/advanced/media/formattedtext01.jpg "FormattedText01")  
Mit dem FormattedText-Objekt angezeigter Text  
  
 Sie können auch formatierten Text in konvertieren <xref:System.Windows.Media.Geometry> Objekte, sodass Sie andere Arten von visuell interessante Text zu erstellen. Sie können z. B. Erstellen einer <xref:System.Windows.Media.Geometry> Objekt auf Grundlage der Gliederung einer Textzeichenfolge.  
  
 ![Textkontur mit einem linearen Farbverlaufspinsel](../../../../docs/framework/wpf/advanced/media/outlinedtext02.jpg "OutlinedText02")  
Textkontur mit einem linearen Farbverlaufspinsel  
  
 Die folgenden Beispiele zeigen verschiedene Möglichkeiten zum Erstellen von visuell interessanten Effekten durch Ändern von Strich, Füllung und Hervorhebung des konvertierten Texts.  
  
 ![Text mit unterschiedlichen Farben für Füllung und Strich](../../../../docs/framework/wpf/advanced/media/outlinedtext03.jpg "OutlinedText03")  
Beispiel für das Festlegen von unterschiedlichen Farben für Strich und Füllung  
  
 ![Text mit auf Strich angewendeten Bildpinsel](../../../../docs/framework/wpf/advanced/media/outlinedtext04.jpg "OutlinedText04")  
Beispiel für die Anwendung eines Bildpinsels auf den Strich  
  
 ![Text mit auf Strich angewendeten Bildpinsel](../../../../docs/framework/wpf/advanced/media/outlinedtext05.jpg "OutlinedText05")  
Beispiel für die Anwendung eines Bildpinsels auf den Strich und die Hervorhebung  
  
 Weitere Informationen zu den <xref:System.Windows.Media.FormattedText> Objekt, finden Sie unter [Zeichnung formatiertem Text](../../../../docs/framework/wpf/advanced/drawing-formatted-text.md).  
  
### <a name="advanced-text-formatting"></a>Erweiterte Textformatierung  
 Das am häufigsten Premiummitglied des Texts [!INCLUDE[TLA2#tla_api#plural](../../../../includes/tla2sharptla-apisharpplural-md.md)], [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] bietet die Möglichkeit zum Erstellen von benutzerdefinierten Textlayout mit der <xref:System.Windows.Media.TextFormatting.TextFormatter> Objekt und anderen Typen in den <xref:System.Windows.Media.TextFormatting> Namespace. Die <xref:System.Windows.Media.TextFormatting.TextFormatter> und die zugeordneten Klassen können Sie benutzerdefinierte Textlayout implementieren, die Ihre eigenen Definitionen für Zeichenformate, Absatzformatvorlagen, unterstützt Zeile Regeln für den Zeilenumbruch und andere Layoutfeatures für internationalen Text. Es gibt nur sehr wenige Fälle, in denen es sinnvoll ist, die Standardimplementierung der [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-Textlayoutunterstützung zu überschreiben. Wenn Sie jedoch ein Steuerelement oder eine Anwendung erstellen, kann möglicherweise eine andere Implementierung als die standardmäßige [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-Implementierung benötigt werden.  
  
 Im Gegensatz zu herkömmlichen Text [!INCLUDE[TLA#tla_api](../../../../includes/tlasharptla-api-md.md)]die <xref:System.Windows.Media.TextFormatting.TextFormatter> interagiert mit einer Textlayout-Clients über eine Reihe von Rückrufmethoden. Es muss der Client diese Methoden in einer Implementierung von der <xref:System.Windows.Media.TextFormatting.TextSource> Klasse. Das folgende Diagramm veranschaulicht die Text-Layout-Interaktion zwischen der Clientanwendung und <xref:System.Windows.Media.TextFormatting.TextFormatter>.  
  
 ![Diagramm des Textlayout-Clients und TextFormatter](../../../../docs/framework/wpf/advanced/media/textformatter01.png "TextFormatter01")  
Interaktion zwischen Anwendung und TextFormatter  
  
 Weitere Informationen zum Erstellen von benutzerdefinierten Textlayouts finden Sie unter [Advanced Text Formatting](../../../../docs/framework/wpf/advanced/advanced-text-formatting.md).  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Windows.Media.FormattedText>  
 <xref:System.Windows.Media.TextFormatting.TextFormatter>  
 [Übersicht über ClearType](../../../../docs/framework/wpf/advanced/cleartype-overview.md)  
 [Features für OpenType-Schriftarten](../../../../docs/framework/wpf/advanced/opentype-font-features.md)  
 [Zeichnen von formatiertem Text](../../../../docs/framework/wpf/advanced/drawing-formatted-text.md)  
 [Erweiterte Textformatierung](../../../../docs/framework/wpf/advanced/advanced-text-formatting.md)  
 [Text](../../../../docs/framework/wpf/advanced/optimizing-performance-text.md)  
 [Microsoft-Typografie](http://www.microsoft.com/typography/default.mspx)
