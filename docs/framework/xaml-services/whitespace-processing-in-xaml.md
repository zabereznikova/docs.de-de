---
title: Leerzeichen in XAML verarbeitet
ms.date: 03/30/2017
helpviewer_keywords:
- East Asian characters [XAML Services]
- XAML [XAML Services], white-space processing
- white-space processing in XAML [XAML Services]
- characters [XAML Services], East Asian
ms.assetid: cc9cc377-7544-4fd0-b65b-117b90bb0b23
ms.openlocfilehash: 89f8a4675b3edc23913549bc24f0d9ae16917519
ms.sourcegitcommit: a885cc8c3e444ca6471348893d5373c6e9e49a47
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/06/2018
ms.locfileid: "43870236"
---
# <a name="white-space-processing-in-xaml"></a>Leerzeichen in XAML verarbeitet
Gemäß den Sprachregeln für XAML Status, signifikante Leerraum verarbeitet werden müssen, indem eine [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] -prozessorimplementierung. In diesem Thema werden diese XAML-Sprachregeln erläutert. Er dokumentiert auch zusätzliche Leerzeichen behandeln, die von definiert ist die [!INCLUDE[TLA#tla_winclient](../../../includes/tlasharptla-winclient-md.md)] Implementierung der XAML-Prozessor und der XAML-Writer für die Serialisierung.  
  
<a name="whitespace_definition"></a>   
## <a name="white-space-definition"></a>White-Space-definition  
 Das sortierflag [!INCLUDE[TLA2#tla_xml](../../../includes/tla2sharptla-xml-md.md)], Leerzeichen [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] werden Leerzeichen, Zeilenvorschub und Registerkarte. Diese entsprechen den [!INCLUDE[TLA#tla_unicode](../../../includes/tlasharptla-unicode-md.md)]-Werten 0020, 000A bzw. 0009.  
  
<a name="whitespace_normalization"></a>   
## <a name="white-space-normalization"></a>Normalisierung von Leerzeichen  
 Wird standardmäßig die folgenden leerstellennormalisierung tritt auf, wenn eine [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] Prozessor Prozesse eine [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] Datei:  
  
1.  Zeilenvorschubzeichen zwischen ostasiatischen Zeichen werden entfernt. Eine Definition dieses Begriffs finden Sie im Abschnitt „Ostasiatische Zeichen“ weiter hinten in diesem Thema.  
  
2.  Alle Leerraumzeichen (Leerzeichen, Zeilenvorschub, Registerkarte ") werden in Leerzeichen konvertiert.  
  
3.  Alle aufeinander folgenden Leerzeichen werden gelöscht und durch ein Leerzeichen ersetzt.  
  
4.  Ein Leerzeichen unmittelbar nach dem Starttag wird gelöscht.  
  
5.  Ein Leerzeichen unmittelbar vor dem Endtag wird gelöscht.  
  
 „Standard“ entspricht dem Zustand, der durch den Standardwert des [xml:space](../../../docs/framework/xaml-services/xml-space-handling-in-xaml.md) -Attribut bezeichnet wird.  
  
<a name="whitespace_in_inner_text_and_string_primitives"></a>   
## <a name="white-space-in-inner-text-and-string-primitives"></a>Leerraum in innerem Text und zeichenfolgenprimitive  
 Die oben genannten Normalisierungsregeln gelten für inneren Text innerhalb von XAML-Elementen. Nach der Normalisierung konvertiert ein XAML-Prozessor inneren Text wie folgt in einen entsprechenden Typ:  
  
-   Wenn der Typ der Eigenschaft keine Auflistung, aber nicht direkt ein <xref:System.Object> -Typ ist, versucht der XAML-Prozessor, unter Verwendung seines Typkonverters eine Konvertierung in diesen Typ durchzuführen. Ein Konvertierungsfehler verursacht einen Fehler zu Kompilierzeit.  
  
-   Wenn der Typ der Eigenschaft eine Auflistung und der innere Text zusammenhängend ist (keine dazwischen liegenden Elementtags), wird der innere Text als einzelner <xref:System.String>analysiert. Wenn der Auflistungstyp <xref:System.String>nicht akzeptieren kann, führt dies ebenfalls zu einem Kompilierzeitfehler.  
  
-   Wenn der Typ der Eigenschaft <xref:System.Object>ist, wird der innere Text als einzelner <xref:System.String>analysiert. Wenn dazwischen liegende Elementtags vorhanden sind, führt dies zu einem Kompilierzeitfehler, da der <xref:System.Object> -Typ ein einzelnes Objekt impliziert (<xref:System.String> oder anderes).  
  
-   Wenn der Typ der Eigenschaft eine Auflistung und der innere Text nicht zusammenhängend ist, wird die erste Teilzeichenfolge in einen <xref:System.String> konvertiert und als Auflistungselement hinzugefügt, das dazwischen liegende Element wird als Auflistungselement hinzugefügt, und schließlich wird die nachgestellte Teilzeichenfolge (sofern vorhanden) der Auflistung als drittes <xref:System.String> -Element hinzugefügt.  
  
<a name="preserving_whitespace"></a>   
## <a name="preserving-white-space"></a>Beibehalten von Leerraum  
 Es gibt mehrere Verfahren zum Beibehalten von Leerzeichen in der Quelle [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] für die nachfolgende Darstellung, die nicht betroffen sind [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] leerstellennormalisierung Prozessor.  
  
 **XML: space = "preserve"**: Geben Sie dieses Attribut auf der Ebene des Elements, in denen Leerraum beibehalten wird. Hierdurch werden alle Leerräume beibehalten, auch die Leerzeichen, die ggf. von Codebearbeitungsanwendungen als visuell intuitive Schachtelung hinzugefügt werden, um Elemente für den Schöndruck auszurichten. Ob diese Leerzeichen gerendert werden, wird jedoch durch das Inhaltsmodell für das enthaltende Element bestimmt. Vermeiden Sie es, `xml:space="preserve"` auf der Stammebene, da die meisten Objektmodelle weiß nicht berücksichtigt werden Leerzeichen als signifikant, unabhängig davon, wie Sie das Attribut festlegen. Die globale Festlegung von `xml:space` kann in einigen Implementierungen die Leistung der XAML-Verarbeitung (insbesondere der Serialisierung) beeinträchtigen. Es ist empfehlenswert, die das Attribut nur speziell auf der Ebene von Elementen festgelegt werden kann, die Leerzeichen in Zeichenfolgen rendern oder Auflistungen Leerzeichen sind.  
  
 **Entitäten und geschützte Leerzeichen**: [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] unterstützt das Platzieren beliebiger [!INCLUDE[TLA#tla_unicode](../../../includes/tlasharptla-unicode-md.md)] -Entitäten in einem Textobjektmodell. Sie können dedizierte Entitäten wie geschützte Leerzeichen (&\#160; in UTF-8-Codierung). Sie können auch Rich-Text-Steuerelemente verwenden, die geschützte Leerzeichen unterstützen. Seien Sie vorsichtig, wenn Sie Entitäten zum Simulieren von Layouteigenschaften wie Einzügen verwenden, da die Laufzeitausgabe der Entitäten basierend auf einer größeren Anzahl von Faktoren variiert, als dies bei den Funktionen zum Erzeugen von Einzugsergebnisse in einem typischen Layoutsystem der Fall ist, z. B. richtige Verwendung von Bereichen und Rändern. Beispielsweise werden Entitäten Schriftarten zugeordnet und können sich als Reaktion auf eine Schriftartauswahl durch den Benutzer in der Größe ändern.  
  
<a name="east_asian_characters"></a>   
## <a name="east-asian-characters"></a>Ostasiatische Zeichen  
 Unter „ostasiatischen Zeichen“ versteht man einen Satz von [!INCLUDE[TLA2#tla_unicode](../../../includes/tla2sharptla-unicode-md.md)] -Zeichen in den Bereichen von U+20000 bis U+2FFFD und U+30000 bis U+3FFFD. Diese Teilmenge wird manchmal auch als „CJK-Ideogramme“ bezeichnet. Weitere Informationen finden Sie unter [http://www.unicode.org](http://www.unicode.org/).  
  
<a name="whitespace_and_text_content_models"></a>   
## <a name="white-space-and-text-content-models"></a>Leerzeichen und Textinhaltsmodelle  
 In der Praxis ist das Beibehalten von Leerzeichen nur von Bedeutung für eine Teilmenge aller möglichen Inhaltsmodelle. Diese Teilmenge besteht aus Inhaltsmodellen, die eine Form von Singleton- <xref:System.String> -Typ, eine dedizierte <xref:System.String> -Auflistung oder eine Mischung aus <xref:System.String> und anderen Typen in einer <xref:System.Collections.IList> - oder <xref:System.Collections.Generic.ICollection%601> -Auflistung verwenden können.  
  
### <a name="white-space-and-text-content-models-in-wpf"></a>Leerzeichen und Textinhaltsmodelle in WPF  
 Zur Veranschaulichung bezieht sich der Rest dieses Abschnitts auf bestimmte von WPF definierte Typen. Die Behandlung von Leerraum Funktionen, die in diesem Thema beschrieben werden gelten im Allgemeinen sowohl WPF als auch .NET Framework-XAML-Dienste. Um diese Verhaltensweisen in Aktion zu sehen, können Sie mit einigen WPF-XAML-Markups experimentieren, die Ergebnisse in einem Objektdiagramm anzeigen und dann wieder zurück zu Markup serialisieren.  
  
 Sogar für Inhaltsmodelle, Zeichenfolgen, das Standardverhalten innerhalb dieser Inhaltsmodelle ist, dass eine beliebige leere Fläche, die verbleibt, als nicht signifikant behandelt wird. Z. B. <xref:System.Windows.Controls.ListBox> nimmt eine <xref:System.Collections.IList>, aber der Leerraum (wie z. B. Zeilenvorschübe zwischen den einzelnen <xref:System.Windows.Controls.ListBoxItem>) wird nicht beibehalten und nicht gerendert. Wenn Sie versuchen, Zeilenvorschübe als Trennzeichen zwischen Zeichenfolgen für <xref:System.Windows.Controls.ListBoxItem> -Elemente zu verwenden, funktioniert dies nicht; alle durch die Zeilenvorschübe getrennten Zeichenfolgen werden als eine Zeichenfolge und ein Element behandelt.  
  
 Diese Auflistungen, die Leerräume als signifikant behandeln, sind in der Regel Teil des flussdokumentmodells. Ist die primäre Auflistung, das Beibehalten von Leerraum Verhalten unterstützt <xref:System.Windows.Documents.InlineCollection>. Diese Auflistungsklasse wird mit deklariert die <xref:System.Windows.Markup.WhitespaceSignificantCollectionAttribute>; Wenn dieses Attribut gefunden wird, die [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] Prozessor behandelt Leerzeichen in der Auflistung als signifikant. Die Kombination von `xml:space="preserve"` und Leerzeichen innerhalb einer <xref:System.Windows.Markup.WhitespaceSignificantCollectionAttribute> bezeichneten Auflistung führt dazu, dass alle Leerräume beibehalten und gerendert werden. Die Kombination von `xml:space="default"` und Leerzeichen innerhalb einer <xref:System.Windows.Markup.WhitespaceSignificantCollectionAttribute> bewirkt die anfängliche leerstellennormalisierung weiter oben beschriebene, die ein Leerzeichen an bestimmten Positionen beibehält, und diese Leerzeichen werden beibehalten und gerendert. Welches Verhalten Sie bevorzugen, steht Ihnen frei, und Sie sollten `xml:space` selektiv verwenden, um das gewünschte Verhalten zu aktivieren.  
  
 Darüber hinaus sollten bestimmte Inlineelemente, die einen Zeilenumbruch in einem Flussdokumentmodell absichtlich nicht auch in eine Auflistung Leerzeichen ein zusätzliches Leerzeichen führen. Z. B. die <xref:System.Windows.Documents.LineBreak> Element hat den gleichen Zweck wie die \<BR / >-Tag in [!INCLUDE[TLA2#tla_html](../../../includes/tla2sharptla-html-md.md)], und zur besseren Lesbarkeit im Markup in der Regel eine <xref:System.Windows.Documents.LineBreak> wird durch einen erstellten Zeilenvorschub von nachfolgendem Text getrennt. Dieser Zeilenvorschub darf nicht zu einem voranstellten Leerzeichen in der nächsten Zeile normalisiert werden. So aktivieren Sie dieses Verhalten, die Klassendefinition für den <xref:System.Windows.Documents.LineBreak> Element gilt die <xref:System.Windows.Markup.TrimSurroundingWhitespaceAttribute>, wird dann von interpretiert die [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] -Prozessor so, Leerzeichen, umgibt <xref:System.Windows.Documents.LineBreak> immer entfernt.  
  
## <a name="see-also"></a>Siehe auch  
 [Übersicht über XAML (WPF)](../../../docs/framework/wpf/advanced/xaml-overview-wpf.md)  
 [XML-Zeichenentitäten und XAML](../../../docs/framework/xaml-services/xml-character-entities-and-xaml.md)  
 [XML: space-Behandlung in XAML](../../../docs/framework/xaml-services/xml-space-handling-in-xaml.md)
