---
title: "XAML-Related CLR Attributes for Custom Types and Libraries | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-wpf"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "CLR attributes for custom types [XAML Services]"
ms.assetid: 5dfb299a-b6e2-41b8-8694-e6ac987547f1
caps.latest.revision: 8
author: "wadepickett"
ms.author: "wpickett"
manager: "wpickett"
caps.handback.revision: 8
---
# XAML-Related CLR Attributes for Custom Types and Libraries
In diesem Thema werden die Attribute der Common Language Runtime \(CLR\) beschrieben, die in den .NET Framework\-XAML\-Diensten definiert sind.  Zudem werden weitere in .NET Framework definierte CLR\-Attribute beschrieben, die ein XAML\-bezogenes Szenario für die Anwendung auf Assemblys oder Typen aufweisen.  Durch die Zuordnung von Assemblys, Typen oder Membern zu diesen CLR\-Attributen werden XAML\-Typsysteminformationen für Ihre Typen bereitgestellt.  Jedem XAML\-Consumer, der .NET Framework\-XAML\-Dienste zum Verarbeiten des XAML\-Knotenstreams direkt oder durch die dedizierten XAML\-Reader oder XAML\-Writer verwendet, werden Informationen bereitgestellt.  
  
## XAML\-bezogene CLR\-Attribute für benutzerdefinierte Typen und Member  
 Die Verwendung von CLR\-Attributen bringt mit sich, dass die Typen mithilfe der gesamten CLR definiert werden müssen, andernfalls sind solche Attribute nicht verfügbar.  Wenn Sie mithilfe der CLR Typunterstützung definieren, kann der von XAML\-Writern der .NET Framework\-XAML\-Dienste verwendete XAML\-Standardschemakontext die CLR\-Zuordnung durch Reflektion mittels unterstützender Assemblys lesen.  
  
 In den folgenden Abschnitten werden die XAML\-bezogenen Attribute beschrieben, die Sie für benutzerdefinierte Typen oder Member übernehmen können.  Jedes CLR\-Attribut übermittelt für ein XAML\-Typsystem relevante Informationen.  Im Ladepfad ermöglichen die zugeordneten Informationen dem XAML\-Reader das Bilden eines gültigen XAML\-Knotenstreams oder dem XAML\-Writer das Erzeugen eines gültigen Objektdiagramms.  Im Speicherpfad ermöglichen die zugeordneten Informationen dem XAML\-Reader das Bilden eines gültigen XAML\-Knotenstreams zum Rekonstruieren von XAML\-Typsysteminformationen, oder sie deklarieren Serialisierungshinweise oder \-anforderungen für den XAML\-Writer oder andere XAML\-Consumer.  
  
### AmbientAttribute  
 **Referenzdokumentation:**  <xref:System.Windows.Markup.AmbientAttribute>  
  
 **Betrifft:** Klasse, Eigenschaft oder `get`\-Accessormember, die anfügbare Eigenschaften unterstützen  
  
 **Argumente:** keine  
  
 <xref:System.Windows.Markup.AmbientAttribute> gibt an, dass die Eigenschaft oder alle Eigenschaften, die den zugeordneten Typ akzeptieren, gemäß dem Ambient\-Eigenschaftskonzept in XAML interpretiert werden sollen.  Das Ambientekonzept bezieht sich darauf, wie XAML\-Prozessoren Typbesitzer von Membern bestimmen.  Eine Ambient\-Eigenschaft ist eine Eigenschaft, bei der der Wert im Parserkontext beim Erstellen eines Objektdiagramms erwartungsgemäß verfügbar ist, die typische Typmembersuche jedoch für den erstellten unmittelbaren XAML\-Knotengruppe angehalten wird.  
  
 Das Umgebungskonzept kann für anfügbare Member übernommen werden, die hinsichtlich der CLR\-Attribut\-Definition von <xref:System.AttributeTargets> nicht als Eigenschaften dargestellt werden.  Die Methodenattributierung sollte nur im Fall eines `get`\-Accessors angewendet werden, der die anfügbare Verwendung für XAML unterstützt.  
  
### ConstructorArgumentAttribute  
 **Referenzdokumentation:**  <xref:System.Windows.Markup.ConstructorArgumentAttribute>  
  
 **Betrifft:** Klasse  
  
 **Argumente:** Eine Zeichenfolge, die den Namen der Eigenschaft angibt, die einem einzelnen Konstruktorargument entspricht  
  
 <xref:System.Windows.Markup.ConstructorArgumentAttribute> gibt an, dass ein Objekt mit einer Nicht\-Standardkonstruktor\-Syntax initialisiert werden kann und dass eine Eigenschaft des angegebenen Namens Konstruktionsinformationen bereitstellt.  Diese Informationen sind hauptsächlich für die XAML\-Serialisierung vorgesehen.  Weitere Informationen finden Sie unter <xref:System.Windows.Markup.ConstructorArgumentAttribute>.  
  
### ContentPropertyAttribute  
 **Referenzdokumentation:**  <xref:System.Windows.Markup.ContentPropertyAttribute>  
  
 **Betrifft:** Klasse  
  
 **Argumente:** Eine Zeichenfolge, die den Namen eines Members des zugeordneten Typs angibt  
  
 <xref:System.Windows.Markup.ContentPropertyAttribute> gibt an, dass die Eigenschaft, wie vom Argument benannt, als XAML\-Inhaltseigenschaft für diesen Typ dienen sollte.  Die XAML\-Inhaltseigenschaftsdefinition erbt an alle abgeleiteten Typen, die dem definierenden Typ zuweisbar sind.  Sie können die Definition für einen bestimmten abgeleiteten Typ überschreiben, indem Sie <xref:System.Windows.Markup.ContentPropertyAttribute> auf den bestimmten abgeleiteten Typ anwenden.  
  
 Für die als XAML\-Inhaltseigenschaft dienende Eigenschaft kann das markierende Eigenschaftenelement in der XAML\-Verwendung weggelassen werden.  In der Regel werden XAML\-Inhaltseigenschaften festgelegt, die ein beschleunigtes XAML\-Markup für Inhalts\- und Kapselungsmodelle höherstufen.  Da nur ein Member als XAML\-Inhaltseigenschaft festgelegt werden kann, muss u. U. eine Designauswahl hinsichtlich der Containereigenschaft eines Typs getroffen werden, die als XAML\-Inhaltseigenschaft ausgewiesen werden soll.  Die anderen Containereigenschaften müssen mit expliziten Eigenschaftselementen verwendet werden.  
  
 Im XAML\-Knotenstream erzeugen XAML\-Inhaltseigenschaften immer noch `StartMember`\-Knoten und `EndMember`\-Knoten und verwenden den Namen der Eigenschaft für den <xref:System.Xaml.XamlMember>.  Um zu bestimmen, ob es sich bei einem Member um die XAML\-Inhaltseigenschaft handelt, überprüfen Sie den <xref:System.Xaml.XamlType>\-Wert an der `StartObject`\-Position, und rufen Sie den Wert von <xref:System.Xaml.XamlType.ContentProperty%2A> auf.  
  
### ContentWrapperAttribute  
 **Referenzdokumentation:**  <xref:System.Windows.Markup.ContentWrapperAttribute>  
  
 **Betrifft:** Klasse, insbesondere Auflistungstypen  
  
 **Argumente:** Ein <xref:System.Type>\-Element, das den Typ angibt, der als Inhaltswrappertyp für fremden Inhalt verwendet werden soll.  
  
 <xref:System.Windows.Markup.ContentWrapperAttribute> gibt mindestens einen Typ des zugeordneten Auflistungstyps an, mit dem fremder Inhalt umschlossen wird.  Fremder Inhalt verweist auf Fälle, in denen die Typsystemeinschränkungen für den Inhaltseigenschaftstyp nicht alle möglichen Inhaltsfälle erfassen, die die XAML\-Verwendung für den übergeordneten Typ unterstützen würde.  XAML\-Unterstützung für Inhalt eines bestimmten Typs könnte z. B. Zeichenfolgen in einem stark typisierten generischen <xref:System.Collections.ObjectModel.Collection%601> unterstützen.  Inhaltswrapper eignen sich für das Migrieren bereits vorhandener Markupkonventionen in das XAML\-Konzept zuweisbarer Werte für Auflistungen, z. B. das Migrieren textbezogener Inhaltsmodelle.  
  
 Übernehmen Sie mehrmals das Attribut, um mehr als einen Inhaltswrappertyp anzugeben.  
  
### DependsOnAttribute  
 **Referenzdokumentation:**  <xref:System.Windows.Markup.DependsOnAttribute>  
  
 **Betrifft:** Eigenschaft  
  
 **Argumente:** Eine Zeichenfolge, die den Namen eines weiteren Members des zugeordneten Typs angibt  
  
 <xref:System.Windows.Markup.DependsOnAttribute> gibt an, dass die zugeordnete Eigenschaft vom Wert einer anderen Eigenschaft abhängig ist.  Das Übernehmen dieses Attributs für eine Eigenschaftsdefinition stellt sicher, dass die abhängigen Eigenschaften zuerst beim Schreiben von XAML\-Objekten verarbeitet werden.  Die Verwendungen von <xref:System.Windows.Markup.DependsOnAttribute> geben die Ausnahmefälle von Eigenschaften für Typen an, bei denen eine bestimmte Analysereihenfolge zur gültigen Objekterstellung eingehalten werden muss.  
  
 Sie können mehrere <xref:System.Windows.Markup.DependsOnAttribute>\-Fälle auf eine Eigenschaftsdefinition anwenden.  
  
### MarkupExtensionReturnTypeAttribute  
 **Referenzdokumentation:**  <xref:System.Windows.Markup.MarkupExtensionReturnTypeAttribute>  
  
 **Betrifft:** Klasse, die ein von <xref:System.Windows.Markup.MarkupExtension> abgeleiteter Typ sein muss  
  
 **Argumente:** Ein <xref:System.Type>\-Element, durch das der präziseste zu erwartende Typ als `ProvideValue`\-Ergebnis des zugeordneten <xref:System.Windows.Markup.MarkupExtension>\-Elements angegeben wird  
  
 Weitere Informationen finden Sie unter [Markup Extensions for XAML Overview](../../../docs/framework/xaml-services/markup-extensions-for-xaml-overview.md).  
  
### NameScopePropertyAttribute  
 **Referenzdokumentation:**  <xref:System.Windows.Markup.NameScopePropertyAttribute>  
  
 **Betrifft:** Klasse  
  
 **Argumente:** unterstützt zwei Formulare der Attributierung:  
  
-   Zeichenfolgen, die den Namen einer Eigenschaft des attributierten Typs angeben.  
  
-   Eine Zeichenfolge, die den Namen der Eigenschaft und ein <xref:System.Type>\-Element für den Typ angibt, der die benannte Eigenschaft darstellt.  Dieses Formular dient zum Angeben eines anfügbaren Members als XAML\-Namescope\-Eigenschaft.  
  
 <xref:System.Windows.Markup.NameScopePropertyAttribute> gibt eine Eigenschaft an, die den Wert des XAML\-Namescopes für die attributierte Klasse bereitstellt.  Die XAML\-Namescope\-Eigenschaft soll auf ein Objekt verweisen, das <xref:System.Windows.Markup.INameScope> implementiert und den tatsächlichen XAML\-Namescope, seinen Speicher und sein Verhalten beinhaltet.  
  
### RuntimeNamePropertyAttribute  
 **Referenzdokumentation:**  <xref:System.Windows.Markup.RuntimeNamePropertyAttribute>  
  
 **Betrifft:** Klasse  
  
 **Argumente:** Eine Zeichenfolge, die den Namen der Laufzeitnamenseigenschaft für den zugeordneten Typ angibt  
  
 <xref:System.Windows.Markup.RuntimeNamePropertyAttribute> meldet eine Eigenschaft des zugeordneten Typs, der der XAML\-[x:Name Directive](../../../docs/framework/xaml-services/x-name-directive.md) entspricht.  Die Eigenschaft muss vom Typ <xref:System.String> sein sowie Lese\-\/Schreibzugriff aufweisen.  
  
 Die Definition erbt an alle abgeleiteten Typen, die dem zu definierenden Typ zuweisbar sind.  Sie können die Definition für einen bestimmten abgeleiteten Typ überschreiben, indem Sie <xref:System.Windows.Markup.RuntimeNamePropertyAttribute> auf den bestimmten abgeleiteten Typ anwenden.  
  
### TrimSurroundingWhitespaceAttribute  
 **Referenzdokumentation:**  <xref:System.Windows.Markup.TrimSurroundingWhitespaceAttribute>  
  
 **Betrifft:** Typen  
  
 **Argumente:** keine  
  
 <xref:System.Windows.Markup.TrimSurroundingWhitespaceAttribute> wird auf bestimmte Typen angewendet, die als untergeordnete Elemente in für Leerstellen bedeutenden Inhalt \(Inhalt einer Auflistung mit <xref:System.Windows.Markup.WhitespaceSignificantCollectionAttribute>\) angezeigt werden können.  <xref:System.Windows.Markup.TrimSurroundingWhitespaceAttribute> ist hauptsächlich relevant für den Speicherpfad aber ist ebenfalls im XAML\-Typsystem im Ladepfad durch Untersuchen des <xref:System.Xaml.XamlType.TrimSurroundingWhitespace%2A?displayProperty=fullName>\-Elements verfügbar.  Weitere Informationen finden Sie unter [Whitespace Processing in XAML](../../../docs/framework/xaml-services/whitespace-processing-in-xaml.md).  
  
### TypeConverterAttribute  
 **Referenzdokumentation:**  <xref:System.ComponentModel.TypeConverterAttribute>  
  
 **Betrifft:** Klasse, Eigenschaft, Methode \(die einzige in XAML gültige Methode ist ein `get`\-Accessor, der einen anfügbaren Member unterstützt\)  
  
 **Argumente:** Der <xref:System.Type> des <xref:System.ComponentModel.TypeConverter>  
  
 <xref:System.ComponentModel.TypeConverterAttribute> verweist im XAML\-Kontext auf ein benutzerdefiniertes <xref:System.ComponentModel.TypeConverter>\-Element.  Dieses <xref:System.ComponentModel.TypeConverter>\-Element stellt Typkonvertierungsverhalten für benutzerdefinierte Typen oder Member dieses Typs bereit.  
  
 Das <xref:System.ComponentModel.TypeConverterAttribute>\-Attribut wird auf Ihren Typ angewendet, und es wird auf die Typkonverterimplementierung verwiesen.  Sie können XAML\-Typkonverter für Klassen, Strukturen oder Schnittstellen definieren.  Sie müssen keine Typkonvertierung für Enumerationen bereitstellen, für die Konvertierung systemintern aktiviert ist.  
  
 Der Typkonverter sollte in der Lage sein, von Zeichenfolgen, die für Attribute oder Initialisierungstext in Markup verwendet werden, in den beabsichtigten Zieltyp zu konvertieren.  Weitere Informationen finden Sie unter [TypeConverter und XAML](../../../docs/framework/wpf/advanced/typeconverters-and-xaml.md).  
  
 Statt für alle Werte eines Typs kann ein Typkonverterverhalten für XAML auch lediglich für eine bestimmte Eigenschaft festgelegt werden.  In diesem Fall wenden Sie <xref:System.ComponentModel.TypeConverterAttribute> auf die Eigenschaftendefinition \(die äußere Definition, nicht die bestimmten `get`\- und `set`\-Definitionen\) an.  
  
 Ein Typkonverterverhalten für die XAML\-Verwendung eines benutzerdefinierten anfügbaren Members kann zugewiesen werden, indem <xref:System.ComponentModel.TypeConverterAttribute> auf den `get`\-Methodenaccessor angewendet wird, der die XAML\-Verwendung unterstützt.  
  
 Wie auch <xref:System.ComponentModel.TypeConverter> war <xref:System.ComponentModel.TypeConverterAttribute> bereits vor XAML in .NET Framework vorhanden, und das Typkonvertermodell diente anderen Zwecken.  Damit ein Verweis auf das <xref:System.ComponentModel.TypeConverterAttribute>\-Element erstellt und darauf verwiesen werden kann, müssen Sie es vollständig qualifizieren oder eine `using`\-Anweisung für <xref:System.ComponentModel> bereitstellen.  Sie müssen außerdem die Systemassembly im Projekt implementieren.  
  
### UidPropertyAttribute  
 **Referenzdokumentation:**  <xref:System.Windows.Markup.UidPropertyAttribute>  
  
 **Betrifft:** Klasse  
  
 **Argumente:** Zeichenfolgen, die auf die relevanten Eigenschaften nach Name verweisen.  
  
 Gibt die CLR\-Eigenschaft einer Klasse an, die auf den [x:Uid Directive](../../../docs/framework/xaml-services/x-uid-directive.md)\-Wert verweist.  
  
### UsableDuringInitializationAttribute  
 **Referenzdokumentation:**  <xref:System.Windows.Markup.UsableDuringInitializationAttribute>  
  
 **Betrifft:** Klasse  
  
 **Argumente:** ein boolescher Wert.  Sofern für den beabsichtigten Zweck des Attributs verwendet, sollte hierfür immer `true` angegeben werden.  
  
 Gibt an, ob dieser Typ während der Erstellung von XAML\-Objektdiagrammen von oben nach unten erstellt wird.  Dies ist ein erweitertes Konzept, das sich wahrscheinlich eng auf die Definition des Programmiermodells bezieht.  Weitere Informationen finden Sie unter <xref:System.Windows.Markup.UsableDuringInitializationAttribute>.  
  
### ValueSerializerAttribute  
 **Referenzdokumentation:**  <xref:System.Windows.Markup.ValueSerializerAttribute>  
  
 **Betrifft:** Klasse, Eigenschaft, Methode \(die einzige in XAML gültige Methode ist ein `get`\-Accessor, der einen anfügbaren Member unterstützt\)  
  
 **Argumente:** Ein <xref:System.Type>\-Element, das beim Serialisieren aller Eigenschaften des attributierten Typs oder der bestimmten attributierten Eigenschaft die zu verwendende Wertserialisierungs\-Unterstützungsklasse angibt.  
  
 <xref:System.Windows.Markup.ValueSerializer> gibt eine Wertserialisierungsklasse an, die mehr Status und Kontext erfordert, als ein <xref:System.ComponentModel.TypeConverter>\-Element.  Ein <xref:System.Windows.Markup.ValueSerializer>\-Element kann einer anfügbaren Eigenschaft zugeordnet werden, indem das <xref:System.Windows.Markup.ValueSerializerAttribute>\-Attribut auf die statische `get`\-Methode für den anfügbaren Member angewendet wird.  Die Wertserialisierung ist auch auf Enumerationen, Schnittstellen und Strukturen anwendbar, nicht aber auf Delegaten.  
  
### WhitespaceSignificantCollectionAttribute  
 **Referenzdokumentation:**  <xref:System.Windows.Markup.WhitespaceSignificantCollectionAttribute>  
  
 **Betrifft:** Klasse, insbesondere Auflistungstypen, die gemischten Inhalt hosten sollen, bei dem Leerzeichen um Objektelemente für die Benutzeroberflächendarstellung wichtig sein können  
  
 **Argumente:** keine  
  
 <xref:System.Windows.Markup.WhitespaceSignificantCollectionAttribute> gibt an, dass ein Auflistungstyp von einen XAML\-Prozessor als wichtig für Leerzeichen verarbeitet werden muss, wodurch die Konstruktion der Wertknoten des XAML\-Knotenstreams innerhalb der Auflistung beeinflusst wird.  Weitere Informationen finden Sie unter [Whitespace Processing in XAML](../../../docs/framework/xaml-services/whitespace-processing-in-xaml.md).  
  
### XamlDeferLoadAttribute  
 **Referenzdokumentation:**  <xref:System.Windows.Markup.XamlDeferLoadAttribute>  
  
 **Betrifft:** Klasse, Eigenschaft  
  
 **Argumente:** Unterstützt zwei Zuordnungstypen als Zeichenfolgen oder Typen als <xref:System.Type>.  Weitere Informationen finden Sie unter <xref:System.Windows.Markup.XamlDeferLoadAttribute>.  
  
 Gibt an, dass eine Klasse oder eine Eigenschaft über eine verzögerte Auslastungsverwendung für XAML \(z. B. ein Vorlagenverhalten\) verfügt, und meldet die Klasse, die das verzögernde Verhalten und seinen Ziel\-\/Inhaltstyp aktiviert.  
  
### XamlSetMarkupExtensionAttribute  
 **Referenzdokumentation:**  <xref:System.Windows.Markup.XamlSetMarkupExtensionAttribute>  
  
 **Betrifft:** Klasse  
  
 **Argumente:** Benennt den Rückruf.  
  
 Gibt an, dass eine Klasse mithilfe einer Markuperweiterung für eine oder mehrere Eigenschaften einen Wert bereitstellen kann, und verweist auf einen Handler, den ein XAML\-Writer vor dem Ausführen eines Markuperweiterungs\-Set\-Vorgangs in einer beliebigen Eigenschaft der Klasse aufrufen sollte.  
  
### XamlSetTypeConverterAttribute  
 **Referenzdokumentation:**  <xref:System.Windows.Markup.XamlSetTypeConverterAttribute>  
  
 **Betrifft:** Klasse  
  
 **Argumente:** Benennt den Rückruf.  
  
 Gibt an, dass eine Klasse mithilfe eines Typkonverters für eine oder mehrere Eigenschaften einen Wert bereitstellen kann, und verweist auf einen Handler, den ein XAML\-Writer vor dem Ausführen eines Typkonverter\-Set\-Vorgangs in einer beliebigen Eigenschaft der Klasse aufrufen sollte.  
  
### XmlLangPropertyAttribute  
 **Referenzdokumentation:**  <xref:System.Windows.Markup.XmlLangPropertyAttribute>  
  
 **Betrifft:** Klasse  
  
 **Argumente:** Eine Zeichenfolge, die den Namen der Eigenschaft, für die ein Alias hinzugefügt werden soll, für `xml:lang` für den attributierten Typ angibt.  
  
 <xref:System.Windows.Markup.XmlLangPropertyAttribute> meldet eine Eigenschaft des attributierten Typs, der der `lang`\-XML\-Direktive zugeordnet ist.  Die Eigenschaft weist nicht notwendigerweise den <xref:System.String>\-Typ auf, aber es muss von einer Zeichenfolge auf sie verwiesen werden können. Dies kann erreicht werden, indem ein Typkonverter dem Eigenschaftstyp oder der speziellen Eigenschaft zugeordnet wird.  Für die Eigenschaft muss Lese\-\/Schreibzugriff festgelegt sein.  
  
 Das Szenario zum Zuordnen von `xml:lang` gestaltet sich wie beschrieben, damit ein Runtime\-Objektmodell auf in XML angegebene Sprachinformationen Zugriff hat, ohne ausdrücklich mit einem XMLDOM verarbeiten zu müssen.  
  
 Die Definition erbt an alle abgeleiteten Typen, die dem zu definierenden Typ zuweisbar sind.  Sie können die Definition für einen bestimmten abgeleiteten Typ überschreiben, indem Sie <xref:System.Windows.Markup.XmlLangPropertyAttribute> für den bestimmten abgeleiteten Typ übernehmen, auch wenn dies ein ungewöhnliches Szenario ist.  
  
## XAML\-bezogene CLR\-Attribute auf Assembly\-Ebene  
 In den folgenden Abschnitten werden die XAML\-bezogenen Attribute beschrieben, die nicht auf Typen oder Memberdefinitionen angewendet sondern stattdessen für Assemblys übernommen werden.  Diese Attribute entsprechen dem Endziel, eine Bibliothek mit benutzerdefinierten Typen zu definieren, die in XAML verwendet werden sollen.  Einige der Attribute beeinflussen nicht notwendigerweise direkt den XAML\-Knotenstream, sondern werden im Knotenstream an andere Consumer zur Verwendung übergeben.  Consumer für die Informationen enthalten Entwurfsumgebungen oder Serialisierungsprozesse, die XAML\-Namespaceinformationen und zugeordnete Präfixinformationen erfordern.  Ein XAML\-Schemakontext \(einschließlich der standardmäßigen .NET Framework\-XAML\-Dienste\) verwendet ebenfalls diese Informationen.  
  
### XmlnsCompatibleWithAttribute  
 **Referenzdokumentation:**  <xref:System.Windows.Markup.XmlnsCompatibleWithAttribute>  
  
 **Argumente:**  
  
-   Zeichenfolgen, die den Bezeichner des XAML\-Namespace zur Klassifizierung angeben.  
  
-   Eine Zeichenfolge, die den Bezeichner des XAML\-Namespace angibt, der den XAML\-Namespace des vorherigen Arguments klassifizieren kann.  
  
 <xref:System.Windows.Markup.XmlnsCompatibleWithAttribute> gibt an, dass ein XAML\-Namespace von einem weiteren XAML\-Namespace klassifiziert werden kann.  In der Regel wird der klassifizierende XAML\-Namespace in einem zuvor definierten <xref:System.Windows.Markup.XmlnsDefinitionAttribute> angegeben.  Diese Technik kann zur Versionsverwaltung eines XAML\-Vokabulars in einer Bibliothek verwendet werden. Außerdem kann so das Vokabular einer früheren Version mit zuvor definierten Markups verwendet werden.  
  
### XmlnsDefinitionAttribute  
 **Referenzdokumentation:**  <xref:System.Windows.Markup.XmlnsDefinitionAttribute>  
  
 **Argumente:**  
  
-   Zeichenfolgen, die den Bezeichner des XAML\-Namespace zur Definition angeben.  
  
-   Eine Zeichenfolge, die einen CLR\-Namespace benennt.  Der CLR\-Namespace muss öffentliche Typen in der Assembly definieren, und mindestens einer der CLR\-Namespacetypen sollte zur XAML\-Verwendung vorgesehen sein.  
  
 <xref:System.Windows.Markup.XmlnsDefinitionAttribute> gibt eine pro Assembly vorgenommene Zuordnung zwischen einem XAML\-Namespace und einem CLR\-Namespace an, die anschließend zur Typauflösung durch einen XAML\-Objektwriter oder XAML\-Schemakontext verwendet wird.  
  
 Mehrere <xref:System.Windows.Markup.XmlnsDefinitionAttribute>\-Elemente können für eine Assembly übernommen werden.  Dies könnte aus folgenden Gründen geschehen:  
  
-   Der Bibliotheksentwurf enthält mehrere CLR\-Namespaces für die logische Organisation des Laufzeit\-API\-Zugriffs. Sie möchten jedoch, dass alle Typen in diesen Namespaces mittels Verweis auf den gleichen XAML\-Namespace in XAML verwendet werden können.  In diesem Fall wenden Sie mehrere <xref:System.Windows.Markup.XmlnsDefinitionAttribute>\-Attribute mit dem gleichen <xref:System.Windows.Markup.XmlnsDefinitionAttribute.XmlNamespace%2A>\-Wert aber unterschiedlichen <xref:System.Windows.Markup.XmlnsDefinitionAttribute.ClrNamespace%2A>\-Werten an.  Dies ist besonders nützlich, wenn Sie Zuordnungen für den XAML\-Namespace definieren, der in der Syntax vom Framework oder von der Anwendung als standardmäßiger XAML\-Namespace verwendet werden soll.  
  
-   Der Bibliotheksentwurf enthält mehrere CLR\-Namespaces, und Sie möchten eine XAML\-Namespacetrennung zwischen den Typverwendungen in diesen CLR\-Namespaces.  
  
-   Sie definieren einen CLR\-Namespace in der Assembly, auf den von mehreren XAML\-Namespaces aus zugegriffen werden kann.  Dieses Szenario tritt auf, wenn Sie mehrere Vokabulare mit der gleichen CodeBase unterstützen.  
  
-   XAML\-Sprachunterstützung wird in mindestens einem CLR\-Namespace definiert.  Für diese sollte der <xref:System.Windows.Markup.XmlnsDefinitionAttribute.XmlNamespace%2A>\-Wert `http://schemas.microsoft.com/winfx/2006/xaml` sein.  
  
### XmlnsPrefixAttribute  
 **Referenzdokumentation:**  <xref:System.Windows.Markup.XmlnsPrefixAttribute>  
  
 **Argumente:**  
  
-   Zeichenfolgen, die den Bezeichner eines XAML\-Namespace angeben.  
  
-   Eine Zeichenfolge, die ein empfohlenes Präfix angibt.  
  
 <xref:System.Windows.Markup.XmlnsDefinitionAttribute> gibt ein empfohlenes Präfix an, das für einen XAML\-Namespace verwendet werden soll.  Das Präfix ist beim Schreiben von Elementen und Attributen in einer XAML\-Datei hilfreich, die vom <xref:System.Xaml.XamlXmlWriter> der .NET Framework\-XAML\-Dienste serialisiert wird, oder wenn eine Bibliothek, die XAML implementiert, mit einer Entwurfsumgebung mit XAML\-Bearbeitungsfunktionen interagiert.  
  
 Auf eine Assembly können mehrere <xref:System.Windows.Markup.XmlnsPrefixAttribute> angewendet werden.  Dies könnte aus folgenden Gründen geschehen:  
  
-   Die Assembly definiert Typen für mehr als einen XAML\-Namespace.  In diesem Fall sollten Sie für jeden XAML\-Namespace andere Präfixwerte definieren.  
  
-   Es werden mehrere Vokabulare unterstützt, und Sie verwenden unterschiedliche Präfixe für jedes Vokabular und jeden XAML\-Namespace.  
  
-   XAML\-Sprachunterstützung wird in der Assembly definiert, und ein <xref:System.Windows.Markup.XmlnsDefinitionAttribute> ist für `http://schemas.microsoft.com/winfx/2006/xaml` vorhanden.  In diesem Fall sollten Sie das `x`\-Präfix höherstufen.  
  
> [!NOTE]
>  .NET Framework\-XAML\-Dienste definieren auch das XAML\-bezogene <xref:System.Windows.Markup.RootNamespaceAttribute>\-Attribut.  Dieses Attribut ist ein Attribut auf Assemblyebene zur Projektsystemunterstützung und für benutzerdefinierte XAML\-Typen nicht relevant.  
  
## Siehe auch  
 <xref:System.Attribute>   
 [Defining Custom Types for Use with .NET Framework XAML Services](../../../docs/framework/xaml-services/defining-custom-types-for-use-with-net-framework-xaml-services.md)