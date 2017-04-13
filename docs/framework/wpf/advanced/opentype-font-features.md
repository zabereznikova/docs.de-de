---
title: "Features f&#252;r OpenType-Schriftarten | Microsoft Docs"
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
  - "Schriftarten, OpenType"
  - "Typografie OpenType-schriftarttechnologie"
  - "OpenType-Schriftarttechnologie"
ms.assetid: 4061a9d1-fe8b-4921-9e17-18ec7d2e3ea2
caps.latest.revision: 38
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 37
---
# Features f&#252;r OpenType-Schriftarten
Dieses Thema enthält eine Übersicht über einige der wichtigsten Features von [!INCLUDE[TLA#tla_opentype](../../../../includes/tlasharptla-opentype-md.md)] Technologie in [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)].  
  
 [!INCLUDE[autoOutline](../Token/autoOutline_md.md)]  
  
<a name="overview"></a>   
## <a name="opentype-font-format"></a>OpenType-Schriftarten  
 Die [!INCLUDE[TLA#tla_opentype](../../../../includes/tlasharptla-opentype-md.md)] Schriftartformat ist eine Erweiterung der [!INCLUDE[TLA#tla_truetype](../../../../includes/tlasharptla-truetype-md.md)] Schriftartformat, Hinzufügen von Unterstützung für PostScript-Schriftartdaten. Die [!INCLUDE[TLA#tla_opentype](../../../../includes/tlasharptla-opentype-md.md)] Schriftartformat Zusammenarbeit von entwickelt wurde [!INCLUDE[TLA#tla_ms](../../../../includes/tlasharptla-ms-md.md)] und Adobe Corporation. [!INCLUDE[TLA#tla_opentype](../../../../includes/tlasharptla-opentype-md.md)]die Unterstützung von Schriftarten und das Betriebssystem services [!INCLUDE[TLA#tla_opentype](../../../../includes/tlasharptla-opentype-md.md)] Schriftarten bieten Benutzern eine einfache Möglichkeit zum Installieren und Verwenden von Schriftarten, ob die Schriftarten enthalten [!INCLUDE[TLA2#tla_truetype](../../../../includes/tla2sharptla-truetype-md.md)] Konturen oder CFF (PostScript) beschrieben werden.  
  
 Die [!INCLUDE[TLA#tla_opentype](../../../../includes/tlasharptla-opentype-md.md)] Schriftartformat behebt die folgenden Probleme für Entwickler:  
  
-   Breitere Multiplattform-Unterstützung.  
  
-   Bessere Unterstützung für internationale Zeichensätze.  
  
-   Besserer Schutz Schriftartdaten.  
  
-   Kleinere Dateigrößen Schriftart Verteilung effizienter zu gestalten.  
  
-   Breitere Unterstützung für erweiterte typografische Steuerelement.  
  
> [!NOTE]
>  Das Windows SDK enthält eine Reihe von [!INCLUDE[TLA#tla_opentype](../../../../includes/tlasharptla-opentype-md.md)] Schriftarten, die Sie verwenden können [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] Applications. Diese Schriftarten bieten die meisten Funktionen, die im Rest dieses Themas veranschaulicht. Weitere Informationen finden Sie unter [Beispiel OpenType-Schriftartenpaket](../../../../docs/framework/wpf/advanced/sample-opentype-font-pack.md).  
  
 Finden Sie unter der [OpenType-Spezifikation](http://go.microsoft.com/fwlink/?LinkId=96731) Details zu den [!INCLUDE[TLA#tla_opentype](../../../../includes/tlasharptla-opentype-md.md)] Schriftartformat.  
  
### <a name="advanced-typographic-extensions"></a>Erweiterte typografische Funktionen  
 Die erweiterten typografischen Tabellen ([!INCLUDE[TLA#tla_opentype](../../../../includes/tlasharptla-opentype-md.md)] Layouttabellen) erweitern die Funktionen der Schriftarten durch [!INCLUDE[TLA2#tla_truetype](../../../../includes/tla2sharptla-truetype-md.md)] oder CFF beschrieben werden. [!INCLUDE[TLA#tla_opentype](../../../../includes/tlasharptla-opentype-md.md)]Layout-Schriftarten enthalten zusätzliche Informationen, die die Funktionen der Schriftarten, um qualitativ hochwertige internationale Typografie unterstützt erweitert. Die meisten [!INCLUDE[TLA#tla_opentype](../../../../includes/tlasharptla-opentype-md.md)] Schriftarten machen nur eine Teilmenge aller [!INCLUDE[TLA#tla_opentype](../../../../includes/tlasharptla-opentype-md.md)] Funktionen verfügbar sind. [!INCLUDE[TLA#tla_opentype](../../../../includes/tlasharptla-opentype-md.md)]Schriftarten werden die folgenden Funktionen bereitstellen.  
  
-   Umfassende Zuordnung zwischen Zeichen und Symbole, die Unterstützung von Ligaturen, Formulare mit Feldern fester Breite, alternativen und andere Schriftarten ersetzen.  
  
-   Unterstützung für zweidimensionale Positionierung und Symbol Anlage.  
  
-   Explizite Skript und die Sprache in enthaltene Informationen Schriftart, damit eine Anwendung für die Verarbeitung von Text sein Verhalten entsprechend angepasst werden kann.  
  
 Die [!INCLUDE[TLA#tla_opentype](../../../../includes/tlasharptla-opentype-md.md)] Layouttabellen werden ausführlich in der ["Font File Tables"](http://www.microsoft.com/typography/otspec/otff.htm) Teil der [!INCLUDE[TLA#tla_opentype](../../../../includes/tlasharptla-opentype-md.md)] Spezifikation.  
  
 Im weiteren Verlauf dieser Übersicht werden, die Breite und Flexibilität einiger der visuell interessanten [!INCLUDE[TLA#tla_opentype](../../../../includes/tlasharptla-opentype-md.md)] Funktionen, die durch die Eigenschaften verfügbar gemacht werden die <xref:System.Windows.Documents.Typography> Objekt. Weitere Informationen zu diesem Objekt, finden Sie unter [Typografie-Klasse](#typography_class).  
  
<a name="variants"></a>   
## <a name="variants"></a>Varianten  
 Varianten werden zum Rendern von verschiedenen typografischen Stilen, wie z. B. hoch- und tiefgestellten Zeichen.  
  
### <a name="superscripts-and-subscripts"></a>Hoch- und tiefgestellte Zeichen  
 Die <xref:System.Windows.Documents.Typography.Variants%2A> -Eigenschaft können Sie hoch- und tiefgestellten Optionswerte für eine [!INCLUDE[TLA#tla_opentype](../../../../includes/tlasharptla-opentype-md.md)] Schriftart.  
  
 Im folgenden Text werden hochgestellte Zeichen für die Schriftart Palatino Linotype definiert werden.  
  
 ![Text mit hochgestellten OpenType-Zeichen](../../../../docs/framework/wpf/advanced/media/opentypefont14.png "opentypefont14")  
Text mit hochgestellten OpenType-Zeichen  
  
 Im folgenden Markupbeispiel wird veranschaulicht, wie hochgestellte Zeichen für die Schriftart Palatino Linotype, mit den Eigenschaften des der <xref:System.Windows.Documents.Typography> Objekt.  
  
 [!code-xml[OpenTypeFontSamples#12](../../../../samples/snippets/csharp/VS_Snippets_Wpf/OpenTypeFontSamples/CS/PageOne.xaml#12)]  
  
 Im folgenden Text werden tiefgestellte Zeichen für die Schriftart Palatino Linotype definiert werden.  
  
 ![Text mit tiefgestellten OpenType-Zeichen](../../../../docs/framework/wpf/advanced/media/opentypefont15.png "opentypefont15")  
Text mit tiefgestellten OpenType-Zeichen  
  
 Im folgenden Markupbeispiel wird veranschaulicht, wie tiefgestellte Zeichen für die Schriftart Palatino Linotype, mit den Eigenschaften des der <xref:System.Windows.Documents.Typography> Objekt.  
  
 [!code-xml[OpenTypeFontSamples#13](../../../../samples/snippets/csharp/VS_Snippets_Wpf/OpenTypeFontSamples/CS/PageOne.xaml#13)]  
  
### <a name="decorative-uses-of-superscripts-and-subscripts"></a>Hoch- und tiefgestellten dekorativen verwendet  
 Hoch- und tiefgestellten können auch um Text mit Groß-Hintergrundbildern zu erstellen. Im folgenden Text werden hoch- und tiefgestellten Text für die Schriftart Palatino Linotype definiert werden. Beachten Sie, dass die Großbuchstaben nicht beeinflusst werden.  
  
 ![Text mit hoch- und tiefgestellten OpenType](../../../../docs/framework/wpf/advanced/media/opentypefont16.png "opentypefont16")  
Text mit hoch- und tiefgestellten OpenType-Zeichen  
  
 Im folgenden Markupbeispiel wird veranschaulicht, wie hoch- und tiefgestellten Zeichen für eine Schriftart anhand der Eigenschaften definieren die <xref:System.Windows.Documents.Typography> Objekt.  
  
 [!code-xml[OpenTypeFontSamples#14](../../../../samples/snippets/csharp/VS_Snippets_Wpf/OpenTypeFontSamples/CS/PageOne.xaml#14)]  
  
<a name="capitals"></a>   
## <a name="capitals"></a>Großbuchstaben  
 Großbuchstaben sind ein Satz typografischen Formen, die Text in Großbuchstaben formatiert Symbole dargestellt. In der Regel, wenn Text als Großbuchstaben gerendert wird, der Abstand zwischen Buchstaben stehen zu eng ist, und die Stärke und die Proportion der Buchstaben zu groß. [!INCLUDE[TLA#tla_opentype](../../../../includes/tlasharptla-opentype-md.md)]unterstützt verschiedene Formate Stilen für Großbuchstaben, einschließlich Kapitälchen kleiner Kapitälchen, anspruchsvolle und Kapitälchenabstand. Dieser Stil-Formate können Sie die Darstellung von Großbuchstaben.  
  
 Im folgenden Text werden die standardmäßigen Großbuchstaben für die Schriftart Pescadero, gefolgt von den Buchstaben "SmallCaps" und "AllSmallCaps". In diesem Fall wird die gleiche Schriftgröße für alle drei Wörter verwendet.  
  
 ![Text mit OpenType-Kapitälchen](../../../../docs/framework/wpf/advanced/media/opentypefont11.png "opentypefont11")  
Text mit OpenType-Kapitälchen  
  
 Im folgenden Markupbeispiel wird veranschaulicht, wie Großbuchstaben für die Schriftart Pescadero anhand der Eigenschaften des definiert die <xref:System.Windows.Documents.Typography> Objekt. Wenn das "SmallCaps"-Format verwendet wird, ist die führende Großbuchstaben ignoriert.  
  
 [!code-xml[OpenTypeFontSamples#9](../../../../samples/snippets/csharp/VS_Snippets_Wpf/OpenTypeFontSamples/CS/PageOne.xaml#9)]  
  
### <a name="titling-capitals"></a>Großbuchstaben  
 Großbuchstaben sind heller und Anteil und sollen im Vergleich zu normalen Großbuchstaben eine elegantere Aussehen verleihen. Großbuchstaben werden in der Regel bei größeren Schriftgraden als Spaltenüberschriften verwendet. Im folgenden Text werden normale Großbuchstaben und Großbuchstaben für die Schriftart Pescadero. Beachten Sie die geringeren Strichstärken des Texts in der zweiten Zeile.  
  
 ![Text mit OpenType-Initialen](../../../../docs/framework/wpf/advanced/media/opentypefont20.png "OpenTypeFont20")  
Text mit OpenType-Initialen  
  
 Im folgenden Markupbeispiel wird veranschaulicht, wie Großbuchstaben für die Schriftart Pescadero anhand der Eigenschaften des definiert die <xref:System.Windows.Documents.Typography> Objekt.  
  
 [!code-xml[OpenTypeFontSamples#OpenTypeFontSnippet17](../../../../samples/snippets/csharp/VS_Snippets_Wpf/OpenTypeFontSamples/CS/PageOne.xaml#opentypefontsnippet17)]  
  
### <a name="capital-spacing"></a>Kapitälchenabstand  
 Kapitälchenabstand ist ein Feature, das Ihnen ermöglicht, weitere Abstände bieten bei Verwendung von Großbuchstaben in Text. Großbuchstaben dienen in der Regel mit einem Kleinbuchstaben blend. Abstand, wird zwischen und einem Großbuchstaben und einem Kleinbuchstaben aussehen zu eng gefasst wenn Großbuchstaben verwendet werden. Im folgenden Text werden normale und Abstand für die Schriftart Pescadero.  
  
 ![Text mit OpenType-Kapitälchenabstand](../../../../docs/framework/wpf/advanced/media/opentypefont21.png "OpenTypeFont21")  
Text mit OpenType-Kapitälchenabstand  
  
 Im folgenden Markupbeispiel wird veranschaulicht, wie Kapitälchenabstand für die Schriftart Pescadero anhand der Eigenschaften definieren die <xref:System.Windows.Documents.Typography> Objekt.  
  
 [!code-xml[OpenTypeFontSamples#OpenTypeFontSnippet18](../../../../samples/snippets/csharp/VS_Snippets_Wpf/OpenTypeFontSamples/CS/PageOne.xaml#opentypefontsnippet18)]  
  
<a name="ligatures"></a>   
## <a name="ligatures"></a>Ligaturen  
 Ligaturen sind zwei oder mehr Symbole, die in ein einzelnes Symbol gebildet werden, um besser lesbaren oder attraktiveren Text zu erstellen. [!INCLUDE[TLA#tla_opentype](../../../../includes/tlasharptla-opentype-md.md)]-Schriftarten unterstützen vier Typen von Ligaturen:  
  
-   **Standardligaturen**. Entwickelt, um die Lesbarkeit zu verbessern. Standardligaturen gehören "Fi", "fl" und "ff".  
  
-   **Kontextbedingte Ligaturen**. Entwickelt, um die Lesbarkeit zu verbessern, indem Sie zwischen den Zeichen, die Ligatur optimiertes Verbinden Verhalten bereitstellen.  
  
-   **Ligaturen**. Konzipiert waren und nicht speziell zur besseren Lesbarkeit.  
  
-   **Historischer Ligaturen**. Soll die Verlaufs- und nicht speziell zur besseren Lesbarkeit werden.  
  
 Im folgenden Text werden Symbole für die Schriftart Pericles Standardligaturen.  
  
 ![Text mit OpenType-Standardligaturen](../../../../docs/framework/wpf/advanced/media/opentypefont04.png "opentypefont04")  
Text mit OpenType-Standardligaturen  
  
 Im folgenden Markupbeispiel wird veranschaulicht, wie Symbole für die mithilfe der Eigenschaften der Schriftart Pericles Standardligaturen definieren die <xref:System.Windows.Documents.Typography> Objekt.  
  
 [!code-xml[OpenTypeFontSamples#4](../../../../samples/snippets/csharp/VS_Snippets_Wpf/OpenTypeFontSamples/CS/PageOne.xaml#4)]  
  
 Im folgenden Text werden Symbole für die Schriftart Pericles Ligaturen.  
  
 ![Text mit OpenType-Ligaturen](../../../../docs/framework/wpf/advanced/media/opentypefont05.png "opentypefont05")  
Text mit bedingten OpenType-Ligaturen  
  
 Im folgenden Markupbeispiel wird veranschaulicht, wie Ligaturen Symbole für die mithilfe der Eigenschaften der Schriftart Pericles definiert die <xref:System.Windows.Documents.Typography> Objekt.  
  
 [!code-xml[OpenTypeFontSamples#5](../../../../samples/snippets/csharp/VS_Snippets_Wpf/OpenTypeFontSamples/CS/PageOne.xaml#5)]  
  
 In der Standardeinstellung [!INCLUDE[TLA#tla_opentype](../../../../includes/tlasharptla-opentype-md.md)] Schriftarten in [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] Standardligaturen. Z. B. bei Verwendung die Schriftart Palatino Linotype angezeigt werden die Standardligaturen "Fi", "ff" und "fl" als kombiniertes Zeichensymbol. Beachten Sie, dass das Paar von Zeichen für die einzelnen Standardligaturen berühren.  
  
 ![Text mit OpenType-Standardligaturen](../../../../docs/framework/wpf/advanced/media/opentypefont06.png "opentypefont06")  
Text mit OpenType-Standardligaturen  
  
 Allerdings können Sie Features für Standardligaturen deaktivieren, damit eine Standardligaturen wie z. B. "ff" als zwei einzelne Symbole, und nicht als ein kombiniertes Zeichen-Symbol angezeigt.  
  
 ![Text mit deaktivierten OpenType-Standardligaturen](../../../../docs/framework/wpf/advanced/media/opentypefont07.png "opentypefont07")  
Text mit deaktivierten OpenType-Standardligaturen  
  
 Im folgenden Markupbeispiel wird veranschaulicht, wie Symbole für die Schriftart Palatino Linotype, mit den Eigenschaften des Standardligaturen deaktiviert die <xref:System.Windows.Documents.Typography> Objekt.  
  
 [!code-xml[OpenTypeFontSamples#6](../../../../samples/snippets/csharp/VS_Snippets_Wpf/OpenTypeFontSamples/CS/PageOne.xaml#6)]  
  
<a name="swashes"></a>   
## <a name="swashes"></a>Schwungschrift  
 Schwungschrift besteht aus dekorativen Symbole, die ausgefeilten Verzierung häufig mit Kalligraphie assoziiert verwenden. Im folgenden Text werden Symbole in Standard- und Schwungschrift für die Schriftart Pescadero.  
  
 ![Text mit OpenType-Standard- und Ziersymbolen](../../../../docs/framework/wpf/advanced/media/opentypefont08.png "opentypefont08")  
Text mit OpenType-Standard- und Ziersymbolen  
  
 Schwungschrift werden häufig als dekorativen Elementen in kurzen Sätzen wie z. B. Ereignis Ankündigungen verwendet. Der folgende Text verwendet Schwungschrift, um den Großbuchstaben, der den Namen des Ereignisses hervorzuheben.  
  
 ![Text mit OpenType-Zierbuchstaben](../../../../docs/framework/wpf/advanced/media/opentypefont09.png "opentypefont09")  
Text mit OpenType-Zierbuchstaben  
  
 Im folgenden Markupbeispiel wird veranschaulicht, wie die Schwungschrift für eine Schriftart anhand der Eigenschaften definiert die <xref:System.Windows.Documents.Typography> Objekt.  
  
 [!code-xml[OpenTypeFontSamples#7](../../../../samples/snippets/csharp/VS_Snippets_Wpf/OpenTypeFontSamples/CS/PageOne.xaml#7)]  
  
### <a name="contextual-swashes"></a>Schwungschrift  
 Bestimmte Kombinationen von Symbolen in Schwungschrift können unästhetisch wirken, z. B. sich überschneidende Unterlängen bei aufeinander folgenden Buchstaben. Eine kontextbedingte Schwungschrift verwenden, können Sie ein Ersatz Schwungschrift Symbol verwenden, die eine bessere Darstellung erzeugt. Im folgenden Text wird das gleiche Wort vor und nach eine kontextbedingte Schwungschrift angewendet wird.  
  
 ![Text mit kontextbezogenen OpenType-Zierbuchstaben](../../../../docs/framework/wpf/advanced/media/opentypefont19.png "OpenTypeFont19")  
Text mit kontextbezogenen OpenType-Zierbuchstaben  
  
 Im folgenden Markupbeispiel wird veranschaulicht, wie eine kontextbedingte Schwungschrift für die Schriftart Pescadero anhand der Eigenschaften definieren die <xref:System.Windows.Documents.Typography> Objekt.  
  
 [!code-xml[OpenTypeFontSamples#OpenTypeFontSnippet16](../../../../samples/snippets/csharp/VS_Snippets_Wpf/OpenTypeFontSamples/CS/PageOne.xaml#opentypefontsnippet16)]  
  
<a name="alternates"></a>   
## <a name="alternates"></a>Stellvertreter  
 Varianten sind Symbole, die ein Standardsymbol ersetzen können. [!INCLUDE[TLA#tla_opentype](../../../../includes/tlasharptla-opentype-md.md)]Schriftarten, z. B. die Schriftart Pericles in den folgenden Beispielen können von Symbolen enthalten, die Sie verwenden können, um unterschiedliche Darstellungen für Text zu erstellen. Im folgenden Text werden die Standardsymbole der Schriftart Pericles.  
  
 ![Text mit OpenType-Standardsymbolen](../../../../docs/framework/wpf/advanced/media/opentypefont01.png "opentypefont01")  
Text mit OpenType-Standardsymbolen  
  
 Die Pericles [!INCLUDE[TLA#tla_opentype](../../../../includes/tlasharptla-opentype-md.md)] enthält zusätzliche Symbole, die Stilvariante für den Standardsatz von Symbolen bereitstellen. Im folgenden Text werden Symbole im alternativen.  
  
 ![Text mit alternativen OpenType-Stilsymbolen](../../../../docs/framework/wpf/advanced/media/opentypefont02.png "opentypefont02")  
Text mit alternativen OpenType-Stilsymbolen  
  
 Im folgenden Markupbeispiel wird veranschaulicht, wie Symbole im alternativen mithilfe der Eigenschaften der Schriftart Pericles definiert die <xref:System.Windows.Documents.Typography> Objekt.  
  
 [!code-xml[OpenTypeFontSamples#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/OpenTypeFontSamples/CS/PageOne.xaml#2)]  
  
 Im folgenden Text werden mehrere andere alternativen Stilsymbolen der Schriftart Pericles.  
  
 ![Text mit alternativen OpenType-Stilsymbolen](../../../../docs/framework/wpf/advanced/media/opentypefont03.png "opentypefont03")  
Text mit alternativen OpenType-Stilsymbolen  
  
 Im folgenden Markupbeispiel wird veranschaulicht, wie diese andere alternativen Stilsymbolen definieren.  
  
 [!code-xml[OpenTypeFontSamples#3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/OpenTypeFontSamples/CS/PageOne.xaml#3)]  
  
### <a name="random-contextual-alternates"></a>Willkürlichen kontextbedingten  
 Willkürlichen kontextbedingten bieten mehrere Ersatzsymbole für ein einzelnes Zeichen. Bei der Implementierung mit Schriftarten kann dieses Feature Handschrift simulieren, indem Sie mit einem Satz zufällig ausgewählter Symbole mit geringfügigen Unterschieden in der Darstellung. Der folgende Text verwendet willkürlichen kontextbedingten für Lindsey-Schriftart. Beachten Sie, dass der Buchstabe "a" variiert leicht in der Darstellung  
  
 ![Text mit willkürlichen kontextbedingten OpenType](../../../../docs/framework/wpf/advanced/media/opentypefont23.png "OpenTypeFont23")  
Text mit willkürlichen kontextbedingten OpenType-Varianten  
  
 Im folgenden Markupbeispiel wird veranschaulicht, wie willkürlichen kontextbedingten für die Lindsey-Schriftart mithilfe der Eigenschaften der definieren die <xref:System.Windows.Documents.Typography> Objekt.  
  
 [!code-xml[OpenTypeFontSamples#OpenTypeFontSnippet20](../../../../samples/snippets/csharp/VS_Snippets_Wpf/OpenTypeFontSamples/CS/Window1.xaml#opentypefontsnippet20)]  
  
### <a name="historical-forms"></a>Mediävalen  
 Mediävalen sind typografische Konventionen, die häufig in der Vergangenheit waren. Im folgenden Text wird der Ausdruck "Boston, Massachusetts", mit einem Verlauf-Formular von Symbolen für die Schriftart Palatino Linotype definiert werden.  
  
 ![Text mit OpenType-Mediävalen](../../../../docs/framework/wpf/advanced/media/opentypefont10.png "opentypefont10")  
Text mit OpenType-Mediävalen  
  
 Im folgenden Markupbeispiel wird veranschaulicht, wie Mediävalen für die mithilfe der Eigenschaften der Schriftart Palatino Linotype definiert die <xref:System.Windows.Documents.Typography> Objekt.  
  
 [!code-xml[OpenTypeFontSamples#8](../../../../samples/snippets/csharp/VS_Snippets_Wpf/OpenTypeFontSamples/CS/PageOne.xaml#8)]  
  
<a name="numerical_styles"></a>   
## <a name="numerical-styles"></a>Numerische Formate  
 OpenType-Schriftarten unterstützen eine große Anzahl von Features, die mit numerischen Werten im Text verwendet werden können.  
  
### <a name="fractions"></a>Brüche  
 [!INCLUDE[TLA#tla_opentype](../../../../includes/tlasharptla-opentype-md.md)]Schriftarten unterstützen Formatvorlagen, einschließlich diagonalem und horizontalem.  
  
 Im folgenden Text werden Bruchformate für die Schriftart Palatino Linotype.  
  
 ![Text mit OpenType-Brüchen mit schrägem oder waagerechtem Bruchstrich](../../../../docs/framework/wpf/advanced/media/opentypefont12.png "opentypefont12")  
Text mit OpenType-Brüchen mit schrägem oder waagerechtem Bruchstrich  
  
 Im folgenden Markupbeispiel veranschaulicht die Bruchformate für die Schriftart Palatino Linotype, mit den Eigenschaften des der <xref:System.Windows.Documents.Typography> Objekt.  
  
 [!code-xml[OpenTypeFontSamples#10](../../../../samples/snippets/csharp/VS_Snippets_Wpf/OpenTypeFontSamples/CS/PageOne.xaml#10)]  
  
### <a name="old-style-numerals"></a>Mediävalziffern  
 [!INCLUDE[TLA#tla_opentype](../../../../includes/tlasharptla-opentype-md.md)]Schriftarten unterstützen ein altes Format Ziffer-Format. Dieses Format eignet sich zum Anzeigen von Zahlen in Formate, die nicht mehr standard sind. Der folgende Text wird ein Datum 18. Jahrhundert im Standard- und Mediävalziffern für die Schriftart Palatino Linotype definiert werden.  
  
 ![Text mit OpenType-Mediävalziffern](../../../../docs/framework/wpf/advanced/media/opentypefont24.png "OpenTypeFont24")  
Text mit OpenType-Mediävalziffern  
  
 Der folgende Text werden in der Schriftart Palatino Linotype, gefolgt von Mediävalziffern.  
  
 ![Text mit OpenType-Mediävalziffernsätzen](../../../../docs/framework/wpf/advanced/media/opentypefont13.png "opentypefont13")  
Text mit OpenType-Mediävalziffernsätzen  
  
 Im folgenden Markupbeispiel wird veranschaulicht, wie Mediävalziffern für die Schriftart Palatino Linotype, mit den Eigenschaften des definieren die <xref:System.Windows.Documents.Typography> Objekt.  
  
 [!code-xml[OpenTypeFontSamples#11](../../../../samples/snippets/csharp/VS_Snippets_Wpf/OpenTypeFontSamples/CS/PageOne.xaml#11)]  
  
### <a name="proportional-and-tabular-figures"></a>Proportional und tabellarische Zahlen  
 [!INCLUDE[TLA#tla_opentype](../../../../includes/tlasharptla-opentype-md.md)]Schriftarten werden eine proportional und tabellarische Abbildung-Funktion, um die Ausrichtung der breiten zu steuern, wenn Zahlen mit unterstützt. Proportionalen Darstellung verfügt jede Ziffer über eine eigene Breite: "1" ist schmaler als "5". Tabellarische Zahlen werden als Ziffern in gleich Breite behandelt, damit sie erhöhen die Lesbarkeit des finanziellen Typinformationen vertikal auszurichten.  
  
 Im folgenden Text werden zwei proportionalen Darstellung in der ersten Spalte, die mit der Schriftart Miramonte definiert wird. Beachten Sie den Unterschied in der Breite zwischen die Ziffern "5" und "1". Die zweite Spalte enthält die gleichen zwei numerische Werte mit der breiten mithilfe der Funktion der tabellarischen Abbildung angepasst.  
  
 ![Text mit OpenType-proportional & tabellarische Tabellensatz](../../../../docs/framework/wpf/advanced/media/opentypefont22.png "OpenTypeFont22")  
Text mit OpenType-proportional und tabellarische Tabellensatz  
  
 Im folgenden Markupbeispiel wird veranschaulicht, wie proportionale und tabellarische Zahlen für die Schriftart Miramonte definiert wird, die mit den Eigenschaften des definieren die <xref:System.Windows.Documents.Typography> Objekt.  
  
 [!code-xml[OpenTypeFontSamples#OpenTypeFontSnippet19](../../../../samples/snippets/csharp/VS_Snippets_Wpf/OpenTypeFontSamples/CS/Window1.xaml#opentypefontsnippet19)]  
  
### <a name="slashed-zero"></a>NULL mit Schrägstrich  
 [!INCLUDE[TLA#tla_opentype](../../../../includes/tlasharptla-opentype-md.md)]Schriftarten unterstützen Ziffernformat NULL Ziffer Format den Unterschied zwischen den Buchstaben "O" und die Ziffer "0" hervorgehoben werden sollen. Das Ziffernformat, die&0; (null) wird häufig für Bezeichner in Finanz- und Informationen verwendet wird.  
  
 Im folgenden Text werden die Kennung ein Beispiel mit der Schriftart Miramonte definiert wird. Die erste Zeile verwendet standard-Zahlen. Die zweite Zeile verwendet Ziffer Null mit Schrägstrich um optisch besser vom Großbuchstaben "O".  
  
 ![Text mit OpenType-Brüchen mit schrägem oder NULL](../../../../docs/framework/wpf/advanced/media/opentypefont17.png "OpenTypeFont17")  
Text mit OpenType-Ziffern mit Null mit Schrägstrich  
  
 Im folgenden Markupbeispiel wird veranschaulicht, wie definieren Ziffer Null mit Schrägstrich für die Schriftart Miramonte definiert wird, die mit den Eigenschaften des der <xref:System.Windows.Documents.Typography> Objekt.  
  
 [!code-xml[OpenTypeFontSamples#OpenTypeFontSnippet15](../../../../samples/snippets/csharp/VS_Snippets_Wpf/OpenTypeFontSamples/CS/PageOne.xaml#opentypefontsnippet15)]  
  
<a name="typography_class"></a>   
## <a name="typography-class"></a>Typografieklasse  
 Die <xref:System.Windows.Documents.Typography> -Objekt macht den Satz von Funktionen, die eine [!INCLUDE[TLA#tla_opentype](../../../../includes/tlasharptla-opentype-md.md)] Schriftart unterstützt. Durch Festlegen der Eigenschaften des <xref:System.Windows.Documents.Typography> im Markup können Sie problemlos Dokumente, die nutzen erstellen [!INCLUDE[TLA#tla_opentype](../../../../includes/tlasharptla-opentype-md.md)] Funktionen.  
  
 Im folgenden Text werden die standardmäßigen Großbuchstaben für die Schriftart Pescadero, gefolgt von den Buchstaben "SmallCaps" und "AllSmallCaps". In diesem Fall wird die gleiche Schriftgröße für alle drei Wörter verwendet.  
  
 ![Text mit OpenType-Kapitälchen](../../../../docs/framework/wpf/advanced/media/opentypefont11.png "opentypefont11")  
Text mit OpenType-Kapitälchen  
  
 Im folgenden Markupbeispiel wird veranschaulicht, wie Großbuchstaben für die Schriftart Pescadero anhand der Eigenschaften des definiert die <xref:System.Windows.Documents.Typography> Objekt. Wenn das "SmallCaps"-Format verwendet wird, ist die führende Großbuchstaben ignoriert.  
  
 [!code-xml[OpenTypeFontSamples#9](../../../../samples/snippets/csharp/VS_Snippets_Wpf/OpenTypeFontSamples/CS/PageOne.xaml#9)]  
  
 Im folgenden Codebeispiel wird die gleiche Aufgabe wie im vorherigen Markupbeispiel erreicht.  
  
 [!code-csharp[TypographyCodeSnippets#TypographyCodeSnippet1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TypographyCodeSnippets/CSharp/Page1.xaml.cs#typographycodesnippet1)]
 [!code-vb[TypographyCodeSnippets#TypographyCodeSnippet1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TypographyCodeSnippets/visualbasic/page1.xaml.vb#typographycodesnippet1)]  
  
### <a name="typography-class-properties"></a>Eigenschaften von Typografie-Klasse  
 Die folgende Tabelle enthält die Eigenschaften, Werte und Standardeinstellungen für die <xref:System.Windows.Documents.Typography> Objekt.  
  
|Eigenschaft|Werte|Standardwert|  
|--------------|----------------|-------------------|  
|<xref:System.Windows.Documents.Typography.AnnotationAlternates%2A>|Numerischen Wert - Byte|0|  
|<xref:System.Windows.Documents.Typography.Capitals%2A>|<xref:System.Windows.FontCapitals> | <xref:System.Windows.FontCapitals> | <xref:System.Windows.FontCapitals> | <xref:System.Windows.FontCapitals> | <xref:System.Windows.FontCapitals> | <xref:System.Windows.FontCapitals> | <xref:System.Windows.FontCapitals>|<xref:System.Windows.FontCapitals?displayProperty=fullName>|  
|<xref:System.Windows.Documents.Typography.CapitalSpacing%2A>|<xref:System.Boolean>|`false`|  
|<xref:System.Windows.Documents.Typography.CaseSensitiveForms%2A>|<xref:System.Boolean>|`false`|  
|<xref:System.Windows.Documents.Typography.ContextualAlternates%2A>|<xref:System.Boolean>|`true`|  
|<xref:System.Windows.Documents.Typography.ContextualLigatures%2A>|<xref:System.Boolean>|`true`|  
|<xref:System.Windows.Documents.Typography.ContextualSwashes%2A>|Numerischen Wert - Byte|0|  
|<xref:System.Windows.Documents.Typography.DiscretionaryLigatures%2A>|<xref:System.Boolean>|`false`|  
|<xref:System.Windows.Documents.Typography.EastAsianExpertForms%2A>|<xref:System.Boolean>|`false`|  
|<xref:System.Windows.Documents.Typography.EastAsianLanguage%2A>|<xref:System.Windows.FontEastAsianLanguage> | <xref:System.Windows.FontEastAsianLanguage> | <xref:System.Windows.FontEastAsianLanguage> | <xref:System.Windows.FontEastAsianLanguage> | <xref:System.Windows.FontEastAsianLanguage> | <xref:System.Windows.FontEastAsianLanguage> | <xref:System.Windows.FontEastAsianLanguage> | <xref:System.Windows.FontEastAsianLanguage> | <xref:System.Windows.FontEastAsianLanguage> | <xref:System.Windows.FontEastAsianLanguage>|<xref:System.Windows.FontEastAsianLanguage?displayProperty=fullName>|  
|<xref:System.Windows.Documents.Typography.EastAsianWidths%2A>|<xref:System.Windows.FontEastAsianWidths> | <xref:System.Windows.FontEastAsianWidths> | <xref:System.Windows.FontEastAsianWidths> | <xref:System.Windows.FontEastAsianWidths> | <xref:System.Windows.FontEastAsianWidths> | <xref:System.Windows.FontEastAsianWidths>|<xref:System.Windows.FontEastAsianWidths?displayProperty=fullName>|  
|<xref:System.Windows.Documents.Typography.Fraction%2A>|<xref:System.Windows.FontFraction> | <xref:System.Windows.FontFraction> | <xref:System.Windows.FontFraction>|<xref:System.Windows.FontFraction?displayProperty=fullName>|  
|<xref:System.Windows.Documents.Typography.HistoricalForms%2A>|<xref:System.Boolean>|`false`|  
|<xref:System.Windows.Documents.Typography.HistoricalLigatures%2A>|<xref:System.Boolean>|`false`|  
|<xref:System.Windows.Documents.Typography.Kerning%2A>|<xref:System.Boolean>|`true`|  
|<xref:System.Windows.Documents.Typography.MathematicalGreek%2A>|<xref:System.Boolean>|`false`|  
|<xref:System.Windows.Documents.Typography.NumeralAlignment%2A>|<xref:System.Windows.FontNumeralAlignment> | <xref:System.Windows.FontNumeralAlignment> | <xref:System.Windows.FontNumeralAlignment>|<xref:System.Windows.FontNumeralAlignment?displayProperty=fullName>|  
|<xref:System.Windows.Documents.Typography.NumeralStyle%2A>|<xref:System.Boolean>|<xref:System.Windows.FontNumeralStyle?displayProperty=fullName>|  
|<xref:System.Windows.Documents.Typography.SlashedZero%2A>|<xref:System.Boolean>|`false`|  
|<xref:System.Windows.Documents.Typography.StandardLigatures%2A>|<xref:System.Boolean>|`true`|  
|<xref:System.Windows.Documents.Typography.StandardSwashes%2A>|numerischen Wert – Byte|0|  
|<xref:System.Windows.Documents.Typography.StylisticAlternates%2A>|numerischen Wert – Byte|0|  
|<xref:System.Windows.Documents.Typography.StylisticSet1%2A>|<xref:System.Boolean>|`false`|  
|<xref:System.Windows.Documents.Typography.StylisticSet2%2A>|<xref:System.Boolean>|`false`|  
|<xref:System.Windows.Documents.Typography.StylisticSet3%2A>|<xref:System.Boolean>|`false`|  
|<xref:System.Windows.Documents.Typography.StylisticSet4%2A>|<xref:System.Boolean>|`false`|  
|<xref:System.Windows.Documents.Typography.StylisticSet5%2A>|<xref:System.Boolean>|`false`|  
|<xref:System.Windows.Documents.Typography.StylisticSet6%2A>|<xref:System.Boolean>|`false`|  
|<xref:System.Windows.Documents.Typography.StylisticSet7%2A>|<xref:System.Boolean>|`false`|  
|<xref:System.Windows.Documents.Typography.StylisticSet8%2A>|<xref:System.Boolean>|`false`|  
|<xref:System.Windows.Documents.Typography.StylisticSet9%2A>|<xref:System.Boolean>|`false`|  
|<xref:System.Windows.Documents.Typography.StylisticSet10%2A>|<xref:System.Boolean>|`false`|  
|<xref:System.Windows.Documents.Typography.StylisticSet11%2A>|<xref:System.Boolean>|`false`|  
|<xref:System.Windows.Documents.Typography.StylisticSet12%2A>|<xref:System.Boolean>|`false`|  
|<xref:System.Windows.Documents.Typography.StylisticSet13%2A>|<xref:System.Boolean>|`false`|  
|<xref:System.Windows.Documents.Typography.StylisticSet14%2A>|<xref:System.Boolean>|`false`|  
|<xref:System.Windows.Documents.Typography.StylisticSet15%2A>|<xref:System.Boolean>|`false`|  
|<xref:System.Windows.Documents.Typography.StylisticSet16%2A>|<xref:System.Boolean>|`false`|  
|<xref:System.Windows.Documents.Typography.StylisticSet17%2A>|<xref:System.Boolean>|`false`|  
|<xref:System.Windows.Documents.Typography.StylisticSet18%2A>|<xref:System.Boolean>|`false`|  
|<xref:System.Windows.Documents.Typography.StylisticSet19%2A>|<xref:System.Boolean>|`false`|  
|<xref:System.Windows.Documents.Typography.StylisticSet20%2A>|<xref:System.Boolean>|`false`|  
|<xref:System.Windows.Documents.Typography.Variants%2A>|<xref:System.Windows.FontVariants> | <xref:System.Windows.FontVariants> | <xref:System.Windows.FontVariants> | <xref:System.Windows.FontVariants> | <xref:System.Windows.FontVariants> | <xref:System.Windows.FontVariants>|<xref:System.Windows.FontVariants?displayProperty=fullName>|  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Windows.Documents.Typography>   
 [OpenType-Spezifikation](http://go.microsoft.com/fwlink/?LinkId=96731)   
 [Typografie in WPF](../../../../docs/framework/wpf/advanced/typography-in-wpf.md)   
 [Beispielschriftartenpaket](../../../../docs/framework/wpf/advanced/sample-opentype-font-pack.md)   
 [Verpacken von Schriftarten mit Anwendungen](../../../../docs/framework/wpf/advanced/packaging-fonts-with-applications.md)