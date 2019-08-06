---
title: Leerstellenverarbeitung in XAML
ms.date: 03/30/2017
helpviewer_keywords:
- East Asian characters [XAML Services]
- XAML [XAML Services], white-space processing
- white-space processing in XAML [XAML Services]
- characters [XAML Services], East Asian
ms.assetid: cc9cc377-7544-4fd0-b65b-117b90bb0b23
ms.openlocfilehash: 077f19690d204d3b8f682d01c51feee9e9edbfd4
ms.sourcegitcommit: bbfcc913c275885381820be28f61efcf8e83eecc
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2019
ms.locfileid: "68796814"
---
# <a name="white-space-processing-in-xaml"></a>Leerstellenverarbeitung in XAML
Die Sprachregeln für XAML State, dass signifikanter Leerraum durch eine [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] Prozessor Implementierung verarbeitet werden muss. In diesem Thema werden diese XAML-Sprachregeln erläutert. Außerdem wird eine zusätzliche Leerraum Behandlung dokumentiert, die durch die [!INCLUDE[TLA#tla_winclient](../../../includes/tlasharptla-winclient-md.md)] Implementierung des XAML-Prozessors und des XAML-Writers für die Serialisierung definiert wird.  
  
<a name="whitespace_definition"></a>   
## <a name="white-space-definition"></a>Leerraum Definition  
 Übereinstimmend mit [!INCLUDE[TLA2#tla_xml](../../../includes/tla2sharptla-xml-md.md)]Leerzeichen in [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] sind Leerzeichen, Zeilenvorschub und Tabulator. Diese entsprechen den [!INCLUDE[TLA#tla_unicode](../../../includes/tlasharptla-unicode-md.md)] -Werten 0020, 000A bzw. 0009.  
  
<a name="whitespace_normalization"></a>   
## <a name="white-space-normalization"></a>Leerraum Normalisierung  
 Standardmäßig tritt die folgende leer Raum Normalisierung auf, wenn [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] ein Prozessor eine [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] Datei verarbeitet:  
  
1. Zeilenvorschubzeichen zwischen ostasiatischen Zeichen werden entfernt. Eine Definition dieses Begriffs finden Sie im Abschnitt „Ostasiatische Zeichen“ weiter hinten in diesem Thema.  
  
2. Alle leer Raum Zeichen (Leerzeichen, Zeilenvorschub, Tabulator) werden in Leerzeichen konvertiert.  
  
3. Alle aufeinander folgenden Leerzeichen werden gelöscht und durch ein Leerzeichen ersetzt.  
  
4. Ein Leerzeichen unmittelbar nach dem Starttag wird gelöscht.  
  
5. Ein Leerzeichen unmittelbar vor dem Endtag wird gelöscht.  
  
 „Standard“ entspricht dem Zustand, der durch den Standardwert des [xml:space](xml-space-handling-in-xaml.md) -Attribut bezeichnet wird.  
  
<a name="whitespace_in_inner_text_and_string_primitives"></a>   
## <a name="white-space-in-inner-text-and-string-primitives"></a>Leerraum in innerem Text und Zeichen folgen primitive  
 Die oben genannten Normalisierungsregeln gelten für inneren Text innerhalb von XAML-Elementen. Nach der Normalisierung konvertiert ein XAML-Prozessor inneren Text wie folgt in einen entsprechenden Typ:  
  
- Wenn der Typ der Eigenschaft keine Auflistung, aber nicht direkt ein <xref:System.Object> -Typ ist, versucht der XAML-Prozessor, unter Verwendung seines Typkonverters eine Konvertierung in diesen Typ durchzuführen. Ein Konvertierungsfehler verursacht einen Fehler zu Kompilierzeit.  
  
- Wenn der Typ der Eigenschaft eine Auflistung und der innere Text zusammenhängend ist (keine dazwischen liegenden Elementtags), wird der innere Text als einzelner <xref:System.String>analysiert. Wenn der Auflistungstyp <xref:System.String>nicht akzeptieren kann, führt dies ebenfalls zu einem Kompilierzeitfehler.  
  
- Wenn der Typ der Eigenschaft <xref:System.Object>ist, wird der innere Text als einzelner <xref:System.String>analysiert. Wenn dazwischen liegende Elementtags vorhanden sind, führt dies zu einem Kompilierzeitfehler, da der <xref:System.Object> -Typ ein einzelnes Objekt impliziert (<xref:System.String> oder anderes).  
  
- Wenn der Typ der Eigenschaft eine Auflistung und der innere Text nicht zusammenhängend ist, wird die erste Teilzeichenfolge in einen <xref:System.String> konvertiert und als Auflistungselement hinzugefügt, das dazwischen liegende Element wird als Auflistungselement hinzugefügt, und schließlich wird die nachgestellte Teilzeichenfolge (sofern vorhanden) der Auflistung als drittes <xref:System.String> -Element hinzugefügt.  
  
<a name="preserving_whitespace"></a>   
## <a name="preserving-white-space"></a>Beibehalten von Leerraum  
 Es gibt mehrere Verfahren zum Beibehalten von Leerraum in der [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] Quelle für die letztliche Darstellung, die [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] von der Leerraum Normalisierung des Prozessors nicht betroffen sind.  
  
 **xml:space="preserve"** : Geben Sie dieses Attribut auf der Ebene des Elements an, auf dem die Leerraum Beibehaltung gewünscht ist. Hierdurch werden alle Leerräume beibehalten, auch die Leerzeichen, die ggf. von Codebearbeitungsanwendungen als visuell intuitive Schachtelung hinzugefügt werden, um Elemente für den Schöndruck auszurichten. Ob diese Leerzeichen gerendert werden, wird jedoch durch das Inhaltsmodell für das enthaltende Element bestimmt. Vermeiden Sie `xml:space="preserve"` die Angabe von auf der Stamm Ebene, da die meisten Objekt Modelle Leerzeichen nicht als signifikant betrachten, unabhängig davon, wie Sie das Attribut festlegen. Die globale Festlegung von `xml:space` kann in einigen Implementierungen die Leistung der XAML-Verarbeitung (insbesondere der Serialisierung) beeinträchtigen. Es empfiehlt sich, das-Attribut nur auf der Ebene der Elemente festzulegen, die Leerzeichen innerhalb von Zeichen folgen darstellen, oder es handelt sich um eine bedeutende Auflistung von Leerraum.  
  
 **Entitäten und geschützte Leerzeichen**: [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] unterstützt das Platzieren beliebiger [!INCLUDE[TLA#tla_unicode](../../../includes/tlasharptla-unicode-md.md)] -Entitäten in einem Textobjektmodell. Sie können dedizierte Entitäten wie z. b. einen\#nicht unterbrechenden Bereich verwenden (& 160; in UTF-8-Codierung) Sie können auch Rich-Text-Steuerelemente verwenden, die geschützte Leerzeichen unterstützen. Seien Sie vorsichtig, wenn Sie Entitäten zum Simulieren von Layouteigenschaften wie Einzügen verwenden, da die Laufzeitausgabe der Entitäten basierend auf einer größeren Anzahl von Faktoren variiert, als dies bei den Funktionen zum Erzeugen von Einzugsergebnisse in einem typischen Layoutsystem der Fall ist, z. B. richtige Verwendung von Bereichen und Rändern. Beispielsweise werden Entitäten Schriftarten zugeordnet und können sich als Reaktion auf eine Schriftartauswahl durch den Benutzer in der Größe ändern.  
  
<a name="east_asian_characters"></a>   
## <a name="east-asian-characters"></a>Ostasiatische Zeichen  
 Unter „ostasiatischen Zeichen“ versteht man einen Satz von [!INCLUDE[TLA2#tla_unicode](../../../includes/tla2sharptla-unicode-md.md)] -Zeichen in den Bereichen von U+20000 bis U+2FFFD und U+30000 bis U+3FFFD. Diese Teilmenge wird manchmal auch als „CJK-Ideogramme“ bezeichnet. Weitere Informationen finden Sie unter <https://www.unicode.org>.  
  
<a name="whitespace_and_text_content_models"></a>   
## <a name="white-space-and-text-content-models"></a>Leerraum-und Text Inhalts Modelle  
 In der Praxis ist das Beibehalten von Leerräumen nur für eine Teilmenge aller möglichen Inhalts Modelle von Bedeutung. Diese Teilmenge besteht aus Inhaltsmodellen, die eine Form von Singleton- <xref:System.String> -Typ, eine dedizierte <xref:System.String> -Auflistung oder eine Mischung aus <xref:System.String> und anderen Typen in einer <xref:System.Collections.IList> - oder <xref:System.Collections.Generic.ICollection%601> -Auflistung verwenden können.  
  
### <a name="white-space-and-text-content-models-in-wpf"></a>Leerraum-und Text Inhalts Modelle in WPF  
 Zur Veranschaulichung bezieht sich der Rest dieses Abschnitts auf bestimmte von WPF definierte Typen. Die in diesem Thema beschriebenen Funktionen zur Behandlung von Leerzeichen sind in der Regel sowohl für .NET Framework XAML-Dienste als auch für WPF relevant. Um diese Verhaltensweisen in Aktion zu sehen, können Sie mit einigen WPF-XAML-Markups experimentieren, die Ergebnisse in einem Objektdiagramm anzeigen und dann wieder zurück zu Markup serialisieren.  
  
 Sogar für Inhalts Modelle, die Zeichen folgen verwenden können, besteht das Standardverhalten innerhalb dieser Inhalts Modelle darin, dass alle verbleibenden Leerräume nicht als signifikant behandelt werden. Beispielsweise <xref:System.Windows.Controls.ListBox> <xref:System.Windows.Controls.ListBoxItem>wird von angenommen, aber der Leerraum (z. b. Zeilen Vorschübe zwischen den einzelnen) wird nicht beibehalten und nicht gerendert. <xref:System.Collections.IList> Wenn Sie versuchen, Zeilenvorschübe als Trennzeichen zwischen Zeichenfolgen für <xref:System.Windows.Controls.ListBoxItem> -Elemente zu verwenden, funktioniert dies nicht; alle durch die Zeilenvorschübe getrennten Zeichenfolgen werden als eine Zeichenfolge und ein Element behandelt.  
  
 Diese Auflistungen, die Leerräume als signifikant behandeln, sind in der Regel Teil des Fluss Dokument Modells. Die primäre Auflistung, die das Verhalten der leer Raum Beibehaltung <xref:System.Windows.Documents.InlineCollection>unterstützt, ist. Diese Auflistungs Klasse wird mit <xref:System.Windows.Markup.WhitespaceSignificantCollectionAttribute>dem deklariert; wenn dieses Attribut gefunden wird [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] , behandelt der Prozessor Leerraum in der Auflistung als signifikant. Die Kombination `xml:space="preserve"` aus und Leerraum innerhalb <xref:System.Windows.Markup.WhitespaceSignificantCollectionAttribute> einer bezeichneten Auflistung besteht darin, dass alle Leerräume beibehalten und gerendert werden. Die Kombination `xml:space="default"` aus-und-Leerraum in einem <xref:System.Windows.Markup.WhitespaceSignificantCollectionAttribute> bewirkt die oben beschriebene anfängliche leer Raum Normalisierung, die ein Leerzeichen an bestimmten Positionen verlässt. diese Leerzeichen werden beibehalten und gerendert. Welches Verhalten Sie bevorzugen, steht Ihnen frei, und Sie sollten `xml:space` selektiv verwenden, um das gewünschte Verhalten zu aktivieren.  
  
 Außerdem sollten bestimmte Inline Elemente, die einen LineBreak in einem Fluss Dokument Modell darstellen, absichtlich keinen zusätzlichen Platz in einer signifikanten Auflistung mit Leerraum einführen. Das <xref:System.Windows.Documents.LineBreak> -Element hat z. b. den gleichen Zweck \<wie das BR/>-Tag in HTML, und zur besseren Lesbarkeit in Markup <xref:System.Windows.Documents.LineBreak> wird ein von einem erstellten Zeilenvorschub in der Regel von jedem nachfolgenden Text getrennt. Dieser Zeilenvorschub darf nicht zu einem voranstellten Leerzeichen in der nächsten Zeile normalisiert werden. Um dieses Verhalten zu aktivieren, wendet die Klassendefinition <xref:System.Windows.Documents.LineBreak> für das- <xref:System.Windows.Markup.TrimSurroundingWhitespaceAttribute>Element das an, das dann vom [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] Prozessor interpretiert wird, um zu bedeuten <xref:System.Windows.Documents.LineBreak> , dass Leerraum immer gekürzt wird.  
  
## <a name="see-also"></a>Siehe auch

- [Übersicht über XAML (WPF)](../wpf/advanced/xaml-overview-wpf.md)
- [XML-Zeichen Entitäten und XAML](xml-character-entities-and-xaml.md)
- [XML: space-Behandlung in XAML](xml-space-handling-in-xaml.md)
