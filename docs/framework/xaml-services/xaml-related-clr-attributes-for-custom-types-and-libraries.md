---
title: XAML-bezogene CLR-Attribute für benutzerdefinierte Typen und Bibliotheken
ms.date: 03/30/2017
helpviewer_keywords:
- CLR attributes for custom types [XAML Services]
ms.assetid: 5dfb299a-b6e2-41b8-8694-e6ac987547f1
ms.openlocfilehash: fc99ada6a3bc8465d22527a7ef985f9b057bcf77
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="xaml-related-clr-attributes-for-custom-types-and-libraries"></a>XAML-bezogene CLR-Attribute für benutzerdefinierte Typen und Bibliotheken
Dieses Thema beschreibt die common Language Common Language Runtime (CLR)-Attribute, die von .NET Framework XAML Services definiert sind. Es beschreibt auch andere CLR-Attribute, die in .NET Framework definiert sind, die einen XAML-bezogene-Szenario für die Anwendung auf Assemblys oder Typen aufweisen. Attributierung Assemblys, Typen oder Member mit diesen Attributen CLR bietet Systeminformationen von XAML-Typ im Zusammenhang mit den Typen. Informationen werden für alle XAML-Consumer bereitgestellt, die .NET Framework-XAML-Dienste für die Verarbeitung von XAML-Knotenstream direkt oder über die dedizierte XAML-Readern und XAML-Writern verwendet.  
  
## <a name="xaml-related-clr-attributes-for-custom-types-and-custom-members"></a>XAML-bezogene CLR-Attribute für benutzerdefinierte Typen und benutzerdefinierte Elemente  
 Verwenden von CLR-Attributen erfordert, dass Sie mithilfe der gesamten CLR die Typen definieren, die solche Attribute sind andernfalls nicht verfügbar. Wenn Sie die CLR verwenden, um typunterstützung zu definieren, kann die standardmäßigen XAML-Schemakontext, die von .NET Framework XAML Services XAML-Writer verwendet CLR namensnennung über Reflektion unterstützenden Assemblys lesen.  
  
 In den folgenden Abschnitten wird beschrieben, die XAML-bezogene Attribute, die auf benutzerdefinierte Typen oder Member angewendet werden können. Jede CLR-Attributen kommuniziert Informationen, die einem XAML-Typsystem relevant sind. Im Ladepfad attributierte Informationen können entweder den XAML-Reader einen gültigen XAML-Knotenstream zu bilden, oder sie hilft bei der XAML-Writer ein gültiges Objektdiagramm erstellt. Im Speicherpfad Pfad, der die attributierte Informationen entweder hilft den XAML-Reader einen gültigen XAML-Knotenstream zu bilden, für die Verwendung von XAML-System zu Empfängerseite oder sie Serialisierung Hinweise oder Anforderungen für die Verwendung von XAML-Writer oder anderen XAML-Consumern deklariert.  
  
### <a name="ambientattribute"></a>AmbientAttribute  
 **Referenzdokumentation:**  <xref:System.Windows.Markup.AmbientAttribute>  
  
 **Gilt für:** -Klasse, Eigenschaft oder `get` Accessor-Elemente, die anfügbare Eigenschaften unterstützen.  
  
 **Argumente:** None  
  
 <xref:System.Windows.Markup.AmbientAttribute> Gibt an, dass die Eigenschaft oder alle Eigenschaften, die der attributierten Typ akzeptieren unter der ambient-Eigenschaftskonzept in XAML interpretiert werden sollen. Das Umgebungskonzept bezieht sich darauf, wie XAML-Prozessoren Typbesitzer von Membern bestimmen. Eine Ambiente-Eigenschaft ist eine Eigenschaft, in dem der Wert muss in der Parserkontext verfügbar sein, für die Erstellung eines Objektdiagramms, jedoch typische Typmember Suche angehalten wird, für den unmittelbaren Verwendung von XAML-Knoten festgelegt, wird erstellt.  
  
 Das Umgebungskonzept kann angewendet werden, für anfügbare Member, die nicht dargestellt werden, als Eigenschaften in Bezug auf die CLR-namensnennung wie definiert <xref:System.AttributeTargets>. Die Methode namensnennung Verwendung angewendet werden soll, nur im Fall von einem `get` Zugriffsmethode, die anfügbare Verwendung für XAML unterstützt.  
  
### <a name="constructorargumentattribute"></a>ConstructorArgumentAttribute  
 **Referenzdokumentation:**  <xref:System.Windows.Markup.ConstructorArgumentAttribute>  
  
 **Gilt für:** Klasse  
  
 **Argumente:** eine Zeichenfolge, die den Namen der Eigenschaft angibt, die einem einzelnen Konstruktorargument entspricht.  
  
 <xref:System.Windows.Markup.ConstructorArgumentAttribute> Gibt an, dass ein Objekt mit einer nicht standardmäßigen Konstruktor initialisiert werden kann, und eine Eigenschaft mit dem angegebenen Namen Informationen zur Erstellung bereitstellt. Diese Informationen sind in erster Linie für die XAML-Serialisierung vorgesehen. Weitere Informationen finden Sie unter <xref:System.Windows.Markup.ConstructorArgumentAttribute>.  
  
### <a name="contentpropertyattribute"></a>"ContentPropertyAttribute"  
 **Referenzdokumentation:**  <xref:System.Windows.Markup.ContentPropertyAttribute>  
  
 **Gilt für:** Klasse  
  
 **Argumente:** eine Zeichenfolge, die den Namen eines Members des attributierten Typs angibt.  
  
 <xref:System.Windows.Markup.ContentPropertyAttribute> Gibt an, dass die Eigenschaft als durch das Argument mit dem Namen als die Verwendung von XAML-Inhaltseigenschaft für diesen Typ verwendet werden soll. Die Definition der XAML-Inhaltseigenschaft erbt an alle abgeleiteten Typen, die zu definierenden Typ zugewiesen werden. Sie können die Definition für einen bestimmten abgeleiteten Typ außer Kraft setzen, durch Anwenden von <xref:System.Windows.Markup.ContentPropertyAttribute> auf den bestimmten abgeleiteten Typ.  
  
 Für die Eigenschaft, die als die Verwendung von XAML-Inhaltseigenschaft dient, kann die Property-Element-Tags für die Eigenschaft in der Verwendung von XAML-ausgelassen werden. In der Regel legen Sie die Verwendung von XAML-Content-Eigenschaften, die ein optimiertes XAML-Markup für den Inhalt und Kapselung Modellen höher stufen. Da nur ein Element als die Verwendung von XAML-Inhaltseigenschaft festgelegt werden kann, müssen Sie manchmal Entwurfsoptionen vornehmen Hinblick auf die mehrere Container Eigenschaften eines Typs als die Verwendung von XAML-Inhaltseigenschaft festgelegt werden soll. Die anderen Containereigenschaften müssen mit expliziten Eigenschaftenelemente verwendet werden.  
  
 In der XAML-Knotenstream erzeugen XAML-Inhaltseigenschaften weiterhin `StartMember` und `EndMember` Knoten, mit dem Namen der Eigenschaft für die <xref:System.Xaml.XamlMember>. Um zu bestimmen, ob ein Element die Verwendung von XAML-Inhaltseigenschaft ist, Überprüfen der <xref:System.Xaml.XamlType> Wert aus der `StartObject` positionieren und Abrufen des Werts <xref:System.Xaml.XamlType.ContentProperty%2A>.  
  
### <a name="contentwrapperattribute"></a>ContentWrapperAttribute  
 **Referenzdokumentation:**  <xref:System.Windows.Markup.ContentWrapperAttribute>  
  
 **Gilt für:** -Klasse, insbesondere Auflistungstypen.  
  
 **Argumente:** ein <xref:System.Type> , die den Typ als Typ Inhaltswrapper für fremden Inhalt angibt.  
  
 <xref:System.Windows.Markup.ContentWrapperAttribute> Gibt einen oder mehrere Typen auf den zugeordneten Auflistungstyps an, mit der fremden Inhalt zu umschließen. Fremden Inhalt bezieht sich auf Fälle, bei denen typeinschränkungen System für den Typ der Content-Eigenschaft nicht alle möglichen Fälle Inhalt aufgezeichnet werden, die XAML-Verwendung für den besitzenden Typs unterstützen würden. Z. B. Unterstützung von XAML für Inhalt eines bestimmten Typs Zeichenfolgen in eine stark typisierte generische unterstützen möglicherweise <xref:System.Collections.ObjectModel.Collection%601>. Inhaltswrapper eignen sich zum Migrieren von vorhandenen Markup-Konventionen in der XAML-Konzeption der zuweisbare Werte für Auflistungen, z. B. Migrieren von Text-bezogene Inhaltsmodelle.  
  
 Um mehr als ein Inhaltswrapper-Typ anzugeben, wenden Sie das Attribut mehrmals.  
  
### <a name="dependsonattribute"></a>DependsOnAttribute  
 **Referenzdokumentation:**  <xref:System.Windows.Markup.DependsOnAttribute>  
  
 **Gilt für:** Eigenschaft  
  
 **Argumente:** eine Zeichenfolge, die den Namen eines anderen Elements des attributierten Typs angibt.  
  
 <xref:System.Windows.Markup.DependsOnAttribute> Gibt an, dass die attributierte Eigenschaft den Wert einer anderen Eigenschaft abhängig ist. Das Anwenden dieses Attributs auf eine Eigenschaftsdefinition wird sichergestellt, dass die abhängigen Eigenschaften zuerst im Schreiben von XAML-Objekt verarbeitet werden. Verwendungen von <xref:System.Windows.Markup.DependsOnAttribute> Ausnahmefälle von Eigenschaften für Typen, in denen eine bestimmte Reihenfolge der Analyse werden, zum Erstellen eines gültigen Objekts beachtet muss, angeben.  
  
 Sie können mehrere anwenden <xref:System.Windows.Markup.DependsOnAttribute> Fälle auf eine Eigenschaftsdefinition.  
  
### <a name="markupextensionreturntypeattribute"></a>MarkupExtensionReturnTypeAttribute  
 **Referenzdokumentation:**  <xref:System.Windows.Markup.MarkupExtensionReturnTypeAttribute>  
  
 **Gilt für:** -Klasse, die voraussichtlich ein <xref:System.Windows.Markup.MarkupExtension> abgeleiteten Typ.  
  
 **Argumente:** ein <xref:System.Type> , die Ausdrucksdatentyp als erwartet gibt die `ProvideValue` Ergebnis die attributierte <xref:System.Windows.Markup.MarkupExtension>.  
  
 Weitere Informationen finden Sie unter [Markup Extensions for XAML Overview](../../../docs/framework/xaml-services/markup-extensions-for-xaml-overview.md).  
  
### <a name="namescopepropertyattribute"></a>NameScopePropertyAttribute  
 **Referenzdokumentation:**  <xref:System.Windows.Markup.NameScopePropertyAttribute>  
  
 **Gilt für:** Klasse  
  
 **Argumente:** unterstützt zwei Arten von Informationsblatt befindet:  
  
-   Eine Zeichenfolge, die den Namen einer Eigenschaft des Attributtyps angibt.  
  
-   Eine Zeichenfolge, die den Namen einer Eigenschaft angibt und ein <xref:System.Type> für den Typ, der die benannte Eigenschaft definiert. Dieses Formular ist zum Angeben einer anfügbaren Members als die Verwendung von XAML-Namensbereich der XAML-Eigenschaft.  
  
 <xref:System.Windows.Markup.NameScopePropertyAttribute> Gibt eine Eigenschaft, die für die attributierte Klasse den Wert des XAML-Namescopes bereitstellt. Die Verwendung von XAML-Namensbereich der XAML-Eigenschaft muss auf ein Objekt zu verweisen, die implementiert <xref:System.Windows.Markup.INameScope> und enthält die tatsächliche Verwendung von XAML-Namensbereich, seinen Speicher und sein Verhalten.  
  
### <a name="runtimenamepropertyattribute"></a>RuntimeNamePropertyAttribute  
 **Referenzdokumentation:**  <xref:System.Windows.Markup.RuntimeNamePropertyAttribute>  
  
 **Gilt für:** Klasse  
  
 **Argumente:** eine Zeichenfolge, die den Namen der Laufzeit-Name-Eigenschaft des Attributtyps angibt.  
  
 <xref:System.Windows.Markup.RuntimeNamePropertyAttribute> Gibt eine Eigenschaft des Attributtyps, der den XAML-Code zugeordnet [X: Name-Direktive](../../../docs/framework/xaml-services/x-name-directive.md). Die Eigenschaft muss vom Typ <xref:System.String> muss Lese-/Schreibzugriff.  
  
 Die Definition erbt an alle abgeleiteten Typen, die zu definierenden Typ zugewiesen werden. Sie können die Definition für einen bestimmten abgeleiteten Typ außer Kraft setzen, durch Anwenden von <xref:System.Windows.Markup.RuntimeNamePropertyAttribute> auf den bestimmten abgeleiteten Typ.  
  
### <a name="trimsurroundingwhitespaceattribute"></a>TrimSurroundingWhitespaceAttribute  
 **Referenzdokumentation:**  <xref:System.Windows.Markup.TrimSurroundingWhitespaceAttribute>  
  
 **Gilt für:** Typen  
  
 **Argumente:** None.  
  
 <xref:System.Windows.Markup.TrimSurroundingWhitespaceAttribute> gilt für bestimmte Typen, die angezeigt als untergeordnete Elemente in der wichtige Leerzeichen-Inhalt werden (Inhalt von einer Auflistung mit reservierten <xref:System.Windows.Markup.WhitespaceSignificantCollectionAttribute>). <xref:System.Windows.Markup.TrimSurroundingWhitespaceAttribute> wird hauptsächlich relevant für den Pfad, jedoch steht in der XAML-Typsystem im Ladepfad durch Untersuchen <xref:System.Xaml.XamlType.TrimSurroundingWhitespace%2A?displayProperty=nameWithType>. Weitere Informationen finden Sie unter [Leerstellenverarbeitung in XAML](../../../docs/framework/xaml-services/whitespace-processing-in-xaml.md).  
  
### <a name="typeconverterattribute"></a>TypeConverterAttribute  
 **Referenzdokumentation:**  <xref:System.ComponentModel.TypeConverterAttribute>  
  
 **Gilt für:** -Klasse, Eigenschaft, Methode (nur XAML-gültige Methode ist ein `get` Accessor, der einer anfügbaren Members unterstützt).  
  
 **Argumente:** der <xref:System.Type> von der <xref:System.ComponentModel.TypeConverter>.  
  
 <xref:System.ComponentModel.TypeConverterAttribute> in einer XAML-Kontext verweist auf ein benutzerdefiniertes <xref:System.ComponentModel.TypeConverter>. Dies <xref:System.ComponentModel.TypeConverter> Typkonvertierungsverhalten für benutzerdefinierte Typen oder Member dieses Typs enthält.  
  
 Sie wenden die <xref:System.ComponentModel.TypeConverterAttribute> -Attribut auf den Typ, verweisen auf Ihre Typkonverter-Implementierung. Sie können den Einsatz von Typkonvertern für XAML für Klassen, Strukturen oder Schnittstellen definieren. Sie müssen keine typkonvertierung für Enumerationen, geben Sie die Konvertierung systemintern aktiviert ist.  
  
 Der Typkonverter muss aus einer Zeichenfolge zu konvertieren, die in der gewünschten Zieltyp für Attribute oder Initialisierungstext im Markup verwendet wird. Weitere Informationen finden Sie unter [TypeConverters und Verwendung von XAML-](../../../docs/framework/wpf/advanced/typeconverters-and-xaml.md).  
  
 Anstatt auf alle Werte eines Typs anwenden, kann ein Verhalten für die Verwendung von XAML-Typkonverters auch auf eine bestimmte Eigenschaft eingerichtet werden. In diesem Fall wenden Sie <xref:System.ComponentModel.TypeConverterAttribute> auf die Eigenschaftsdefinition (die äußere Definition, nicht die spezifischen `get` und `set` Definitionen).  
  
 Ein Typ-Konverter-Verhalten für die Verwendung von XAML-Verwendung eines benutzerdefinierten anfügbaren Members kann zugewiesen werden, durch Anwenden von <xref:System.ComponentModel.TypeConverterAttribute> auf die `get` Accessor für die Methode, die die Verwendung von XAML-Verwendung unterstützt.  
  
 Ähnlich wie <xref:System.ComponentModel.TypeConverter>, <xref:System.ComponentModel.TypeConverterAttribute> Waren in .NET Framework vor das Vorhandensein von XAML und die Typ-Konverter Modell diente anderen Zwecken. Um verweisen und Verwendung <xref:System.ComponentModel.TypeConverterAttribute>, müssen Sie vollständig qualifizieren Sie ihn oder Bereitstellen einer `using` -Anweisung für <xref:System.ComponentModel>. Sie müssen auch die Systemassembly in Ihrem Projekt einschließen.  
  
### <a name="uidpropertyattribute"></a>UidPropertyAttribute  
 **Referenzdokumentation:**  <xref:System.Windows.Markup.UidPropertyAttribute>  
  
 **Gilt für:** Klasse  
  
 **Argumente:** eine Zeichenfolge, die die relevante Eigenschaft mit Ihrem Namen verweist.  
  
 Gibt an, der CLR-Eigenschaft einer Klasse, Aliase der [X: Uid-Direktive](../../../docs/framework/xaml-services/x-uid-directive.md).  
  
### <a name="usableduringinitializationattribute"></a>UsableDuringInitializationAttribute  
 **Referenzdokumentation:**  <xref:System.Windows.Markup.UsableDuringInitializationAttribute>  
  
 **Gilt für:** Klasse  
  
 **Argumente:** ein boolescher Wert. Wenn für den beabsichtigten Zweck des Attributs verwendet wird, dies sollte immer angegeben werden als `true`.  
  
 Gibt an, ob dieser Typ beim Erstellen des XAML-Objektdiagramms von oben nach unten (Top-Down) erstellt wird. Dies ist ein erweiterter Ansatz, die die Definition des Programmiermodells wahrscheinlich eng miteinander verbunden ist. Weitere Informationen finden Sie unter <xref:System.Windows.Markup.UsableDuringInitializationAttribute>.  
  
### <a name="valueserializerattribute"></a>ValueSerializerAttribute  
 **Referenzdokumentation:**  <xref:System.Windows.Markup.ValueSerializerAttribute>  
  
 **Gilt für:** -Klasse, Eigenschaft, Methode (nur XAML-gültige Methode ist ein `get` Accessor, der einer anfügbaren Members unterstützt).  
  
 **Argumente:** ein <xref:System.Type> , die Unterstützungsklasse für Wert Serialisierungsprogramm zu verwenden, wenn alle Eigenschaften des attributierten Typs serialisieren angibt, oder die spezifische attributierte Eigenschaft.  
  
 <xref:System.Windows.Markup.ValueSerializer> Gibt an, eine Wertklasse für die Serialisierung, die mehr Status und Kontext als erfordert eine <xref:System.ComponentModel.TypeConverter> verfügt. <xref:System.Windows.Markup.ValueSerializer> durch Anwenden einer anfügbaren Members zugeordnet werden kann die <xref:System.Windows.Markup.ValueSerializerAttribute> -Attribut auf die statische `get` Accessor-Methode für die anfügbaren Members. Wertserialisierung gilt auch für Enumerationen, Schnittstellen und Strukturen, aber nicht für Delegaten.  
  
### <a name="whitespacesignificantcollectionattribute"></a>WhitespaceSignificantCollectionAttribute  
 **Referenzdokumentation:**  <xref:System.Windows.Markup.WhitespaceSignificantCollectionAttribute>  
  
 **Gilt für:** -Klasse, insbesondere Auflistungstypen, der zum Hosten von gemischten Inhalts, in dem Leerraum um Objektelemente für die Benutzeroberflächendarstellung wichtig sein könnte erwartet werden.  
  
 **Argumente:** None.  
  
 <xref:System.Windows.Markup.WhitespaceSignificantCollectionAttribute> Gibt an, ein Sammlungstyp als signifikante Leerräume von einem XAML-Prozessor verarbeitet werden sollte die beeinflusst, die zur Erstellung von der Verwendung von XAML-Knotenstream Wertknoten innerhalb der Auflistung. Weitere Informationen finden Sie unter [Leerstellenverarbeitung in XAML](../../../docs/framework/xaml-services/whitespace-processing-in-xaml.md).  
  
### <a name="xamldeferloadattribute"></a>XamlDeferLoadAttribute  
 **Referenzdokumentation:**  <xref:System.Windows.Markup.XamlDeferLoadAttribute>  
  
 **Gilt für:** -Eigenschaft-Klasse.  
  
 **Argumente:** unterstützt zwei Zuordnungstypen als Zeichenfolgen oder als Typen <xref:System.Type>. Siehe <xref:System.Windows.Markup.XamlDeferLoadAttribute>.  
  
 Gibt an, dass eine Klasse oder die Eigenschaft eine Verwendung des verzögerten Laden für XAML (z. B. ein Vorlagenverhalten weist), und meldet die Klasse, die das verzögern Verhalten und die Ziel-/Inhaltstyp ermöglicht.  
  
### <a name="xamlsetmarkupextensionattribute"></a>XamlSetMarkupExtensionAttribute  
 **Referenzdokumentation:**  <xref:System.Windows.Markup.XamlSetMarkupExtensionAttribute>  
  
 **Gilt für:** Klasse  
  
 **Argumente:** benennt den Rückruf.  
  
 Gibt an, dass eine Klasse eine Markuperweiterung einen Wert für eine oder mehrere Eigenschaften angeben können, und verweist auf ein Handler, den ein XAML-Writer aufrufen sollte, bevor Sie ein Markup-Erweiterung Set-Operation für eine Eigenschaft der Klasse.  
  
### <a name="xamlsettypeconverterattribute"></a>XamlSetTypeConverterAttribute  
 **Referenzdokumentation:**  <xref:System.Windows.Markup.XamlSetTypeConverterAttribute>  
  
 **Gilt für:** Klasse  
  
 **Argumente:** benennt den Rückruf.  
  
 Gibt an, dass eine Klasse einen Typkonverter für eine oder mehrere Eigenschaften einen Wert angeben können, und verweist auf ein Handler, den ein XAML-Writer aufrufen sollte, bevor Sie einen Typkonverter Set-Operation für eine Eigenschaft der Klasse.  
  
### <a name="xmllangpropertyattribute"></a>XmlLangPropertyAttribute  
 **Referenzdokumentation:**  <xref:System.Windows.Markup.XmlLangPropertyAttribute>  
  
 **Gilt für:** Klasse  
  
 **Argumente:** eine Zeichenfolge mit dem Namen der Eigenschaft, um Alias `xml:lang` des Attributtyps.  
  
 <xref:System.Windows.Markup.XmlLangPropertyAttribute> Gibt eine Eigenschaft des Attributtyps, der den XML-Code zugeordnet `lang` Richtlinie. Die Eigenschaft ist der Typ nicht unbedingt <xref:System.String>, jedoch muss aus einer Zeichenfolge (Dies kann erreicht werden durch einen Typkonverter zuordnen, den Typ der Eigenschaft oder mit spezifischen-Eigenschaft) zugewiesen werden können. Die Eigenschaft muss Lese-/Schreibzugriff sein.  
  
 Das Szenario für die Zuordnung `xml:lang` ist, damit eine Laufzeitobjektmodell Zugriff auf die angegebene XML-Code Sprachinformationen ohne speziell mit einem XMLDOM verarbeiten kann.  
  
 Die Definition erbt an alle abgeleiteten Typen, die zu definierenden Typ zugewiesen werden. Sie können die Definition für einen bestimmten abgeleiteten Typ außer Kraft setzen, durch Anwenden von <xref:System.Windows.Markup.XmlLangPropertyAttribute> auf den bestimmten abgeleiteten Typ, obwohl dies ein ungewöhnliches Szenario ist.  
  
## <a name="xaml-related-clr-attributes-at-the-assembly-level"></a>XAML-bezogene CLR-Attributen auf Assemblyebene  
 In den folgenden Abschnitten wird beschrieben, die XAML-bezogene Attribute, die nicht auf Typen oder Memberdefinitionen angewendet werden, sondern werden stattdessen auf Assemblys angewendet. Diese Attribute gelten die Gesamtziel der Definition einer Bibliothek, die benutzerdefinierte Typen zu XAML-Datei enthält. Einige der Attribute beeinflussen nicht notwendigerweise den XAML-Knotenstream direkt, sondern werden im Knotenstream für andere Consumer übergeben. Consumer für das die Informationen umfassen entwurfsumgebungen oder Serialisierungsprozesse, die XAML-Namespaceinformationen benötigen und die zugehörigen Präfixinformationen. Ein XAML-Schemakontext (einschließlich des .NET Framework-XAML-Dienste) auch anhand dieser Informationen.  
  
### <a name="xmlnscompatiblewithattribute"></a>XmlnsCompatibleWithAttribute  
 **Referenzdokumentation:**  <xref:System.Windows.Markup.XmlnsCompatibleWithAttribute>  
  
 **Argumente:**  
  
-   Eine Zeichenfolge, die den Bezeichner des XAML-Namespace zur Klassifizierung angibt.  
  
-   Eine Zeichenfolge, die den Bezeichner des XAML-Namespace angibt, die die Verwendung von XAML-Namespace des vorherigen Arguments klassifizieren kann.  
  
 <xref:System.Windows.Markup.XmlnsCompatibleWithAttribute> Gibt an, dass ein XAML-Namespace durch einen anderen XAML-Namespace eingeordnet werden kann. Der zusammenfassende XAML-Namespace wird angegeben, in der Regel in einem zuvor definierten <xref:System.Windows.Markup.XmlnsDefinitionAttribute>. Diese Technik kann für die versionsverwaltung verwendet, ein XAML-Vokabular in einer Bibliothek und mit den zuvor definierten Markup für das zuvor mit versionsverwaltung durch das Vokabular kompatibel zu machen.  
  
### <a name="xmlnsdefinitionattribute"></a>XmlnsDefinitionAttribute  
 **Referenzdokumentation:**  <xref:System.Windows.Markup.XmlnsDefinitionAttribute>  
  
 **Argumente:**  
  
-   Eine Zeichenfolge, die den Bezeichner des XAML-Namespace definieren angibt.  
  
-   Eine Zeichenfolge, die Namen von einem CLR-Namespace. CLR-Namespace sollten öffentliche Typen definieren, in der Assembly, und mindestens eine der Namespace-CLR-Typen sollten werden für die Verwendung von XAML.  
  
 <xref:System.Windows.Markup.XmlnsDefinitionAttribute> Gibt eine Zuordnung auf der Basis eines pro Assembly zwischen einem XAML-Namespace und einem CLR-Namespace, die dann von einem XAML-Objektwriter oder XAML-Schemakontext für die typauflösung verwendet wird.  
  
 Mehrere <xref:System.Windows.Markup.XmlnsDefinitionAttribute> kann auf eine Assembly angewendet werden. Dies kann für eine beliebige Kombination aus folgenden Gründen erfolgen:  
  
-   Der Bibliotheksentwurf enthält mehrere CLR-Namespaces für die logische Organisation der Laufzeit-API-Zugriff. Möchten Sie jedoch alle Typen in diesen Namespaces als XAML-verwendbar durch Verweisen auf den gleichen XAML-Namespace an. In diesem Fall wenden Sie mehrere <xref:System.Windows.Markup.XmlnsDefinitionAttribute> Attribute unter Verwendung des gleichen <xref:System.Windows.Markup.XmlnsDefinitionAttribute.XmlNamespace%2A> -Wert aber unterschiedliche <xref:System.Windows.Markup.XmlnsDefinitionAttribute.ClrNamespace%2A> Werte. Dies ist besonders hilfreich, wenn Sie Zuordnungen für die Verwendung von XAML-Namespace definieren, die dem Framework oder der Anwendung in die allgemeine Verwendung der standardmäßigen XAML-Namespace werden möchte.  
  
-   Der Bibliotheksentwurf enthält mehrere CLR-Namespaces und eine absichtliche Verwendung von XAML-Namespacetrennung zwischen der Verwendung von Typen in diesen CLR-Namespaces werden sollen.  
  
-   Definieren Sie einen CLR-Namespace in der Assembly, und Sie über mehr als eine XAML-Namespace zugegriffen werden soll. Dieses Szenario tritt auf, wenn Sie mehrere Vokabulare mit derselben Codebasis unterstützen möchten.  
  
-   XAML-sprachunterstützung definiert in einen oder mehrere CLR-Namespaces. Für diese die <xref:System.Windows.Markup.XmlnsDefinitionAttribute.XmlNamespace%2A> Wert sollte `http://schemas.microsoft.com/winfx/2006/xaml`.  
  
### <a name="xmlnsprefixattribute"></a>XmlnsPrefixAttribute  
 **Referenzdokumentation:**  <xref:System.Windows.Markup.XmlnsPrefixAttribute>  
  
 **Argumente:**  
  
-   Eine Zeichenfolge, die den Bezeichner eines XAML-Namespace angibt.  
  
-   Eine Zeichenfolge, die ein empfohlenes Präfix angibt.  
  
 <xref:System.Windows.Markup.XmlnsDefinitionAttribute> Gibt ein empfohlenes Präfix für einen XAML-Namespace verwendet. Das Präfix ist nützlich, wenn Elemente und Attribute in einer XAML-Datei zu schreiben, die durch die .NET Framework XAML Services serialisiert wird <xref:System.Xaml.XamlXmlWriter>, oder wenn eine Bibliothek von XAML-Implementierung mit einer entwurfsumgebung interagiert, die XAML-Bearbeitungsfunktionen.  
  
 Mehrere <xref:System.Windows.Markup.XmlnsPrefixAttribute> kann auf eine Assembly angewendet werden. Dies kann für eine beliebige Kombination aus folgenden Gründen erfolgen:  
  
-   Die Assembly definiert Typen für mehr als eine XAML-Namespace. In diesem Fall sollten Sie verschiedene Präfixwerte für jede Verwendung von XAML-Namespace definieren.  
  
-   Sie können mehrere Vokabulare werden unterstützt, und Sie verwenden unterschiedliche Präfixe für jedes Vokabular und die Verwendung von XAML-Namespace.  
  
-   Definieren von XAML-sprachunterstützung in der Assembly und haben eine <xref:System.Windows.Markup.XmlnsDefinitionAttribute> für `http://schemas.microsoft.com/winfx/2006/xaml`. In diesem Fall Sie in der Regel sollte höher stufen, das Präfix `x`.  
  
> [!NOTE]
>  .NET Framework XAML Services definiert auch das XAML-bezogene Attribut <xref:System.Windows.Markup.RootNamespaceAttribute>. Dieses Attribut ist ein Attribut auf Assemblyebene projektsystemunterstützung, und es ist nicht für die Verwendung von XAML-benutzerdefinierte Typen relevant.  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Attribute>  
 [Definieren von benutzerdefinierten Typen für die Verwendung mit .NET Framework-XAML-Diensten](../../../docs/framework/xaml-services/defining-custom-types-for-use-with-net-framework-xaml-services.md)
