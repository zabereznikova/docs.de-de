---
title: "Typografie in WPF | Microsoft Docs"
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
  - "Typografie, Informationen über Typografie"
ms.assetid: 06cbf17b-6eff-4fe5-949d-2dd533e4e1f4
caps.latest.revision: 27
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 26
---
# Typografie in WPF
In diesem Thema werden die wichtigsten typografischen Features von [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] eingeführt.  Diese Features umfassen verbesserte Qualität und Leistung beim Rendern von Text, Unterstützung von [!INCLUDE[TLA#tla_opentype](../../../../includes/tlasharptla-opentype-md.md)]\-Typografie, verbesserten internationalen Text, verbesserte Unterstützung für Schriftarten sowie neue Text\-Anwendungsprogrammierschnittstellen \(APIs\).  
  
   
  
<a name="Improved_Quality_and_Performance_of_Text"></a>   
## Verbesserte Textqualität und Leistung  
 Text in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] wird mit [!INCLUDE[TLA#tla_ct](../../../../includes/tlasharptla-ct-md.md)] gerendert. Damit wird die Übersichtlichkeit und die Lesbarkeit von Texten verbessert.  [!INCLUDE[TLA2#tla_ct](../../../../includes/tla2sharptla-ct-md.md)] ist eine von [!INCLUDE[TLA#tla_ms](../../../../includes/tlasharptla-ms-md.md)] entwickelte Softwaretechnologie, mit der die Lesbarkeit auf LCD\-Bildschirmen \(Liquid Crystal Displays\) verbessert wird, z. B. auf Laptopbildschirmen, Pocket PC\-Bildschirmen und Flachbildschirmen.  In [!INCLUDE[TLA2#tla_ct](../../../../includes/tla2sharptla-ct-md.md)] werden Teilpixel gerendert. Dies ermöglicht es, den Text mit größerer Wiedergabetreue anzuzeigen, indem Zeichen an Bruchteilen eines Pixels ausgerichtet werden.  Die zusätzliche Auflösung verbessert die Schärfe der kleinen Details bei der Textanzeige, wodurch der Text viel leichter über lange Zeiträume gelesen werden kann.  Eine weitere Verbesserung von [!INCLUDE[TLA2#tla_ct](../../../../includes/tla2sharptla-ct-md.md)] in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] ist Antialiasing in y\-Richtung, wodurch flache Kurven von Textzeichen oben und unten geglättet werden.  Weitere Informationen zu [!INCLUDE[TLA2#tla_ct](../../../../includes/tla2sharptla-ct-md.md)]\-Features finden Sie unter [Übersicht über ClearType](../../../../docs/framework/wpf/advanced/cleartype-overview.md).  
  
 ![Text mit ClearType&#45;Y&#45;Richtung&#45;Antialiasing](../../../../docs/framework/wpf/advanced/media/typographyinwpf02.png "TypographyInWPF02")  
Text mit ClearType\-Antialiasing in y\-Richtung  
  
 In [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] kann für die gesamte Textrenderingpipeline Hardwarebeschleunigung verwendet werden, vorausgesetzt, der Computer erfüllt die Mindesthardwareanforderungen.  Rendering, das nicht über Hardware ausgeführt werden kann, wird als Softwarerendering ausgeführt.  Die Hardwarebeschleunigung hat Auswirkungen auf alle Phasen der Textrenderingpipeline, vom Speichern einzelner Symbole über das Zusammenstellen von Symbolfolgen und das Anwenden von Effekten bis zum Anwenden des [!INCLUDE[TLA2#tla_ct](../../../../includes/tla2sharptla-ct-md.md)]\-Blendingalgorithmus auf die angezeigte Endausgabe.  Weitere Informationen zur Hardwarebeschleunigung finden Sie unter [Renderingebenen für Grafiken](../../../../docs/framework/wpf/advanced/graphics-rendering-tiers.md).  
  
 ![Diagramm der Text&#45;Rendering&#45;Pipeline](../../../../docs/framework/wpf/advanced/media/typographyinwpf01.png "TypographyInWPF01")  
  
        Diagramm der Textrenderingpipeline  
  
 Weiterhin werden für Text mit animierten Zeichen oder Symbolen die von [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] zur Verfügung gestellten Grafikhardwarefunktionen vollständig genutzt.  Das Ergebnis ist eine glatte Textanimation.  
  
<a name="Rich_Typography"></a>   
## Umfangreiche Typografie  
 Das [!INCLUDE[TLA2#tla_opentype](../../../../includes/tla2sharptla-opentype-md.md)]\-Schriftartformat ist eine Erweiterung des [!INCLUDE[TLA#tla_truetype](../../../../includes/tlasharptla-truetype-md.md)]\-Schriftartformats.  Das [!INCLUDE[TLA2#tla_opentype](../../../../includes/tla2sharptla-opentype-md.md)]\-Schriftartformat wurde von [!INCLUDE[TLA#tla_ms](../../../../includes/tlasharptla-ms-md.md)] und Adobe gemeinsam entwickelt und bietet eine umfangreiche Auswahl erweiterter typografischer Features.  Das <xref:System.Windows.Documents.Typography>\-Objekt macht viele der erweiterten Features von [!INCLUDE[TLA2#tla_opentype](../../../../includes/tla2sharptla-opentype-md.md)]\-Schriftarten verfügbar, z. B. alternativer Stil und Schwünge.  Im [!INCLUDE[TLA2#tla_lhsdk](../../../../includes/tla2sharptla-lhsdk-md.md)] wird eine Reihe von [!INCLUDE[TLA2#tla_opentype](../../../../includes/tla2sharptla-opentype-md.md)]\-Beispielschriftarten zur Verfügung gestellt, die umfangreiche Features aufweisen, z. B. die Schriftarten Pericles und Pescadero.  Weitere Informationen finden Sie unter [OpenType\-Beispielschriftartenpaket](../../../../docs/framework/wpf/advanced/sample-opentype-font-pack.md).  
  
 Die [!INCLUDE[TLA2#tla_opentype](../../../../includes/tla2sharptla-opentype-md.md)]\-Schriftart Pericles enthält zusätzliche Symbole, die als alternativer Stil für den Standardsatz von Symbolen verwendet werden können.  Im folgenden Text werden Symbole im alternativen Stil angezeigt.  
  
 ![Text mit alternativen OpenType&#45;Stilsymbolen](../../../../docs/framework/wpf/advanced/media/opentypefont02.png "opentypefont02")  
  
        Text mit OpenType\-Symbolen im alternativen Stil  
  
 Schwünge sind dekorative Symbole, deren reiche Verzierungen häufig mit Kalligraphie assoziiert werden.  Im folgenden Text werden Standard\- und Schwungsymbole für die Schriftart Pescadero angezeigt.  
  
 ![Text mit OpenType&#45;Standard&#45; und Ziersymbolen](../../../../docs/framework/wpf/advanced/media/opentypefont08.png "opentypefont08")  
  
        Text mit OpenType\-Standard\- und \-Schwungsymbolen  
  
 Weitere Details zu den Features von [!INCLUDE[TLA2#tla_opentype](../../../../includes/tla2sharptla-opentype-md.md)] finden Sie unter [Features für OpenType\-Schriftarten](../../../../docs/framework/wpf/advanced/opentype-font-features.md).  
  
<a name="Enhanced_International_Text_Support"></a>   
## Verbesserte Unterstützung von internationalem Text  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] bietet durch die folgenden Features verbesserte Unterstützung für internationalen Text:  
  
-   Automatischer Zeilenabstand in allen Schriftsystemen durch adaptive Maßeinheiten  
  
-   Umfassende Unterstützung für internationalen Text.  Weitere Informationen finden Sie unter [Globalisierung für WPF](../../../../docs/framework/wpf/advanced/globalization-for-wpf.md).  
  
-   Zeilenumbruch, Silbentrennung und Ausrichtung entsprechend der Sprache  
  
<a name="Enhanced_Font_Support"></a>   
## Verbesserte Schriftartunterstützung  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] bietet durch die folgenden Features verbesserte Schriftartunterstützung:  
  
-   Unicode für jeden Text.  Für Schriftartverhalten und \-auswahl ist kein Charset bzw. keine Codepage mehr erforderlich.  
  
-   Von globalen Einstellungen unabhängiges Schriftartverhalten, z. B. vom Systemgebietsschema  
  
-   Die Typen <xref:System.Windows.FontWeight>, <xref:System.Windows.FontStretch> und <xref:System.Windows.FontStyle> zum Definieren von <xref:System.Windows.Media.FontFamily> sind getrennt.  Dies verbessert die Flexibilität gegenüber der Programmierung in [!INCLUDE[TLA#tla_win32](../../../../includes/tlasharptla-win32-md.md)], wo zum Definieren einer Schriftfamilie boolesche Kombinationen aus Kursiv und Fett verwendet werden.  
  
-   Die Schreibrichtung \(horizontal gegenüber vertikal\) wird unabhängig vom Schriftartnamen behandelt.  
  
-   Schriftartverknüpfungen und Ersatzschriftarten in einer portierbaren [!INCLUDE[TLA#tla_xml](../../../../includes/tlasharptla-xml-md.md)]\-Datei mit der Technologie für zusammengesetzte Schriftarten.  Mit zusammengesetzten Schriftarten können vollständige mehrsprachige Schriftarten erstellt werden.  Zusammengesetzte Schriftarten verfügen zudem über einen Mechanismus, der das Anzeigen fehlender Symbole verhindert.  Weitere Informationen finden Sie in den Hinweisen zur <xref:System.Windows.Media.FontFamily>\-Klasse.  
  
-   Erstellen von internationalen Schriftarten aus zusammengesetzten Schriftarten mithilfe mehrerer Einzelsprachenschriftarten.  Hierdurch werden bei der Entwicklung von Schriftarten für mehrere Sprachen Ressourcen eingespart.  
  
-   In ein Dokument eingebettete zusammengesetzte Schriftarten für die Portierung von Dokumenten.  Weitere Informationen finden Sie in den Hinweisen zur <xref:System.Windows.Media.FontFamily>\-Klasse.  
  
<a name="New_Text_APIs"></a>   
## Neue Text\-APIs  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] enthält mehrere Text\-[!INCLUDE[TLA2#tla_api#plural](../../../../includes/tla2sharptla-apisharpplural-md.md)], die Entwickler zum Einfügen von Text in Anwendungen verwenden können.  Diese [!INCLUDE[TLA2#tla_api#plural](../../../../includes/tla2sharptla-apisharpplural-md.md)] werden in drei Kategorien unterteilt:  
  
-   **Layout und Benutzeroberfläche**.  Die allgemeinen Textsteuerelemente für [!INCLUDE[TLA#tla_gui](../../../../includes/tlasharptla-gui-md.md)].  
  
-   **Einfache Textzeichnung**.  Ermöglicht das direkte Zeichnen von Text auf Objekten.  
  
-   **Erweiterte Textformatierung**.  Ermöglicht das Implementieren eines benutzerdefinierten Textmoduls.  
  
### Layout und Benutzeroberfläche  
 Auf der höchsten Funktionalitätsebene stellen die Text\-[!INCLUDE[TLA2#tla_api#plural](../../../../includes/tla2sharptla-apisharpplural-md.md)] allgemeine [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)]\-Steuerelemente wie <xref:System.Windows.Controls.Label>, <xref:System.Windows.Controls.TextBlock> und <xref:System.Windows.Controls.TextBox> bereit.  Diese Steuerelemente stellen innerhalb einer Anwendung die grundlegenden [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]\-Elemente zur Verfügung und bieten eine einfache Möglichkeit, Text darzustellen und zu bearbeiten.  Durch Steuerelemente wie <xref:System.Windows.Controls.RichTextBox> und <xref:System.Windows.Controls.PasswordBox> wird eine erweiterte oder spezialisierte Textbehandlung ermöglicht.  Klassen wie <xref:System.Windows.Documents.TextRange>, <xref:System.Windows.Documents.TextSelection> und <xref:System.Windows.Documents.TextPointer> stellen nützliche Textbearbeitungsoptionen bereit.  Diese [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]\-Steuerelemente stellen Eigenschaften wie <xref:System.Windows.Controls.Control.FontFamily%2A>, <xref:System.Windows.Controls.Control.FontSize%2A> und <xref:System.Windows.Controls.Control.FontStyle%2A> bereit, mit denen Sie die zum Rendern des Texts verwendete Schriftart steuern können.  
  
#### Verwenden von Bitmapeffekten, Transformationen und Texteffekten  
 Mit [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] können Sie mithilfe von Features wie Bitmapeffekten, Transformationen und Texteffekten visuell interessante Texte erstellen.  Im folgenden Beispiel wird ein typischer Schlagschatteneffekt auf einen Text angewendet.  
  
 ![Textschatten mit Weichheit &#61; 0,25](../../../../docs/framework/wpf/advanced/media/shadowtext01.png "ShadowText01")  
  
        Text mit Schlagschatten  
  
 Im folgenden Beispiel wird ein Text mit einem Schlagschatteneffekt und einem Geräusch versehen.  
  
 ![Textschatten mit Rauschen](../../../../docs/framework/wpf/advanced/media/shadowtext04.png "ShadowText04")  
  
        Text mit Schlagschatten und Geräusch  
  
 Im folgenden Beispiel wird ein Text mit einem Leuchteffekt umgeben.  
  
 ![Textschatten mit einem OuterGlowBitmapEffect](../../../../docs/framework/wpf/advanced/media/shadowtext05.png "ShadowText05")  
  
        Text umgeben von einem Leuchteffekt  
  
 Im folgenden Beispiel wird ein Weichzeichnereffekt auf einen Text angewendet.  
  
 ![Textschatten mit einem BlurBitmapEffect](../../../../docs/framework/wpf/advanced/media/shadowtext06.png "ShadowText06")  
  
        Text mit Weichzeichnereffekt  
  
 Im folgenden Beispiel wird die zweite Textzeile entlang der x\-Achse und die dritte Textzeile entlang der y\-Achse um je 150 % skaliert.  
  
 ![Skalierter Text mithilfe einer ScaleTransform](../../../../docs/framework/wpf/advanced/media/transformedtext02.png "TransformedText02")  
  
        Text mit ScaleTransform  
  
 Im folgenden Beispiel wird ein entlang der x\-Achse verzerrter Text dargestellt.  
  
 ![Geneigter Text mithilfe einer SkewTransform](../../../../docs/framework/wpf/advanced/media/transformedtext03.png "TransformedText03")  
  
        Text mit SkewTransform  
  
 Ein <xref:System.Windows.Media.TextEffect>\-Objekt ist ein Hilfsobjekt, mit dem Text als eine oder mehrere Zeichengruppen in einer Textzeichenfolge behandelt werden kann.  Im folgenden Beispiel wird ein einzelnes, sich drehendes Zeichen dargestellt.  Jedes Zeichen wird unabhängig in Intervallen von 1 Sekunde gedreht.  
  
 ![Bildschirmabbildung des Texteffekts zum Drehen von Text](../../../../docs/framework/wpf/advanced/media/texteffect01.png "TextEffect01")  
  
        Beispiel für eine sich drehende Texteffektanimation  
  
#### Verwenden von Flussdokumenten  
 Zusätzlich zu den allgemeinen [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]\-Steuerelementen bietet [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] ein Layoutsteuerelement für die Textpräsentation, das <xref:System.Windows.Documents.FlowDocument>\-Element.  Das <xref:System.Windows.Documents.FlowDocument>\-Element stellt in Verbindung mit dem <xref:System.Windows.Controls.DocumentViewer>\-Element ein Steuerelement für große Textmengen mit unterschiedlichen Layoutanforderungen bereit.  Layoutsteuerelemente ermöglichen den Zugriff auf erweiterte Typografie durch das <xref:System.Windows.Documents.Typography>\-Objekt und schriftartbezogene Eigenschaften anderer [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]\-Steuerelemente.  
  
 Der im folgenden Beispiel dargestellte Text wird in einem <xref:System.Windows.Controls.FlowDocumentReader> gehostet, der Suche, Navigation, Paginierung und Inhaltskalierung unterstützt.  
  
 ![Bildschirmabbildung des Beispiels für die Verwendung von OpenType&#45;Schriftarten](../../../../docs/framework/wpf/advanced/media/typographyinwpf-03.png "TypographyInWPF\_03")  
  
        In einem FlowDocumentReader gehosteter Text  
  
 Weitere Informationen finden Sie unter [Dokumente in WPF](../../../../docs/framework/wpf/advanced/documents-in-wpf.md).  
  
### Einfache Textzeichnung  
 Text kann direkt auf [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]\-Objekte gezeichnet werden, indem die <xref:System.Windows.Media.DrawingContext.DrawText%2A>\-Methode des <xref:System.Windows.Media.DrawingContext>\-Objekts verwendet wird.  Zum Verwenden dieser Methode erstellen Sie ein <xref:System.Windows.Media.FormattedText>\-Objekt.  Dieses Objekt ermöglicht das Zeichnen von mehrzeiligem Text, in dem jedes Zeichen einzeln formatiert werden kann.  Die Funktionalität des <xref:System.Windows.Media.FormattedText>\-Objekts umfasst einen großen Teil der Funktionalität der DrawText\-Flags der Win32\-API.  Zudem enthält das <xref:System.Windows.Media.FormattedText>\-Objekt Funktionen wie die Unterstützung von Auslassungszeichen, wodurch Auslassungszeichen angezeigt werden, wenn der Text die Begrenzungen überschreitet.  Im folgenden Beispiel wird ein Text gezeigt, auf den mehrere Formatierungen angewendet wurden, unter anderem ein linearer Farbverlauf beim zweiten und dritten Wort.  
  
 ![Mit dem FormattedText&#45;Objekt angezeigter Text](../../../../docs/framework/wpf/advanced/media/formattedtext01.png "FormattedText01")  
  
        Angezeigter Text mit FormattedText\-Objekt  
  
 Formatierter Text kann in <xref:System.Windows.Media.Geometry>\-Objekte umgewandelt werden, sodass Sie andere visuell interessante Textarten erstellen können.  Sie können beispielsweise auf Grundlage der Gliederung einer Textzeichenfolge ein <xref:System.Windows.Media.Geometry>\-Objekt erstellen.  
  
 ![Textkontur mit einem linearen Farbverlaufspinsel](../../../../docs/framework/wpf/advanced/media/outlinedtext02.png "OutlinedText02")  
  
        Textgliederung mit einem Pinsel für linearen Farbverlauf  
  
 Im folgenden Beispiel werden mehrere Möglichkeiten zum Erstellen interessanter visueller Effekte durch Ändern von Strichen, Füllung und Hervorhebung des konvertierten Texts veranschaulicht.  
  
 ![Text mit unterschiedlichen Farben für Füllung und Strich](../../../../docs/framework/wpf/advanced/media/outlinedtext03.png "OutlinedText03")  
  
        Beispiel für das Festlegen von verschiedenen Farben für Striche und Füllung  
  
 ![Text mit auf Strich angewendeten Bildpinsel](../../../../docs/framework/wpf/advanced/media/outlinedtext04.png "OutlinedText04")  
  
        Beispiel für die Anwendung eines Bildpinsels auf den Strich  
  
 ![Text mit auf Strich angewendeten Bildpinsel](../../../../docs/framework/wpf/advanced/media/outlinedtext05.png "OutlinedText05")  
Beispiel für die Anwendung eines Bildpinsels auf den Strich und die Hervorhebung  
  
 Weitere Informationen über das <xref:System.Windows.Media.FormattedText>\-Objekt finden Sie unter [Zeichnen von formatiertem Text](../../../../docs/framework/wpf/advanced/drawing-formatted-text.md).  
  
### Erweiterte Textformatierung  
 Auf der höchsten Ebene von Text\-[!INCLUDE[TLA2#tla_api#plural](../../../../includes/tla2sharptla-apisharpplural-md.md)] bietet [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] die Möglichkeit, mithilfe des <xref:System.Windows.Media.TextFormatting.TextFormatter>\-Objekts und anderer Typen im <xref:System.Windows.Media.TextFormatting>\-Namespace benutzerdefinierte Textlayouts zu erstellen.  Mit dem <xref:System.Windows.Media.TextFormatting.TextFormatter> und den zugeordneten Klassen können Sie benutzerdefinierte Textlayouts implementieren, die Ihre eigenen Definitionen für  Zeichenformate, Absatzformatvorlagen, Regeln für den Zeilenumbruch und andere Layoutfeatures für internationalen Text unterstützen.  Es ist nur selten sinnvoll, die Standardimplementierung der [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]\-Textlayoutunterstützung zu überschreiben.  Zum Erstellen eines Steuerelements oder einer Anwendung für die Textbearbeitung kann jedoch eine andere Implementierung als die [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]\-Standardimplementierung erforderlich sein.  
  
 Im Gegensatz zu einer herkömmlichen Text\-[!INCLUDE[TLA#tla_api](../../../../includes/tlasharptla-api-md.md)] interagiert der <xref:System.Windows.Media.TextFormatting.TextFormatter> mit einem Textlayoutclient über eine Reihe von Rückrufmethoden.  Hierfür ist erforderlich, dass der Client diese Methoden in einer Implementierung der <xref:System.Windows.Media.TextFormatting.TextSource>\-Klasse bereitstellt.  Im folgenden Diagramm wird die Textlayoutinteraktion zwischen der Clientanwendung und <xref:System.Windows.Media.TextFormatting.TextFormatter> veranschaulicht.  
  
 ![Diagramm des Textlayout&#45;Clients und TextFormatter](../../../../docs/framework/wpf/advanced/media/textformatter01.png "TextFormatter01")  
Interaktion zwischen Anwendung und TextFormatter  
  
 Weitere Informationen zum Erstellen von benutzerdefinierten Textlayouts finden Sie unter [Erweiterte Textformatierung](../../../../docs/framework/wpf/advanced/advanced-text-formatting.md).  
  
## Siehe auch  
 <xref:System.Windows.Media.FormattedText>   
 <xref:System.Windows.Media.TextFormatting.TextFormatter>   
 [Übersicht über ClearType](../../../../docs/framework/wpf/advanced/cleartype-overview.md)   
 [Features für OpenType\-Schriftarten](../../../../docs/framework/wpf/advanced/opentype-font-features.md)   
 [Zeichnen von formatiertem Text](../../../../docs/framework/wpf/advanced/drawing-formatted-text.md)   
 [Erweiterte Textformatierung](../../../../docs/framework/wpf/advanced/advanced-text-formatting.md)   
 [Text](../../../../docs/framework/wpf/advanced/optimizing-performance-text.md)   
 [Microsoft\-Typografie](http://www.microsoft.com/typography/default.mspx)