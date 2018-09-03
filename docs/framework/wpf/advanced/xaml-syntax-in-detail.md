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
ms.openlocfilehash: eabb9c84824a4604319a346612e84563abaf2b76
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/03/2018
ms.locfileid: "43485728"
---
# <a name="xaml-syntax-in-detail"></a>Ausführliche Erläuterung der XAML-Syntax
In diesem Thema definiert die Bedingungen, die zum beschreiben die Elemente der XAML-Syntax verwendet werden. Diese Begriffe werden häufig in den restlichen dieser Dokumentation wird sowohl für WPF-Dokumentation verwendet, insbesondere und für die anderen Frameworks, die XAML oder die grundlegenden XAML-Konzepte, die aktiviert, indem die XAML-sprachunterstützung auf der Ebene "System.xaml" verwenden. Dieses Thema baut auf die grundlegende Terminologie eingeführt, die im Thema [XAML Overview (WPF)](../../../../docs/framework/wpf/advanced/xaml-overview-wpf.md).  
  

  
<a name="the_xaml_language_specification"></a>   
## <a name="the-xaml-language-specification"></a>Der XAML-Sprachspezifikation  
 Die XAML-syntaxterminologie, die hier definierten wird auch definiert, oder der XAML-Sprachspezifikation auf die verwiesen wird. XAML ist eine auf XML basierende Sprache und folgt oder XML-strukturellen Regeln erweitert. Einige der Begriffe gemeinsam verwendet wird, oder basiert darauf, dass die Terminologie, die häufig verwendet, wenn der XML-Sprache oder das XML-Document Object Model beschreibt.  
  
 Weitere Informationen über die XAML-Sprachspezifikation herunterladen [ \[MS-XAML-\] ](https://go.microsoft.com/fwlink/?LinkId=114525) aus dem Microsoft Download Center.  
  
<a name="xaml_and_clr"></a>   
## <a name="xaml-and-clr"></a>XAML und CLR  
 XAML ist eine Markupsprache. Die [!INCLUDE[TLA#tla_clr](../../../../includes/tlasharptla-clr-md.md)], wie soeben anhand ihres Namens, Ausführung zur Laufzeit ermöglicht. XAML ist nicht selbst einer der allgemeinen Sprachen, die direkt von der CLR-Laufzeit verwendet wird. Stattdessen können Sie XAML vorstellen als einen eigenen-Typsystem unterstützt. Das bestimmte XAML-Analysesystem, das von WPF verwendet wird, basiert auf der CLR und CLR-Typsystem. CLR-Typen, um eine Darstellung zur Laufzeit zu instanziieren, bei der Analyse der XAML für WPF werden XAML-Typen zugeordnet. Aus diesem Grund enthält der Rest der Erläuterung der Syntax in diesem Dokument Verweise auf die CLR-Typsystems, obwohl die entsprechende Syntaxdiskussionen in der XAML-Sprachspezifikation nicht der Fall ist. (Pro die Ebene des XAML-Spezifikation können XAML-Typen zugeordnet werden alle anderen Typ Systeme, die keine werden von der CLR, aber voraus, dass die Erstellung und Verwendung eines anderen XAML-parsers.)  
  
#### <a name="members-of-types-and-class-inheritance"></a>Member von Typen und Klassenvererbung  
 Eigenschaften und Ereignisse, die als als XAML-Member, der angezeigt werden eine [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] geben häufig von Basistypen geerbt werden. Betrachten Sie beispielsweise die in diesem Beispiel: `<Button Background="Blue" .../>`. Die <xref:System.Windows.Controls.Control.Background%2A> Eigenschaft ist nicht direkt deklarierte Eigenschaft auf die <xref:System.Windows.Controls.Button> Klasse, würden Sie auf die Klassendefinition, Reflektionsergebnisse oder der Dokumentation zu suchen. Stattdessen <xref:System.Windows.Controls.Control.Background%2A> wird von der Basisklasse geerbt <xref:System.Windows.Controls.Control> Klasse.  
  
 Die Klasse Vererbungsverhalten [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] XAML-Elementen ist ein bedeutender Unterschied aus einem Schema erzwungenen Interpretation von XML-Markup. Klassenvererbung kann komplex werden, insbesondere dann, wenn zwischen Klassen abstrakt sind, oder wenn Schnittstellen beteiligt sind. Dies ist ein Grund, die der Satz von XAML-Elemente und die zulässigen Attribute schwierig ist, die darstellen, die exakt und vollständig mit der Schematypen in der Regel für die verwendeten [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] Programmierung, z. B. DTD oder des XSD-Format. Ein weiterer Grund ist, Erweiterbarkeit und Typzuordnung Funktionen der XAML-Sprache selbst ausgeschlossen Vollständigkeit für alle festen Darstellung der die zulässigen Typen und Member.  
  
<a name="object_element_syntax"></a>   
## <a name="object-element-syntax"></a>Objektelementsyntax  
 *-Objekt Eigenschaftselementsyntax* ist die Syntax der XAML-Markup, das eine CLR-Klasse oder Struktur instanziiert werden, durch die Deklaration eines XML-Elements. Diese Syntax ähnelt die Syntax der anderer Markupsprachen, z. B. HTML. Objektelementsyntax beginnt mit einer linken spitzen Klammer (\<) unmittelbar folgen der Typname der Klasse oder Struktur, die instanziiert wird. NULL oder mehr Leerzeichen können folgen, den Typnamen, und NULL oder mehr Attribute können ebenfalls deklariert werden auf das Object-Element, klicken Sie mit der ein oder mehrere Leerzeichen, trennen Sie jedes Attributnamen = "Wert"-Paar. Schließlich muss eine der folgenden erfüllt sein:  
  
-   Das Element und der Tag müssen durch einen Schrägstrich (/), und unmittelbar danach eine öffnende spitze Klammer (>) geschlossen werden.  
  
-   Das öffnende Tag muss durch eine schließende spitze Klammer (>) abgeschlossen werden. Andere Objektelementen, Eigenschaftenelementen oder inneren Text kann das öffnende Tag folgen. Genau hier enthalten sind die Inhalte werden möglicherweise wird durch das Objektmodell des Elements in der Regel eingeschränkt. Das entsprechende schließende Tag für das Object-Element muss außerdem vorhanden sind, in die richtige Schachtelung und mit anderen Paare mit öffnenden und schließenden Tag gleichmäßig zu verteilen.  
  
 XAML-Implementierung von .NET verfügt über einen Satz von Regeln, die Typen, Attribute, Eigenschaften oder Ereignisse und XAML-Namespaces zu CLR-Namespaces sowie die Assembly in Object-Elementen zuzuordnen. Für WPF und .NET Framework XAML-Objektelemente zuordnen [!INCLUDE[TLA#tla_net](../../../../includes/tlasharptla-net-md.md)] Typen wie definiert in Assemblys verwiesen wird, und die Attribute für Mitglieder dieser Typen. Wenn Sie einen CLR-Typ in XAML verweisen, haben Sie Zugriff auf die geerbten Member dieses Typs auch.  
  
 Im folgende Beispiel wird z. B. Objektelement-Syntax, die instanziiert eine neue Instanz der der <xref:System.Windows.Controls.Button> -Klasse und gibt auch eine <xref:System.Windows.FrameworkElement.Name%2A> -Attribut und einen Wert für dieses Attribut:  
  
 [!code-xaml[XAMLOvwSupport#SyntaxOE](../../../../samples/snippets/csharp/VS_Snippets_Wpf/XAMLOvwSupport/CSharp/Page1.xaml#syntaxoe)]  
  
 Im folgende Beispiel wird die Objektelement-Syntax, die auch die Syntax des XAML-Inhaltseigenschaft enthält. Der innere Text enthaltenen wird verwendet, um das Festlegen der <xref:System.Windows.Controls.TextBox> XAML-Inhaltseigenschaft, <xref:System.Windows.Controls.TextBox.Text%2A>.  
  
 [!code-xaml[XAMLOvwSupport#ThisIsATextBox](../../../../samples/snippets/csharp/VS_Snippets_Wpf/XAMLOvwSupport/CSharp/Page1.xaml#thisisatextbox)]  
  
### <a name="content-models"></a>Inhaltsmodelle  
 Eine Klasse kann eine Verwendung als ein XAML-Objektelement im Hinblick auf die Syntax unterstützt, aber dieses Element wird in einer Anwendung oder Seite nur einwandfrei, wenn sie in der gesamten Modell oder einer allgemeinen Elementstruktur einer erwarteten Position platziert wird. Z. B. eine <xref:System.Windows.Controls.MenuItem> sollten in der Regel nur als untergeordnetes Element angeordnet werden eine <xref:System.Windows.Controls.Primitives.MenuBase> abgeleitete Klasse wie z. B. <xref:System.Windows.Controls.Menu>. Content-Modelle für bestimmte Elemente sind als Teil der Hinweise auf den Klassenseiten für Steuerelemente und andere dokumentiert [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Klassen, die als XAML-Elemente verwendet werden können.  
  
<a name="properties_of_object_elements"></a>   
## <a name="properties-of-object-elements"></a>Eigenschaften von Objektelementen  
 Eigenschaften in XAML werden durch verschiedene syntaxmöglichkeiten festgelegt. Die Syntax für eine bestimmte Eigenschaft verwendet werden kann, hängt basierend auf den zugrunde liegenden Typ System Merkmalen der Eigenschaft, die Sie festlegen.  
  
 Wenn Sie die Werte der Eigenschaften festlegen, fügen Sie Funktionen oder Merkmale auf Objekte wie sie in der Laufzeit-Objektdiagramm vorhanden sind. Der anfängliche Zustand des erstellten Objekts aus einem Objektelement basiert auf das Standardverhalten für den Konstruktor. In der Regel wird die Anwendung einen anderen Wert als Standardinstanz eines Objekts verwenden.  
  
<a name="attribute_syntax_properties"></a>   
## <a name="attribute-syntax-properties"></a>Attributsyntax (Eigenschaften)  
 Die Attributsyntax ist die XAML-Markup-Syntax, die einen Wert für eine Eigenschaft legt fest, indem Sie ein Attribut auf ein vorhandenes Objektelement deklarieren. Der Attributname muss die CLR-Membername der Eigenschaft der Klasse übereinstimmen, die die relevante Objektelement unterstützt. Ein Zuweisungsoperator (=) der Attributnamen folgt. Der Attributwert muss eine Zeichenfolge in Anführungszeichen eingeschlossen sein.  
  
> [!NOTE]
>  Sie können die abwechselnde Anführungszeichen verwenden, um ein literales Anführungszeichen innerhalb eines Attributs zu platzieren. Beispielsweise können Sie einfache Anführungszeichen als Mittel verwenden, eine Zeichenfolge zu deklarieren, die darin enthaltenen ein doppeltes Anführungszeichen enthält. Ob Sie einfache oder doppelte Anführungszeichen verwenden, sollten Sie ein übereinstimmendes Paar verwenden, für das Öffnen und schließen die Attribut-Wert-Zeichenfolge. Es stehen auch Escape-Sequenzen oder andere Methoden zur Umgehung von Zeichen von sicherheitseinschränkungen durch die jede bestimmte XAML-Syntax. Finden Sie unter [XML-Zeichenentitäten und XAML](../../../../docs/framework/xaml-services/xml-character-entities-and-xaml.md).  
  
 Um mithilfe von Attributsyntax festgelegt werden, eine Eigenschaft muss öffentlich sein und muss beschreibbar sein. Der Wert der Eigenschaft im Unterstützungstypsystem muss ein Werttyp sein oder bei muss werden ein Verweistyp, der instanziiert werden kann oder die von einem XAML-Prozessor verwiesen wird, wenn der Zugriff auf den entsprechenden Typ.  
  
 Für WPF XAML-Ereignisse muss das Ereignis, das als ein Attribut verwiesen wird öffentlich sein und einen öffentlichen Delegaten haben.  
  
 Die Eigenschaft oder das Ereignis muss ein Member der Klasse oder Struktur, die durch das Container-Objektelement instanziiert wird.  
  
### <a name="processing-of-attribute-values"></a>Verarbeiten von Attributwerten  
 Der Zeichenfolgenwert, der innerhalb des öffnenden und schließenden Anführungszeichen enthalten, wird von einem XAML-Prozessor verarbeitet. Informationen zu Eigenschaften wird das standardmäßige Verhalten bei der Verarbeitung durch den Typ des zugrunde liegenden CLR-Eigenschaft bestimmt.  
  
 Der Attributwert mit einer der folgenden gefüllt wird durch diese Verarbeitungsreihenfolge verwenden:  
  
1.  Wenn der XAML-Prozessor erkennt eine geschweifte Klammer oder ein Objektelement, das von abgeleitet ist <xref:System.Windows.Markup.MarkupExtension>, klicken Sie dann auf die verwiesen wird Auswertung der Markuperweiterung wird zuerst anstatt die Verarbeitung des Werts als Zeichenfolge und das Objekt, das von der Markuperweiterung zurückgegeben wird verwendet, als die -Wert. In vielen Fällen werden die von einer Markuperweiterung zurückgegebene Objekt einen Verweis auf ein vorhandenes Objekt oder ein Ausdruck, der Auswertung bis zur Laufzeit zurückstellt, ist kein neu instanziierten Objekt.  
  
2.  Wenn die Eigenschaft deklariert wird mit einem attributierten <xref:System.ComponentModel.TypeConverter>, oder der Werttyp der Eigenschaft deklariert ist mit einem attributierten <xref:System.ComponentModel.TypeConverter>, wird der Zeichenfolgenwert des Attributs für den Typkonverter als Konvertierungseingabe übermittelt, und der Konverter zurück ein neue Objektinstanz.  
  
3.  Es ist keine <xref:System.ComponentModel.TypeConverter>, eine direkte Konvertierung in den Typ der versucht wird. Diese letzte Ebene ist eine direkte Konvertierung des Werts der Parser Native zwischen primitiven Typen von XAML-Sprache oder überprüft, ob die Namen der benannten Konstanten in einer Enumeration (der Parser greift dann auf die entsprechenden Werte).  
  
#### <a name="enumeration-attribute-values"></a>Enumerationswerte-Attribut  
 Enumerationen in XAML intrinsisch vom XAML-Parser verarbeitet werden, und die Member einer Enumeration sollte angegeben werden, indem Sie den Zeichenfolgennamen eines benannten Konstanten der Enumeration angeben.  
  
 Dessen native Verhalten werden für Attributwerts aus die Zeichenfolge eines Attributwerts zu verarbeiten, und lösen Sie ihn auf einer der Enumerationswerte. Geben Sie nicht die Enumeration im Format *Enumeration*. *Wert*, wie Sie im Code. Stattdessen geben Sie nur *Wert*, und *Enumeration* abgeleitet wird, durch den Typ der Eigenschaft, die Sie festlegen. Wenn Sie angeben, dass ein Attribut in der *Enumeration*. *Wert* angeben, es kann nicht aufgelöst werden ordnungsgemäß.  
  
 Bei Flag-Enumerationen basiert auf das Verhalten der <xref:System.Enum.Parse%2A?displayProperty=nameWithType> Methode. Sie können mehrere Werte für eine Flag-Enumeration angeben, durch die einzelnen Werte durch ein Komma trennen. Sie können keine jedoch Enumerationswerte kombinieren, die nicht Flag-Enumerationswerte sind. Beispielsweise können keine die Komma-Syntax versuchen, erstellen eine <xref:System.Windows.Trigger> , die auf mehrere Bedingungen für eine Enumeration des Attributwerts fungiert:  
  
```  
<!--This will not compile, because Visibility is not a flagwise enumeration.-->  
...  
<Trigger Property="Visibility" Value="Collapsed,Hidden">  
  <Setter ... />  
</Trigger>  
...  
```  
  
 Flag-Enumerationen, die Attribute unterstützen, kann in XAML festgelegt werden, sind in WPF selten. Eine solche Enumeration ist jedoch <xref:System.Windows.Media.StyleSimulations>. Sie können z. B. die Attributsyntax durch Trennzeichen getrennte verwenden, so ändern Sie das Beispiel in den Hinweisen zu den <xref:System.Windows.Documents.Glyphs> Klasse. `StyleSimulations = "BoldSimulation"` kann werden `StyleSimulations = "BoldSimulation,ItalicSimulation"`. <xref:System.Windows.Input.KeyBinding.Modifiers%2A?displayProperty=nameWithType> ist eine andere Eigenschaft, in denen mehr als eine Enumerationswert angegeben werden kann. Jedoch diese Eigenschaft ist ein Sonderfall, da die <xref:System.Windows.Input.ModifierKeys> Enumeration unterstützt einen eigenen Typkonverter. Der Typkonverter für Modifizierer verwendet ein Pluszeichen (+) als Trennzeichen ein Komma (,). Diese Konvertierung unterstützt die herkömmliche Syntax zur Darstellung von Tastenkombinationen in der Microsoft Windows-Programmierung, z. B. "Strg + Alt +".  
  
### <a name="properties-and-event-member-name-references"></a>Eigenschaften und Ereignis-Member-Namensverweise  
 Wenn Sie ein Attribut angeben, können Sie verweisen, beliebige Eigenschaften oder Ereignisse, die als Mitglied der CLR-Typ vorhanden ist, wenn Sie für das enthaltende Objektelement instanziiert.  
  
 Oder Sie können eine angefügte Eigenschaft verweisen angefügtes Ereignis, unabhängig von der enthaltenden Object-Element. (Angefügte Eigenschaften sind in einem späteren Abschnitt erläutert.)  
  
 Sie können auch alle Ereignisse aller Objekte, die über den Standardnamespace mit Namen eine *TypeName*. *Ereignis* teilweise qualifizierten Namen; diese Syntax unterstützt, die Handler für Routingereignisse anfügen, in dem der Handler zum Behandeln von Ereignissen, die aus untergeordneten Elementen, aber das übergeordnete Element routing vorgesehen ist auch keine dieses Ereignis in der Membertabelle. Diese Syntax ähnelt einer angefügten Ereignissyntax, aber das Ereignis hier nicht um ein angefügtes Ereignis ist. Stattdessen sind Sie ein Ereignis mit einem qualifizierten Namen verweisen. Weitere Informationen finden Sie unter [Übersicht über Routingereignisse](../../../../docs/framework/wpf/advanced/routed-events-overview.md).  
  
 Für einige Szenarien werden die Eigenschaftennamen manchmal als Wert für ein Attribut, anstatt den Attributnamen bereitgestellt. Der Eigenschaftenname kann auch enthalten die Qualifizierer, z. B. die Eigenschaft, die im Formular angegeben habe *Besitzertyp*. *dependencyPropertyName angegebene Eigenschaft*. Dieses Szenario kommt häufig, beim Schreiben von Stilen oder Vorlagen in XAML. Die Verarbeitungsregeln für als Attributwert bereitgestellten Eigenschaftennamen unterscheiden, und werden durch den Typ der festzulegenden Eigenschaft oder das Verhalten der Verarbeitungsregeln gesteuert. Weitere Informationen finden Sie unter [Stile und Vorlagen](../../../../docs/framework/wpf/controls/styling-and-templating.md).  
  
 Eine andere Verwendung für Eigenschaftennamen ist, wenn ein Attributwert eine Eigenschaft Beziehung beschreibt. Dieses Feature wird für die Datenbindung und für die Storyboardziele verwendet, und wird über die <xref:System.Windows.PropertyPath> -Klasse und seinen Typkonverter. Eine vollständige Beschreibung der Suchsemantik, finden Sie unter [XAML-Syntax "PropertyPath"](../../../../docs/framework/wpf/advanced/propertypath-xaml-syntax.md).  
  
<a name="property_element_syntax"></a>   
## <a name="property-element-syntax"></a>Eigenschaftenelement-Syntax  
 *Eigenschaftenelement-Syntax* ist eine Syntax, die von der einfachen XML-Syntaxregeln für Elemente abweicht. Der Wert eines Attributs ist eine Zeichenfolge mit de-facto, mit der einzig mögliche Variante, wird die Codierung Zeichenfolgenformat verwendet wird, in XML. In XAML können Sie andere Object-Elemente auf den Wert einer Eigenschaft zuweisen. Diese Funktion wird durch das Eigenschaftenelement-Syntax aktiviert. Anstelle der Eigenschaft, die als ein Attribut innerhalb des Elementtags angegeben wird, wird die Eigenschaft angegeben, mit einer öffnenden Element markieren in *Formular ElementTypeName*. *PropertyName* Form der Wert der Eigenschaft wird angegeben, in, und klicken Sie dann das Property-Element geschlossen.  
  
 Insbesondere die Syntax beginnt mit einer linken spitzen Klammer (\<) unmittelbar folgen der Typname der Klasse oder Struktur, die die Eigenschaftenelement-Syntax in enthalten ist. Dies sofort ein einzelner Punkt (.), klicken Sie dann mit dem Namen einer Eigenschaft, klicken Sie dann eine schließende spitze Klammer (>) folgt. Wie bei der Attributsyntax, muss diese Eigenschaft in der deklarierte öffentliche Member des angegebenen Typs vorhanden sein. Der Wert der Eigenschaft zugewiesen werden soll, ist in der Property-Element enthalten. In der Regel erhält der Wert als ein oder mehrere Object-Elemente, da die Objekte als Werte angegeben. das Szenario ist, Eigenschaftenelement-Syntax Adresse soll. Schließlich ein entsprechendes Endtag Geben Sie die gleiche *Formular ElementTypeName*. *PropertyName* Kombination muss angegeben werden, und in die richtige Schachtelung und der Lastenausgleich mit anderen Elementtags.  
  
 Folgendes ist z. B. Eigenschaftenelement-Syntax für die <xref:System.Windows.FrameworkElement.ContextMenu%2A> Eigenschaft eine <xref:System.Windows.Controls.Button>.  
  
 [!code-xaml[XAMLOvwSupport#ContextMenu](../../../../samples/snippets/csharp/VS_Snippets_Wpf/XAMLOvwSupport/CSharp/Page1.xaml#contextmenu)]  
  
 Der Wert innerhalb eines Eigenschaftselements kann auch angegeben werden als innerer Text, der Eigenschaftentyp angegeben ist, einen primitive-Wert-Typ, z. B. <xref:System.String>, oder eine Enumeration, in dem ein Name angegeben ist. Diese zwei Verwendungen sind etwas ungewöhnlich, da es sich bei jedem dieser Fälle können auch eine einfachere Attributsyntax verwenden. Ein Szenario für das Auffüllen von einem Property-Element mit einer Zeichenfolge wird für Eigenschaften, die nicht die XAML-Inhaltseigenschaft aber weiterhin zur Darstellung von Benutzeroberflächen-Text verwendet werden, und bestimmte White-Space-Elemente wie z. B. Zeilenvorschübe sind erforderlich, um in diesem Text angezeigt werden. Attributsyntax kann Zeilenvorschübe nicht beibehalten, aber Eigenschaftenelement-Syntax kann, solange signifikanten Leerraum Beibehaltung aktiviert ist (Weitere Informationen finden Sie unter [Leerzeichen, die Verarbeitung in XAML](../../../../docs/framework/xaml-services/whitespace-processing-in-xaml.md)). Ein weiteres Szenario ist, damit [X: Uid Directive](../../../../docs/framework/xaml-services/x-uid-directive.md) kann auf das Property-Element angewendet werden, und markieren Sie den Wert im daher wie ein Wert, der in WPF-Anwendungen lokalisiert werden soll, BAML ausgeben oder andere Techniken.  
  
 Ein Property-Element wird nicht in der WPF-Struktur dargestellt. Ein Property-Element ist nur einer bestimmten Syntax zum Festlegen einer Eigenschaft, und es ist kein Element, das eine Instanz oder ein Objekt, die gesichert wurde. (Weitere Informationen auf dem Konzept der logischen Struktur finden Sie unter [Strukturen in WPF](../../../../docs/framework/wpf/advanced/trees-in-wpf.md).)  
  
 Für Eigenschaften, in denen sowohl Attribut auch Eigenschaftenelementsyntax unterstützt werden, haben die beiden Syntaxformen in der Regel das gleiche Ergebnis, obwohl feinheiten, z. B. die Bearbeitung der Leerzeichen zwischen Syntaxformen geringfügig variieren können.  
  
<a name="collection_syntax"></a>   
## <a name="collection-syntax"></a>Auflistungssyntax  
 Die XAML-Spezifikation erfordert XAML-Implementierungen von ereignissprozessoren um Eigenschaften zu identifizieren, in dem eine Auflistung von der Werttyp ist. Die allgemeine XAML-Prozessor-Implementierung in .NET basiert auf verwaltetem Code und die CLR und identifiziert Auflistungstypen, die über eine der folgenden:  
  
-   Geben Sie implementiert <xref:System.Collections.IList>.  
  
-   Geben Sie implementiert <xref:System.Collections.IDictionary>.  
  
-   Typ leitet sich von <xref:System.Array> (Weitere Informationen zu Arrays in XAML finden Sie unter [X: Array Markup Extension](../../../../docs/framework/xaml-services/x-array-markup-extension.md).)  
  
 Wenn der Typ einer Eigenschaft eine Auflistung ist, klicken Sie dann muss der Auflistungstyp der abgeleiteten nicht im Markup als Objektelement angegeben werden. Stattdessen werden die Elemente, die vorgesehen sind, werden die Elemente in der Auflistung als ein oder mehrere untergeordnete Elemente des Property-Elements angegeben. Die einzelnen Elemente zu einem Objekt ausgewertet wird, während des Ladens und der Auflistung hinzugefügt werden, indem die `Add` -Methode der impliziten Auflistung. Z. B. die <xref:System.Windows.Style.Triggers%2A> Eigenschaft <xref:System.Windows.Style> der speziellen Auflistungstyp <xref:System.Windows.TriggerCollection>, implementiert <xref:System.Collections.IList>. Es ist nicht erforderlich, zum Instanziieren einer <xref:System.Windows.TriggerCollection> Object-Element im Markup. Stattdessen geben Sie eine oder mehrere <xref:System.Windows.Trigger> als Elemente innerhalb der `Style.Triggers` Property-Element, in denen <xref:System.Windows.Trigger> (oder einer abgeleiteten Klasse) ist der Typ als Elementtyp für die stark typisierte und implizite erwartet <xref:System.Windows.TriggerCollection>.  
  
 [!code-xaml[XAMLOvwSupport#SyntaxPECollection](../../../../samples/snippets/csharp/VS_Snippets_Wpf/XAMLOvwSupport/CSharp/Page1.xaml#syntaxpecollection)]  
  
 Eine Eigenschaft kann sowohl für einen Auflistungstyp als auch für die XAML-Inhaltseigenschaft für diesen Typ und abgeleiteten Typen, die im nächsten Abschnitt dieses Themas wird erläutert.  
  
 Ein implizites Auflistungselement erstellt ein Element in der logischen Struktur-Darstellung, obwohl es nicht im Markup als ein Element angezeigt wird. In der Regel führt des Konstruktors des übergeordneten Typs die Instanziierung für die Sammlung, die eine seiner Eigenschaften ist, und die anfänglich leere Auflistung wird die Baumstruktur im Objekt.  
  
> [!NOTE]
>  Die generische Liste und Wörterbuch-Schnittstellen (<xref:System.Collections.Generic.IList%601> und <xref:System.Collections.Generic.IDictionary%602>) werden für die auflistungserkennung nicht unterstützt. Allerdings können Sie die <xref:System.Collections.Generic.List%601> Klasse als Basisklasse verwendet, da er implementiert <xref:System.Collections.IList> direkt oder <xref:System.Collections.Generic.Dictionary%602> als Basisklasse, da er implementiert <xref:System.Collections.IDictionary> direkt.  
  
 In den .NET Referenzseiten für Sammlungstypen wird diese Syntax mit dem absichtlichen Weglassen des Object-Elements für eine Sammlung gelegentlich als implizite Auflistungssyntax in den Abschnitten der XAML-Syntax aufgeführt.  
  
 Mit Ausnahme von der "Root"-Element ist jedes Objektelement in einer XAML-Datei, die als untergeordnetes Element eines anderen Elements geschachtelt ist wirklich ein Element, das eine oder beide der folgenden Fälle: ein Mitglied einer impliziten Auflistungseigenschaft des übergeordneten Elements , oder ein Element aus, der angibt, den Wert, der die XAML-Inhaltseigenschaft für das übergeordnete Element (XAML-Inhalten, Eigenschaften in einem späteren Abschnitt erläutert). Das heißt, die Beziehung zwischen übergeordneten und untergeordneten Elementen auf einer Markupseite ist wirklich ein einzelnes Objekt im Stammverzeichnis, und jedes Objektelement unterhalb des Stamms ist entweder eine einzelne Instanz, die einen Eigenschaftswert des übergeordneten Elements bereitstellt oder eines der Elemente in einer Spalte abgeleitet, die auch einen Eigenschaftswert von Typ "Auflistung" des übergeordneten Elements ist. Dieses Konzept einzelstamm wird häufig mit XML und im Verhalten von APIs, die z. B. Laden von XAML unterstützt <xref:System.Windows.Markup.XamlReader.Load%2A>.  
  
 Im folgende Beispiel wird eine Syntax, wobei das Object-Element für eine Sammlung (<xref:System.Windows.Media.GradientStopCollection>) explizit angegeben werden.  
  
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
  
 Beachten Sie, dass es nicht immer möglich, die die Auflistung explizit deklarieren. Beispielsweise möchten, deklarieren Sie <xref:System.Windows.TriggerCollection> explizit in die zuvor gezeigte <xref:System.Windows.Style.Triggers%2A> Beispiel würde fehlschlagen. Die Auflistung explizit deklarieren erfordert, dass die Auflistungsklasse einen Standardkonstruktor, unterstützen muss und <xref:System.Windows.TriggerCollection> nicht über einen Standardkonstruktor verfügen.  
  
<a name="xaml_content_properties"></a>   
## <a name="xaml-content-properties"></a>XAML-Inhaltseigenschaften  
 XAML Inhalt ist eine Syntax, die nur für Klassen aktiviert ist, die angeben, die <xref:System.Windows.Markup.ContentPropertyAttribute> als Teil der Klassendeklaration. Die <xref:System.Windows.Markup.ContentPropertyAttribute> verweist auf den Namen der Eigenschaft, die die Inhaltseigenschaft für diese Art von Element (einschließlich der abgeleitete Klassen) ist. Wenn von einem XAML-Prozessor verarbeitet werden, werden alle untergeordneten Elemente oder innere Text, der zwischen den öffnenden und schließenden Tags des Objektelements gefunden werden als Wert für das der XAML-Inhaltseigenschaft für dieses Objekt zugewiesen werden. Sie dürfen explizite Eigenschaftenelemente für die Content-Eigenschaft angegeben, aber diese Verwendung wird nicht in der Regel in den Abschnitten des XAML-Syntax in der Referenz zu .NET angezeigt. Die explizite/verbose Technik ist, gelegentlich Wert aus Gründen der Übersichtlichkeit von Markup oder als eine Frage des Stils von Markup, aber die Absicht des Content-Eigenschaft in der Regel ist, um das Markup zu optimieren, sodass Elemente, die als über-/ intuitiv beziehen direkt geschachtelt werden können. Eigenschaftenelement-Tags für die anderen Eigenschaften für ein Element sind nicht als "Inhalt" pro eine strenge Definition der XAML-Sprache; zugewiesen. Sie werden in der XAML-Parser Verarbeitungsreihenfolge zuvor verarbeitet und sind nicht als "Inhalt".  
  
### <a name="xaml-content-property-values-must-be-contiguous"></a>XAML-Inhaltseigenschaftenwerte müssen zusammenhängend sein.  
 Der Wert einer XAML-Inhaltseigenschaft muss entweder vor oder nach allen anderen Eigenschaftenelemente für dieses Objektelement angegeben werden. Dies gilt, ob der Wert einer XAML-Inhaltseigenschaft als eine Zeichenfolge oder als ein oder mehrere Objekte angegeben wird. Beispielsweise wird das folgende Markup nicht analysiert werden:  
  
```  
<Button>I am a   
  <Button.Background>Blue</Button.Background>  
  blue button</Button>  
```  
  
 Dies ist im Wesentlichen unzulässig, weil die Content-Eigenschaft zweimal festgelegt werden, wenn diese Syntax explizite vorgenommen wurden mithilfe von Eigenschaftenelement-Syntax für die Inhaltseigenschaft, würden:  
  
```xml  
<Button>  
  <Button.Content>I am a </Button.Content>  
  <Button.Background>Blue</Button.Background>  
  <Button.Content> blue button</Button.Content>  
</Button>  
```  
  
 Ein Beispiel für auf ähnliche Weise ungültig ist, wenn die Inhaltseigenschaft eine Sammlung ist und Eigenschaftenelemente sind untergeordnete Elemente enthält:  
  
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
 Zum akzeptieren muss mehr als ein einzelnes Objektelement als Inhalt der Typ der Content-Eigenschaft explizit einen Auflistungstyp sein. Ähnlich wie Eigenschaftenelement-Syntax für Sammlungstypen, muss ein XAML-Prozessor Typen identifizieren, die Auflistungstypen sind. Wenn ein Element verfügt über eine XAML-Inhaltseigenschaft, und der Typ der XAML-Inhaltseigenschaft eine Sammlung ist, klicken Sie dann der impliziten Auflistungstyp muss sich nicht im Markup als Objektelement angegeben werden, und die XAML-Inhaltseigenschaft muss nicht als eine Eigenschaft el angegeben werden Ement. Aus diesem Grund haben deutlich Inhaltsmodell im Markup jetzt mehr als ein untergeordnetes Element als Inhalt zugewiesen. Im folgenden finden Sie Inhalte Syntax für eine <xref:System.Windows.Controls.Panel> abgeleitete Klasse. Alle <xref:System.Windows.Controls.Panel> abgeleitete Klassen herstellen, um die XAML-Inhaltseigenschaft <xref:System.Windows.Controls.Panel.Children%2A>, wofür einen Wert vom Typ <xref:System.Windows.Controls.UIElementCollection>.  
  
 [!code-xaml[XAMLOvwSupport#SyntaxContent](../../../../samples/snippets/csharp/VS_Snippets_Wpf/XAMLOvwSupport/CSharp/page5.xaml#syntaxcontent)]  
  
 Beachten Sie, dass weder die Property-Element für <xref:System.Windows.Controls.Panel.Children%2A> noch das Element für die <xref:System.Windows.Controls.UIElementCollection> in das Markup erforderlich ist. Dies ist eine Funktion Entwerfen von XAML, so, dass rekursiv Elemente enthalten, die definieren, eine [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] intuitiver als eine Struktur von geschachtelten Elementen mit den unmittelbar übergeordneten und untergeordneten-Element-Beziehungen ohne dazwischenliegende Eigenschaftenelement-Tags dargestellt werden oder Objekte der Auflistung. In der Tat <xref:System.Windows.Controls.UIElementCollection> nicht explizit angegeben werden im Markup als Objektelement, beabsichtigt. Da die einzige vorgesehene Verwendung als implizite Sammlung ist, <xref:System.Windows.Controls.UIElementCollection> macht einen öffentlichen Standardkonstruktor nicht verfügbar und kann daher nicht als Objektelement instanziiert werden.  
  
### <a name="mixing-property-elements-and-object-elements-in-an-object-with-a-content-property"></a>Das Kombinieren von Eigenschaftenelementen und Object-Elemente in ein Objekt mit einem Content-Eigenschaft  
 Die XAML-Spezifikation wird deklariert, dass ein XAML-Prozessor in Kraft setzen kann, dass Object-Elemente, die verwendet werden, um die XAML-Inhaltseigenschaft in einem Objektelement zu füllen zusammenhängend sein müssen und nicht gemischt werden müssen. Diese Einschränkung für das Kombinieren von Eigenschaftenelementen und Inhalt wird erzwungen, indem die [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] XAML-Prozessoren.  
  
 Sie können ein untergeordnetes Objektelement als erstes unmittelbares Markup in einem Objektelement verwenden. Anschließend können Sie Eigenschaftenelemente einführen. Oder Sie können ein oder mehrere Eigenschaftenelemente, und klicken Sie dann Inhalt und dann weitere Eigenschaftenelemente angeben. Aber nach ein Eigenschaftenelement Inhalt folgt, keine weiteren Inhalte nicht das Eigenschaftenelemente können nur hinzugefügt werden.  
  
 Dieser Inhalt / Eigenschaft Element Reihenfolge Anforderung gilt nicht für inneren Text als Inhalt verwendet. Es ist jedoch immer noch einen guten Markup-Stil für die inneren Text zusammenhängend, aufbewahren, da signifikanter Leerraum nur schwer visuell im Markup erkannt wird, wenn Eigenschaftenelemente mit innerem Text kombiniert werden.  
  
<a name="xaml_namespaces"></a>   
## <a name="xaml-namespaces"></a>XAML-Namespaces  
 Keine der obigen Syntaxbeispiele angegeben einen XAML-Namespace als dem XAML-Standardnamespace. In typischen [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Anwendungen, die Standard-XAML-Namespace angegeben ist, werden die [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Namespace. Sie können XAML-Namespaces als dem XAML-Standardnamespace angeben und immer noch eine ähnliche Syntax verwenden. Aber dann an einer beliebigen Stelle, in dem eine Klasse namens ist, die nicht zugegriffen werden kann, in der XAML-Standardnamespace, Klassennamens muss stehen mit dem Präfix des XAML-Namespace als auf den entsprechenden CLR-Namespace zugeordnet. Z. B. `<custom:Example/>` Objektelement-Syntax zum Instanziieren einer Instanz von wird die `Example` -Klasse, wobei der CLR-Namespace, Klasse (und möglicherweise die externe Assembly-Informationen, die Unterstützungstypen enthalten) enthält zuvor zugeordnet wurde die `custom` Präfix.  
  
 Weitere Informationen zu XAML-Namespaces finden Sie unter [XAML-Namespaces und Namespace-Zuordnung für WPF XAML](../../../../docs/framework/wpf/advanced/xaml-namespaces-and-namespace-mapping-for-wpf-xaml.md).  
  
<a name="markup_extensions"></a>   
## <a name="markup-extensions"></a>Markuperweiterungen  
 XAML definiert eine Markuperweiterung, die Entität, das ein Escapezeichen von der normalen XAML-Prozessor-Bearbeitung der zeichenfolgenattributwerten oder Object-Elemente und überlässt die Verarbeitung in eine Sicherungsklasse, Programmieren. Das Zeichen, das eine Markuperweiterung für einen XAML-Prozessor identifiziert, wenn mithilfe der Attributsyntax die öffnende geschweifte Klammer ({}), gefolgt von beliebigen anderen Zeichens als eine schließende geschweifte Klammer (}) ist. Die erste Zeichenfolge, die nach der öffnenden geschweiften Klammer, muss die Klasse verweisen, die das Verhalten der bestimmten-Erweiterung, in dem die Teilzeichenfolge des Verweises weggelassen werden kann "Extension" bereitstellt, wenn diese Teilzeichenfolge Teil des Namens "true" ist. Danach ein einzelnes Leerzeichen angezeigt werden kann, und klicken Sie dann jede nachfolgende Zeichen wird als Eingabe verwendet durch die Implementierung, bis die schließende geschweifte Klammer gefunden wird.  
  
 Die .NET XAML-Implementierung verwendet die <xref:System.Windows.Markup.MarkupExtension> abstrakte Klasse als Basis für alle Markuperweiterungen von unterstützten [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] sowie andere Frameworks oder -Technologien. Markuperweiterungen, [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] speziell implementiert dienen häufig bieten eine Möglichkeit, andere vorhandene Objekte zu verweisen oder verzögerte Verweise auf Objekte zu machen, die zur Laufzeit ausgewertet werden. Eine einfache WPF-Datenbindung erfolgt z. B. durch Angeben der `{Binding}` Markuperweiterung anstelle des Werts, der eine bestimmte Eigenschaft normalerweise dauern würde. Viele der WPF-Markuperweiterungen ermöglichen eine Attributsyntax für Eigenschaften, was andernfalls nicht möglich wäre. Z. B. eine <xref:System.Windows.Style> Objekt ist ein relativ komplexer Typ, der eine geschachtelte Reihe von Objekten und Eigenschaften enthält. Stile in WPF werden in der Regel als Ressource definiert eine <xref:System.Windows.ResourceDictionary>, und klicken Sie dann auf die verwiesen wird durch eine der beiden WPF Markuperweiterungen, die eine Ressource anfordern. Die Markuperweiterung verzögert die Auswertung den Wert der Eigenschaft in eine Ressourcensuche und ermöglicht die Bereitstellung von der <xref:System.Windows.FrameworkElement.Style%2A> Eigenschaft, wobei der Typ <xref:System.Windows.Style>in Attributsyntax wie im folgenden Beispiel gezeigt:  
  
 `<Button Style="{StaticResource MyStyle}">My button</Button>`  
  
 Hier `StaticResource` identifiziert die <xref:System.Windows.StaticResourceExtension> -Klasse, die die Implementierung der Markuperweiterung bereitstellt. Die nächste Zeichenfolge `MyStyle` dient als Eingabe für den nicht standardmäßigen <xref:System.Windows.StaticResourceExtension> -Konstruktor, der Parameter aus der Erweiterungszeichenfolge, in dem der angeforderte deklariert <xref:System.Windows.ResourceKey>. `MyStyle` wird erwartet die [X: Key](../../../../docs/framework/xaml-services/x-key-directive.md) Wert eine <xref:System.Windows.Style> als Ressource definiert. Die [StaticResource-Markuperweiterung](../../../../docs/framework/wpf/advanced/staticresource-markup-extension.md) Nutzung fordert, dass die Ressource verwendet werden, zu der <xref:System.Windows.Style> Eigenschaftswert über die statische Suche Logik zur Ladezeit.  
  
 Weitere Informationen über Markuperweiterungen finden Sie unter [Markuperweiterungen und WPF XAML](../../../../docs/framework/wpf/advanced/markup-extensions-and-wpf-xaml.md). Markuperweiterungen und andere XAML Features aktiviert, die in der allgemeinen .NET XAML-Implementierung programmieren, finden Sie unter [XAML-Namespace (x:)) Sprachfunktionen](../../../../docs/framework/xaml-services/xaml-namespace-x-language-features.md). WPF-spezifische Markuperweiterungen finden Sie unter [WPF-XAML-Erweiterungen](../../../../docs/framework/wpf/advanced/wpf-xaml-extensions.md).  
  
<a name="attached_properties"></a>   
## <a name="attached-properties"></a>Angefügte Eigenschaften  
 Angefügte Eigenschaften sind ein Programmierkonzept, eingeführt in XAML durch Eigenschaften gehören und durch einen bestimmten Typ, definiert werden können als Attribute oder Eigenschaftenelemente auf ein beliebiges Element jedoch festgelegt. Das primäre Szenario für angefügte Eigenschaften vorgesehen sind untergeordnete Elemente in einer Markupstruktur, um Informationen an ein übergeordnetes Element zu aktivieren, ohne dass ein Modell häufig gemeinsam genutzte Objekt auf alle Elemente ist. Im Gegensatz dazu können die angefügte Eigenschaften durch übergeordnete Elemente, um Informationen an die untergeordneten Elemente verwendet werden. Weitere Informationen zu den Zweck von angefügten Eigenschaften "und" Gewusst wie: Erstellen eigener angefügte Eigenschaften, finden Sie unter [Übersicht über angefügte Eigenschaften](../../../../docs/framework/wpf/advanced/attached-properties-overview.md).  
  
 Angefügte Eigenschaften verwendet eine Syntax, die Eigenschaftenelement-Syntax, ersten Blick ähnelt insofern, dass Sie auch angeben, ein *TypeName*. *PropertyName* Kombination. Es gibt zwei wichtige Unterschiede:  
  
-   Sie können die *TypeName*. *PropertyName* Kombination, selbst wenn Sie über die Attributsyntax eine angefügte Eigenschaft festlegen. Angefügte Eigenschaften sind, dass der einzige Fall, qualifizieren den Eigenschaftennamen in Attributsyntax erforderlich ist.  
  
-   Sie können auch Eigenschaftenelement-Syntax für angefügte Eigenschaften verwenden. Beachten Sie jedoch bei typischen Eigenschaftenelement-Syntax die *TypeName* Sie angeben, ist das Object-Element, das das Property-Element enthält. Wenn Sie auf eine angefügte Eigenschaft verweisen die *TypeName* ist die Klasse, die die angefügte Eigenschaft, nicht des enthaltenden Objekts-Elements definiert.  
  
<a name="attached_events"></a>   
## <a name="attached-events"></a>Angefügte Ereignisse  
 Angefügte Ereignisse handelt es sich um einen anderen Programmierungskonzept, eingeführt in XAML können Ereignisse eines bestimmten Typs definiert werden, wobei ein Handler für jedes Objektelement angefügt werden. In der Implementierung der Routingereignisalias häufig ist des Typs, der ein angefügtes Ereignis definiert ein statischer Typ, der ein Dienst definiert, und manchmal die angefügte Ereignisse verfügbar gemacht werden ein Routingereignisalias in Typen, die den Dienst verfügbar machen. Handler für angefügte Ereignisse werden über die Attributsyntax angegeben. Wie Sie mit der angefügten Ereignisse, die Attributsyntax für angefügte Ereignisse können erweitert wird eine *TypeName*. *EventName* Nutzung, in denen *TypeName* ist die Klasse, die eine `Add` und `Remove` ereigniszugriffsmethoden der Handler für das angefügte Ereignis-Infrastruktur und *EventName* Ereignisnamen.  
  
<a name="anatomy_of_a_xaml_page_root_element"></a>   
## <a name="anatomy-of-a-xaml-root-element"></a>Anatomie einer XAML-Stammelement  
 Die folgende Tabelle zeigt die typische XAML Stammelement unterteilt, die bestimmte Attribute der ein Stammelement anzeigt:  
  
|||  
|-|-|  
|`<Page`|Object-Element des Stammelements öffnen|  
|`xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"`|Der Standardwert ([!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]) XAML-Namespace|  
|`xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"`|Die XAML-Namespace der XAML-Sprache|  
|`x:Class="ExampleNamespace.ExampleCode"`|Die Deklaration der partiellen Klasse, die Markup mit Code-Behind verbindet, die für die partielle Klasse definiert|  
|`>`|Das Ende der Object-Element für den Stammknoten. Objekt ist noch nicht geschlossen, da das Element untergeordnete Elemente enthält.|  
  
<a name="optional_and_nonrecommended_xaml_usages"></a>   
## <a name="optional-and-nonrecommended-xaml-usages"></a>Optional und auf XAML-Verwendungen  
 Die folgenden Abschnitte beschreiben die XAML-Verwendungen technisch von XAML-Prozessoren unterstützt werden, aber erzeugt Ausführlichkeit oder andere ästhetischen Probleme, die XAML-Dateien, die verbleibenden lesbare Wenn beeinträchtigen Ihrer Anwendungen entwickeln, die XAML-Quellen enthalten .  
  
### <a name="optional-property-element-usages"></a>Optionale Eigenschaftenelementen  
 Optionale Eigenschaftenelementen gehört, explizit ausgeben Element Content-Eigenschaften, die XAML-Prozessor als implizit behandelt. Z. B. Wenn Sie deklarieren den Inhalt des eine <xref:System.Windows.Controls.Menu>, Sie können auch explizit deklarieren, die <xref:System.Windows.Controls.ItemsControl.Items%2A> Auflistung von der <xref:System.Windows.Controls.Menu> als eine `<Menu.Items>` Eigenschaftentag-Element, und Stelle jedes <xref:System.Windows.Controls.MenuItem> in `<Menu.Items>`, sondern als die Verwendung der impliziten XAML-Prozessor-Verhaltens, die alle untergeordneten Elemente des eine <xref:System.Windows.Controls.Menu> muss eine <xref:System.Windows.Controls.MenuItem> und befinden sich der <xref:System.Windows.Controls.ItemsControl.Items%2A> Auflistung. In einigen Fällen können die optionale Verwendung um visuell die Objektstruktur zu verdeutlichen, wie im Markup angegeben. Oder manchmal eine explizite Eigenschaftselementverwendung Markup, das aber visuell verwirrend ist, z. B. geschachtelte Markuperweiterungen in einem Attribut technisch funktionsfähig ist, vermeiden kann.  
  
### <a name="full-typenamemembername-qualified-attributes"></a>Vollständige typeName.memberName qualifizierte Attribute  
 Die *TypeName*. *MemberName* bilden für ein Attribut als nur die Routingereignissen universell tatsächlich funktioniert. Aber in anderen Situationen ist diese Form überflüssig, und sollte nicht verwendet werden, wenn nur aus Gründen der Markup-Stil und Lesbarkeit. Im folgenden Beispiel führt die drei Verweise auf die <xref:System.Windows.Controls.Control.Background%2A> Attribut sind vollständig äquivalent:  
  
 [!code-xaml[XAMLOvwSupport#TypeNameProp](../../../../samples/snippets/csharp/VS_Snippets_Wpf/XAMLOvwSupport/CSharp/page8.xaml#typenameprop)]  
  
 `Button.Background` funktioniert, weil die qualifizierte Suche für diese Eigenschaft auf <xref:System.Windows.Controls.Button> ist erfolgreich (<xref:System.Windows.Controls.Control.Background%2A> wurde vom Steuerelement geerbt) und <xref:System.Windows.Controls.Button> ist die Klasse des Object-Element oder eine Basisklasse. `Control.Background` funktioniert, weil die <xref:System.Windows.Controls.Control> -Klasse definiert <xref:System.Windows.Controls.Control.Background%2A> und <xref:System.Windows.Controls.Control> ist eine <xref:System.Windows.Controls.Button> Basisklasse.  
  
 Allerdings die folgenden *TypeName*. *MemberName* Form-Beispiel funktioniert nicht und wird kommentiert:  
  
 [!code-xaml[XAMLOvwSupport#TypeNameBadProp](../../../../samples/snippets/csharp/VS_Snippets_Wpf/XAMLOvwSupport/CSharp/page8.xaml#typenamebadprop)]  
  
 <xref:System.Windows.Controls.Label> ist eine andere abgeleitete Klasse von <xref:System.Windows.Controls.Control>, und wenn Sie angegeben haben `Label.Background` innerhalb einer <xref:System.Windows.Controls.Label> Object-Element, diese Verwendung wird gearbeitet haben. Aber da <xref:System.Windows.Controls.Label> ist nicht der Klasse oder Basisklasse <xref:System.Windows.Controls.Button>, das angegebene XAML-Prozessor-Verhalten ist, verarbeitet `Label.Background` als angefügte Eigenschaft. `Label.Background` ist nicht verfügbare angefügte Eigenschaft, und hier ein Fehler auftritt.  
  
### <a name="basetypenamemembername-property-elements"></a>baseTypeName.memberName Eigenschaftenelemente  
 So, wie die *TypeName*. *MemberName* für Attributsyntax, funktioniert die Form einer *Basistypname*. *MemberName* Syntax funktioniert für Eigenschaftenelement-Syntax. Beispielsweise funktioniert die folgende Syntax:  
  
 [!code-xaml[XAMLOvwSupport#GoofyPE](../../../../samples/snippets/csharp/VS_Snippets_Wpf/XAMLOvwSupport/CSharp/page8.xaml#goofype)]  
  
 Hier wurde das Property-Element angegeben, als `Control.Background` , obwohl das Property-Element im enthalten waren `Button`.  
  
 Aber wie *TypeName*. *MemberName* Form für Attribute, *Basistypname*. *MemberName* Markupformat ist, und sollte nicht verwendet werden.  
  
## <a name="see-also"></a>Siehe auch  
 [Übersicht über XAML (WPF)](../../../../docs/framework/wpf/advanced/xaml-overview-wpf.md)  
 [Sprachfunktionen des XAML-Namespace (x:)](../../../../docs/framework/xaml-services/xaml-namespace-x-language-features.md)  
 [WPF-XAML-Erweiterungen](../../../../docs/framework/wpf/advanced/wpf-xaml-extensions.md)  
 [Übersicht über Abhängigkeitseigenschaften](../../../../docs/framework/wpf/advanced/dependency-properties-overview.md)  
 [TypeConverter und XAML](../../../../docs/framework/wpf/advanced/typeconverters-and-xaml.md)  
 [XAML- und benutzerdefinierte Klassen für WPF](../../../../docs/framework/wpf/advanced/xaml-and-custom-classes-for-wpf.md)
