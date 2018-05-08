---
title: Leerstellenverarbeitung in XAML
ms.date: 03/30/2017
helpviewer_keywords:
- East Asian characters [XAML Services]
- XAML [XAML Services], whitespace processing
- whitespace processing in XAML [XAML Services]
- characters [XAML Services], East Asian
ms.assetid: cc9cc377-7544-4fd0-b65b-117b90bb0b23
ms.openlocfilehash: 9f7d7ca900955b8899322533f9d69338042d88ab
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="whitespace-processing-in-xaml"></a>Leerstellenverarbeitung in XAML
Gemäß den Sprachregeln für XAML müssen signifikante Leerräume von einer [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] -Prozessorimplementierung verarbeitet werden. In diesem Thema werden diese XAML-Sprachregeln erläutert. Außerdem wird die Behandlung zusätzlicher Leerräume erörtert, die durch die [!INCLUDE[TLA#tla_winclient](../../../includes/tlasharptla-winclient-md.md)] -Implementierung des XAML-Prozessors und des XAML-Writers für die Serialisierung definiert wird.  
  
<a name="whitespace_definition"></a>   
## <a name="whitespace-definition"></a>Was ist Leerraum?  
 Gemäß [!INCLUDE[TLA2#tla_xml](../../../includes/tla2sharptla-xml-md.md)]versteht man unter Leerraum in [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] Leerzeichen, Zeilenvorschübe und Tabulatoren. Diese entsprechen den [!INCLUDE[TLA#tla_unicode](../../../includes/tlasharptla-unicode-md.md)]-Werten 0020, 000A bzw. 0009.  
  
<a name="whitespace_normalization"></a>   
## <a name="whitespace-normalization"></a>Normalisierung von Leerraum  
 Standardmäßig findet bei der Verarbeitung einer [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] -Datei durch einen [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] -Prozessor die folgende Leerraumnormalisierung statt:  
  
1.  Zeilenvorschubzeichen zwischen ostasiatischen Zeichen werden entfernt. Eine Definition dieses Begriffs finden Sie im Abschnitt „Ostasiatische Zeichen“ weiter hinten in diesem Thema.  
  
2.  Alle Leerraumzeichen (Leerzeichen, Zeilenvorschub, Tabulator) werden in Leerzeichen konvertiert.  
  
3.  Alle aufeinander folgenden Leerzeichen werden gelöscht und durch ein Leerzeichen ersetzt.  
  
4.  Ein Leerzeichen unmittelbar nach dem Starttag wird gelöscht.  
  
5.  Ein Leerzeichen unmittelbar vor dem Endtag wird gelöscht.  
  
 „Standard“ entspricht dem Zustand, der durch den Standardwert des [xml:space](../../../docs/framework/xaml-services/xml-space-handling-in-xaml.md) -Attribut bezeichnet wird.  
  
<a name="whitespace_in_inner_text_and_string_primitives"></a>   
## <a name="whitespace-in-inner-text-and-string-primitives"></a>Leerraum in innerem Text und Zeichenfolgenprimitive  
 Die oben genannten Normalisierungsregeln gelten für inneren Text innerhalb von XAML-Elementen. Nach der Normalisierung konvertiert ein XAML-Prozessor inneren Text wie folgt in einen entsprechenden Typ:  
  
-   Wenn der Typ der Eigenschaft keine Auflistung, aber nicht direkt ein <xref:System.Object> -Typ ist, versucht der XAML-Prozessor, unter Verwendung seines Typkonverters eine Konvertierung in diesen Typ durchzuführen. Ein Konvertierungsfehler verursacht einen Fehler zu Kompilierzeit.  
  
-   Wenn der Typ der Eigenschaft eine Auflistung und der innere Text zusammenhängend ist (keine dazwischen liegenden Elementtags), wird der innere Text als einzelner <xref:System.String>analysiert. Wenn der Auflistungstyp <xref:System.String>nicht akzeptieren kann, führt dies ebenfalls zu einem Kompilierzeitfehler.  
  
-   Wenn der Typ der Eigenschaft <xref:System.Object>ist, wird der innere Text als einzelner <xref:System.String>analysiert. Wenn dazwischen liegende Elementtags vorhanden sind, führt dies zu einem Kompilierzeitfehler, da der <xref:System.Object> -Typ ein einzelnes Objekt impliziert (<xref:System.String> oder anderes).  
  
-   Wenn der Typ der Eigenschaft eine Auflistung und der innere Text nicht zusammenhängend ist, wird die erste Teilzeichenfolge in einen <xref:System.String> konvertiert und als Auflistungselement hinzugefügt, das dazwischen liegende Element wird als Auflistungselement hinzugefügt, und schließlich wird die nachgestellte Teilzeichenfolge (sofern vorhanden) der Auflistung als drittes <xref:System.String> -Element hinzugefügt.  
  
<a name="preserving_whitespace"></a>   
## <a name="preserving-whitespace"></a>Beibehalten von Leerraum  
 Es gibt mehrere Verfahren zum Beibehalten von Leerräumen in der Quell- [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] für die nachfolgende Darstellung, die nicht von der Leerraumnormalisierung durch den [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] -Prozessor betroffen sind.  
  
 **XML: space = "preserve"**: Legen Sie dieses Attribut auf der Ebene des Elements fest, für das Leerräume beibehalten werden sollen. Hierdurch werden alle Leerräume beibehalten, auch die Leerzeichen, die ggf. von Codebearbeitungsanwendungen als visuell intuitive Schachtelung hinzugefügt werden, um Elemente für den Schöndruck auszurichten. Ob diese Leerzeichen gerendert werden, wird jedoch durch das Inhaltsmodell für das enthaltende Element bestimmt. Vermeiden Sie die Angabe von `xml:space="preserve"` auf der Stammebene, da die meisten Objektmodelle Leerräume nicht als signifikat betrachten, unabhängig davon, wie Sie das Attribut festlegen. Die globale Festlegung von `xml:space` kann in einigen Implementierungen die Leistung der XAML-Verarbeitung (insbesondere der Serialisierung) beeinträchtigen. Es ist besser, das Attribut nur auf der Ebene von Elementen spezifisch festzulegen, die Leerräume in Zeichenfolgen rendern oder leeraumsignifikate Auflistungen sind.  
  
 **Entitäten und geschützte Leerzeichen**: [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] unterstützt das Platzieren beliebiger [!INCLUDE[TLA#tla_unicode](../../../includes/tlasharptla-unicode-md.md)] -Entitäten in einem Textobjektmodell. Sie können dedizierte Entitäten wie geschützte Leerzeichen (&\#160; in UTF-8-Codierung). Sie können auch Rich-Text-Steuerelemente verwenden, die geschützte Leerzeichen unterstützen. Seien Sie vorsichtig, wenn Sie Entitäten zum Simulieren von Layouteigenschaften wie Einzügen verwenden, da die Laufzeitausgabe der Entitäten basierend auf einer größeren Anzahl von Faktoren variiert, als dies bei den Funktionen zum Erzeugen von Einzugsergebnisse in einem typischen Layoutsystem der Fall ist, z. B. richtige Verwendung von Bereichen und Rändern. Beispielsweise werden Entitäten Schriftarten zugeordnet und können sich als Reaktion auf eine Schriftartauswahl durch den Benutzer in der Größe ändern.  
  
<a name="east_asian_characters"></a>   
## <a name="east-asian-characters"></a>Ostasiatische Zeichen  
 Unter „ostasiatischen Zeichen“ versteht man einen Satz von [!INCLUDE[TLA2#tla_unicode](../../../includes/tla2sharptla-unicode-md.md)] -Zeichen in den Bereichen von U+20000 bis U+2FFFD und U+30000 bis U+3FFFD. Diese Teilmenge wird manchmal auch als „CJK-Ideogramme“ bezeichnet. Weitere Informationen finden Sie unter [http://www.unicode.org](http://www.unicode.org/).  
  
<a name="whitespace_and_text_content_models"></a>   
## <a name="whitespace-and-text-content-models"></a>Leerräume und Textinhaltsmodelle  
 In der Praxis ist das Beibehalten von Leerräumen nur für eine Teilmenge aller möglichen Inhaltsmodelle von Bedeutung. Diese Teilmenge besteht aus Inhaltsmodellen, die eine Form von Singleton- <xref:System.String> -Typ, eine dedizierte <xref:System.String> -Auflistung oder eine Mischung aus <xref:System.String> und anderen Typen in einer <xref:System.Collections.IList> - oder <xref:System.Collections.Generic.ICollection%601> -Auflistung verwenden können.  
  
### <a name="whitespace-and-text-content-models-in-wpf"></a>Leerräume und Textinhaltsmodelle in WPF  
 Zur Veranschaulichung bezieht sich der Rest dieses Abschnitts auf bestimmte von WPF definierte Typen. Die in diesem Thema beschriebenen Funktionen zur Behandlung von Leerräumen gelten im Allgemeinen sowohl für .NET Framework-XAML-Dienste als auch für WPF. Um diese Verhaltensweisen in Aktion zu sehen, können Sie mit einigen WPF-XAML-Markups experimentieren, die Ergebnisse in einem Objektdiagramm anzeigen und dann wieder zurück zu Markup serialisieren.  
  
 Sogar für Inhaltsmodelle, die Zeichenfolgen unterstützen, besteht das Standardverhalten innerhalb dieser Inhaltsmodelle darin, dass alle verbleibenden Leerräume als nicht signifikant behandelt werden. Beispielsweise verwendet <xref:System.Windows.Controls.ListBox> eine <xref:System.Collections.IList>, aber der Leerraum (wie z. B. Zeilenvorschübe zwischen den einzelnen <xref:System.Windows.Controls.ListBoxItem>-Elementen) wird nicht beibehalten und nicht gerendert. Wenn Sie versuchen, Zeilenvorschübe als Trennzeichen zwischen Zeichenfolgen für <xref:System.Windows.Controls.ListBoxItem> -Elemente zu verwenden, funktioniert dies nicht; alle durch die Zeilenvorschübe getrennten Zeichenfolgen werden als eine Zeichenfolge und ein Element behandelt.  
  
 Diese Auflistungen, die Leerräume als signifikant behandeln, sind in der Regel Teil des Flussdokumentmodells. Die primäre Auflistung, die die Beibehaltung von Leerräumen unterstützt, ist <xref:System.Windows.Documents.InlineCollection>. Diese Auflistungsklasse wird mit dem <xref:System.Windows.Markup.WhitespaceSignificantCollectionAttribute>deklariert; wenn dieses Attribut gefunden wird, behandelt der [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] -Prozessor Leerräume in der Auflistung als signifikant. Die Kombination von `xml:space="preserve"` und Leerräumen in einer mit <xref:System.Windows.Markup.WhitespaceSignificantCollectionAttribute> bezeichneten Auflistung führt dazu, dass alle Leerräume beibehalten und gerendert werden. Die Kombination von `xml:space="default"` und Leerräumen in einem <xref:System.Windows.Markup.WhitespaceSignificantCollectionAttribute> bewirkt die weiter oben beschriebene anfängliche Leerraumnormalisierung, die ein Leerzeichen an bestimmten Positionen beibehält; diese Leerzeichen werden beibehalten und gerendert. Welches Verhalten Sie bevorzugen, steht Ihnen frei, und Sie sollten `xml:space` selektiv verwenden, um das gewünschte Verhalten zu aktivieren.  
  
 Außerdem dürfen bestimmte Inlineelemente, die einen Zeilenumbruch in einem Flussdokumentmodell darstellen, nicht absichtlich ein zusätzliches Leerzeichen einfügen, selbst nicht in einer leerraumsignifikaten Auflistung. Z. B. die <xref:System.Windows.Documents.LineBreak> Element hat den gleichen Zweck wie das \<BR / >-Tag in [!INCLUDE[TLA2#tla_html](../../../includes/tla2sharptla-html-md.md)], und zur besseren Lesbarkeit im Markup in der Regel eine <xref:System.Windows.Documents.LineBreak> wird durch einen erstellten Zeilenvorschub von nachfolgenden Text getrennt. Dieser Zeilenvorschub darf nicht zu einem voranstellten Leerzeichen in der nächsten Zeile normalisiert werden. Um dieses Verhalten zu aktivieren, wendet die Klassendefinition für das <xref:System.Windows.Documents.LineBreak> -Element das <xref:System.Windows.Markup.TrimSurroundingWhitespaceAttribute>an, das dann vom [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] -Prozessor so interpretiert wird, dass Leerraum um <xref:System.Windows.Documents.LineBreak> immer entfernt werden soll.  
  
## <a name="see-also"></a>Siehe auch  
 [Übersicht über XAML (WPF)](../../../docs/framework/wpf/advanced/xaml-overview-wpf.md)  
 [XML-Zeichenentitäten und XAML](../../../docs/framework/xaml-services/xml-character-entities-and-xaml.md)  
 [xml:space-Behandlung in XAML](../../../docs/framework/xaml-services/xml-space-handling-in-xaml.md)
