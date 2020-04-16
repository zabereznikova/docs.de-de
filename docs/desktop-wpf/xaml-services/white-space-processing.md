---
title: Leerstellenverarbeitung in XAML
ms.date: 03/30/2017
helpviewer_keywords:
- East Asian characters [XAML Services]
- XAML [XAML Services], white-space processing
- white-space processing in XAML [XAML Services]
- characters [XAML Services], East Asian
ms.assetid: cc9cc377-7544-4fd0-b65b-117b90bb0b23
ms.openlocfilehash: 05f28c9115326424164b92e1b704c52bba31cf35
ms.sourcegitcommit: c2d9718996402993cf31541f11e95531bc68bad0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/27/2020
ms.locfileid: "81432845"
---
# <a name="white-space-processing-in-xaml"></a>Leerstellenverarbeitung in XAML

Die Sprachregeln für XAML geben an, dass [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] erheblicher Leerraum von einer Prozessorimplementierung verarbeitet werden muss. Dieser Artikel dokumentiert diese XAML-Sprachregeln. Darüber hinaus wird eine zusätzliche Leerraumbehandlung [!INCLUDE[TLA#tla_winclient](../../../includes/tlasharptla-winclient-md.md)] dokumentiert, die durch die Implementierung des XAML-Prozessors und des XAML-Writers für die Serialisierung definiert wird.

## <a name="white-space-definition"></a>Leerraumdefinition

Konsistent mit XML sind Leerraumzeichen in [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] Leerzeichen, Zeilenvorschub und Registerkarte. Diese entsprechen den Unicode-Werten 0020, 000A und 0009.

## <a name="white-space-normalization"></a>Leerraumnormalisierung

Standardmäßig tritt die folgende Leerraumnormalisierung [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] auf, [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] wenn ein Prozessor eine Datei verarbeitet:

1. Zeilenvorschubzeichen zwischen ostasiatischen Zeichen werden entfernt. Eine Definition dieses Begriffs finden Sie im Abschnitt „Ostasiatische Zeichen“ weiter hinten in diesem Thema.

2. Alle Leerraumzeichen (Leerzeichen, Zeilenvorschub, Tab) werden in Leerzeichen konvertiert.

3. Alle aufeinander folgenden Leerzeichen werden gelöscht und durch ein Leerzeichen ersetzt.

4. Ein Leerzeichen unmittelbar nach dem Starttag wird gelöscht.

5. Ein Leerzeichen unmittelbar vor dem Endtag wird gelöscht.

„Standard“ entspricht dem Zustand, der durch den Standardwert des [xml:space](xml-space-handling.md) -Attribut bezeichnet wird.

## <a name="white-space-in-inner-text-and-string-primitives"></a>Leerraum im inneren Text und Zeichenfolgenprimitive

Die oben genannten Normalisierungsregeln gelten für inneren Text innerhalb von XAML-Elementen. Nach der Normalisierung konvertiert ein XAML-Prozessor inneren Text wie folgt in einen entsprechenden Typ:

- Wenn der Typ der Eigenschaft keine Auflistung, aber nicht direkt ein <xref:System.Object> -Typ ist, versucht der XAML-Prozessor, unter Verwendung seines Typkonverters eine Konvertierung in diesen Typ durchzuführen. Ein Konvertierungsfehler verursacht einen Fehler zu Kompilierzeit.

- Wenn der Typ der Eigenschaft eine Auflistung und der innere Text zusammenhängend ist (keine dazwischen liegenden Elementtags), wird der innere Text als einzelner <xref:System.String>analysiert. Wenn der Auflistungstyp <xref:System.String>nicht akzeptieren kann, führt dies ebenfalls zu einem Kompilierzeitfehler.

- Wenn der Typ der Eigenschaft <xref:System.Object>ist, wird der innere Text als einzelner <xref:System.String>analysiert. Wenn dazwischen liegende Elementtags vorhanden sind, führt dies zu einem Kompilierzeitfehler, da der <xref:System.Object> -Typ ein einzelnes Objekt impliziert (<xref:System.String> oder anderes).

- Wenn der Typ der Eigenschaft eine Auflistung und der innere Text nicht zusammenhängend ist, wird die erste Teilzeichenfolge in einen <xref:System.String> konvertiert und als Auflistungselement hinzugefügt, das dazwischen liegende Element wird als Auflistungselement hinzugefügt, und schließlich wird die nachgestellte Teilzeichenfolge (sofern vorhanden) der Auflistung als drittes <xref:System.String> -Element hinzugefügt.

## <a name="preserving-white-space"></a>Erhaltung des Leerraums

Es gibt mehrere Techniken zum Beibehalten [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] von Leerraum in der [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] Quelle für eine eventuelle Präsentation, die nicht von der Normalisierung des Prozessor-Leerraums betroffen sind.

**xml:space="preserve"**: Geben Sie dieses Attribut auf der Ebene des Elements an, in dem die Leerraumerhaltung gewünscht wird. Hierdurch werden alle Leerräume beibehalten, auch die Leerzeichen, die ggf. von Codebearbeitungsanwendungen als visuell intuitive Schachtelung hinzugefügt werden, um Elemente für den Schöndruck auszurichten. Ob diese Leerzeichen gerendert werden, wird jedoch durch das Inhaltsmodell für das enthaltende Element bestimmt. Vermeiden Sie `xml:space="preserve"` die Angabe auf Stammebene, da die meisten Objektmodelle Leerraum nicht als signifikant betrachten, unabhängig davon, wie Sie das Attribut festlegen. Die globale Festlegung von `xml:space` kann in einigen Implementierungen die Leistung der XAML-Verarbeitung (insbesondere der Serialisierung) beeinträchtigen. Es ist eine bessere Methode, das Attribut nur speziell auf der Ebene von Elementen festzulegen, die Leerraum in Zeichenfolgen rendern oder wichtige Sammlungen im Leerraum sind.

**Entitäten und nicht brechende Leerzeichen:** [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] Unterstützt das Platzieren einer beliebigen Unicode-Entität in einem Textobjektmodell. Sie können dedizierte Entitäten wie leerstehendes Leerzeichen (&\#160; in utF-8-Codierung) verwenden. Sie können auch Rich-Text-Steuerelemente verwenden, die geschützte Leerzeichen unterstützen. Seien Sie vorsichtig, wenn Sie Entitäten zum Simulieren von Layouteigenschaften wie Einzügen verwenden, da die Laufzeitausgabe der Entitäten basierend auf einer größeren Anzahl von Faktoren variiert, als dies bei den Funktionen zum Erzeugen von Einzugsergebnisse in einem typischen Layoutsystem der Fall ist, z. B. richtige Verwendung von Bereichen und Rändern. Beispielsweise werden Entitäten Schriftarten zugeordnet und können sich als Reaktion auf eine Schriftartauswahl durch den Benutzer in der Größe ändern.

## <a name="east-asian-characters"></a>Ostasiatische Zeichen

"Ostasiatische Zeichen" ist definiert als ein Satz von Unicode-Zeichenbereichen U+20000 bis U+2FFFD und U+30000 bis U+3FFFD. Diese Teilmenge wird manchmal auch als „CJK-Ideogramme“ bezeichnet. Weitere Informationen finden Sie unter <https://www.unicode.org>.

## <a name="white-space-and-text-content-models"></a>Leerraum- und Textinhaltsmodelle

In der Praxis ist die Erhaltung des Leerraums nur für eine Teilmenge aller möglichen Inhaltsmodelle von Belang. Diese Teilmenge besteht aus Inhaltsmodellen, die eine Form von Singleton- <xref:System.String> -Typ, eine dedizierte <xref:System.String> -Auflistung oder eine Mischung aus <xref:System.String> und anderen Typen in einer <xref:System.Collections.IList> - oder <xref:System.Collections.Generic.ICollection%601> -Auflistung verwenden können.

### <a name="white-space-and-text-content-models-in-wpf"></a>Leerraum- und Textinhaltsmodelle in WPF

Zur Veranschaulichung bezieht sich der Rest dieses Abschnitts auf bestimmte von WPF definierte Typen. Die in diesem Artikel beschriebenen Features für die Leerraumbehandlung sind sowohl für .NET XAML Services als auch für WPF relevant. Um diese Verhaltensweisen in Aktion zu sehen, können Sie mit einigen WPF-XAML-Markups experimentieren, die Ergebnisse in einem Objektdiagramm anzeigen und dann wieder zurück zu Markup serialisieren.

Selbst bei Inhaltsmodellen, die Zeichenfolgen annehmen können, besteht das Standardverhalten in diesen Inhaltsmodellen darin, dass alle leer bleibenden Leerzeichen nicht als signifikant behandelt werden. Nimmt z. <xref:System.Windows.Controls.ListBox> <xref:System.Collections.IList>B. ein , aber der Leerraum <xref:System.Windows.Controls.ListBoxItem>(z. B. Zeilenvorschübe zwischen den einzelnen ) wird nicht beibehalten und nicht gerendert. Wenn Sie versuchen, Zeilenvorschübe als Trennzeichen zwischen Zeichenfolgen für <xref:System.Windows.Controls.ListBoxItem> -Elemente zu verwenden, funktioniert dies nicht; alle durch die Zeilenvorschübe getrennten Zeichenfolgen werden als eine Zeichenfolge und ein Element behandelt.

Die Auflistungen, die Leerraum als signifikant behandeln, sind in der Regel Teil des Flow-Dokumentmodells. Die primäre Auflistung, die das <xref:System.Windows.Documents.InlineCollection>Verhalten zur Leerraumerhaltung unterstützt, ist . Diese Auflistungsklasse wird <xref:System.Windows.Markup.WhitespaceSignificantCollectionAttribute>mit der deklariert; Wenn dieses Attribut gefunden [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] wird, behandelt der Prozessor Leerraum innerhalb der Auflistung als signifikant. Die Kombination `xml:space="preserve"` aus und <xref:System.Windows.Markup.WhitespaceSignificantCollectionAttribute> Leerraum innerhalb einer bezeichneten Auflistung besteht darin, dass der gesamte Leerraum erhalten und gerendert wird. Die Kombination `xml:space="default"` von und <xref:System.Windows.Markup.WhitespaceSignificantCollectionAttribute> Leerraum innerhalb eines verursacht die zuvor beschriebene anfängliche Leerraumnormalisierung, die einen Raum in bestimmten Positionen hinterlässt, und diese Räume werden beibehalten und gerendert. Welches Verhalten Sie bevorzugen, steht Ihnen frei, und Sie sollten `xml:space` selektiv verwenden, um das gewünschte Verhalten zu aktivieren.

Außerdem sollten bestimmte Inlineelemente, die einen Zeilenumbruch in einem Flow-Dokumentmodell konnotieren, absichtlich keinen zusätzlichen Platz einführen, selbst in einer signifikanten Sammlung für leerräumig. Beispielsweise hat <xref:System.Windows.Documents.LineBreak> das Element denselben Zweck \<wie das BR/>-Tag in HTML, und <xref:System.Windows.Documents.LineBreak> für die Lesbarkeit im Markup wird in der Regel ein Element durch einen erstellten Zeilenvorschub von jedem nachfolgenden Text getrennt. Dieser Zeilenvorschub darf nicht zu einem voranstellten Leerzeichen in der nächsten Zeile normalisiert werden. Um dieses Verhalten zu aktivieren, <xref:System.Windows.Documents.LineBreak> wendet <xref:System.Windows.Markup.TrimSurroundingWhitespaceAttribute>die Klassendefinition für [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] das Element die an, die dann vom Prozessor so interpretiert wird, dass die Umgebenzäunung <xref:System.Windows.Documents.LineBreak> des Leerraums immer getrimmt wird.

## <a name="see-also"></a>Weitere Informationen

- [XAML-Übersicht (WPF)](../fundamentals/xaml.md)
- [XML-Zeichenentitäten und XAML](xml-character-entities.md)
- [xml:Raumbehandlung in XAML](xml-space-handling.md)
