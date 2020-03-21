---
title: Features für OpenType-Schriftarten
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- fonts [WPF], OpenType
- typography [WPF], OpenType font technology
- OpenType font technology [WPF]
ms.assetid: 4061a9d1-fe8b-4921-9e17-18ec7d2e3ea2
ms.openlocfilehash: 52fe73bccd625c9508b398874fd6b075af2445e0
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79186804"
---
# <a name="opentype-font-features"></a>Features für OpenType-Schriftarten

Dieses Thema bietet einen Überblick über einige der wichtigsten [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]Funktionen der OpenType-Schriftarttechnologie in .  
  
<a name="overview"></a>
## <a name="opentype-font-format"></a>OpenType-Schriftartformat  
 Das OpenType-Schriftartformat ist eine Erweiterung des TrueType®-Schriftartformats, das PostScript-Schriftartdaten unterstützt. Das OpenType-Schriftartformat wurde gemeinsam von Microsoft und Adobe Corporation entwickelt. OpenType-Schriftarten und die Betriebssystemdienste, die OpenType-Schriftarten unterstützen, bieten Benutzern eine einfache Möglichkeit, Schriftarten zu installieren und zu verwenden, unabhängig davon, ob die Schriftarten TrueType-Umrisse oder CFF-Umrisse (PostScript) enthalten.  
  
 Das OpenType-Schriftartformat behebt die folgenden Entwicklerherausforderungen:  
  
- Breitere Multiplattform-Unterstützung.  
  
- Bessere Unterstützung für internationale Zeichensätze.  
  
- Besserer Schutz der Schriftartdaten.  
  
- Kleinere Dateigrößen die eine effizientere Schriftartenverteilung ermöglichen.  
  
- Breitere Unterstützung für erweiterte typografische Steuerelement.  
  
> [!NOTE]
> Das Windows SDK enthält eine Reihe von OpenType-Beispielschriftarten, die Sie mit [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] Anwendungen verwenden können. Diese Schriftarten bieten die meisten der Funktionen, wie im folgenden Thema dargestellt. Weitere Informationen finden Sie unter [Beispiel OpenType Font Pack](sample-opentype-font-pack.md).  
  
Weitere Informationen zum OpenType-Schriftartformat finden Sie in der [OpenType-Spezifikation](https://docs.microsoft.com/typography/opentype/spec/).  
  
### <a name="advanced-typographic-extensions"></a>Erweiterte typografische Funktionen  
 Die erweiterten typografischen Tabellen (OpenType Layout-Tabellen) erweitern die Funktionalität von Schriftarten mit TrueType- oder CFF-Umrissen. OpenType Layout-Schriftarten enthalten zusätzliche Informationen, die die Funktionen der Schriftarten erweitern, um hochwertige internationale Typografie zu unterstützen. Die meisten OpenType-Schriftarten machen nur eine Teilmenge der gesamten OpenType-Funktionen verfügbar. OpenType-Schriftarten bieten die folgenden Funktionen.  
  
- Umfangreiche Zuordnung zwischen Zeichen und Symbolen, die Ligaturen, positionelle Formen, alternative Stile und andere Schriftartersetzungen unterstützen.  
  
- Unterstützung von zweidimensionaler Positionierung und Symbolanfügung.  
  
- Explizite Skript- und Sprachinformationen, die in der Schriftart enthalten sind, damit Textverarbeitungsanwendungen ihr Verhalten entsprechend anpassen können.  
  
 Die OpenType-Layouttabellen werden im Abschnitt ["Font File Tables"](https://www.microsoft.com/typography/otspec/otff.htm) der OpenType-Spezifikation ausführlicher beschrieben.  
  
 Der Rest dieser Übersicht stellt die Breite und Flexibilität einiger visuell interessanter OpenType-Features vor, die von den Eigenschaften des <xref:System.Windows.Documents.Typography> Objekts verfügbar gemacht werden. Weitere Informationen über dieses Objekt finden Sie unter [Typografieklasse](#typography_class).  
  
<a name="variants"></a>
## <a name="variants"></a>Varianten  
 Varianten werden verwendet, um verschiedene typographische Formate zu rendern, z.B. hoch- und tiefgestellte Zeichen.  
  
### <a name="superscripts-and-subscripts"></a>Hoch- und tiefgestellte Zeichen  
 Mit <xref:System.Windows.Documents.Typography.Variants%2A> der Eigenschaft können Sie hoch- und subscript-Werte für eine OpenType-Schriftart festlegen.  
  
 Der folgende Text zeigt hochgestellte Zeichen für die Schriftart Palatino Linotype.  
  
 ![Text mit hochgestellten OpenType-Zeichen](./media/opentype-font-features/opentype-superscripts.gif "Text mit hochgestellten OpenType-Zeichen")  
  
 Das folgende Markupbeispiel zeigt, wie Hochlegende für die Palatino <xref:System.Windows.Documents.Typography> Linotype-Schriftart mithilfe von Eigenschaften des Objekts definiert werden.  
  
 [!code-xaml[OpenTypeFontSamples#12](~/samples/snippets/csharp/VS_Snippets_Wpf/OpenTypeFontSamples/CS/PageOne.xaml#12)]  
  
 Der folgende Text zeigt tiefgestellte Zeichen für die Schriftart Palatino Linotype.  
  
 ![Text mit tiefgestellten OpenType-Zeichen](./media/opentype-font-features/opentype-subscripts.gif "Text mit tiefgestellten OpenType-Zeichen")  
  
 Das folgende Markupbeispiel zeigt, wie Subskriptionen für die Palatino <xref:System.Windows.Documents.Typography> Linotype-Schriftart mithilfe von Eigenschaften des Objekts definiert werden.  
  
 [!code-xaml[OpenTypeFontSamples#13](~/samples/snippets/csharp/VS_Snippets_Wpf/OpenTypeFontSamples/CS/PageOne.xaml#13)]  
  
### <a name="decorative-uses-of-superscripts-and-subscripts"></a>Dekorative Verwendung von hoch- und tiefgestellten Zeichen  
 Hoch- und tiefgestellte Zeichen können auch verwendet werden, um mit Groß- und Kleinbuchstaben aus einem Text dekorative Effekte zu erzielen. Der folgende Text zeigt hoch- und tiefgestellte Zeichen für die Schriftart Palatino Linotype. Beachten Sie, dass Großbuchstaben nicht beeinflusst werden.  
  
 ![Text mit hoch- und tiefgestellten Zeichen im OpenType-Format](./media/opentype-font-features/opentype-superscripts-subscripts.gif "Text mit hoch- und tiefgestellten OpenType-Zeichen")  

 Das folgende Markupbeispiel zeigt, wie Hochschreibungen und Subskriptionen für <xref:System.Windows.Documents.Typography> eine Schriftart mithilfe von Eigenschaften des Objekts definiert werden.  
  
 [!code-xaml[OpenTypeFontSamples#14](~/samples/snippets/csharp/VS_Snippets_Wpf/OpenTypeFontSamples/CS/PageOne.xaml#14)]  
  
<a name="capitals"></a>
## <a name="capitals"></a>Großbuchstaben  
 Großbuchstaben sind ein Satz typografischer Formen, bei dem Text mit Symbolen gerendert wird, die als Großbuchstaben formatiert sind. Wenn Text ausschließlich in Großbuchstaben gerendert wird, kann der Abstand zwischen den Buchstaben als zu gering, die Breite der Buchstaben als zu groß und die Proportionen der Buchstaben als zu unausgewogen erscheinen. OpenType unterstützt eine Reihe von Styling-Formaten für Großbuchstaben, einschließlich kleiner Großbuchstaben, zierlicher Großbuchstaben, Titling und Kapitalabstand. Mit diesen Formatierungen kann die Darstellung von Großbuchstaben gesteuert werden.  
  
 Der folgende Text zeigt zuerst die Standardgroßbuchstaben, gefolgt von den Buchstaben in den Formaten „SmallCaps“ und „AllSmallCaps“ für die Schriftart Pescadero. Für alle drei Wörter wird der gleiche Schriftgrad verwendet.  
  
 ![Text mit OpenType-Kapitälchen](./media/opentype-font-features/opentype-capitals.gif "Text mit OpenType-Kapitälchen")  
  
 Das folgende Markupbeispiel zeigt, wie Großbuchstaben für die Pescadero-Schriftart mithilfe von Eigenschaften des <xref:System.Windows.Documents.Typography> Objekts definiert werden. Wenn das „SmallCaps“-Format verwendet wird, werden führende Großbuchstaben ignoriert.  
  
 [!code-xaml[OpenTypeFontSamples#9](~/samples/snippets/csharp/VS_Snippets_Wpf/OpenTypeFontSamples/CS/PageOne.xaml#9)]  
  
### <a name="titling-capitals"></a>Großbuchstaben für Titel  
 Großbuchstaben für Titel sind weniger stark ausgebildet und proportioniert und sollen im Vergleich zu normalen Großbuchstaben eine elegantere Darstellungsweise sicherstellen. Großbuchstaben für Titel werden üblicherweise mit größeren Schriftgraden in Überschriften verwendet. Der folgende Text zeigt normale Großbuchstaben und Großbuchstaben für Titel für die Schriftart Pescadero. Beachten Sie die geringeren Strichstärken des Texts in der zweiten Zeile.  
  
 ![Text mit OpenType-Initialen](./media/opentype-font-features/opentype-titling-capitals.gif "Text mit OpenType-Initialen")  
  
 Das folgende Markupbeispiel zeigt, wie Titling-Großbuchstaben für die Pescadero-Schriftart mithilfe von Eigenschaften des <xref:System.Windows.Documents.Typography> Objekts definiert werden.  
  
 [!code-xaml[OpenTypeFontSamples#OpenTypeFontSnippet17](~/samples/snippets/csharp/VS_Snippets_Wpf/OpenTypeFontSamples/CS/PageOne.xaml#opentypefontsnippet17)]  
  
### <a name="capital-spacing"></a>Großbuchstabenabstand  
 Der Großbuchstabenabstand ist ein Feature, mit dem Sie in einem Textabschnitt, der ausschließlich aus Großbuchstaben besteht, die Laufweite vergrößern können. Großbuchstaben werden i. d. R. so entworfen, dass sie mit Kleinbuchstaben harmonieren. Ein Abstand, der zwischen einem Großbuchstaben und einem Kleinbuchstaben ästhetisch wirkt, kann zwischen Großbuchstaben zu gering erscheinen. Im folgende Text werden normale Großbuchstaben und Großbuchstaben für Titel für die Schriftart Pescadero gezeigt.  
  
 ![Text mit OpenType-Kapitälchenabstand](./media/opentype-font-features/opentype-capital-spacing.gif "Text mit OpenType-Kapitälchenabstand")  

 Das folgende Markupbeispiel zeigt, wie Sie den Großbuchstabenabstand für die <xref:System.Windows.Documents.Typography> Pescadero-Schriftart mithilfe von Eigenschaften des Objekts definieren.  
  
 [!code-xaml[OpenTypeFontSamples#OpenTypeFontSnippet18](~/samples/snippets/csharp/VS_Snippets_Wpf/OpenTypeFontSamples/CS/PageOne.xaml#opentypefontsnippet18)]  
  
<a name="ligatures"></a>
## <a name="ligatures"></a>Ligaturen  
 Ligaturen sind zwei oder mehr Symbole, die zu einem einzigen Symbol zusammengefügt werden, um einen besser lesbaren oder attraktiveren Text zu erstellen. OpenType-Schriftarten unterstützen vier Ligaturentypen:  
  
- **Standardligaturen**. Zur Verbesserung der Lesbarkeit. Zu den Standardligaturen gehören „fi“, „fl“ und „ff“.  
  
- **Kontextbedingte Ligaturen**. Mit Kontextligaturen soll die Lesbarkeit verbessert werden, indem die Buchstaben einer Ligatur optimal verbunden werden.  
  
- **Bedingte Ligaturen**. Bedingte Ligaturen sollen verzierend wirken, wobei die Lesbarkeit eine untergeordnete Rolle spielt.  
  
- **Historische Ligaturen**. Historische Ligaturen sollen eine historische Wirkung erzielen, wobei die Lesbarkeit eine untergeordnete Rolle spielt.  
  
 Im folgenden Text werden Symbole für Standardligaturen in der Schriftart Pericles gezeigt.  
  
 ![Text mit OpenType-Standardligaturen](./media/opentype-font-features/opentype-standard-ligatures.gif "Text mit OpenType-Standardligaturen")  
  
 Das folgende Markupbeispiel zeigt, wie Sie Standardligatur-Glyphen für die <xref:System.Windows.Documents.Typography> Pericles-Schriftart mithilfe von Eigenschaften des Objekts definieren.  
  
 [!code-xaml[OpenTypeFontSamples#4](~/samples/snippets/csharp/VS_Snippets_Wpf/OpenTypeFontSamples/CS/PageOne.xaml#4)]  
  
 Im folgenden Text werden Symbole für bedingte Ligaturen in der Schriftart Pericles gezeigt.  
  
 ![Text mit bedingten OpenType-Ligaturen](./media/opentype-font-features/opentype-discretionary-ligatures.gif "Text mit bedingten OpenType-Ligaturen")  
  
 Das folgende Markupbeispiel zeigt, wie diskretionäre Ligatur-Glyphen für die <xref:System.Windows.Documents.Typography> Pericles-Schriftart mithilfe von Eigenschaften des Objekts definiert werden.  
  
 [!code-xaml[OpenTypeFontSamples#5](~/samples/snippets/csharp/VS_Snippets_Wpf/OpenTypeFontSamples/CS/PageOne.xaml#5)]  
  
 Standardmäßig aktivieren OpenType-Schriftarten in [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] Standardligaturen. Wenn Sie beispielsweise die Schriftart Palatino Linotype verwenden, werden die Standardligaturen „fi“, „ff“ und „fl“ als kombiniertes Zeichensymbol angezeigt. Dabei berühren die beiden Zeichen einer Standardligatur einander.  
  
 ![Text mit OpenType-Standardligaturen mit Palatino Linotype](./media/opentype-font-features/opentype-standard-ligatures-palatino.gif "Text mit OpenType-Standardligaturen mit Palatino Linotype")

 Allerdings können Sie die Features für Standardligaturen auch deaktivieren, sodass z.B. die Standardligatur „ff“ nicht als kombiniertes Zeichensymbol, sondern als zwei einzelne Symbole angezeigt wird.  
  
 ![Text mit deaktivierten OpenType-Standardligaturen](./media/opentype-font-features/disabled-opentype-standard-ligatures.gif "Text mit deaktivierten OpenType-Standardligaturen")  

 Das folgende Markupbeispiel zeigt, wie Sie Standardligatur-Glyphen für die <xref:System.Windows.Documents.Typography> Palatino-Linotype-Schriftart mithilfe von Eigenschaften des Objekts deaktivieren.  
  
 [!code-xaml[OpenTypeFontSamples#6](~/samples/snippets/csharp/VS_Snippets_Wpf/OpenTypeFontSamples/CS/PageOne.xaml#6)]  
  
<a name="swashes"></a>
## <a name="swashes"></a>Schwünge  
 Schwungschrift besteht aus dekorativen Symbolen, deren ausgefeilte Verzierung häufig mit Kalligraphie assoziiert wird. Im folgenden Text werden Standard- und Schwungsymbole für die Schriftart Pescadero gezeigt.  
  
 ![Text mit OpenType-Standard- und Ziersymbolen](./media/opentype-font-features/opentype-standard-swash-glyphs.gif "Text mit OpenType-Standard- und Ziersymbolen")  

 Schwungschrift wird häufig als dekoratives Element in kurzen Sätzen verwendet, z.B. in Veranstaltungsankündigungen. Im folgenden Text werden die Großbuchstaben eines Veranstaltungstitels mit Schwungschrift hervorgehoben.  
  
 ![Text mit OpenType-Zierbuchstaben](./media/opentype-font-features/opentype-swashes.gif "Text mit OpenType-Zierbuchstaben")  
  
 Das folgende Markupbeispiel zeigt, wie Sie Mithilfe von Swashes für eine Schriftart mithilfe von Eigenschaften des <xref:System.Windows.Documents.Typography> Objekts definieren.  
  
 [!code-xaml[OpenTypeFontSamples#7](~/samples/snippets/csharp/VS_Snippets_Wpf/OpenTypeFontSamples/CS/PageOne.xaml#7)]  
  
### <a name="contextual-swashes"></a>Kontextbedingte Schwungschrift  
 Bestimmte Kombinationen von Symbolen in Schwungschrift können unästhetisch wirken, z.B. sich überschneidende Unterlängen bei aufeinander folgenden Buchstaben. Mit kontextbedingter Schwungschrift können Sie Varianten eines Symbols in Schwungschrift verwenden, deren Darstellung dann ästhetischer wirkt. Im folgenden Text wird das gleiche Wort vor und nach dem Übernehmen einer kontextbedingten Variante für die Schwungschrift gezeigt.  
  
 ![Text mit kontextbezogenen OpenType-Zierbuchstaben](./media/opentype-font-features/opentype-contextual-swashes.gif "Text mit kontextbezogenen OpenType-Zierbuchstaben")  
  
 Das folgende Markupbeispiel zeigt, wie Sie mithilfe von Eigenschaften des <xref:System.Windows.Documents.Typography> Objekts einen kontextbezogenen Swash für die Pescadero-Schriftart definieren.  
  
 [!code-xaml[OpenTypeFontSamples#OpenTypeFontSnippet16](~/samples/snippets/csharp/VS_Snippets_Wpf/OpenTypeFontSamples/CS/PageOne.xaml#opentypefontsnippet16)]  
  
<a name="alternates"></a>
## <a name="alternates"></a>Alternative Stile  
 Alternative Stilvarianten sind Symbole, die ein Standardsymbol ersetzen können. OpenType-Schriftarten, wie die in den folgenden Beispielen verwendete Pericles-Schriftart, können alternative Glyphen enthalten, mit denen Sie unterschiedliche Darstellungen für Text erstellen können. Im folgenden Text werden die Standardsymbole der Schriftart Pericles dargestellt.  
  
 ![Text mit OpenType-Standardsymbolen](./media/opentype-font-features/opentype-standard-glyphs.gif "Text mit OpenType-Standardsymbolen")  

 Die Pericles OpenType-Schriftart enthält zusätzliche Glyphen, die stilistische Alternativen zum Standardsatz von Glyphen bieten. Im folgenden Text werden Symbole im alternativen Stil gezeigt.  
  
 ![Text mit alternativen OpenType-Stilsymbolen](./media/opentype-font-features/opentype-stylistic-alternate-glyphs.gif "Text mit alternativen OpenType-Stilsymbolen")  
  
 Das folgende Markupbeispiel zeigt, wie sie stilistische alternative Glyphen für <xref:System.Windows.Documents.Typography> die Pericles-Schriftart mithilfe von Eigenschaften des Objekts definieren.  
  
 [!code-xaml[OpenTypeFontSamples#2](~/samples/snippets/csharp/VS_Snippets_Wpf/OpenTypeFontSamples/CS/PageOne.xaml#2)]  
  
 Im folgenden Text werden verschiedene Symbole im alternativen Stil in der Schriftart Pericles gezeigt.  
  
 ![Text mit OpenType-Stilalternativen-Glyphen für die Pericles-Schriftart](./media/opentype-font-features/opentype-stylistic-alternate-glyphs-pericles.gif "Text mit OpenType-Stilalternativen-Glyphen für die Pericles-Schriftart")

 Im folgenden Markupbeispiel wird veranschaulicht, wie diese zusätzlichen Stilvarianten von Symbolen definiert werden.  
  
 [!code-xaml[OpenTypeFontSamples#3](~/samples/snippets/csharp/VS_Snippets_Wpf/OpenTypeFontSamples/CS/PageOne.xaml#3)]  
  
### <a name="random-contextual-alternates"></a>Zufällige kontextbedingte Varianten  
 Bei zufälligen kontextbedingten Varianten werden mehrere Ersatzsymbole für ein einzelnes Zeichen bereitgestellt. Wenn dieses Feature für handschriftähnliche Schriftarten implementiert ist, kann Handschrift mit einem Satz zufällig ausgewählter Symbole simuliert werden, die leicht unterschiedlich dargestellt werden. Im folgenden Text werden zufällige kontextbedingte Varianten für die Schriftart Lindsey verwendet. Dabei wird der Buchstabe „a“ in der Darstellung leicht abgewandelt.  
  
 ![Text mit willkürlichen kontextbedingten OpenType-Varianten](./media/opentype-font-features/opentype-random-contextual-alternates.gif "Text mit willkürlichen kontextbedingten OpenType-Varianten")  
  
 Das folgende Markupbeispiel zeigt, wie sie zufällige kontextbezogene Alternativen <xref:System.Windows.Documents.Typography> für die Lindsey-Schriftart mithilfe von Eigenschaften des Objekts definieren.  
  
 [!code-xaml[OpenTypeFontSamples#OpenTypeFontSnippet20](~/samples/snippets/csharp/VS_Snippets_Wpf/OpenTypeFontSamples/CS/Window1.xaml#opentypefontsnippet20)]  
  
### <a name="historical-forms"></a>Historische Formen  
 Unter historischen Formen werden der Vergangenheit verbreitete typografische Konventionen verstanden. Im folgenden Text wird „Boston, Massachusetts“ unter Verwendung einer historischen Form der Symbole in der Schriftart Palatino Linotype gezeigt.  
  
 ![Text mit OpenType-Mediävalen](./media/opentype-font-features/opentype-historical-forms.gif "Text mit OpenType-Mediävalen")  

 Das folgende Markupbeispiel zeigt, wie historische Formulare für die Palatino <xref:System.Windows.Documents.Typography> Linotype-Schriftart mithilfe von Eigenschaften des Objekts definiert werden.  
  
 [!code-xaml[OpenTypeFontSamples#8](~/samples/snippets/csharp/VS_Snippets_Wpf/OpenTypeFontSamples/CS/PageOne.xaml#8)]  
  
<a name="numerical_styles"></a>
## <a name="numerical-styles"></a>Numerische Formate  
 OpenType-Schriftarten unterstützen eine große Anzahl von Features, die mit numerischen Werten im Text verwendet werden können.  
  
### <a name="fractions"></a>Brüche  
 OpenType-Schriftarten unterstützen Stile für Brüche, einschließlich geschlitzt und gestapelt.  
  
 Im folgenden Text werden Bruchformate für die Schriftart Palatino Linotype gezeigt.  
  
 ![Text mit OpenType-Brüchen mit schrägem oder waagerechtem Bruchstrich](./media/opentype-font-features/opentype-slashed-stacked-fractions.gif "Text mit OpenType-Brüchen mit schrägem oder waagerechtem Bruchstrich")  

 Das folgende Markupbeispiel zeigt, wie Bruchstile für die Palatino <xref:System.Windows.Documents.Typography> Linotype-Schriftart mithilfe von Eigenschaften des Objekts definiert werden.  
  
 [!code-xaml[OpenTypeFontSamples#10](~/samples/snippets/csharp/VS_Snippets_Wpf/OpenTypeFontSamples/CS/PageOne.xaml#10)]  
  
### <a name="old-style-numerals"></a>Mediävalziffern  
 OpenType-Schriftarten unterstützen ein altes Format der Numeralformate. Dieses Format dient der Anzeige von Ziffern in nicht mehr üblichen Stilen. Im folgenden Text wird ein Datum aus dem 18. Jahrhundert im Standardformat und mit Mediävalziffern in der Schriftart Palatino Linotype gezeigt.  
  
 ![Text mit OpenType-Mediävalziffern](./media/opentype-font-features/opentype-old-style-numerals.gif "Text mit OpenType-Mediävalziffern")  

 Im folgenden Text werden in der Schriftart Palatino Linotype zuerst Standardziffern und dann Mediävalziffern gezeigt.  
  
 ![Text mit OpenType-Mediävalziffernsätzen](./media/opentype-font-features/opentype-old-style-numeral-sets.gif "Text mit OpenType-Mediävalziffernsätzen")  
  
 Das folgende Markupbeispiel zeigt, wie alte Stilziffern für die Palatino Linotype-Schriftart mithilfe von Eigenschaften des <xref:System.Windows.Documents.Typography> Objekts definiert werden.  
  
 [!code-xaml[OpenTypeFontSamples#11](~/samples/snippets/csharp/VS_Snippets_Wpf/OpenTypeFontSamples/CS/PageOne.xaml#11)]  
  
### <a name="proportional-and-tabular-figures"></a>Proportionale Darstellung und Tabellendarstellung  
 OpenType-Schriftarten unterstützen ein proportionales und tabellarisches Abbildungs-Feature, um die Ausrichtung von Breiten bei Verwendung von Ziffern zu steuern. In der proportionalen Darstellung verfügt jede Ziffer über eine eigene Breite: die „1“ ist schmaler als die „5“. In der Tabellendarstellung werden alle Ziffern mit der gleichen Breite dargestellt und vertikal ausgerichtet. Dies verbessert die Lesbarkeit z.B. bei Finanzinformationen.  
  
 Im folgenden Text werden in der ersten Spalte zwei proportionale Zahlen in der Schriftart Miramonte proportional dargestellt. Die Ziffern „5“ und „1“ unterscheiden sich in der Breite. In der zweiten Spalte wurde die Breite der gleichen Zahlen mit dem Feature für die Tabellendarstellung angepasst.  
  
 ![Text mit proportionaler und Tabellendarstellung im OpenType-Format](./media/opentype-font-features/opentype-proportional-tabular-figures.gif "Text mit proportionaler und Tabellendarstellung im OpenType-Format")  

 Das folgende Markupbeispiel zeigt, wie proportionale und tabellarische Zahlen für <xref:System.Windows.Documents.Typography> die Miramonte-Schriftart mithilfe von Eigenschaften des Objekts definiert werden.  
  
 [!code-xaml[OpenTypeFontSamples#OpenTypeFontSnippet19](~/samples/snippets/csharp/VS_Snippets_Wpf/OpenTypeFontSamples/CS/Window1.xaml#opentypefontsnippet19)]  
  
### <a name="slashed-zero"></a>Null mit Schrägstrich  
 OpenType-Schriftarten unterstützen ein gekürztes Null-Zahlenformat, um den Unterschied zwischen dem Buchstaben "O" und der Ziffern "0" hervorzuheben. Die Ziffer 0 (null) mit Schrägstrich wird häufig für Kennungen in Finanz- und Geschäftsinformationen verwendet.  
  
 Im folgenden Text wird ein Beispiel mit einer Bestellnummer in der Schriftart Miramonte gezeigt. In der ersten Zeile werden Standardziffern verwendet. In der zweiten wird die Ziffer 0 (null) mit Schrägstrich verwendet, um die Ziffer 0 (null) optisch besser vom Großbuchstaben „O“ zu unterscheiden.  
  
 ![Text mit OpenType-Ziffern mit null mit Schrägstrich](./media/opentype-font-features/opentype-slashed-zero-numerals.gif "Text mit OpenType-Ziffern mit Null mit Schrägstrich")  

 Das folgende Markupbeispiel zeigt, wie Sie gekürzte Nullziffern für die Miramonte-Schriftart mithilfe von Eigenschaften des <xref:System.Windows.Documents.Typography> Objekts definieren.  
  
 [!code-xaml[OpenTypeFontSamples#OpenTypeFontSnippet15](~/samples/snippets/csharp/VS_Snippets_Wpf/OpenTypeFontSamples/CS/PageOne.xaml#opentypefontsnippet15)]  
  
<a name="typography_class"></a>
## <a name="typography-class"></a>Typografieklasse  
 Das <xref:System.Windows.Documents.Typography> Objekt macht den Satz von Features verfügbar, den eine OpenType-Schriftart unterstützt. Durch Festlegen der <xref:System.Windows.Documents.Typography> Eigenschaften von in Markup können Sie problemlos Dokumente erstellen, die OpenType-Funktionen nutzen.  
  
 Der folgende Text zeigt zuerst die Standardgroßbuchstaben, gefolgt von den Buchstaben in den Formaten „SmallCaps“ und „AllSmallCaps“ für die Schriftart Pescadero. Für alle drei Wörter wird der gleiche Schriftgrad verwendet.  
  
 ![Text mit OpenType-Kapitälchen](./media/opentype-font-features/opentype-capitals.gif "Text mit OpenType-Kapitälchen")  

 Das folgende Markupbeispiel zeigt, wie Großbuchstaben für die Pescadero-Schriftart mithilfe von Eigenschaften des <xref:System.Windows.Documents.Typography> Objekts definiert werden. Wenn das „SmallCaps“-Format verwendet wird, werden führende Großbuchstaben ignoriert.  
  
 [!code-xaml[OpenTypeFontSamples#9](~/samples/snippets/csharp/VS_Snippets_Wpf/OpenTypeFontSamples/CS/PageOne.xaml#9)]  
  
 Im folgenden Codebeispiel wird die gleiche Aufgabe wie im vorherigen Markupbeispiel ausgeführt.  
  
 [!code-csharp[TypographyCodeSnippets#TypographyCodeSnippet1](~/samples/snippets/csharp/VS_Snippets_Wpf/TypographyCodeSnippets/CSharp/Page1.xaml.cs#typographycodesnippet1)]
 [!code-vb[TypographyCodeSnippets#TypographyCodeSnippet1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TypographyCodeSnippets/visualbasic/page1.xaml.vb#typographycodesnippet1)]  
  
### <a name="typography-class-properties"></a>Typografieklasseneigenschaften  
 In der folgenden Tabelle sind die Eigenschaften, <xref:System.Windows.Documents.Typography> Werte und Standardeinstellungen des Objekts aufgeführt.  
  
|Eigenschaft|Wert(e)|Standardwert|  
|--------------|----------------|-------------------|  
|<xref:System.Windows.Documents.Typography.AnnotationAlternates%2A>|Numerischer Wert – Byte|0|  
|<xref:System.Windows.Documents.Typography.Capitals%2A>|<xref:System.Windows.FontCapitals.AllPetiteCaps>&#124; <xref:System.Windows.FontCapitals.AllSmallCaps> <xref:System.Windows.FontCapitals.Normal> &#124; <xref:System.Windows.FontCapitals.PetiteCaps> <xref:System.Windows.FontCapitals.SmallCaps> &#124; <xref:System.Windows.FontCapitals.Titling> &#124; &#124; &#124; &#124; &#124;<xref:System.Windows.FontCapitals.Unicase>|<xref:System.Windows.FontCapitals.Normal?displayProperty=nameWithType>|  
|<xref:System.Windows.Documents.Typography.CapitalSpacing%2A>|<xref:System.Boolean>|`false`|  
|<xref:System.Windows.Documents.Typography.CaseSensitiveForms%2A>|<xref:System.Boolean>|`false`|  
|<xref:System.Windows.Documents.Typography.ContextualAlternates%2A>|<xref:System.Boolean>|`true`|  
|<xref:System.Windows.Documents.Typography.ContextualLigatures%2A>|<xref:System.Boolean>|`true`|  
|<xref:System.Windows.Documents.Typography.ContextualSwashes%2A>|Numerischer Wert – Byte|0|  
|<xref:System.Windows.Documents.Typography.DiscretionaryLigatures%2A>|<xref:System.Boolean>|`false`|  
|<xref:System.Windows.Documents.Typography.EastAsianExpertForms%2A>|<xref:System.Boolean>|`false`|  
|<xref:System.Windows.Documents.Typography.EastAsianLanguage%2A>|<xref:System.Windows.FontEastAsianLanguage.HojoKanji>&#124; <xref:System.Windows.FontEastAsianLanguage.Jis04> <xref:System.Windows.FontEastAsianLanguage.Jis78> &#124; <xref:System.Windows.FontEastAsianLanguage.Jis83> <xref:System.Windows.FontEastAsianLanguage.Jis90> &#124; <xref:System.Windows.FontEastAsianLanguage.NlcKanji> <xref:System.Windows.FontEastAsianLanguage.Normal> &#124; <xref:System.Windows.FontEastAsianLanguage.Simplified> <xref:System.Windows.FontEastAsianLanguage.Traditional> &#124; &#124; &#124; &#124; &#124; &#124; &#124; &#124; &#124; &#124;<xref:System.Windows.FontEastAsianLanguage.TraditionalNames>|<xref:System.Windows.FontEastAsianLanguage.Normal?displayProperty=nameWithType>|  
|<xref:System.Windows.Documents.Typography.EastAsianWidths%2A>|<xref:System.Windows.FontEastAsianWidths.Full>&#124; <xref:System.Windows.FontEastAsianWidths.Half> <xref:System.Windows.FontEastAsianWidths.Normal> &#124; <xref:System.Windows.FontEastAsianWidths.Proportional> <xref:System.Windows.FontEastAsianWidths.Quarter> &#124; &#124; &#124; &#124;<xref:System.Windows.FontEastAsianWidths.Third>|<xref:System.Windows.FontEastAsianWidths.Normal?displayProperty=nameWithType>|  
|<xref:System.Windows.Documents.Typography.Fraction%2A>|<xref:System.Windows.FontFraction.Normal> &#124; <xref:System.Windows.FontFraction.Slashed> &#124; <xref:System.Windows.FontFraction.Stacked>|<xref:System.Windows.FontFraction.Normal?displayProperty=nameWithType>|  
|<xref:System.Windows.Documents.Typography.HistoricalForms%2A>|<xref:System.Boolean>|`false`|  
|<xref:System.Windows.Documents.Typography.HistoricalLigatures%2A>|<xref:System.Boolean>|`false`|  
|<xref:System.Windows.Documents.Typography.Kerning%2A>|<xref:System.Boolean>|`true`|  
|<xref:System.Windows.Documents.Typography.MathematicalGreek%2A>|<xref:System.Boolean>|`false`|  
|<xref:System.Windows.Documents.Typography.NumeralAlignment%2A>|<xref:System.Windows.FontNumeralAlignment.Normal> &#124; <xref:System.Windows.FontNumeralAlignment.Proportional> &#124; <xref:System.Windows.FontNumeralAlignment.Tabular>|<xref:System.Windows.FontNumeralAlignment.Normal?displayProperty=nameWithType>|  
|<xref:System.Windows.Documents.Typography.NumeralStyle%2A>|<xref:System.Boolean>|<xref:System.Windows.FontNumeralStyle.Normal?displayProperty=nameWithType>|  
|<xref:System.Windows.Documents.Typography.SlashedZero%2A>|<xref:System.Boolean>|`false`|  
|<xref:System.Windows.Documents.Typography.StandardLigatures%2A>|<xref:System.Boolean>|`true`|  
|<xref:System.Windows.Documents.Typography.StandardSwashes%2A>|Numerischer Wert – Byte|0|  
|<xref:System.Windows.Documents.Typography.StylisticAlternates%2A>|Numerischer Wert – Byte|0|  
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
|<xref:System.Windows.Documents.Typography.Variants%2A>|<xref:System.Windows.FontVariants.Inferior>&#124; <xref:System.Windows.FontVariants.Normal> <xref:System.Windows.FontVariants.Ordinal> &#124; <xref:System.Windows.FontVariants.Ruby> <xref:System.Windows.FontVariants.Subscript> &#124; &#124; &#124; &#124;<xref:System.Windows.FontVariants.Superscript>|<xref:System.Windows.FontVariants.Normal?displayProperty=nameWithType>|  
  
## <a name="see-also"></a>Weitere Informationen

- <xref:System.Windows.Documents.Typography>
- [OpenType-Spezifikation](https://docs.microsoft.com/typography/opentype/spec/)
- [Typografie in WPF](typography-in-wpf.md)
- [OpenType-Beispielschriftartenpaket](sample-opentype-font-pack.md)
- [Verpacken von Schriftarten mit Anwendungen](packaging-fonts-with-applications.md)
