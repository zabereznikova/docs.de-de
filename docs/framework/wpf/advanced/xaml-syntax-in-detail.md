---
title: "Ausführliche Erläuterung der XAML-Syntax"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- XML [WPF], namespaces
- XAML [WPF], parsing of attributes
- parsing of attributes [WPF]
- XAML [WPF], markup extensions
- attached properties [WPF]
- tag syntax [XAML]
- markup extensions [WPF]
- XAML [WPF], object element syntax
- XAML [WPF], syntax terminology
- attached events [WPF]
- lookup semantics [WPF]
- XAML [WPF], attached events
- XAML [WPF], content syntax
- XAML [WPF], lookup semantics
- content syntax [WPF]
- object element syntax [WPF]
- syntax terminology [XAML]
- XAML [WPF], attached properties
- attributes [XAML], parsing
- XAML [WPF], tag syntax
- XAML [WPF], attribute syntax
- property element syntax [WPF]
- terminology [XAML]
- namespaces [WPF], XML
- attribute syntax [XAML]
- XAML [WPF], property element syntax
ms.assetid: 67cce290-ca26-4c41-a797-b68aabc45479
caps.latest.revision: "26"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 0aa85c9ec6e6b911444b07a4169dc769ac4df816
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="xaml-syntax-in-detail"></a>Ausführliche Erläuterung der XAML-Syntax
In diesem Thema definiert die Begriffe, die verwendet werden, um die Elemente eines XAML-Syntax zu beschreiben. Diese Begriffe werden häufig in den restlichen Abschnitten dieser Dokumentation wird sowohl für WPF-Dokumentation verwendet, insbesondere und für die anderen Frameworks, die XAML-Code oder die Grundkonzepte von XAML-aktiviert, indem die Verwendung von XAML-sprachunterstützung auf der Ebene "System.xaml" verwenden. Dieses Thema baut auf die grundlegende Terminologie eingeführt, die im Thema [XAML Overview (WPF)](../../../../docs/framework/wpf/advanced/xaml-overview-wpf.md).  
  

  
<a name="the_xaml_language_specification"></a>   
## <a name="the-xaml-language-specification"></a>Der XAML-Sprachspezifikation  
 Die Verwendung von XAML-Syntax Terminologie, die hier definierten ist auch definiert, oder in der XAML-Sprachspezifikation verwiesen. XAML ist eine Programmiersprache, die auf XML basierendes und folgt oder XML-strukturellen Regeln erweitert. Einen Teil der Terminologie von freigegeben wird oder basiert auf der Terminologie, die häufig verwendet, wenn die XML-Sprache oder das XML-Document Object Model, beschreibt.  
  
 Weitere Informationen über die XAML-Sprachspezifikation herunterladen [ \[MS-XAML-\] ](http://go.microsoft.com/fwlink/?LinkId=114525) aus dem Microsoft Download Center.  
  
<a name="xaml_and_clr"></a>   
## <a name="xaml-and-clr"></a>Verwendung von XAML- und CLR  
 XAML ist eine Markupsprache. Die [!INCLUDE[TLA#tla_clr](../../../../includes/tlasharptla-clr-md.md)], als implizite nach seinem Namen, die Ausführung zur Laufzeit ermöglicht. XAML ist keiner allein allgemeine Sprachen, die direkt von der CLR-Laufzeit verwendet wird. Sie können stattdessen XAML als unterstützende eigene Typsystem vorstellen. Bestimmte XAML-Analysesystem, das von WPF verwendet wird, basiert auf der CLR und dem CLR-Typsystem. Für CLR-Typen für die eine Darstellung zur Laufzeit zu instanziieren, wenn die XAML für WPF analysiert wird, werden XAML-Typen zugeordnet. Aus diesem Grund umfasst der Rest der Erläuterung der Syntax in diesem Dokument Verweise auf die CLR-Typsystem, auch wenn die entsprechende Syntaxdiskussionen in der XAML-Sprachspezifikation keinen. (Pro Sprachebene-Spezifikation von XAML-konnte XAML-Typen zugeordnet werden alle anderen Typsystem, dem muss nicht in der CLR werden, aber die Erstellung und Verwendung von einem anderen XAML-Parser erforderlich.)  
  
#### <a name="members-of-types-and-class-inheritance"></a>Member von Typen und Klassenvererbung  
 Eigenschaften und Ereignisse, die als XAML-Member angezeigt ein [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Typ werden oft von Basistypen geerbt. Betrachten Sie beispielsweise die in diesem Beispiel: `<Button Background="Blue" .../>`. Die <xref:System.Windows.Controls.Control.Background%2A> Eigenschaft ist ein unmittelbar deklarierte Eigenschaft nicht auf die <xref:System.Windows.Controls.Button> -Klasse, würden Sie die Klassendefinition, Reflektionsergebnisse oder der Dokumentation zu betrachten. Stattdessen <xref:System.Windows.Controls.Control.Background%2A> wird von der Basisklasse geerbt <xref:System.Windows.Controls.Control> Klasse.  
  
 Die Klasse Vererbungsverhalten von [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] XAML-Elementen ist eine erhebliche Abweichung von einem Schema erzwungen Interpretation von XML-Markup. Klassenvererbung kann sehr komplex, insbesondere dann, wenn intermediate Basisklassen abstrakt sind oder wenn Schnittstellen beteiligt sind. Dies ist ein Grund, die der Satz von XAML-Elemente und die zulässigen Attribute schwierig ist, richtig und vollständig mit der Schematypen darstellen, die in der Regel für verwendet werden [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] Programmierung, z. B. DTD- oder XSD-Format. Ein weiterer Grund dafür ist, Erweiterbarkeit und typenzuordnung-Funktionen der XAML-Sprache selbst entgegen Vollständigkeit für alle festen Darstellung der zulässigen Typen und Member.  
  
<a name="object_element_syntax"></a>   
## <a name="object-element-syntax"></a>Objektelementsyntax  
 *Objekt Elementsyntax* ist die Verwendung von XAML-Markup-Syntax, die eine CLR-Klasse oder Struktur instanziiert, indem ein XML-Element zu deklarieren. Diese Syntax ähnelt die Syntax von anderen Markupsprachen z. B. HTML. Die Syntax der Object-Element beginnt mit einer linken spitzen Klammer (\<), gefolgt von der Typname der Klasse oder Struktur instanziierte sofort. NULL oder mehr Leerzeichen können folgen den vollständigen Typnamen und NULL oder mehr Attribute können ebenfalls deklariert werden, auf den Object-Element, mit der ein oder mehrere Leerzeichen Attribut Schriftartnamen = "Value"-Paar. Schließlich muss eine der folgenden "true" sein:  
  
-   Das Element und Tag müssen durch einen Schrägstrich (/), unmittelbar gefolgt von einem spitze Klammer rechts (>) geschlossen werden.  
  
-   Das öffnende Tag muss eine entsprechende schließende spitze Klammer (>) abgeschlossen werden. Andere Objektelemente, Eigenschaftenelemente oder innere Text kann das Starttag folgen. Genau welche Inhalte hier enthalten sein kann wird durch das Objektmodell des Elements in der Regel eingeschränkt. Das entsprechende schließende Tag für das Object-Element muss auch vorhanden sind, in die richtige Schachtelung und mit anderen öffnenden und schließenden Tags Paare ausgleichen.  
  
 XAML-Implementierung durch .NET hat es sich um einen Satz von Regeln, mit denen Objektelemente Typen, Attribute, Eigenschaften oder Ereignisse und XAML-Namespaces für CLR-Namespaces plus -Assembly zugeordnet. Für WPF und .NET Framework-XAML-Objektelemente [!INCLUDE[TLA#tla_net](../../../../includes/tlasharptla-net-md.md)] Typen in Assemblys verwiesen wird, und ordnen Sie die Attribute für Mitglieder dieser Typen. Wenn Sie einen CLR-Typ in XAML verweisen, haben Sie Zugriff auf die geerbten Member dieses Typs auch.  
  
 Im folgende Beispiel wird z. B. Syntax der Object-Element, die instanziiert eine neue Instanz der der <xref:System.Windows.Controls.Button> Klasse, und gibt auch an eine <xref:System.Windows.FrameworkElement.Name%2A> Attribut und einen Wert für dieses Attribut:  
  
 [!code-xaml[XAMLOvwSupport#SyntaxOE](../../../../samples/snippets/csharp/VS_Snippets_Wpf/XAMLOvwSupport/CSharp/Page1.xaml#syntaxoe)]  
  
 Das folgende Beispiel ist die Element-Objektsyntax, die auch die Verwendung von XAML-Inhaltseigenschaftensyntax enthält. Der innere Text enthaltenen wird verwendet, um das Festlegen der <xref:System.Windows.Controls.TextBox> XAML-Inhaltseigenschaft <xref:System.Windows.Controls.TextBox.Text%2A>.  
  
 [!code-xaml[XAMLOvwSupport#ThisIsATextBox](../../../../samples/snippets/csharp/VS_Snippets_Wpf/XAMLOvwSupport/CSharp/Page1.xaml#thisisatextbox)]  
  
### <a name="content-models"></a>Inhaltsmodelle  
 Eine Klasse unterstützt möglicherweise eine Verwendung als eine XAML-Objektelement im Hinblick auf die Syntax, aber dieses Element wird in einer Anwendung oder die Seite nur ordnungsgemäß, wenn er in einer erwarteten Position eines allgemeinen Modells oder einer allgemeinen Elementstruktur platziert wird. Z. B. eine <xref:System.Windows.Controls.MenuItem> sollte normalerweise nur als untergeordnetes Element platziert werden eine <xref:System.Windows.Controls.Primitives.MenuBase> abgeleitete Klasse wie z. B. <xref:System.Windows.Controls.Menu>. Modelle für bestimmte Elemente werden als Teil der Hinweise auf den Klassenseiten für Steuerelemente und andere dokumentiert Content [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Klassen, die als XAML-Elementen verwendet werden können.  
  
<a name="properties_of_object_elements"></a>   
## <a name="properties-of-object-elements"></a>Eigenschaften von Objektelementen  
 Eigenschaften in XAML werden durch eine Vielzahl von syntaxmöglichkeiten festgelegt. Die Syntax für eine bestimmte Eigenschaft verwendet werden kann, hängt basierend auf den zugrunde liegenden Typ Systemmerkmalen der Eigenschaft, die Sie festlegen.  
  
 Wenn Sie die Werte der Eigenschaften festlegen, fügen Sie Funktionen oder die Eigenschaften auf Objekte wie sie in der Laufzeit-Objektdiagramm vorhanden sind. Der Anfangszustand des erstellten Objekts aus einem Objektelement basiert auf dem Standardverhalten der Konstruktor. Die Anwendung wird in der Regel etwas anderes als eine Standardinstanz vollständig eines angegebenen Objekts verwendet.  
  
<a name="attribute_syntax_properties"></a>   
## <a name="attribute-syntax-properties"></a>Attributsyntax (Eigenschaften)  
 Die Attributsyntax ist die Verwendung von XAML-Markup-Syntax, die einen Wert für eine Eigenschaft legt fest, indem Sie ein Attribut auf einem vorhandenen Objektelement deklarieren. Der Attributname muss der CLR-Membername der Eigenschaft der Klasse übereinstimmen, die das relevante Objektelement sichert. Zuweisungsoperator (=) im Namen des Attributs folgt. Der Attributwert muss es sich um eine Zeichenfolge in Anführungszeichen eingeschlossen sein.  
  
> [!NOTE]
>  Sie können abwechselnde Anführungszeichen verwenden, um ein literales Anführungszeichen innerhalb eines Attributs zu platzieren. Beispielsweise können Sie einfache Anführungszeichen als Mittel um eine Zeichenfolge zu deklarieren, die ein doppeltes Anführungszeichen enthält. Ob Sie einfache oder doppelte Anführungszeichen verwenden, sollten Sie ein übereinstimmendes Paar für öffnende bzw. schließende Attributwertzeichenfolge verwenden. Es stehen auch Escapesequenzen oder andere Techniken für umgehungslösungen zeicheneinschränkungen, die von jeder bestimmten XAML-Syntax. Finden Sie unter [XML-Zeichenentitäten und XAML](../../../../docs/framework/xaml-services/xml-character-entities-and-xaml.md).  
  
 Um über Attributsyntax festgelegt werden, eine Eigenschaft muss öffentlich sein und muss beschreibbar sein. Der Wert der Eigenschaft in der Unterstützungstypsystem muss ein Werttyp sein, oder muss werden ein Verweistyp, der instanziiert werden kann oder auf einen XAML-Prozessor verweisen, wenn der Zugriff auf den entsprechenden Unterstützungstyp.  
  
 Das Ereignis, das als Namen des Attributs verwiesen wird muss öffentlich sein und einen öffentlichen Delegaten haben, für WPF XAML-Ereignisse.  
  
 Die Eigenschaft oder das Ereignis muss ein Member der Klasse oder Struktur, die von der enthaltenden Objektelement instanziiert wird.  
  
### <a name="processing-of-attribute-values"></a>Verarbeiten von Attributwerten  
 Der Zeichenfolgenwert, der innerhalb des öffnenden und schließenden Anführungszeichen enthalten, wird von einem XAML-Prozessor verarbeitet. Für Eigenschaften richtet sich das standardmäßige Verhalten bei der Verarbeitung durch den Typ des zugrunde liegenden CLR-Eigenschaft.  
  
 Der Attributwert wird ausgefüllt, indem eine der folgenden, durch diese Verarbeitungsreihenfolge verwenden:  
  
1.  Findet der XAML-Prozessor eine geschweifte Klammer oder ein Object-Element, das von abgeleitet ist <xref:System.Windows.Markup.MarkupExtension>, klicken Sie dann die referenzierten Markuperweiterung zuerst statt der Verarbeitung des Werts als Zeichenfolge ausgewertet wird, und das von der Markuperweiterung zurückgegebene Objekt dient als die Wert. In vielen Fällen wird das Objekt zurückgegeben, die für eine Markuperweiterung einen Verweis auf ein vorhandenes Objekt oder ein Ausdruck, der Auswertung bis zur Laufzeit verzögert, und ist kein neu instanziierten Objekt sein.  
  
2.  Wenn die Eigenschaft deklariert ist mit einem attributierten <xref:System.ComponentModel.TypeConverter>, oder der Werttyp der Eigenschaft deklariert ist mit einem attributierten <xref:System.ComponentModel.TypeConverter>der Zeichenfolgenwert des Attributs wird übermittelt, des Typkonverters eine Konvertierung Domänenmodells und der Konverter wird zurückgeben, eine neue Objektinstanz.  
  
3.  Es ist keine <xref:System.ComponentModel.TypeConverter>, eine direkte Konvertierung in den Eigenschaftentyp wird versucht. Dieser letzten Ebene handelt es sich um eine direkte Konvertierung der Parser systemeigenen Höchstwert zwischen den primitiven Typen von XAML-Sprache oder eine Überprüfung auf die Namen der benannten Konstanten in einer Enumeration (der Parser greift dann auf die entsprechenden Werte).  
  
#### <a name="enumeration-attribute-values"></a>Enumerationswerte-Attribut  
 Enumerationen in XAML werden systemintern durch Verwendung von XAML-Parser verarbeitet, und die Member einer Enumeration durch Angeben des Namens der Zeichenfolge eines der benannten Konstanten der Enumeration angegeben werden.  
  
 Ist für Attributwerts Enumerationswerte die Verhalten von systemeigene die Zeichenfolge der Attributwert zu verarbeiten, und lösen Sie ihn zu einer der Enumerationswerte. Geben Sie nicht die Enumeration im Format *Enumeration*. *Wert*, wie Sie im Code. Stattdessen geben Sie nur *Wert*, und *Enumeration* wird durch den Typ der Eigenschaft, die beim Festlegen des abgeleitet. Bei Angabe ein Attributs in der *Enumeration*. *Wert* Formular löst ordnungsgemäß.  
  
 Bei Flag-Enumerationen basiert auf das Verhalten der <xref:System.Enum.Parse%2A?displayProperty=nameWithType> Methode. Sie können mehrere Werte für eine Flag-Enumeration angeben, durch die einzelnen Werte durch ein Komma trennen. Sie können jedoch nicht Enumerationswerte kombiniert, die nicht Flag-Enumerationswerte. Beispielsweise können keine die Komma-Syntax versuchen, erstellen eine <xref:System.Windows.Trigger> , die auf mehrere Bedingungen für eine Enumeration des Attributwerts fungiert:  
  
```  
<!--This will not compile, because Visibility is not a flagwise enumeration.-->  
...  
<Trigger Property="Visibility" Value="Collapsed,Hidden">  
  <Setter ... />  
</Trigger>  
...  
```  
  
 Flag-Enumerationen, die Attribute unterstützen, die festlegbar in XAML werden selten in WPF. Eine solche Enumeration ist jedoch <xref:System.Windows.Media.StyleSimulations>. Sie können z. B. Attributsyntax durch Kommas getrennt verwenden, so ändern Sie das Beispiel in den Hinweisen für die <xref:System.Windows.Documents.Glyphs> Klasse. `StyleSimulations = "BoldSimulation"` werden `StyleSimulations = "BoldSimulation,ItalicSimulation"`. <xref:System.Windows.Input.KeyBinding.Modifiers%2A?displayProperty=nameWithType>ist eine andere Eigenschaft, in denen mehr als ein Enumerationswert angegeben werden können. Diese Eigenschaft geschieht jedoch ist ein Sonderfall, da die <xref:System.Windows.Input.ModifierKeys> Enumeration unterstützt einen eigene Typkonverter. Der Typkonverter für Modifizierer wird ein Pluszeichen (+) als ein Komma (,), anstatt ein Trennzeichen verwendet. Diese Konvertierung unterstützt die herkömmliche Syntax, um die Darstellung von Tastenkombinationen in Microsoft Windows-Programmierung, z. B. "Strg + Alt".  
  
### <a name="properties-and-event-member-name-references"></a>Eigenschaften und Ereignis Namen Elementverweise  
 Wenn Sie ein Attribut angeben, können Sie verweisen, jede Eigenschaft oder ein Ereignis, das als Mitglied der CLR-Typ vorhanden ist, den Sie für das enthaltende Objektelement instanziiert.  
  
 Oder Sie können eine angefügte Eigenschaft verweisen oder angefügtes Ereignis, unabhängig von der enthaltenden Object-Element. (Angefügte Eigenschaften werden in einem späteren Abschnitt erläutert.)  
  
 Sie können auch Namen jedes Ereignis aller Objekte, die über den Standardnamespace zugänglich mithilfe einer *TypeName*. *Ereignis* teilweise qualifizierten Namen; diese Syntax unterstützt, die Handler für Routingereignisse anfügen, in dem der Handler zum Behandeln von Ereignissen, die von untergeordneten Elementen, aber das übergeordnete Element routing vorgesehen ist auch keine Ereignis in der Tabelle für Mitglieder. Diese Syntax ähnelt der Syntax für eine angefügte Ereignisse, aber das Ereignis hier ist ein angefügtes Ereignis. Stattdessen sind Sie ein Ereignis mit einem qualifizierten Namen verweisen. Weitere Informationen finden Sie unter [Ereignisübersicht weitergeleitet](../../../../docs/framework/wpf/advanced/routed-events-overview.md).  
  
 Für einige Szenarien werden Eigenschaftennamen manchmal als der Wert eines Attributs, statt den Attributnamen bereitgestellt. Dieser Eigenschaftenname zählen auch Qualifizierer, z. B. im Format angegebene Eigenschaft *Besitzertyp*. *dependencyPropertyName angegebene Eigenschaft*. Dieses Szenario ist beim Schreiben von Stilen oder Vorlagen in XAML. Die Verarbeitungsregeln für Eigenschaftennamen als Attributwert angegeben unterscheiden und werden durch den Typ der Eigenschaft festgelegt wird oder durch die Verhaltensweisen Verarbeitungsregeln gesteuert. Weitere Informationen finden Sie unter [Erstellen von Formaten und Vorlagen](../../../../docs/framework/wpf/controls/styling-and-templating.md).  
  
 Eine weitere Verwendungsmöglichkeit für Eigenschaftennamen ist, wenn ein Attributwert eine Beziehung Eigenschaft beschreibt. Diese Funktion wird verwendet, für die Datenbindung und Storyboardziele und aktiviert ist, indem die <xref:System.Windows.PropertyPath> Klasse und dessen Typkonverter. Eine umfangreichere Beschreibung der Lookup-Semantik, finden Sie unter [die Verwendung von XAML-Syntax "PropertyPath"](../../../../docs/framework/wpf/advanced/propertypath-xaml-syntax.md).  
  
<a name="property_element_syntax"></a>   
## <a name="property-element-syntax"></a>Eigenschaftenelement-Syntax  
 *Eigenschaftenelementsyntax* ist eine Syntax, die gewissen von den allgemeinen XML-Syntaxregeln für Elemente Grad. Im XML-Code der Wert eines Attributs ist eine Zeichenfolge mit de facto, wobei der einzig möglichen Variante welche Codierung Zeichenfolgenformat verwendet wird. In XAML können Sie andere Objektelemente auf den Wert einer Eigenschaft zuweisen. Diese Funktion wird durch die Eigenschaftenelementsyntax aktiviert. Anstelle der Eigenschaft, die innerhalb der Element-Tag als Attribut angegeben wird, ist die Eigenschaft angegeben, unter Verwendung eines Elements öffnende tag im *Formular ElementTypeName*. *PropertyName* Form der Wert der Eigenschaft wird angegeben, in, und anschließend das Eigenschaftselement geschlossen ist.  
  
 Insbesondere die Syntax beginnt mit einer linken spitzen Klammer (\<), gefolgt von der Typname der Klasse oder Struktur, die die Eigenschaftenelementsyntax enthalten ist sofort. Sofort durch einen einzelnen Punkt (.), klicken Sie dann den Namen einer Eigenschaft klicken Sie dann eine entsprechende schließende spitze Klammer (>) darauf folgt. Wie bei der Attributsyntax, muss diese Eigenschaft in der deklarierte öffentliche Member des angegebenen Typs vorhanden sein. Der Wert der Eigenschaft zugewiesen werden soll, ist in der Property-Element enthalten. In der Regel der Wert als ein oder mehrere Objektelemente erhält, weil das angeben Objekte als Werte des Szenarios diese Eigenschaftenelementsyntax soll Adresse. Schließlich ein entsprechendes Endtag Angabe desselben *Formular ElementTypeName*. *PropertyName* Kombination muss angegeben werden, und in die richtige Schachtelung und der Lastenausgleich mit anderen Element-Tags.  
  
 Folgendes ist z. B. Eigenschaftenelementsyntax für die <xref:System.Windows.FrameworkElement.ContextMenu%2A> Eigenschaft eine <xref:System.Windows.Controls.Button>.  
  
 [!code-xaml[XAMLOvwSupport#ContextMenu](../../../../samples/snippets/csharp/VS_Snippets_Wpf/XAMLOvwSupport/CSharp/Page1.xaml#contextmenu)]  
  
 Der Wert in ein Eigenschaftenelement kann auch gegeben werden als innerer Text, der Eigenschaftentyp angegeben ist, einen primitiven Werttyp aufweist, wie z. B. <xref:System.String>, oder eine Enumeration, in dem ein Name angegeben ist. Diese zwei Verwendungen sind relativ selten, da es sich bei jedem dieser Fälle können auch eine einfachere Attributsyntax verwenden. Ein Szenario zum Ausfüllen ein Eigenschaftenelement mit einer Zeichenfolge, die für Eigenschaften, die für die Darstellung der Benutzeroberflächentext verwendet werden, sind nicht die Verwendung von XAML-Inhaltseigenschaft ist, und bestimmte leerzeichenelementen z. B. Zeilenvorschübe sind erforderlich, um in diesem Text angezeigt werden. Attributsyntax kann Zeilenvorschübe nicht beibehalten, aber Eigenschaftenelementsyntax kann, solange signifikante Leerräume beibehalten werden sollen aktiv ist (Weitere Informationen finden Sie unter [Leerstellenverarbeitung in XAML](../../../../docs/framework/xaml-services/whitespace-processing-in-xaml.md)). Ein weiteres Szenario ist, damit [X: Uid-Direktive](../../../../docs/framework/xaml-services/x-uid-directive.md) kann auf dem Eigenschaftselement angewendet werden und somit den Wert im kennzeichnen, wie ein Wert, der in der WPF lokalisiert werden soll BAML ausgeben oder andere Techniken.  
  
 Ein Eigenschaftenelement wird nicht in der logischen WPF-Struktur dargestellt. Ein Eigenschaftenelement ist lediglich eine bestimmte Syntax zum Festlegen einer Eigenschaft, und es ist kein Element, das eine Instanz oder ein Objekt, die gesichert wurde. (Ausführliche auf dem Konzept der logischen Struktur finden Sie unter [Strukturen in WPF](../../../../docs/framework/wpf/advanced/trees-in-wpf.md).)  
  
 Für Eigenschaften, in denen sowohl Attribute als auch Eigenschaft Elementsyntax unterstützt werden, haben zwei Syntaxarten in der Regel das gleiche Ergebnis, obwohl Besonderheiten z. B. zur Behandlung von Leerräumen leicht zwischen der Syntax variieren können.  
  
<a name="collection_syntax"></a>   
## <a name="collection-syntax"></a>Auflistungssyntax  
 Die XAML-Spezifikation erfordert Implementierungen von XAML-Prozessor zum Identifizieren von Eigenschaften, wobei der Wert einer Auflistung ist. Die allgemeine Implementierung der XAML-Prozessor in .NET basiert auf verwaltetem Code und der CLR, und es identifiziert Auflistungstypen über eine der folgenden:  
  
-   Geben Sie implementiert <xref:System.Collections.IList>.  
  
-   Geben Sie implementiert <xref:System.Collections.IDictionary>.  
  
-   Typ leitet sich von <xref:System.Array> (Weitere Informationen zu Arrays in XAML finden Sie unter [X: Array-Markuperweiterung](../../../../docs/framework/xaml-services/x-array-markup-extension.md).)  
  
 Wenn der Typ einer Eigenschaft eine Auflistung ist, klicken Sie dann muss der abgeleitete Auflistungstyp nicht in das Markup als Objektelement angegeben werden. Stattdessen werden die Elemente der Auflistung als ein oder mehrere untergeordnete Elemente des Eigenschaftenelements angegeben. Die einzelnen Elemente zu einem Objekt beim Laden von ausgewertet und der Auflistung hinzugefügt werden, indem die `Add` -Methode der impliziten Auflistung. Z. B. die <xref:System.Windows.Style.Triggers%2A> Eigenschaft <xref:System.Windows.Style> der speziellen Auflistungstyp <xref:System.Windows.TriggerCollection>, implementiert <xref:System.Collections.IList>. Es ist nicht erforderlich, beim Instanziieren einer <xref:System.Windows.TriggerCollection> Object-Element im Markup. Stattdessen geben Sie eine oder mehrere <xref:System.Windows.Trigger> als Elemente innerhalb der `Style.Triggers` Property-Element, in dem <xref:System.Windows.Trigger> (oder eine abgeleitete Klasse) ist der Typ als Elementtyp für die stark typisierte und implizite erwartete <xref:System.Windows.TriggerCollection>.  
  
 [!code-xaml[XAMLOvwSupport#SyntaxPECollection](../../../../samples/snippets/csharp/VS_Snippets_Wpf/XAMLOvwSupport/CSharp/Page1.xaml#syntaxpecollection)]  
  
 Eine Eigenschaft ist möglicherweise ein Sammlungstyp und die Verwendung von XAML-Inhaltseigenschaft für diesen Typ und die abgeleiteten Typen, die im nächsten Abschnitt dieses Themas wird erläutert.  
  
 Ein implizites Auflistungselement erstellt ein Element in der logischen strukturdarstellung, obwohl dies nicht in das Markup als ein Element angezeigt wird. In der Regel führt der Konstruktor des übergeordneten Typs die Instanziierung für die Auflistung, die eine seiner Eigenschaften wird sowie die anfänglich leere Auflistung wird Teil der Objektstruktur.  
  
> [!NOTE]
>  Die generische Liste und Wörterbuch-Schnittstellen (<xref:System.Collections.Generic.IList%601> und <xref:System.Collections.Generic.IDictionary%602>) werden zur Erkennung der Auflistung nicht unterstützt. Allerdings können Sie die <xref:System.Collections.Generic.List%601> Klasse als Basisklasse, da er implementiert <xref:System.Collections.IList> direkt oder <xref:System.Collections.Generic.Dictionary%602> als Basisklasse, da implementiert <xref:System.Collections.IDictionary> direkt.  
  
 In der .NET Referenzseiten für Auflistungstypen wird diese Syntax mit dem absichtlichen Weglassen der Object-Element für eine Sammlung gelegentlich als implizite Auflistungssyntax in den XAML-Syntaxabschnitten aufgeführt.  
  
 Mit Ausnahme von der "Root"-Element wird jedem Object-Element in einer XAML-Datei, die als untergeordnetes Element eines anderen Elements geschachtelt ist wirklich ein Element, das eine oder beide der folgenden Fälle ist: ein Mitglied einer impliziten Auflistungseigenschaft des übergeordneten Elements , oder ein Element, das den Wert der XAML-Inhaltseigenschaft für das übergeordnete Element (Verwendung von XAML-Inhalt Eigenschaften in einem späteren Abschnitt erläutert) angibt. Das heißt, die Beziehung zwischen übergeordneten und untergeordneten Elementen in einer Markupseite ist in Wirklichkeit ein einzelnes Objekt auf der Stammebene und jedes Objektelement unterhalb des Stamms ist entweder eine einzelne Instanz, die einen Eigenschaftswert des übergeordneten Elements bereitstellt, oder eines der Elemente innerhalb einer Spalte LEXIONSGRADE, die auch einen Eigenschaftswert von Typ "Auflistung" des übergeordneten Elements ist. Dieses Konzept Single-Root wird häufig mit XML und wird häufig im Verhalten von APIs, die z. B. Laden von XAML unterstützt <xref:System.Windows.Markup.XamlReader.Load%2A>.  
  
 Im folgende Beispiel wird eine Syntax, wobei das Object-Element für eine Auflistung (<xref:System.Windows.Media.GradientStopCollection>) explizit angegeben.  
  
```xaml  
<LinearGradientBrush>  
  <LinearGradientBrush.GradientStops>  
    <GradientStopCollection>  
      <GradientStop Offset="0.0" Color="Red" />  
      <GradientStop Offset="1.0" Color="Blue" />  
    </GradientStopCollection>  
  </LinearGradientBrush.GradientStops>  
</LinearGradientBrush>  
```  
  
 Beachten Sie, dass es nicht immer möglich, die die Auflistung explizit deklarieren. Versucht, z. B. deklarieren <xref:System.Windows.TriggerCollection> explizit in die oben <xref:System.Windows.Style.Triggers%2A> Beispiel fehlschlagen. Explizit deklarieren der auflistungs muss einen Standardkonstruktor unterstützen die Auflistungsklasse und <xref:System.Windows.TriggerCollection> nicht über einen Standardkonstruktor verfügen.  
  
<a name="xaml_content_properties"></a>   
## <a name="xaml-content-properties"></a>XAML-Inhaltseigenschaften  
 Verwendung von XAML-Inhalt ist eine Syntax, die nur für Klassen aktiviert ist, die angeben, die <xref:System.Windows.Markup.ContentPropertyAttribute> als Teil der Klassendeklaration. Die <xref:System.Windows.Markup.ContentPropertyAttribute> verweist auf den Namen der Eigenschaft, die die Inhaltseigenschaft für diesen Typ des Elements (einschließlich der abgeleiteten Klassen) ist. Wenn von einem XAML-Prozessor verarbeitet werden, wird untergeordneten Elemente oder innere Text, die zwischen dem Start- und Endtags des Objektelements gefunden werden als der Wert der Verwendung von XAML-Inhaltseigenschaft für dieses Objekt zugewiesen. Sie sind berechtigt, explizite Eigenschaftenelemente für die Content-Eigenschaft angeben, aber diese Verwendung ist nicht in der Regel in den XAML-Syntaxabschnitten in der Referenz zu .NET angezeigt. Die explizite/verbose Technik ist aus Gründen der Übersichtlichkeit Markup oder als Markup stilistischen gelegentliche Wert, aber die Absicht der Content-Eigenschaft in der Regel ist, um das Markup zu optimieren, damit Elemente, die als über-/ intuitiv beziehen direkt geschachtelt werden können. Eigenschaftselementtags für andere Eigenschaften eines Elements werden nicht als "Inhalt" pro eine strikte XAML-Sprachendefinition; zugewiesen. Sie werden in der Verwendung von XAML-Parser Verarbeitungsreihenfolge von Artikeln zuvor verarbeitet und gelten nicht als "Inhalt" sein.  
  
### <a name="xaml-content-property-values-must-be-contiguous"></a>Verwendung von XAML-Inhaltseigenschaftenwerte müssen zusammenhängend sein.  
 Der Wert von einem XAML-Inhaltseigenschaft muss entweder vor oder nach anderen Eigenschaftenelementen vollständig für das Objektelement zugewiesen werden. Dies gilt, ob der Wert von einem XAML-Inhaltseigenschaft als Zeichenfolge oder als ein oder mehrere Objekte angegeben wird. Beispielsweise wird das folgende Markup nicht analysiert werden:  
  
```  
<Button>I am a   
  <Button.Background>Blue</Button.Background>  
  blue button</Button>  
```  
  
 Dies ist im Wesentlichen nicht zulässig, da die Inhaltseigenschaft zweimal festgelegt werden, wenn diese Syntax explizite vorgenommen wurden mithilfe der Eigenschaftenelementsyntax für die Content-Eigenschaft, würden:  
  
```xml  
<Button>  
  <Button.Content>I am a </Button.Content>  
  <Button.Background>Blue</Button.Background>  
  <Button.Content> blue button</Button.Content>  
</Button>  
```  
  
 Ein Beispiel für die auf ähnliche Weise ungültig ist, wenn die Content-Eigenschaft eine Sammlung ist, und untergeordnete Elemente mit Eigenschaftenelemente vermischt werden:  
  
```xml  
<StackPanel>  
  <Button>This example</Button>  
  <StackPanel.Resources>  
    <SolidColorBrush x:Key="BlueBrush" Color="Blue"/>  
  </StackPanel.Resources>  
  <Button>... is illegal XAML</Button>  
</StackPanel>  
```  
  
<a name="content_properties_and_collection_syntax_combined"></a>   
## <a name="content-properties-and-collection-syntax-combined"></a>Inhaltseigenschaften und Auflistungssyntax in Kombination  
 Damit angenommen muss der Typ der Inhaltseigenschaft mehr als ein einzelnes Objektelement als Inhalt, insbesondere einen Sammlungstyp. Ähnlich wie bei Eigenschaftenelementsyntax für Auflistungstypen, muss ein XAML-Prozessor Typen als Auflistungstypen identifizieren. Wenn ein Element eine Verwendung von XAML-Inhaltseigenschaft weist und der Typ der Verwendung von XAML-Inhaltseigenschaft eine Sammlung ist, der implizite Auflistungstyp muss nicht in das Markup als Objektelement angegeben werden, und die Verwendung von XAML-Inhaltseigenschaft muss nicht als eine Eigenschaft in der Ereignisliste angegeben werden. Ement. Aus diesem Grund haben die offensichtliche Inhaltsmodell im Markup jetzt mehr als ein untergeordnetes Element als Inhalt zugewiesen. Im folgenden finden Sie Inhalt Syntax für eine <xref:System.Windows.Controls.Panel> abgeleitete Klasse. Alle <xref:System.Windows.Controls.Panel> abgeleitete Klassen herstellen, die Verwendung von XAML-Inhaltseigenschaft-Umfang <xref:System.Windows.Controls.Panel.Children%2A>, wofür einen Wert vom Typ <xref:System.Windows.Controls.UIElementCollection>.  
  
 [!code-xaml[XAMLOvwSupport#SyntaxContent](../../../../samples/snippets/csharp/VS_Snippets_Wpf/XAMLOvwSupport/CSharp/page5.xaml#syntaxcontent)]  
  
 Beachten Sie, dass weder das Eigenschaftselement für <xref:System.Windows.Controls.Panel.Children%2A> noch das Element für die <xref:System.Windows.Controls.UIElementCollection> in das Markup erforderlich ist. Dies ist ein Feature Entwurf von XAML, sodass rekursiv Elemente enthalten, die definieren, eine [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] sind intuitiver dargestellt als eine Struktur mit geschachtelten Elementen mit den unmittelbar übergeordneten und untergeordneten-Element-Beziehungen ohne dazwischen liegenden Elementtags für die Eigenschaft oder Auflistungsobjekten. In der Tat <xref:System.Windows.Controls.UIElementCollection> nicht explizit angegeben werden im Markup als Element eines Objektelements entwurfsbedingt. Da die einzige vorgesehene Verwendung als eine implizite Auflistung ist <xref:System.Windows.Controls.UIElementCollection> macht sich nicht auf einen öffentlichen Standardkonstruktor und daher nicht als Objektelement instanziiert werden.  
  
### <a name="mixing-property-elements-and-object-elements-in-an-object-with-a-content-property"></a>Das Mischen von Eigenschaftenelemente und Objektelemente in einem Objekt mit der Content-Eigenschaft  
 Die XAML-Spezifikation deklariert, dass ein XAML-Prozessor erzwingen kann, dass Objektelemente, mit denen die Verwendung von XAML-Inhaltseigenschaft in einem Objektelement ausfüllen zusammenhängend sein müssen und nicht gemischt werden müssen. Diese Einschränkung Eigenschaftenelementen Eigenschaftenelemente und Inhalt wird erzwungen, indem die [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] XAML-Prozessoren.  
  
 Sie können ein untergeordnetes Objektelement als erstes unmittelbares Markup in einem Objektelement verwenden. Dann können Sie Eigenschaftenelemente einführen. Oder Sie können eine oder mehrere Eigenschaftenelemente auf Inhalt und dann weitere Eigenschaftenelemente angeben. Aber nach ein Eigenschaftenelement Inhalt folgt, Sie können keine weiteren Inhalte einführen, Eigenschaftenelemente können nur hinzugefügt werden.  
  
 Dieser Inhalt / Eigenschaft Element Reihenfolge Anforderung gilt nicht für innere Text als Inhalt verwendet. Es ist jedoch weiterhin einen guten Markup-Stil für innere Text zusammenhängend aufbewahren, da signifikante Leerräume nur schwer zu visuell im Markup erkennen, wenn Eigenschaftenelemente mit innerem Text kombiniert werden.  
  
<a name="xaml_namespaces"></a>   
## <a name="xaml-namespaces"></a>XAML-Namespaces  
 Keines der vorangehenden Syntaxbeispiele angegeben einen XAML-Namespace als dem XAML-Standardnamespace. In typischen [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Anwendungen, die standardmäßigen XAML-Namespace wird angegeben, werden die [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Namespace. Sie können angeben von XAML-Namespaces außer dem XAML-Standardnamespace und weiterhin eine ähnliche Syntax verwenden. Klicken Sie dann eine beliebige Stelle, in dem eine Klasse mit dem Namen, die nicht innerhalb der standardmäßigen XAML-Namespace zugegriffen werden kann, Klassenname muss werden steht aber mit dem Präfix des XAML-Namespace als auf den entsprechenden CLR-Namespace zugeordnet. Beispielsweise `<custom:Example/>` ist Objekt Elementsyntax zum Instanziieren einer Instanz von der `Example` -Klasse, wobei der CLR-Namespace, die mit dieser Klasse (und möglicherweise die externe Assembly-Informationen, die Unterstützungstypen enthalten) zuvor zugeordnet wurde die `custom` Präfix.  
  
 Weitere Informationen zur Verwendung von XAML-Namespaces finden Sie unter [XAML-Namespaces und Namespace-Zuordnung für WPF-XAML](../../../../docs/framework/wpf/advanced/xaml-namespaces-and-namespace-mapping-for-wpf-xaml.md).  
  
<a name="markup_extensions"></a>   
## <a name="markup-extensions"></a>Markuperweiterungen  
 XAML-Code definiert eine Markuperweiterung, die Entität, die einem Escapezeichen über die normale Verwendung von XAML-Prozessor Behandlung zeichenfolgenattributwerten oder Objektelemente ermöglicht und verzögert die Verarbeitung in eine Sicherungsklasse programmieren. Das Zeichen, das eine Markuperweiterung für eine XAML-Prozessor identifiziert, wenn mithilfe der Attributsyntax der öffnenden geschweiften Klammer ({}), gefolgt von einem Zeichen, eine schließende geschweifte Klammer (}) ist. Die erste Zeichenfolge, die nach der öffnenden geschweiften Klammer muss die Klasse verweisen, die das Erweiterungsverhalten der bestimmten, in dem die Teilzeichenfolge der Verweis weggelassen werden kann "Extension" bereitstellt, wenn diese Teilzeichenfolge Bestandteil des Klassennamens "true" ist. Danach kann ein einzelnes Leerzeichen angezeigt, und klicken Sie dann jedes nachfolgende Zeichen dient als Eingabe durch die Implementierung, bis die schließende geschweifte Klammer gefunden wird.  
  
 Die .NET XAML-Implementierung verwendet die <xref:System.Windows.Markup.MarkupExtension> abstrakte Klasse als Basis für alle Markuperweiterungen von unterstützten [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] sowie andere Frameworks oder Technologien. Markuperweiterungen, [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] speziell implementiert werden häufig für das bieten eine Möglichkeit, um auf andere vorhandene Objekte zu verweisen oder verzögerte Verweise auf Objekte zu erstellen, die zur Laufzeit ausgewertet werden soll. Eine einfache WPF-Datenbindung erfolgt z. B. durch Angeben der `{Binding}` Markuperweiterung anstelle des Werts, der eine bestimmte Eigenschaft in der Regel in Anspruch nehmen würde. Viele der WPF-Markuperweiterungen ermöglichen eine Attributsyntax für Eigenschaften, was andernfalls nicht möglich wäre. Angenommen, ein <xref:System.Windows.Style> Objekt ist eine relativ komplexe Typ, der eine geschachtelte Reihe von Objekten und Eigenschaften enthält. Stile in WPF werden in der Regel definiert, als Ressource in einer <xref:System.Windows.ResourceDictionary>, und klicken Sie dann auf die verwiesen wird durch eine der beiden Markuperweiterungen WPF, das Anfordern einer Ressource. Die Markuperweiterung stellt die Auswertung des Eigenschaftswerts in eine Ressourcensuche zurück und ermöglicht die Bereitstellung von der <xref:System.Windows.FrameworkElement.Style%2A> -Eigenschaft, wobei der Typ <xref:System.Windows.Style>in Attributsyntax wie im folgenden Beispiel gezeigt:  
  
 `<Button Style="{StaticResource MyStyle}">My button</Button>`  
  
 Hier `StaticResource` identifiziert die <xref:System.Windows.StaticResourceExtension> -Klasse, die die Implementierung der Markuperweiterung bereitstellt. Die nächste Zeichenfolge `MyStyle` dient als Eingabe für den nicht standardmäßigen <xref:System.Windows.StaticResourceExtension> -Konstruktor, der Parameter aus der Erweiterungszeichenfolge, in dem der angeforderte deklariert <xref:System.Windows.ResourceKey>. `MyStyle`wird erwartet die [X: Key](../../../../docs/framework/xaml-services/x-key-directive.md) Wert, der eine <xref:System.Windows.Style> als Ressource definiert. Die [StaticResource Markuperweiterung](../../../../docs/framework/wpf/advanced/staticresource-markup-extension.md) Verwendung fordert an, dass die Ressource verwendet werden, um bereitzustellen der <xref:System.Windows.Style> Eigenschaftswert über die statische Suche Logik zur Ladezeit.  
  
 Weitere Informationen über Markuperweiterungen finden Sie unter [Markuperweiterungen und WPF XAML](../../../../docs/framework/wpf/advanced/markup-extensions-and-wpf-xaml.md). Eine Referenz zu Markuperweiterungen und anderen XAML-Programmierfeatures, die in der allgemeinen .NET XAML-Implementierung aktiviert, finden Sie unter [XAML-Namespace ("x:") Sprachfunktionen](../../../../docs/framework/xaml-services/xaml-namespace-x-language-features.md). WPF-spezifische Markuperweiterungen finden Sie unter [WPF-XAML-Erweiterungen](../../../../docs/framework/wpf/advanced/wpf-xaml-extensions.md).  
  
<a name="attached_properties"></a>   
## <a name="attached-properties"></a>Angefügte Eigenschaften  
 Angefügte Eigenschaften sind ein Programmierkonzept eingeführt, die in XAML, bei dem können Eigenschaften im Besitz und durch einen bestimmten Typ, definiert, aber als Attribute oder Eigenschaftenelemente für beliebige Elemente festgelegt. Das Hauptszenario für angefügte Eigenschaften bestimmt sind untergeordnete Elemente in einer Markupstruktur, um Informationen an ein übergeordnetes Element aktivieren, ohne dass ein umfassendes gemeinsam genutztes Objektmodell über alle Elemente ist. Umgekehrt können angefügte Eigenschaften von übergeordneten Elementen, um Informationen zu melden, untergeordnete Elemente verwendet werden. Weitere Informationen zu den Zweck der angefügte Eigenschaften und Gewusst wie: Erstellen eigener angefügte Eigenschaften, finden Sie unter [Eigenschaftenübersicht angefügt](../../../../docs/framework/wpf/advanced/attached-properties-overview.md).  
  
 Angefügte Eigenschaften verwenden eine Syntax ähnelt der Eigenschaftenelementsyntax, oberflächlich betrachtet, da Sie auch angeben einer *TypeName*. *PropertyName* Kombination. Es gibt zwei wichtige Unterschiede:  
  
-   Sie können die *TypeName*. *PropertyName* Kombination, selbst wenn eine angefügte Eigenschaft mittels Attributsyntax festlegen. Angefügte Eigenschaften sind der einzige Fall, qualifizieren den Namen der Eigenschaft in der Attributsyntax erforderlich ist.  
  
-   Sie können auch Eigenschaftenelementsyntax für angefügte Eigenschaften. Bei typischen Eigenschaftenelementsyntax, jedoch die *TypeName* Sie angeben, ist das Object-Element, das die Property-Element enthält. Wenn Sie auf eine angefügte Eigenschaft verwiesen werden und dann die *TypeName* Klasse, die die angefügte Eigenschaft, die nicht dem enthaltenden Object-Element definiert ist.  
  
<a name="attached_events"></a>   
## <a name="attached-events"></a>Angefügte Ereignisse  
 Angefügte Ereignisse sind eine andere Programmierkonzept eingeführt, die in XAML können Ereignisse eines bestimmten Typs definiert werden, wobei ein Handler für jedes Objektelement angefügt werden. In der Implementierung der Routingereignisalias häufig wird des Typs, der ein angefügtes Ereignis definiert ein statischer Typ, der einen Dienst definiert, und in einigen Fällen sind diese angefügte Ereignisse eines Routingereignisses Alias in Typen, die den Dienst verfügbar machen verfügbar. Handler für angefügte Ereignisse werden durch die Attributsyntax festgelegt. Mit angefügte Ereignisse die Attributsyntax für angefügte Ereignisse können erweitert ist eine *TypeName*. *Ereignisname* Verwendung ",", in dem *TypeName* ist die Klasse, die eine `Add` und `Remove` Ereignisaccessoren der Handler für das angefügte Ereignisinfrastruktur und *EventName* ist der Name des Ereignisses.  
  
<a name="anatomy_of_a_xaml_page_root_element"></a>   
## <a name="anatomy-of-a-xaml-root-element"></a>Aufbau eines XAML-Stammelement  
 Die folgende Tabelle zeigt eine typische XAML-Stammelement unterteilt, die spezifischen Attribute des Root-Element angezeigt:  
  
|||  
|-|-|  
|`<Page`|Object-Element des Stammelements öffnen|  
|`xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"`|Die Standardeinstellung ([!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]) XAML-Namespace|  
|`xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"`|XAML-Namespace der XAML-Sprache|  
|`x:Class="ExampleNamespace.ExampleCode"`|Die Deklaration der partiellen Klasse die Herstellung der Code-Behind Markup für die partielle Klasse definiert|  
|`>`|Ende der Object-Element für den Stammknoten. Objekt ist noch nicht geschlossen, da das Element untergeordnete Elemente enthält.|  
  
<a name="optional_and_nonrecommended_xaml_usages"></a>   
## <a name="optional-and-nonrecommended-xaml-usages"></a>Dies ist optional und Konfigurationswerts XAML-Verwendungen  
 Die folgenden Abschnitte beschreiben die XAML-Verwendungen, die technisch von XAML-Prozessoren unterstützt, aber erzeugt Ausführlichkeit oder andere Layoutgründen Probleme, die sich möglicherweise mit XAML-Dateien, die verbleibenden lesbare, wenn, Ihre Anwendungen entwickeln, die Verwendung von XAML-Quellen enthalten .  
  
### <a name="optional-property-element-usages"></a>Optionale Eigenschaftenelementen  
 Optionale Eigenschaftenelementen gehört, explizit schreiben Inhaltseigenschaften Element, dass die Verwendung von XAML-Prozessor als implizit behandelt. Wenn Sie z. B. den Inhalt der deklarieren eine <xref:System.Windows.Controls.Menu>, wahlweise konnten Sie explizit deklarieren die <xref:System.Windows.Controls.ItemsControl.Items%2A> Auflistung von der <xref:System.Windows.Controls.Menu> als eine `<Menu.Items>` Eigenschaftstag-Element, und platzieren jeweils <xref:System.Windows.Controls.MenuItem> innerhalb `<Menu.Items>`, anstelle als die Verwendung der impliziten XAML-Prozessor-Verhaltens, die alle untergeordneten Elemente des eine <xref:System.Windows.Controls.Menu> muss ein <xref:System.Windows.Controls.MenuItem> und befinden sich der <xref:System.Windows.Controls.ItemsControl.Items%2A> Auflistung. In einigen Fällen können optionale Verwendungen um der Objektstruktur visuell zu verdeutlichen, wie im Markup dargestellt. Oder manchmal ein expliziter Eigenschaftenelementen Markup, das jedoch visuell verwirrend ist, z. B. verschachtelte Markuperweiterungen in einem Attributwert technisch funktionsfähig ist, vermeiden kann.  
  
### <a name="full-typenamemembername-qualified-attributes"></a>Vollständige typeName.memberName qualifizierte Attribute  
 Die *TypeName*. *MemberName* Formular für ein Attribut tatsächlich mehr universell als nur den Routingereignis Fall funktioniert. Aber in anderen Situationen, die dieses Formular ist überflüssig, und vermeiden Sie es, wenn nur aus Gründen der Markup-Stil und Lesbarkeit. Im folgenden Beispiel führt jeder der drei Verweise auf die <xref:System.Windows.Controls.Control.Background%2A> Attribut vollständig gleichwertig:  
  
 [!code-xaml[XAMLOvwSupport#TypeNameProp](../../../../samples/snippets/csharp/VS_Snippets_Wpf/XAMLOvwSupport/CSharp/page8.xaml#typenameprop)]  
  
 `Button.Background`funktioniert, da die qualifizierte Suche für diese Eigenschaft auf <xref:System.Windows.Controls.Button> ist erfolgreich (<xref:System.Windows.Controls.Control.Background%2A> wurde vom Steuerelement geerbt) und <xref:System.Windows.Controls.Button> ist die Klasse der Object-Element oder eine Basisklasse. `Control.Background`funktioniert, da die <xref:System.Windows.Controls.Control> Klasse tatsächlich definiert <xref:System.Windows.Controls.Control.Background%2A> und <xref:System.Windows.Controls.Control> ist eine <xref:System.Windows.Controls.Button> Basisklasse.  
  
 Allerdings die folgenden *TypeName*. *MemberName* Formular Beispiel funktioniert nicht und wird kommentiert:  
  
 [!code-xaml[XAMLOvwSupport#TypeNameBadProp](../../../../samples/snippets/csharp/VS_Snippets_Wpf/XAMLOvwSupport/CSharp/page8.xaml#typenamebadprop)]  
  
 <xref:System.Windows.Controls.Label>ist eine andere abgeleitete Klasse von <xref:System.Windows.Controls.Control>, und wenn Sie angegeben hatten `Label.Background` innerhalb einer <xref:System.Windows.Controls.Label> Object-Element, diese Art der Verwendung würde gearbeitet haben. Allerdings da <xref:System.Windows.Controls.Label> hat nicht die Klasse oder die Basisklasse von <xref:System.Windows.Controls.Button>, das angegebene Verhalten der XAML-Prozessor wird anschließend verarbeitet `Label.Background` als angefügte Eigenschaft. `Label.Background`ist keine verfügbaren angefügten Eigenschaft, und diese Verwendung schlägt fehl.  
  
### <a name="basetypenamemembername-property-elements"></a>baseTypeName.memberName Eigenschaftenelemente  
 Auf analoge Weise, wie die *TypeName*. *MemberName* für die Attributsyntax, funktioniert die Form einer *Basistypname*. *MemberName* Syntax für Eigenschaftenelementsyntax funktioniert. Beispielsweise gilt die folgende Syntax:  
  
 [!code-xaml[XAMLOvwSupport#GoofyPE](../../../../samples/snippets/csharp/VS_Snippets_Wpf/XAMLOvwSupport/CSharp/page8.xaml#goofype)]  
  
 Hier die Property-Element angegeben wurde, als `Control.Background` , obwohl das Eigenschaftselement in enthalten war `Button`.  
  
 Aber wie *TypeName*. *MemberName* Form der Attribute, *Basistypname*. *MemberName* ist schlecht Format im Markup und sollte nicht verwendet werden.  
  
## <a name="see-also"></a>Siehe auch  
 [Übersicht über XAML (WPF)](../../../../docs/framework/wpf/advanced/xaml-overview-wpf.md)  
 [Sprachfunktionen des XAML-Namespace (x:)](../../../../docs/framework/xaml-services/xaml-namespace-x-language-features.md)  
 [WPF-XAML-Erweiterungen](../../../../docs/framework/wpf/advanced/wpf-xaml-extensions.md)  
 [Übersicht über Abhängigkeitseigenschaften](../../../../docs/framework/wpf/advanced/dependency-properties-overview.md)  
 [TypeConverter und XAML](../../../../docs/framework/wpf/advanced/typeconverters-and-xaml.md)  
 [XAML- und benutzerdefinierte Klassen für WPF](../../../../docs/framework/wpf/advanced/xaml-and-custom-classes-for-wpf.md)
