---
title: "Ausf&#252;hrliche Erl&#228;uterung der XAML-Syntax | Microsoft Docs"
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
  - "XML-namespaces"
  - "XAML, Analysieren von Attributen"
  - "Analysieren von Attributen"
  - "XAML-Markuperweiterungen"
  - "Angefügte Eigenschaften"
  - "Tagsyntax [XAML]"
  - "Markuperweiterungen"
  - "XAML-Objektelementsyntax"
  - "XAML-syntaxterminologie"
  - "Angefügte Ereignisse"
  - "Suchsemantik"
  - "XAML, angefügte Ereignisse"
  - "XAML Inhaltssyntax"
  - "XAML Suchsemantik"
  - "Inhaltssyntax"
  - "Objektelementsyntax"
  - "Syntaxterminologie [XAML]"
  - "XAML, angefügte Eigenschaften"
  - "Attribute [XAML], analysieren"
  - "XAML Tagsyntax"
  - "XAML-Attributsyntax"
  - "Eigenschaftenelementsyntax"
  - "Terminologie [XAML]"
  - "XML-Namespaces"
  - "Attributsyntax [XAML]"
  - "XAML Eigenschaftenelementsyntax"
ms.assetid: 67cce290-ca26-4c41-a797-b68aabc45479
caps.latest.revision: 26
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 26
---
# Ausf&#252;hrliche Erl&#228;uterung der XAML-Syntax
In diesem Thema definiert die Begriffe, mit denen die Elemente der XAML-Syntax beschrieben. Diese Begriffe werden häufig im weiteren Verlauf dieser Dokumentation für WPF-Dokumentation verwendet, insbesondere und für die anderen Frameworks, die XAML oder die Grundkonzepte von XAML-aktiviert die Unterstützung der XAML-Sprache auf die System.Xaml-Ebene verwenden. Dieses Thema baut auf der im Thema eingeführten grundlegenden Terminologie [XAML Overview (WPF)](../../../../docs/framework/wpf/advanced/xaml-overview-wpf.md).  
  

  
<a name="the_xaml_language_specification"></a>   
## <a name="the-xaml-language-specification"></a>Der XAML-Sprachspezifikation  
 Die hier definierte Terminologie der XAML--Syntax wird auch definiert oder in der XAML-Sprachspezifikation verwiesen werden. XAML ist eine auf XML basierende Sprache und folgt oder XML-strukturellen Regeln erweitert. Einige der Begriffe aus freigegeben wird oder basiert auf der Terminologie, die häufig verwendet, wenn der XML-Sprache oder das XML-Document Object Model beschreibt.  
  
 Weitere Informationen über die XAML-Sprachspezifikation herunterladen [ \[MS-XAML\] ](http://go.microsoft.com/fwlink/?LinkId=114525) aus dem Microsoft Download Center.  
  
<a name="xaml_and_clr"></a>   
## <a name="xaml-and-clr"></a>Verwendung von XAML- und CLR  
 XAML ist eine Markupsprache. Die [!INCLUDE[TLA#tla_clr](../../../../includes/tlasharptla-clr-md.md)], als implizite mit seinem Namen Ausführung zur Laufzeit ermöglicht. XAML ist nicht allein eine gemeinsame Sprache, die direkt von der CLR-Laufzeit verarbeitet wird. Sie können stattdessen XAML unterstützt ein eigenes Typsystem vorstellen. Bestimmte XAML-Analysesystem, das von WPF verwendet wird, basiert auf der CLR und CLR-Typsystem. Eine Darstellung zur Laufzeit instanziiert werden, bei der Analyse des XAML für WPF-CLR-Typen werden XAML-Typen zugeordnet. Aus diesem Grund enthalten die verbleibende Diskussion der Syntax in diesem Dokument Verweise auf das CLR-Typsystem, obwohl nicht die entsprechende Syntaxdiskussionen in der XAML-Sprachspezifikation. (Pro der XAML-Spezifikation Sprachebene konnte XAML-Typen zugeordnet werden alle anderen Typsystem, das muss nicht die CLR, aber wäre es erforderlich, die Erstellung und Verwendung von einem anderen XAML-Parser.)  
  
#### <a name="members-of-types-and-class-inheritance"></a>Member von Typen und Klassenvererbung  
 Eigenschaften und Ereignisse, die als XAML-Member angezeigt ein [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Typ werden oft von Basistypen geerbt. Betrachten Sie z. B. die in diesem Beispiel: `<Button Background="Blue" .../>`. Die <xref:System.Windows.Controls.Control.Background%2A> Eigenschaft ist nicht direkt deklarierte Eigenschaft in der <xref:System.Windows.Controls.Button> Klasse, wenn Sie die Klassendefinition, Reflektionsergebnisse oder die Dokumentation ansehen würden. Stattdessen <xref:System.Windows.Controls.Control.Background%2A> wird von der Basisklasse geerbt <xref:System.Windows.Controls.Control> Klasse.  
  
 Das Klassenvererbungsverhalten von [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] XAML-Elementen ist eine erhebliche Abweichung von einem Schema erzwungenen Interpretation von XML-Markup. Vererbung von Testklassen kann komplex, besonders wenn intermediate Basisklassen, abstrakte Klassen oder Schnittstellen beteiligt sind. Dies ist ein Grund, die der Satz von XAML-Elemente und die zulässigen Attribute schwierig ist, genau und vollständig mit den Schematypen darstellen, die in der Regel dienen [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] Programmierung, z. B. DTD oder des XSD-Format. Ein weiterer Grund ist, Erweiterbarkeit und Typmapping Funktionen der XAML-Sprache selbst entgegen Vollständigkeit für alle festen Darstellung der zulässigen Typen und Member.  
  
<a name="object_element_syntax"></a>   
## <a name="object-element-syntax"></a>Objektelementsyntax  
 *Syntax für Eigenschaftselemente Objekt* ist die XAML-Markup-Syntax, die eine CLR-Klasse oder Struktur durch Deklarieren eines XML-Elements instanziiert. Diese Syntax ähnelt die Syntax von anderen Markupsprachen wie HTML. Objektelementsyntax beginnt mit einer linken spitzen Klammer)\<), followed immediately by the type name of the class or structure being instantiated. followed="" immediately="" by="" the="" type="" name="" of="" the="" class="" or="" structure="" being="">\</), followed immediately by the type name of the class or structure being instantiated.> NULL oder mehr Leerzeichen können den Typnamen folgen, und&0; (null) oder mehr Attribute können ebenfalls deklariert werden, auf das Object-Element mit ein oder mehrere Leerzeichen trennen jedes Attributname = "Wert"-Paar. Schließlich muss eine der folgenden erfüllt sein:  
  
-   Element und Tag müssen durch einen Schrägstrich (/), unmittelbar gefolgt von einer schließenden spitzen Klammer (>) geschlossen werden.  
  
-   Das Starttag muss durch eine schließende spitze Klammer (>) abgeschlossen werden. Andere Objektelemente, Eigenschaftenelemente oder innerer Text kann das Starttag folgen. Genau welche Inhalte zugelassen sind wird durch das Objektmodell des Elements in der Regel eingeschränkt. Das entsprechende schließende Tag für das Object-Element muss auch vorhanden, in die richtige Schachtelung und mit anderen öffnenden und schließenden Tag-Paare auszugleichen.  
  
 XAML in der Implementierung durch .NET verfügt über einen Satz von Regeln, mit denen Objektelemente Typen, Attribute, Eigenschaften oder Ereignisse und XAML-Namespaces CLR-Namespaces Plus Assembly zugeordnet. Für WPF und .NET Framework-XAML-Objektelemente [!INCLUDE[TLA#tla_net](../../../../includes/tlasharptla-net-md.md)] Typen in referenzierten Assemblys und Attribute Member dieser Typen zugeordnet. Wenn Sie einen CLR-Typ in XAML verweisen, haben Sie Zugriff auf geerbte Member dieses Typs als auch.  
  
 Im folgende Beispiel wird z. B. Objektelementsyntax, die instanziiert eine neue Instanz der der <xref:System.Windows.Controls.Button> -Klasse und gibt auch eine <xref:System.Windows.FrameworkElement.Name%2A> Attribut und einem Wert für dieses Attribut:  
  
 [!code-xml[XAMLOvwSupport#SyntaxOE](../../../../samples/snippets/csharp/VS_Snippets_Wpf/XAMLOvwSupport/CSharp/Page1.xaml#syntaxoe)]  
  
 Im folgende Beispiel ist die Objektelementsyntax, die auch die Syntax der XAML-Inhaltseigenschaft umfasst. Festlegen der enthaltene innere Text verwendet werden die <xref:System.Windows.Controls.TextBox> XAML-Inhaltseigenschaft <xref:System.Windows.Controls.TextBox.Text%2A>.  
  
 [!code-xml[XAMLOvwSupport#ThisIsATextBox](../../../../samples/snippets/csharp/VS_Snippets_Wpf/XAMLOvwSupport/CSharp/Page1.xaml#thisisatextbox)]  
  
### <a name="content-models"></a>Inhaltsmodelle  
 Eine Klasse unterstützt möglicherweise eine Verwendung als XAML-Objektelement im Hinblick auf die Syntax, aber dieses Element wird in einer Anwendung oder Seite nur einwandfrei, wenn es in einer erwarteten Position eines allgemeinen Modells oder einer allgemeinen Elementstruktur eingefügt wird. Z. B. eine <xref:System.Windows.Controls.MenuItem> sollten in der Regel nur als untergeordnetes Element angeordnet werden eine <xref:System.Windows.Controls.Primitives.MenuBase> abgeleitete Klasse wie <xref:System.Windows.Controls.Menu>. Inhaltsmodelle für bestimmte Elemente sind als Teil der Hinweise auf den für Steuerelemente und andere dokumentiert Content [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Klassen, die als XAML-Elemente verwendet werden können.  
  
<a name="properties_of_object_elements"></a>   
## <a name="properties-of-object-elements"></a>Eigenschaften von Objektelementen  
 Eigenschaften in XAML werden durch eine Vielzahl möglicher Syntaxarten festgelegt. Die Syntax für eine bestimmte Eigenschaft verwendet werden kann, hängt basierend auf den zugrunde liegenden Typ Systemmerkmalen der Eigenschaft, die Sie festlegen.  
  
 Festlegen von Eigenschaftswerten, fügen Sie Funktionen oder Merkmale auf Objekte wie sie in der Laufzeit-Objektdiagramm vorhanden sind. Der Ausgangszustand des aus einem Objektelement erstellten Objekts basiert auf Verhalten des Standardkonstruktors. Die Anwendung wird in der Regel etwas anderes als Standardinstanz eines angegebenen Objekts verwenden.  
  
<a name="attribute_syntax_properties"></a>   
## <a name="attribute-syntax-properties"></a>Attributsyntax (Eigenschaften)  
 Die Attributsyntax ist die XAML-Markup-Syntax, die einen Wert für eine Eigenschaft durch Deklarieren eines Attributs in einem vorhandenen Objektelement einstellt. Der Attributname muss die CLR-Membernamen der Eigenschaft der Klasse übereinstimmen, die das relevante Objektelement unterstützt. Der Attributname folgt ein Zuweisungsoperator (=). Der Attributwert muss eine Zeichenfolge in Anführungszeichen eingeschlossen sein.  
  
> [!NOTE]
>  Mithilfe von unterschiedlichen Anführungszeichen können Sie ein echtes Anführungszeichen innerhalb eines Attributs platzieren. Beispielsweise können Sie einfache Anführungszeichen als Mittel eine Zeichenfolge zu deklarieren, die ein doppeltes Anführungszeichen enthält. Ob Sie einfache oder doppelte Anführungszeichen verwenden, sollten Sie ein übereinstimmendes Paar zum Öffnen und Schließen der Attributwertzeichenfolge verwenden. Es stehen auch Escapesequenzen oder andere Techniken für umgehen zeicheneinschränkungen durch alle bestimmten XAML-Syntax. Finden Sie unter [XML-Zeichenentitäten und XAML-](../../../../docs/framework/xaml-services/xml-character-entities-and-xaml.md).  
  
 Um über die Attributsyntax festgelegt werden, wird eine Eigenschaft muss öffentlich sein und muss beschreibbar sein. Der Wert der Eigenschaft im Unterstützungstypsystem muss ein Werttyp sein oder muss werden ein Referenztyp, der instanziiert werden kann oder die XAML-Prozessor verwiesen wird, wenn der Zugriff auf den entsprechenden Unterstützungstyp.  
  
 Das Ereignis, das als Attributname verwiesen wird muss öffentlich sein und einen öffentlichen Delegaten haben, für XAML WPF-Ereignisse.  
  
 Die Eigenschaft oder das Ereignis muss ein Member der Klasse oder Struktur, die durch das Container-Objektelement instanziiert wird.  
  
### <a name="processing-of-attribute-values"></a>Verarbeiten von Attributwerten  
 Innerhalb des öffnenden und schließenden Anführungszeichen Zeichenfolgenwert wird von einem XAML-Prozessor verarbeitet. Für Eigenschaften wird das Standardverarbeitungsverhalten durch den Typ der zugrunde liegenden CLR-Eigenschaft festgelegt.  
  
 Der Attributwert mit einer der folgenden gefüllt wird durch diese Verarbeitungsreihenfolge verwenden:  
  
1.  Wenn der XAML-Prozessor findet eine geschweifte Klammer oder ein Object-Element, die von abgeleitet <xref:System.Windows.Markup.MarkupExtension>, dann die Markuperweiterung verwiesen wird zuerst statt der Verarbeitung des Werts als Zeichenfolge ausgewertet wird, und das von der Markuperweiterung zurückgegebene Objekt wird als Wert verwendet. In vielen Fällen werden die von der Markuperweiterung zurückgegebene Objekt einen Verweis auf ein vorhandenes Objekt oder ein Ausdruck, der Auswertung bis zur Laufzeit verzögert, und kein neu instanziiertes Objekt.  
  
2.  Wenn die Eigenschaft deklariert wird mit einem attributierten <xref:System.ComponentModel.TypeConverter>, oder der dieser Eigenschaft ist deklarierte Werttyp mit einem attributierten <xref:System.ComponentModel.TypeConverter>, wird der Zeichenfolgenwert des Attributs für den Typkonverter als Konvertierungseingabe übermittelt, und der Konverter gibt eine neue Objektinstanz zurück.  
  
3.  Es ist keine <xref:System.ComponentModel.TypeConverter>, eine direkte Konvertierung in den Eigenschaftentyp wird versucht. Dieser letzten Ebene handelt es sich um eine direkte Konvertierung der Parser mit systemeigenen Wert zwischen XAML-Sprache primitiven Typen oder um eine Überprüfung der Namen von benannten Konstanten in einer Enumeration (der Parser greift dann auf die entsprechenden Werte).  
  
#### <a name="enumeration-attribute-values"></a>Enumerationswerte-Attribut  
 Enumerationen in XAML werden von XAML-Parser systemintern verarbeitet, und die Member einer Enumeration sollten durch Angabe des Zeichenfolgennamens einer der benannten Konstanten der Enumeration angegeben werden.  
  
 Das Verhalten von systemeigene werden für Attributwerts aus die Zeichenfolge eines Attributwerts verarbeitet und lösen Sie ihn auf einen der Enumerationswerte. Geben Sie nicht die Enumeration im Format *Enumeration*.*Wert*, wie Sie im Code. Stattdessen geben Sie nur *Wert*, und *Enumeration* abgeleitet wird, durch den Typ der Eigenschaft festlegen. Wenn Sie ein Attribut in der *Enumeration*.*Wert* Form, es werden nicht ordnungsgemäß aufgelöst.  
  
 Bei Flag-Enumerationen basiert das Verhalten auf der <xref:System.Enum.Parse%2A?displayProperty=fullName> Methode. Sie können mehrere Werte für eine Flag-Enumeration angeben, indem Sie die einzelnen Werte durch ein Komma trennen. Sie können keine jedoch Enumerationswerte kombinieren, die nicht Flag-Enumerationswerte. Beispielsweise können die Syntax Komma versuchen, erstellen eine <xref:System.Windows.Trigger> , die auf mehreren Kriterien einer Enumeration Attributwerts fungiert:  
  
```  
<!--This will not compile, because Visibility is not a flagwise enumeration.-->  
...  
<Trigger Property="Visibility" Value="Collapsed,Hidden">  
  <Setter ... />  
</Trigger>  
...  
```  
  
 Flag-Enumerationen, die Attribute zu unterstützen, die in XAML festgelegt werden, sind selten in WPF. Eine solche Enumeration ist jedoch <xref:System.Windows.Media.StyleSimulations>. Sie können z. B. Attributsyntax Komma als Trennzeichen verwenden, um das Beispiel in den Hinweisen zu ändern die <xref:System.Windows.Documents.Glyphs> Klasse. `StyleSimulations = "BoldSimulation"` kann `StyleSimulations = "BoldSimulation,ItalicSimulation"`. <xref:System.Windows.Input.KeyBinding.Modifiers%2A?displayProperty=fullName> ist eine andere Eigenschaft, in denen mehr als ein Enumerationswert angegeben werden kann. Diese Eigenschaft geschieht jedoch um einen Spezialfall, da die <xref:System.Windows.Input.ModifierKeys> -Enumeration einen eigenen Typkonverter unterstützt. Der Typkonverter für Modifizierer verwendet ein Pluszeichen (+) als Trennzeichen ein Komma (,). Diese Konvertierung unterstützt die herkömmlichere Syntax zur Darstellung von Tastenkombinationen in Microsoft Windows-Programmierung, z. B. "Strg + Alt".  
  
### <a name="properties-and-event-member-name-references"></a>Eigenschaften und Ereignismembernamen  
 Wenn Sie ein Attribut angeben, können Sie verweisen, Eigenschaft oder ein Ereignis, das als Mitglied der CLR-Typ vorhanden ist, den Sie für das Container-Objektelement instanziiert.  
  
 Oder Sie können eine angefügte Eigenschaft verweisen angefügtes Ereignis unabhängig vom Container-Objektelement. (Angefügte Eigenschaften werden in einem späteren Abschnitt erläutert.)  
  
 Sie können auch alle Ereignisse aus allen Objekten, die über den Standardnamespace mit Namen einer *TypeName*.*Ereignis* teilweise qualifizierten Namen und diese Handler für Routingereignisse unterstützt, in dem der Handler zum Behandeln von Ereignissen, die von untergeordneten Elementen, aber das übergeordnete Element routing vorgesehen ist auch keine das Ereignis in der Membertabelle Syntax. Diese Syntax ähnelt der Syntax für eine angefügte Ereignisse, jedoch handelt es sich kein angefügtes Ereignis. Stattdessen sind Sie ein Ereignis mit einem qualifizierten Namen verweisen. Weitere Informationen finden Sie unter [Ereignisübersicht weitergeleitet](../../../../docs/framework/wpf/advanced/routed-events-overview.md).  
  
 Bei einigen Szenarien werden Eigenschaftennamen manchmal als Wert für ein Attribut, anstatt den Attributnamen bereitgestellt. Diese Eigenschaftennamen kann auch Qualifizierer enthalten, z. B. die im Formular angegebene Eigenschaft einschließen *Besitzertyp*.*dependencyPropertyName angegebene Eigenschaft*. Dieses Szenario wird häufig, beim Schreiben von Stilen oder Vorlagen in XAML. Die Verarbeitungsregeln für als Attributwerte bereitgestellte Eigenschaftennamen sind unterschiedlich, und werden durch den Typ der festzulegenden Eigenschaft oder das Verhalten der Verarbeitungsregeln gesteuert. Weitere Informationen finden Sie unter [von Formaten und Vorlagen](../../../../docs/framework/wpf/controls/styling-and-templating.md).  
  
 Eine andere Verwendung für Eigenschaftennamen ist ein Attributwert eine Beziehung Eigenschaften beschrieben. Dieses Feature wird für die Datenbindung und für Storyboardziele verwendet und wird aktiviert, indem die <xref:System.Windows.PropertyPath> Klasse und ihren Typkonverter. Eine vollständige Beschreibung der Suchsemantik finden Sie unter [PropertyPath XAML-Syntax](../../../../docs/framework/wpf/advanced/propertypath-xaml-syntax.md).  
  
<a name="property_element_syntax"></a>   
## <a name="property-element-syntax"></a>Eigenschaftenelementsyntax  
 *Syntax für Eigenschaftselemente* ist eine Syntax, die gewissen von den allgemeinen XML-Syntaxregeln für Elemente Grad. Im XML-Code der Wert eines Attributs ist ein de-facto-Zeichenfolge, und die einzige welche Codierung Zeichenfolgenformat verwendet wird. In XAML können Sie andere Objektelemente den Wert einer Eigenschaft zuweisen. Diese Funktion wird durch die Eigenschaftenelementsyntax aktiviert. Anstelle der Eigenschaft innerhalb des Elementtags als Attribut angegeben wird, wird die Eigenschaft angegeben, mithilfe eines Tags im *Formular ElementTypeName*.*PropertyName* Form innerhalb der Wert der Eigenschaft angegeben ist, und das Property-Element wird anschließend geschlossen.  
  
 Die Syntax beginnt mit einer linken spitzen Klammer)\<), followed immediately by the type name of the class or structure that the property element syntax is contained within. followed="" immediately="" by="" the="" type="" name="" of="" the="" class="" or="" structure="" that="" the="" property="" element="" syntax="" is="" contained="">\</), followed immediately by the type name of the class or structure that the property element syntax is contained within.> Dies sofort ein einzelner Punkt (.), dann den Namen einer Eigenschaft, klicken Sie dann eine schließende spitze Klammer (>) folgt. Wie bei der Attributsyntax muss diese Eigenschaft in den deklarierten öffentlichen Membern des angegebenen Typs vorhanden sein. Der Wert der Eigenschaft zugewiesen werden soll, ist in Property-Element enthalten. In der Regel der Wert bei der ein oder mehrere Objektelemente, da Angabe von Objekten als Werte des Szenarios ist diese Eigenschaftenelementsyntax soll die Adresse. Abschließend ein entsprechendes Endtag Angabe desselben *Formular ElementTypeName*.*PropertyName* Kombination muss angegeben werden, und in die richtige Schachtelung und der Lastenausgleich mit anderen Element-Tags.  
  
 Folgendes ist z. B. Eigenschaftenelementsyntax für die <xref:System.Windows.FrameworkElement.ContextMenu%2A> Eigenschaft ein <xref:System.Windows.Controls.Button>.  
  
 [!code-xml[XAMLOvwSupport#ContextMenu](../../../../samples/snippets/csharp/VS_Snippets_Wpf/XAMLOvwSupport/CSharp/Page1.xaml#contextmenu)]  
  
 Der Wert innerhalb eines Eigenschaftselements kann auch zugewiesen werden, als innere Text in Fällen, in denen die angegebenen Eigenschaftentyp ein primitiver Typ, z. B. <xref:System.String>, oder eine Enumeration, in denen ein Name angegeben ist. Diese zwei Verwendungen sind relativ selten, da es sich bei jedem dieser Fälle können auch eine einfachere Attributsyntax verwenden. Ein Beispiel für das Auffüllen eines Eigenschaftenelements mit einer Zeichenfolge ist für Eigenschaften, die zur Darstellung von Benutzeroberflächen-Text verwendet werden, sind nicht die XAML-Inhaltseigenschaft, und bestimmte Whitespace-Elemente wie z. B. Zeilenvorschübe sind erforderlich, um in diesem Text angezeigt werden. Attributsyntax kann Zeilenvorschübe nicht beibehalten, aber Eigenschaftenelementsyntax kann, solange die Beibehaltung signifikanter Leerräume aktiviert ist (Weitere Informationen finden Sie unter [Whitespace Processing in XAML](../../../../docs/framework/xaml-services/whitespace-processing-in-xaml.md)). Ein weiteres Szenario ist, damit [X: Uid-Direktive](../../../../docs/framework/xaml-services/x-uid-directive.md) auf das Property-Element angewendet werden können und daher den Wert im kennzeichnen, wie ein Wert, der in WPF lokalisiert werden soll--BAML Ausgabe oder durch andere Techniken.  
  
 Ein Eigenschaftenelement wird nicht in der logischen WPF-Struktur dargestellt. Ein Eigenschaftenelement ist lediglich eine bestimmte Syntax zum Festlegen einer Eigenschaft, und ein Element mit einer Instanz oder das Objekt ist. (Ausführliche Informationen über das Konzept der logischen Struktur, finden Sie unter [Strukturen in WPF](../../../../docs/framework/wpf/advanced/trees-in-wpf.md).)  
  
 Für Eigenschaften, in denen sowohl Attribute als auch unterstützt werden, besitzen zwei Syntaxarten im Allgemeinen das gleiche Ergebnis Besonderheiten wie z. B. die Behandlung von Leerzeichen zwischen Syntax geringfügig abweichen können.  
  
<a name="collection_syntax"></a>   
## <a name="collection-syntax"></a>Auflistungssyntax  
 Die XAML-Spezifikation erfordert XAML-Prozessor-Implementierungen zum Identifizieren von Eigenschaften, wobei der Wert eine Auflistung ist. Die allgemeine Implementierung der XAML-Prozessor in .NET basiert auf verwaltetem Code sowie der CLR, und es identifiziert Auflistungstypen mit einer der folgenden:  
  
-   Typ implementiert <xref:System.Collections.IList>.  
  
-   Typ implementiert <xref:System.Collections.IDictionary>.  
  
-   Typ leitet sich von <xref:System.Array> (Weitere Informationen zu Arrays in XAML finden Sie unter [X: Array-Markuperweiterung](../../../../docs/framework/xaml-services/x-array-markup-extension.md).)  
  
 Wenn der Typ einer Eigenschaft eine Auflistung ist, dann muss der abgeleitete Auflistungstyp nicht im Markup als Objektelement angegeben werden. Stattdessen werden die Elemente der Auflistung als ein oder mehrere untergeordnete Elemente des Eigenschaftenelements angegeben. Die einzelnen Elemente wird beim Laden eines Objekts ausgewertet und zur Auflistung hinzugefügt werden, indem die `Add` -Methode der impliziten Auflistung. Z. B. die <xref:System.Windows.Style.Triggers%2A> -Eigenschaft des <xref:System.Windows.Style> der speziellen Auflistungstyp <xref:System.Windows.TriggerCollection>, implementiert <xref:System.Collections.IList>. Es ist nicht notwendig, instanziieren Sie ein <xref:System.Windows.TriggerCollection> Object-Element im Markup. Stattdessen geben Sie mindestens eine <xref:System.Windows.Trigger> als Elemente innerhalb der `Style.Triggers` Property-Element, in dem <xref:System.Windows.Trigger> (oder eine abgeleitete Klasse) als Elementtyp für die stark typisierte und implizite erwartet wird <xref:System.Windows.TriggerCollection>.  
  
 [!code-xml[XAMLOvwSupport#SyntaxPECollection](../../../../samples/snippets/csharp/VS_Snippets_Wpf/XAMLOvwSupport/CSharp/Page1.xaml#syntaxpecollection)]  
  
 Eine Eigenschaft möglicherweise einen Sammlungstyp und die XAML-Inhaltseigenschaft für diesen Typ und die abgeleiteten Typen, die im nächsten Abschnitt dieses Themas wird erläutert.  
  
 Ein implizites Auflistungselement erstellt ein Element in der logischen Struktur-Darstellung, obwohl er nicht im Markup als Element angezeigt wird. In der Regel führt des Konstruktors des übergeordneten Typs die Instanziierung für die Auflistung, die eine seiner Eigenschaften ist, und die zunächst leere Auflistung wird Teil der Objektstruktur.  
  
> [!NOTE]
>  Die generischen Schnittstellen Liste und Wörterbuch (<xref:System.Collections.Generic.IList%601> und <xref:System.Collections.Generic.IDictionary%602>) werden für die Erkennung von Auflistung nicht unterstützt.\</TKey, TValue> Können jedoch die <xref:System.Collections.Generic.List%601> Klasse als Basisklasse verwendet, da es implementiert <xref:System.Collections.IList> direkt oder <xref:System.Collections.Generic.Dictionary%602> als Basisklasse verwendet, da es implementiert <xref:System.Collections.IDictionary> direkt.\</TKey, TValue>  
  
 In den .NET Referenzseiten für Auflistungstypen wird diese Syntax mit dem absichtlichen Weglassen des Objektelements für eine Auflistung gelegentlich als implizite Auflistungssyntax in den XAML-Syntaxabschnitten aufgeführt.  
  
 Mit Ausnahme des Stammelements ist jedes Objektelement in einer XAML-Datei, die als untergeordnetes Element eines anderen Elements geschachtelt ist wirklich ein Element, das eine oder beide der folgenden Fälle sind: Mitglied einer impliziten Auflistungseigenschaft des übergeordneten Elements oder ein Element, das gibt den Wert der XAML-Inhalt-Eigenschaft für das übergeordnete Element (XAML-Inhalt Eigenschaften in einem späteren Abschnitt erläutert). Das heißt, die Beziehung zwischen übergeordneten und untergeordneten Elementen auf einer Markupseite ist wirklich ein einzelnes Objekt im Stammverzeichnis, und jedem Objektelemente unter dem Stamm ist eine einzelne Instanz, die einen Eigenschaftswert des übergeordneten Elements bereitstellt, oder eines der Elemente in einer Sammlung, die auch einer Auflistung den Eigenschaftswert des übergeordneten Elements ist. Dieses Konzept für die einzelnen Stamm wird häufig mit XML und im Verhalten von APIs, die XAML, z. B. Laden unterstützt <xref:System.Windows.Markup.XamlReader.Load%2A>.  
  
 Im folgende Beispiel wird eine Syntax, wobei das Objektelement für eine Auflistung (<xref:System.Windows.Media.GradientStopCollection>) explizit angegeben wird.  
  
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
  
 Beachten Sie, dass es nicht immer möglich, zu die Auflistung explizit deklarieren. Beispielsweise versucht deklarieren <xref:System.Windows.TriggerCollection> explizit in das zuvor gezeigte <xref:System.Windows.Style.Triggers%2A> Beispiel würde fehlschlagen. Nur die Auflistung explizit deklariert werden, dass die Auflistungsklasse einen Standardkonstruktor unterstützt und <xref:System.Windows.TriggerCollection> nicht über einen Standardkonstruktor verfügen.  
  
<a name="xaml_content_properties"></a>   
## <a name="xaml-content-properties"></a>XAML-Inhaltseigenschaften  
 Verwendung von XAML-Inhalt ist eine Syntax, die nur bei Klassen aktiviert, die angeben, die <xref:System.Windows.Markup.ContentPropertyAttribute> als Teil der Klassendeklaration. Die <xref:System.Windows.Markup.ContentPropertyAttribute> verweist auf den Eigenschaftennamen, die die Content-Eigenschaft für diese Art von Element (einschließlich abgeleitete Klassen). Nach der Verarbeitung durch einen XAML-Prozessor werden alle untergeordneten Elemente oder innere Text, der zwischen dem öffnenden und schließenden Tags des Object-Elements gefunden werden auf den Wert der XAML-Inhalt-Eigenschaft für dieses Objekt zugewiesen werden. Sie sind berechtigt, explizite Eigenschaftenelemente für die Inhaltseigenschaft angeben, aber diese Verwendung wird im Allgemeinen nicht in den XAML-Syntaxabschnitten in der Referenz zu .NET angezeigt. Die explizite/verbose Methode bietet gelegentlichen Wert für die Markup-Klarheit oder als Markup stilistischen, aber in der Regel die Absicht des Content-Eigenschaft ist das Markup optimieren, sodass Elemente, die intuitiv als Übergeordnet-Untergeordnet verknüpft sind, direkt verschachtelt werden können. Eigenschaft Element-Tags für andere Eigenschaften eines Elements werden als "Inhalt" pro eine strikte XAML-Sprachdefinition; nicht zugewiesen. Sie werden in der XAML-Parser Verarbeitungsreihenfolge zuvor verarbeitet und gelten nicht als "Inhalt".  
  
### <a name="xaml-content-property-values-must-be-contiguous"></a>XAML-Inhaltseigenschaftenwerte müssen zusammenhängend sein.  
 Der Wert einer XAML-Inhaltseigenschaft muss entweder vor oder nach anderen Eigenschaftenelementen vollständig das Objektelement erteilt werden. Dies gilt, ob der Wert einer XAML-Inhaltseigenschaft als Zeichenfolge oder als ein oder mehrere Objekte angegeben wird. Das folgende Markup wird beispielsweise nicht analysiert:  
  
```  
<Button>I am a   
  <Button.Background>Blue</Button.Background>  
  blue button</Button>  
```  
  
 Dies ist im Wesentlichen nicht zulässig, da die Inhaltseigenschaft zweimal festgelegt werden, wenn diese Syntax explizite vorgenommen wurden mithilfe der Eigenschaftenelementsyntax für die Inhaltseigenschaft, würden:  
  
```  
<Button>  
  <Button.Content>I am a </Button.Content>  
  <Button.Background>Blue</Button.Background>  
  <Button.Content> blue button</Button.Content>  
</Button>  
```  
  
 Ein Beispiel für die auf ähnliche Weise ungültig ist, wenn die Content-Eigenschaft eine Sammlung ist und untergeordnete Elemente mit Eigenschaftenelementen vermischt werden:  
  
```  
<StackPanel>  
  <Button>This example</Button>  
  <StackPanel.Resources>  
    <SolidColorBrush x:Key="BlueBrush" Color="Blue"/>  
  </StackPanel.Resources>  
  <Button>... is illegal XAML</Button>  
</StackPanel>  
```  
  
<a name="content_properties_and_collection_syntax_combined"></a>   
## <a name="content-properties-and-collection-syntax-combined"></a>Inhaltseigenschaften und Auflistungssyntax kombiniert  
 Damit angenommen muss mehr als ein einzelnes Objektelement als Inhalt der Typ der Inhaltseigenschaft speziell ein Auflistungstyp sein. Ähnlich wie bei Eigenschaftenelementsyntax für Auflistungstypen muss ein XAML-Prozessor Typen als Auflistungstypen identifizieren. Wenn ein Element verfügt über eine XAML-Inhaltseigenschaft, und der Typ der XAML-Inhalt-Eigenschaft eine Auflistung ist, die implizite Auflistungstyp muss nicht im Markup als Objektelement angegeben werden, und die XAML-Inhaltseigenschaft muss nicht als Eigenschaftenelement angegeben werden. Daher kann die im Markup vorhandenen Inhaltsmodell jetzt mehr als ein untergeordnetes Element als Inhalt zugewiesen haben. Im folgenden finden Sie die Inhaltssyntax für eine <xref:System.Windows.Controls.Panel> abgeleitete Klasse. Alle <xref:System.Windows.Controls.Panel> abgeleitete Klassen herstellen, die XAML-Inhaltseigenschaft um <xref:System.Windows.Controls.Panel.Children%2A>, erfordert, dass einen Wert vom Typ <xref:System.Windows.Controls.UIElementCollection>.  
  
 [!code-xml[XAMLOvwSupport#SyntaxContent](../../../../samples/snippets/csharp/VS_Snippets_Wpf/XAMLOvwSupport/CSharp/page5.xaml#syntaxcontent)]  
  
 Beachten Sie, dass weder das Eigenschaftenelement für <xref:System.Windows.Controls.Panel.Children%2A> noch das Element für die <xref:System.Windows.Controls.UIElementCollection> in das Markup erforderlich ist. Dies ist ein Entwurfsfeature von XAML, sodass rekursiv Elemente enthalten, die definieren, eine [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] intuitiver als eine Struktur von geschachtelten Elementen mit unmittelbar übergeordneten und untergeordneten elementbeziehungen ohne Eigenschaftenelementtags oder Objekten dargestellt werden. In der Tat <xref:System.Windows.Controls.UIElementCollection> nicht explizit angegeben werden im Markup als Objektelement vorgesehen. Da die einzige Verwendung einer impliziten Auflistung ist <xref:System.Windows.Controls.UIElementCollection> macht einen öffentlichen Standardkonstruktor verfügbar und kann daher nicht als Objektelement instanziiert werden.  
  
### <a name="mixing-property-elements-and-object-elements-in-an-object-with-a-content-property"></a>Kombinieren von Eigenschaftenelementen und Object-Elemente in einem Objekt mit der Content-Eigenschaft  
 Die XAML-Spezifikation wird deklariert, dass ein XAML-Prozessor erzwingen kann, dass Object-Elemente, die verwendet werden, um die XAML-Inhaltseigenschaft in einem Objektelement füllen zusammenhängend sein müssen und nicht gemischt werden müssen. Diese Einschränkung Eigenschaftenelementen und Inhalt wird erzwungen, indem die [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] XAML-Prozessoren.  
  
 Sie können ein untergeordnetes Objektelement als erstes unmittelbares Markup in einem Objektelement verwenden. Dann können Sie Eigenschaftenelemente angeben. Alternativ können Sie eine oder mehrere Eigenschaftenelemente, dann Inhalt und dann weitere Eigenschaftenelemente angeben. Aber nach einem Eigenschaftenelement Inhalt folgt, führen Sie keinen weiteren Inhalt können nicht Eigenschaftenelemente können nur hinzugefügt werden.  
  
 Dieser Inhalt / Eigenschaft Element Reihenfolge gilt nicht für inneren Text als Inhalt verwendet. Es ist jedoch immer noch einen guten Markup-Stil für innere Text zusammenhängend aufbewahren, da wichtige Leerstellen nur schwer zu visuell im Markup zu erkennen, wenn Eigenschaftenelemente mit innerem Text kombiniert werden.  
  
<a name="xaml_namespaces"></a>   
## <a name="xaml-namespaces"></a>XAML-Namespaces  
 Keines der vorangehenden Syntaxbeispiele angegeben einen XAML-Namespace als dem standardmäßigen XAML-Namespace. In typischen [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Clientanwendungen, die standardmäßigen XAML-Namespace wird angegeben, werden die [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Namespace. Sie können XAML-Namespaces außer dem XAML-Standardnamespace angeben und weiterhin eine ähnliche Syntax verwenden. Aber dann überall, wo eine Klasse namens, der nicht in der standardmäßigen XAML-Namespace zugegriffen werden kann, Klassenname muss stehen mit dem Präfix des XAML-Namespace den entsprechenden CLR-Namespace zugeordnet. Beispielsweise `<custom:Example/>` Objektelementsyntax zum Instanziieren einer Instanz von der `Example` -Klasse, wobei der CLR-Namespace, die Klasse (und möglicherweise auch die externen Assemblyinformationen, die Unterstützungstypen enthalten) enthält zuvor zugeordnet wurde die `custom` Präfix.  
  
 Weitere Informationen zu XAML-Namespaces finden Sie unter [XAML-Namespaces und Namespace-Zuordnung für WPF-XAML](../../../../docs/framework/wpf/advanced/xaml-namespaces-and-namespace-mapping-for-wpf-xaml.md).  
  
<a name="markup_extensions"></a>   
## <a name="markup-extensions"></a>Markuperweiterungen  
 XAML-Code definiert eine Markuperweiterung, die Entität, ermöglicht ein Escapezeichen aus der normalen XAML-Prozessor-Behandlung von Zeichenfolgen-Attributwerten oder Object-Elemente, verzögert die Verarbeitung in eine Sicherungsklasse programmieren. Das Zeichen, das eine Markuperweiterung für ein XAML-Prozessor identifiziert, wird mithilfe der Attributsyntax die öffnende geschweifte Klammer ({}), gefolgt von einem Zeichen, eine schließende geschweifte Klammer (}). Die erste Zeichenfolge nach der öffnenden geschweiften Klammer muss die Klasse verweisen, die das Verhalten der entsprechenden Erweiterung in die Referenz die Teilzeichenfolge weglassen, kann "Extension" bereitstellt, wenn diese Teilzeichenfolge Teil des eigentlichen Klassennamens ist. Danach kann ein einzelnes Leerzeichen angezeigt, und dann alle nachfolgenden Zeichen werden als Eingabe durch die erweiterungsimplementierung, bis die schließende geschweifte Klammer gefunden wird.  
  
 Die .NET XAML-Implementierung verwendet die <xref:System.Windows.Markup.MarkupExtension> abstrakte Klasse als Basis für alle Markuperweiterungen, die von unterstützten [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] sowie andere Frameworks oder Technologien. Markuperweiterungen, [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] speziell implementierten dienen häufig bieten eine Möglichkeit, um auf andere vorhandene Objekte zu verweisen oder zurückgestellte Verweise auf Objekte auszuführen, die zur Laufzeit ausgewertet werden. Eine einfache WPF-Bindung erfolgt z. B. durch Angabe der `{Binding}` Markuperweiterung anstelle des Werts, der eine bestimmte Eigenschaft normalerweise dauern würde. Viele der WPF-Markuperweiterungen ermöglichen die Verwendung eine Attributsyntax für Eigenschaften, was andernfalls nicht möglich wäre. Angenommen, ein <xref:System.Windows.Style> Objekt ist ein relativ komplexer Typ, der eine geschachtelte Reihe von Objekten und Eigenschaften enthält. Stile in WPF werden normalerweise als Ressource definiert eine <xref:System.Windows.ResourceDictionary>, und klicken Sie dann auf die verwiesen wird durch eine der beiden WPF-Markuperweiterungen, die eine Ressource anfordern. Die Markuperweiterung stellt die Auswertung des Eigenschaftswerts in eine Ressourcensuche zurück und ermöglicht die Bereitstellung von der <xref:System.Windows.FrameworkElement.Style%2A> Eigenschaft, wobei der Typ <xref:System.Windows.Style>in Attributsyntax wie im folgenden Beispiel:  
  
 `<Button Style="{StaticResource MyStyle}">My button</Button>`  
  
 Hier `StaticResource` identifiziert die <xref:System.Windows.StaticResourceExtension> -Klasse, die die Markuperweiterungsimplementierung bereitstellt. Die nächste Zeichenfolge `MyStyle` dient als Eingabe für den nicht standardmäßigen <xref:System.Windows.StaticResourceExtension> -Konstruktor, der Parameter aus der Erweiterungszeichenfolge, in dem der angeforderte deklariert <xref:System.Windows.ResourceKey>. `MyStyle`sollten die [X: Key](../../../../docs/framework/xaml-services/x-key-directive.md) Wert eine <xref:System.Windows.Style> als Ressource definiert. Die [StaticResource-Markuperweiterung](../../../../docs/framework/wpf/advanced/staticresource-markup-extension.md) Verwendung angefordert wird, dass die Ressource verwendet wird, geben Sie die <xref:System.Windows.Style> -Eigenschaftswert über die Logik einer statische Ressourcensuche zur Ladezeit.  
  
 Weitere Informationen über Markuperweiterungen finden Sie unter [Markuperweiterungen und WPF-XAML](../../../../docs/framework/wpf/advanced/markup-extensions-and-wpf-xaml.md). Referenzen zu Markuperweiterungen und anderen XAML-Programmierfunktionen in der allgemeinen .NET XAML-Implementierung aktiviert, finden Sie unter [XAML-Namespace (x:)) Sprachfeatures](../../../../docs/framework/xaml-services/xaml-namespace-x-language-features.md). WPF-spezifische Markuperweiterungen finden Sie unter [WPF-XAML-Erweiterungen](../../../../docs/framework/wpf/advanced/wpf-xaml-extensions.md).  
  
<a name="attached_properties"></a>   
## <a name="attached-properties"></a>Angefügte Eigenschaften  
 Angefügte Eigenschaften sind ein Programmierungskonzept in XAML durch Eigenschaften gehören und durch einen bestimmten Typ, definiert aber als Attribute oder Eigenschaftenelemente für jedes Element festgelegt. Das Hauptszenario für angefügte Eigenschaften bestimmt sind untergeordnete Elemente in einer Markupstruktur, um Informationen an ein übergeordnetes Element zu aktivieren, ohne dass ein umfassendes gemeinsam genutztes Objektmodell über alle Elemente ist. Umgekehrt können angefügte Eigenschaften von übergeordneten Elementen, Informationen zu untergeordneten Elementen verwendet werden. Weitere Informationen zu angefügten Eigenschaften und zum Erstellen eigener angefügte Eigenschaften, finden Sie unter [Übersicht über angefügte Eigenschaften](../../../../docs/framework/wpf/advanced/attached-properties-overview.md).  
  
 Angefügte Eigenschaften verwendete Syntax ähnelt der Eigenschaftenelementsyntax oberflächlich betrachtet, da Sie ebenfalls angeben einer *TypeName*.*PropertyName* zusammen. Es gibt zwei wichtige Unterschiede:  
  
-   Sie können die *TypeName*.*PropertyName* Kombination, selbst wenn eine angefügte Eigenschaft mittels Attributsyntax festlegen. Angefügte Eigenschaften sind der einzige Fall, qualifizieren den Eigenschaftennamen in der Attributsyntax erforderlich ist.  
  
-   Sie können auch Eigenschaftenelementsyntax für angefügte Eigenschaften verwenden. Für normale Eigenschaftenelementsyntax, jedoch die *TypeName* Sie angeben, ist das Object-Element, das das Property-Element enthält. Wenn Sie auf eine angefügte Eigenschaft, verweisen die *TypeName* -Klasse, die die angefügte Eigenschaft, nicht das Container-Objektelement definiert ist.  
  
<a name="attached_events"></a>   
## <a name="attached-events"></a>Angefügte Ereignisse  
 Bei angefügten Ereignissen handelt es sich um einen anderen Programmierungskonzept in XAML Ereignisse eines bestimmten Typs definiert werden können, wobei ein Handler für ein beliebiges Objektelement angefügt werden. Bei der Implementierung von Routingereignisalias werden häufig ist des Typs, der ein angefügtes Ereignis definiert einen statischen Typ, der einen Dienst definiert, und manchmal die angefügte Ereignisse durch einen Alias Routingereignis Typen, die den Dienst verfügbar machen. Handler für angefügte Ereignisse werden mit Attributsyntax angegeben. Mit angefügten Ereignissen, die Attributsyntax für angefügte Ereignisse zu erweiterten ein *TypeName*.*EventName* Verwendung, in dem *TypeName* ist die Klasse, die eine `Add` und `Remove` Ereignis-Handler Accessoren für die angefügte Ereignisinfrastruktur und *EventName* ist der Name des Ereignisses.  
  
<a name="anatomy_of_a_xaml_page_root_element"></a>   
## <a name="anatomy-of-a-xaml-root-element"></a>Anatomie einer XAML-Stammelement  
 Die folgende Tabelle zeigt normalerweise XAML-Stammelements aufgeschlüsselt, die spezifischen Attribute des ein Stammelement angezeigt:  
  
|||  
|-|-|  
|`<Page`|Öffnendes Objektelement des Stammelements|  
|`xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"`|Die Standardeinstellung ([!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]) XAML-Namespace|  
|`xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"`|XAML-Namespace der XAML-Sprache|  
|`x:Class="ExampleNamespace.ExampleCode"`|Die Deklaration der partiellen Klasse, die Markup mit Code-Behind verbindet für die partielle Klasse definiert|  
|`>`|Ende des Objektelements für den Stamm. Objekt ist noch nicht abgeschlossen, da das Element untergeordnete Elemente enthält.|  
  
<a name="optional_and_nonrecommended_xaml_usages"></a>   
## <a name="optional-and-nonrecommended-xaml-usages"></a>Dies ist optional und auf XAML-Verwendungen  
 Die folgenden Abschnitte beschreiben die XAML-Verwendungen technisch von XAML-Prozessoren unterstützt werden, aber der Ausführlichkeitsgrad oder andere ästhetischen Probleme, die XAML-Dateien, die verbleibenden lesbare Wenn stören erzeugt die Anwendungsentwicklung, die XAML-Quellen enthalten.  
  
### <a name="optional-property-element-usages"></a>Optionale Eigenschaftenelementen  
 Optionale Eigenschaftenelementen gehört Ausschreiben von explizit Element Content-Eigenschaften, dass der XAML-Prozessor als implizit behandelt. Deklarieren z. B. Wenn Sie den Inhalt der ein <xref:System.Windows.Controls.Menu>, können Sie festlegen, explizit deklarieren die <xref:System.Windows.Controls.ItemsControl.Items%2A> Auflistung von der <xref:System.Windows.Controls.Menu> als ein `<Menu.Items>` Property-Element-Tag, und Stelle jedes <xref:System.Windows.Controls.MenuItem> innerhalb `<Menu.Items>`, statt der impliziten XAML-Prozessorverhalten, alle untergeordneten Elemente des ein <xref:System.Windows.Controls.Menu> muss ein <xref:System.Windows.Controls.MenuItem> abgelegt und der <xref:System.Windows.Controls.ItemsControl.Items%2A> Auflistung. Manchmal können die Verwendung der optionalen helfen, um die Objektstruktur visuell zu verdeutlichen, wie im Markup angegeben. Oder manchmal eine explizite Eigenschaftenelementen Markup, das jedoch visuell verwirrend, wie z. B. verschachtelte Markuperweiterungen in einem Attributwert technisch funktionsfähig ist, vermeiden kann.  
  
### <a name="full-typenamemembername-qualified-attributes"></a>Vollständige typeName.memberName qualifizierte Attribute  
 The *typeName*.*MemberName* Formular für ein Attribut als nur bei Routingereignissen universell tatsächlich funktioniert. Aber in anderen Situationen ist diese Form überflüssig und sollte nicht verwendet werden, wenn nur aus Gründen der Markup-Stil und die Lesbarkeit. Im folgenden Beispiel, die drei Verweise auf die <xref:System.Windows.Controls.Control.Background%2A> Attribut sind vollständig äquivalent:  
  
 [!code-xml[XAMLOvwSupport#TypeNameProp](../../../../samples/snippets/csharp/VS_Snippets_Wpf/XAMLOvwSupport/CSharp/page8.xaml#typenameprop)]  
  
 `Button.Background`funktioniert, da die qualifizierte Suche für diese Eigenschaft auf <xref:System.Windows.Controls.Button> ist erfolgreich (<xref:System.Windows.Controls.Control.Background%2A> wurde vom Steuerelement geerbt) und <xref:System.Windows.Controls.Button> ist die Klasse des Objektelements oder eine Basisklasse. `Control.Background`funktioniert, da die <xref:System.Windows.Controls.Control> -Klasse definiert <xref:System.Windows.Controls.Control.Background%2A> und <xref:System.Windows.Controls.Control> ist ein <xref:System.Windows.Controls.Button> Basisklasse.  
  
 Allerdings die folgende *TypeName*.*MemberName* Beispiel funktioniert nicht und wird kommentiert:  
  
 [!code-xml[XAMLOvwSupport#TypeNameBadProp](../../../../samples/snippets/csharp/VS_Snippets_Wpf/XAMLOvwSupport/CSharp/page8.xaml#typenamebadprop)]  
  
 <xref:System.Windows.Controls.Label> ist eine weitere abgeleitete Klasse von <xref:System.Windows.Controls.Control>, und die Angabe `Label.Background` innerhalb einer <xref:System.Windows.Controls.Label> Object-Element, diese Verwendung würde gearbeitet haben. Allerdings da <xref:System.Windows.Controls.Label> ist nicht der Klasse oder Basisklasse von <xref:System.Windows.Controls.Button>, das angegebene XAML-Prozessorverhalten ist, verarbeitet `Label.Background` als angefügte Eigenschaft. `Label.Background`eine verfügbare angefügte Eigenschaft ist, und schlägt diese Methode fehl.  
  
### <a name="basetypenamemembername-property-elements"></a>Elemente der baseTypeName.memberName-Eigenschaft  
 So wie die *TypeName*.*MemberName* für Attributsyntax funktioniert die Form einer *Basistypname*.* MemberName* Syntax Eigenschaftenelementsyntax funktioniert. Beispielsweise kann die folgende Syntax:  
  
 [!code-xml[XAMLOvwSupport#GoofyPE](../../../../samples/snippets/csharp/VS_Snippets_Wpf/XAMLOvwSupport/CSharp/page8.xaml#goofype)]  
  
 Hier wurde das Eigenschaftenelement als angegeben `Control.Background` , obwohl das Eigenschaftenelement in enthalten war `Button`.  
  
 Aber wie *TypeName*.*MemberName* Form der Attribute, *Basistypname*.* MemberName* schlechter Stil im Markup ist, und sollte nicht verwendet werden.  
  
## <a name="see-also"></a>Siehe auch  
 [Übersicht über XAML (WPF)](../../../../docs/framework/wpf/advanced/xaml-overview-wpf.md)   
 [Verwendung von XAML-Namespace (x:)) Sprachfunktionen](../../../../docs/framework/xaml-services/xaml-namespace-x-language-features.md)   
 [WPF-XAML-Erweiterungen](../../../../docs/framework/wpf/advanced/wpf-xaml-extensions.md)   
 [Übersicht über Abhängigkeitseigenschaften](../../../../docs/framework/wpf/advanced/dependency-properties-overview.md)   
 [TypeConverter und XAML](../../../../docs/framework/wpf/advanced/typeconverters-and-xaml.md)   
 [XAML- und benutzerdefinierte Klassen für WPF](../../../../docs/framework/wpf/advanced/xaml-and-custom-classes-for-wpf.md)