---
title: Übersicht über XAML
description: Erfahren Sie, wie die XAML-Sprache von Windows Presentation Foundation (WPF) für .NET Core strukturiert und implementiert wird.
author: thraka
ms.date: 08/08/2019
ms.author: adegeo
dev_langs:
- csharp
- vb
helpviewer_keywords:
- user interfaces [XAML]
- classes [XAML]
- root element [XAML]
- XAML [WPF], about XAML
- base classes [XAML]
- routed events [WPF]
- code-behind files [WPF], XAML
- collection properties [XAML]
- events [XAML]
- property element [XAML]
- content models [XAML]
- Extensible Application Markup Language (see XAML)
- attribute syntax [XAML]
ms.openlocfilehash: b0a9357b623fbde08731a5b1ddb8fee3a93824c2
ms.sourcegitcommit: 515469828d0f040e01bde01df6b8e4eb43630b06
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/06/2020
ms.locfileid: "81433001"
---
# <a name="xaml-overview-in-wpf"></a>Übersicht über XAML in WPF

Dieser Artikel beschreibt die Funktionen der XAML-Sprache und zeigt, wie Sie XAML zum Schreiben von WPF-Apps (Windows Presentation Foundation) verwenden können. Dieser Artikel beschreibt speziell XAML entsprechend der Implementierung durch WPF. XAML selbst geht über das in WPF implementierte Sprachkonzept hinaus.

[!INCLUDE [desktop guide under construction](../../../includes/desktop-guide-preview-note.md)]

## <a name="what-is-xaml"></a>Was ist XAML?

XAML ist eine deklarative Markupsprache. Wie auf das .NET Core-Programmiermodell angewendet, vereinfacht XAML die Erstellung einer Benutzeroberfläche für eine .NET Core-App. Sie können sichtbare Benutzeroberflächenelemente im deklarativen XAML-Markup erstellen und anschließend die Benutzeroberflächendefinition mithilfe von Code-Behind-Dateien, die über partielle Klassendefinitionen an das Markup geknüpft sind, von der Laufzeitlogik trennen. XAML repräsentiert direkt die Instanziierung von Objekten in einem spezifischen Satz von in Assemblys definierten Unterstützungstypen dar. Dies ist ein anderer Ansatz als der anderer Markupsprachen, die üblicherweise interpretierte Sprachen sind, die keine direkte Verbindung zu einem System von Unterstützungstypen besitzen. XAML ermöglicht einen Workflow, bei dem separate Parteien auf der Benutzeroberfläche und der Logik einer App unter Verwendung möglicherweise unterschiedlicher Tools arbeiten können.

Bei der Darstellung als Text sind XAML-Dateien XML-Dateien, die in der Regel die `.xaml`-Erweiterung haben. Die Dateien können in jeder XML-Codierung codiert sein, üblich ist jedoch UTF-8-Codierung.

Das folgende Beispiel zeigt, wie Sie eine Schaltfläche als Teil einer Benutzeroberfläche erstellen können. Dieses Beispiel soll Ihnen ein erstes Gefühl dafür vermitteln, wie XAML allgemeine Benutzeroberflächen-Programmiermetaphern darstellt (es handelt sich nicht um ein vollständiges Beispiel).

[!code-xaml[XAMLOvwSupport#DirtSimple](~/samples/snippets/csharp/VS_Snippets_Wpf/XAMLOvwSupport/CSharp/page2.xaml#dirtsimple)]

## <a name="xaml-syntax-in-brief"></a>Kurzer Überblick über die XAML-Syntax

In den folgenden Abschnitten werden die grundlegenden Formen der XAML-Syntax erläutert und ein kurzes Markupbeispiel vorgestellt. Diese Abschnitte beabsichtigen keine Wiedergabe vollständiger Informationen über jedes Syntaxformat, z.B. wie diese im Unterstützungstypsystem dargestellt werden. Weitere Informationen zu den Besonderheiten der XAML-Syntax finden Sie unter [Ausführliche Erläuterung der XAML-Syntax](../../framework/wpf/advanced/xaml-syntax-in-detail.md).

Wenn Sie bereits mit der XML-Sprache vertraut sind, wird Ihnen vieles dessen, was Sie in den folgenden Abschnitten lesen, elementar erscheinen. Dies liegt im grundlegenden Entwurfsprinzip von XAML begründet. Die XAML-Sprache definiert zwar eigene Konzepte, aber diese Konzepte arbeiten mit der XML-Sprache und -Markupform.

### <a name="xaml-object-elements"></a>XAML-Objektelemente

Ein Objektelement deklariert in der Regel eine Instanz eines Typs. Dieser Typ wird in den Assemblys definiert, auf die von der Technologie verwiesen wird, die XAML als Sprache verwendet.

Objektelementsyntax beginnt immer mit einer öffnenden spitzen Klammer (`<`). Dies wird gefolgt vom Namen des Typs, in dem Sie eine Instanz erstellen möchten. (Dieser Name kann auch ein Präfix enthalten. Dieses Konzept wird später erläutert.) Danach können Sie optional Attribute für das Objektelement deklarieren. Um das Objektelement-Tag abzuschließen, beenden Sie es mit einer schließenden spitzen Klammer (`>`). Sie können stattdessen auch eine selbstschließende Form verwenden, die keinen Inhalte besitzt, indem Sie das Tag mit einem Schrägstrich gefolgt von einer schließenden spitzen Klammer beenden (`/>`). Sehen Sie sich z. B. den oben gezeigten Markupausschnitt erneut an.

[!code-xaml[XAMLOvwSupport#DirtSimple](~/samples/snippets/csharp/VS_Snippets_Wpf/XAMLOvwSupport/CSharp/page2.xaml#dirtsimple)]

Hier werden zwei Objektelemente angegeben: `<StackPanel>` (mit Inhalt und einem später folgenden schließenden Tag) und `<Button .../>` (in selbstschließender Form, mit mehreren Attributen). Die Objektelemente `StackPanel` und `Button` sind jeweils dem Namen einer Klasse zugeordnet, die durch WPF definiert und Teil der WPF-Assemblys ist. Wenn Sie ein Objektelement-Tag angeben, erstellen Sie eine Anweisung für den XAML-Prozessor, eine neue Instanz des zugrunde liegenden Typs zu erstellen. Jede Instanz wird durch Aufrufen des parameterlosen Konstruktors des zugrunde liegenden Typs beim Analysieren und Laden des XAML-Codes erstellt.

### <a name="attribute-syntax-properties"></a>Attributsyntax (Eigenschaften)

Eigenschaften eines Objekts können oft als Attribute des Objektelements ausgedrückt werden. Die Attributsyntax benennt die Objekteigenschaft, die festgelegt wird, gefolgt vom Zuweisungsoperator (=). Der Wert eines Attributs wird immer als Zeichenfolge angegeben, die in Anführungszeichen eingeschlossen ist.

Die Attributsyntax ist die geradlinigste Syntax zur Festlegung von Eigenschaften und die intuitivste Syntax für Entwickler, die bereits in der Vergangenheit Markupsprachen verwendet haben. Das folgende Markup erstellt z.B. eine Schaltfläche mit rotem Text und einem blauen Hintergrund, wobei der anzuzeigende Textinhalt als `Content` angegeben ist.

[!code-xaml[XAMLOvwSupport#BlueRedButton](~/samples/snippets/csharp/VS_Snippets_Wpf/XAMLOvwSupport/CSharp/Page1.xaml#blueredbutton)]

### <a name="property-element-syntax"></a>Eigenschaftenelementsyntax

Einige Eigenschaften eines Objektelements können nicht in Attributsyntax angegeben werden, da die Objekte oder Informationen, die für den Eigenschaftswert benötigt werden, nicht hinreichend innerhalb der durch Anführungszeichen und Zeichenfolgen beschränkten Attributsyntax ausgedrückt werden können. Für solche Fälle kann eine andere Syntax, die Eigenschaftenelement-Syntax genannt wird, verwendet werden.

Die Syntax für das Starttag des Eigenschaftenelements lautet `<TypeName.PropertyName>`. Im Allgemeinen ist der Inhalt dieses Tags ein Objektelement des Typs, den die Eigenschaft als Wert annimmt. Nachdem der Inhalt angegeben wurde, müssen Sie das Eigenschaftenelement mit einem Endtag schließen. Die Syntax für das Endtag ist `</TypeName.PropertyName>`.

Wenn Attributsyntax möglich ist, ist deren Verwendung in der Regel bequemer und ermöglicht ein kompakteres Markup, aber das ist oft nur eine Frage des Stils, keine technische Einschränkung. Das folgende Beispiel zeigt die Festlegung derselben Eigenschaften wie im vorherigen Attributsyntax-Beispiel, aber dieses Mal unter Verwendung von Eigenschaftenelement-Syntax für alle Eigenschaften des `Button`-Elements.

[!code-xaml[XAMLOvwSupport#BlueRedButtonPE](~/samples/snippets/csharp/VS_Snippets_Wpf/XAMLOvwSupport/CSharp/Page1.xaml#blueredbuttonpe)]

### <a name="collection-syntax"></a>Sammlungssyntax

Die XAML-Sprache enthält einige Optimierungen, die besser lesbares Markup erstellen. Eine dieser Optimierungen bewirkt, dass bei Eigenschaften, die vom Typ Auflistung sind, Elemente, die Sie in Markup als untergeordnete Elemente dieses Eigenschaftswerts anlegen, automatisch Teil der Auflistung werden. In diesem Fall ist der Wert, welcher der Auflistungseigenschaft zugewiesen wird, eine Auflistung von untergeordneten Objektelementen.

Im folgenden Beispiel wird die Sammlungssyntax zum Festlegen von Werten für die <xref:System.Windows.Media.GradientBrush.GradientStops%2A>-Eigenschaft gezeigt.

```xaml
<LinearGradientBrush>
  <LinearGradientBrush.GradientStops>
    <!-- no explicit new GradientStopCollection, parser knows how to find or create -->
    <GradientStop Offset="0.0" Color="Red" />
    <GradientStop Offset="1.0" Color="Blue" />
  </LinearGradientBrush.GradientStops>
</LinearGradientBrush>
```

### <a name="xaml-content-properties"></a>XAML-Inhaltseigenschaften

Ein Feature der XAML-Sprache ist, dass eine Klasse genau eine ihrer Eigenschaften als XAML-_Inhaltseigenschaft_ auszeichnen kann. Untergeordnete Elemente dieses Objektelements werden verwendet, um den Wert dieser Inhaltseigenschaft festzulegen. Anders gesagt: nur für die Inhaltseigenschaft dürfen Sie ein Eigenschaftenelement beim Festlegen dieser Eigenschaft in XAML-Markup auslassen und so eine besser sichtbare übergeordnet/untergeordnet-Metapher im Markup erzeugen.

<xref:System.Windows.Controls.Border> gibt z. B. eine _Inhaltseigenschaft_ von <xref:System.Windows.Controls.Decorator.Child%2A>an. Die folgenden zwei <xref:System.Windows.Controls.Border>-Elemente werden identisch behandelt. Der erste nutzt den Vorteil der Inhaltseigenschaften-Syntax und lässt das `Border.Child`-Eigenschaftenelement aus. Das zweite Beispiel zeigt `Border.Child` explizit.

```xaml
<Border>
  <TextBox Width="300"/>
</Border>
<!--explicit equivalent-->
<Border>
  <Border.Child>
    <TextBox Width="300"/>
  </Border.Child>
</Border>
```

In der XAML-Sprache gilt die Regel, dass der Wert einer XAML-Inhaltseigenschaft nur vor oder nach allen anderen Eigenschaftenelemente für dieses Objektelement festgelegt werden darf. Daher wird das folgende Markup beispielsweise nicht kompiliert.

```xaml
<Button>I am a
  <Button.Background>Blue</Button.Background>
  blue button</Button>
```

Weitere Informationen zu den Besonderheiten der XAML-Syntax finden Sie unter [Ausführliche Erläuterung der XAML-Syntax](../../framework/wpf/advanced/xaml-syntax-in-detail.md).

### <a name="text-content"></a>Textinhalte

Eine kleine Anzahl von XAML-Elementen kann Text direkt als Inhalt verarbeiten. Um dies zu ermöglichen, muss einer der folgenden Fälle zutreffen:

- Die Klasse muss eine Inhaltseigenschaft deklarieren und Inhaltseigenschaft muss von einem Typ sein, der Zeichenfolgen akzeptiert (z.B <xref:System.Object>). Beispielsweise verwendet jedes <xref:System.Windows.Controls.ContentControl>-Element <xref:System.Windows.Controls.ContentControl.Content%2A> als Inhaltseigenschaft und ist vom Typ <xref:System.Object>. Dies unterstützt die folgende Syntax für ein <xref:System.Windows.Controls.ContentControl>, z. B. <xref:System.Windows.Controls.Button>: `<Button>Hello</Button>`.

- Der Typ muss einen Typkonverter deklarieren, für den in diesem Fall der Textinhalt als Initialisierungstext verwendet wird. `<Brush>Blue</Brush>` konvertiert z. B. den Inhaltswert `Blue` in einen Pinsel. Dieser Fall ist in der Praxis weniger häufig.

- Der Typ muss eine bekanntes XAML-Sprachprimitiv sein.

### <a name="content-properties-and-collection-syntax-combined"></a>Inhaltseigenschaften und Auflistungssyntax in Kombination

Betrachten Sie das folgende Beispiel.

```xaml
<StackPanel>
  <Button>First Button</Button>
  <Button>Second Button</Button>
</StackPanel>
```

Hier ist jedes <xref:System.Windows.Controls.Button>-Element ein untergeordnetes Element von <xref:System.Windows.Controls.StackPanel>. Dies ist ein optimiertes und intuitives Markup, bei dem zwei Tags aus zwei verschiedenen Gründen weggelassen wurden.

- **Ausgelassenes StackPanel.Children-Eigenschaftselement:** <xref:System.Windows.Controls.StackPanel> von <xref:System.Windows.Controls.Panel> abgeleitet. <xref:System.Windows.Controls.Panel> definiert <xref:System.Windows.Controls.Panel.Children%2A?displayProperty=nameWithType> als XAML-Inhaltseigenschaft.

- **Ausgelassenes UIElementCollection-Objektelement:** Die <xref:System.Windows.Controls.Panel.Children%2A?displayProperty=nameWithType>-Eigenschaft nimmt den Typ <xref:System.Windows.Controls.UIElementCollection> an, der <xref:System.Collections.IList>implementiert. Das Elementtag der Sammlung kann gemäß den XAML-Regeln zum Verarbeiten von Auflistungen wie z. B. <xref:System.Collections.IList> ausgelassen werden. (In diesem Fall kann <xref:System.Windows.Controls.UIElementCollection> tatsächlich nicht instanziiert werden, da das Element keinen parameterlosen Konstruktor bereitstellt. Aus diesem Grund wird das <xref:System.Windows.Controls.UIElementCollection>-Objektelement auskommentiert angezeigt).

```xaml
<StackPanel>
  <StackPanel.Children>
    <!--<UIElementCollection>-->
    <Button>First Button</Button>
    <Button>Second Button</Button>
    <!--</UIElementCollection>-->
  </StackPanel.Children>
</StackPanel>
```

### <a name="attribute-syntax-events"></a>Attributsyntax (Ereignisse)

Attributsyntax kann auch für Mitglieder verwendet werden, die Ereignisse und keine Eigenschaften sind. In diesem Fall ist der Name des Attributs der Name des Ereignisses. In der WPF-Implementierung von Ereignissen für XAML ist der Wert des Attributs der Name eines Ereignishandlers, der den Ereignisdelegaten implementiert. Das folgende Markup weist z. B. einen Handler für das <xref:System.Windows.Controls.Primitives.ButtonBase.Click>-Ereignis einem im Markup erstellten <xref:System.Windows.Controls.Button>-Element zu:

[!code-xaml[XAMLOvwSupport#ButtonWithCodeBehind](~/samples/snippets/csharp/VS_Snippets_Wpf/XAMLOvwSupport/CSharp/page3.xaml#buttonwithcodebehind)]

Es steckt noch mehr hinter Ereignissen und XAML in WPF, als dieses Beispiel für die Attributsyntax zeigt. So fragen Sie sich vielleicht, was der hier referenzierte `ClickHandler` darstellt und wie er definiert wird. Dies wird im späteren Abschnitt [Ereignisse und XAML-CodeBehind](#events-and-xaml-code-behind) dieses Artikels erläutert.

## <a name="case-and-white-space-in-xaml"></a>Groß-/Kleinschreibung und Leerzeichen in XAML

Im Allgemeinen wird in XAML Groß-/Kleinschreibung unterschieden. Zum Auflösen von Unterstützungstypen wird in WPF-XAML die Groß-/Kleinschreibung nach den gleichen Regeln wie in CLR beachtet. Bei Objektelementen, Eigenschaftenelementen und Attributnamen muss beim Vergleich anhand des Namens des zugrunde liegenden Typs in der Assembly oder eines Typmitglieds immer die Groß-/Kleinschreibung beachtet werden. Auch XAML-Schlüsselwörter und Primitive beachten die Groß-/Kleinschreibung. Bei Werte wird nicht immer Groß-/Kleinschreibung beachtet. Ob bei Werten Groß-/Kleinschreibung beachtet wird, hängt vom Verhalten ab, das dem Typkonverter für die den Wert annehmende Eigenschaft zugeordnet ist, oder vom Typ des Eigenschaftswerts. So können z. B. Eigenschaften, die den Typ <xref:System.Boolean> annehmen, sowohl `true` als auch `True` als äquivalente Werte annehmen, aber nur deshalb, weil die Typkonvertierung von Zeichenfolgen in <xref:System.Boolean> des nativen WPF-XAML-Parsers diese bereits als gleichwertig zulässt.

WPF XAML-Prozessoren und -Serialisierungsmodule ignorieren oder löschen alle nicht signifikanten Leerzeichen und normalisieren alle signifikanten Leerzeichen. Dies entspricht dem empfohlenen standardmäßigen Leerzeichenverhalten der XAML-Spezifikation. Dieses Verhalten hat nur dann Auswirkungen, wenn Sie Zeichenfolgen innerhalb von XAML-Inhaltseigenschaften angeben. Vereinfacht ausgedrückt: XAML konvertiert Leerzeichen, Zeilenvorschub und Tabulatorzeichen in Leerzeichen und behält anschließend ein Leerzeichen bei, wenn sich dieses an einem Ende einer zusammenhängenden Zeichenfolge befindet. Eine vollständige Erläuterung der Leerzeichenbehandlung in XAML ist nicht Gegenstand dieses Artikels. Weitere Informationen finden Sie unter [Leerzeichenverarbeitung in XAML](../xaml-services/white-space-processing.md).

## <a name="markup-extensions"></a>Markuperweiterungen

Markuperweiterungen sind ein XAML-Sprachkonzept. Wenn geschweifte Klammern zum Bereitstellen des Werts einer Attributsyntax verwendet werden (`{` und `}`), handelt es sich dabei um die Verwendung einer Markuperweiterung. Diese Verwendung weist den XAML-Prozessor an, von der allgemeinen Behandlung von Attributwerten als Zeichenfolgenliteral oder zu einer Zeichenfolge konvertierbarem Wert abzuweichen.

Die bei der Programmierung von WPF-Apps am häufigsten verwendeten Markuperweiterungen sind [`Binding`](../../framework/wpf/advanced/binding-markup-extension.md), die für Datenbindungsausdrücke verwendet werden, und die Ressourcenverweise [`StaticResource`](../../framework/wpf/advanced/staticresource-markup-extension.md) und [`DynamicResource`](../../framework/wpf/advanced/dynamicresource-markup-extension.md). Durch die Verwendung von Markuperweiterungen können Sie mit Attributsyntax auch dann Werte für Eigenschaften bereitstellen, wenn diese Eigenschaft im Allgemeinen keine Attributsyntax unterstützt. Markuperweiterungen verwenden oft intermediäre Ausdruckstypen, um Features wie z. B. das Zurückstellen von Werten oder das Verweisen auf andere Objekte, die nur zur Laufzeit vorhanden sind, zu aktivieren.

Das folgende Markup legt z.B. den Wert für die <xref:System.Windows.FrameworkElement.Style%2A>-Eigenschaft mithilfe der Attributsyntax fest. Die <xref:System.Windows.FrameworkElement.Style%2A>-Eigenschaft nimmt eine Instanz der <xref:System.Windows.Style>-Klasse an, die standardmäßig nicht von einer Attributsyntaxzeichenfolge instanziiert werden konnte. In diesem Fall verweist das Attribut jedoch auf eine bestimmte Markuperweiterung: `StaticResource`. Wenn diese Markuperweiterung verarbeitet wird, wird ein Verweis auf einen Stil zurückgegeben, der bereits zuvor als mit einem Schlüssel versehene Ressource in einem Ressourcenverzeichnis instanziiert wurde.

[!code-xaml[FEResourceSH_snip#XAMLOvwShortResources](~/samples/snippets/csharp/VS_Snippets_Wpf/FEResourceSH_snip/CS/page1.xaml#xamlovwshortresources)]
[!code-xaml[FEResourceSH_snip#XAMLOvwShortResources2](~/samples/snippets/csharp/VS_Snippets_Wpf/FEResourceSH_snip/CS/page1.xaml#xamlovwshortresources2)]
[!code-xaml[FEResourceSH_snip#XAMLOvwShortResources3](~/samples/snippets/csharp/VS_Snippets_Wpf/FEResourceSH_snip/CS/page1.xaml#xamlovwshortresources3)]

Eine Verweisliste mit Markuperweiterungen für XAML, die spezifisch in WPF implementiert sind, finden Sie unter [WPF-XAML-Erweiterungen](../../framework/wpf/advanced/wpf-xaml-extensions.md). Eine Verweisliste der Markuperweiterungen, die von System.Xaml definiert und für .NET Core-XAML-Implementierungen besser verfügbar sind, finden Sie unter [XAML Namespace (x:) Language Features (Sprachfunktionen des XAML-Namespace (x:))](../xaml-services/namespace-language-features.md). Weitere Informationen über die Konzepte der Markuperweiterungen finden Sie unter [Markuperweiterungen und WPF XAML](../../framework/wpf/advanced/markup-extensions-and-wpf-xaml.md).

## <a name="type-converters"></a>Typkonverter

Im Abschnitt [XAML-Syntax in Kürze](#xaml-syntax-in-brief) wurde behauptet, dass man den Attributwert durch eine Zeichenfolge festlegen können muss. Die einfache, native Behandlung, wie Zeichenfolgen in andere Objekttypen oder primitive Werte konvertiert werden, basiert auf dem <xref:System.String>-Typ selbst, sowie auf der nativen Verarbeitung bestimmter Typen wie <xref:System.DateTime> oder <xref:System.Uri>. Viele WPF-Typen oder deren Member erweitern das grundlegende Verhalten der Zeichenfolgenverarbeitung so, dass Instanzen komplexerer Objekttypen als Zeichenfolgen und Attribute angegeben werden können.

Die <xref:System.Windows.Thickness>-Struktur ist ein Beispiel für einen Typ, für den Typkonvertierung für XAML-Syntax aktiviert ist. <xref:System.Windows.Thickness> gibt Maße innerhalb eines geschachtelten Rechtecks an und wird als Wert für Eigenschaften wie <xref:System.Windows.FrameworkElement.Margin%2A> verwendet. Durch Festlegen eines Typkonverters für <xref:System.Windows.Thickness> sind alle Eigenschaften, die <xref:System.Windows.Thickness> verwenden, einfacher in XAML anzugeben, da sie als Attribute angegeben werden können. Im folgenden Beispiel wird eine Konvertierung und die Attributsyntax verwendet, um einen Wert für ein <xref:System.Windows.FrameworkElement.Margin%2A>-Element festzulegen:

[!code-xaml[XAMLOvwSupport#MarginTCE](~/samples/snippets/csharp/VS_Snippets_Wpf/XAMLOvwSupport/CSharp/page7.xaml#margintce)]

Das obige Attributsyntax-Beispiel ist äquivalent zum nachfolgenden, umständlicheren Beispiel, in dem <xref:System.Windows.FrameworkElement.Margin%2A> stattdessen durch Eigenschaftenelement-Syntax mit einem <xref:System.Windows.Thickness>-Objektelement festgelegt wird. Die vier Schlüsseleigenschaften von <xref:System.Windows.Thickness> werden als Attribute der neuen Instanz festgelegt:

[!code-xaml[XAMLOvwSupport#MarginVerbose](~/samples/snippets/csharp/VS_Snippets_Wpf/XAMLOvwSupport/CSharp/page7.xaml#marginverbose)]

> [!NOTE]
> Es gibt auch eine begrenzte Anzahl von Objekten, in denen die Typkonvertierung die einzige öffentliche Methode zum Festlegen einer Eigenschaft auf diesen Typ ist, die keine Unterklasse benötigt, da der Typ selbst nicht über einen parameterlosen Konstruktor verfügt. z. B. <xref:System.Windows.Input.Cursor>.

Weitere Informationen zur Typkonvertierung finden Sie unter [TypeConverter und XAML](../../framework/wpf/advanced/typeconverters-and-xaml.md).

## <a name="xaml-root-elements-and-xaml-namespaces"></a>XAML-Stammelemente und XAML-Namespaces

Eine XAML-Datei darf nur ein Stammelement haben, um sowohl eine wohlgeformte XML-Datei als auch eine gültige XAML-Datei zu sein. Bei typischen WPF-Szenarien verwenden Sie ein Stammelement, das eine wichtige Bedeutung im WPF-App-Modell aufweist (z. B. <xref:System.Windows.Window> oder <xref:System.Windows.Controls.Page> für eine Seite, <xref:System.Windows.ResourceDictionary> für ein externes Wörterbuch oder <xref:System.Windows.Application> für die App-Definition). Das folgende Beispiel zeigt das Stammelement einer normalen XAML-Datei für eine WPF-Seite mit dem Stammelement <xref:System.Windows.Controls.Page>.

[!code-xaml[XAMLOvwSupport#RootOnly](~/samples/snippets/csharp/VS_Snippets_Wpf/XAMLOvwSupport/CSharp/page2.xaml#rootonly)]
[!code-xaml[XAMLOvwSupport#RootOnly2](~/samples/snippets/csharp/VS_Snippets_Wpf/XAMLOvwSupport/CSharp/page2.xaml#rootonly2)]

Das Stammelement enthält auch die Attribute `xmlns` und `xmlns:x`. Diese Attribute geben einem XAML-Prozessor an, welche XAML-Namespaces die Typdefinitionen für Unterstützungstypen enthalten, auf die das Markup als Elemente verweist. Das `xmlns`-Attribut gibt ausdrücklich den XAML-Standardnamespace an. Innerhalb des XAML-Standardnamespaces können Objektelemente im Markup ohne Präfix angegeben werden. Für die meisten WPF-Anwendungsszenarien und für fast alle der in den WPF-Abschnitten des SDK angegebenen Beispiele ist der XAML-Standardnamespace dem WPF-Namespace `http://schemas.microsoft.com/winfx/2006/xaml/presentation` zugeordnet. Das `xmlns:x`-Attribut gibt einen zusätzlichen XAML-Namespace an, der dem XAML-Sprachnamespace `http://schemas.microsoft.com/winfx/2006/xaml` zugeordnet ist.

Diese Verwendung von `xmlns` zum Definieren eines Geltungsbereich für die Verwendung und Zuordnung eines Namescopes ist mit der XML 1.0-Spezifikation verträglich. XAML-Namescopes unterscheiden sich von XML-Namescopes nur darin, dass ein XAML-Namescope auch darüber etwas impliziert, wie Elemente durch Typen unterstützt werden, wenn es zur Typauflösung und Analyse des XAML-Codes kommt.

Die `xmlns`-Attribute sind nur für das Stammelement jeder XAML-Datei unbedingt erforderlich. `xmlns`-Definitionen gelten für alle Nachfolgerelemente des Stammelements (dieses Verhalten entspricht wieder der XML 1.0-Spezifikation für `xmlns`.) `xmlns`-Attribute sind auch bei anderen Elementen unterhalb des Stamms zulässig und gelten für alle Nachfolgerelemente des definierenden Elements. Allerdings kann häufiges Definieren oder Neudefinieren von XAML-Namespaces zu einem nur schwer lesbaren XAML-Markup-Stil führen.

Die WPF-Implementierung des XAML-Prozessors schließt eine Infrastruktur ein, der die WPF-Kernassemblys bekannt sind. Es ist bekannt, dass die WPF-Kernassemblys die Typen enthalten, welche die WPF-Zuordnungen zum XAML-Standardnamespace unterstützen. Dies wird durch eine Konfiguration ermöglicht, die Teil Ihrer Projekt-Builddatei und des WPF-Builds und -Projektsystems ist. Daher ist die Deklaration des XAML-Namespaces als Standard-`xmlns` das Einzige, was benötigt wird, um auf XAML-Elemente zu verweisen, die aus WPF-Assemblys stammen.

### <a name="the-x-prefix"></a>Das Präfix x:

Im vorherigen Beispiel zum Stammelement wurde das Präfix `x:` verwendet, um den XAML-Namespaces `http://schemas.microsoft.com/winfx/2006/xaml` zuzuordnen, also der dedizierte XAML-Namespace, der XAML-Sprachkonstrukte unterstützt. Dieses `x:`-Präfix wird für die Zuordnung des XAML-Namespaces in den Vorlagen für Projekte, in Beispielen und in der Dokumentation im gesamten SDK verwendet. Der XAML-Namespace für die XAML-Sprache enthält verschiedene Programmierkonstrukte, die Sie häufig in XAML verwenden werden. Im folgenden finden Sie eine Liste der häufigsten `x:`-Präfix-Programmierkonstrukte, die Sie verwenden werden:

- [x:Key](../xaml-services/xkey-directive.md): Legt einen eindeutigen Schlüssel für jede Ressource in einem <xref:System.Windows.ResourceDictionary> fest (oder in ähnlichen Wörterbuchkonzepten in anderen Frameworks). `x:Key` wird sich wahrscheinlich für 90 % der Syntax von `x:` im Markup einer normalen WPF-App verantwortlich zeigen.

- [x:Class](../xaml-services/xclass-directive.md): Gibt den CLR-Namespace und den Klassennamen für die Klasse an, die CodeBehind für eine XAML-Seite bereitstellt. Das WPF-Programmiermodell schreibt eine solche Klasse für CodeBehind-Unterstützung vor, weshalb Sie fast immer eine Zuordnung von `x:` sehen werden, selbst wenn keine Ressourcen vorhanden sind.

- [x:Name](../xaml-services/xname-directive.md): Gibt einen Namen für das Laufzeitobjekt einer Instanz an, die im Laufzeitcode vorhanden ist, nachdem ein Objektelement verarbeitet wurde. Im Allgemeinen werden Sie häufig eine entsprechende WPF-definierte Eigenschaft für [x:Name](../xaml-services/xname-directive.md) verwenden. Solche Eigenschaften werden spezifisch einer CLR-Unterstützungseigenschaft zugeordnet und erleichtern daher die App-Programmierung, bei der Sie häufig Laufzeitcode verwenden, um die benannten Elemente aus initialisiertem XAML zu finden. Die häufigste derartige Eigenschaft ist <xref:System.Windows.FrameworkElement.Name%2A?displayProperty=nameWithType>. Unter Umständen werden Sie dennoch [x:Name](../xaml-services/xname-directive.md) verwenden, wenn die entsprechende auf WPF-Frameworkebene verfügbare Eigenschaft <xref:System.Windows.FrameworkElement.Name%2A> für einen bestimmten Typ nicht unterstützt wird. Dies ist bei einigen Animations-Szenarios der Fall.

- [x:Static](../xaml-services/xstatic-markup-extension.md): Ermöglicht einen Verweis, der einen statischen Wert zurückgibt, der nicht anderweitig als XAML-kompatible Eigenschaft verwendbar ist.

- [x:Type](../xaml-services/xtype-markup-extension.md): Erstellt einen <xref:System.Type>-Verweis auf der Grundlage eines Typnamens. Dies wird verwendet, um Attribute anzugeben, die <xref:System.Type> annehmen, etwa <xref:System.Windows.Style.TargetType%2A?displayProperty=nameWithType>, obwohl die Eigenschaft häufig über native Zeichenfolge-zu-<xref:System.Type>-Konvertierung verfügt, sodass die Syntax der [x:Type](../xaml-services/xtype-markup-extension.md)-Markuperweiterung optional ist.

Es gibt weitere Programmierkonstrukte im `x:`-Präfix/XAML-Namespace, die nicht so häufig verwendet werden. Weitere Informationen finden Sie unter [XAML Namespace (x:) Language Features (Sprachfunktionen des XAML-Namespace (x:))](../xaml-services/namespace-language-features.md).

## <a name="custom-prefixes-and-custom-types-in-xaml"></a>Benutzerdefinierte Präfixe und benutzerdefinierte Typen in XAML

Für eigene benutzerdefinierte Assemblys oder Assemblys außerhalb des WPF-Kerns aus **PresentationCore**, **PresentationFramework** und **WindowsBase** können Sie die Assembly als Teil einer benutzerdefinierten `xmlns`-Zuordnung angeben. Sie können dann auf Typen aus dieser Assembly in Ihrem XAML verweisen, sofern dieser Typ korrekt implementiert wird, um die von Ihnen beabsichtigten XAML-Verwendungen zu unterstützen.

Im Folgenden sehen Sie ein einfaches Beispiel dafür, wie benutzerdefinierte Präfixe in XAML-Markup funktionieren. Das Präfix `custom` ist im Stammelement definiert und einer bestimmten Assembly zugeordnet, die mit der App verpackt wird und verfügbar ist. Diese Assembly enthält einen Typ `NumericUpDown`, der für die Unterstützung allgemeiner XAML-Verwendung implementiert ist und eine Klassenvererbung verwendet, die ihre Einfügung an diesem bestimmten Punkt im WPF-XAML-Inhaltsmodell zulässt. Eine Instanz dieses `NumericUpDown`-Steuerelements wird mithilfe des Präfix als Objektelement deklariert, damit der XAML-Parser weiß, welcher XAML-Namespace den Typ enthält und damit auch, wo sich die Unterstützungsassembly befindet, die die Typdefinition enthält.

```xaml
<Page
    xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
    xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
    xmlns:custom="clr-namespace:NumericUpDownCustomControl;assembly=CustomLibrary"
    >
  <StackPanel Name="LayoutRoot">
    <custom:NumericUpDown Name="numericCtrl1" Width="100" Height="60"/>
...
  </StackPanel>
</Page>
```

Weitere Informationen zu benutzerdefinierten Typen in XAML finden Sie unter [XAML- und benutzerdefinierte Klassen für WPF](../../framework/wpf/advanced/xaml-and-custom-classes-for-wpf.md).

Weitere Informationen zur Beziehung zwischen XML-Namespaces und den Codenamespaces in Assemblys finden Sie unter [XAML-Namespaces und Namespace-Zuordnung für WPF-XAML](../../framework/wpf/advanced/xaml-namespaces-and-namespace-mapping-for-wpf-xaml.md).

## <a name="events-and-xaml-code-behind"></a>Ereignisse und XAML-CodeBehind

Die meisten WPF-Anwendungen bestehen aus XAML-Markup und CodeBehind. Innerhalb eines Projekts wird der XAML-Code als `.xaml`-Datei geschrieben, und eine CLR-Sprache (z. B. Microsoft Visual Basic oder C#) wird verwendet, um eine CodeBehind-Datei zu schreiben. Wenn das Markup einer XAML-Datei als Teil der WPF-Programmierungs- und -Anwendungsmodelle kompiliert wird, wird der Speicherort der XAML-CodeBehind-Datei für eine XAML-Datei durch Angeben eines Namespaces und einer Klasse als `x:Class`-Attribut des Stammelements des XAML identifiziert.

In den bisherigen Beispielen haben Sie verschiedene Schaltflächen gesehen, aber noch war keiner dieser Schaltflächen ein logisches Verhalten zugeordnet. Der primäre Mechanismus auf Anwendungsebene zum Hinzufügen eines Verhaltens für ein Objektelement ist, ein vorhandenes Ereignis der Elementklasse zu verwenden und einen bestimmten Handler für dieses Ereignis zu schreiben, der aufgerufen wird, wenn das Ereignis zur Laufzeit ausgelöst wird. Der Name des Ereignisses und der Name der zu verwendenden Handler werden im Markup angegeben, während der Code, der den Handler implementiert, im CodeBehind definiert ist.

[!code-xaml[XAMLOvwSupport#ButtonWithCodeBehind](~/samples/snippets/csharp/VS_Snippets_Wpf/XAMLOvwSupport/CSharp/page3.xaml#buttonwithcodebehind)]

[!code-csharp[XAMLOvwSupport#ButtonWithCodeBehindHandler](~/samples/snippets/csharp/VS_Snippets_Wpf/XAMLOvwSupport/CSharp/page3.xaml.cs#buttonwithcodebehindhandler)]
[!code-vb[XAMLOvwSupport#ButtonWithCodeBehindHandler](~/samples/snippets/visualbasic/VS_Snippets_Wpf/XAMLOvwSupport/VisualBasic/Page1.xaml.vb#buttonwithcodebehindhandler)]

Beachten Sie, dass die CodeBehind-Datei den CLR-Namespace `ExampleNamespace` verwendet und `ExamplePage` als partielle Klasse in diesem Namespace deklariert. Dies entspricht dem `x:Class`-Attributwert von `ExampleNamespace`.`ExamplePage`, der im Stammelement des Markups bereitgestellt wurde. Der WPF-Markupcompiler erstellt für jede kompilierte XAML-Datei eine partielle Klasse durch Ableiten einer Klasse des Typs des Stammelements. Wenn Sie CodeBehind bereitstellen, in dem die gleiche partielle Klasse definiert ist, wird der resultierende Code innerhalb der gleichen Namespace- und Klassennamen der kompilierten App kombiniert.

Weitere Informationen zu den Anforderungen für die CodeBehind-Programmierung in WPF finden Sie unter [CodeBehind, Ereignishandler und Anforderungen der partiellen Klasse in WPF](../../framework/wpf/advanced/code-behind-and-xaml-in-wpf.md#code-behind-event-handler-and-partial-class-requirements-in-wpf).

Wenn Sie keine separate CodeBehind-Datei erstellen möchten, können Sie Ihren den Code auch inline in eine XAML-Datei schreiben. Inline-Code ist jedoch eine weniger vielseitige Technik, die erhebliche Einschränkungen hat. Weitere Informationen finden Sie unter [CodeBehind und XAML in WPF](../../framework/wpf/advanced/code-behind-and-xaml-in-wpf.md).

### <a name="routed-events"></a>Routingereignisse

Ein bestimmtes, in WPF grundlegendes Ereignisfeature ist das Routingereignis. Routingereignisse ermöglichen es einem Element, ein Ereignis zu behandeln, das durch ein anderes Element ausgelöst wurde, solange diese Elemente über eine strukturelle Beziehung verbunden sind. Gibt man eine Ereignisbehandlung über ein XAML-Attribut an, kann jedes beliebige Element nach diesem Routingereignis lauschen und es behandeln, einschließlich der Elemente, für die dieses bestimmte Element nicht in der Mitgliedstabelle der Klasse aufgeführt ist. Dies wird durch Qualifizierung des Ereignisnamen-Attributs mit dem besitzenden Klassennamen erreicht. Das übergeordnete `StackPanel`-Element im aktuellen `StackPanel` / `Button`-Beispiel könnte z. B. einen Handler für das <xref:System.Windows.Controls.Primitives.ButtonBase.Click>-Ereignis der Schaltfläche des untergeordneten Elements registrieren, indem es das Attribut `Button.Click` für das `StackPanel`-Objektelement mit dem Handlernamen als Attributwert angibt. Weitere Informationen finden Sie unter [Übersicht über Routingereignisse](../../framework/wpf/advanced/routed-events-overview.md).

## <a name="xaml-named-elements"></a>Benannte Elemente in XAML

Die Objektinstanz, die in einem Objektdiagramm durch Verarbeitung eines XAML-Objektelements erstellt wird, hat standardmäßig keinen eindeutigen Bezeichner oder Objektverweis. Wenn Sie allerdings einen Konstruktor im Code aufrufen, verwenden Sie fast immer das Konstruktorergebnis zum Festlegen einer Variablen auf die erstellte Instanz, damit Sie später im Code auf die Instanz verweisen können. Um standardisierten Zugriff auf Objekte bereitzustellen, die durch eine Markupdefinition erstellt wurden, definiert XAML-Code das [x:Name-Attribut](../xaml-services/xname-directive.md). Sie können den Wert des `x:Name`-Attributs auf jedes beliebiges Objektelement festlegen. Im CodeBehind entspricht der von Ihnen gewählte Bezeichner einer Instanzvariablen, die auf die erstellte Instanz verweist. Benannte Elemente funktionieren in jeder Hinsicht wie Objektinstanzen (der Name verweist auf diese Instanz), und im CodeBehind kann auf die benannten Elemente verwiesen werden, um anwendungsinterne Interaktionen zur Laufzeit zu behandeln. Diese Verbindung zwischen Instanzen und Variablen wird durch den WPF-XAML-Markupcompiler hergestellt und umfasst insbesondere Merkmale und Muster wie <xref:System.Windows.Markup.IComponentConnector.InitializeComponent%2A>, auf die in diesem Artikel nicht näher eingegangen wird.

XAML-Elemente auf WPF-Frameworkebene erben eine <xref:System.Windows.FrameworkElement.Name%2A>-Eigenschaft, die dem in XAML definierten `x:Name`-Attribut entspricht. Bestimmte andere Klassen bieten ebenfalls Entsprechungen für `x:Name` auf Eigenschaftenebene, was in der Regel ebenfalls als `Name`-Eigenschaft definiert ist. Allgemein gilt, dass Sie ersatzweise `x:Name` nutzen sollten, wenn Sie keine `Name`-Eigenschaft in der Mitgliedertabelle Ihres gewünschten Elements/Typs finden können. Die `x:Name`-Werte stellen einen Bezeichner für ein XAML-Element bereit, der zur Laufzeit durch bestimmte Subsysteme oder durch Hilfsmethoden wie <xref:System.Windows.FrameworkElement.FindName%2A> verwendet werden kann.

Im folgenden Beispiel wird ein <xref:System.Windows.FrameworkElement.Name%2A> für ein <xref:System.Windows.Controls.StackPanel>-Element festgelegt. Dann verweist ein Handler für ein <xref:System.Windows.Controls.Button>-Element innerhalb dieses <xref:System.Windows.Controls.StackPanel>-Elements auf das <xref:System.Windows.Controls.StackPanel>-Element über den Instanzverweis `buttonContainer`, wie von <xref:System.Windows.FrameworkElement.Name%2A>festgelegt.

[!code-xaml[XAMLOvwSupport#NamedE](~/samples/snippets/csharp/VS_Snippets_Wpf/XAMLOvwSupport/CSharp/page7.xaml#namede)]
[!code-xaml[XAMLOvwSupport#NamedE2](~/samples/snippets/csharp/VS_Snippets_Wpf/XAMLOvwSupport/CSharp/page7.xaml#namede2)]

[!code-csharp[XAMLOvwSupport#NameCode](~/samples/snippets/csharp/VS_Snippets_Wpf/XAMLOvwSupport/CSharp/page7.xaml.cs#namecode)]
[!code-vb[XAMLOvwSupport#NameCode](~/samples/snippets/visualbasic/VS_Snippets_Wpf/XAMLOvwSupport/VisualBasic/Page1.xaml.vb#namecode)]

Der XAML-Name einer Instanz unterliegt genau wie eine Variable dem Konzept eines Geltungsbereichs, sodass die Eindeutigkeit von Namen innerhalb eines bestimmten, vorhersagbaren Geltungsbereichs erzwungen werden kann. Das primäre Markup, das eine Seite definiert, kennzeichnet einen eindeutigen XAML-Namescope, dessen Grenze das Stammelement dieser Seite ist. Allerdings können andere Markupquellen zur Laufzeit mit einer Seite interagieren, z. B. Stile oder Vorlagen innerhalb von Stilen, und solche Markupquellen verfügen häufig über ihre eigenen XAML-Namescopes, die nicht unbedingt mit dem XAML-Namescope der Seite verbunden sind. Weitere Informationen zu `x:Name` und XAML-Namescopes finden Sie unter <xref:System.Windows.FrameworkElement.Name%2A>, [x:Name-Direktive](../xaml-services/xname-directive.md) oder [WPF-XAML-Namescopes](../../framework/wpf/advanced/wpf-xaml-namescopes.md).

## <a name="attached-properties-and-attached-events"></a>Angefügte Eigenschaften und angefügte Ereignisse

In XAML ist ein Sprachfeature spezifiziert, das es ermöglicht, bestimmte Eigenschaften oder Ereignisse für jedes Element zu aktivieren, unabhängig davon, ob diese Eigenschaft oder dieses Ereignis in den Typdefinitionen für das Element vorhanden sind, für die sie festgelegt werden. Die Eigenschaftsversion dieser Funktion wird „angefügte Eigenschaft”, die Ereignisversion „angefügtes Ereignis” genannt. Im Prinzip können Sie sich angefügte Eigenschaften und Ereignisse als globale Mitglieder vorstellen, die für eine Instanz jedes XAML-Elements oder -Objekts festgelegt werden können. Jedoch muss dieses Element/diese Klasse oder eine größere Infrastruktur einen unterstützenden Eigenschaftenspeicher für die angefügten Werte unterstützen.

Angefügte Eigenschaften in XAML werden in der Regel über die Attributsyntax verwendet. In der Attributsyntax geben Sie eine angefügte Eigenschaft in der Form `ownerType.propertyName` an.

Oberflächlich betrachtet, gleicht dies der Verwendung eines Eigenschaftenelements, aber in diesem Fall ist der von Ihnen angegebene `ownerType` immer ein anderer Typ als das Objektelement, in dem die angefügte Eigenschaft festgelegt wird. `ownerType` ist der Typ, der die Accessormethoden bereitstellt, die von einem XAML-Prozessor zum Abrufen oder Festlegen des Werts der angefügten Eigenschaft benötigt werden.

Das häufigste Szenario für angefügte Eigenschaften ist, es untergeordneten Elementen zu ermöglichen, einen Eigenschaftswert an ihr übergeordnetes Element zu melden.

Das folgende Beispiel veranschaulicht die Verwendung der angefügten <xref:System.Windows.Controls.DockPanel.Dock%2A?displayProperty=nameWithType>-Eigenschaft. Die <xref:System.Windows.Controls.DockPanel>-Klasse definiert die Accessoren für <xref:System.Windows.Controls.DockPanel.Dock%2A?displayProperty=nameWithType> und ist daher Besitzer der angefügten Eigenschaft. Die <xref:System.Windows.Controls.DockPanel>-Klasse enthält auch Logik, die die untergeordneten Elemente durchläuft und jedes Element auf einen festgelegten Wert <xref:System.Windows.Controls.DockPanel.Dock%2A?displayProperty=nameWithType> prüft. Wenn ein Wert gefunden wird, wird dieser Wert während des Layouts zum Positionieren der untergeordneten Elemente verwendet. Die Verwendung der angefügten <xref:System.Windows.Controls.DockPanel.Dock%2A?displayProperty=nameWithType>-Eigenschaft und diese Positionierungsfunktion ist in der Tat das motivierende Szenario für die <xref:System.Windows.Controls.DockPanel>-Klasse.

[!code-xaml[XAMLOvwSupport#DockAP](~/samples/snippets/csharp/VS_Snippets_Wpf/XAMLOvwSupport/CSharp/page8.xaml#dockap)]

In WPF sind die meisten angefügten Eigenschaften auch als Abhängigkeitseigenschaften implementiert. Weitere Informationen finden Sie unter [Übersicht über angefügte Eigenschaften](../../framework/wpf/advanced/attached-properties-overview.md).

Angefügte Ereignisse verwenden eine ähnliche `ownerType.eventName`-Form der Attributsyntax. Wie bei nicht angefügten Ereignissen gibt der Attributwert für ein angefügtes Ereignis in XAML den Namen der Handlermethode an, die aufgerufen wird, wenn das Ereignis für das Element behandelt wird. Angefügte Ereignisse werden in WPF-XAML seltener verwendet. Weitere Informationen finden Sie unter [Übersicht über angefügte Ereignisse](../../framework/wpf/advanced/attached-events-overview.md).

## <a name="base-types-and-xaml"></a>Basistypen und XAML

WPF-XAML und dem zugehörigen XAML-Namespace liegt zusätzlich zu Markupelementen für XAML eine Auflistung von Typen zugrunde, die CLR-Objekten entsprechen. Allerdings können nicht alle Klassen Elementen zugeordnet werden. Abstrakte Klassen (z. B. <xref:System.Windows.Controls.Primitives.ButtonBase>) und bestimmte nicht abstrakte Basisklassen werden für Vererbung im CLR-Objektmodell verwendet. Basisklassen, einschließlich abstrakter Klassen, sind dennoch wichtig für die XAML-Entwicklung, da jedes konkrete XAML-Element Mitglieder einer Basisklasse in der eigenen Hierarchie erbt. Häufig enthalten diese Mitglieder Eigenschaften, die als Attribute für das Element festgelegt werden können, oder Ereignisse, die behandelt werden können. <xref:System.Windows.FrameworkElement> ist die konkrete Benutzeroberflächen-Basiskasse von WPF auf WPF-Frameworkebene. Beim Entwerfen von Benutzeroberfläche verwenden Sie verschiedene Form-, Bereichs-, Decorator- oder Steuerelemente-Klassen die alle von <xref:System.Windows.FrameworkElement> abgeleitet sind. Eine zugehörige Basisklasse (<xref:System.Windows.FrameworkContentElement>) unterstützt dokumentorientierte Elemente, die sich gut für eine Flusslayoutpräsentation eignen, wobei APIs verwendet werden, die die APIs in <xref:System.Windows.FrameworkElement> absichtlich spiegeln. Die Kombination aus Attributen auf Elementebene und einem CLR-Objektmodell stellt Ihnen eine Reihe von allgemeinen Eigenschaften bereit, die für die meisten konkreten XAML-Elemente unabhängig vom jeweiligen XAML-Element und dem zugrunde liegenden Typ festlegbar sind.

## <a name="xaml-security"></a>Sicherheit in XAML

XAML ist eine Markupsprache, die Objektinstanziierung und -ausführung direkt darstellt. Daher verfügen in XAML erstellte Elemente über dieselbe Fähigkeit zur Interaktion mit Systemressourcen (z.B. Netzwerkzugriff, Dateisystem E/A), wie der gleichwertig generierte Code. In eine voll vertrauenswürdige App geladenes XAML hat es den gleichen Zugriff auf Systemressourcen wie die Hostanwendung.

### <a name="code-access-security-cas-in-wpf"></a>Codezugriffssicherheit (Code Access Security, CAS) in WPF

**Dieser Abschnitt betrifft nur .NET Framework. CAS wird von WPF für .NET Core nicht unterstützt. Weitere Informationen finden Sie unter [Unterschiede in der Codezugriffssicherheit](../migration/differences-from-net-framework.md#code-access-security).**

WPF für .NET Framework unterstützt Codezugriffssicherheit (Code Access Security, CAS). Dies bedeutet, dass in der Internetzone ausgeführter WPF-Inhalt eingeschränkte Ausführungsberechtigungen hat. „Loose XAML“ (Seiten mitnicht kompiliertem XAML-Code, die beim Laden von einem XAML-Viewer interpretiert werden) und XBAP werden normalerweise in dieser Internetzone ausgeführt und verwenden die gleiche Berechtigungsmenge. Wenn XAML allerdings in eine voll vertrauenswürdige Anwendung geladen wird, hat es den gleichen Zugriff auf Systemressourcen wie die Hostanwendung. Weitere Informationen finden Sie unter [WPF-Sicherheit mit teilweiser Vertrauenswürdigkeit](../../framework/wpf/wpf-partial-trust-security.md).

## <a name="loading-xaml-from-code"></a>Laden von XAML aus Code

XAML kann zum Definieren der gesamten Benutzeroberfläche verwendet werden, aber manchmal ist es auch sinnvoll, nur einen Teil der Benutzeroberfläche in XAML zu definieren. Diese Fähigkeit könnte man für eine teilweise Anpassungsfähigkeit durch den Benutzer verwenden, lokales Speichern von Informationen, die Verwendung von XAML zur Bereitstellung eines Geschäftsobjekts oder eine Vielzahl weiterer möglicher Szenarios. Der Schlüssel zu diesen Szenarien sind die <xref:System.Windows.Markup.XamlReader>-Klasse und ihre <xref:System.Windows.Markup.XamlReader.Load%2A>-Methode. Als Eingabe dient eine XAML-Datei, und die Ausgabe ist ein Objekt, das die gesamte Laufzeitstruktur von Objekten darstellt, die über dieses Markup erstellt wurde. Sie können dieses Objekt dann als Eigenschaft eines anderen, bereits in der App vorhandenen Objekts einfügen. Solange die Eigenschaft eine geeignete Eigenschaft im Inhaltsmodell ist, die tatsächliche Anzeigefähigkeiten besitzt und die der Ausführungs-Engine meldet, dass in der App neue Inhalte hinzugefügt wurden, können Sie den Inhalt einer aktuell ausgeführten App einfach durch Laden von externem XAML ändern. Für .NET Framework ist aufgrund der offensichtlichen Sicherheitsimplikationen beim Laden von Dateien in aktuelle ausgeführten Anwendungen diese Funktion im Allgemeinen nur in voll vertrauenswürdigen Umgebungen verfügbar.

## <a name="see-also"></a>Siehe auch

- [Ausführliche Erläuterung der XAML-Syntax](../../framework/wpf/advanced/xaml-syntax-in-detail.md)
- [XAML- und benutzerdefinierte Klassen für WPF](../../framework/wpf/advanced/xaml-and-custom-classes-for-wpf.md)
- [XAML-Namespace (x:) Sprachfunktionen](../xaml-services/namespace-language-features.md)
- [WPF-XAML-Erweiterungen](../../framework/wpf/advanced/wpf-xaml-extensions.md)
- [Übersicht über Basiselemente](../../framework/wpf/advanced/base-elements-overview.md)
- [Strukturen in WPF](../../framework/wpf/advanced/trees-in-wpf.md)
