---
title: Ausführliche Erläuterung der XAML-Syntax
description: Erfahren Sie mehr über Begriffe, die verwendet werden, um die Elemente der XAML-Syntax für Windows Presentation Foundation und andere Frameworks zu beschreiben, die XAML verwenden.
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
ms.openlocfilehash: 6ef217a646b14f02c0b812f6316ec84f26d4b660
ms.sourcegitcommit: 87cfeb69226fef01acb17c56c86f978f4f4a13db
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/24/2020
ms.locfileid: "87168350"
---
# <a name="xaml-syntax-in-detail"></a>Ausführliche Erläuterung der XAML-Syntax
In diesem Thema werden die Begriffe definiert, die verwendet werden, um die Elemente der XAML-Syntax zu beschreiben. Diese Begriffe werden im restlichen Teil dieser Dokumentation häufig verwendet, sowohl für die WPF-Dokumentation als auch für die anderen Frameworks, die XAML oder die grundlegenden XAML-Konzepte verwenden, die von der XAML-Sprachunterstützung auf der System. XAML-Ebene aktiviert werden. Dieses Thema erweitert die grundlegende Terminologie, die im Thema [Übersicht über XAML (WPF)](../../../desktop-wpf/fundamentals/xaml.md)vorgestellt wurde.  

<a name="the_xaml_language_specification"></a>
## <a name="the-xaml-language-specification"></a>Die XAML-Sprachspezifikation  
 Die hier definierte XAML-Syntax Terminologie ist auch definiert oder wird innerhalb der XAML-Sprachspezifikation referenziert. XAML ist eine Sprache, die auf XML basiert und auf XML-Struktur Regeln folgt oder Sie erweitert. Einige der Begriffe werden von freigegeben oder basieren auf der Terminologie, die häufig verwendet wird, wenn die XML-Sprache oder das XML-Dokument Objektmodell beschrieben wird.  
  
 Weitere Informationen zur XAML-Sprachspezifikation finden Sie unter Herunterladen von [ \[ MS- \] XAML](https://download.microsoft.com/download/0/A/6/0A6F7755-9AF5-448B-907D-13985ACCF53E/[MS-XAML].pdf) aus dem Microsoft Download Center.  
  
<a name="xaml_and_clr"></a>
## <a name="xaml-and-clr"></a>XAML und CLR  
 XAML ist eine Markup Sprache. Der Common Language Runtime (CLR), wie er durch seinen Namen impliziert, ermöglicht die Lauf Zeit Ausführung. Bei XAML handelt es sich nicht um eine der allgemeinen Sprachen, die von der CLR-Laufzeit direkt genutzt werden. Stattdessen können Sie sich XAML als Unterstützung eines eigenen Typsystems vorstellen. Das spezielle von WPF verwendete XAML-Erstellungs System basiert auf der CLR und dem CLR-Typsystem. XAML-Typen werden CLR-Typen zugeordnet, um eine Lauf Zeit Darstellung zu instanziieren, wenn die XAML für WPF analysiert wird. Aus diesem Grund enthält der Rest der Erörterung der Syntax in diesem Dokument Verweise auf das CLR-Typsystem, auch wenn die entsprechenden Syntax Diskussionen in der XAML-Sprachspezifikation dies nicht tun. (Gemäß der XAML-sprach Spezifikations Ebene können XAML-Typen einem beliebigen anderen Typsystem zugeordnet werden, was nicht die CLR sein muss, aber dies erfordert die Erstellung und Verwendung eines anderen XAML-Parsers.)  
  
#### <a name="members-of-types-and-class-inheritance"></a>Member von Typen und Klassen Vererbung  
 Eigenschaften und Ereignisse, die als XAML-Member eines [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Typs angezeigt werden, werden oft von Basis Typen geerbt. Sehen Sie sich beispielsweise Folgendes Beispiel an: `<Button Background="Blue" .../>` . Die- <xref:System.Windows.Controls.Control.Background%2A> Eigenschaft ist keine sofort deklarierte Eigenschaft in der <xref:System.Windows.Controls.Button> Klasse, wenn Sie die Klassendefinition, die Reflektionsergebnisse oder die Dokumentation betrachten. Stattdessen <xref:System.Windows.Controls.Control.Background%2A> wird von der-Basis <xref:System.Windows.Controls.Control> Klasse geerbt.  
  
 Das Klassen Vererbungs Verhalten von [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] XAML-Elementen ist eine bedeutende Abkehr von der durch das Schema erzwungene Interpretation von XML-Markup. Die Klassen Vererbung kann komplex werden, insbesondere dann, wenn zwischen Basisklassen abstrakt sind oder wenn Schnittstellen beteiligt sind. Dies ist ein Grund, warum der Satz von XAML-Elementen und deren zulässige Attribute schwierig und vollständig mit den Schema Typen, die normalerweise für die XML-Programmierung verwendet werden, wie z. b. DTD oder XSD-Format, darstellen kann. Ein weiterer Grund ist, dass Erweiterbarkeits-und Typmapping-Features der XAML-Sprache selbst die Vollständigkeit jeder festgelegten Darstellung der zulässigen Typen und Member ausschließen.  
  
<a name="object_element_syntax"></a>
## <a name="object-element-syntax"></a>Objektelementsyntax  
 Die *Objekt Element Syntax* ist die XAML-Markup Syntax, die eine CLR-Klasse oder-Struktur durch Deklarieren eines XML-Elements instanziiert. Diese Syntax ähnelt der Element Syntax anderer Markup Sprachen, wie z. b. html. Die Objekt Element Syntax beginnt mit einer öffnende spitze Klammer ( \< ), gefolgt von dem Typnamen der Klasse oder Struktur, die instanziiert wird. 0 (null) oder mehr Leerzeichen können dem Typnamen folgen, und NULL oder mehr Attribute können auch für das Object-Element deklariert werden, wobei ein oder mehrere Leerzeichen das Paar Attribute Name = "Wert" trennen. Schließlich muss einer der folgenden Punkte zutreffen:  
  
- Das Element und das Tag müssen mit einem Schrägstrich (/) geschlossen werden, gefolgt von einer rechten Spitze Klammer (>).  
  
- Das öffnende Tag muss durch eine schließende spitze Klammer (>) abgeschlossen werden. Andere Objekt Elemente, Eigenschaften Elemente oder innerer Text können dem öffnenden Tag folgen. Der Inhalt, der hier enthalten sein kann, wird in der Regel durch das Objektmodell des Elements eingeschränkt. Das entsprechende schließende Tag für das Object-Element muss auch vorhanden sein, in ordnungsgemäßer Schachtelung und in Einklang mit anderen öffnenden und schließenden Tagpaaren.  
  
 XAML, wie von .NET implementiert, verfügt über eine Reihe von Regeln, die Objekt Elemente Typen, Attributen in Eigenschaften oder Ereignissen und XAML-Namespaces in CLR-Namespaces Plus Assembly zuordnen. Für WPF und .net werden XAML-Objekt Elemente .NET-Typen entsprechend den in referenzierten Assemblys definierten zugeordnet, und die Attribute werden den Membern dieser Typen zugeordnet. Wenn Sie in XAML auf einen CLR-Typ verweisen, haben Sie auch Zugriff auf die geerbten Member dieses Typs.  
  
 Beispielsweise ist das folgende Beispiel eine Objekt Element Syntax, die eine neue Instanz der-Klasse instanziiert <xref:System.Windows.Controls.Button> und außerdem ein <xref:System.Windows.FrameworkElement.Name%2A> -Attribut und einen Wert für dieses Attribut angibt:  
  
 [!code-xaml[XAMLOvwSupport#SyntaxOE](~/samples/snippets/csharp/VS_Snippets_Wpf/XAMLOvwSupport/CSharp/Page1.xaml#syntaxoe)]  
  
 Das folgende Beispiel ist eine Objekt Element Syntax, die auch die Syntax der XAML-Inhalts Eigenschaft enthält. Der innere Text, der in enthalten ist, wird verwendet <xref:System.Windows.Controls.TextBox> , um die XAML-Inhalts Eigenschaft festzulegen <xref:System.Windows.Controls.TextBox.Text%2A> .  
  
 [!code-xaml[XAMLOvwSupport#ThisIsATextBox](~/samples/snippets/csharp/VS_Snippets_Wpf/XAMLOvwSupport/CSharp/Page1.xaml#thisisatextbox)]  
  
### <a name="content-models"></a>Inhalts Modelle  
 Eine Klasse unterstützt möglicherweise eine Verwendung als XAML-Objekt Element in Bezug auf die Syntax, dieses Element funktioniert jedoch nur ordnungsgemäß in einer Anwendung oder einer Seite, wenn es an einer erwarteten Position eines gesamten Inhalts Modells oder einer Elementstruktur platziert wird. Beispielsweise sollte eine <xref:System.Windows.Controls.MenuItem> in der Regel nur als untergeordnetes Element einer <xref:System.Windows.Controls.Primitives.MenuBase> abgeleiteten Klasse, z. b., platziert werden <xref:System.Windows.Controls.Menu> . Inhalts Modelle für bestimmte Elemente werden als Teil der Hinweise auf die Klassen Seiten für Steuerelemente und andere [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Klassen dokumentiert, die als XAML-Elemente verwendet werden können.  
  
<a name="properties_of_object_elements"></a>
## <a name="properties-of-object-elements"></a>Eigenschaften von Objekt Elementen  
 Eigenschaften in XAML werden durch eine Vielzahl von Syntax Möglichkeiten festgelegt. Welche Syntax für eine bestimmte Eigenschaft verwendet werden kann, hängt von den zugrunde liegenden typsystemmerkmalen der Eigenschaft ab, die Sie festlegen.  
  
 Wenn Sie Werte für Eigenschaften festlegen, fügen Sie Objekten Funktionen oder Eigenschaften hinzu, wie Sie im Laufzeitobjekt Diagramm vorhanden sind. Der ursprüngliche Zustand des erstellten Objekts aus einem-Objekt Element basiert auf dem Parameter losen konstruktorverhalten. In der Regel verwendet Ihre Anwendung etwas anderes als eine vollständig Standard Instanz eines beliebigen Objekts.  
  
<a name="attribute_syntax_properties"></a>
## <a name="attribute-syntax-properties"></a>Attributsyntax (Eigenschaften)  
 Die Attribut Syntax ist die XAML-Markup Syntax, mit der ein Wert für eine Eigenschaft festgelegt wird, indem ein Attribut für ein vorhandenes Objekt Element deklariert wird. Der Attribut Name muss mit dem CLR-Elementnamen der-Eigenschaft der-Klasse, die das relevante Object-Element sichert, identisch sein. Auf den Attributnamen folgt ein Zuweisungs Operator (=). Der Attribut Wert muss eine in Anführungszeichen eingeschlossene Zeichenfolge sein.  
  
> [!NOTE]
> Sie können abwechselnde Anführungszeichen verwenden, um ein literales Anführungszeichen innerhalb eines Attributs zu platzieren. Beispielsweise können Sie einfache Anführungszeichen als Mittel zum Deklarieren einer Zeichenfolge verwenden, die ein doppeltes Anführungszeichen enthält. Unabhängig davon, ob Sie einfache oder doppelte Anführungszeichen verwenden, sollten Sie ein entsprechendes Paar zum Öffnen und Schließen der Zeichenfolge für den Attribut Wert verwenden. Es gibt auch Escapesequenzen oder andere Techniken zum Umgehen von Zeichen Einschränkungen, die von einer bestimmten XAML-Syntax auferlegt werden. Siehe [XML-Zeichen Entitäten und XAML](../../../desktop-wpf/xaml-services/xml-character-entities.md).  
  
 Damit eine Eigenschaft über die Attribut Syntax festgelegt werden kann, muss sie öffentlich sein und beschreibbar sein. Der Wert der Eigenschaft im Unterstützungs-Typsystem muss ein Werttyp oder ein Verweistyp sein, der beim Zugriff auf den entsprechenden Sicherungstyp von einem XAML-Prozessor instanziiert oder referenziert werden kann.  
  
 Bei WPF-XAML-Ereignissen muss das Ereignis, auf das als Attribut Name verwiesen wird, öffentlich sein und über einen öffentlichen Delegaten verfügen.  
  
 Die Eigenschaft oder das Ereignis muss ein Member der Klasse oder Struktur sein, die vom enthaltenden Objekt Element instanziiert wird.  
  
### <a name="processing-of-attribute-values"></a>Verarbeiten von Attributwerten  
 Der Zeichen folgen Wert, der in den öffnenden und schließenden Anführungszeichen enthalten ist, wird von einem XAML-Prozessor verarbeitet. Bei-Eigenschaften wird das Standard Verarbeitungs Verhalten durch den Typ der zugrunde liegenden CLR-Eigenschaft bestimmt.  
  
 Der Attribut Wert wird mithilfe der folgenden Verarbeitungsreihenfolge von einem der folgenden Werte aufgefüllt:  
  
1. Wenn der XAML-Prozessor auf eine geschweifte Klammer oder ein Objekt Element trifft, das von abgeleitet <xref:System.Windows.Markup.MarkupExtension> wird, wird die referenzierte Markup Erweiterung zuerst ausgewertet, anstatt den Wert als Zeichenfolge zu verarbeiten, und das von der Markup Erweiterung zurückgegebene Objekt wird als Wert verwendet. In vielen Fällen handelt es sich bei dem Objekt, das von einer Markup Erweiterung zurückgegeben wird, um einen Verweis auf ein vorhandenes Objekt oder um einen Ausdruck, der die Auswertung bis zur Laufzeit auswertet und kein neu instanziierenes Objekt ist.  
  
2. Wenn die Eigenschaft mit einem attributierten deklariert wird <xref:System.ComponentModel.TypeConverter> oder der Werttyp dieser Eigenschaft mit einem attributierten deklariert wird <xref:System.ComponentModel.TypeConverter> , wird der Zeichen folgen Wert des Attributs als Konvertierungs Eingabe an den Typkonverter übermittelt, und der Konverter gibt eine neue Objektinstanz zurück.  
  
3. Wenn keine vorhanden ist <xref:System.ComponentModel.TypeConverter> , wird versucht, eine direkte Konvertierung in den Eigenschaftentyp auszuführen. Diese abschließende Ebene ist eine direkte Konvertierung bei dem Parser-systemeigenen Wert zwischen XAML-sprach primitiven Typen oder eine Überprüfung der Namen von benannten Konstanten in einer Enumeration (der Parser greift dann auf die übereinstimmenden Werte zu).  
  
#### <a name="enumeration-attribute-values"></a>Enumerationsattributwerte  
 Enumerationen in XAML werden intrinsisch von XAML-Parser verarbeitet, und die Member einer Enumeration sollten durch Angabe des Zeichen folgen Namens einer der benannten Konstanten der Enumeration angegeben werden.  
  
 Für nicht-Flag-Enumerationswerte besteht das Native Verhalten darin, die Zeichenfolge eines Attribut Werts zu verarbeiten und in einen der Enumerationswerte aufzulösen. Sie geben die Enumeration nicht in der *formatenumeration*an. - *Wert*, wie im Code. Stattdessen geben Sie nur den *Wert*an, und die *Enumeration* wird durch den Typ der Eigenschaft abgeleitet, die Sie festlegen. Wenn Sie ein Attribut in der- *Enumeration*angeben. *Wertformular* , das nicht ordnungsgemäß aufgelöst wird.  
  
 Bei gekennzeichneten Enumerationen basiert das Verhalten auf der- <xref:System.Enum.Parse%2A?displayProperty=nameWithType> Methode. Sie können mehrere Werte für eine flagweise Enumeration angeben, indem Sie die einzelnen Werte durch ein Komma voneinander trennen. Enumerationswerte, die nicht flagweise sind, können jedoch nicht kombiniert werden. Beispielsweise können Sie nicht die Komma Syntax verwenden, um zu versuchen, eine zu erstellen <xref:System.Windows.Trigger> , die mehrere Bedingungen einer Enumeration vom Typ nonflag bearbeitet:  
  
```xaml  
<!--This will not compile, because Visibility is not a flagwise enumeration.-->  
...  
<Trigger Property="Visibility" Value="Collapsed,Hidden">  
  <Setter ... />  
</Trigger>  
...  
```  
  
 Flagweise Enumerationen, die Attribute unterstützen, die in XAML festgelegt werden können, sind in WPF selten. Eine solche Enumeration ist jedoch <xref:System.Windows.Media.StyleSimulations> . Sie könnten z. b. die durch Kommas getrennte Flag-Attribut Syntax verwenden, um das in den Hinweisen für die-Klasse bereitgestellte Beispiel zu ändern <xref:System.Windows.Documents.Glyphs> `StyleSimulations = "BoldSimulation"` . könnte z `StyleSimulations = "BoldSimulation,ItalicSimulation"` . b. werden. <xref:System.Windows.Input.KeyBinding.Modifiers%2A?displayProperty=nameWithType>eine andere Eigenschaft, bei der mehr als ein Enumerationswert angegeben werden kann. Diese Eigenschaft ist jedoch ein Sonderfall, da die <xref:System.Windows.Input.ModifierKeys> Enumeration ihren eigenen Typkonverter unterstützt. Der Typkonverter für Modifizierer verwendet ein Pluszeichen (+) als Trennzeichen anstelle eines Kommas (,). Diese Konvertierung unterstützt die herkömmlichere Syntax zur Darstellung von Tastenkombinationen in der Microsoft Windows-Programmierung, z. b. "Strg + Alt".  
  
### <a name="properties-and-event-member-name-references"></a>Verweise auf Eigenschaften und Namen von Ereignis Membern  
 Wenn Sie ein Attribut angeben, können Sie auf eine beliebige Eigenschaft oder ein Ereignis verweisen, das als Member des CLR-Typs vorhanden ist, den Sie für das enthaltende Objekt Element instanziiert haben.  
  
 Oder Sie können unabhängig vom enthaltenden Objekt Element auf eine angefügte Eigenschaft oder ein angefügtes Ereignis verweisen. (Angefügte Eigenschaften werden in einem zukünftigen Abschnitt erläutert.)  
  
 Sie können auch ein beliebiges Ereignis aus jedem Objekt benennen, auf das über den Standard Namespace mit einem *Typnamen*zugegriffen werden kann. teilweise qualifizierter *Ereignis* Name; Diese Syntax unterstützt das Anfügen von Handlern für Routing Ereignisse, bei denen der Handler das Routing von Ereignissen aus untergeordneten Elementen verarbeiten soll, aber das übergeordnete Element verfügt nicht auch über dieses Ereignis in der Members-Tabelle. Diese Syntax ähnelt der Syntax des angefügten Ereignisses, aber das Ereignis hier ist kein true angefügtes Ereignis. Stattdessen verweisen Sie auf ein Ereignis mit einem qualifizierten Namen. Weitere Informationen finden Sie unter [Übersicht über Routingereignisse](routed-events-overview.md).  
  
 In einigen Szenarios werden Eigenschaftsnamen manchmal als Wert eines Attributs und nicht als Attribut Name bereitgestellt. Dieser Eigenschaftsname kann auch Qualifizierer einschließen, wie z. b. die Eigenschaft, die im Formular Besitzer *Type*angegeben ist. *dependencypropertyname*. Dieses Szenario kommt häufig beim Schreiben von Stilen oder Vorlagen in XAML vor. Die Verarbeitungs Regeln für Eigenschaftsnamen, die als Attribut Wert bereitgestellt werden, unterscheiden sich voneinander und werden durch den Typ der festzulegenden Eigenschaft oder durch das Verhalten bestimmter WPF-Subsysteme gesteuert. Weitere Informationen finden Sie unter Erstellen von Formaten [und](../../../desktop-wpf/fundamentals/styles-templates-overview.md)Vorlagen.  
  
 Eine weitere Verwendung für Eigenschaftsnamen ist, wenn ein Attribut Wert eine Eigenschafts Eigenschafts Beziehung beschreibt. Diese Funktion wird für die Datenbindung und für Storyboard-Ziele verwendet und wird durch die <xref:System.Windows.PropertyPath> -Klasse und deren Typkonverter ermöglicht. Eine ausführlichere Beschreibung der Such Semantik finden Sie unter [PropertyPath-XAML-Syntax](propertypath-xaml-syntax.md).  
  
<a name="property_element_syntax"></a>
## <a name="property-element-syntax"></a>Eigenschaftenelement-Syntax  
 Die *Syntax von Eigenschafts Elementen* ist eine Syntax, die von den grundlegenden XML-Syntax Regeln für Elemente abweicht. In XML ist der Wert eines Attributs eine de-facto-Zeichenfolge, wobei die einzige mögliche Variation darin besteht, welches Zeichen folgen Codierungsformat verwendet wird. In XAML können Sie andere Objekt Elemente als Wert einer Eigenschaft zuweisen. Diese Funktion wird durch die Eigenschafts Element Syntax aktiviert. Anstelle der Eigenschaft, die als Attribut innerhalb des Elementtags angegeben wird, wird die Eigenschaft mithilfe eines öffnenden Elementtags in *elementtykename*angegeben. *propertyName* -Formular, der Wert der-Eigenschaft wird in angegeben, und dann wird das Property-Element geschlossen.  
  
 Die Syntax beginnt mit einer linken spitzen Klammer ( \<), followed immediately by the type name of the class or structure that the property element syntax is contained within. This is followed immediately by a single dot (.), then by the name of a property, then by a right angle bracket (> ). Wie bei der Attribut Syntax muss diese Eigenschaft innerhalb der deklarierten öffentlichen Member des angegebenen Typs vorhanden sein. Der Wert, der der Eigenschaft zugewiesen werden soll, ist im Property-Element enthalten. In der Regel wird der Wert als ein oder mehrere Objekt Elemente angegeben, da die Angabe von Objekten als Werte das Szenario ist, mit dem die Eigenschaften Element Syntax adressiert werden soll. Und schließlich ein entsprechendes Schließ Endes Tag, das denselben *elementtykename*angibt. die Kombination aus *propertyName* muss bereitgestellt werden, und zwar in angemessener Schachtelung und mit anderen Element Tags.  
  
 Beispielsweise ist die Syntax des Eigenschafts Elements für die- <xref:System.Windows.FrameworkElement.ContextMenu%2A> Eigenschaft eines <xref:System.Windows.Controls.Button> .  
  
 [!code-xaml[XAMLOvwSupport#ContextMenu](~/samples/snippets/csharp/VS_Snippets_Wpf/XAMLOvwSupport/CSharp/Page1.xaml#contextmenu)]  
  
 Der Wert in einem Property-Element kann auch als innerer Text angegeben werden, in Fällen, in denen der angegebene Eigenschaftentyp ein primitiver Werttyp (z. b.) <xref:System.String> oder eine Enumeration ist, in der ein Name angegeben ist. Diese beiden Verwendungen sind etwas ungewöhnlich, da in jedem dieser Fälle auch eine einfachere Attribut Syntax verwendet werden kann. Ein Szenario zum Auffüllen eines Eigenschafts Elements mit einer Zeichenfolge ist für Eigenschaften, die nicht die XAML-Inhalts Eigenschaft sind, aber immer noch für die Darstellung von UI-Text verwendet werden, und bestimmte leer Raumelemente (z. b. Zeilen Vorschübe) müssen in diesem Benutzeroberflächen Text angezeigt werden. Die Attribut Syntax kann Linefeeds nicht beibehalten, aber die Syntax von Eigenschafts Elementen kann so lange sein, dass eine bedeutende Leerraum Beibehaltung aktiv ist (Ausführliche Informationen finden Sie unter [Leerraum Verarbeitung in XAML](../../../desktop-wpf/xaml-services/white-space-processing.md)). Ein anderes Szenario besteht darin, dass die [x:UID-Direktive](../../../desktop-wpf/xaml-services/xuid-directive.md) auf das Property-Element angewendet werden kann, wodurch der Wert in als Wert markiert wird, der in der WPF-Ausgabe-BAML oder in anderen Techniken lokalisiert werden soll.  
  
 Ein Property-Element wird nicht in der logischen WPF-Struktur dargestellt. Ein Eigenschafts Element ist nur eine bestimmte Syntax zum Festlegen einer Eigenschaft, und ist kein Element, das eine Instanz oder ein Objekt unterstützt. (Ausführliche Informationen zum Konzept der logischen Struktur finden Sie Unterstrukturen [in WPF](trees-in-wpf.md).)  
  
 Bei Eigenschaften, bei denen sowohl Attribut-als auch Eigenschafts Element Syntax unterstützt wird, weisen die beiden Syntaxen im allgemeinen dasselbe Ergebnis auf, obwohl Feinheiten wie die Leerraum Behandlung leicht zwischen Syntaxen variieren können.  
  
<a name="collection_syntax"></a>
## <a name="collection-syntax"></a>Auflistungssyntax  
 Die XAML-Spezifikation erfordert XAML-Prozessor Implementierungen, um Eigenschaften zu identifizieren, bei denen der Werttyp eine Auflistung ist. Die allgemeine Implementierung des XAML-Prozessors in .NET basiert auf verwaltetem Code und CLR und identifiziert Auflistungs Typen mit einem der folgenden:  
  
- Der Typ implementiert <xref:System.Collections.IList> .  
  
- Der Typ implementiert <xref:System.Collections.IDictionary> .  
  
- Der Typ wird von abgeleitet <xref:System.Array> (Weitere Informationen zu Arrays in XAML finden Sie unter [x:Array-Markup Erweiterung](../../../desktop-wpf/xaml-services/xarray-markup-extension.md).)  
  
 Wenn der Typ einer Eigenschaft eine Auflistung ist, muss der abzurufende Auflistungstyp nicht im Markup als Objekt Element angegeben werden. Stattdessen werden die Elemente, die als Elemente in der Auflistung dienen sollen, als ein oder mehrere untergeordnete Elemente des Property-Elements angegeben. Jedes dieser Elemente wird beim Laden zu einem Objekt ausgewertet und der Auflistung hinzugefügt, indem die- `Add` Methode der impliziten Auflistung aufgerufen wird. Die- <xref:System.Windows.Style.Triggers%2A> Eigenschaft von übernimmt z <xref:System.Windows.Style> . b. den spezialisierten Sammlungstyp <xref:System.Windows.TriggerCollection> , der implementiert <xref:System.Collections.IList> . Es ist nicht erforderlich, ein- <xref:System.Windows.TriggerCollection> Objekt Element im Markup zu instanziieren. Stattdessen geben Sie ein oder mehrere <xref:System.Windows.Trigger> Elemente als Elemente innerhalb des `Style.Triggers` Property-Elements an, wobei <xref:System.Windows.Trigger> (oder eine abgeleitete Klasse) der Typ ist, der als Elementtyp für den stark typisierten und impliziten Wert erwartet wird <xref:System.Windows.TriggerCollection> .  
  
 [!code-xaml[XAMLOvwSupport#SyntaxPECollection](~/samples/snippets/csharp/VS_Snippets_Wpf/XAMLOvwSupport/CSharp/Page1.xaml#syntaxpecollection)]  
  
 Eine Eigenschaft kann sowohl ein Auflistungstyp als auch die XAML-Inhalts Eigenschaft für diesen Typ und die abgeleiteten Typen sein, die im nächsten Abschnitt dieses Themas erläutert werden.  
  
 Ein implizites Auflistungs Element erstellt ein Element in der logischen Struktur Darstellung, obwohl es nicht im Markup als Element angezeigt wird. In der Regel führt der Konstruktor des übergeordneten Typs die Instanziierung für die Auflistung aus, die eine seiner Eigenschaften ist, und die anfänglich leere Auflistung wird Teil der Objektstruktur.  
  
> [!NOTE]
> Die generischen Listen-und Wörterbuch Schnittstellen ( <xref:System.Collections.Generic.IList%601> und <xref:System.Collections.Generic.IDictionary%602> ) werden nicht für die Sammlungs Erkennung unterstützt. Allerdings können Sie die- <xref:System.Collections.Generic.List%601> Klasse als Basisklasse verwenden, da Sie <xref:System.Collections.IList> direkt implementiert, oder <xref:System.Collections.Generic.Dictionary%602> als Basisklasse, da Sie direkt implementiert <xref:System.Collections.IDictionary> .  
  
 In den .net-Referenzseiten für Auflistungs Typen wird diese Syntax gelegentlich in den XAML-Syntax Abschnitten als implizite Sammlungs Syntax angegeben.  
  
 Mit Ausnahme des Stamm Elements ist jedes Objekt Element in einer XAML-Datei, das als untergeordnetes Element eines anderen Elements als untergeordnetes Element angezeigt wird, tatsächlich ein Element, bei dem es sich um einen oder beide der folgenden Fälle handelt: ein Member einer impliziten Auflistungs Eigenschaft des übergeordneten Elements oder ein Element, das den Wert der XAML-Inhalts Eigenschaft für das übergeordnete Element angibt (XAML-Inhalts Eigenschaften werden in einem kommenden Abschnitt erläutert). Anders ausgedrückt: die Beziehung zwischen übergeordneten Elementen und untergeordneten Elementen in einer Markup Seite ist tatsächlich ein einzelnes Objekt am Stamm, und jedes Objekt Element unterhalb des Stamms ist entweder eine einzelne Instanz, die einen Eigenschafts Wert des übergeordneten Elements bereitstellt, oder eines der Elemente in einer Auflistung, bei dem es sich auch um einen Auflistungstyp-Eigenschafts Wert des übergeordneten Elements handelt Dieses Single-root-Konzept ist in XML üblich und wird häufig durch das Verhalten von APIs verstärkt, die XAML wie laden <xref:System.Windows.Markup.XamlReader.Load%2A> .  
  
 Das folgende Beispiel ist eine Syntax, bei der das Object-Element für eine Auflistung ( <xref:System.Windows.Media.GradientStopCollection> ) explizit angegeben ist.  
  
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
  
 Beachten Sie, dass es nicht immer möglich ist, die Auflistung explizit zu deklarieren. Wenn Sie z. b. versuchen, <xref:System.Windows.TriggerCollection> explizit im zuvor gezeigten Beispiel zu deklarieren, tritt ein Fehler auf <xref:System.Windows.Style.Triggers%2A> . Die explizite Deklaration der Auflistung erfordert, dass die Auflistungs Klasse einen Parameter losen Konstruktor unterstützen muss und <xref:System.Windows.TriggerCollection> keinen Parameter losen Konstruktor hat.  
  
<a name="xaml_content_properties"></a>
## <a name="xaml-content-properties"></a>XAML-Inhaltseigenschaften  
 Die XAML-Inhalts Syntax ist eine Syntax, die nur für Klassen aktiviert ist, die <xref:System.Windows.Markup.ContentPropertyAttribute> als Teil ihrer Klassen Deklaration angeben. Der <xref:System.Windows.Markup.ContentPropertyAttribute> verweist auf den Eigenschaftsnamen, der die Content-Eigenschaft für diesen Elementtyp (einschließlich abgeleiteter Klassen) ist. Bei der Verarbeitung durch einen XAML-Prozessor werden alle untergeordneten Elemente oder inneren Text, die zwischen den öffnenden und schließenden Tags des Object-Elements gefunden werden, dem Wert der XAML-Inhalts Eigenschaft für dieses Objekt zugewiesen. Sie sind berechtigt, explizite Eigenschaften Elemente für die Content-Eigenschaft anzugeben. diese Verwendung wird jedoch im Allgemeinen nicht in den XAML-Syntax Abschnitten in der .net-Referenz aufgeführt. Das explizite/ausführliche Verfahren hat einen gelegentlichen Wert für die Markup Übersichtlichkeit oder eine Frage des Markup Stils, aber in der Regel ist es eine Inhalts Eigenschaft, das Markup zu optimieren, sodass Elemente, die intuitiv als über-/unterordnungsweise als übergeordnetes Element verwandt sind, direkt eingefügt werden können. Eigenschaften Element Tags für andere Eigenschaften eines Elements werden nicht gemäß einer strengen XAML-Sprachdefinition als "Content" zugewiesen. Sie werden zuvor in der Verarbeitungsreihenfolge des XAML-Parsers verarbeitet und werden nicht als "Content" betrachtet.  
  
### <a name="xaml-content-property-values-must-be-contiguous"></a>XAML-Inhalts Eigenschaftswerte müssen zusammenhängend sein.  
 Der Wert einer XAML-Inhalts Eigenschaft muss entweder vollständig vor oder vollständig nach allen anderen Eigenschafts Elementen für dieses Objekt Element angegeben werden. Dies gilt unabhängig davon, ob der Wert einer XAML-Inhalts Eigenschaft als Zeichenfolge oder als ein oder mehrere-Objekte angegeben wird. Beispielsweise wird das folgende Markup nicht analysiert:  
  
```xaml  
<Button>I am a
  <Button.Background>Blue</Button.Background>  
  blue button</Button>  
```  
  
 Dies ist im Wesentlichen der Fall, wenn diese Syntax mithilfe der Eigenschafts Element Syntax für die Content-Eigenschaft explizit festgelegt wurde, dann wird die Content-Eigenschaft zweimal festgelegt:  
  
```xaml  
<Button>  
  <Button.Content>I am a </Button.Content>  
  <Button.Background>Blue</Button.Background>  
  <Button.Content> blue button</Button.Content>  
</Button>  
```  
  
 Ein ähnliches Beispiel ist, wenn die Content-Eigenschaft eine Auflistung ist und untergeordnete Elemente mit Eigenschafts Elementen vermischt werden:  
  
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
 Um mehr als ein einzelnes Objekt Element als Inhalt zu akzeptieren, muss der Typ der Inhalts Eigenschaft ein Sammlungstyp sein. Ähnlich wie bei der Eigenschafts Element Syntax für Auflistungs Typen müssen von einem XAML-Prozessortypen identifiziert werden, die Sammlungs Typen sind. Wenn ein Element über eine XAML-Inhalts Eigenschaft verfügt und der Typ der XAML-Inhalts Eigenschaft eine Auflistung ist, muss der implizite Sammlungstyp nicht im Markup als Objekt Element angegeben werden, und die XAML-Inhalts Eigenschaft muss nicht als Eigenschafts Element angegeben werden. Daher kann dem offensichtlich Inhalts Modell im Markup nun mehr als ein untergeordnetes Element als Inhalt zugewiesen werden. Im folgenden finden Sie eine Inhalts Syntax für eine <xref:System.Windows.Controls.Panel> abgeleitete Klasse. Alle <xref:System.Windows.Controls.Panel> abgeleiteten Klassen stellen die XAML-Inhalts Eigenschaft als <xref:System.Windows.Controls.Panel.Children%2A> dar, die einen Wert vom Typ erfordert <xref:System.Windows.Controls.UIElementCollection> .  
  
 [!code-xaml[XAMLOvwSupport#SyntaxContent](~/samples/snippets/csharp/VS_Snippets_Wpf/XAMLOvwSupport/CSharp/page5.xaml#syntaxcontent)]  
  
 Beachten Sie, dass weder das Property-Element für <xref:System.Windows.Controls.Panel.Children%2A> noch das-Element für das <xref:System.Windows.Controls.UIElementCollection> im Markup erforderlich ist. Dies ist eine Entwurfs Funktion von XAML, sodass rekursiv enthaltene Elemente, die eine definieren, intuitiver [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] als eine Struktur von untergeordneten Elementen mit direkt über-und untergeordneten Element Beziehungen dargestellt werden, ohne dass es dabei um Eigenschaften-oder Auflistungs Objekte handelt. In der Tat <xref:System.Windows.Controls.UIElementCollection> kann nicht explizit im Markup als Objekt Element explizit angegeben werden. Da die einzige beabsichtigte Verwendung als implizite Auflistung verwendet wird, <xref:System.Windows.Controls.UIElementCollection> macht keinen öffentlichen Parameter losen Konstruktor verfügbar und kann daher nicht als Objekt Element instanziiert werden.  
  
### <a name="mixing-property-elements-and-object-elements-in-an-object-with-a-content-property"></a>Mischen von Eigenschafts Elementen und Objekt Elementen in einem Objekt mit einer Content-Eigenschaft  
 Die XAML-Spezifikation deklariert, dass ein XAML-Prozessor erzwingen kann, dass Objekt Elemente, die zum Ausfüllen der XAML-Inhalts Eigenschaft in einem Objekt Element verwendet werden, zusammenhängend sein müssen und nicht gemischt werden dürfen. Diese Einschränkung für das Mischen von Eigenschaften Elementen und Inhalten wird durch die [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] XAML-Prozessoren erzwungen.  
  
 Sie können ein untergeordnetes Object-Element als erstes unmittelbares Markup innerhalb eines Object-Elements haben. Anschließend können Sie Eigenschaften Elemente einführen. Oder Sie können ein oder mehrere Eigenschaften Elemente, dann den Inhalt und dann weitere Eigenschaften Elemente angeben. Wenn jedoch ein Eigenschaften Element auf den Inhalt folgt, können Sie keinen weiteren Inhalt einführen, Sie können nur Eigenschaften Elemente hinzufügen.  
  
 Diese Anforderungs Anforderung für Inhalt/Eigenschaften Element gilt nicht für inneren Text, der als Inhalt verwendet wird. Allerdings ist es immer noch ein guter Markup Stil, um inneren Text zusammenhängend aufzubewahren, da es schwierig ist, im Markup visuell zu erkennen, wenn die Eigenschaften Elemente mit innerem Text miteinander vermischt werden.  
  
<a name="xaml_namespaces"></a>
## <a name="xaml-namespaces"></a>XAML-Namespaces  
 Keines der vorangehenden Syntax Beispiele hat einen anderen XAML-Namespace als den standardmäßigen XAML-Namespace angegeben. In typischen [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Anwendungen wird der XAML-Standard Namespace als [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Namespace angegeben. Sie können andere XAML-Namespaces als den standardmäßigen XAML-Namespace angeben und dennoch eine ähnliche Syntax verwenden. Wenn eine Klasse den Namen hat, auf die nicht innerhalb des standardmäßigen XAML-Namespace zugegriffen werden kann, muss dem Klassennamen jedoch das Präfix des XAML-Namespace vorangestellt sein, das dem entsprechenden CLR-Namespace zugeordnet ist. Beispielsweise `<custom:Example/>` ist eine Objekt Element Syntax zum Instanziieren einer Instanz der- `Example` Klasse, bei der der CLR-Namespace, der diese Klasse enthält (und möglicherweise die Informationen der externen Assembly, die Unterstützungs Typen enthalten), zuvor dem- `custom` Präfix zugeordnet wurde.  
  
 Weitere Informationen zu XAML-Namespaces finden Sie unter [XAML-Namespaces und Namespace Zuordnung für WPF-XAML](xaml-namespaces-and-namespace-mapping-for-wpf-xaml.md).  
  
<a name="markup_extensions"></a>
## <a name="markup-extensions"></a>Markuperweiterungen  
 XAML definiert eine Markup-Erweiterungs Programmier Entität, die einen Escapezeichen aus der normalen XAML-Prozessor Verarbeitung von Zeichen folgen Attributwerten oder Objekt Elementen ermöglicht und die Verarbeitung einer Unterstützungs Klasse zusichert. Das Zeichen, das eine Markup Erweiterung eines XAML-Prozessors identifiziert, wenn die Attribut Syntax verwendet wird, ist die öffnende geschweifte Klammer ({), gefolgt von einem beliebigen Zeichen, das keine schließende geschweifte Klammer (}) ist. Die erste Zeichenfolge, die auf die öffnende geschweifte Klammer folgt, muss auf die Klasse verweisen, die das jeweilige Erweiterungs Verhalten bereitstellt, wobei der Verweis die Teil Zeichenfolge "Extension" weglassen kann, wenn diese Teil Zeichenfolge Teil des echten Klassen namens ist. Danach kann ein einzelnes Leerzeichen angezeigt werden, und dann wird jedes nachfolgende Zeichen als Eingabe von der Erweiterungs Implementierung verwendet, bis die schließende geschweifte Klammer gefunden wird.  
  
 Die .net XAML-Implementierung verwendet die <xref:System.Windows.Markup.MarkupExtension> abstrakte-Klasse als Grundlage für alle Markup Erweiterungen, die von unterstützt werden, sowie [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] andere Frameworks oder Technologien. Die [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] speziell implementierten Markup Erweiterungen sind häufig dazu gedacht, eine Möglichkeit bereitzustellen, auf andere vorhandene Objekte zu verweisen, oder verzögerte Verweise auf Objekte zu erstellen, die zur Laufzeit ausgewertet werden. Beispielsweise wird eine einfache WPF-Datenbindung durch Angabe der `{Binding}` Markup Erweiterung anstelle des Werts durchgeführt, den eine bestimmte Eigenschaft normalerweise annehmen würde. Viele der WPF-Markup Erweiterungen ermöglichen eine Attribut Syntax für Eigenschaften, bei denen andernfalls eine Attribut Syntax nicht möglich wäre. Beispielsweise ist ein- <xref:System.Windows.Style> Objekt ein relativ komplexer Typ, der eine Reihe von-Objekten und-Eigenschaften enthält. Stile in WPF werden in der Regel als Ressource in einer definiert <xref:System.Windows.ResourceDictionary> . Anschließend wird auf eine der beiden WPF-Markup Erweiterungen verwiesen, die eine Ressource anfordern. Die Markup Erweiterung gibt die Auswertung des Eigenschafts Werts zu einer Ressourcen Suche zurück und ermöglicht die Bereitstellung des Werts der <xref:System.Windows.FrameworkElement.Style%2A> Eigenschaft, die den Typ annimmt <xref:System.Windows.Style> , in der Attribut Syntax, wie im folgenden Beispiel gezeigt:  
  
 `<Button Style="{StaticResource MyStyle}">My button</Button>`  
  
 Hier `StaticResource` identifiziert die- <xref:System.Windows.StaticResourceExtension> Klasse, die die Implementierung der Markup Erweiterung bereitstellt. Die nächste Zeichenfolge `MyStyle` wird als Eingabe für den nicht <xref:System.Windows.StaticResourceExtension> Standardkonstruktor verwendet, wobei der Parameter, der aus der Erweiterungs Zeichenfolge entnommen wurde, die angeforderte deklariert <xref:System.Windows.ResourceKey> . `MyStyle`Es wird erwartet, dass es sich um den [x:Key](../../../desktop-wpf/xaml-services/xkey-directive.md) -Wert einer handelt, die <xref:System.Windows.Style> als Ressource definiert ist. Die Verwendung der [statikresource-Markup Erweiterung](staticresource-markup-extension.md) fordert an, dass die Ressource verwendet wird, um den <xref:System.Windows.Style> Eigenschafts Wert über die statische Ressourcen Suchlogik zur Ladezeit bereitzustellen.  
  
 Weitere Informationen über Markuperweiterungen finden Sie unter [Markuperweiterungen und WPF XAML](markup-extensions-and-wpf-xaml.md). Einen Verweis auf Markup Erweiterungen und andere XAML-Programmierfunktionen, die in der allgemeinen .net XAML-Implementierung aktiviert sind, finden Sie unter [XAML-Namespace (x:) Sprach Features](../../../desktop-wpf/xaml-services/namespace-language-features.md). Informationen zu WPF-spezifischen Markup Erweiterungen finden Sie unter [WPF-XAML-Erweiterungen](wpf-xaml-extensions.md).  
  
<a name="attached_properties"></a>
## <a name="attached-properties"></a>Angefügte Eigenschaften  
 Angefügte Eigenschaften sind ein in XAML eingeführte Programmier Konzept, bei dem Eigenschaften im Besitz eines bestimmten Typs sein können, aber als Attribute oder Eigenschaften Elemente für jedes Element festgelegt werden. Das primäre Szenario, für das angefügte Eigenschaften vorgesehen sind, besteht darin, untergeordneten Elementen in einer Markup Struktur das Melden von Informationen an ein übergeordnetes Element zu ermöglichen, ohne dass ein umfassend frei gegebenes Objektmodell über alle Elemente hinweg Umgekehrt können von übergeordneten Elementen angefügte Eigenschaften verwendet werden, um Informationen an untergeordnete Elemente zu melden. Weitere Informationen zum Zweck angefügter Eigenschaften und zum Erstellen eigener angefügter Eigenschaften finden Sie unter [Übersicht über angefügte Eigenschaften](attached-properties-overview.md).  
  
 Angefügte Eigenschaften verwenden eine Syntax, die der Eigenschafts Element Syntax sehr ähnlich ist, da Sie auch einen *Typnamen*angeben. *propertyName* -Kombination. Es gibt zwei wichtige Unterschiede:  
  
- Sie können den *Typnamen*verwenden. *propertyName* -Kombination, auch wenn eine angefügte Eigenschaft durch Attribut Syntax festgelegt wird. Angefügte Eigenschaften sind der einzige Fall, bei dem das qualifizieren des Eigenschafts namens eine Anforderung in einer Attribut Syntax ist.  
  
- Sie können auch die Eigenschaften Element Syntax für angefügte Eigenschaften verwenden. Bei der typischen Eigenschafts Element Syntax ist der von Ihnen angegebene *Typname* jedoch das Object-Element, das das Property-Element enthält. Wenn Sie auf eine angefügte Eigenschaft verweisen, ist der *Typname* die Klasse, die die angefügte Eigenschaft definiert, nicht das enthaltende Objekt Element.  
  
<a name="attached_events"></a>
## <a name="attached-events"></a>Angefügte Ereignisse  
 Angefügte Ereignisse sind ein weiteres Programmier Konzept, das in XAML eingeführt wurde, in dem Ereignisse von einem bestimmten Typ definiert werden können, aber Handler können an jedes beliebige Objekt Element angefügt werden. In der WOF-Implementierung ist oft der Typ, der ein angefügtes Ereignis definiert, ein statischer Typ, der einen Dienst definiert, und manchmal werden diese angefügten Ereignisse von einem Alias Ereignis Alias in Typen verfügbar gemacht, die den Dienst verfügbar machen. Handler für angefügte Ereignisse werden durch Attribut Syntax angegeben. Wie bei angefügten Ereignissen wird die Attribut Syntax für angefügte Ereignisse so erweitert, dass ein *Typname*zulässig ist. Verwendung von *EventName* , wobei *tyadapame* die Klasse ist, die `Add` - `Remove` Ereignishandleraccessoren für die angefügte Ereignis Infrastruktur bereitstellt, und *EventName* ist der Ereignis Name.  
  
<a name="anatomy_of_a_xaml_page_root_element"></a>
## <a name="anatomy-of-a-xaml-root-element"></a>Anatomie eines XAML-Stamm Elements  
 Die folgende Tabelle zeigt ein typisches XAML-Stamm Element, das die spezifischen Attribute eines Stamm Elements anzeigt:  
  
|||  
|-|-|  
|`<Page`|Öffnen des Object-Elements des Root-Elements|  
|`xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"`|Der Standard- [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] XAML-Namespace ()|  
|`xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"`|XAML-Namespace der XAML-Sprache|  
|`x:Class="ExampleNamespace.ExampleCode"`|Die Deklaration der partiellen Klasse, die das Markup mit allen für die partiellen Klasse definierten Code Behind-Klassen verbindet|  
|`>`|Das Ende des Objekt Elements für den Stamm. Das Objekt ist noch nicht geschlossen, da das Element untergeordnete Elemente enthält.|  
  
<a name="optional_and_nonrecommended_xaml_usages"></a>
## <a name="optional-and-nonrecommended-xaml-usages"></a>Optionale und nicht empfohlene XAML-Verwendungen  
 In den folgenden Abschnitten werden XAML-Verwendungen beschrieben, die in technischer Hinsicht von XAML-Prozessoren unterstützt werden, die jedoch ausführlichkeits-oder andere ästhetische Probleme mit sich bringen, die bei der Entwicklung von Anwendungen, die XAML-Quellen enthalten, eine Benutzer lesbare XAML-Datei  
  
### <a name="optional-property-element-usages"></a>Optionale Verwendung von Eigenschafts Elementen  
 Optionale Verwendung von Eigenschafts Elementen schließt das explizite Schreiben von Element Inhalts Eigenschaften ein, die vom XAML-Prozessor als implizit betrachtet werden. Wenn Sie z. b. den Inhalt eines deklarieren <xref:System.Windows.Controls.Menu> , können Sie festlegen, dass die <xref:System.Windows.Controls.ItemsControl.Items%2A> -Auflistung der <xref:System.Windows.Controls.Menu> als `<Menu.Items>` Eigenschaftenelementtag explizit deklariert und <xref:System.Windows.Controls.MenuItem> innerhalb von `<Menu.Items>` platziert wird, anstatt das implizite XAML-Prozessor Verhalten zu verwenden, dass alle untergeordneten Elemente von <xref:System.Windows.Controls.Menu> eine sein müssen <xref:System.Windows.Controls.MenuItem> und in der Auflistung platziert werden <xref:System.Windows.Controls.ItemsControl.Items%2A> . Manchmal können die optionalen Verwendungen dabei helfen, die Objektstruktur visuell zu verdeutlichen, wie im Markup dargestellt. Manchmal kann eine explizite Verwendung eines Eigenschafts Elements Markup vermeiden, das technisch funktional, aber visuell verwirrend ist, wie z. b. geschachtelte Markup Erweiterungen innerhalb eines Attribut Werts.  
  
### <a name="full-typenamemembername-qualified-attributes"></a>Vollständige Typname. Mitgliedschafts Name qualifizierte Attribute  
 Der *Typname*. das Formular für *Mitgliedsnamen* für ein Attribut funktioniert tatsächlich eher universell als nur der Routing Ereignis Fall. In anderen Situationen ist das Formular jedoch überflüssig, und Sie sollten es vermeiden, wenn dies nur aus Gründen der Markup-und Lesbarkeit erfolgt. Im folgenden Beispiel ist jeder der drei Verweise auf das- <xref:System.Windows.Controls.Control.Background%2A> Attribut vollständig äquivalent:  
  
 [!code-xaml[XAMLOvwSupport#TypeNameProp](~/samples/snippets/csharp/VS_Snippets_Wpf/XAMLOvwSupport/CSharp/page8.xaml#typenameprop)]  
  
 `Button.Background`funktioniert, weil die qualifizierte Suche für diese Eigenschaft für <xref:System.Windows.Controls.Button> erfolgreich ist ( <xref:System.Windows.Controls.Control.Background%2A> wurde von Control geerbt) und <xref:System.Windows.Controls.Button> die Klasse des Object-Elements oder einer Basisklasse ist. `Control.Background`funktioniert, weil die <xref:System.Windows.Controls.Control> -Klasse tatsächlich definiert <xref:System.Windows.Controls.Control.Background%2A> und <xref:System.Windows.Controls.Control> eine <xref:System.Windows.Controls.Button> Basisklasse ist.  
  
 Der folgende *Typname*ist jedoch. das Formular für den *Mitgliedsnamen* funktioniert nicht und wird daher als kommentiert angezeigt:  
  
 [!code-xaml[XAMLOvwSupport#TypeNameBadProp](~/samples/snippets/csharp/VS_Snippets_Wpf/XAMLOvwSupport/CSharp/page8.xaml#typenamebadprop)]  
  
 <xref:System.Windows.Controls.Label>ist eine andere abgeleitete Klasse von <xref:System.Windows.Controls.Control> , und wenn Sie `Label.Background` in einem- <xref:System.Windows.Controls.Label> Objekt Element angegeben haben, hätte diese Verwendung funktioniert. Da jedoch <xref:System.Windows.Controls.Label> nicht die Klasse oder Basisklasse von ist <xref:System.Windows.Controls.Button> , wird das angegebene XAML-Prozessor Verhalten `Label.Background` als angefügte Eigenschaft verarbeitet. `Label.Background`ist keine verfügbare angefügte Eigenschaft, und diese Verwendung schlägt fehl.  
  
### <a name="basetypenamemembername-property-elements"></a>basetypame. Membership Name-Eigenschafts Elemente  
 Analog zur Art des *Typnamens*. das Formular für den *Mitgliednamen* funktioniert für die Attribut Syntax, einen *basety-Name*. die Syntax des *Mitgliedschafts namens* funktioniert für die Eigenschafts Element Syntax. Beispielsweise funktioniert die folgende Syntax:  
  
 [!code-xaml[XAMLOvwSupport#GoofyPE](~/samples/snippets/csharp/VS_Snippets_Wpf/XAMLOvwSupport/CSharp/page8.xaml#goofype)]  
  
 Hier wurde das Property-Element als angegeben, `Control.Background` Obwohl das Property-Element in enthalten war `Button` .  
  
 Aber genau wie *tygtame*. Formular für *mitgliedschaftsnamen* für Attribute, *basetyname*. der *Name der Mitgliedschaft* ist im Markup unzureichend, und Sie sollten ihn vermeiden.  
  
## <a name="see-also"></a>Siehe auch

- [Übersicht über XAML (WPF)](../../../desktop-wpf/fundamentals/xaml.md)
- [XAML-Namespace (x:) Sprachfunktionen](../../../desktop-wpf/xaml-services/namespace-language-features.md)
- [WPF-XAML-Erweiterungen](wpf-xaml-extensions.md)
- [Übersicht über Abhängigkeitseigenschaften](dependency-properties-overview.md)
- [TypeConverter und XAML](typeconverters-and-xaml.md)
- [XAML- und benutzerdefinierte Klassen für WPF](xaml-and-custom-classes-for-wpf.md)
