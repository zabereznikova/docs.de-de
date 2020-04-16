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
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/06/2020
ms.locfileid: "81433001"
---
# <a name="xaml-overview-in-wpf"></a>XAML-Übersicht in WPF

In diesem Artikel werden die Features der XAML-Sprache beschrieben und veranschaulicht, wie Sie XAML zum Schreiben von Windows Presentation Foundation (WPF)-Apps verwenden können. In diesem Artikel wird XAML speziell als von WPF implementiert beschrieben. XAML selbst ist ein größeres Sprachkonzept als WPF.

[!INCLUDE [desktop guide under construction](../../../includes/desktop-guide-preview-note.md)]

## <a name="what-is-xaml"></a>Was ist XAML

XAML ist eine deklarative Markupsprache. Wie auf das .NET Core-Programmiermodell angewendet, vereinfacht XAML das Erstellen einer Benutzeroberfläche für eine .NET Core-App. Sie können sichtbare UI-Elemente im deklarativen XAML-Markup erstellen und dann die UI-Definition von der Laufzeitlogik trennen, indem Sie CodeBehind-Dateien verwenden, die durch partielle Klassendefinitionen mit dem Markup verknüpft sind. XAML repräsentiert direkt die Instanziierung von Objekten in einem spezifischen Satz von in Assemblys definierten Unterstützungstypen dar. Dies ist ein anderer Ansatz als der anderer Markupsprachen, die üblicherweise interpretierte Sprachen sind, die keine direkte Verbindung zu einem System von Unterstützungstypen besitzen. XAML ermöglicht einen Workflow, in dem separate Parteien mit potenziell unterschiedlichen Tools an der Benutzeroberfläche und der Logik einer App arbeiten können.

Bei der Darstellung als Text sind XAML-Dateien XML-Dateien, die in der Regel die `.xaml`-Erweiterung haben. Die Dateien können in jeder XML-Codierung codiert sein, üblich ist jedoch UTF-8-Codierung.

Das folgende Beispiel zeigt, wie Sie eine Schaltfläche als Teil einer Benutzeroberfläche erstellen können. Dieses Beispiel soll Ihnen einen Vorgeschmack darauf geben, wie XAML allgemeine UI-Programmiermetaphern darstellt (es handelt sich nicht um ein vollständiges Beispiel).

[!code-xaml[XAMLOvwSupport#DirtSimple](~/samples/snippets/csharp/VS_Snippets_Wpf/XAMLOvwSupport/CSharp/page2.xaml#dirtsimple)]

## <a name="xaml-syntax-in-brief"></a>XAML-Syntax in Kürze

In den folgenden Abschnitten werden die grundlegenden Formen der XAML-Syntax erläutert und ein kurzes Markupbeispiel vorgestellt. Diese Abschnitte beabsichtigen keine Wiedergabe vollständiger Informationen über jedes Syntaxformat, z.B. wie diese im Unterstützungstypsystem dargestellt werden. Weitere Informationen zu den Besonderheiten der XAML-Syntax finden Sie unter [XAML-Syntax im Detail](../../framework/wpf/advanced/xaml-syntax-in-detail.md).

Ein Großteil des Materials in den nächsten Abschnitten wird für Sie elementar sein, wenn Sie bereits mit der XML-Sprache vertraut sind. Dies liegt im grundlegenden Entwurfsprinzip von XAML begründet. Die XAML-Sprache definiert eigene Konzepte, aber diese Konzepte funktionieren innerhalb der XML-Sprache und des Markupformulars.

### <a name="xaml-object-elements"></a>XAML-Objektelemente

Ein Objektelement deklariert in der Regel eine Instanz eines Typs. Dieser Typ wird in den Assemblys definiert, auf die von der Technologie verwiesen wird, die XAML als Sprache verwendet.

Objektelementsyntax beginnt immer mit einer öffnenden spitzen Klammer (`<`). Dies wird gefolgt vom Namen des Typs, in dem Sie eine Instanz erstellen möchten. (Der Name kann ein Präfix enthalten, ein Konzept, das später erläutert wird.) Danach können Sie optional Attribute für das Objektelement deklarieren. Um das Objektelement-Tag zu vervollständigen,`>`enden Sie mit einer schließenden winkeln den Winkel ( ). Sie können stattdessen ein selbstschließendes Formular verwenden, das keinen Inhalt hat, indem Sie das`/>`Tag mit einem Schrägstrich und einer schließenden winkelförmigen Klammer nacheinander ausfüllen ( ). Sehen Sie sich beispielsweise den zuvor angezeigten Markupausschnitt erneut an.

[!code-xaml[XAMLOvwSupport#DirtSimple](~/samples/snippets/csharp/VS_Snippets_Wpf/XAMLOvwSupport/CSharp/page2.xaml#dirtsimple)]

Hier werden zwei Objektelemente angegeben: `<StackPanel>` (mit Inhalt und einem später folgenden schließenden Tag) und `<Button .../>` (in selbstschließender Form, mit mehreren Attributen). Die `StackPanel` Objektelemente `Button` und jede Zuordnung zum Namen einer Klasse, die von WPF definiert wird und Teil der WPF-Assemblys ist. Wenn Sie ein Objektelement-Tag angeben, erstellen Sie eine Anweisung für die XAML-Verarbeitung, um eine neue Instanz des zugrunde liegenden Typs zu erstellen. Jede Instanz wird erstellt, indem beim Analysieren und Laden des XAML der parameterlose Konstruktor des zugrunde liegenden Typs aufgerufen wird.

### <a name="attribute-syntax-properties"></a>Attributsyntax (Eigenschaften)

Eigenschaften eines Objekts können oft als Attribute des Objektelements ausgedrückt werden. Die Attributsyntax benennt die Objekteigenschaft, die festgelegt wird, gefolgt vom Zuweisungsoperator (=). Der Wert eines Attributs wird immer als Zeichenfolge angegeben, die in Anführungszeichen eingeschlossen ist.

Die Attributsyntax ist die geradlinigste Syntax zur Festlegung von Eigenschaften und die intuitivste Syntax für Entwickler, die bereits in der Vergangenheit Markupsprachen verwendet haben. Das folgende Markup erstellt z.B. eine Schaltfläche mit rotem Text und einem blauen Hintergrund, wobei der anzuzeigende Textinhalt als `Content` angegeben ist.

[!code-xaml[XAMLOvwSupport#BlueRedButton](~/samples/snippets/csharp/VS_Snippets_Wpf/XAMLOvwSupport/CSharp/Page1.xaml#blueredbutton)]

### <a name="property-element-syntax"></a>Syntax für Eigenschaftselemente

Einige Eigenschaften eines Objektelements können nicht in Attributsyntax angegeben werden, da die Objekte oder Informationen, die für den Eigenschaftswert benötigt werden, nicht hinreichend innerhalb der durch Anführungszeichen und Zeichenfolgen beschränkten Attributsyntax ausgedrückt werden können. Für solche Fälle kann eine andere Syntax, die Eigenschaftenelement-Syntax genannt wird, verwendet werden.

Die Syntax für das Eigenschaftenelement start-Tag ist `<TypeName.PropertyName>`. Im Allgemeinen ist der Inhalt dieses Tags ein Objektelement des Typs, den die Eigenschaft als Wert annimmt. Nachdem Sie den Inhalt angegeben haben, müssen Sie das Eigenschaftselement mit einem Endtag schließen. Die Syntax für das `</TypeName.PropertyName>`Endtag lautet .

Wenn Attributsyntax möglich ist, ist deren Verwendung in der Regel bequemer und ermöglicht ein kompakteres Markup, aber das ist oft nur eine Frage des Stils, keine technische Einschränkung. Das folgende Beispiel zeigt die Festlegung derselben Eigenschaften wie im vorherigen Attributsyntax-Beispiel, aber dieses Mal unter Verwendung von Eigenschaftenelement-Syntax für alle Eigenschaften des `Button`-Elements.

[!code-xaml[XAMLOvwSupport#BlueRedButtonPE](~/samples/snippets/csharp/VS_Snippets_Wpf/XAMLOvwSupport/CSharp/Page1.xaml#blueredbuttonpe)]

### <a name="collection-syntax"></a>Sammlungsyntax

Die XAML-Sprache enthält einige Optimierungen, die besser lesbares Markup erstellen. Eine dieser Optimierungen bewirkt, dass bei Eigenschaften, die vom Typ Auflistung sind, Elemente, die Sie in Markup als untergeordnete Elemente dieses Eigenschaftswerts anlegen, automatisch Teil der Auflistung werden. In diesem Fall ist der Wert, welcher der Auflistungseigenschaft zugewiesen wird, eine Auflistung von untergeordneten Objektelementen.

Das folgende Beispiel zeigt die Auflistungssyntax zum Festlegen von Werten der <xref:System.Windows.Media.GradientBrush.GradientStops%2A> Eigenschaft.

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

XAML gibt ein Sprachfeature an, bei dem eine Klasse genau _content_ eine ihrer Eigenschaften als XAML-Inhaltseigenschaft festlegen kann. Untergeordnete Elemente dieses Objektelements werden verwendet, um den Wert dieser Inhaltseigenschaft festzulegen. Anders gesagt: nur für die Inhaltseigenschaft dürfen Sie ein Eigenschaftenelement beim Festlegen dieser Eigenschaft in XAML-Markup auslassen und so eine besser sichtbare übergeordnet/untergeordnet-Metapher im Markup erzeugen.

<xref:System.Windows.Controls.Border> Gibt z. B. eine <xref:System.Windows.Controls.Decorator.Child%2A> _content-Eigenschaft_ von an. Die folgenden <xref:System.Windows.Controls.Border> beiden Elemente werden identisch behandelt. Der erste nutzt den Vorteil der Inhaltseigenschaften-Syntax und lässt das `Border.Child`-Eigenschaftenelement aus. Das zweite Beispiel zeigt `Border.Child` explizit.

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

In der XAML-Sprache gilt die Regel, dass der Wert einer XAML-Inhaltseigenschaft nur vor oder nach allen anderen Eigenschaftenelemente für dieses Objektelement festgelegt werden darf. Das folgende Markup wird z. B. nicht kompiliert.

```xaml
<Button>I am a
  <Button.Background>Blue</Button.Background>
  blue button</Button>
```

Weitere Informationen zu den Besonderheiten der XAML-Syntax finden Sie unter [XAML-Syntax im Detail](../../framework/wpf/advanced/xaml-syntax-in-detail.md).

### <a name="text-content"></a>Textinhalt

Eine kleine Anzahl von XAML-Elementen kann Text direkt als Inhalt verarbeiten. Um dies zu ermöglichen, muss einer der folgenden Fälle zutreffen:

- Die Klasse muss eine content-Eigenschaft deklarieren, und diese content-Eigenschaft muss <xref:System.Object>von einem Typ sein, der einer Zeichenfolge zugewiesen werden kann (der Typ könnte sein ). Beispielsweise wird <xref:System.Windows.Controls.ContentControl> jede <xref:System.Windows.Controls.ContentControl.Content%2A> Verwendung als Content-Eigenschaft <xref:System.Object>verwendet, und es ist <xref:System.Windows.Controls.ContentControl> typ <xref:System.Windows.Controls.Button>, `<Button>Hello</Button>`und dies unterstützt die folgende Verwendung in einer z. B. : .

- Der Typ muss einen Typkonverter deklarieren, für den in diesem Fall der Textinhalt als Initialisierungstext verwendet wird. `<Brush>Blue</Brush>` Konvertiert z. B. den `Blue` Inhaltswert von in einen Pinsel. Dieser Fall ist in der Praxis weniger häufig.

- Der Typ muss eine bekanntes XAML-Sprachprimitiv sein.

### <a name="content-properties-and-collection-syntax-combined"></a>Inhaltseigenschaften und Auflistungssyntax kombiniert

Betrachten Sie dieses Beispiel.

```xaml
<StackPanel>
  <Button>First Button</Button>
  <Button>Second Button</Button>
</StackPanel>
```

Hier ist <xref:System.Windows.Controls.Button> jedes ein <xref:System.Windows.Controls.StackPanel>untergeordnetes Element von . Dies ist ein optimiertes und intuitives Markup, bei dem zwei Tags aus zwei verschiedenen Gründen weggelassen wurden.

- **Ausgelassenes StackPanel.Children-Eigenschaftselement:** <xref:System.Windows.Controls.StackPanel> leitet von ab. <xref:System.Windows.Controls.Panel> <xref:System.Windows.Controls.Panel>definiert <xref:System.Windows.Controls.Panel.Children%2A?displayProperty=nameWithType> als XAML-Inhaltseigenschaft.

- **Ausgelassenes UIElementCollection-Objektelement:** Die <xref:System.Windows.Controls.Panel.Children%2A?displayProperty=nameWithType> Eigenschaft nimmt <xref:System.Windows.Controls.UIElementCollection>den Typ <xref:System.Collections.IList>an, der implementiert. Das Element-Tag der Auflistung kann auf der Grundlage der XAML-Regeln für die Verarbeitung von Auflistungen wie <xref:System.Collections.IList>ausgelassen werden. (In diesem <xref:System.Windows.Controls.UIElementCollection> Fall kann eigentlich nicht instanziiert werden, da kein parameterloser Konstruktor verfügbar gemacht wird, und aus diesem Grund wird das <xref:System.Windows.Controls.UIElementCollection> Objektelement auskommentiert angezeigt).

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

Attributsyntax kann auch für Mitglieder verwendet werden, die Ereignisse und keine Eigenschaften sind. In diesem Fall ist der Name des Attributs der Name des Ereignisses. In der WPF-Implementierung von Ereignissen für XAML ist der Wert des Attributs der Name eines Ereignishandlers, der den Ereignisdelegaten implementiert. Das folgende Markup weist z. B. <xref:System.Windows.Controls.Primitives.ButtonBase.Click> einem <xref:System.Windows.Controls.Button> in Markup erstellten Profil up einen Handler für das Ereignis zu:

[!code-xaml[XAMLOvwSupport#ButtonWithCodeBehind](~/samples/snippets/csharp/VS_Snippets_Wpf/XAMLOvwSupport/CSharp/page3.xaml#buttonwithcodebehind)]

Es steckt noch mehr hinter Ereignissen und XAML in WPF, als dieses Beispiel für die Attributsyntax zeigt. So fragen Sie sich vielleicht, was der hier referenzierte `ClickHandler` darstellt und wie er definiert wird. Dies wird im kommenden [Abschnitt "Events" und "XAML codebehind"](#events-and-xaml-code-behind) in diesem Artikel erläutert.

## <a name="case-and-white-space-in-xaml"></a>Gehäuse und Leerraum in XAML

Im Allgemeinen wird bei XAML die Groß-/Kleinschreibung beachtet. Zum Auflösen von Sicherungstypen wird bei WPF XAML die Groß-/Kleinschreibung nach denselben Regeln berücksichtigt, bei denen die Groß-/Kleinschreibung der CLR berücksichtigt wird. Bei Objektelementen, Eigenschaftenelementen und Attributnamen muss beim Vergleich anhand des Namens des zugrunde liegenden Typs in der Assembly oder eines Typmitglieds immer die Groß-/Kleinschreibung beachtet werden. XAML-Sprachschlüsselwörter und Primitive werden ebenfalls von Groß-/Kleinschreibung berücksichtigt. Bei Werten wird die Groß-/Kleinschreibung nicht immer berücksichtigt. Ob bei Werten Groß-/Kleinschreibung beachtet wird, hängt vom Verhalten ab, das dem Typkonverter für die den Wert annehmende Eigenschaft zugeordnet ist, oder vom Typ des Eigenschaftswerts. Beispielsweise können Eigenschaften, <xref:System.Boolean> die den `true` Typ `True` annehmen, entweder oder als äquivalente Werte verwendet werden, jedoch <xref:System.Boolean> nur, weil die native WPF XAML-Parsertypkonvertierung für string bereits diese als Äquivalente zulässt.

WPF XAML-Prozessoren und Serialisierer ignorieren oder löschen den gesamten nicht signifikanten Leerraum und normalisieren jeden signifikanten Leerraum. Dies stimmt mit den standardmäßigen White-Space-Verhaltensempfehlungen der XAML-Spezifikation überein. Dieses Verhalten ist nur dann von Bedeutung, wenn Sie Zeichenfolgen innerhalb von XAML-Inhaltseigenschaften angeben. In einfachen Worten konvertiert XAML Leerzeichen, Zeilenvorschub- und Tabstoppzeichen in Leerzeichen und behält dann ein Leerzeichen bei, wenn es an beiden Enden einer zusammenhängenden Zeichenfolge gefunden wird. Die vollständige Erläuterung der XAML-Leerraumbehandlung wird in diesem Artikel nicht behandelt. Weitere Informationen finden Sie [unter Leerraumverarbeitung in XAML](../xaml-services/white-space-processing.md).

## <a name="markup-extensions"></a>Markuperweiterungen

Markuperweiterungen sind ein XAML-Sprachkonzept. Wenn geschweifte Klammern zum Bereitstellen des Werts einer Attributsyntax verwendet werden (`{` und `}`), handelt es sich dabei um die Verwendung einer Markuperweiterung. Diese Verwendung weist den XAML-Prozessor an, von der allgemeinen Behandlung von Attributwerten als Zeichenfolgenliteral oder zu einer Zeichenfolge konvertierbarem Wert abzuweichen.

Die am häufigsten verwendeten Markuperweiterungen, [`Binding`](../../framework/wpf/advanced/binding-markup-extension.md)die in der WPF-App-Programmierung verwendet werden, sind , die für Datenbindungsausdrücke verwendet werden, und die Ressourcenverweise [`StaticResource`](../../framework/wpf/advanced/staticresource-markup-extension.md) und [`DynamicResource`](../../framework/wpf/advanced/dynamicresource-markup-extension.md). Durch die Verwendung von Markuperweiterungen können Sie mit Attributsyntax auch dann Werte für Eigenschaften bereitstellen, wenn diese Eigenschaft im Allgemeinen keine Attributsyntax unterstützt. Markuperweiterungen verwenden häufig Zwischenausdruckstypen, um Features wie das Aufschieben von Werten oder das Verweisen auf andere Objekte zu aktivieren, die nur zur Laufzeit vorhanden sind.

Das folgende Markup legt beispielsweise den <xref:System.Windows.FrameworkElement.Style%2A> Wert der Eigenschaft mithilfe der Attributsyntax fest. Die <xref:System.Windows.FrameworkElement.Style%2A> Eigenschaft nimmt eine <xref:System.Windows.Style> Instanz der Klasse an, die standardmäßig nicht durch eine Attributsyntaxzeichenfolge instanziiert werden konnte. In diesem Fall verweist das Attribut jedoch `StaticResource`auf eine bestimmte Markuperweiterung , . Wenn diese Markuperweiterung verarbeitet wird, wird ein Verweis auf einen Stil zurückgegeben, der bereits zuvor als mit einem Schlüssel versehene Ressource in einem Ressourcenverzeichnis instanziiert wurde.

[!code-xaml[FEResourceSH_snip#XAMLOvwShortResources](~/samples/snippets/csharp/VS_Snippets_Wpf/FEResourceSH_snip/CS/page1.xaml#xamlovwshortresources)]
[!code-xaml[FEResourceSH_snip#XAMLOvwShortResources2](~/samples/snippets/csharp/VS_Snippets_Wpf/FEResourceSH_snip/CS/page1.xaml#xamlovwshortresources2)]
[!code-xaml[FEResourceSH_snip#XAMLOvwShortResources3](~/samples/snippets/csharp/VS_Snippets_Wpf/FEResourceSH_snip/CS/page1.xaml#xamlovwshortresources3)]

Eine Verweisliste mit Markuperweiterungen für XAML, die spezifisch in WPF implementiert sind, finden Sie unter [WPF-XAML-Erweiterungen](../../framework/wpf/advanced/wpf-xaml-extensions.md). Eine Referenzliste der Markuperweiterungen, die von System.Xaml definiert sind und für .NET Core XAML-Implementierungen breiter verfügbar sind, finden Sie unter [XAML Namespace (x:) Sprachfunktionen](../xaml-services/namespace-language-features.md). Weitere Informationen über die Konzepte der Markuperweiterungen finden Sie unter [Markuperweiterungen und WPF XAML](../../framework/wpf/advanced/markup-extensions-and-wpf-xaml.md).

## <a name="type-converters"></a>Typkonverter

Im Abschnitt [XAML-Syntax in Kürze](#xaml-syntax-in-brief) wurde behauptet, dass man den Attributwert durch eine Zeichenfolge festlegen können muss. Die grundlegende, systemeigene Behandlung der Konvertierung von Zeichenfolgen in <xref:System.String> andere Objekttypen oder primitive Werte basiert <xref:System.DateTime> auf <xref:System.Uri>dem Typ selbst, zusätzlich zur systemeigenen Verarbeitung für bestimmte Typen wie oder . Viele WPF-Typen oder Member dieser Typen erweitern jedoch das grundlegende Verarbeitungsverhalten von Zeichenfolgenattributen so, dass Instanzen komplexerer Objekttypen als Zeichenfolgen und Attribute angegeben werden können.

Die <xref:System.Windows.Thickness> Struktur ist ein Beispiel für einen Typ, für den eine Typkonvertierung für XAML-Verwendungen aktiviert ist. <xref:System.Windows.Thickness>gibt Messungen innerhalb eines verschachtelten Rechtecks an und <xref:System.Windows.FrameworkElement.Margin%2A>wird als Wert für Eigenschaften wie verwendet. Durch Platzieren eines <xref:System.Windows.Thickness>Typkonverters auf <xref:System.Windows.Thickness> sind alle Eigenschaften, die a verwenden, in XAML einfacher anzugeben, da sie als Attribute angegeben werden können. Im folgenden Beispiel wird eine Typkonvertierung und Attributsyntax verwendet, um einen Wert für eine <xref:System.Windows.FrameworkElement.Margin%2A>bereitzustellen:

[!code-xaml[XAMLOvwSupport#MarginTCE](~/samples/snippets/csharp/VS_Snippets_Wpf/XAMLOvwSupport/CSharp/page7.xaml#margintce)]

Das vorherige Attributsyntaxbeispiel entspricht dem folgenden ausführlicheren Syntaxbeispiel, bei dem der stattdessen durch die Eigenschaftenelementsyntax festgelegt wird, die <xref:System.Windows.FrameworkElement.Margin%2A> ein <xref:System.Windows.Thickness> Objektelement enthält. Die vier Schlüsseleigenschaften von <xref:System.Windows.Thickness> sind als Attribute für die neue Instanz festgelegt:

[!code-xaml[XAMLOvwSupport#MarginVerbose](~/samples/snippets/csharp/VS_Snippets_Wpf/XAMLOvwSupport/CSharp/page7.xaml#marginverbose)]

> [!NOTE]
> Es gibt auch eine begrenzte Anzahl von Objekten, bei denen die Typkonvertierung die einzige öffentliche Möglichkeit ist, eine Eigenschaft auf diesen Typ festzulegen, ohne eine Unterklasse einzubeziehen, da der Typ selbst keinen parameterlosen Konstruktor hat. z. B. <xref:System.Windows.Input.Cursor>.

Weitere Informationen zur Typkonvertierung finden Sie unter [TypeConverters und XAML](../../framework/wpf/advanced/typeconverters-and-xaml.md).

## <a name="xaml-root-elements-and-xaml-namespaces"></a>XAML-Stammelemente und XAML-Namespaces

Eine XAML-Datei darf nur über ein Stammelement verfügen, um sowohl eine wohlgeformte XML-Datei als auch eine gültige XAML-Datei zu sein. Für typische WPF-Szenarien verwenden Sie ein Stammelement, das im WPF-App-Modell eine <xref:System.Windows.ResourceDictionary> herausragende Bedeutung hat <xref:System.Windows.Application> (z. B. <xref:System.Windows.Window> für <xref:System.Windows.Controls.Page> eine Seite, für ein externes Wörterbuch oder für die App-Definition). Das folgende Beispiel zeigt das Stammelement einer typischen XAML-Datei für <xref:System.Windows.Controls.Page>eine WPF-Seite mit dem Stammelement von .

[!code-xaml[XAMLOvwSupport#RootOnly](~/samples/snippets/csharp/VS_Snippets_Wpf/XAMLOvwSupport/CSharp/page2.xaml#rootonly)]
[!code-xaml[XAMLOvwSupport#RootOnly2](~/samples/snippets/csharp/VS_Snippets_Wpf/XAMLOvwSupport/CSharp/page2.xaml#rootonly2)]

Das Stammelement enthält auch die Attribute `xmlns` und `xmlns:x`. Diese Attribute geben einem XAML-Prozessor an, welche XAML-Namespaces die Typdefinitionen für Unterstützungstypen enthalten, auf die das Markup als Elemente verweist. Das `xmlns`-Attribut gibt ausdrücklich den XAML-Standardnamespace an. Innerhalb des XAML-Standardnamespaces können Objektelemente im Markup ohne Präfix angegeben werden. Für die meisten WPF-App-Szenarien und für fast alle Beispiele in den WPF-Abschnitten des SDK wird der `http://schemas.microsoft.com/winfx/2006/xaml/presentation`standardmäßige XAML-Namespace dem WPF-Namespace zugeordnet. Das `xmlns:x`-Attribut gibt einen zusätzlichen XAML-Namespace an, der dem XAML-Sprachnamespace `http://schemas.microsoft.com/winfx/2006/xaml` zugeordnet ist.

Diese Verwendung von `xmlns` zum Definieren eines Geltungsbereich für die Verwendung und Zuordnung eines Namescopes ist mit der XML 1.0-Spezifikation verträglich. XAML-Namescopes unterscheiden sich von XML-Namescopes nur darin, dass ein XAML-Namescope auch darüber etwas impliziert, wie Elemente durch Typen unterstützt werden, wenn es zur Typauflösung und Analyse des XAML-Codes kommt.

Die `xmlns` Attribute sind nur für das Stammelement jeder XAML-Datei unbedingt erforderlich. `xmlns`-Definitionen gelten für alle Nachfolgerelemente des Stammelements (dieses Verhalten entspricht wieder der XML 1.0-Spezifikation für `xmlns`.) `xmlns`-Attribute sind auch bei anderen Elementen unterhalb des Stamms zulässig und gelten für alle Nachfolgerelemente des definierenden Elements. Allerdings kann häufiges Definieren oder Neudefinieren von XAML-Namespaces zu einem nur schwer lesbaren XAML-Markup-Stil führen.

Die WPF-Implementierung des XAML-Prozessors umfasst eine Infrastruktur, die für die WPF-Kernassemblys bekannt ist. Es ist bekannt, dass die WPF-Kernassemblys die Typen enthalten, die die WPF-Zuordnungen zum standardmäßigen XAML-Namespace unterstützen. Dies wird durch eine Konfiguration ermöglicht, die Teil Ihrer Projekt-Builddatei und des WPF-Builds und -Projektsystems ist. Daher ist das Deklarieren des standardmäßigen `xmlns` XAML-Namespace als Standard alles, was erforderlich ist, um auf XAML-Elemente zu verweisen, die aus WPF-Assemblys stammen.

### <a name="the-x-prefix"></a>Das x:-Präfix

Im vorherigen Beispiel zum Stammelement wurde das Präfix `x:` verwendet, um den XAML-Namespaces `http://schemas.microsoft.com/winfx/2006/xaml` zuzuordnen, also der dedizierte XAML-Namespace, der XAML-Sprachkonstrukte unterstützt. Dieses `x:` Präfix wird zum Zuordnen dieses XAML-Namespace in den Vorlagen für Projekte, in Beispielen und in der Dokumentation in diesem SDK verwendet. Der XAML-Namespace für die XAML-Sprache enthält mehrere Programmierkonstrukte, die Sie häufig in Ihrem XAML verwenden. Im folgenden finden Sie eine Liste der häufigsten `x:`-Präfix-Programmierkonstrukte, die Sie verwenden werden:

- [x:Key](../xaml-services/xkey-directive.md): Legt einen eindeutigen <xref:System.Windows.ResourceDictionary> Schlüssel für jede Ressource in einem (oder ähnlichen Wörterbuchkonzepten in anderen Frameworks) fest. `x:Key`90 Prozent der Nutzungen, die `x:` Sie im Markup einer typischen WPF-App sehen, machen wahrscheinlich aus.

- [x:Class](../xaml-services/xclass-directive.md): Gibt den CLR-Namespace und den Klassennamen für die Klasse an, die CodeBehind für eine XAML-Seite bereitstellt. Das WPF-Programmiermodell schreibt eine solche Klasse für CodeBehind-Unterstützung vor, weshalb Sie fast immer eine Zuordnung von `x:` sehen werden, selbst wenn keine Ressourcen vorhanden sind.

- [x:Name](../xaml-services/xname-directive.md): Gibt einen Namen für das Laufzeitobjekt einer Instanz an, die im Laufzeitcode existiert, nachdem ein Objektelement verarbeitet ist. Im Allgemeinen werden Sie häufig eine entsprechende WPF-definierte Eigenschaft für [x:Name](../xaml-services/xname-directive.md) verwenden. Solche Eigenschaften werden speziell einer CLR-Backing-Eigenschaft zugeordnet und eignen sich daher bequemer für die App-Programmierung, bei der Sie häufig Laufzeitcode verwenden, um die benannten Elemente aus initialisiertem XAML zu finden. Die häufigste Eigenschaft <xref:System.Windows.FrameworkElement.Name%2A?displayProperty=nameWithType>dieser Art ist . Sie können [x:Name](../xaml-services/xname-directive.md) weiterhin verwenden, wenn <xref:System.Windows.FrameworkElement.Name%2A> die entsprechende WPF-Framework-Level-Eigenschaft in einem bestimmten Typ nicht unterstützt wird. Dies ist bei einigen Animations-Szenarios der Fall.

- [x:Static](../xaml-services/xstatic-markup-extension.md): Ermöglicht einen Verweis, der einen statischen Wert zurückgibt, der nicht anderweitig als XAML-kompatible Eigenschaft verwendbar ist.

- [x:Typ](../xaml-services/xtype-markup-extension.md): Erstellt <xref:System.Type> einen Verweis basierend auf einem Typnamen. Dies wird verwendet, um <xref:System.Type>Attribute <xref:System.Windows.Style.TargetType%2A?displayProperty=nameWithType>anzugeben, die nehmen, z.<xref:System.Type> B. , obwohl die Eigenschaft häufig über eine systemeigene Zeichenfolge-zu-Konvertierung verfügt, sodass die Verwendung der [x:Type-Markuperweiterung](../xaml-services/xtype-markup-extension.md) optional ist.

Es gibt weitere Programmierkonstrukte im `x:`-Präfix/XAML-Namespace, die nicht so häufig verwendet werden. Weitere Informationen finden Sie unter [Sprachfunktionen des XAML-Namespace (x:)](../xaml-services/namespace-language-features.md).

## <a name="custom-prefixes-and-custom-types-in-xaml"></a>Benutzerdefinierte Präfixe und benutzerdefinierte Typen in XAML

Für eigene benutzerdefinierte Assemblys oder für Assemblys außerhalb des WPF-Kerns von **PresentationCore**, `xmlns` **PresentationFramework** und **WindowsBase**können Sie die Assembly als Teil einer benutzerdefinierten Zuordnung angeben. Sie können dann auf Typen aus dieser Assembly in Ihrem XAML verweisen, sofern dieser Typ korrekt implementiert wird, um die von Ihnen beabsichtigten XAML-Verwendungen zu unterstützen.

Im Folgenden finden Sie ein grundlegendes Beispiel für die Funktionsweise benutzerdefinierter Präfixe im XAML-Markup. Das Präfix `custom` wird im Root-Element-Tag definiert und einer bestimmten Assembly zugeordnet, die mit der App verpackt und verfügbar ist. Diese Assembly enthält einen Typ `NumericUpDown`, der für die Unterstützung allgemeiner XAML-Verwendung implementiert ist und eine Klassenvererbung verwendet, die ihre Einfügung an diesem bestimmten Punkt im WPF-XAML-Inhaltsmodell zulässt. Eine Instanz dieses `NumericUpDown`-Steuerelements wird mithilfe des Präfix als Objektelement deklariert, damit der XAML-Parser weiß, welcher XAML-Namespace den Typ enthält und damit auch, wo sich die Unterstützungsassembly befindet, die die Typdefinition enthält.

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

Weitere Informationen dazu, wie XML-Namespaces und Codenamespaces in Assemblys miteinander verknüpft sind, finden Sie unter [XAML-Namespaces und Namespace-Zuordnung für WPF XAML](../../framework/wpf/advanced/xaml-namespaces-and-namespace-mapping-for-wpf-xaml.md).

## <a name="events-and-xaml-code-behind"></a>Ereignisse und XAML-CodeBehind

Die meisten WPF-Apps bestehen sowohl aus XAML-Markup als auch code-Behind. Innerhalb eines Projekts wird das XAML als `.xaml` Datei geschrieben, und eine CLR-Sprache wie Microsoft Visual Basic oder C- wird verwendet, um eine CodeBehind-Datei zu schreiben. Wenn das Markup einer XAML-Datei als Teil der WPF-Programmierungs- und -Anwendungsmodelle kompiliert wird, wird der Speicherort der XAML-CodeBehind-Datei für eine XAML-Datei durch Angeben eines Namespaces und einer Klasse als `x:Class`-Attribut des Stammelements des XAML identifiziert.

In den bisherigen Beispielen haben Sie verschiedene Schaltflächen gesehen, aber noch war keiner dieser Schaltflächen ein logisches Verhalten zugeordnet. Der primäre Mechanismus auf Anwendungsebene zum Hinzufügen eines Verhaltens für ein Objektelement besteht darin, ein vorhandenes Ereignis der Elementklasse zu verwenden und einen bestimmten Handler für dieses Ereignis zu schreiben, das aufgerufen wird, wenn dieses Ereignis zur Laufzeit ausgelöst wird. Der Name des Ereignisses und der Name der zu verwendenden Handler werden im Markup angegeben, während der Code, der den Handler implementiert, im CodeBehind definiert ist.

[!code-xaml[XAMLOvwSupport#ButtonWithCodeBehind](~/samples/snippets/csharp/VS_Snippets_Wpf/XAMLOvwSupport/CSharp/page3.xaml#buttonwithcodebehind)]

[!code-csharp[XAMLOvwSupport#ButtonWithCodeBehindHandler](~/samples/snippets/csharp/VS_Snippets_Wpf/XAMLOvwSupport/CSharp/page3.xaml.cs#buttonwithcodebehindhandler)]
[!code-vb[XAMLOvwSupport#ButtonWithCodeBehindHandler](~/samples/snippets/visualbasic/VS_Snippets_Wpf/XAMLOvwSupport/VisualBasic/Page1.xaml.vb#buttonwithcodebehindhandler)]

Beachten Sie, dass die CodeBehind-Datei den CLR-Namespace `ExampleNamespace` verwendet und `ExamplePage` als partielle Klasse in diesem Namespace deklariert. Dies entspricht dem `x:Class`-Attributwert von `ExampleNamespace`.`ExamplePage`, der im Stammelement des Markups bereitgestellt wurde. Der WPF-Markupcompiler erstellt für jede kompilierte XAML-Datei eine partielle Klasse durch Ableiten einer Klasse des Typs des Stammelements. Wenn Sie CodeBehind bereitstellen, der auch dieselbe Partielle Klasse definiert, wird der resultierende Code innerhalb desselben Namespace und derselben Klasse der kompilierten App kombiniert.

Weitere Informationen zu Anforderungen für die CodeBehind-Programmierung in WPF finden Sie unter [Code-Behind, Event Handler und Partial Class Requirements in WPF](../../framework/wpf/advanced/code-behind-and-xaml-in-wpf.md#code-behind-event-handler-and-partial-class-requirements-in-wpf).

Wenn Sie keine separate CodeBehind-Datei erstellen möchten, können Sie Ihren den Code auch inline in eine XAML-Datei schreiben. Inline-Code ist jedoch eine weniger vielseitige Technik, die erhebliche Einschränkungen hat. Weitere Informationen finden Sie [unter Code-Behind und XAML in WPF](../../framework/wpf/advanced/code-behind-and-xaml-in-wpf.md).

### <a name="routed-events"></a>Routingereignisse

Ein bestimmtes Ereignisfeature, das für WPF von grundlegender Bedeutung ist, ist ein routingiertes Ereignis. Routingereignisse ermöglichen es einem Element, ein Ereignis zu behandeln, das durch ein anderes Element ausgelöst wurde, solange diese Elemente über eine strukturelle Beziehung verbunden sind. Gibt man eine Ereignisbehandlung über ein XAML-Attribut an, kann jedes beliebige Element nach diesem Routingereignis lauschen und es behandeln, einschließlich der Elemente, für die dieses bestimmte Element nicht in der Mitgliedstabelle der Klasse aufgeführt ist. Dies wird durch Qualifizierung des Ereignisnamen-Attributs mit dem besitzenden Klassennamen erreicht. Beispielsweise kann das `StackPanel` übergeordnete `StackPanel`  /  `Button` Element im laufenden Beispiel einen Handler <xref:System.Windows.Controls.Primitives.ButtonBase.Click> für das Ereignis `Button.Click` der `StackPanel` untergeordneten Elementschaltfläche registrieren, indem es das Attribut für das Objektelement mit dem Handlernamen als Attributwert angibt. Weitere Informationen finden Sie unter Übersicht über [geroutete Ereignisse](../../framework/wpf/advanced/routed-events-overview.md).

## <a name="xaml-named-elements"></a>XAML-Benannte Elemente

Die Objektinstanz, die in einem Objektdiagramm durch Verarbeitung eines XAML-Objektelements erstellt wird, hat standardmäßig keinen eindeutigen Bezeichner oder Objektverweis. Wenn Sie allerdings einen Konstruktor im Code aufrufen, verwenden Sie fast immer das Konstruktorergebnis zum Festlegen einer Variablen auf die erstellte Instanz, damit Sie später im Code auf die Instanz verweisen können. Um standardisierten Zugriff auf Objekte bereitzustellen, die durch eine Markupdefinition erstellt wurden, definiert XAML-Code das [x:Name-Attribut](../xaml-services/xname-directive.md). Sie können den Wert des `x:Name`-Attributs auf jedes beliebiges Objektelement festlegen. Im CodeBehind entspricht der von Ihnen gewählte Bezeichner einer Instanzvariablen, die auf die erstellte Instanz verweist. In jeder Hinsicht funktionieren benannte Elemente so, als wären sie Objektinstanzen (der Name verweist auf diese Instanz), und Ihr CodeBehind kann auf die benannten Elemente verweisen, um Laufzeitinteraktionen innerhalb der App zu behandeln. Diese Verbindung zwischen Instanzen und Variablen wird vom WPF XAML-Markupcompiler <xref:System.Windows.Markup.IComponentConnector.InitializeComponent%2A> hergestellt und umfasst insbesondere Features und Muster, wie sie in diesem Artikel nicht im Detail erläutert werden.

XAML-Elemente auf WPF-Frameworkebene <xref:System.Windows.FrameworkElement.Name%2A> erben eine Eigenschaft, die dem `x:Name` xAML-definierten Attribut entspricht. Bestimmte andere Klassen bieten ebenfalls Entsprechungen für `x:Name` auf Eigenschaftenebene, was in der Regel ebenfalls als `Name`-Eigenschaft definiert ist. Allgemein gilt, dass Sie ersatzweise `x:Name` nutzen sollten, wenn Sie keine `Name`-Eigenschaft in der Mitgliedertabelle Ihres gewünschten Elements/Typs finden können. Die `x:Name` Werte stellen einen Bezeichner für ein XAML-Element bereit, das zur Laufzeit entweder <xref:System.Windows.FrameworkElement.FindName%2A>von bestimmten Subsystemen oder von Dienstprogrammmethoden wie verwendet werden kann.

Im folgenden <xref:System.Windows.FrameworkElement.Name%2A> Beispiel <xref:System.Windows.Controls.StackPanel> wird für ein Element festgelegt. Dann verweist ein <xref:System.Windows.Controls.Button> Handler <xref:System.Windows.Controls.StackPanel> auf <xref:System.Windows.Controls.StackPanel> ein innerhalb, `buttonContainer` der <xref:System.Windows.FrameworkElement.Name%2A>auf den durch seine Instanzreferenz verweist, wie von festgelegt.

[!code-xaml[XAMLOvwSupport#NamedE](~/samples/snippets/csharp/VS_Snippets_Wpf/XAMLOvwSupport/CSharp/page7.xaml#namede)]
[!code-xaml[XAMLOvwSupport#NamedE2](~/samples/snippets/csharp/VS_Snippets_Wpf/XAMLOvwSupport/CSharp/page7.xaml#namede2)]

[!code-csharp[XAMLOvwSupport#NameCode](~/samples/snippets/csharp/VS_Snippets_Wpf/XAMLOvwSupport/CSharp/page7.xaml.cs#namecode)]
[!code-vb[XAMLOvwSupport#NameCode](~/samples/snippets/visualbasic/VS_Snippets_Wpf/XAMLOvwSupport/VisualBasic/Page1.xaml.vb#namecode)]

Der XAML-Name einer Instanz unterliegt genau wie eine Variable dem Konzept eines Geltungsbereichs, sodass die Eindeutigkeit von Namen innerhalb eines bestimmten, vorhersagbaren Geltungsbereichs erzwungen werden kann. Das primäre Markup, das eine Seite definiert, kennzeichnet einen eindeutigen XAML-Namescope, dessen Grenze das Stammelement dieser Seite ist. Andere Markupquellen können jedoch zur Laufzeit mit einer Seite interagieren, z. B. Stile oder Vorlagen innerhalb von Formatvorlagen, und solche Markupquellen verfügen häufig über eigene XAML-Namescopes, die nicht unbedingt eine Verbindung mit dem XAML-Namescope der Seite herstellen. Weitere Informationen `x:Name` zu und XAML-Namescopes finden Sie unter <xref:System.Windows.FrameworkElement.Name%2A>, [x:Name-Direktive](../xaml-services/xname-directive.md)oder [WPF XAML-Namescopes](../../framework/wpf/advanced/wpf-xaml-namescopes.md).

## <a name="attached-properties-and-attached-events"></a>Angefügte Eigenschaften und angefügte Ereignisse

In XAML ist ein Sprachfeature spezifiziert, das es ermöglicht, bestimmte Eigenschaften oder Ereignisse für jedes Element zu aktivieren, unabhängig davon, ob diese Eigenschaft oder dieses Ereignis in den Typdefinitionen für das Element vorhanden sind, für die sie festgelegt werden. Die Eigenschaftsversion dieser Funktion wird „angefügte Eigenschaft”, die Ereignisversion „angefügtes Ereignis” genannt. Im Prinzip können Sie sich angefügte Eigenschaften und Ereignisse als globale Mitglieder vorstellen, die für eine Instanz jedes XAML-Elements oder -Objekts festgelegt werden können. Jedoch muss dieses Element/diese Klasse oder eine größere Infrastruktur einen unterstützenden Eigenschaftenspeicher für die angefügten Werte unterstützen.

Angefügte Eigenschaften in XAML werden in der Regel über die Attributsyntax verwendet. In der Attributsyntax geben Sie eine `ownerType.propertyName`angefügte Eigenschaft im Formular an.

Oberflächlich betrachtet ähnelt dies einer Eigenschaftselementverwendung, `ownerType` aber in diesem Fall ist die von Ihnen angegebene Immer ein anderer Typ als das Objektelement, in dem die angefügte Eigenschaft festgelegt wird. `ownerType`ist der Typ, der die Accessormethoden bereitstellt, die von einem XAML-Prozessor benötigt werden, um den zugeordneten Eigenschaftswert abzusuchen oder festzulegen.

Das häufigste Szenario für angefügte Eigenschaften ist, es untergeordneten Elementen zu ermöglichen, einen Eigenschaftswert an ihr übergeordnetes Element zu melden.

Im folgenden Beispiel <xref:System.Windows.Controls.DockPanel.Dock%2A?displayProperty=nameWithType> wird die angefügte Eigenschaft veranschaulicht. Die <xref:System.Windows.Controls.DockPanel> Klasse definiert die <xref:System.Windows.Controls.DockPanel.Dock%2A?displayProperty=nameWithType> Accessoren für und besitzt daher die angefügte Eigenschaft. Die <xref:System.Windows.Controls.DockPanel> Klasse enthält auch Logik, die ihre untergeordneten Elemente iteriert, und überprüft speziell jedes Element auf einen festgelegten Wert von <xref:System.Windows.Controls.DockPanel.Dock%2A?displayProperty=nameWithType>. Wenn ein Wert gefunden wird, wird dieser Wert während des Layouts zum Positionieren der untergeordneten Elemente verwendet. Die Verwendung <xref:System.Windows.Controls.DockPanel.Dock%2A?displayProperty=nameWithType> der angefügten Eigenschaft und diese Positionierungsfunktion <xref:System.Windows.Controls.DockPanel> ist in der Tat das motivierende Szenario für die Klasse.

[!code-xaml[XAMLOvwSupport#DockAP](~/samples/snippets/csharp/VS_Snippets_Wpf/XAMLOvwSupport/CSharp/page8.xaml#dockap)]

In WPF werden die meisten oder alle angefügten Eigenschaften auch als Abhängigkeitseigenschaften implementiert. Weitere Informationen finden Sie unter [Übersicht über angefügte Eigenschaften](../../framework/wpf/advanced/attached-properties-overview.md).

Angefügte Ereignisse `ownerType.eventName` verwenden eine ähnliche Form der Attributsyntax. Wie bei nicht angefügten Ereignissen gibt der Attributwert für ein angefügtes Ereignis in XAML den Namen der Handlermethode an, die aufgerufen wird, wenn das Ereignis für das Element behandelt wird. Angefügte Ereignisse werden in WPF-XAML seltener verwendet. Weitere Informationen finden Sie unter [Übersicht über angefügte Ereignisse](../../framework/wpf/advanced/attached-events-overview.md).

## <a name="base-types-and-xaml"></a>Basistypen und XAML

Der zugrunde liegende WPF XAML und sein XAML-Namespace ist eine Auflistung von Typen, die zusätzlich zu Markupelementen für XAML CLR-Objekten entsprechen. Allerdings können nicht alle Klassen Elementen zugeordnet werden. Abstrakte Klassen, <xref:System.Windows.Controls.Primitives.ButtonBase>z. B. , und bestimmte nicht abstrakte Basisklassen werden für die Vererbung im CLR-Objektmodell verwendet. Basisklassen, einschließlich abstrakter Klassen, sind dennoch wichtig für die XAML-Entwicklung, da jedes konkrete XAML-Element Mitglieder einer Basisklasse in der eigenen Hierarchie erbt. Häufig enthalten diese Mitglieder Eigenschaften, die als Attribute für das Element festgelegt werden können, oder Ereignisse, die behandelt werden können. <xref:System.Windows.FrameworkElement>ist die konkrete Basis-UI-Klasse von WPF auf WPF-Frameworkebene. Beim Entwerfen der Benutzeroberfläche verwenden Sie verschiedene Form-, Bedienfeld-, Dekorator- oder Steuerungsklassen, die alle von <xref:System.Windows.FrameworkElement>stammen. Eine verwandte Basisklasse unterstützt dokumentorientierte Elemente, die gut für eine Flowlayoutpräsentation funktionieren, mithilfe von APIs, <xref:System.Windows.FrameworkContentElement>die die APIs in <xref:System.Windows.FrameworkElement>absichtlich spiegeln. Die Kombination von Attributen auf Elementebene und einem CLR-Objektmodell bietet Ihnen eine Reihe allgemeiner Eigenschaften, die für die meisten konkreten XAML-Elemente festgelegt sind, unabhängig vom spezifischen XAML-Element und dem zugrunde liegenden Typ.

## <a name="xaml-security"></a>XAML-Sicherheit

XAML ist eine Markupsprache, die Objektinstanziierung und -ausführung direkt darstellt. Daher verfügen in XAML erstellte Elemente über dieselbe Fähigkeit zur Interaktion mit Systemressourcen (z.B. Netzwerkzugriff, Dateisystem E/A), wie der gleichwertig generierte Code. XAML, das in eine vollständig vertrauenswürdige App geladen wird, hat denselben Zugriff auf die Systemressourcen wie die Hosting-App.

### <a name="code-access-security-cas-in-wpf"></a>Code Zugriffssicherheit (CAS) in WPF

**Dieser Abschnitt gilt nur für .NET Framework. WPF für .NET Core unterstützt CAS nicht. Weitere Informationen finden Sie unter Unterschiede zur [Codezugriffssicherheit](../migration/differences-from-net-framework.md#code-access-security).**

WPF für .NET Framework unterstützt Code Access Security (CAS). Dies bedeutet, dass WPF-Inhalte, die in der Internetzone ausgeführt werden, über eingeschränkte Ausführungsberechtigungen verfügen. "Loose XAML" (Seiten mit nicht kompiliertem XAML, die zum Zeitpunkt des Ladens von einem XAML-Viewer interpretiert werden) und XBAP werden in der Regel in dieser Internetzone ausgeführt und verwenden denselben Berechtigungssatz. Wenn XAML allerdings in eine voll vertrauenswürdige Anwendung geladen wird, hat es den gleichen Zugriff auf Systemressourcen wie die Hostanwendung. Weitere Informationen finden Sie unter [WPF-Sicherheit mit teilweiser Vertrauenswürdigkeit](../../framework/wpf/wpf-partial-trust-security.md).

## <a name="loading-xaml-from-code"></a>Laden von XAML aus Code

XAML kann zum Definieren der gesamten Benutzeroberfläche verwendet werden, aber manchmal ist es auch sinnvoll, nur einen Teil der Benutzeroberfläche in XAML zu definieren. Diese Fähigkeit könnte man für eine teilweise Anpassungsfähigkeit durch den Benutzer verwenden, lokales Speichern von Informationen, die Verwendung von XAML zur Bereitstellung eines Geschäftsobjekts oder eine Vielzahl weiterer möglicher Szenarios. Der Schlüssel zu diesen <xref:System.Windows.Markup.XamlReader> Szenarien <xref:System.Windows.Markup.XamlReader.Load%2A> ist die Klasse und ihre Methode. Als Eingabe dient eine XAML-Datei, und die Ausgabe ist ein Objekt, das die gesamte Laufzeitstruktur von Objekten darstellt, die über dieses Markup erstellt wurde. Anschließend können Sie das Objekt als Eigenschaft eines anderen Objekts einfügen, das bereits in der App vorhanden ist. Solange die Eigenschaft eine geeignete Eigenschaft im Inhaltsmodell ist, die über eventuelle Anzeigefunktionen verfügt und das Ausführungsmodul benachrichtigt, dass der App neue Inhalte hinzugefügt wurden, können Sie den Inhalt einer ausgeführten App einfach ändern, indem Sie in XAML geladen werden. Für .NET Framework ist diese Funktion in der Regel nur in Vollvertrauenswürdigen Anwendungen verfügbar, da das Laden von Dateien in Anwendungen beim Ausführen offensichtlich auf die Sicherheit zukommt.

## <a name="see-also"></a>Weitere Informationen

- [Ausführliche Erläuterung der XAML-Syntax](../../framework/wpf/advanced/xaml-syntax-in-detail.md)
- [XAML- und benutzerdefinierte Klassen für WPF](../../framework/wpf/advanced/xaml-and-custom-classes-for-wpf.md)
- [XAML-Namespace (x:) Sprachfunktionen](../xaml-services/namespace-language-features.md)
- [WPF-XAML-Erweiterungen](../../framework/wpf/advanced/wpf-xaml-extensions.md)
- [Übersicht über Basiselemente](../../framework/wpf/advanced/base-elements-overview.md)
- [Strukturen in WPF](../../framework/wpf/advanced/trees-in-wpf.md)
