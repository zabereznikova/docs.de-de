---
title: Übersicht über XAML (WPF)
ms.date: 03/30/2017
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
ms.assetid: a80db4cd-dd0f-479f-a45f-3740017c22e4
ms.openlocfilehash: 7aa695ae3402c4a834e5f83c40f341c5448ab524
ms.sourcegitcommit: 30a83efb57c468da74e9e218de26cf88d3254597
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/20/2019
ms.locfileid: "68364129"
---
# <a name="xaml-overview-wpf"></a>Übersicht über XAML (WPF)
Dieses Thema beschreibt die Funktionen der XAML-Sprache und zeigt, wie Sie XAML zum Schreiben von [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]-Anwendungen verwenden können. Dieses Thema beschreibt speziell XAML entsprechend der Implementierung durch [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]. XAML selbst geht über das in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] implementierte Sprachkonzept hinaus.  

<a name="what_is_xaml"></a>   
## <a name="what-is-xaml"></a>Was ist XAML?  
 XAML ist eine deklarative Markupsprache. Wie auf das .NET Framework Programmiermodell angewendet, vereinfacht XAML das Erstellen [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] eines für eine .NET Framework Anwendung. Sie können sichtbare Elemente der [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] im deklarativen XAML-Markup erstellen und anschließend die Definition der [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] mithilfe von CodeBehind-Dateien, die über partielle Klassendefinitionen an das Markup geknüpft sind, von der Laufzeitlogik trennen. XAML repräsentiert direkt die Instanziierung von Objekten in einem spezifischen Satz von in Assemblys definierten Unterstützungstypen dar. Dies ist ein anderer Ansatz als der anderer Markupsprachen, die üblicherweise interpretierte Sprachen sind, die keine direkte Verbindung zu einem System von Unterstützungstypen besitzen. XAML ermöglicht einen Workflow, bei dem separate Parteien auf der [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] und der Logik einer Anwendung unter der Verwendung möglicherweise unterschiedlicher Tools arbeiten können.  
  
 Bei der Darstellung als Text sind XAML-Dateien XML-Dateien, die in der Regel die `.xaml`-Erweiterung haben. Die Dateien können in jeder XML-Codierung codiert sein, üblich ist jedoch UTF-8-Codierung.  
  
 Das folgende Beispiel zeigt, wie Sie eine Schaltfläche als Teil einer [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] erstellen können. Dieses Beispiel soll Ihnen nur ein erstes Gefühl dafür geben, wie XAML allgemeine [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]-Programmiermetaphern darstellt (es handelt sich nicht um ein vollständiges Beispiel).  
  
 [!code-xaml[XAMLOvwSupport#DirtSimple](~/samples/snippets/csharp/VS_Snippets_Wpf/XAMLOvwSupport/CSharp/page2.xaml#dirtsimple)]  
  
<a name="xaml_syntax_in_brief"></a>   
## <a name="xaml-syntax-in-brief"></a>Kurzübersicht über die XAML-Syntax  
 In den folgenden Abschnitten werden die grundlegenden Formen der XAML-Syntax erläutert und ein kurzes Markupbeispiel vorgestellt. Diese Abschnitte beabsichtigen keine Wiedergabe vollständiger Informationen über jedes Syntaxformat, z.B. wie diese im Unterstützungstypsystem dargestellt werden. Weitere Informationen zu den Besonderheiten der XAML-Syntax für jede der in diesem Thema vorgestellten Syntax finden Sie unter [Ausführliche Erläuterung der XAML-Syntax](xaml-syntax-in-detail.md).  
  
 Wenn Sie bereits mit der XML-Sprache vertraut sind, wird Ihnen vieles dessen, was Sie in den folgenden Abschnitten lesen, elementar erscheinen. Dies liegt im grundlegenden Entwurfsprinzip von XAML begründet.  Die XAML-Sprache definiert eigene Konzepte, aber diese Konzepte funktionieren in der XML-Sprache und im Markup-Formular.  
  
### <a name="xaml-object-elements"></a>XAML-Objekt Elemente  
 Ein Objektelement deklariert in der Regel eine Instanz eines Typs. Dieser Typ ist in den Assemblys definiert, die die Unterstützungstypen für eine Technologie bereitstellen, die XAML als Sprache verwendet.  
  
 Objektelementsyntax beginnt immer mit einer öffnenden spitzen Klammer (\<). Dies wird gefolgt vom Namen des Typs, in dem Sie eine Instanz erstellen möchten. (Dieser Name kann auch ein Präfix enthalten. Dieses Konzept wird später erläutert.) Danach können Sie optional Attribute für das Objektelement deklarieren. Um das Objektelement-Tag abzuschließen, beenden Sie es mit einer schließenden spitzen Klammer (>). Sie können stattdessen auch eine selbstschließende Form verwenden, die keinen Inhalte besitzt, indem Sie das Tag mit einem Schrägstrich gefolgt von einer schließenden spitzen Klammer beenden (/>). Sehen Sie sich z.B. den oben gezeigten Markupausschnitt erneut an:  
  
 [!code-xaml[XAMLOvwSupport#DirtSimple](~/samples/snippets/csharp/VS_Snippets_Wpf/XAMLOvwSupport/CSharp/page2.xaml#dirtsimple)]  
  
 Hier werden zwei Objektelemente angegeben: `<StackPanel>` (mit Inhalt und einem später folgenden schließenden Tag) und `<Button .../>` (in selbstschließender Form, mit mehreren Attributen). Die Objektelemente `StackPanel` und `Button` sind jeweils dem Namen einer Klasse zugeordnet, die durch [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] definiert und Teil der [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Assemblys ist. Wenn Sie ein Objektelement-Tag angeben, erstellen Sie eine Anweisung für den XAML-Prozessor, eine neue Instanz zu erstellen. Jede Instanz wird erstellt, indem beim Auswerten und Laden von XAML der Parameter lose Konstruktor des zugrunde liegenden Typs aufgerufen wird.  
  
### <a name="attribute-syntax-properties"></a>Attribut Syntax (Eigenschaften)  
 Eigenschaften eines Objekts können oft als Attribute des Objektelements ausgedrückt werden. Eine Attributsyntax benennt die Eigenschaft, die in der Attributsyntax festgelegt wird, gefolgt vom Zuweisungsoperator (=). Der Wert eines Attributs wird immer als Zeichenfolge angegeben, die in Anführungszeichen eingeschlossen ist.  
  
 Die Attributsyntax ist die geradlinigste Syntax zur Festlegung von Eigenschaften und die intuitivste Syntax für Entwickler, die bereits in der Vergangenheit Markupsprachen verwendet haben. Das folgende Markup erstellt z.B. eine Schaltfläche mit rotem Text und einem blauen Hintergrund, wobei der anzuzeigende Textinhalt als `Content` angegeben ist.  
  
 [!code-xaml[XAMLOvwSupport#BlueRedButton](~/samples/snippets/csharp/VS_Snippets_Wpf/XAMLOvwSupport/CSharp/Page1.xaml#blueredbutton)]  
  
### <a name="property-element-syntax"></a>Eigenschafts Element Syntax  
 Einige Eigenschaften eines Objektelements können nicht in Attributsyntax angegeben werden, da die Objekte oder Informationen, die für den Eigenschaftswert benötigt werden, nicht hinreichend innerhalb der durch Anführungszeichen und Zeichenfolgen beschränkten Attributsyntax ausgedrückt werden können. Für solche Fälle kann eine andere Syntax, die Eigenschaftenelement-Syntax genannt wird, verwendet werden.  
  
 Die Syntax für das Starttag des Eigenschaftenelements lautet `<`*Typname*`.`*Eigenschaftenname*`>`. Im Allgemeinen ist der Inhalt dieses Tags ein Objekt Element des Typs, den die Eigenschaft als Wert annimmt. Nachdem Sie den Inhalt angegeben haben, müssen Sie das Property-Element mit einem Endtag schließen. Die Syntax für das Endtag lautet `</`*Typname*`.`*Eigenschaftenname*`>`.  
  
 Wenn Attributsyntax möglich ist, ist deren Verwendung in der Regel bequemer und ermöglicht ein kompakteres Markup, aber das ist oft nur eine Frage des Stils, keine technische Einschränkung. Das folgende Beispiel zeigt die Festlegung derselben Eigenschaften wie im vorherigen Attributsyntax-Beispiel, aber dieses Mal unter Verwendung von Eigenschaftenelement-Syntax für alle Eigenschaften des `Button`-Elements.  
  
 [!code-xaml[XAMLOvwSupport#BlueRedButtonPE](~/samples/snippets/csharp/VS_Snippets_Wpf/XAMLOvwSupport/CSharp/Page1.xaml#blueredbuttonpe)]  
  
### <a name="collection-syntax"></a>Sammlungs Syntax  
 Die XAML-Sprache enthält einige Optimierungen, die besser lesbares Markup erstellen. Eine dieser Optimierungen bewirkt, dass bei Eigenschaften, die vom Typ Auflistung sind, Elemente, die Sie in Markup als untergeordnete Elemente dieses Eigenschaftswerts anlegen, automatisch Teil der Auflistung werden. In diesem Fall ist der Wert, welcher der Auflistungseigenschaft zugewiesen wird, eine Auflistung von untergeordneten Objektelementen.  
  
 Das folgende Beispiel zeigt die Auflistungs Syntax zum Festlegen <xref:System.Windows.Media.GradientBrush.GradientStops%2A> von Werten der-Eigenschaft:  
  
```xaml  
<LinearGradientBrush>  
  <LinearGradientBrush.GradientStops>  
    <!-- no explicit new GradientStopCollection, parser knows how to find or create -->  
    <GradientStop Offset="0.0" Color="Red" />  
    <GradientStop Offset="1.0" Color="Blue" />  
  </LinearGradientBrush.GradientStops>  
</LinearGradientBrush>  
```  
  
### <a name="xaml-content-properties"></a>XAML-Inhalts Eigenschaften  
 Ein Feature der XAML-Sprache ist, dass eine Klasse genau eine ihrer Eigenschaften als XAML-Inhaltseigenschaft auszeichnen kann. Untergeordnete Elemente dieses Objektelements werden verwendet, um den Wert dieser Inhaltseigenschaft festzulegen. Anders gesagt: nur für die Inhaltseigenschaft dürfen Sie ein Eigenschaftenelement beim Festlegen dieser Eigenschaft in XAML-Markup auslassen und so eine besser sichtbare übergeordnet/untergeordnet-Metapher im Markup erzeugen.  
  
 <xref:System.Windows.Controls.Border> Gibt z. b. eine Inhalts Eigenschaft <xref:System.Windows.Controls.Decorator.Child%2A>von an. Die folgenden beiden <xref:System.Windows.Controls.Border> Elemente werden identisch behandelt. Der erste nutzt den Vorteil der Inhaltseigenschaften-Syntax und lässt das `Border.Child`-Eigenschaftenelement aus. Das zweite Beispiel zeigt `Border.Child` explizit.  
  
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
  
 In der XAML-Sprache gilt die Regel, dass der Wert einer XAML-Inhaltseigenschaft nur vor oder nach allen anderen Eigenschaftenelemente für dieses Objektelement festgelegt werden darf. Daher wird das folgende Markup beispielsweise nicht kompilieren:  
  
```  
<Button>I am a   
  <Button.Background>Blue</Button.Background>  
  blue button</Button>  
```  
  
 Weitere Informationen zu dieser Einschränkung bei XAML-Inhaltseigenschaften finden Sie im Abschnitt "XAML-Inhaltseigenschaften" von [Ausführliche Erläuterung der XAML-Syntax](xaml-syntax-in-detail.md).  
  
### <a name="text-content"></a>Text Inhalt  
 Eine kleine Anzahl von XAML-Elementen kann Text direkt als Inhalt verarbeiten. Um dies zu ermöglichen, muss einer der folgenden Fälle zutreffen:  
  
- Die Klasse muss eine Content-Eigenschaft deklarieren, und diese Inhalts Eigenschaft muss von einem Typ sein, der einer Zeichenfolge zugewiesen werden kann <xref:System.Object>(der Typ könnte sein). Beispielsweise verwendet <xref:System.Windows.Controls.ContentControl.Content%2A> jeder <xref:System.Windows.Controls.ContentControl> als Inhalts Eigenschaft, und er ist vom Typ <xref:System.Object>und unterstützt die <xref:System.Windows.Controls.Button>folgende Verwendung für eine praktische <xref:System.Windows.Controls.ContentControl> , z. b. `<Button>Hello</Button>`:.  
  
- Der Typ muss einen Typkonverter deklarieren, für den in diesem Fall der Textinhalt als Initialisierungstext verwendet wird. Beispielsweise `<Brush>Blue</Brush>`. Dieser Fall ist in der Praxis weniger häufig.  
  
- Der Typ muss eine bekanntes XAML-Sprachprimitiv sein.  
  
### <a name="content-properties-and-collection-syntax-combined"></a>Kombination aus Inhalts Eigenschaften und Sammlungs Syntax  
 Betrachten Sie das folgende Beispiel:  
  
```xaml  
<StackPanel>  
  <Button>First Button</Button>  
  <Button>Second Button</Button>  
</StackPanel>  
```  
  
 Hier handelt es sich um ein untergeordnetes <xref:System.Windows.Controls.StackPanel>Element von. <xref:System.Windows.Controls.Button> Dies ist ein optimiertes und intuitives Markup, bei dem zwei Tags aus zwei verschiedenen Gründen weggelassen wurden.  
  
- **Ausgelassenes StackPanel. Children-Eigenschaften Element:** <xref:System.Windows.Controls.StackPanel> wird von<xref:System.Windows.Controls.Panel>abgeleitet. <xref:System.Windows.Controls.Panel>definiert <xref:System.Windows.Controls.Panel.Children%2A?displayProperty=nameWithType> als XAML-Inhalts Eigenschaft.  
  
- **Ausgelassenes UIElementCollection-Objekt Element:** Die <xref:System.Windows.Controls.Panel.Children%2A?displayProperty=nameWithType> -Eigenschaft übernimmt den <xref:System.Windows.Controls.UIElementCollection>-Typ, <xref:System.Collections.IList>der implementiert. Das Elementtag der Auflistung kann basierend auf den XAML-Regeln zum Verarbeiten von Auflistungen wie <xref:System.Collections.IList>ausgelassen werden. (In diesem Fall <xref:System.Windows.Controls.UIElementCollection> kann nicht instanziiert werden, da kein Parameter loser Konstruktor verfügbar gemacht wird, und aus diesem Grund wird das <xref:System.Windows.Controls.UIElementCollection> Objekt Element auskommentiert).  
  
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
  
### <a name="attribute-syntax-events"></a>Attribut Syntax (Ereignisse)  
 Attributsyntax kann auch für Mitglieder verwendet werden, die Ereignisse und keine Eigenschaften sind. In diesem Fall ist der Name des Attributs der Name des Ereignisses. In der WPF-Implementierung von Ereignissen für XAML ist der Wert des Attributs der Name eines Ereignishandlers, der den Ereignisdelegaten implementiert. Das folgende Markup weist z. b. einen Handler für <xref:System.Windows.Controls.Primitives.ButtonBase.Click> das-Ereignis <xref:System.Windows.Controls.Button> einem im Markup erstellten zu:  
  
 [!code-xaml[XAMLOvwSupport#ButtonWithCodeBehind](~/samples/snippets/csharp/VS_Snippets_Wpf/XAMLOvwSupport/CSharp/page3.xaml#buttonwithcodebehind)]  
  
 Es steckt noch mehr hinter Ereignissen und XAML in WPF, als dieses Beispiel für die Attributsyntax zeigt. So fragen Sie sich vielleicht, was der hier referenzierte `ClickHandler` darstellt und wie er definiert wird. Dies wird im kommenden Abschnitt [Ereignisse und XAML-Code-Behind](xaml-overview-wpf.md#events_and_xaml_codebehind) dieses Themas erläutert.  
  
<a name="case_and_white space_in_xaml"></a>   
## <a name="case-and-white-space-in-xaml"></a>Groß-/Kleinschreibung und Leerzeichen in XAML  
 In XAML wird im Allgemeinen Groß-/Kleinschreibung beachtet. Zum Auflösen von Unterstützungstypen wird in WPF-XAML die Groß-/Kleinschreibung nach den gleichen Regeln wie in CLR beachtet. Bei Objektelementen, Eigenschaftenelementen und Attributnamen muss beim Vergleich anhand des Namens des zugrunde liegenden Typs in der Assembly oder eines Typmitglieds immer die Groß-/Kleinschreibung beachtet werden. Auch XAML-Schlüsselwörter und Primitive beachten die Groß-/Kleinschreibung. Bei Werte wird nicht immer Groß-/Kleinschreibung beachtet. Ob bei Werten Groß-/Kleinschreibung beachtet wird, hängt vom Verhalten ab, das dem Typkonverter für die den Wert annehmende Eigenschaft zugeordnet ist, oder vom Typ des Eigenschaftswerts. Eigenschaften, die <xref:System.Boolean> den-Typ verwenden, können z. b. entweder `true` oder als äquivalente Werte annehmen, dies ist jedoch nur möglich, da die Typkonvertierung durch <xref:System.Boolean> den systemeigenen `True` WPF-XAML-Parser für eine Zeichenfolge in bereits als  
  
 WPF-XAML-Prozessoren und serialisierungsinitialisierer ignorieren oder löschen alle nicht signifikanten Leerräume, und normalisiert alle wichtigen Leerzeichen. Dies entspricht den Standard Empfehlungen für das leer Raum Verhalten der XAML-Spezifikation. Dieses Verhalten hat im Allgemeinen nur dann Auswirkungen, wenn Sie Zeichenfolgen innerhalb von XAML-Inhaltseigenschaften angeben. Vereinfacht ausgedrückt: XAML konvertiert Leerzeichen, Zeilenvorschub und Tabulatorzeichen in Leerzeichen und behält anschließend ein Leerzeichen bei, wenn sich dieses an einem Ende einer zusammenhängenden Zeichenfolge befindet. Die vollständige Erläuterung der XAML-Leerraum Behandlung wird in diesem Thema nicht behandelt. Weitere Informationen finden Sie unter [Leerraum Verarbeitung in XAML](../../xaml-services/whitespace-processing-in-xaml.md).  
  
<a name="markup_extensions"></a>   
## <a name="markup-extensions"></a>Markuperweiterungen  
 Markuperweiterungen sind ein XAML-Sprachkonzept. Wenn geschweifte Klammern zum Bereitstellen des Werts einer Attributsyntax verwendet werden (`{` und `}`), handelt es sich dabei um die Verwendung einer Markuperweiterung. Diese Verwendung weist den XAML-Prozessor an, von der allgemeinen Behandlung von Attributwerten als Zeichenfolgenliteral oder zu einer Zeichenfolge konvertierbarem Wert abzuweichen.  
  
 Die in der [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-Anwendungsprogrammierung am häufigsten verwendeten Markuperweiterungen sind [Binding](binding-markup-extension.md) für Datenbindungsausdrücke und die Ressourcenverweise [StaticResource](staticresource-markup-extension.md) und [DynamicResource](dynamicresource-markup-extension.md). Durch die Verwendung von Markuperweiterungen können Sie mit Attributsyntax auch dann Werte für Eigenschaften bereitstellen, wenn diese Eigenschaft im Allgemeinen keine Attributsyntax unterstützt. Markuperweiterungen verwenden oft intermediäre Ausdruckstypen, um Features wie z.B. das Zurückstellen von Werten oder das Verweisen auf andere Objekte, die nur zur Laufzeit vorhanden sind, zu aktivieren.  
  
 Das folgende Markup legt z. b. den Wert <xref:System.Windows.FrameworkElement.Style%2A> der-Eigenschaft mithilfe der Attribut Syntax fest. Die <xref:System.Windows.FrameworkElement.Style%2A> -Eigenschaft nimmt eine Instanz <xref:System.Windows.Style> der-Klasse an, die standardmäßig nicht von einer Attribut Syntax Zeichenfolge instanziiert werden konnte. In diesem Fall verweist das Attribut jedoch auf eine bestimmte Markuperweiterung, [StaticResource](staticresource-markup-extension.md). Wenn diese Markuperweiterung verarbeitet wird, wird ein Verweis auf einen Stil zurückgegeben, der bereits zuvor als mit einem Schlüssel versehene Ressource in einem Ressourcenverzeichnis instanziiert wurde.  
  
 [!code-xaml[FEResourceSH_snip#XAMLOvwShortResources](~/samples/snippets/csharp/VS_Snippets_Wpf/FEResourceSH_snip/CS/page1.xaml#xamlovwshortresources)]  
[!code-xaml[FEResourceSH_snip#XAMLOvwShortResources2](~/samples/snippets/csharp/VS_Snippets_Wpf/FEResourceSH_snip/CS/page1.xaml#xamlovwshortresources2)]  
[!code-xaml[FEResourceSH_snip#XAMLOvwShortResources3](~/samples/snippets/csharp/VS_Snippets_Wpf/FEResourceSH_snip/CS/page1.xaml#xamlovwshortresources3)]  
  
 Eine Verweisliste mit Markuperweiterungen für XAML, die spezifisch in WPF implementiert sind, finden Sie unter [WPF-XAML-Erweiterungen](wpf-xaml-extensions.md). Eine Referenz Auflistung der Markup Erweiterungen, die von System. XAML definiert werden und für .NET Framework XAML-Implementierungen breiter verfügbar sind, finden [Sie unter XAML-Namespace (x:) Sprach Features](../../xaml-services/xaml-namespace-x-language-features.md). Weitere Informationen über die Konzepte der Markuperweiterungen finden Sie unter [Markuperweiterungen und WPF XAML](markup-extensions-and-wpf-xaml.md).  
  
<a name="type_converters"></a>   
## <a name="type-converters"></a>Typkonverter  
 Im Abschnitt [XAML-Syntax in Kürze](xaml-overview-wpf.md#xaml_syntax_in_brief) wurde behauptet, dass man den Attributwert durch eine Zeichenfolge festlegen können muss. Die grundlegende, systemeigene Verarbeitung der Art und Weise, wie Zeichen folgen in andere Objekttypen oder primitive <xref:System.String> Werte konvertiert werden, basiert auf dem Typ selbst, zusätzlich zur nativen <xref:System.Uri>Verarbeitung für bestimmte Typen, <xref:System.DateTime> z. b. oder. Viele [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-Typen oder deren Mitglieder erweitern das grundlegende Verhalten der Zeichenfolgenverarbeitung so, dass Instanzen komplexerer Objekttypen als Zeichenfolgen und Attribute angegeben werden können.  
  
 Die <xref:System.Windows.Thickness> -Struktur ist ein Beispiel für einen Typ, für den eine Typkonvertierung für XAML-Verwendungen aktiviert ist. <xref:System.Windows.Thickness>gibt Messungen innerhalb eines geschachtelten Rechtecks an und wird als Wert für Eigenschaften <xref:System.Windows.FrameworkElement.Margin%2A>wie z. b. verwendet. Wenn Sie einen Typkonverter in <xref:System.Windows.Thickness>platzieren, können alle Eigenschaften, <xref:System.Windows.Thickness> die eine verwenden, einfacher in XAML angegeben werden, da Sie als Attribute angegeben werden können. Im folgenden Beispiel wird eine Typkonvertierung und Attribut Syntax verwendet, um einen Wert für <xref:System.Windows.FrameworkElement.Margin%2A>einen bereitzustellen:  
  
 [!code-xaml[XAMLOvwSupport#MarginTCE](~/samples/snippets/csharp/VS_Snippets_Wpf/XAMLOvwSupport/CSharp/page7.xaml#margintce)]  
  
 Das vorherige Attribut Syntax Beispiel entspricht dem folgenden ausführlicheren Syntax Beispiel, bei dem stattdessen durch die <xref:System.Windows.FrameworkElement.Margin%2A> Eigenschaften Element Syntax festgelegt wird, die ein <xref:System.Windows.Thickness> -Objekt Element enthält. Die vier Schlüsseleigenschaften von <xref:System.Windows.Thickness> werden auf der neuen-Instanz als Attribute festgelegt:  
  
 [!code-xaml[XAMLOvwSupport#MarginVerbose](~/samples/snippets/csharp/VS_Snippets_Wpf/XAMLOvwSupport/CSharp/page7.xaml#marginverbose)]  
  
> [!NOTE]
>  Es gibt auch eine begrenzte Anzahl von Objekten, bei denen die Typkonvertierung die einzige öffentliche Methode zum Festlegen einer Eigenschaft auf diesen Typ ist, ohne eine Unterklasse einzubeziehen, da der Typ selbst keinen Parameter losen Konstruktor hat. Ein Beispiel hierfür <xref:System.Windows.Input.Cursor>ist.  
  
 Weitere Informationen zu Typkonvertierung und wie deren Verwendung in Attributsyntax unterstützt wird, finden Sie unter [TypeConverter und XAML](typeconverters-and-xaml.md).  
  
<a name="xaml_root_elements_and_xaml_namespaces"></a>   
## <a name="xaml-root-elements-and-xaml-namespaces"></a>XAML-Stamm Elemente und XAML-Namespaces  
 Eine XAML-Datei darf nur ein Stammelement haben, um sowohl wohlgeformtes [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] als auch eine gültige XAML-Datei zu sein. Bei typischen WPF-Szenarien verwenden Sie ein root-Element, das eine deutliche Bedeutung im WPF-Anwendungsmodell aufweist (z <xref:System.Windows.Window> . <xref:System.Windows.Controls.Page> b. oder für <xref:System.Windows.ResourceDictionary> eine Seite, für ein externes <xref:System.Windows.Application> Wörterbuch oder für die Anwendungs Definition). Das folgende Beispiel zeigt das Stamm Element einer typischen XAML-Datei für eine [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Seite mit dem Stamm Element von. <xref:System.Windows.Controls.Page>  
  
 [!code-xaml[XAMLOvwSupport#RootOnly](~/samples/snippets/csharp/VS_Snippets_Wpf/XAMLOvwSupport/CSharp/page2.xaml#rootonly)]  
[!code-xaml[XAMLOvwSupport#RootOnly2](~/samples/snippets/csharp/VS_Snippets_Wpf/XAMLOvwSupport/CSharp/page2.xaml#rootonly2)]  
  
 Das Stammelement enthält auch die Attribute `xmlns` und `xmlns:x`. Diese Attribute geben einem XAML-Prozessor an, welche XAML-Namespaces die Typdefinitionen für Unterstützungstypen enthalten, auf die das Markup als Elemente verweist. Das `xmlns`-Attribut gibt ausdrücklich den XAML-Standardnamespace an. Innerhalb des XAML-Standardnamespaces können Objektelemente im Markup ohne Präfix angegeben werden. Für die meisten [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-Anwendungsszenarios und für fast alle der in den [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-Abschnitten des [!INCLUDE[TLA2#tla_sdk](../../../../includes/tla2sharptla-sdk-md.md)] gegebenen Beispiele, ist der XAML-Standardnamespace dem [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-Namespace [!INCLUDE[TLA#tla_wpfxmlnsv1](../../../../includes/tlasharptla-wpfxmlnsv1-md.md)] zugeordnet. Das `xmlns:x`-Attribut gibt einen zusätzlichen XAML-Namespace an, der dem XAML-Sprachnamespace [!INCLUDE[TLA#tla_xamlxmlnsv1](../../../../includes/tlasharptla-xamlxmlnsv1-md.md)] zugeordnet ist.  
  
 Diese Verwendung von `xmlns` zum Definieren eines Geltungsbereich für die Verwendung und Zuordnung eines Namescopes ist mit der XML 1.0-Spezifikation verträglich. XAML-Namescopes unterscheiden sich von XML-Namescopes nur darin, dass ein XAML-Namescope auch darüber etwas impliziert, wie Elemente durch Typen unterstützt werden, wenn es zur Typauflösung und Analyse des XAML-Codes kommt.  
  
 Beachten Sie, dass die `xmlns`-Attribute nur für das Stammelement jeder XAML-Datei unbedingt erforderlich sind. `xmlns`-Definitionen gelten für alle Nachfolgerelemente des Stammelements (dieses Verhalten entspricht wieder der XML 1.0-Spezifikation für `xmlns`.) `xmlns`-Attribute sind auch bei anderen Elementen unterhalb des Stamms zulässig und gelten für alle Nachfolgerelemente des definierenden Elements. Allerdings kann häufiges Definieren oder Neudefinieren von XAML-Namespaces zu einem nur schwer lesbaren XAML-Markup-Stil führen.  
  
 Die [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-Implementierung des XAML-Prozessors schließt eine Infrastruktur ein, der die WPF-Kernassemblys bekannt sind. Ihr ist bekannt, dass die [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-Kernassemblys die Typen enthalten, welche die [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-Zuordnungen zum XAML-Standardnamespace unterstützen. Dies wird durch eine Konfiguration ermöglicht, die Teil Ihrer Projekt-Builddatei und des WPF-Builds und -Projektsystems ist. Daher ist die Deklaration des XAML-Namespaces als Standard-`xmlns` das Einzige, was benötigt wird, um auf XAML-Elemente zu verweisen, die aus [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-Assemblys stammen.  
  
### <a name="the-x-prefix"></a>Das x:-Präfix  
 Im vorherigen Beispiel zum Stammelement wurde das Präfix `x:` verwendet, um den XAML-Namespaces [!INCLUDE[TLA#tla_xamlxmlnsv1](../../../../includes/tlasharptla-xamlxmlnsv1-md.md)] zuzuordnen, also der dedizierte XAML-Namespace, der XAML-Sprachkonstrukte unterstützt. Dieses `x:`-Präfix wird für die Zuordnung des XAML-Namespaces in den Vorlagen für Projekte, in Beispielen und in der Dokumentation im gesamten [!INCLUDE[TLA2#tla_sdk](../../../../includes/tla2sharptla-sdk-md.md)] verwendet. Der XAML-Namespace für die XAML-Sprache enthält mehrere Programmierkonstrukte, die Sie sehr häufig in XAML verwenden werden. Im folgenden finden Sie eine Liste der häufigsten `x:`-Präfix-Programmierkonstrukte, die Sie verwenden werden:  
  
- [x:Key](../../xaml-services/x-key-directive.md): Legt einen eindeutigen Schlüssel für jede Ressource in einem <xref:System.Windows.ResourceDictionary> (oder ähnlichen Wörterbuch Konzepten in anderen Frameworks) fest. `x:Key` wird wahrscheinlich für 90 % der Verwendungen von `x:` im Markup einer normalen WPF-Anwendung verantwortlich zeigen.  
  
- [x:Class](../../xaml-services/x-class-directive.md): Gibt den [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)] Namespace und den Klassennamen für die Klasse an, die Code Behind für eine XAML-Seite bereitstellt. Das WPF-Programmiermodell schreibt eine solche Klasse für CodeBehind-Unterstützung vor, weshalb Sie fast immer eine Zuordnung von `x:` sehen werden, selbst wenn keine Ressourcen vorhanden sind.  
  
- [x:Name](../../xaml-services/x-name-directive.md): Gibt einen Laufzeitobjekt Namen für die Instanz an, die im Lauf Zeit Code vorhanden ist, nachdem ein Objekt Element verarbeitet wurde. Im Allgemeinen werden Sie häufig eine entsprechende WPF-definierte Eigenschaft für [x:Name](../../xaml-services/x-name-directive.md) verwenden. Solche Eigenschaften werden spezifisch einer CLR-Unterstützungseigenschaft zugeordnet und erleichtern daher die Anwendungsprogrammierung, bei der Sie häufig Laufzeitcode verwenden, um die benannten Elemente aus initialisiertem XAML zu finden. Die häufigste solche Eigenschaft ist <xref:System.Windows.FrameworkElement.Name%2A?displayProperty=nameWithType>. Sie können weiterhin [x:Name](../../xaml-services/x-name-directive.md) verwenden, wenn die entsprechende WPF-Frameworkebene <xref:System.Windows.FrameworkElement.Name%2A> -Eigenschaft in einem bestimmten Typ nicht unterstützt wird. Dies ist bei einigen Animations-Szenarios der Fall.  
  
- [x:Static](../../xaml-services/x-static-markup-extension.md): Aktiviert einen Verweis, der einen statischen Wert zurückgibt, der nicht anderweitig eine XAML-kompatible Eigenschaft ist.  
  
- [x:Type](../../xaml-services/x-type-markup-extension.md): Erstellt einen <xref:System.Type> Verweis auf Grundlage eines Typnamens. Dies wird zum Angeben von Attributen verwendet, <xref:System.Type>die verwenden, <xref:System.Windows.Style.TargetType%2A?displayProperty=nameWithType>wie z. b., obwohl die-Eigenschaft häufig<xref:System.Type> über eine systemeigene Konvertierung von Zeichen folgen in eine Weise verfügt, dass die Verwendung der [x:Type](../../xaml-services/x-type-markup-extension.md) -Markup Erweiterung optional ist.  
  
 Es gibt weitere Programmierkonstrukte im `x:`-Präfix/XAML-Namespace, die nicht so häufig verwendet werden. Weitere Informationen finden [Sie unter XAML-Namespace (x:). Sprach Features](../../xaml-services/xaml-namespace-x-language-features.md).  
  
<a name="custom_prefixes_and_custom_types_in_xaml"></a>   
## <a name="custom-prefixes-and-custom-types-in-xaml"></a>Benutzerdefinierte Präfixe und benutzerdefinierte Typen in XAML  
 Für eigene benutzerdefinierte Assemblys oder Assemblys außerhalb des WPF-Kerns aus PresentationCore, PresentationFramework und WindowsBase können Sie die Assembly als Teil einer benutzerdefinierten `xmlns`-Zuordnung angeben. Sie können dann auf Typen aus dieser Assembly in Ihrem XAML verweisen, sofern dieser Typ korrekt implementiert wird, um die von Ihnen beabsichtigten XAML-Verwendungen zu unterstützen.  
  
 Im Folgenden sehen Sie ein einfaches Beispiel dafür, wie benutzerdefinierte Präfixe in XAML-Markup funktionieren. Das Präfix `custom` ist im Stammelement definiert und einer bestimmten Assembly zugeordnet, die mit der Anwendung verpackt wird und verfügbar ist. Diese Assembly enthält einen Typ `NumericUpDown`, der für die Unterstützung allgemeiner XAML-Verwendung implementiert ist und eine Klassenvererbung verwendet, die ihre Einfügung an diesem bestimmten Punkt im WPF-XAML-Inhaltsmodell zulässt. Eine Instanz dieses `NumericUpDown`-Steuerelements wird mithilfe des Präfix als Objektelement deklariert, damit der XAML-Parser weiß, welcher XAML-Namespace den Typ enthält und damit auch, wo sich die Unterstützungsassembly befindet, die die Typdefinition enthält.  
  
```  
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
  
 Weitere Informationen zu benutzerdefinierten Typen in XAML finden Sie unter [XAML- und benutzerdefinierte Klassen für WPF](xaml-and-custom-classes-for-wpf.md).  
  
 Weitere Informationen zur Beziehung zwischen XML-Namespaces und den Namespaces des unterstützenden Codes in Assemblys finden Sie unter [XAML-Namespaces und Namespace-Zuordnung für WPF-XAML](xaml-namespaces-and-namespace-mapping-for-wpf-xaml.md).  
  
<a name="events_and_xaml_codebehind"></a>   
## <a name="events-and-xaml-code-behind"></a>Ereignisse und XAML-Code Behind  
 Die meisten [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-Anwendungen bestehen aus XAML-Markup und CodeBehind. Innerhalb eines Projekts wird der XAML-Code als `.xaml` Datei und eine [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)] Sprache wie Microsoft Visual Basic geschrieben oder C# zum Schreiben einer Code Behind-Datei verwendet. Wenn das Markup einer XAML-Datei als Teil der WPF-Programmierungs- und -Anwendungsmodelle kompiliert wird, wird der Speicherort der XAML-CodeBehind-Datei für eine XAML-Datei durch Angeben eines Namespaces und einer Klasse als `x:Class`-Attribut des Stammelements des XAML identifiziert.  
  
 In den bisherigen Beispielen haben Sie verschiedene Schaltflächen gesehen, aber noch war keiner dieser Schaltflächen ein logisches Verhalten zugeordnet. Der primäre Mechanismus auf Anwendungsebene zum Hinzufügen eines Verhaltens für ein Objektelement ist, ein vorhandenes Ereignis der Elementklasse zu verwenden und einen bestimmten Handler für dieses Ereignis zu schreiben, der aufgerufen wird, wenn das Ereignis zur Laufzeit ausgelöst wird. Der Name des Ereignisses und der Name der zu verwendenden Handler werden im Markup angegeben, während der Code, der den Handler implementiert, im CodeBehind definiert ist.  
  
 [!code-xaml[XAMLOvwSupport#ButtonWithCodeBehind](~/samples/snippets/csharp/VS_Snippets_Wpf/XAMLOvwSupport/CSharp/page3.xaml#buttonwithcodebehind)]  
  
 [!code-csharp[XAMLOvwSupport#ButtonWithCodeBehindHandler](~/samples/snippets/csharp/VS_Snippets_Wpf/XAMLOvwSupport/CSharp/page3.xaml.cs#buttonwithcodebehindhandler)]
 [!code-vb[XAMLOvwSupport#ButtonWithCodeBehindHandler](~/samples/snippets/visualbasic/VS_Snippets_Wpf/XAMLOvwSupport/VisualBasic/Page1.xaml.vb#buttonwithcodebehindhandler)]  
  
 Beachten Sie, dass die CodeBehind-Datei den CLR-Namespace `ExampleNamespace` verwendet und `ExamplePage` als partielle Klasse in diesem Namespace deklariert. Dies entspricht dem `x:Class`-Attributwert von `ExampleNamespace`.`ExamplePage`, der im Stammelement des Markups bereitgestellt wurde. Der WPF-Markupcompiler erstellt für jede kompilierte XAML-Datei eine partielle Klasse durch Ableiten einer Klasse des Typs des Stammelements. Wenn Sie CodeBehind bereitstellen, in dem die gleiche partielle Klasse definiert ist, wird der resultierende Code innerhalb der gleichen Namespace- und Klassennamen der kompilierten Anwendung kombiniert.  
  
 Weitere Informationen zu den Anforderungen für die CodeBehind-Programmierung in WPF finden Sie im Abschnitt "Code-Behind-Ereignishandler und Anforderungen der partiellen Klasse" von [Code-Behind und XAML in WPF](code-behind-and-xaml-in-wpf.md).  
  
 Wenn Sie keine separate CodeBehind-Datei erstellen möchten, können Sie Ihren den Code auch inline in eine XAML-Datei schreiben. Inline-Code ist jedoch eine weniger vielseitige Technik, die erhebliche Einschränkungen hat. Weitere Informationen finden Sie unter [CodeBehind und XAML in WPF](code-behind-and-xaml-in-wpf.md).  
  
### <a name="routed-events"></a>Routing Ereignisse  
 Ein bestimmtes, in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] grundlegendes Ereignis-Feature ist das Routingereignis. Routingereignisse ermöglichen es einem Element, ein Ereignis zu behandeln, das durch ein anderes Element ausgelöst wurde, solange diese Elemente über eine strukturelle Beziehung verbunden sind. Gibt man eine Ereignisbehandlung über ein XAML-Attribut an, kann jedes beliebige Element nach diesem Routingereignis lauschen und es behandeln, einschließlich der Elemente, für die dieses bestimmte Element nicht in der Mitgliedstabelle der Klasse aufgeführt ist. Dies wird durch Qualifizierung des Ereignisnamen-Attributs mit dem besitzenden Klassennamen erreicht. Beispielsweise könnte das über `StackPanel` geordnete Element im `StackPanel` laufenden `Button.Click` <xref:System.Windows.Controls.Primitives.ButtonBase.Click>  /  `Button` Beispiel einen Handler für das-Ereignis der untergeordneten Element-Schaltfläche registrieren, indem `StackPanel` das-Attribut im Object-Element mit Ihrem Handlernamen als Attribut Wert. Weitere Informationen zu Routingereignissen finden Sie unter [Übersicht über Routingereignisse](routed-events-overview.md).  
  
<a name="x_name_and_xaml_named_elements"></a>   
## <a name="xaml-named-elements"></a>Benannte XAML-Elemente  
 Die Objektinstanz, die in einem Objektdiagramm durch Verarbeitung eines XAML-Objektelements erstellt wird, hat standardmäßig keinen eindeutigen Bezeichner oder Objektverweis. Wenn Sie allerdings einen Konstruktor im Code aufrufen, verwenden Sie fast immer das Konstruktorergebnis zum Festlegen einer Variablen auf die erstellte Instanz, damit Sie später im Code auf die Instanz verweisen können. Um standardisierten Zugriff auf Objekte bereitzustellen, die durch eine Markupdefinition erstellt wurden, definiert XAML-Code das [x:Name-Attribut](../../xaml-services/x-name-directive.md). Sie können den Wert des `x:Name`-Attributs auf jedes beliebiges Objektelement festlegen. Im CodeBehind entspricht der von Ihnen gewählte Bezeichner einer Instanzvariablen, die auf die erstellte Instanz verweist. Benannte Elemente funktionieren in jeder Hinsicht wie Objektinstanzen (der Name verweist auf diese Instanz), und das CodeBehind kann auf die benannten Elemente verweisen, um anwendungsinterne Interaktionen zur Laufzeit zu behandeln. Diese Verbindung zwischen Instanzen und Variablen wird durch den WPF-XAML-Markup Compiler hergestellt, und es werden insbesondere Features und Muster <xref:System.Windows.Markup.IComponentConnector.InitializeComponent%2A> , wie z. b., in diesem Thema nicht ausführlich erläutert.  
  
 XAML-Elemente auf WPF-Frameworkebene erben eine <xref:System.Windows.FrameworkElement.Name%2A> Eigenschaft, die dem XAML-definierten `x:Name` Attribut entspricht. Bestimmte andere Klassen bieten ebenfalls Entsprechungen für `x:Name` auf Eigenschaftenebene, was in der Regel ebenfalls als `Name`-Eigenschaft definiert ist. Allgemein gilt, dass Sie ersatzweise `x:Name` nutzen sollten, wenn Sie keine `Name`-Eigenschaft in der Mitgliedertabelle Ihres gewünschten Elements/Typs finden können. Die `x:Name` -Werte stellen einen Bezeichner für ein XAML-Element bereit, das zur Laufzeit verwendet werden kann, entweder durch bestimmte Subsysteme oder durch Hilfsprogrammmethoden <xref:System.Windows.FrameworkElement.FindName%2A>wie.  
  
 Im folgenden Beispiel wird <xref:System.Windows.FrameworkElement.Name%2A> auf ein <xref:System.Windows.Controls.StackPanel> -Element festgelegt. Anschließend <xref:System.Windows.Controls.Button> wird ein Handler für innerhalb von, <xref:System.Windows.Controls.StackPanel> der auf den <xref:System.Windows.Controls.StackPanel> verweist, durch `buttonContainer` den zugehörigen Instanzverweis, wie von <xref:System.Windows.FrameworkElement.Name%2A>festgelegt.  
  
 [!code-xaml[XAMLOvwSupport#NamedE](~/samples/snippets/csharp/VS_Snippets_Wpf/XAMLOvwSupport/CSharp/page7.xaml#namede)]  
[!code-xaml[XAMLOvwSupport#NamedE2](~/samples/snippets/csharp/VS_Snippets_Wpf/XAMLOvwSupport/CSharp/page7.xaml#namede2)]  
  
 [!code-csharp[XAMLOvwSupport#NameCode](~/samples/snippets/csharp/VS_Snippets_Wpf/XAMLOvwSupport/CSharp/page7.xaml.cs#namecode)]
 [!code-vb[XAMLOvwSupport#NameCode](~/samples/snippets/visualbasic/VS_Snippets_Wpf/XAMLOvwSupport/VisualBasic/Page1.xaml.vb#namecode)]  
  
 Der XAML-Name einer Instanz unterliegt genau wie eine Variable dem Konzept eines Geltungsbereichs, sodass die Eindeutigkeit von Namen innerhalb eines bestimmten, vorhersagbaren Geltungsbereichs erzwungen werden kann. Das primäre Markup, das eine Seite definiert, kennzeichnet einen eindeutigen XAML-Namescope, dessen Grenze das Stammelement dieser Seite ist. Allerdings können andere Markupquellen zur Laufzeit mit einer Seite interagieren, z.B. Stile oder Vorlagen innerhalb von Stilen, und solche Markupquellen verfügen häufig über ihre eigenen XAML-Namescopes, die nicht unbedingt mit dem XAML-Namescope der Seite verbunden sind. Weitere `x:Name` Informationen zu und XAML- <xref:System.Windows.FrameworkElement.Name%2A>Namescopes finden Sie unter, [x:Name-Direktive](../../xaml-services/x-name-directive.md)oder [WPF-XAML-Namescopes](wpf-xaml-namescopes.md).  
  
<a name="attached_properties_and_attached_events"></a>   
## <a name="attached-properties-and-attached-events"></a>Angefügte Eigenschaften und angefügte Ereignisse  
 In XAML ist ein Sprachfeature spezifiziert, das es ermöglicht, bestimmte Eigenschaften oder Ereignisse für jedes Element zu aktivieren, unabhängig davon, ob diese Eigenschaft oder dieses Ereignis in den Typdefinitionen für das Element vorhanden sind, für die sie festgelegt werden. Die Eigenschaftsversion dieser Funktion wird „angefügte Eigenschaft”, die Ereignisversion „angefügtes Ereignis” genannt. Im Prinzip können Sie sich angefügte Eigenschaften und Ereignisse als globale Mitglieder vorstellen, die für eine Instanz jedes XAML-Elements oder -Objekts festgelegt werden können. Jedoch muss dieses Element/diese Klasse oder eine größere Infrastruktur einen unterstützenden Eigenschaftenspeicher für die angefügten Werte unterstützen.  
  
 Angefügte Eigenschaften in XAML werden in der Regel über die Attributsyntax verwendet. In der Attributsyntax geben Sie eine angefügte Eigenschaft in der Form *Besitzertyp*.*Eigenschaftenname* an.  
  
 Oberflächlich betrachtet, gleicht dies der Verwendung eines Eigenschaftenelements, aber in diesem Fall ist der von Ihnen angegebene *Besitzertyp* immer ein anderer Typ als das Objektelement, in dem die angefügte Eigenschaft festgelegt wird. *Besitzertyp* ist der Typ, der die Accessormethoden bereitstellt, die von einem XAML-Prozessor zum Abrufen oder Festlegen des Werts der angefügten Eigenschaft benötigt werden.  
  
 Das häufigste Szenario für angefügte Eigenschaften ist, es untergeordneten Elementen zu ermöglichen, einen Eigenschaftswert an ihr übergeordnetes Element zu melden.  
  
 Im folgenden Beispiel wird die <xref:System.Windows.Controls.DockPanel.Dock%2A?displayProperty=nameWithType> angefügte-Eigenschaft veranschaulicht. Die <xref:System.Windows.Controls.DockPanel> -Klasse definiert die Accessoren <xref:System.Windows.Controls.DockPanel.Dock%2A?displayProperty=nameWithType> für und besitzt daher die angefügte-Eigenschaft. Die <xref:System.Windows.Controls.DockPanel> -Klasse enthält auch Logik, die die untergeordneten Elemente iteriert und jedes-Element auf einen fest <xref:System.Windows.Controls.DockPanel.Dock%2A?displayProperty=nameWithType>gelegten Wert von prüft. Wenn ein Wert gefunden wird, wird dieser Wert während des Layouts zum Positionieren der untergeordneten Elemente verwendet. Die Verwendung <xref:System.Windows.Controls.DockPanel> der angefügten-EigenschaftunddiesePositionierungsfunktionisttatsächlichdasMotivationsSzenariofür<xref:System.Windows.Controls.DockPanel.Dock%2A?displayProperty=nameWithType> die-Klasse.  
  
 [!code-xaml[XAMLOvwSupport#DockAP](~/samples/snippets/csharp/VS_Snippets_Wpf/XAMLOvwSupport/CSharp/page8.xaml#dockap)]  
  
 In [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] sind die meisten angefügten Eigenschaften auch als Abhängigkeitseigenschaften implementiert. Weitere Informationen finden Sie unter [Übersicht über angefügte Eigenschaften](attached-properties-overview.md).  
  
 Angefügte Ereignisse verwenden eine ähnliche *Besitzertyp*. *EventName*-Form der Attributsyntax. Wie bei nicht angefügten Ereignissen gibt der Attributwert für ein angefügtes Ereignis in XAML den Namen der Handlermethode an, die aufgerufen wird, wenn das Ereignis für das Element behandelt wird. Angefügte Ereignisse werden in WPF-XAML seltener verwendet. Weitere Informationen finden Sie unter [Übersicht über angefügte Ereignisse](attached-events-overview.md).  
  
<a name="base_classes_and_xaml"></a>   
## <a name="base-types-and-xaml"></a>Basis Typen und XAML  
 WPF-XAML und dem zugehörigen XAML-Namespace liegt zusätzlich zu Markupelementen für XAML eine Auflistung von Typen zugrunde, die [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)]-Objekten entsprechen. Allerdings können nicht alle Klassen Elementen zugeordnet werden. Abstrakte Klassen, z <xref:System.Windows.Controls.Primitives.ButtonBase>. b., und bestimmte nicht abstrakte Basisklassen werden für Vererbung [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)] im-Objektmodell verwendet. Basisklassen, einschließlich abstrakter Klassen, sind dennoch wichtig für die XAML-Entwicklung, da jedes konkrete XAML-Element Mitglieder einer Basisklasse in der eigenen Hierarchie erbt. Häufig enthalten diese Mitglieder Eigenschaften, die als Attribute für das Element festgelegt werden können, oder Ereignisse, die behandelt werden können. <xref:System.Windows.FrameworkElement>ist die konkrete Basis [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] Klasse von [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] auf der WPF-Frameworkebene. Beim Entwerfen [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]von verwenden Sie verschiedene Form-, Panel-, Decorator-oder Steuerelement Klassen, von <xref:System.Windows.FrameworkElement>denen alle abgeleitet werden. Eine zugehörige Basisklasse <xref:System.Windows.FrameworkContentElement>,, unterstützt Dokument orientierte Elemente, die für eine Fluss Layout-Präsentation gut geeignet sind, mithilfe von APIs, <xref:System.Windows.FrameworkElement>die die APIs in absichtlich widerspiegeln. Die Kombination aus Attributen auf Elementebene und einem [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)]-Objektmodell stellt Ihnen eine Reihe von allgemeinen Eigenschaften bereit, die für die meisten konkreten XAML-Elemente unabhängig vom jeweiligen XAML-Element und dem zugrunde liegenden Typ festlegbar sind.  
  
<a name="xaml_security"></a>   
## <a name="xaml-security"></a>XAML-Sicherheit  
 XAML ist eine Markupsprache, die Objektinstanziierung und -ausführung direkt darstellt. Daher verfügen in XAML erstellte Elemente über dieselbe Fähigkeit zur Interaktion mit Systemressourcen (z.B. Netzwerkzugriff, Dateisystem E/A), wie der gleichwertig generierte Code.  
  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]unterstützt die .NET Framework 4 Security Framework Code Access Security (CAS). Dies bedeutet, dass in der Internetzone ausgeführter [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-Inhalt eingeschränkte Ausführungsberechtigungen hat. "Loose XAML" (Seiten nicht kompilierten XAML-Codes, die beim Laden von einem XAML-Viewer interpretiert werden) und [!INCLUDE[TLA#tla_xbap](../../../../includes/tlasharptla-xbap-md.md)] werden normalerweise in dieser Internetzone ausgeführt und verwenden die gleiche Berechtigungsmenge.  Wenn XAML allerdings in eine voll vertrauenswürdige Anwendung geladen wird, hat es den gleichen Zugriff auf Systemressourcen wie die Hostanwendung. Weitere Informationen finden Sie unter [WPF-Sicherheit mit teilweiser Vertrauenswürdigkeit](../wpf-partial-trust-security.md).  
  
<a name="loading_xaml_from_code"></a>   
## <a name="loading-xaml-from-code"></a>Laden von XAML aus dem Code  
 XAML kann zum Definieren der gesamten Benutzeroberfläche verwendet werden, aber manchmal ist es auch sinnvoll, nur einen Teil der Benutzeroberfläche in XAML zu definieren. Diese Fähigkeit könnte man für eine teilweise Anpassungsfähigkeit durch den Benutzer verwenden, lokales Speichern von Informationen, die Verwendung von XAML zur Bereitstellung eines Geschäftsobjekts oder eine Vielzahl weiterer möglicher Szenarios. Der Schlüssel zu diesen Szenarien ist die <xref:System.Windows.Markup.XamlReader> <xref:System.Windows.Markup.XamlReader.Load%2A> -Klasse und die zugehörige-Methode. Als Eingabe dient eine XAML-Datei, und die Ausgabe ist ein Objekt, das die gesamte Laufzeitstruktur von Objekten darstellt, die über dieses Markup erstellt wurde. Sie können dieses Objekt dann als Eigenschaft eines anderen, bereits in der Anwendung bestehenden Objektes einfügen. Solange die Eigenschaft eine geeignete Eigenschaft im Inhaltsmodell ist, die tatsächliche Anzeigefähigkeiten besitzt und die der Ausführungs-Engine meldet, dass in der Anwendung neue Inhalte hinzugefügt wurden, können Sie den Inhalt einer laufenden Anwendung sehr einfach durch Laden von externem XAML ändern. Beachten Sie, dass aufgrund der offensichtlichen Sicherheitsimplikationen beim Laden von Dateien in laufende Anwendungen diese Funktion im Allgemeinen nur in voll vertrauenswürdigen Umgebungen verfügbar ist.  
  
<a name="whats_next"></a>   
## <a name="whats-next"></a>Ausblick  
 Dieses Thema enthält eine grundlegende Einführung in Konzepte und Terminologie der XAML-Syntax, wie sie in WPF Anwendung finden. Weitere Informationen zu den hier verwendeten Begriffen finden Sie unter [Ausführliche Erläuterung der XAML-Syntax](xaml-syntax-in-detail.md).  
  
 Wenn Sie dies noch nicht getan haben, testen Sie die Übungen im [Lernprogramm Exemplarische Vorgehensweise: Meine erste WPF-Desktop](../getting-started/walkthrough-my-first-wpf-desktop-application.md)Anwendung. Wenn Sie die im Tutorial beschriebene Markup-orientierte Anwendung erstellen, kann diese Übung helfen, viele der in diesem Thema beschriebenen Konzepte zu vertiefen.  
  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]verwendet ein bestimmtes Anwendungsmodell, das auf der <xref:System.Windows.Application> -Klasse basiert. Weitere Informationen finden Sie unter [Übersicht über die Anwendungsverwaltung](../app-development/application-management-overview.md).  
  
 Unter [Erstellen einer WPF-Anwendung](../app-development/building-a-wpf-application-wpf.md) erhalten Sie weitere Informationen zum Erstellen von XAML, einschließlich Anwendungen über die Befehlszeile und mit [!INCLUDE[TLA#tla_visualstu](../../../../includes/tlasharptla-visualstu-md.md)].  
  
 Unter [Übersicht über Abhängigkeitseigenschaften](dependency-properties-overview.md) finden Sie weitere Informationen über die Vielseitigkeit der Eigenschaften in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] und das Konzept von Abhängigkeitseigenschaften.  
  
## <a name="see-also"></a>Siehe auch

- [Ausführliche Erläuterung der XAML-Syntax](xaml-syntax-in-detail.md)
- [XAML- und benutzerdefinierte Klassen für WPF](xaml-and-custom-classes-for-wpf.md)
- [XAML-Namespace (x:) Sprach Features](../../xaml-services/xaml-namespace-x-language-features.md)
- [WPF-XAML-Erweiterungen](wpf-xaml-extensions.md)
- [Übersicht über Basiselemente](base-elements-overview.md)
- [Strukturen in WPF](trees-in-wpf.md)
