---
title: "&#220;bersicht &#252;ber XAML (WPF) | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-wpf"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "Attributsyntax [XAML]"
  - "Basisklassen [XAML]"
  - "Klassen [XAML]"
  - "Code-Behind-Dateien [WPF], XAML"
  - "Auflistungseigenschaften [XAML]"
  - "Inhaltsmodelle [XAML]"
  - "Ereignisse [XAML]"
  - "Extensible Application Markup Language (siehe XAML)"
  - "Eigenschaftselement [XAML]"
  - "Stammelement [XAML]"
  - "Routingereignisse"
  - "Benutzeroberflächen [XAML]"
  - "XAML [WPF], Informationen über XAML"
ms.assetid: a80db4cd-dd0f-479f-a45f-3740017c22e4
caps.latest.revision: 57
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 50
---
# &#220;bersicht &#252;ber XAML (WPF)
In diesem Thema werden die Funktionen der Sprache XAML beschrieben, und es wird gezeigt, wie Sie mithilfe von XAML [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]\-Anwendungen schreiben können.  Es wird in erster Linie die Implementierung von XAML in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] beschrieben.  XAML stellt ein größeres Sprachkonzept dar als [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  
  
 [!INCLUDE[autoOutline](../Token/autoOutline_md.md)]  
  
<a name="what_is_xaml"></a>   
## Was ist XAML?  
 XAML ist eine deklarative Markupsprache.  Bei Anwendung auf das [!INCLUDE[TLA2#tla_winfx](../../../../includes/tla2sharptla-winfx-md.md)]\-Programmiermodell vereinfacht XAML das Erstellen einer [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] für eine [!INCLUDE[TLA2#tla_winfx](../../../../includes/tla2sharptla-winfx-md.md)]\-Anwendung.  Sie können sichtbare [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]\-Elemente im deklarativen XAML\-Markup erstellen und anschließend die [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]\-Definition mithilfe von Code\-Behind\-Dateien, die über partielle Klassendefinitionen an das Markup geknüpft sind, von der Laufzeitlogik trennen.  XAML stellt die Instanziierung von Objekten in einem spezifischen Satz von in Assemblys definierten Unterstützungstypen direkt dar. Dieser Ansatz unterscheidet sich von den meisten anderen Markupsprachen, die in der Regel interpretierte Sprachen ohne eine direkte Verbindung zu einem Unterstützungstypsystem sind.  XAML ermöglicht einen Workflow, in dem unterschiedliche Personen mit ggf. unterschiedlichen Tools an der [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] und der Logik einer Anwendung arbeiten können.  
  
 Bei der Darstellung als Text sind XAML\-Dateien XML\-Dateien, die im Allgemeinen die Erweiterung `.xaml` aufweisen.  Die Dateien können mit jeder XML\-Codierung codiert werden, typisch ist jedoch die Codierung als UTF\-8.  
  
 Im folgenden Beispiel wird gezeigt, wie Sie eine Schaltfläche als Teil einer [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] erstellen können.  Dieses Beispiel soll nur einen Eindruck davon vermitteln, wie in XAML allgemeine [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]\-Programmiermetaphern dargestellt werden \(das Beispiel ist nicht vollständig\).  
  
 [!code-xml[XAMLOvwSupport#DirtSimple](../../../../samples/snippets/csharp/VS_Snippets_Wpf/XAMLOvwSupport/CSharp/page2.xaml#dirtsimple)]  
  
<a name="xaml_syntax_in_brief"></a>   
## Zusammenfassung der XAML\-Syntax  
 In den folgenden Abschnitten werden die grundlegenden Formen der XAML\-Syntax beschrieben, und es wird ein kurzes Markupbeispiel vorgestellt.  Diese Abschnitte sollen keine umfassenden Informationen über jedes Syntaxformat vermitteln, z. B. wie es im Unterstützungstypsystem dargestellt wird.  Weitere Informationen zu den Details der XAML\-Syntax für die unterschiedlichen in diesem Thema eingeführten Syntaxformate finden Sie unter [Ausführliche Erläuterung der XAML\-Syntax](../../../../docs/framework/wpf/advanced/xaml-syntax-in-detail.md).  
  
 Ein großer Teil des Materials in den nächsten Abschnitten ist für Sie elementar, wenn Sie bereits mit der XML\-Sprache vertraut sind.  Dies ist eine Folge eines der grundlegenden Entwurfsprinzipien von XAML.  Die XAML\-Sprache definiert eigene Konzepte, aber diese Konzepte funktionieren innerhalb der XML\-Sprache und des Markupformats.  
  
### XAML\-Objektelemente  
 Ein Objektelement deklariert in der Regel eine Instanz eines Typs.  Dieser Typ wird in den Assemblys definiert, die die Basistypen für eine Technologie bereitstellen, die XAML als Sprache verwendet.  
  
 Die Objektelementsyntax beginnt immer mit einer öffnenden spitzen Klammer \(\<\).  Darauf folgt der Name des Typs, in dem Sie eine Instanz erstellen möchten.  \(Der Name kann möglicherweise ein Präfix enthalten. Dieses Konzept wird später erläutert.\) Danach können Sie optional Attribute für das Objektelement deklarieren.  Zum Abschließen des Objektelementtags fügen Sie eine schließende spitze Klammer \(\>\) ein.  Sie können stattdessen eine selbstschließende Form ohne Inhalt verwenden, indem Sie das Tag mit einem Schrägstrich und direkt folgend einer schließenden spitzen Klammer \(\/\>\) abschließen.  Betrachten Sie z. B. den oben dargestellten Markupausschnitt erneut:  
  
 [!code-xml[XAMLOvwSupport#DirtSimple](../../../../samples/snippets/csharp/VS_Snippets_Wpf/XAMLOvwSupport/CSharp/page2.xaml#dirtsimple)]  
  
 Dort werden zwei Objektelemente angegeben: `<StackPanel>` \(mit Inhalt und einem später folgenden schließenden Tag\) und `<Button .../>` \(die selbstschließende Form mit mehreren Attributen\).  Die Objektelemente `StackPanel` und `Button` werden jeweils dem Namen einer Klasse zugeordnet, die durch [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] definiert wird und Teil der [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]\-Assemblys ist.  Beim Angeben eines Objektelementtags erstellen Sie eine Anweisung für die XAML\-Verarbeitung zum Erstellen einer neuen Instanz.  Die einzelnen Instanzen werden durch Aufrufen des Standardkonstruktors des zugrunde liegenden Typs beim Analysieren und Laden von XAML erstellt.  
  
### Attributsyntax \(Eigenschaften\)  
 Eigenschaften eines Objekts können oft als Attribute des Objektelements ausgedrückt werden.  In der Attributsyntax wird die Eigenschaft, die festgelegt wird, in Attributsyntax benannt, gefolgt vom Zuweisungsoperator \(\=\).  Der Wert eines Attributs wird immer als Zeichenfolge in Anführungszeichen angegeben.  
  
 Die Attributsyntax ist die optimale Syntax zum Festlegen von Eigenschaften. Sie eignet sich hervorragend für Entwickler, die in der Vergangenheit Markupsprachen verwendet haben.  Mit dem folgenden Markup wird beispielsweise eine Schaltfläche mit rotem Text auf blauem Hintergrund erstellt, mit der der als `Content` angegebene Text angezeigt wird.  
  
 [!code-xml[XAMLOvwSupport#BlueRedButton](../../../../samples/snippets/csharp/VS_Snippets_Wpf/XAMLOvwSupport/CSharp/Page1.xaml#blueredbutton)]  
  
### Eigenschaftenelementsyntax  
 Bei einigen Eigenschaften eines Objektelements kann keine Attributsyntax verwendet werden, da die zum Bereitstellen des Eigenschaftswerts erforderlichen Objekte oder Informationen innerhalb der Einschränkungen der Attributsyntax für Anführungszeichen und Zeichenfolgen nicht angemessen ausgedrückt werden können.  In diesen Fällen kann eine andere Syntax verwendet werden, die als Eigenschaftenelementsyntax bezeichnet wird.  
  
 Die Syntax für das Starttag des Eigenschaftenelements lautet: `<`*Typname*`.`*Eigenschaftenname*`>`.  Im Allgemeinen ist der Inhalt dieses Tags ein Objektelement des Typs, den die Eigenschaft als Wert annimmt.  Sie müssen das Eigenschaftenelement mit einem Endtag schließen, nachdem Sie Inhalt angegeben haben.  Die Syntax für das Endtag lautet: `</`*Typname*`.`*Eigenschaftenname*`>`.  
  
 Wenn eine Attributsyntax verwendet werden kann, ist diese in der Regel bequemer und ermöglicht ein kompakteres Markup. Das ist jedoch häufig lediglich eine Frage des Stils, keine technische Beschränkung.  Im Folgenden Beispiel sind dieselben Eigenschaften wie im vorhergehenden Beispiel mit der Attributsyntax dargestellt, wobei hier die Eigenschaftenelementsyntax für alle Eigenschaften von `Button` verwendet wird.  
  
 [!code-xml[XAMLOvwSupport#BlueRedButtonPE](../../../../samples/snippets/csharp/VS_Snippets_Wpf/XAMLOvwSupport/CSharp/Page1.xaml#blueredbuttonpe)]  
  
### Auflistungssyntax  
 Die Sprache XAML umfasst eine Reihe von Optimierungen, die ein besser lesbares Markup ermöglichen.  Eine solche Optimierung besteht darin, dass, wenn eine bestimmte Eigenschaft einen Auflistungstyp akzeptiert, im Markup als untergeordnete Elemente innerhalb des Werts dieser Eigenschaft definierte Elemente Teil der Auflistung werden.  In diesem Fall ist der Wert, der auf die Auflistungseigenschaft festgelegt wird, eine Auflistung von untergeordneten Objektelementen.  
  
 Im folgenden Beispiel wird die Auflistungssyntax zum Festlegen von Werten der <xref:System.Windows.Media.GradientBrush.GradientStops%2A>\-Eigenschaft veranschaulicht:  
  
```xaml  
<LinearGradientBrush>  
  <LinearGradientBrush.GradientStops>  
    <!-- no explicit new GradientStopCollection, parser knows how to find or create -->  
    <GradientStop Offset="0.0" Color="Red" />  
    <GradientStop Offset="1.0" Color="Blue" />  
  </LinearGradientBrush.GradientStops>  
</LinearGradientBrush>  
```  
  
### XAML\-Inhaltseigenschaften  
 XAML gibt eine Sprachfunktion an, wodurch eine Klasse genau eine ihrer Eigenschaften als XAML\-Inhaltseigenschaft festlegen kann.  Untergeordnete Elemente dieses Objektelements werden verwendet, um den Wert dieser Inhaltseigenschaft festzulegen.  Anders ausgedrückt können Sie nur für die Inhaltseigenschaft ein Eigenschaftenelement auslassen, wenn Sie diese Eigenschaft in XAML\-Markup festlegen, und im Markup eine besser sichtbare Metapher für über\- und untergeordnete Elemente erzeugen.  
  
 <xref:System.Windows.Controls.Border> gibt z. B. eine Inhaltseigenschaft von <xref:System.Windows.Controls.Decorator.Child%2A> an.  Die folgenden beiden <xref:System.Windows.Controls.Border>\-Elemente werden identisch behandelt.  Beim ersten Element wird die Inhaltseigenschaftensyntax genutzt, und das `Border.Child`\-Eigenschaftenelement wird ausgelassen.  Im zweiten Element wird `Border.Child` explizit angezeigt.  
  
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
  
 Als Regel für die XAML\-Sprache muss der Wert einer XAML\-Inhaltseigenschaft entweder vor oder nach anderen Eigenschaftenelementen in diesem Objektelement vollständig angegeben werden.  Das folgende Markup wird beispielsweise nicht kompiliert:  
  
```  
<Button>I am a   
  <Button.Background>Blue</Button.Background>  
  blue button</Button>  
```  
  
 Weitere Informationen zu dieser Einschränkung bei XAML\-Inhaltseigenschaften finden Sie im Abschnitt "XAML\-Inhaltseigenschaften" unter [Ausführliche Erläuterung der XAML\-Syntax](../../../../docs/framework/wpf/advanced/xaml-syntax-in-detail.md).  
  
### Textinhalt  
 Eine kleine Anzahl von XAML\-Elementen kann Text direkt als Inhalt verarbeiten.  Damit dies möglich ist, muss eine der beiden folgenden Bedingungen erfüllt werden:  
  
-   Die Klasse muss eine Inhaltseigenschaft deklarieren, und der Typ dieser Inhaltseigenschaft muss einer Zeichenfolge zugewiesen werden können \(der Typ könnte <xref:System.Object> lauten\).  Zum Beispiel verwendet jedes <xref:System.Windows.Controls.ContentControl> <xref:System.Windows.Controls.ContentControl.Content%2A> als Inhaltseigenschaft, es ist vom Typ <xref:System.Object>, und dies unterstützt die folgende Verwendung für ein praktisches <xref:System.Windows.Controls.ContentControl>, z. B. einen <xref:System.Windows.Controls.Button>: `<Button>Hello</Button>`.  
  
-   Der Typ muss einen Typkonverter deklarieren. In diesem Fall wird der Textinhalt als Initialisierungstext für diesen Typkonverter verwendet.  Beispielsweise `<Brush>Blue</Brush>`.  Dieser Fall ist in der Praxis weniger häufig.  
  
-   Der Typ muss eine bekannte XAML\-Sprachprimitive sein.  
  
### Kombination von Inhaltseigenschaften und Auflistungssyntax  
 Betrachten Sie das folgende Beispiel:  
  
```xaml  
<StackPanel>  
  <Button>First Button</Button>  
  <Button>Second Button</Button>  
</StackPanel>  
```  
  
 In diesem Beispiel ist jeder <xref:System.Windows.Controls.Button> ein untergeordnetes Element von <xref:System.Windows.Controls.StackPanel>.  Hierbei handelt es sich um ein optimiertes und intuitives Markup, bei dem zwei Tags aus zwei unterschiedlichen Gründen weggelassen werden.  
  
-   **Weggelassenes StackPanel.Children\-Eigenschaftenelement:** <xref:System.Windows.Controls.StackPanel> wird von <xref:System.Windows.Controls.Panel> abgeleitet.  <xref:System.Windows.Controls.Panel> definiert <xref:System.Windows.Controls.Panel.Children%2A?displayProperty=fullName> als seine XAML\-Inhaltseigenschaft.  
  
-   **Weggelassenes UIElementCollection\-Objektelement:** Die <xref:System.Windows.Controls.Panel.Children%2A?displayProperty=fullName>\-Eigenschaft nimmt den Typ <xref:System.Windows.Controls.UIElementCollection> an, der <xref:System.Collections.IList> implementiert.  Das Elementtag der Auflistung kann ausgelassen werden, entsprechend den Regeln zum Verarbeiten von Auflistungen, z. B. <xref:System.Collections.IList>.  \(In diesem Fall kann <xref:System.Windows.Controls.UIElementCollection> nicht instanziiert werden, da kein Standardkonstruktor verfügbar gemacht wird. Deshalb wurde das <xref:System.Windows.Controls.UIElementCollection>\-Objektelement auskommentiert\).  
  
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
  
### Attributsyntax \(Ereignisse\)  
 Die Attributsyntax kann auch für Member verwendet werden, die Ereignisse und keine Eigenschaften sind.  In diesem Fall ist der Attributname der Name des Ereignisses.  In der WPF\-Implementierung von Ereignissen für XAML ist der Attributwert der Name eines Handlers, der den Delegaten dieses Ereignisses implementiert.  Das folgende Markup weist z. B. einen Handler für das <xref:System.Windows.Controls.Primitives.ButtonBase.Click>\-Ereignis zu einem in Markup erstellten <xref:System.Windows.Controls.Button> zu:  
  
 [!code-xml[XAMLOvwSupport#ButtonWithCodeBehind](../../../../samples/snippets/csharp/VS_Snippets_Wpf/XAMLOvwSupport/CSharp/page3.xaml#buttonwithcodebehind)]  
  
 Ereignisse und XAML in WPF sind komplexer, als dies in diesem Beispiel für die Attributsyntax dargestellt wird.  Sie könnten sich z. B. fragen, was der hier referenzierte `ClickHandler` darstellt und wie er definiert wird.  Dies wird im Abschnitt  weiter unten in diesem Thema erläutert.  
  
<a name="case_and_whitespace_in_xaml"></a>   
## Groß\-\/Kleinschreibung und Leerzeichen in XAML  
 In XAML wird im Allgemeinen die Groß\-\/Kleinschreibung beachtet.  Zum Auflösen von Unterstützungstypen wird in WPF\-XAML die Groß\-\/Kleinschreibung nach den gleichen Regeln wie in CLR beachtet.  Objektelemente, Eigenschaftenelemente und Attributnamen müssen beim Vergleich anhand des Namens des zugrunde liegenden Typs oder mit einem Member eines Typs unter Beachtung der Groß\-\/Kleinschreibung angegeben werden.  Bei XAML\-Schlüsselwörtern und Primitiven wird die Groß\-\/Kleinschreibung ebenfalls beachtet.  Bei Werten muss die Groß\-\/Kleinschreibung nicht immer beachtet werden.  Ob die Groß\-\/Kleinschreibung beachtet werden muss, hängt vom Verhalten des der Eigenschaft zugeordneten Typkonverters, der den Wert annimmt, oder vom Eigenschaftswerttyp ab.  Eigenschaften, die beispielsweise den <xref:System.Boolean>\-Typ annehmen, können entweder `true` oder `True` als entsprechende Werte annehmen, aber nur deswegen, weil die systemeigene WPF\-XAML\-Parsertypkonvertierung für Zeichenfolgen in <xref:System.Boolean> diese bereits als Entsprechungen zulässt.  
  
 WPF\-XAML\-Prozessoren und \-Serialisierungsprogramme ignorieren oder löschen alle nicht signifikanten Leerzeichen und normalisieren alle signifikanten Leerzeichen.  Dies entspricht den Empfehlungen der XAML\-Spezifikation für das Standardverhalten von Leerstellen.  Dieses Verhalten hat im Allgemeinen nur Folgen, wenn Sie innerhalb von XAML\-Inhaltseigenschaften Zeichenfolgen angeben.  Vereinfacht ausgedrückt: XAML konvertiert Leerzeichen, Zeilenvorschub und Tabulatorzeichen in Leerzeichen und behält ein Leerzeichen bei, wenn sich dieses an einem Ende einer zusammenhängenden Zeichenfolge befindet.  Die Behandlung von Leerzeichen bei XAML wird in diesem Thema nicht erschöpfend behandelt.  Weitere Informationen finden Sie unter [Leerstellenverarbeitung in XAML](../../../../docs/framework/xaml-services/whitespace-processing-in-xaml.md).  
  
<a name="markup_extensions"></a>   
## Markuperweiterungen  
 Markuperweiterungen sind ein XAML\-Sprachkonzept.  Wenn sie zum Bereitstellen des Werts einer Attributsyntax verwendet werden, geben geschweifte Klammern \(`{` und `}`\) eine Markuperweiterungsverwendung an.  Durch diese Verwendung werden bei der XAML\-Verarbeitung Attributwerte nicht wie üblich als Zeichenfolgenliterale oder als in Zeichenfolgen konvertierbarer Werte behandelt.  
  
 Die bei der [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]\-Anwendungsprogrammierung am häufigsten verwendeten Markuperweiterungen sind [Bindung](../../../../docs/framework/wpf/advanced/binding-markup-extension.md) für Datenbindungsausdrücke sowie die Ressourcenverweise [StaticResource](../../../../docs/framework/wpf/advanced/staticresource-markup-extension.md) und [DynamicResource](../../../../docs/framework/wpf/advanced/dynamicresource-markup-extension.md).  Mit Markuperweiterungen können Sie Werte mithilfe der Attributsyntax für Eigenschaften bereitstellen, auch wenn diese Eigenschaft allgemein keine Attributsyntax unterstützt.  Markuperweiterungen verwenden oft Zwischenausdruckstypen, um Funktionen wie das späte Zuweisen von Werten oder das Verweisen auf andere Objekte zu aktivieren, die nur zur Laufzeit vorhanden sind.  
  
 Das folgende Markup legt z. B. den Wert der <xref:System.Windows.FrameworkElement.Style%2A>\-Eigenschaft mithilfe der Attributsyntax fest.  Die <xref:System.Windows.FrameworkElement.Style%2A>\-Eigenschaft enthält eine Instanz der <xref:System.Windows.Style>\-Klasse, die standardmäßig nicht von einer Zeichenfolge der Attributsyntax instanziiert werden kann.  In diesem Fall verweist das Attribut jedoch auf eine bestimmte Markuperweiterung, [StaticResource](../../../../docs/framework/wpf/advanced/staticresource-markup-extension.md).  Bei der Verarbeitung der Markuperweiterung wird ein Verweis auf ein Format zurückgegeben, das zuvor als Ressource mit Schlüssel in einem Ressourcenwörterbuch instanziiert wurde.  
  
<!-- TODO: review snippet reference  [!CODE [FEResourceSH#XAMLOvwShortResources](FEResourceSH#XAMLOvwShortResources)]  -->  
<!-- TODO: review snippet reference [!CODE [FEResourceSH#XAMLOvwShortResources2](FEResourceSH#XAMLOvwShortResources2)]  -->  
<!-- TODO: review snippet reference [!CODE [FEResourceSH#XAMLOvwShortResources3](FEResourceSH#XAMLOvwShortResources3)]  -->  
  
 Eine Verweisliste mit Markuperweiterungen für XAML bei spezieller Implementierung in WPF finden Sie unter [WPF\-XAML\-Erweiterungen](../../../../docs/framework/wpf/advanced/wpf-xaml-extensions.md).  Eine Verweisliste mit Markuperweiterungen, die in "System.Xaml" definiert sind und für .NET Framework\-XAML\-Implementierungen umfassender verfügbar sind, finden Sie unter [Sprachfeatures des XAML\-Namespace \(x:\)](../../../../docs/framework/xaml-services/xaml-namespace-x-language-features.md).  Weitere Informationen über Markuperweiterungskonzepte finden Sie unter [Markuperweiterungen und WPF\-XAML](../../../../docs/framework/wpf/advanced/markup-extensions-and-wpf-xaml.md).  
  
<a name="type_converters"></a>   
## Typkonverter  
 Im Abschnitt zur  wurde angegeben, dass es möglich sein muss, dass der Attributwert von einer Zeichenfolge festgelegt wird.  Die einfache, integrierte Behandlung, wie Zeichenfolgen in andere Objekttypen oder primitive Werte konvertiert werden, hängt vom <xref:System.String>\-Typ selbst ab, ebenso wie in einigen Fällen die systemeigene Verarbeitung für bestimmte Typen wie <xref:System.DateTime> oder <xref:System.Uri>.  Viele [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]\-Typen oder \-Member dieser Typen erweitern das einfache Verhalten bei der Verarbeitung von Attributen in Zeichenfolgen insofern, als dass Instanzen komplexerer Objekttypen als Zeichenfolgen und Attribute angegeben werden können.  
  
 Die <xref:System.Windows.Thickness>\-Struktur ist ein Beispiel für einen Typ, bei dem die Typkonvertierung für die XAML\-Verwendung aktiviert ist.  <xref:System.Windows.Thickness> gibt Maße innerhalb eines geschachtelten Rechtecks an und wird als Wert für Eigenschaften wie <xref:System.Windows.FrameworkElement.Margin%2A> verwendet.  Durch Festlegen eines Typkonverters für <xref:System.Windows.Thickness> können alle Eigenschaften, die <xref:System.Windows.Thickness> verwenden, einfacher in XAML angegeben werden, da sie als Attribute angegeben werden können.  Im folgenden Beispiel wird eine Typkonvertierung und Attributsyntax zum Bereitstellen eines Werts für einen <xref:System.Windows.FrameworkElement.Margin%2A> verwendet:  
  
 [!code-xml[XAMLOvwSupport#MarginTCE](../../../../samples/snippets/csharp/VS_Snippets_Wpf/XAMLOvwSupport/CSharp/page7.xaml#margintce)]  
  
 Das vorherige Beispiel mit der Attributsyntax entspricht dem folgenden Beispiel einer umständlicheren Syntax, bei der der <xref:System.Windows.FrameworkElement.Margin%2A> über die Eigenschaftenelementsyntax festgelegt wird, die ein <xref:System.Windows.Thickness>\-Objektelement enthält.  Die vier Schlüsseleigenschaften von <xref:System.Windows.Thickness> werden als Attribute der neuen Instanz festgelegt:  
  
 [!code-xml[XAMLOvwSupport#MarginVerbose](../../../../samples/snippets/csharp/VS_Snippets_Wpf/XAMLOvwSupport/CSharp/page7.xaml#marginverbose)]  
  
> [!NOTE]
>  Es gibt außerdem einige Objekte, bei denen eine Eigenschaft nur mithilfe der Typkonvertierung für diesen Typ ohne Einbeziehung einer Unterklasse öffentlich festgelegt werden kann, da der Typ selbst keinen Standardkonstruktor aufweist.  Ein Beispiel hierfür ist <xref:System.Windows.Input.Cursor>.  
  
 Weitere Informationen zur Typkonvertierung und der Verwendung für die Attributsyntax finden Sie unter [TypeConverter und XAML](../../../../docs/framework/wpf/advanced/typeconverters-and-xaml.md).  
  
<a name="xaml_root_elements_and_xaml_namespaces"></a>   
## XAML\-Stammelemente und XAML\-Namespaces  
 Eine XAML\-Datei darf nur über ein Stammelement verfügen, wenn es sich sowohl um eine regelkonforme [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)]\-Datei als auch um eine zulässige XAML\-Datei handeln soll.  Verwenden Sie für typische WPF\-Szenarios ein Stammelement, das eine wichtige Bedeutung im WPF\-Anwendungsmodell hat \(z. B. <xref:System.Windows.Window> oder <xref:System.Windows.Controls.Page> für eine Seite, <xref:System.Windows.ResourceDictionary> für ein externes Wörterbuch oder <xref:System.Windows.Application> für die Anwendungsdefinition\).  Das folgende Beispiel zeigt das Stammelement einer typischen XAML\-Datei für eine [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]\-Seite mit dem Stammelement <xref:System.Windows.Controls.Page>.  
  
 [!code-xml[XAMLOvwSupport#RootOnly](../../../../samples/snippets/csharp/VS_Snippets_Wpf/XAMLOvwSupport/CSharp/page2.xaml#rootonly)]  
[!code-xml[XAMLOvwSupport#RootOnly2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/XAMLOvwSupport/CSharp/page2.xaml#rootonly2)]  
  
 Das Stammelement enthält darüber hinaus auch die Attribute `xmlns` und `xmlns:x`.  Diese Attribute geben einem XAML\-Prozessor an, welche XAML\-Namespaces die Typdefinitionen für Basistypen enthalten, auf die das Markup als Elemente verweist.  Das `xmlns`\-Attribut gibt ausdrücklich den XAML\-Standardnamespace an.  Innerhalb des XAML\-Standardnamespace können Objektelemente im Markup ohne Präfix angegeben werden.  Bei den meisten [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]\-Anwendungen sowie bei fast allen Beispielen in den [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]\-Abschnitten im [!INCLUDE[TLA2#tla_sdk](../../../../includes/tla2sharptla-sdk-md.md)] wird der XAML\-Standardnamespace dem [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]\-Namespace [!INCLUDE[TLA#tla_wpfxmlnsv1](../../../../includes/tlasharptla-wpfxmlnsv1-md.md)] zugeordnet.  Das `xmlns:x`\-Attribut gibt einen zusätzlichen XAML\-Namespace an, der dem XAML\-Sprachnamespace [!INCLUDE[TLA#tla_xamlxmlnsv1](../../../../includes/tlasharptla-xamlxmlnsv1-md.md)] zuordnet.  
  
 Diese Verwendung von `xmlns` zum Definieren eines Bereichs für die Verwendung und Zuordnung eines Namensbereichs stimmt mit der XML 1.0\-Spezifikation überein.  XAML\-Namensbereiche unterscheiden sich nur darin von XML\-Namensbereichen, dass ein XAML\-Namensbereich impliziert, wie die Elemente des Namensbereichs bei der Typauflösung und XAML\-Analyse von Typen unterstützt werden.  
  
 Beachten Sie, dass die `xmlns`\-Attribute nur beim Stammelement jeder XAML\-Datei unbedingt erforderlich sind.  `xmlns`\-Definitionen gelten für alle Nachfolgerelemente des Stammelements \(auch dieses Verhalten entspricht der XML 1.0\-Spezifikation für `xmlns`\). `xmlns`\-Attribute sind auch bei anderen Elementen unterhalb des Stamms zulässig und gelten für alle Nachfolgerelemente des definierenden Elements.  Allerdings können regelmäßige Definitionen oder Neudefinitionen von XAML\-Namespaces ein XAML\-Markupformat ergeben, das schwer zu lesen ist.  
  
 Die [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]\-Implementierung des XAML\-Prozessors schließt eine Infrastruktur ein, die die WPF\-Kernassemblys erkennt.  Die [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]\-Kernassemblys enthalten bekanntermaßen die Typen, die die [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]\-Zuordnungen zum XML\-Standardnamespace unterstützen.  Dies wird durch die Konfiguration ermöglicht, die Teil der Projektbuilddatei und der WPF\-Build\- und \-Projektsysteme ist.  Daher ist nur das Deklarieren des XAML\-Standardnamespaces als Standard\-`xmlns` erforderlich, um auf XAML\-Elemente zu verweisen, die aus [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]\-Assemblys stammen.  
  
### Das Präfix x:  
 Im vorherigen Stammelementbeispiel wurde das Präfix `x:` verwendet, um den XAML\-Namespace [!INCLUDE[TLA#tla_xamlxmlnsv1](../../../../includes/tlasharptla-xamlxmlnsv1-md.md)] zuzuordnen, der der dedizierte XAML\-Namespace für die Unterstützung von XAML\-Sprachkonstrukten ist.  Hier wird das Präfix `x:` verwendet, um den XAML\-Namespace in den Vorlagen für Projekte, in Beispielen und in der Dokumentation in diesem [!INCLUDE[TLA2#tla_sdk](../../../../includes/tla2sharptla-sdk-md.md)] zuzuordnen.  Der XAML\-Namespace für die XAML\-Sprache enthält verschiedene Programmierkonstrukte, die Sie in Ihrem XAML\-Code sehr häufig verwenden werden.  Im Folgenden finden Sie eine Auflistung der am häufigsten verwendeten `x:`\-Präfixprogrammierkonstrukte:  
  
-   [x:Key](../../../../docs/framework/xaml-services/x-key-directive.md): Legt einen eindeutigen Schlüssel für jede Ressource in einem <xref:System.Windows.ResourceDictionary> \(oder ähnlichen Wörterbuchkonzepten in anderen Frameworks\) fest.  `x:Key` wird wohl 90 % der Verwendung von `x:` im Markup einer typischen WPF\-Anwendung ausmachen.  
  
-   [x:Class](../../../../docs/framework/xaml-services/x-class-directive.md): Gibt den [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)]\-Namespace und \-Klassennamen für die Klasse an, die den Code\-Behind für eine XAML\-Seite angibt.  Eine Klasse dieser Art muss vorhanden sein, um den Code\-Behind gemäß dem WPF\-Programmiermodell unterstützen zu können. Aus diesem Grund ist `x:` fast immer zugeordnet, auch wenn keine Ressourcen vorhanden sind.  
  
-   [x:Name](../../../../docs/framework/xaml-services/x-name-directive.md): Gibt einen Laufzeitobjektnamen für die Instanz an, die nach der Verarbeitung eines Objektelements im Laufzeitcode vorhanden ist.  Im Allgemeinen verwenden Sie häufig eine in WPF definierte entsprechende Eigenschaft für [x:Name](../../../../docs/framework/xaml-services/x-name-directive.md).  Solche Eigenschaften werden speziell einer CLR\-Unterstützungseigenschaft zugeordnet und sind so praktischer für die Anwendungsprogrammierung, wo Sie häufig mithilfe von Laufzeitcode die benannten Elemente von initialisiertem XAML\-Code suchen.  Die gebräuchlichste Eigenschaft dieser Art ist <xref:System.Windows.FrameworkElement.Name%2A?displayProperty=fullName>.  Sie könnten weiterhin [x:Name](../../../../docs/framework/xaml-services/x-name-directive.md) verwenden, wenn die entsprechende [WPF\-Frameworkebene](GTMT) <xref:System.Windows.FrameworkElement.Name%2A>\-Eigenschaft in einem bestimmten Typ nicht unterstützt wird.  Dies ist bei bestimmten Animationsszenarien der Fall.  
  
-   [x:Static](../../../../docs/framework/xaml-services/x-static-markup-extension.md): Ermöglicht einen Verweis, der einen statischen Wert zurückgibt, der nicht anderweitig als XAML\-kompatible Eigenschaft festgelegt werden kann.  
  
-   [x:Type](../../../../docs/framework/xaml-services/x-type-markup-extension.md): Erstellt anhand eines Typnamens einen <xref:System.Type>\-Verweis.  Wird verwendet, um Attribute anzugeben, die <xref:System.Type> annehmen, wie z. B. <xref:System.Windows.Style.TargetType%2A?displayProperty=fullName>, obwohl die Eigenschaft häufig eine eigene Konvertierung von Zeichenfolgen in <xref:System.Type> aufweist, sodass die Markuperweiterungsverwendung von [x:Type](../../../../docs/framework/xaml-services/x-type-markup-extension.md) optional ist.  
  
 Es gibt weitere Programmierungskonstrukte im `x:`\-Präfix\/XAML\-Namespace, die nicht so häufig verwendet werden.  Ausführlichere Informationen hierzu finden Sie unter [Sprachfeatures des XAML\-Namespace \(x:\)](../../../../docs/framework/xaml-services/xaml-namespace-x-language-features.md).  
  
<a name="custom_prefixes_and_custom_types_in_xaml"></a>   
## Benutzerdefinierte Präfixe und benutzerdefinierte Typen in XAML  
 Für eigene benutzerdefinierte Assemblys oder für Assemblys außerhalb des WPF\-Kerns aus PresentationCore, PresentationFramework und WindowsBase können Sie die Assembly als Teil einer benutzerdefinierten `xmlns`\-Zuordnung angeben.  Sie können dann auf Typen in dieser Assembly im XAML\-Code verweisen, sofern dieser Typ korrekt implementiert wird, um die gewünschten XAML\-Verwendungen zu unterstützen.  
  
 Im Folgenden finden Sie ein einfaches Beispiel dafür, wie benutzerdefinierte Präfixe in XAML\-Markup verwendet werden.  Das Präfix `custom` wird im Stammelementtag definiert und einer bestimmten Assembly zugeordnet, die mit der Anwendung gepackt und verfügbar ist.  Diese Assembly enthält den Typ `NumericUpDown`, der implementiert wird, um die allgemeine XAML\-Verwendung sowie die Verwendung einer Klassenvererbung zu unterstützen, die das Einfügen an dieser Stelle in einem WPF\-XAML\-Inhaltsmodell ermöglicht.  Eine Instanz dieses `NumericUpDown`\-Steuerelements wird als Objektelement deklariert. Dabei wird das Präfix verwendet, damit dem XAML\-Parser bekannt ist, welcher XAML\-Namespace den Typ enthält und wo sich daher die Unterstützungsassembly befindet, die die Typdefinition enthält.  
  
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
  
 Weitere Informationen zu benutzerdefinierten Typen in XAML finden Sie unter [XAML\- und benutzerdefinierte Klassen für WPF](../../../../docs/framework/wpf/advanced/xaml-and-custom-classes-for-wpf.md).  
  
 Weitere Informationen zum Zusammenhang zwischen XML\-Namespaces und den Namespaces des Sicherungscodes in Assemblys finden Sie unter [XAML\-Namespaces und Namespacezuordnung für WPF\-XAML](../../../../docs/framework/wpf/advanced/xaml-namespaces-and-namespace-mapping-for-wpf-xaml.md).  
  
<a name="events_and_xaml_codebehind"></a>   
## Ereignisse und XAML\-Code\-Behind  
 Die meisten [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]\-Anwendungen bestehen sowohl aus XAML\-Markup als auch aus Code\-Behind.  Innerhalb eines Projekts wird der XAML\-Code als `.xaml`\-Datei geschrieben, und zum Schreiben einer CodeBehind\-Datei wird eine [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)]\-Sprache wie [!INCLUDE[TLA#tla_visualb](../../../../includes/tlasharptla-visualb-md.md)] oder [!INCLUDE[TLA#tla_cshrp](../../../../includes/tlasharptla-cshrp-md.md)] verwendet.  Beim Markupkompilieren einer XAML\-Datei als Teil des WPF\-Programmier\- und Anwendungsmodells wird der Speicherort der XAML\-CodeBehind\-Datei für eine XAML\-Datei durch die Angabe eines Namespace und einer Klasse als `x:Class`\-Attribut des Stammelements des XAML\-Codes identifiziert.  
  
 Im Beispiel haben Sie bisher verschiedene Schaltflächen gesehen, aber keiner dieser Schaltflächen war ein logisches Verhalten zugeordnet.  Der erste Mechanismus auf Anwendungsebene zum Hinzufügen eines Verhaltens für ein Objektelement besteht darin, ein vorhandenes Ereignis der Elementklasse zu verwenden und einen spezifischen Handler für dieses Ereignis zu schreiben, der beim Auslösen dieses Ereignisses zur Laufzeit aufgerufen wird.  Der Ereignisname und der Name des zu verwendenden Handlers werden im Markup angegeben, während der Code, der den Handler implementiert, im Code\-Behind definiert wird.  
  
 [!code-xml[XAMLOvwSupport#ButtonWithCodeBehind](../../../../samples/snippets/csharp/VS_Snippets_Wpf/XAMLOvwSupport/CSharp/page3.xaml#buttonwithcodebehind)]  
  
 [!code-csharp[XAMLOvwSupport#ButtonWithCodeBehindHandler](../../../../samples/snippets/csharp/VS_Snippets_Wpf/XAMLOvwSupport/CSharp/page3.xaml.cs#buttonwithcodebehindhandler)]
 [!code-vb[XAMLOvwSupport#ButtonWithCodeBehindHandler](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/XAMLOvwSupport/VisualBasic/Page1.xaml.vb#buttonwithcodebehindhandler)]  
  
 Beachten Sie, dass die Code\-Behind\-Datei den CLR\-Namespace `ExampleNamespace` verwendet und `ExamplePage` als partielle Klasse in diesem Namespace deklariert.  Dies entspricht dem `x:Class`\-Attributwert von `ExampleNamespace`.`ExamplePage`, der im Markupstamm bereitgestellt wurde.  Der WPF\-Markupcompiler erstellt für jede kompilierte XAML\-Datei eine partielle Klasse, indem er eine Klasse vom Stammelementtyp ableitet.  Wenn Sie Code\-Behind bereitstellen, der dieselbe partielle Klasse definiert, wird der resultierende Code im selben Namespace und in derselben Klasse der kompilierten Anwendung kombiniert.  
  
 Weitere Informationen zu den Anforderungen für die Code\-Behind\-Programmierung in WPF finden Sie im Abschnitt "Anforderungen für Code\-Behind, Ereignishandler und partielle Klassen" im Thema [Code\-Behind und XAML in WPF](../../../../docs/framework/wpf/advanced/code-behind-and-xaml-in-wpf.md).  
  
 Wenn Sie keine eigene Code\-Behind\-Datei erstellen möchten, können Sie den Code auch inline in einer XAML\-Datei erstellen.  Inlinecode ist jedoch eine weniger vielseitige Technik mit erheblichen Einschränkungen.  Weitere Informationen finden Sie unter [Code\-Behind und XAML in WPF](../../../../docs/framework/wpf/advanced/code-behind-and-xaml-in-wpf.md).  
  
### Routingereignisse  
 Ein bestimmtes Ereignisfeature, das für [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] wichtig ist, ist ein [Routingereignis](GTMT).  Mithilfe von Routingereignissen kann ein Element ein von einem anderen Element ausgelöstes Ereignis behandeln, vorausgesetzt, die Elemente sind über eine Strukturbeziehung miteinander verbunden.  Beim Angeben der Ereignisbehandlung mit einem XAML\-Attribut kann jedes Element nach dem Routingereignis lauschen, das in jedem Element behandelt werden kann, auch in Elementen, bei denen dieses spezielle Ereignis nicht in der Klassenmembertabelle aufgeführt ist.  Dies wird durch das Qualifizieren des Ereignisnamensattributs mit dem Namen der übergeordneten Klasse erzielt.  Das übergeordnete `StackPanel` im aktuellen `StackPanel`\/`Button`\-Beispiel kann beispielsweise einen Handler für das <xref:System.Windows.Controls.Primitives.ButtonBase.Click>\-Ereignis der Schaltfläche des untergeordneten Elements registrieren, indem er das `Button.Click`\-Attribut für das `StackPanel`\-Objektelement angibt, wobei der Handlername als Attributwert verwendet wird.  Weitere Informationen zur Funktion von Routingereignissen finden Sie unter [Übersicht über Routingereignisse](../../../../docs/framework/wpf/advanced/routed-events-overview.md).  
  
<a name="x_name_and_xaml_named_elements"></a>   
## Benannte XAML\-Elemente  
 Die Objektinstanz, die in einem Objektdiagramm durch die Verarbeitung eines XAML\-Objektelements erstellt wird, weist standardmäßig keinen eindeutigen Bezeichner oder Objektverweis auf.  Wenn Sie im Code einen Konstruktor aufrufen, verwenden Sie vielmehr fast immer das Konstruktorergebnis zum Festlegen einer Variablen auf die erstellte Instanz, sodass Sie später im Code auf die Instanz verweisen können.  Um standardisierten Zugriff auf Objekte bereitzustellen, die über eine Markupdefinition erstellt wurden, definiert XAML das [x:Name\-Attribut](../../../../docs/framework/xaml-services/x-name-directive.md).  Sie können den Wert des `x:Name`\-Attributs auf ein beliebiges Objektelement festlegen.  Im Code\-Behind entspricht der ausgewählte Bezeichner einer Instanzvariablen, die auf die erstellte Instanz verweist.  Benannte Elemente funktionieren in jeder Hinsicht wie Objektinstanzen \(der Name verweist auf diese Instanz\), und der Code\-Behind kann auf die benannten Elemente verweisen, um Laufzeitinteraktionen innerhalb der Anwendung zu behandeln.  Diese Verbindung zwischen Instanzen und Variablen wird durch den WPF\-XAML\-Markupcompiler erreicht und schließt insbesondere Funktionen und Muster wie <xref:System.Windows.Markup.IComponentConnector.InitializeComponent%2A> ein, die in diesem Thema nicht ausführlich erläutert werden.  
  
 XAML\-Elemente auf [WPF\-Frameworkebene](GTMT) erben eine <xref:System.Windows.FrameworkElement.Name%2A>\-Eigenschaft, die dem im `x:Name`\-Attribut definierten XAML entspricht.  Bestimmte andere Klassen stellen darüber hinaus auch Entsprechungen auf Eigenschaftenebene für `x:Name` bereit, das auch allgemein als `Name`\-Eigenschaft definiert ist.  Wenn in der Membertabelle für das ausgewählte Element bzw. den Typ keine `Name`\-Eigenschaft vorhanden ist, verwenden Sie stattdessen `x:Name`.  Die `x:Name`\-Werte stellen einen Bezeichner für ein XAML\-Element bereit, das zur Laufzeit verwendet werden kann, entweder durch bestimmte Subsysteme oder durch Hilfsmethoden wie <xref:System.Windows.FrameworkElement.FindName%2A>.  
  
 Im folgenden Beispiel wird <xref:System.Windows.FrameworkElement.Name%2A> auf ein <xref:System.Windows.Controls.StackPanel>\-Element festgelegt.  Dann verweist ein Handler in einer <xref:System.Windows.Controls.Button> innerhalb dieser <xref:System.Windows.Controls.StackPanel> über den vom <xref:System.Windows.FrameworkElement.Name%2A> festgelegten Instanzenverweis `buttonContainer` auf das <xref:System.Windows.Controls.StackPanel>.  
  
 [!code-xml[XAMLOvwSupport#NamedE](../../../../samples/snippets/csharp/VS_Snippets_Wpf/XAMLOvwSupport/CSharp/page7.xaml#namede)]  
[!code-xml[XAMLOvwSupport#NamedE2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/XAMLOvwSupport/CSharp/page7.xaml#namede2)]  
  
 [!code-csharp[XAMLOvwSupport#NameCode](../../../../samples/snippets/csharp/VS_Snippets_Wpf/XAMLOvwSupport/CSharp/page7.xaml.cs#namecode)]
 [!code-vb[XAMLOvwSupport#NameCode](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/XAMLOvwSupport/VisualBasic/Page1.xaml.vb#namecode)]  
  
 Der XAML\-Name für eine Instanz wird ebenso wie eine Variable durch einen Bereich bestimmt, sodass erzwungen werden kann, dass Namen in einem bestimmten vorhersehbaren Bereich eindeutig sind.  Das primäre Markup, das eine Seite definiert, gibt einen eindeutigen XAML\-Namensbereich an, wobei die Grenzen des XAML\-Namensbereichs dem Stammelement dieser Seite entsprechen.  Andere Markupquellen wie Formate oder Vorlagen in Formaten, können zur Laufzeit mit einer Seite interagieren. Markupquellen dieser Art verfügen häufig über eigene XAML\-Namensbereiche, die nicht unbedingt mit dem XAML\-Namensbereich der Seite in Verbindung stehen.  Weitere Informationen zu `x:Name` und XAML\-Namensbereichen finden Sie unter <xref:System.Windows.FrameworkElement.Name%2A>, [x:Name\-Direktive](../../../../docs/framework/xaml-services/x-name-directive.md) oder [WPF\-XAML\-Namescopes](../../../../docs/framework/wpf/advanced/wpf-xaml-namescopes.md).  
  
<a name="attached_properties_and_attached_events"></a>   
## Angefügte Eigenschaften und angefügte Ereignisse  
 XAML gibt eine Sprachfunktion an, mit der es möglich ist, bestimmte Eigenschaften oder Ereignisse für ein Element unabhängig davon anzugeben, ob die Eigenschaft oder das Ereignis in den Typdefinitionen für das Element vorhanden ist, für das die Eigenschaft festgelegt wird.  Die Eigenschaftenversion dieses Features wird als [angefügte Eigenschaft](GTMT) bezeichnet, die Ereignisversion als [angefügtes Ereignis](GTMT).  Im Prinzip können Sie sich angefügte Eigenschaften und Ereignisse als globale Member vorstellen, die auf ein XAML\-Element oder eine Objektinstanz festgelegt werden können.  Jedoch muss dieses Element bzw. diese Klasse oder eine größere Infrastruktur einen Unterstützungseigenschaftenspeicher für die angefügten Werte unterstützen.  
  
 Angefügte Eigenschaften in XAML werden in der Regel über die Attributsyntax verwendet.  In der Attributsyntax geben Sie eine angefügte Eigenschaft in der Form *Besitzertyp*.*Eigenschaftenname* an.  
  
 Oberflächlich betrachtet gleicht dies der Verwendung eines Eigenschaftenelements. In diesem Fall unterscheidet sich jedoch der angegebene *Besitzertyp* immer von dem Typ des Objektelements, auf das die angefügte Eigenschaft festgelegt wird.  *Besitzertyp* ist der Typ, der die Accessormethoden bereitstellt, die der XAML\-Prozessor benötigt, um den Wert der angefügten Eigenschaft abzurufen oder festzulegen.  
  
 Das typischste Szenario für angefügte Eigenschaften besteht darin, untergeordneten Elementen zu ermöglichen, dem übergeordneten Element einen Eigenschaftswert zu melden.  
  
 Im folgenden Beispiel wird die angefügte Eigenschaft <xref:System.Windows.Controls.DockPanel.Dock%2A?displayProperty=fullName> dargestellt.  Die <xref:System.Windows.Controls.DockPanel>\-Klasse definiert die Accessoren für <xref:System.Windows.Controls.DockPanel.Dock%2A?displayProperty=fullName> und besitzt deshalb die angefügte Eigenschaft.  Die <xref:System.Windows.Controls.DockPanel>\-Klasse enthält darüber hinaus auch die Logik, die die untergeordneten Elemente durchläuft und insbesondere die einzelnen Elemente auf den festgelegten Wert <xref:System.Windows.Controls.DockPanel.Dock%2A?displayProperty=fullName> überprüft.  Wenn ein Wert gefunden wird, wird dieser Wert bei der Anordnung der untergeordneten Elemente verwendet.  Die Verwendung der angefügten Eigenschaft <xref:System.Windows.Controls.DockPanel.Dock%2A?displayProperty=fullName> und diese Anordnungsmöglichkeit stellen die Motivation für die <xref:System.Windows.Controls.DockPanel>\-Klasse dar.  
  
 [!code-xml[XAMLOvwSupport#DockAP](../../../../samples/snippets/csharp/VS_Snippets_Wpf/XAMLOvwSupport/CSharp/page8.xaml#dockap)]  
  
 In [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] werden die meisten oder alle angefügten Eigenschaften auch als [Abhängigkeitseigenschaften](GTMT) implementiert.  Ausführliche Informationen finden Sie unter [Übersicht über angefügte Eigenschaften](../../../../docs/framework/wpf/advanced/attached-properties-overview.md).  
  
 Angefügte Ereignisse verwenden ein ähnliches Format der Attributsyntax von *Besitzertyp*.*Ereignisname*.  Wie bei nicht angefügten Ereignissen gibt der Attributwert für ein angefügtes Ereignis in XAML den Namen der Handlermethode an, die bei der Behandlung des Ereignisses im Element aufgerufen wird.  Angefügte Ereignisse werden in WPF\-XAML weniger häufig verwendet.  Weitere Informationen finden Sie unter [Übersicht über angefügte Ereignisse](../../../../docs/framework/wpf/advanced/attached-events-overview.md).  
  
<a name="base_classes_and_xaml"></a>   
## Basistypen und XAML  
 Zugrunde liegender WPF\-XAML\-Code und der zugehörige XAML\-Namespace stellen eine Auflistung von Typen dar, die [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)]\-Objekten sowie Markupelementen für XAML entsprechen.  Es können jedoch nicht alle Klassen Elementen zugeordnet werden.  Abstrakte Klassen wie <xref:System.Windows.Controls.Primitives.ButtonBase> und bestimmte nicht abstrakte Basisklassen werden im [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)]\-Objektmodell für die Vererbung verwendet.  Basisklassen, z. B. abstrakte Klassen, sind dennoch wichtig für die XAML\-Entwicklung, da jedes konkrete XAML\-Element Member von einer Basisklasse in der eigenen Hierarchie erbt.  Häufig enthalten diese Member Eigenschaften, die als Attribute für das Element festgelegt werden können, oder als Ereignisse, die behandelt werden können.  <xref:System.Windows.FrameworkElement> ist die konkrete [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]\-Basisklasse von [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] auf der [WPF\-Frameworkebene](GTMT).  Beim Entwerfen von [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] werden Sie verschiedene Form\-, Panel\-, Decorator\- oder Steuerelement\-Klassen verwenden, die alle vom <xref:System.Windows.FrameworkElement> abgeleitet werden.  Eine verwandte Klasse, <xref:System.Windows.FrameworkContentElement>, unterstützt für eine Flusslayoutdarstellung geeignete, dokumentorientierte Elemente und verwendet hierzu [!INCLUDE[TLA2#tla_api#plural](../../../../includes/tla2sharptla-apisharpplural-md.md)], die die [!INCLUDE[TLA2#tla_api#plural](../../../../includes/tla2sharptla-apisharpplural-md.md)] in <xref:System.Windows.FrameworkElement> explizit spiegeln.  Aufgrund der Kombination aus Attributen auf Elementebene und [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)]\-Objektmodell verfügen Sie über allgemeine Eigenschaften, die unabhängig vom spezifischen XAML\-Element und dem zugrunde liegenden Typ für die meisten konkreten XAML\-Elemente festgelegt werden können.  
  
<a name="xaml_security"></a>   
## XAML\-Sicherheit  
 XAML ist eine Markupsprache, die die Objektinstanziierung und \-Ausführung direkt darstellt.  Daher verfügen in XAML erstellte Elemente über dieselbe Fähigkeit, mit Systemressourcen \(z. B. Netzwerkzugriff, Dateisystemeingabe\/\-ausgabe\) zu interagieren, wie der entsprechend erstellte Code.  
  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] unterstützt das [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)]\-Sicherheitsframework [!INCLUDE[TLA#tla_cas](../../../../includes/tlasharptla-cas-md.md)].  Das bedeutet, dass in der Internetzone ausgeführter [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]\-Inhalt über eingeschränkte Berechtigungen zum Ausführen verfügt. "  Loose XAML" \(Seiten mit nicht kompiliertem XAML\-Code, der beim Laden von einem XAML\-Viewer interpretiert wird\) und [!INCLUDE[TLA#tla_xbap](../../../../includes/tlasharptla-xbap-md.md)] werden normalerweise in dieser Internetzone ausgeführt und verwenden dieselben Berechtigungen.  Wenn XAML\-Code in eine voll vertrauenswürdige Anwendung geladen wird, hat er denselben Zugriff auf die Systemressourcen wie die Hostanwendung.  Weitere Informationen finden Sie unter [WPF\-Sicherheit mit teilweiser Vertrauenswürdigkeit](../../../../docs/framework/wpf/wpf-partial-trust-security.md).  
  
<a name="loading_xaml_from_code"></a>   
## Laden von XAML aus Code  
 XAML kann zum Definieren der gesamten Benutzeroberfläche verwendet werden, eignet sich jedoch auch, um nur einen Teil der Benutzeroberfläche in XAML zu definieren.  Dadurch sind partielle Anpassungen, die lokale Speicherung von Informationen, die Verwendung von XAML zum Bereitstellen eines Geschäftsobjekts oder eine Reihe anderer möglicher Szenarien möglich.  Der Schlüssel zu diesen Szenarien ist die <xref:System.Windows.Markup.XamlReader>\-Klasse und die zugehörige <xref:System.Windows.Markup.XamlReader.Load%2A>\-Methode.  Als Eingabe dient eine XAML\-Datei und als Ausgabe ein Objekt, das die gesamte Laufzeitstruktur von Objekten darstellt, die über dieses Markup erstellt wurden.  Das Objekt kann dann als Eigenschaft eines anderen Objekts eingefügt werden, das in der Anwendung bereits vorhanden ist.  Vorausgesetzt, bei der Eigenschaft handelt es sich um eine geeignete Eigenschaft im Inhaltsmodell mit tatsächlichen Anzeigefunktionen, die das Ausführungsmodul benachrichtigt, wenn neuer Inhalt zur Anwendung hinzugefügt wurde, können Sie den Inhalt einer aktiven Anwendung sehr einfach ändern, indem Sie ihn in XAML laden.  Beachten Sie, dass diese Funktion aufgrund der offensichtlichen Sicherheitsrisiken beim Laden von Dateien in aktive Anwendungen im Allgemeinen nur in voll vertrauenswürdigen Anwendungen verfügbar ist.  
  
<a name="whats_next"></a>   
## Weitere Informationen  
 Dieses Thema enthält eine grundlegende Einführung in die Begriffe und die Terminologie der XAML\-Syntax in Bezug auf WPF.  Weitere Informationen zu den hier verwendeten Begriffen finden Sie unter [Ausführliche Erläuterung der XAML\-Syntax](../../../../docs/framework/wpf/advanced/xaml-syntax-in-detail.md).  
  
 Wenn Sie es noch nicht getan haben, bearbeiten Sie die Übungen im Lernprogramm unter dem Thema [Exemplarische Vorgehensweise: Erste Schritte mit WPF](../../../../docs/framework/wpf/getting-started/walkthrough-my-first-wpf-desktop-application.md).  Beim Erstellen der im Lernprogramm beschriebenen markupzentrierten Anwendung werden die zahlreichen, in diesem Thema beschriebenen Begriffe im Rahmen der Übungen vertieft.  
  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] verwendet ein bestimmtes Anwendungsmodell, das auf der <xref:System.Windows.Application>\-Klasse basiert.  Ausführlichere Informationen hierzu finden Sie unter [Übersicht über die Anwendungsverwaltung](../../../../docs/framework/wpf/app-development/application-management-overview.md).  
  
 Unter [Erstellen einer WPF\-Anwendung](../../../../docs/framework/wpf/app-development/building-a-wpf-application-wpf.md) finden Sie ausführlichere Informationen zum Erstellen von XAML\-Anwendungen über die Befehlszeile und mit [!INCLUDE[TLA#tla_visualstu](../../../../includes/tlasharptla-visualstu-md.md)].  
  
 [Übersicht über Abhängigkeitseigenschaften](../../../../docs/framework/wpf/advanced/dependency-properties-overview.md) enthält weitere Informationen zur Vielseitigkeit von Eigenschaften in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] sowie eine Einführung in das Konzept von [Abhängigkeitseigenschaften](GTMT).  
  
## Siehe auch  
 [Ausführliche Erläuterung der XAML\-Syntax](../../../../docs/framework/wpf/advanced/xaml-syntax-in-detail.md)   
 [XAML\- und benutzerdefinierte Klassen für WPF](../../../../docs/framework/wpf/advanced/xaml-and-custom-classes-for-wpf.md)   
 [Sprachfeatures des XAML\-Namespace \(x:\)](../../../../docs/framework/xaml-services/xaml-namespace-x-language-features.md)   
 [WPF\-XAML\-Erweiterungen](../../../../docs/framework/wpf/advanced/wpf-xaml-extensions.md)   
 [Übersicht über Basiselemente](../../../../docs/framework/wpf/advanced/base-elements-overview.md)   
 [Strukturen in WPF](../../../../docs/framework/wpf/advanced/trees-in-wpf.md)