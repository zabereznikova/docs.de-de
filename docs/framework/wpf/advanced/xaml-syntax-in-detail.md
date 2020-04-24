---
title: Ausführliche Erläuterung der XAML-Syntax
ms.date: 03/30/2017
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
ms.openlocfilehash: 5f8bb862ce443fd7397036b10f69cda65a6960bc
ms.sourcegitcommit: 62285ec11fa8e8424bab00511a90760c60e63c95
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/20/2020
ms.locfileid: "81646144"
---
# <a name="xaml-syntax-in-detail"></a>Ausführliche Erläuterung der XAML-Syntax
In diesem Thema werden die Begriffe definiert, die zum Beschreiben der Elemente der XAML-Syntax verwendet werden. Diese Begriffe werden häufig in der restlichen Dokumentation verwendet, sowohl für die WPF-Dokumentation als auch für die anderen Frameworks, die XAML verwenden, oder für die grundlegenden XAML-Konzepte, die durch die XAML-Sprachunterstützung auf System.Xaml-Ebene aktiviert werden. In diesem Thema wird die grundlegende Terminologie erläutert, die im Thema [XAML-Übersicht (WPF)](../../../desktop-wpf/fundamentals/xaml.md)vorgestellt wurde.  

<a name="the_xaml_language_specification"></a>
## <a name="the-xaml-language-specification"></a>Die XAML-Sprachspezifikation  
 Die hier definierte XAML-Syntaxterminologie wird auch in der XAML-Sprachspezifikation definiert oder referenziert. XAML ist eine auf XML basierende Sprache, die XML-Strukturregeln folgt oder erweitert. Ein Teil der Terminologie wird von der Terminologie gemeinsam genutzt oder basiert auf der Terminologie, die häufig bei der Beschreibung der XML-Sprache oder des XML-Dokumentobjektmodells verwendet wird.  
  
 Weitere Informationen zur XAML-Sprachspezifikation [ \[finden\] ](https://download.microsoft.com/download/0/A/6/0A6F7755-9AF5-448B-907D-13985ACCF53E/[MS-XAML].pdf) Sie im Microsoft Download Center.  
  
<a name="xaml_and_clr"></a>
## <a name="xaml-and-clr"></a>XAML und CLR  
 XAML ist eine Markupsprache. Die Common Language Runtime (CLR), wie durch ihren Namen impliziert, ermöglicht die Laufzeitausführung. XAML ist für sich genommen keine der gängigen Sprachen, die direkt von der CLR-Laufzeit verwendet werden. Stattdessen können Sie sich XAML als Unterstützung eines eigenen Typsystems vorstellen. Das spezielle XAML-Analysesystem, das von WPF verwendet wird, basiert auf der CLR und dem CLR-Typsystem. XAML-Typen werden CLR-Typen zugeordnet, um eine Laufzeitdarstellung zu instanziieren, wenn das XAML für WPF analysiert wird. Aus diesem Grund enthält der Rest der Diskussion über Syntax in diesem Dokument Verweise auf das CLR-Typsystem, auch wenn die entsprechenden Syntaxdiskussionen in der XAML-Sprachspezifikation dies nicht tun. (Gemäß der XAML-Sprachspezifikationsstufe können XAML-Typen jedem anderen Typsystem zugeordnet werden, das nicht die CLR sein muss, dies jedoch die Erstellung und Verwendung eines anderen XAML-Parsers erfordert.)  
  
#### <a name="members-of-types-and-class-inheritance"></a>Member von Typen und Klassenvererbung  
 Eigenschaften und Ereignisse, wie sie als [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] XAML-Member eines Typs angezeigt werden, werden häufig von Basistypen geerbt. Betrachten Sie beispielsweise dieses `<Button Background="Blue" .../>`Beispiel: . Die <xref:System.Windows.Controls.Control.Background%2A> Eigenschaft ist keine sofort <xref:System.Windows.Controls.Button> deklarierte Eigenschaft für die Klasse, wenn Sie sich die Klassendefinition, die Reflexionsergebnisse oder die Dokumentation ansehen sollten. Stattdessen <xref:System.Windows.Controls.Control.Background%2A> wird von der <xref:System.Windows.Controls.Control> Basisklasse geerbt.  
  
 Das Klassenvererbungsverhalten von [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] XAML-Elementen ist eine wesentliche Abweichung von einer schemaerzwungenen Interpretation von XML-Markup. Die Klassenvererbung kann komplex werden, insbesondere wenn zwischengeschaltete Basisklassen abstrakt sind oder wenn Schnittstellen beteiligt sind. Dies ist ein Grund dafür, dass der Satz von XAML-Elementen und deren zulässige Attribute schwierig und vollständig mit den Schematypen dargestellt werden können, die normalerweise für die XML-Programmierung verwendet werden, z. B. DTD- oder XSD-Format. Ein weiterer Grund ist, dass Erweiterbarkeits- und Typzuordnungsfeatures der XAML-Sprache selbst die Vollständigkeit einer festen Darstellung der zulässigen Typen und Member ausschließen.  
  
<a name="object_element_syntax"></a>
## <a name="object-element-syntax"></a>Objektelementsyntax  
 *Die Objektelementsyntax* ist die XAML-Markupsyntax, die eine CLR-Klasse oder -Struktur instanziiert, indem ein XML-Element deklariert wird. Diese Syntax ähnelt der Elementsyntax anderer Markupsprachen wie HTML. Die Objektelementsyntax beginnt mit\<einer linken, spitzen Klammer ( ), gefolgt unmittelbar vom Typnamen der Klasse oder Struktur, die instanziiert wird. Null oder mehr Leerzeichen können dem Typnamen folgen, und null oder mehr Attribute können auch für das Objektelement deklariert werden, wobei ein oder mehrere Leerzeichen jedes Attributname="Wert"-Paar trennen. Schließlich muss eine der folgenden Optionen zutreffen:  
  
- Das Element und das Tag müssen durch einen Schrägstrich (/) geschlossen werden, gefolgt von einer rechten Winkelhalterung (>).  
  
- Das öffnende Tag muss durch eine rechte Winkelhalterung (>) ausgefüllt werden. Andere Objektelemente, Eigenschaftselemente oder innentexten können dem öffnenden Tag folgen. Welcher Inhalt hier genau enthalten sein kann, wird in der Regel durch das Objektmodell des Elements eingeschränkt. Das entsprechende schließende Tag für das Objektelement muss ebenfalls vorhanden sein, in der richtigen Verschachtelung und Balance mit anderen öffnenden und schließenden Tag-Paaren.  
  
 XAML, wie von .NET implementiert, verfügt über eine Reihe von Regeln, die Objektelemente Typen zuordnen, Attribute in Eigenschaften oder Ereignisse und XAML-Namespaces zu CLR-Namespaces plus Assembly. Für WPF und .NET werden XAML-Objektelemente .NET-Typen zugeordnet, wie in Assemblys definiert, und die Attribute werden Membern dieser Typen zugeordnet. Wenn Sie in XAML auf einen CLR-Typ verweisen, haben Sie auch Zugriff auf die geerbten Member dieses Typs.  
  
 Das folgende Beispiel ist z. B. die Objektelementsyntax, <xref:System.Windows.Controls.Button> die eine neue <xref:System.Windows.FrameworkElement.Name%2A> Instanz der Klasse instanziiert und auch ein Attribut und einen Wert für dieses Attribut angibt:  
  
 [!code-xaml[XAMLOvwSupport#SyntaxOE](~/samples/snippets/csharp/VS_Snippets_Wpf/XAMLOvwSupport/CSharp/Page1.xaml#syntaxoe)]  
  
 Das folgende Beispiel ist die Objektelementsyntax, die auch die Syntax der XAML-Inhaltseigenschaft enthält. Der darin enthaltene innere Text <xref:System.Windows.Controls.TextBox> wird verwendet, um <xref:System.Windows.Controls.TextBox.Text%2A>die XAML-Inhaltseigenschaft .  
  
 [!code-xaml[XAMLOvwSupport#ThisIsATextBox](~/samples/snippets/csharp/VS_Snippets_Wpf/XAMLOvwSupport/CSharp/Page1.xaml#thisisatextbox)]  
  
### <a name="content-models"></a>Inhaltsmodelle  
 Eine Klasse unterstützt möglicherweise eine Verwendung als XAML-Objektelement in Bezug auf die Syntax, aber dieses Element funktioniert nur dann ordnungsgemäß in einer Anwendung oder Seite, wenn es an einer erwarteten Position eines allgemeinen Inhaltsmodells oder einer Elementstruktur platziert wird. Beispielsweise sollte <xref:System.Windows.Controls.MenuItem> ein in der Regel nur <xref:System.Windows.Controls.Primitives.MenuBase> als untergeordnetes <xref:System.Windows.Controls.Menu>Element einer abgeleiteten Klasse wie platziert werden. Inhaltsmodelle für bestimmte Elemente werden als Teil der Anmerkungen auf [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] den Klassenseiten für Steuerelemente und andere Klassen dokumentiert, die als XAML-Elemente verwendet werden können.  
  
<a name="properties_of_object_elements"></a>
## <a name="properties-of-object-elements"></a>Eigenschaften von Objektelementen  
 Eigenschaften in XAML werden durch eine Vielzahl möglicher Syntaxen festgelegt. Welche Syntax für eine bestimmte Eigenschaft verwendet werden kann, hängt von den zugrunde liegenden Typsystemeigenschaften der Eigenschaft ab, die Sie festlegen.  
  
 Durch Festlegen von Werten von Eigenschaften fügen Sie Features oder Merkmale zu Objekten hinzu, wie sie im Laufzeitobjektdiagramm vorhanden sind. Der Anfangszustand des erstellten Objekts aus einem Objektelement basiert auf dem parameterlosen Konstruktorverhalten. In der Regel verwendet Ihre Anwendung etwas anderes als eine vollständig standardmäßige Instanz eines bestimmten Objekts.  
  
<a name="attribute_syntax_properties"></a>
## <a name="attribute-syntax-properties"></a>Attributsyntax (Eigenschaften)  
 Attributsyntax ist die XAML-Markupsyntax, die einen Wert für eine Eigenschaft festlegt, indem ein Attribut für ein vorhandenes Objektelement deklariert wird. Der Attributname muss mit dem CLR-Membernamen der Eigenschaft der Klasse übereinstimmen, die das entsprechende Objektelement unterstützt. Auf den Attributnamen folgt ein Zuweisungsoperator (=). Der Attributwert muss eine Zeichenfolge sein, die in Anführungszeichen eingeschlossen ist.  
  
> [!NOTE]
> Sie können abwechselnde Anführungszeichen verwenden, um ein wörtliches Anführungszeichen innerhalb eines Attributs zu platzieren. Sie können z. B. einfache Anführungszeichen verwenden, um eine Zeichenfolge zu deklarieren, die ein doppeltes Anführungszeichen darin enthält. Unabhängig davon, ob Sie einfache oder doppelte Anführungszeichen verwenden, sollten Sie ein übereinstimmendes Paar zum Öffnen und Schließen der Attributwertzeichenfolge verwenden. Es stehen auch Escapesequenzen oder andere Techniken zur Verfügung, um Zeichenbeschränkungen zu umgehen, die durch eine bestimmte XAML-Syntax auferlegt werden. Siehe [XML-Zeichenentitäten und XAML](../../../desktop-wpf/xaml-services/xml-character-entities.md).  
  
 Um durch Attributsyntax festgelegt zu werden, muss eine Eigenschaft öffentlich und schreibbar sein. Der Wert der Eigenschaft im Sicherungstypsystem muss ein Werttyp sein oder ein Verweistyp sein, der von einem XAML-Prozessor instanziiert oder referenziert werden kann, wenn er auf den entsprechenden Sicherungstyp zugreift.  
  
 Bei WPF XAML-Ereignissen muss das Ereignis, auf das als Attributname verwiesen wird, öffentlich sein und über einen öffentlichen Delegaten verfügen.  
  
 Die Eigenschaft oder das Ereignis muss ein Member der Klasse oder Struktur sein, die vom enthaltenden Objektelement instanziiert wird.  
  
### <a name="processing-of-attribute-values"></a>Verarbeitung von Attributwerten  
 Der Zeichenfolgenwert, der in den öffnenden und schließenden Anführungszeichen enthalten ist, wird von einem XAML-Prozessor verarbeitet. Bei Eigenschaften wird das Standardverarbeitungsverhalten durch den Typ der zugrunde liegenden CLR-Eigenschaft bestimmt.  
  
 Der Attributwert wird mit diesem Verarbeitungsauftrag durch einen der folgenden Werte ausgefüllt:  
  
1. Wenn der XAML-Prozessor auf eine geschweifte geschweifte geschweifte Klammer oder ein Objektelement trifft, das von <xref:System.Windows.Markup.MarkupExtension>abgeleitet wird, wird zuerst die referenzierte Markuperweiterung ausgewertet, anstatt den Wert als Zeichenfolge zu verarbeiten, und das von der Markuperweiterung zurückgegebene Objekt wird als Wert verwendet. In vielen Fällen ist das von einer Markuperweiterung zurückgegebene Objekt ein Verweis auf ein vorhandenes Objekt oder ein Ausdruck, der die Auswertung bis zur Laufzeit aufschiebt und kein neu instanziiertes Objekt ist.  
  
2. Wenn die Eigenschaft mit <xref:System.ComponentModel.TypeConverter>einer attributierten deklariert wird oder der <xref:System.ComponentModel.TypeConverter>Werttyp dieser Eigenschaft mit einem attributierten deklariert wird, wird der Zeichenfolgenwert des Attributs als Konvertierungseingabe an den Typkonverter übermittelt, und der Konverter gibt eine neue Objektinstanz zurück.  
  
3. Wenn keine <xref:System.ComponentModel.TypeConverter>vorhanden ist, wird versucht, eine direkte Konvertierung in den Eigenschaftstyp durchzuführen. Diese letzte Ebene ist eine direkte Konvertierung am parser-nativen Wert zwischen XAML-Sprachprimitiventypen oder eine Überprüfung der Namen benannter Konstanten in einer Enumeration (der Parser greift dann auf die übereinstimmenden Werte zu).  
  
#### <a name="enumeration-attribute-values"></a>Enumerationsattributwerte  
 Enumerationen in XAML werden von XAML-Parsern an sich weiterverarbeitet, und die Member einer Enumeration sollten angegeben werden, indem der Zeichenfolgenname einer der benannten Konstanten der Enumeration angegeben wird.  
  
 Bei Nichtflag-Enumerationswerten besteht das systemeigene Verhalten darin, die Zeichenfolge eines Attributwerts zu verarbeiten und in einen der Enumerationswerte aufzulösen. Sie geben die Enumeration nicht im Format *Enumeration*an. *Wert*, wie sie es im Code tun. Stattdessen geben Sie nur *Wert*an, und *Enumeration* wird durch den Typ der Eigenschaft abgeleitet, die Sie festlegen. Wenn Sie ein Attribut in der *Enumeration*angeben. *Wertformular* wird nicht ordnungsgemäß aufgelöst.  
  
 Bei flagweisen Enumerationen basiert das <xref:System.Enum.Parse%2A?displayProperty=nameWithType> Verhalten auf der Methode. Sie können mehrere Werte für eine flagweise Enumeration angeben, indem Sie jeden Wert durch ein Komma trennen. Sie können jedoch keine Enumerationswerte kombinieren, die nicht flagweise sind. Sie können z. B. nicht die Kommasyntax verwenden, um zu versuchen, eine <xref:System.Windows.Trigger> zu erstellen, die auf mehrere Bedingungen einer Nichtflag-Enumeration wirkt:  
  
```xaml  
<!--This will not compile, because Visibility is not a flagwise enumeration.-->  
...  
<Trigger Property="Visibility" Value="Collapsed,Hidden">  
  <Setter ... />  
</Trigger>  
...  
```  
  
 Flagweise-Enumerationen, die Attribute unterstützen, die in XAML festgelegt sind, sind in WPF selten. Eine solche Aufzählung ist <xref:System.Windows.Media.StyleSimulations>jedoch . Sie können z. B. die durch Kommas durch Kommas beschränkte flagweise <xref:System.Windows.Documents.Glyphs> Attributsyntax verwenden, um das Beispiel zu ändern, das in den Anmerkungen für die Klasse angegeben ist. `StyleSimulations = "BoldSimulation"` könnte `StyleSimulations = "BoldSimulation,ItalicSimulation"`werden . <xref:System.Windows.Input.KeyBinding.Modifiers%2A?displayProperty=nameWithType>ist eine andere Eigenschaft, bei der mehr als ein Enumerationswert angegeben werden kann. Diese Eigenschaft ist jedoch ein Sonderfall, <xref:System.Windows.Input.ModifierKeys> da die Enumeration einen eigenen Typkonverter unterstützt. Der Typkonverter für Modifikatoren verwendet ein Pluszeichen (+) als Trennzeichen anstelle eines Kommas (,). Diese Konvertierung unterstützt die traditionellere Syntax, die Tastenkombinationen in der Microsoft Windows-Programmierung darstellt, z. B. "Strg+Alt".  
  
### <a name="properties-and-event-member-name-references"></a>Eigenschaften und Ereignismembernamensreferenzen  
 Wenn Sie ein Attribut angeben, können Sie auf jede Eigenschaft oder jedes Ereignis verweisen, das als Member des CLR-Typs vorhanden ist, den Sie für das enthaltende Objektelement instanziiert haben.  
  
 Sie können auch auf eine angefügte Eigenschaft oder ein angefügtes Ereignis verweisen, unabhängig vom enthaltenden Objektelement. (Angefügte Eigenschaften werden in einem kommenden Abschnitt erläutert.)  
  
 Sie können auch jedes Ereignis von jedem Objekt benennen, auf das über den Standardnamespace zugegriffen werden kann, indem Sie einen *typeName*verwenden. *Ereignis* teilweise qualifizierter Name; Diese Syntax unterstützt das Anfügen von Handlern für routingd-Ereignisse, bei denen der Handler das Routing von Ereignissen aus untergeordneten Elementen behandeln soll, das übergeordnete Element jedoch nicht auch dieses Ereignis in der Members-Tabelle enthält. Diese Syntax ähnelt einer angefügten Ereignissyntax, aber das Ereignis hier ist kein echtes angefügtes Ereignis. Stattdessen verweisen Sie auf ein Ereignis mit einem qualifizierten Namen. Weitere Informationen finden Sie unter Übersicht über [geroutete Ereignisse](routed-events-overview.md).  
  
 In einigen Szenarien werden Eigenschaftsnamen manchmal als Wert eines Attributs und nicht als Attributname angegeben. Dieser Eigenschaftsname kann auch Qualifizierer enthalten, z. B. die Eigenschaft, die im Formular *ownerType*angegeben ist. *dependencyPropertyName*. Dieses Szenario ist beim Schreiben von Stilen oder Vorlagen in XAML üblich. Die Verarbeitungsregeln für Eigenschaftsnamen, die als Attributwert bereitgestellt werden, unterscheiden sich und werden durch den Typ der festzulegenden Eigenschaft oder durch das Verhalten bestimmter WPF-Subsysteme gesteuert. Weitere Informationen finden Sie unter [Styling und Templating](../../../desktop-wpf/fundamentals/styles-templates-overview.md).  
  
 Eine weitere Verwendung für Eigenschaftsnamen ist, wenn ein Attributwert eine Eigenschaftseigenschaftsbeziehung beschreibt. Diese Funktion wird für die Datenbindung und für Storyboardziele verwendet und durch die <xref:System.Windows.PropertyPath> Klasse und ihren Typkonverter aktiviert. Eine ausführlichere Beschreibung der Suchsemantik finden Sie unter [PropertyPath XAML Syntax](propertypath-xaml-syntax.md).  
  
<a name="property_element_syntax"></a>
## <a name="property-element-syntax"></a>Eigenschaftenelement-Syntax  
 Die Syntax von *Eigenschaftselementen* ist eine Syntax, die etwas von den grundlegenden XML-Syntaxregeln für Elemente abweicht. In XML ist der Wert eines Attributs eine De-facto-Zeichenfolge, wobei die einzige mögliche Variation darin besteht, welches Zeichenfolgencodierungsformat verwendet wird. In XAML können Sie andere Objektelemente als Wert einer Eigenschaft zuweisen. Diese Funktion wird durch die Syntax des Eigenschaftenelements aktiviert. Anstatt die Eigenschaft als Attribut innerhalb des Element-Tags anzugeben, wird die Eigenschaft mithilfe eines öffnenden Element-Tags in *elementTypeName*angegeben. *propertyName-Formular,* wird der Wert der Eigenschaft innerhalb angegeben, und dann wird das Eigenschaftselement geschlossen.  
  
 Insbesondere beginnt die Syntax mit einer\<linken, eckigen Klammer ( ), gefolgt unmittelbar vom Typnamen der Klasse oder Struktur, in der sich die Eigenschaftenelementsyntax befindet. Darauf folgt sofort ein einzelner Punkt (.), dann der Name einer Eigenschaft, dann eine rechte Winkelhalterung (>). Wie bei der Attributsyntax muss diese Eigenschaft innerhalb der deklarierten öffentlichen Member des angegebenen Typs vorhanden sein. Der Wert, der der Eigenschaft zugewiesen werden soll, ist im Eigenschaftselement enthalten. In der Regel wird der Wert als ein oder mehrere Objektelemente angegeben, da die Angabe von Objekten als Werte das Szenario ist, das die Eigenschaftenelementsyntax adressieren soll. Schließlich ein entsprechendes schließendes Tag, das denselben *elementTypeName*angibt. *propertyName-Kombination* muss bereitgestellt werden, in der richtigen Verschachtelung und Balance mit anderen Element-Tags.  
  
 Im Folgenden ist z. B. <xref:System.Windows.FrameworkElement.ContextMenu%2A> die <xref:System.Windows.Controls.Button>Eigenschaftselementsyntax für die Eigenschaft einer .  
  
 [!code-xaml[XAMLOvwSupport#ContextMenu](~/samples/snippets/csharp/VS_Snippets_Wpf/XAMLOvwSupport/CSharp/Page1.xaml#contextmenu)]  
  
 Der Wert innerhalb eines Eigenschaftselements kann auch als innerer Text angegeben werden, wenn <xref:System.String>der angegebene Eigenschaftstyp ein primitiver Werttyp ist, z. B. , oder eine Enumeration, in der ein Name angegeben wird. Diese beiden Verwendungen sind etwas ungewöhnlich, da jeder dieser Fälle auch eine einfachere Attributsyntax verwenden könnte. Ein Szenario zum Füllen eines Eigenschaftselements mit einer Zeichenfolge ist für Eigenschaften, die nicht die XAML-Inhaltseigenschaft sind, aber dennoch für die Darstellung von UI-Text verwendet werden, und bestimmte Leerraumelemente wie Zeilenvorschübe müssen in diesem UI-Text angezeigt werden. Die Attributsyntax kann keine Zeilenvorschübe beibehalten, aber die Syntax von Eigenschaftselementen kann, solange eine signifikante Leerraumerhaltung aktiv ist (Details finden Sie unter [Leerraumverarbeitung in XAML](../../../desktop-wpf/xaml-services/white-space-processing.md)). Ein weiteres Szenario ist, dass die [x:Uid-Direktive](../../../desktop-wpf/xaml-services/xuid-directive.md) auf das Eigenschaftselement angewendet werden kann und somit den Wert innerhalb als Wert markiert, der in der WPF-Ausgabe-BAML oder durch andere Techniken lokalisiert werden soll.  
  
 Ein Eigenschaftselement wird in der logischen WPF-Struktur nicht dargestellt. Ein Eigenschaftselement ist nur eine bestimmte Syntax zum Festlegen einer Eigenschaft und kein Element, das über eine Instanz oder ein Objekt verfügt, das es unterstützt. (Details zum logischen Baumkonzept finden Sie [unter Bäume in WPF](trees-in-wpf.md).)  
  
 Bei Eigenschaften, bei denen sowohl die Attribut- als auch die Eigenschaftenelementsyntax unterstützt werden, haben die beiden Syntaxen im Allgemeinen das gleiche Ergebnis, obwohl Feinheiten wie die Leerraumbehandlung zwischen den Syntaxen leicht variieren können.  
  
<a name="collection_syntax"></a>
## <a name="collection-syntax"></a>Auflistungssyntax  
 Die XAML-Spezifikation erfordert XAML-Prozessorimplementierungen, um Eigenschaften zu identifizieren, bei denen der Werttyp eine Auflistung ist. Die allgemeine XAML-Prozessorimplementierung in .NET basiert auf verwaltetem Code und der CLR und identifiziert Auflistungstypen über einen der folgenden Punkte:  
  
- Typ implementiert <xref:System.Collections.IList>.  
  
- Typ implementiert <xref:System.Collections.IDictionary>.  
  
- Typ leitet sich <xref:System.Array> von ab (weitere Informationen zu Arrays in XAML finden Sie unter [x:Array Markup Extension](../../../desktop-wpf/xaml-services/xarray-markup-extension.md).)  
  
 Wenn der Typ einer Eigenschaft eine Auflistung ist, muss der abgeleitete Auflistungstyp im Markup nicht als Objektelement angegeben werden. Stattdessen werden die Elemente, die zu den Elementen in der Auflistung werden sollen, als ein oder mehrere untergeordnete Elemente des Eigenschaftselements angegeben. Jedes dieser Elemente wird beim Laden zu einem Objekt `Add` ausgewertet und der Auflistung hinzugefügt, indem die Methode der impliziten Auflistung aufgerufen wird. Die <xref:System.Windows.Style.Triggers%2A> Eigenschaft von <xref:System.Windows.Style> takes übernimmt z. B. den spezialisierten Auflistungstyp <xref:System.Windows.TriggerCollection> <xref:System.Collections.IList>, der implementiert. Es ist nicht erforderlich, ein <xref:System.Windows.TriggerCollection> Objektelement im Markup zu instanziieren. Stattdessen geben Sie ein <xref:System.Windows.Trigger> oder mehrere `Style.Triggers` Elemente als <xref:System.Windows.Trigger> Elemente innerhalb des Eigenschaftselements an, wobei (oder eine abgeleitete Klasse) der Typ ist, der als Elementtyp für den stark typisierten und impliziten <xref:System.Windows.TriggerCollection>elementstyp erwartet wird.  
  
 [!code-xaml[XAMLOvwSupport#SyntaxPECollection](~/samples/snippets/csharp/VS_Snippets_Wpf/XAMLOvwSupport/CSharp/Page1.xaml#syntaxpecollection)]  
  
 Eine Eigenschaft kann sowohl ein Auflistungstyp als auch die XAML-Inhaltseigenschaft für diesen Typ und abgeleitete Typen sein, die im nächsten Abschnitt dieses Themas erläutert wird.  
  
 Ein implizites Auflistungselement erstellt ein Element in der logischen Strukturdarstellung, auch wenn es im Markup nicht als Element angezeigt wird. Normalerweise führt der Konstruktor des übergeordneten Typs die Instanziierung für die Auflistung aus, die eine ihrer Eigenschaften ist, und die anfänglich leere Auflistung wird Teil der Objektstruktur.  
  
> [!NOTE]
> Die generischen Listen-<xref:System.Collections.Generic.IList%601> und <xref:System.Collections.Generic.IDictionary%602>Wörterbuchschnittstellen ( und ) werden für die Sammlungserkennung nicht unterstützt. Sie können <xref:System.Collections.Generic.List%601> die Klasse jedoch als Basisklasse verwenden, da sie <xref:System.Collections.IList> direkt oder <xref:System.Collections.Generic.Dictionary%602> als <xref:System.Collections.IDictionary> Basisklasse implementiert wird, da sie direkt implementiert wird.  
  
 In den .NET-Referenzseiten für Auflistungstypen wird diese Syntax mit der absichtlichen Auslassung des Objektelements für eine Auflistung gelegentlich in den XAML-Syntaxabschnitten als implizite Auflistungssyntax vermerkt.  
  
 Mit Ausnahme des root-Elements ist jedes Objektelement in einer XAML-Datei, das als untergeordnetes Element eines anderen Elements verschachtelt ist, wirklich ein Element, das einer oder beide der folgenden Fälle ist: ein Member einer impliziten Auflistungseigenschaft des übergeordneten Elements oder ein Element, das den Wert der XAML-Inhaltseigenschaft für das übergeordnete Element angibt (XAML-Inhaltseigenschaften werden in einem kommenden Abschnitt erläutert). Mit anderen Worten, die Beziehung zwischen übergeordneten Elementen und untergeordneten Elementen in einer Markupseite ist wirklich ein einzelnes Objekt im Stamm, und jedes Objektelement unter dem Stamm ist entweder eine einzelne Instanz, die einen Eigenschaftswert des übergeordneten Elements bereitstellt, oder eines der Elemente innerhalb einer Auflistung, das auch ein Auflistungstyp-Eigenschaftswert des übergeordneten Elements ist. Dieses Single-Root-Konzept ist mit XML üblich und wird häufig im Verhalten von <xref:System.Windows.Markup.XamlReader.Load%2A>APIs verstärkt, die XAML laden, z. B. .  
  
 Das folgende Beispiel ist eine Syntax mit<xref:System.Windows.Media.GradientStopCollection>dem Objektelement für eine Auflistung ( ) explizit angegeben.  
  
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
  
 Beachten Sie, dass es nicht immer möglich ist, die Auflistung explizit zu deklarieren. Beispielsweise schlägt der Versuch <xref:System.Windows.TriggerCollection> fehl, explizit <xref:System.Windows.Style.Triggers%2A> im zuvor gezeigten Beispiel zu deklarieren. Das explizite Deklarieren der Auflistung erfordert, dass die <xref:System.Windows.TriggerCollection> Auflistungsklasse einen parameterlosen Konstruktor unterstützen muss und nicht über einen parameterlosen Konstruktor verfügt.  
  
<a name="xaml_content_properties"></a>
## <a name="xaml-content-properties"></a>XAML-Inhaltseigenschaften  
 XAML-Inhaltssyntax ist eine Syntax, die nur <xref:System.Windows.Markup.ContentPropertyAttribute> für Klassen aktiviert ist, die die als Teil ihrer Klassendeklaration angeben. Der <xref:System.Windows.Markup.ContentPropertyAttribute> verweist auf den Eigenschaftsnamen, der die Inhaltseigenschaft für diesen Elementtyp (einschließlich abgeleiteter Klassen) ist. Wenn sie von einem XAML-Prozessor verarbeitet werden, werden alle untergeordneten Elemente oder der innere Text, die zwischen den öffnenden und schließenden Tags des Objektelements gefunden werden, als Wert der XAML-Inhaltseigenschaft für dieses Objekt zugewiesen. Sie können explizite Eigenschaftselemente für die content-Eigenschaft angeben, aber diese Verwendung wird im Allgemeinen nicht in den XAML-Syntaxabschnitten im .NET-Verweis angezeigt. Die explizite/verbose Technik hat gelegentlichen Wert für Markupklarheit oder als eine Frage des Markupstils, aber in der Regel besteht die Absicht einer Content-Eigenschaft darin, das Markup so zu optimieren, dass Elemente, die intuitiv als Parent-Child verknüpft sind, direkt geschachtelt werden können. Eigenschaftselement-Tags für andere Eigenschaften in einem Element werden nicht als "Inhalt" gemäß einer strengen XAML-Sprachdefinition zugewiesen. Sie werden zuvor in der Verarbeitungsreihenfolge des XAML-Parsers verarbeitet und gelten nicht als "Inhalt".  
  
### <a name="xaml-content-property-values-must-be-contiguous"></a>XAML-Inhaltseigenschaftswerte müssen zusammenhängend sein  
 Der Wert einer XAML-Inhaltseigenschaft muss entweder vollständig vor oder vollständig nach anderen Eigenschaftselementen in diesem Objektelement angegeben werden. Dies gilt unabhängig davon, ob der Wert einer XAML-Inhaltseigenschaft als Zeichenfolge oder als ein oder mehrere Objekte angegeben wird. Das folgende Markup wird z. B. nicht analysiert:  
  
```xaml  
<Button>I am a
  <Button.Background>Blue</Button.Background>  
  blue button</Button>  
```  
  
 Dies ist im Wesentlichen unzulässig, da, wenn diese Syntax explizit gemacht würde, indem die Syntax des Eigenschaftenelements für die content-Eigenschaft verwendet würde, würde die content-Eigenschaft zweimal festgelegt:  
  
```xaml  
<Button>  
  <Button.Content>I am a </Button.Content>  
  <Button.Background>Blue</Button.Background>  
  <Button.Content> blue button</Button.Content>  
</Button>  
```  
  
 Ein ähnlich illegales Beispiel ist, wenn die content-Eigenschaft eine Auflistung ist und untergeordnete Elemente mit Eigenschaftselementen durchsetzt sind:  
  
```xaml  
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
 Um mehr als ein einzelnes Objektelement als Inhalt zu akzeptieren, muss der Typ der content-Eigenschaft speziell ein Auflistungstyp sein. Ähnlich wie die Eigenschaftenelementsyntax für Auflistungstypen muss ein XAML-Prozessor Typen identifizieren, die Auflistungstypen sind. Wenn ein Element über eine XAML-Inhaltseigenschaft verfügt und der Typ der XAML-Inhaltseigenschaft eine Auflistung ist, muss der implizite Auflistungstyp im Markup nicht als Objektelement angegeben werden, und die XAML-Inhaltseigenschaft muss nicht als Eigenschaftselement angegeben werden. Daher kann dem scheinbaren Inhaltsmodell im Markup jetzt mehr als ein untergeordnetes Element als Inhalt zugewiesen werden. Im Folgenden finden Sie <xref:System.Windows.Controls.Panel> die Inhaltssyntax für eine abgeleitete Klasse. Alle <xref:System.Windows.Controls.Panel> abgeleiteten Klassen richten die XAML-Inhaltseigenschaft als ein <xref:System.Windows.Controls.Panel.Children%2A>, der einen Wert vom Typ <xref:System.Windows.Controls.UIElementCollection>erfordert.  
  
 [!code-xaml[XAMLOvwSupport#SyntaxContent](~/samples/snippets/csharp/VS_Snippets_Wpf/XAMLOvwSupport/CSharp/page5.xaml#syntaxcontent)]  
  
 Beachten Sie, dass <xref:System.Windows.Controls.Panel.Children%2A> weder das <xref:System.Windows.Controls.UIElementCollection> Eigenschaftselement für noch das Element für die im Markup erforderlich ist. Dies ist ein Entwurfsfeature von XAML, sodass rekursiv enthaltene Elemente, die eine [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] definieren, intuitiver als Eine Struktur von verschachtelten Elementen mit sofortigen Parent-Child-Element-Beziehungen dargestellt werden, ohne dass Eigenschaftenelement-Tags oder Auflistungsobjekte einzugreifen. Tatsächlich <xref:System.Windows.Controls.UIElementCollection> kann nicht explizit in Markup als Objektelement durch Entwurf angegeben werden. Da die einzige beabsichtigte Verwendung <xref:System.Windows.Controls.UIElementCollection> als implizite Auflistung ist, wird kein öffentlicher parameterloser Konstruktor verfügbar gemacht und kann daher nicht als Objektelement instanziiert werden.  
  
### <a name="mixing-property-elements-and-object-elements-in-an-object-with-a-content-property"></a>Mischen von Eigenschaftenelementen und Objektelementen in einem Objekt mit einer Content-Eigenschaft  
 Die XAML-Spezifikation deklariert, dass ein XAML-Prozessor erzwingen kann, dass Objektelemente, die zum Ausfüllen der XAML-Inhaltseigenschaft innerhalb eines Objektelements verwendet werden, zusammenhängend sein und nicht gemischt werden dürfen. Diese Einschränkung zum Mischen von Eigenschaftselementen [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] und Inhalten wird von den XAML-Prozessoren erzwungen.  
  
 Sie können ein untergeordnetes Objektelement als erstes direktes Markup innerhalb eines Objektelements haben. Anschließend können Sie Eigenschaftselemente einführen. Sie können auch ein oder mehrere Eigenschaftselemente angeben, dann Deninhalt und dann weitere Eigenschaftselemente. Sobald jedoch ein Eigenschaftselement dem Inhalt folgt, können Sie keinen weiteren Inhalt einführen, Sondern nur Eigenschaftselemente hinzufügen.  
  
 Diese Inhalts-/Eigenschaftselementreihenfolgeanforderung gilt nicht für inneren Text, der als Inhalt verwendet wird. Es ist jedoch immer noch ein guter Markupstil, um den inneren Text zusammenhängend zu halten, da ein erheblicher Leerraum im Markup nur schwer visuell zu erkennen ist, wenn Eigenschaftselemente mit innerem Text durchsetzt sind.  
  
<a name="xaml_namespaces"></a>
## <a name="xaml-namespaces"></a>XAML-Namespaces  
 Keiner der vorherigen Syntaxbeispiele hat einen anderen XAML-Namespace als den Standardmäßigen XAML-Namespace angegeben. In [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] typischen Anwendungen wird der standardmäßige XAML-Namespace als [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Namespace angegeben. Sie können andere XAML-Namespaces als den Standardmäßigen XAML-Namespace angeben und trotzdem eine ähnliche Syntax verwenden. An einer beliebigen Stelle, an der eine Klasse benannt ist, auf die im Standard-XAML-Namespace nicht zugegriffen werden kann, muss diesem Klassennamen jedoch das Präfix des XAML-Namespace vorangestellt werden, das dem entsprechenden CLR-Namespace zugeordnet ist. `<custom:Example/>` Beispielsweise ist die Objektelementsyntax zum Instanziieren `Example` einer Instanz der Klasse, bei der der CLR-Namespace, der diese Klasse enthält `custom` (und möglicherweise die externen Assemblyinformationen, die Sicherungstypen enthalten), zuvor dem Präfix zugeordnet wurde.  
  
 Weitere Informationen zu XAML-Namespaces finden Sie unter [XAML-Namespaces und Namespace-Zuordnung für WPF XAML](xaml-namespaces-and-namespace-mapping-for-wpf-xaml.md).  
  
<a name="markup_extensions"></a>
## <a name="markup-extensions"></a>Markuperweiterungen  
 XAML definiert eine Markuperweiterungsprogrammierentität, die ein Escapeaus aus der normalen XAML-Prozessorbehandlung von Zeichenfolgenattributwerten oder Objektelementen ermöglicht und die Verarbeitung auf eine Sicherungsklasse verschiebt. Das Zeichen, das eine Markuperweiterung zu einem XAML-Prozessor identifiziert, wenn die Attributsyntax verwendet wird, ist die öffnende geschweifte geschweifte Klammer () gefolgt von einem anderen Zeichen als einer schließenden geschweiften geschweiften Klammer . Die erste Zeichenfolge, die auf die öffnende geschweifte Klammer folgt, muss auf die Klasse verweisen, die das bestimmte Erweiterungsverhalten bereitstellt, wobei der Verweis die Teilzeichenfolge "Extension" weglassen kann, wenn diese Teilzeichenfolge Teil des true-Klassennamens ist. Danach kann ein einzelnes Leerzeichen angezeigt werden, und dann wird jedes nachfolgende Zeichen von der Erweiterungsimplementierung als Eingabe verwendet, bis die abschließende geschweifte Klammer gefunden wird.  
  
 Die .NET XAML-Implementierung verwendet die <xref:System.Windows.Markup.MarkupExtension> abstrakte Klasse als Grundlage [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] für alle Markuperweiterungen, die von sowie von anderen Frameworks oder Technologien unterstützt werden. Die Markuperweiterungen, die [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] speziell implementiert werden, dienen häufig dazu, auf andere vorhandene Objekte zu verweisen oder verzögerte Verweise auf Objekte zu erstellen, die zur Laufzeit ausgewertet werden. Beispielsweise wird eine einfache WPF-Datenbindung erreicht, indem die `{Binding}` Markuperweiterung anstelle des Werts angegeben wird, den eine bestimmte Eigenschaft normalerweise annehmen würde. Viele der WPF-Markuperweiterungen ermöglichen eine Attributsyntax für Eigenschaften, bei denen eine Attributsyntax andernfalls nicht möglich wäre. Ein <xref:System.Windows.Style> Objekt ist z. B. ein relativ komplexer Typ, der eine geschachtelte Reihe von Objekten und Eigenschaften enthält. Stile in WPF werden in der <xref:System.Windows.ResourceDictionary>Regel als Ressource in einem definiert und dann über eine der beiden WPF-Markuperweiterungen referenziert, die eine Ressource anfordern. Die Markuperweiterung verschiebt die Auswertung des Eigenschaftswerts auf eine Ressourcensuche und ermöglicht die Bereitstellung des Werts der <xref:System.Windows.FrameworkElement.Style%2A> Eigenschaft unter Berücksichtigung des Typs <xref:System.Windows.Style>in der Attributsyntax wie im folgenden Beispiel:  
  
 `<Button Style="{StaticResource MyStyle}">My button</Button>`  
  
 Identifiziert `StaticResource` hier <xref:System.Windows.StaticResourceExtension> die Klasse, die die Markuperweiterungsimplementierung bereitstellt. Die nächste `MyStyle` Zeichenfolge wird als Eingabe für <xref:System.Windows.StaticResourceExtension> den nicht standardmäßigen Konstruktor verwendet, wobei <xref:System.Windows.ResourceKey>der Parameter, der aus der Erweiterungszeichenfolge entnommen wird, die angeforderte deklariert. `MyStyle`wird erwartet, dass der [x:Key-Wert](../../../desktop-wpf/xaml-services/xkey-directive.md) einer <xref:System.Windows.Style> Ressource ist, die als Ressource definiert ist. Die [Verwendung von StaticResource Markup Extension](staticresource-markup-extension.md) fordert, <xref:System.Windows.Style> dass die Ressource verwendet wird, um den Eigenschaftswert über statische Ressourcensuchlogik zur Ladezeit bereitzustellen.  
  
 Weitere Informationen über Markuperweiterungen finden Sie unter [Markuperweiterungen und WPF XAML](markup-extensions-and-wpf-xaml.md). Eine Referenz zu Markuperweiterungen und anderen XAML-Programmierfeatures, die in der allgemeinen .NET XAML-Implementierung aktiviert sind, finden Sie unter [XAML Namespace (x:) Sprachfunktionen](../../../desktop-wpf/xaml-services/namespace-language-features.md). Informationen zu WPF-spezifischen Markuperweiterungen finden Sie unter [WPF XAML Extensions](wpf-xaml-extensions.md).  
  
<a name="attached_properties"></a>
## <a name="attached-properties"></a>Angefügte Eigenschaften  
 Angefügte Eigenschaften sind ein Programmierkonzept, das in XAML eingeführt wird, wobei Eigenschaften von einem bestimmten Typ besessen und definiert werden können, aber als Attribute oder Eigenschaftselemente für jedes Element festgelegt werden. Das primäre Szenario, für das angefügte Eigenschaften vorgesehen sind, besteht darin, untergeordneten Elementen in einer Markupstruktur das Melden von Informationen an ein übergeordnetes Element zu ermöglichen, ohne dass ein umfassend freigegebenes Objektmodell für alle Elemente erforderlich ist. Umgekehrt können angefügte Eigenschaften von übergeordneten Elementen verwendet werden, um Informationen an untergeordnete Elemente zu melden. Weitere Informationen zum Zweck der angefügten Eigenschaften und zum Erstellen eigener angefügter Eigenschaften finden Sie unter [Übersicht über zugeordnete Eigenschaften](attached-properties-overview.md).  
  
 Angefügte Eigenschaften verwenden eine Syntax, die oberflächlich der Eigenschaftenelementsyntax ähnelt, da Sie auch einen *typeName*angeben. *propertyName-Kombination.* Es gibt zwei wichtige Unterschiede:  
  
- Sie können den *typeName*verwenden. *propertyName-Kombination* auch beim Festlegen einer angefügten Eigenschaft durch Attributsyntax. Angefügte Eigenschaften sind der einzige Fall, in dem das Qualifizieren des Eigenschaftennamens eine Anforderung in einer Attributsyntax ist.  
  
- Sie können auch die Eigenschaftenelementsyntax für angefügte Eigenschaften verwenden. Für die typische Eigenschaftenelementsyntax ist der von Ihnen angegebene *typeName* jedoch das Objektelement, das das Eigenschaftselement enthält. Wenn Sie auf eine angefügte Eigenschaft verweisen, ist der *typeName* die Klasse, die die angefügte Eigenschaft definiert, nicht das enthaltende Objektelement.  
  
<a name="attached_events"></a>
## <a name="attached-events"></a>Angefügte Ereignisse  
 Angefügte Ereignisse sind ein weiteres Programmierkonzept, das in XAML eingeführt wurde, bei dem Ereignisse durch einen bestimmten Typ definiert werden können, Handler jedoch an jedes Objektelement angefügt werden können. In der WOF-Implementierung ist der Typ, der ein angefügtes Ereignis definiert, häufig ein statischer Typ, der einen Dienst definiert, und manchmal werden diese angefügten Ereignisse von einem routingierten Ereignisalias in Typen verfügbar gemacht, die den Dienst verfügbar machen. Handler für angefügte Ereignisse werden durch Attributsyntax angegeben. Wie bei angefügten Ereignissen wird die Attributsyntax für angefügte Ereignisse erweitert, um einen *typeName*zuzulassen. *die ereignisName-Verwendung,* wobei *typeName* `Remove` die Klasse ist, die Und Ereignishandler-Accessoren für die angefügte Ereignisinfrastruktur bereitstellt, `Add` und *eventName* der Ereignisname.  
  
<a name="anatomy_of_a_xaml_page_root_element"></a>
## <a name="anatomy-of-a-xaml-root-element"></a>Anatomie eines XAML-Wurzelelements  
 Die folgende Tabelle zeigt ein typisches XAML-Stammelement, das aufgebrochen wird und die spezifischen Attribute eines Stammelements zeigt:  
  
|||  
|-|-|  
|`<Page`|Öffnen des Objektelements des Stammelements|  
|`xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"`|Der Standardwert ([!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]) XAML-Namespace|  
|`xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"`|Der XAML-Sprach-XAML-Namespace|  
|`x:Class="ExampleNamespace.ExampleCode"`|Die partielle Klassendeklaration, die Markup mit einem codebehind verbindet, der für die partielle Klasse definiert ist.|  
|`>`|Ende des Objektelements für den Stamm. Das Objekt ist noch nicht geschlossen, da das Element untergeordnete Elemente enthält.|  
  
<a name="optional_and_nonrecommended_xaml_usages"></a>
## <a name="optional-and-nonrecommended-xaml-usages"></a>Optionale und nicht empfohlene XAML-Verwendungen  
 In den folgenden Abschnitten werden XAML-Verwendungen beschrieben, die technisch von XAML-Prozessoren unterstützt werden, aber ausführlich oder andere ästhetische Probleme verursachen, die xAML-Dateien stören, die beim Entwickeln von Anwendungen, die XAML-Quellen enthalten, weiterhin lesbar sind.  
  
### <a name="optional-property-element-usages"></a>Optionale Eigenschaftenelementverwendungen  
 Zu den optionalen Eigenschaftenelementverwendungen gehört das explizite Ausschreiben von Elementinhaltseigenschaften, die der XAML-Prozessor als implizit betrachtet. Wenn Sie z. B. <xref:System.Windows.Controls.Menu>den Inhalt einer deklarieren, können <xref:System.Windows.Controls.ItemsControl.Items%2A> Sie die Auflistung des <xref:System.Windows.Controls.MenuItem> `<Menu.Items>` <xref:System.Windows.Controls.Menu> als `<Menu.Items>` Eigenschaftselement-Tags explizit deklarieren und jedes <xref:System.Windows.Controls.Menu> in platzieren, anstatt das implizite XAML-Prozessorverhalten zu verwenden, dass alle untergeordneten Elemente von a a <xref:System.Windows.Controls.MenuItem> sein müssen und in der <xref:System.Windows.Controls.ItemsControl.Items%2A> Auflistung platziert werden. Manchmal können die optionalen Verwendungen helfen, die Objektstruktur, wie sie im Markup dargestellt wird, visuell zu verdeutlichen. Manchmal kann eine explizite Eigenschaftenelementverwendung Markup vermeiden, das technisch funktional, aber visuell verwirrend ist, z. B. geschachtelte Markuperweiterungen innerhalb eines Attributwerts.  
  
### <a name="full-typenamemembername-qualified-attributes"></a>Vollständige typeName.memberName Qualifizierte Attribute  
 Der *typName*. *MemberName-Formular* für ein Attribut funktioniert tatsächlich universeller als nur der routingierte Ereignisfall. Aber in anderen Situationen ist diese Form überflüssig und Sie sollten es vermeiden, wenn auch nur aus Gründen des Markup-Stils und der Lesbarkeit. Im folgenden Beispiel ist jeder der <xref:System.Windows.Controls.Control.Background%2A> drei Verweise auf das Attribut vollständig äquivalent:  
  
 [!code-xaml[XAMLOvwSupport#TypeNameProp](~/samples/snippets/csharp/VS_Snippets_Wpf/XAMLOvwSupport/CSharp/page8.xaml#typenameprop)]  
  
 `Button.Background`funktioniert, da die qualifizierte Suche <xref:System.Windows.Controls.Button> für<xref:System.Windows.Controls.Control.Background%2A> diese Eigenschaft erfolgreich ist <xref:System.Windows.Controls.Button> (wurde von Control geerbt) und die Klasse des Objektelements oder einer Basisklasse ist. `Control.Background`funktioniert, <xref:System.Windows.Controls.Control> da die <xref:System.Windows.Controls.Control.Background%2A> Klasse <xref:System.Windows.Controls.Control> tatsächlich <xref:System.Windows.Controls.Button> definiert und eine Basisklasse ist.  
  
 Der folgende *typName*. *MemberName-Formularbeispiel* funktioniert nicht und wird daher kommentiert angezeigt:  
  
 [!code-xaml[XAMLOvwSupport#TypeNameBadProp](~/samples/snippets/csharp/VS_Snippets_Wpf/XAMLOvwSupport/CSharp/page8.xaml#typenamebadprop)]  
  
 <xref:System.Windows.Controls.Label>ist eine andere <xref:System.Windows.Controls.Control>abgeleitete Klasse `Label.Background` von <xref:System.Windows.Controls.Label> , und wenn Sie innerhalb eines Objektelements angegeben hätten, hätte diese Verwendung funktioniert. Da es <xref:System.Windows.Controls.Label> sich jedoch nicht um <xref:System.Windows.Controls.Button>die Klasse oder Basisklasse von `Label.Background` handelt, soll das angegebene XAML-Prozessorverhalten dann als angefügte Eigenschaft verarbeitet werden. `Label.Background`ist keine verfügbare angefügte Eigenschaft, und diese Verwendung schlägt fehl.  
  
### <a name="basetypenamemembername-property-elements"></a>baseTypeName.memberName-Eigenschaftselemente  
 In analoger Weise, wie der *typName*. *memberName-Formular* funktioniert für die Attributsyntax, einen *baseTypeName*. *MemberName-Syntax* funktioniert für die Eigenschaftenelementsyntax. Die folgende Syntax funktioniert z. B.:  
  
 [!code-xaml[XAMLOvwSupport#GoofyPE](~/samples/snippets/csharp/VS_Snippets_Wpf/XAMLOvwSupport/CSharp/page8.xaml#goofype)]  
  
 Hier wurde das Eigenschaftselement so `Control.Background` angegeben, dass `Button`das Eigenschaftselement in enthalten war.  
  
 Aber genau wie *typeName*. *memberName-Formular* für Attribute, *baseTypeName*. *memberName* ist ein schlechter Stil im Markup, und Sie sollten ihn vermeiden.  
  
## <a name="see-also"></a>Siehe auch

- [Übersicht über XAML (WPF)](../../../desktop-wpf/fundamentals/xaml.md)
- [XAML-Namespace (x:) Sprachfunktionen](../../../desktop-wpf/xaml-services/namespace-language-features.md)
- [WPF-XAML-Erweiterungen](wpf-xaml-extensions.md)
- [Übersicht über Abhängigkeitseigenschaften](dependency-properties-overview.md)
- [TypeConverter und XAML](typeconverters-and-xaml.md)
- [XAML- und benutzerdefinierte Klassen für WPF](xaml-and-custom-classes-for-wpf.md)
