---
title: XAML-bezogene CLR-Attribute für benutzerdefinierte Typen und Bibliotheken
ms.date: 03/30/2017
helpviewer_keywords:
- CLR attributes for custom types [XAML Services]
ms.assetid: 5dfb299a-b6e2-41b8-8694-e6ac987547f1
ms.openlocfilehash: 13cc4d85a1a4b5c9b1ff61afbf7980a54e3d22d0
ms.sourcegitcommit: fb78d8abbdb87144a3872cf154930157090dd933
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/28/2018
ms.locfileid: "47424440"
---
# <a name="xaml-related-clr-attributes-for-custom-types-and-libraries"></a>XAML-bezogene CLR-Attribute für benutzerdefinierte Typen und Bibliotheken
Dieses Thema beschreibt die allgemeinen Language Runtime (CLR)-Attribute, die von .NET Framework-XAML-Dienste definiert werden. Außerdem werden andere CLR-Attribute, die in .NET Framework definiert sind, die ein XAML-bezogene-Szenario für die Anwendung auf die Assemblys oder Typen beschrieben. Assemblys, Typen oder Mitglieder mit diesen Attributen CLR Attributierung stellt XAML-Typsysteminformationen in Bezug auf Ihre Typen bereit. Informationen werden für alle XAML-Consumer bereitgestellt, die .NET Framework-XAML-Dienste für die Verarbeitung von des XAML-Knotenstreams direkt oder über die dedizierte XAML-Reader und XAML-Writer verwendet.  
  
## <a name="xaml-related-clr-attributes-for-custom-types-and-custom-members"></a>XAML-bezogene CLR-Attribute für benutzerdefinierte Typen und benutzerdefinierte Elemente  
 Verwenden von CLR-Attributen zur Folge, dass Sie sind die allgemeine CLR verwenden, um Ihre Typen definieren, die diese Attribute sind andernfalls nicht verfügbar. Wenn Sie die CLR verwenden, um typunterstützung zu definieren, kann der Standard-XAML-Schemakontext, die von .NET Framework XAML Services XAML-Writer verwendet dann CLR-Zuordnung über Reflektion für die unterstützenden Assemblys gelesen.  
  
 Den folgenden Abschnitten werden die vom XAML-bezogene Attribute, die Sie auf benutzerdefinierte Typen oder Member anwenden können. Jedes Attribut CLR kommuniziert Informationen, die für ein XAML-Typsystem relevant sind. Im Ladepfad mit den attributierte Informationen kann entweder des XAML-Readers einen gültigen XAML-Knotenstream zu bilden, oder dadurch, dass des XAML-Writers, der ein gültiges Objektdiagramm erstellt. Klicken Sie im Pfad, der die attributierte Informationen entweder unterstützt den XAML-Reader einen gültigen XAML-Knotenstream zu bilden, für die XAML-Typsysteminformationen; stellt wieder her oder serialisierungshinweise oder Anforderungen für den XAML-Writer oder anderen XAML-Consumern deklariert.  
  
### <a name="ambientattribute"></a>AmbientAttribute  
 **Referenzdokumentation:**  <xref:System.Windows.Markup.AmbientAttribute>  
  
 **Gilt für:** -Klasse, Eigenschaft oder `get` -Member, die anfügbare Eigenschaften unterstützen.  
  
 **Argumente:** keine  
  
 <xref:System.Windows.Markup.AmbientAttribute> Gibt an, dass die Eigenschaft oder alle Eigenschaften, die der attributierten Typ, in das Konzept der ambient-Eigenschaft in XAML interpretiert werden soll. Das Umgebungskonzept bezieht sich darauf, wie XAML-Prozessoren Typbesitzer von Membern bestimmen. Eine Ambiente-Eigenschaft ist eine Eigenschaft, in denen der Wert muss in der Parserkontext verfügbar sein, beim Erstellen eines Objektdiagramms, aber bei der Suche nach typischen Typ-Membern angehalten wird, für den unmittelbaren XAML-Knoten festgelegt, wird erstellt.  
  
 Das Umgebungskonzept auf anfügbare Member, die nicht dargestellt werden, als Eigenschaften in Bezug auf die definiert, wie CLR-Attribut angewendet werden kann <xref:System.AttributeTargets>. Die Verwendung der Methode sind nur im Fall von angewendet werden soll eine `get` Accessor, der anfügbare Verwendung für XAML unterstützt.  
  
### <a name="constructorargumentattribute"></a>ConstructorArgumentAttribute  
 **Referenzdokumentation:**  <xref:System.Windows.Markup.ConstructorArgumentAttribute>  
  
 **Gilt für:** Klasse  
  
 **Argumente:** eine Zeichenfolge, die den Namen der Eigenschaft gibt an, die eine einzelne Konstruktorargument entspricht.  
  
 <xref:System.Windows.Markup.ConstructorArgumentAttribute> Gibt an, dass ein Objekt mit einer nicht standardmäßigen Konstruktorsyntax initialisiert werden kann und eine Eigenschaft mit dem angegebenen Namen Informationen zur Erstellung bereitstellt. Diese Informationen sind in erster Linie für die XAML-Serialisierung vorgesehen. Weitere Informationen finden Sie unter <xref:System.Windows.Markup.ConstructorArgumentAttribute>.  
  
### <a name="contentpropertyattribute"></a>ContentPropertyAttribute  
 **Referenzdokumentation:**  <xref:System.Windows.Markup.ContentPropertyAttribute>  
  
 **Gilt für:** Klasse  
  
 **Argumente:** eine Zeichenfolge, die den Namen eines Members des attributierten Typs angibt.  
  
 <xref:System.Windows.Markup.ContentPropertyAttribute> Gibt an, dass die Eigenschaft als durch das Argument mit dem Namen als die XAML-Inhaltseigenschaft für diesen Typ bereitstellen soll. Die Definition der XAML-Inhaltseigenschaft erbt für alle abgeleiteten Typen, die zu definierenden Typs zugewiesen werden können. Sie können die Definition für einen bestimmten abgeleiteten Typ durch Anwenden von überschreiben <xref:System.Windows.Markup.ContentPropertyAttribute> auf den bestimmten abgeleiteten Typ.  
  
 Property-Element-Tags für die Eigenschaft kann in der XAML-Verwendung ausgelassen werden, für die Eigenschaft, die als die XAML-Inhaltseigenschaft dient. In der Regel legen Sie die XAML-Inhaltseigenschaften, die eine optimierte XAML-Markup für Ihre Inhalte und Kapselung Modelle zu unterstützen. Da nur ein Element als die XAML-Inhaltseigenschaft festgelegt werden kann, müssen Sie manchmal Entwurf Entscheidungen treffen müssen, im Hinblick auf die mehrere Container wie die XAML-Inhaltseigenschaft Eigenschaften eines Typs festgelegt werden. Die anderen Containereigenschaften müssen mit expliziten Eigenschaftenelemente verwendet werden.  
  
 In den XAML-Knotenstream, XAML-Inhaltseigenschaften weiterhin erzeugen `StartMember` und `EndMember` Knoten, die mit dem Namen der Eigenschaft für die <xref:System.Xaml.XamlMember>. Um zu bestimmen, ob ein Element die XAML-Inhaltseigenschaft ist, überprüfen die <xref:System.Xaml.XamlType> Wert aus der `StartObject` positionieren und Abrufen des Werts <xref:System.Xaml.XamlType.ContentProperty%2A>.  
  
### <a name="contentwrapperattribute"></a>ContentWrapperAttribute  
 **Referenzdokumentation:**  <xref:System.Windows.Markup.ContentWrapperAttribute>  
  
 **Gilt für:** -Klasse, insbesondere Auflistungstypen.  
  
 **Argumente:** ein <xref:System.Type> , der den Typ als Typ Inhaltswrapper für fremden Inhalt angibt.  
  
 <xref:System.Windows.Markup.ContentWrapperAttribute> Gibt einen oder mehrere Typen in den zugeordneten Auflistungstyps, der verwendet wird, fremden Inhalt zu umschließen. Fremden Inhalt bezieht sich auf Fälle, in denen die systemeinschränkungen für den Typ der Content-Eigenschaft nicht alle möglichen Fälle Content erfasst werden, die XAML-Verwendung für den besitzenden Typ unterstützen würde. Beispielsweise XAML unterstützt, für die Inhalte eines bestimmten Typs Zeichenfolgen in eine stark typisierte generische unterstützen möglicherweise <xref:System.Collections.ObjectModel.Collection%601>. Inhaltswrapper eignen sich zum Migrieren von vorhandenen Markup-Konventionen in XAMLs Konzeption der zugewiesen werden Werte für Auflistungen, z. B. Migrieren von textbezogenen Inhaltsmodelle.  
  
 Um mehr als eine Inhaltswrapper-Typ anzugeben, wenden Sie das Attribut mehrmals.  
  
### <a name="dependsonattribute"></a>DependsOnAttribute  
 **Referenzdokumentation:**  <xref:System.Windows.Markup.DependsOnAttribute>  
  
 **Gilt für:** Eigenschaft  
  
 **Argumente:** eine Zeichenfolge, die den Namen eines anderen Elements des attributierten Typs angibt.  
  
 <xref:System.Windows.Markup.DependsOnAttribute> Gibt an, dass die attributierte Eigenschaft den Wert einer anderen Eigenschaft abhängig ist. Das Anwenden dieses Attributs auf eine Eigenschaftsdefinition wird sichergestellt, dass die abhängigen Eigenschaften in XAML-Objekt das Schreiben von zuerst verarbeitet werden. Verwendung von <xref:System.Windows.Markup.DependsOnAttribute> Geben Sie die Ausnahmefälle der Eigenschaften, die auf Typen, in dem eine bestimmte Reihenfolge der Analyse zum Erstellen eines gültigen Objekts gefolgt sein muss.  
  
 Sie können mehrere anwenden <xref:System.Windows.Markup.DependsOnAttribute> Fällen auf eine Eigenschaftsdefinition.  
  
### <a name="markupextensionreturntypeattribute"></a>MarkupExtensionReturnTypeAttribute  
 **Referenzdokumentation:**  <xref:System.Windows.Markup.MarkupExtensionReturnTypeAttribute>  
  
 **Gilt für:** -Klasse, die voraussichtlich eine <xref:System.Windows.Markup.MarkupExtension> abgeleiteten Typ.  
  
 **Argumente:** ein <xref:System.Type> , die am besten passendste den Typ als erwarten angibt der `ProvideValue` Ergebnis die attributierte <xref:System.Windows.Markup.MarkupExtension>.  
  
 Weitere Informationen finden Sie unter [Markup Extensions for XAML Overview](../../../docs/framework/xaml-services/markup-extensions-for-xaml-overview.md).  
  
### <a name="namescopepropertyattribute"></a>NameScopePropertyAttribute  
 **Referenzdokumentation:**  <xref:System.Windows.Markup.NameScopePropertyAttribute>  
  
 **Gilt für:** Klasse  
  
 **Argumente:** unterstützt zwei Arten von sind:  
  
-   Eine Zeichenfolge, die den Namen einer Eigenschaft des Attributtyps angibt.  
  
-   Eine Zeichenfolge, die den Namen einer Eigenschaft angibt und einen <xref:System.Type> für den Typ, der die benannte Eigenschaft definiert. Dieses Formular wird einen anfügbaren Member als XAML-Namescope-Eigenschaft angegeben.  
  
 <xref:System.Windows.Markup.NameScopePropertyAttribute> Gibt eine Eigenschaft, die den XAML-Namescope-Wert für die attributierte Klasse bereitstellt. Die XAML-Namescope-Eigenschaft muss auf ein Objekt zu verweisen, die implementiert <xref:System.Windows.Markup.INameScope> und enthält den tatsächlichen XAML-Namescope, Speicher und das Verhalten.  
  
### <a name="runtimenamepropertyattribute"></a>RuntimeNamePropertyAttribute  
 **Referenzdokumentation:**  <xref:System.Windows.Markup.RuntimeNamePropertyAttribute>  
  
 **Gilt für:** Klasse  
  
 **Argumente:** eine Zeichenfolge, die den Namen der Laufzeit-Name-Eigenschaft des Attributtyps angibt.  
  
 <xref:System.Windows.Markup.RuntimeNamePropertyAttribute> Gibt eine Eigenschaft des Attributtyps, der die XAML zugeordnet [X: Name Directive](../../../docs/framework/xaml-services/x-name-directive.md). Die Eigenschaft muss vom Typ <xref:System.String> muss Lese-/Schreibzugriff.  
  
 Die Definition erbt für alle abgeleiteten Typen, die zu definierenden Typs zugewiesen werden können. Sie können die Definition für einen bestimmten abgeleiteten Typ durch Anwenden von überschreiben <xref:System.Windows.Markup.RuntimeNamePropertyAttribute> auf den bestimmten abgeleiteten Typ.  
  
### <a name="trimsurroundingwhitespaceattribute"></a>TrimSurroundingWhitespaceAttribute  
 **Referenzdokumentation:**  <xref:System.Windows.Markup.TrimSurroundingWhitespaceAttribute>  
  
 **Gilt für:** Typen  
  
 **Argumente:** None.  
  
 <xref:System.Windows.Markup.TrimSurroundingWhitespaceAttribute> gilt für bestimmte Typen, die als untergeordnete Elemente in erheblichen Leerzeichen-Inhalt angezeigt werden können (Inhalte frei, die eine Sammlung mit <xref:System.Windows.Markup.WhitespaceSignificantCollectionAttribute>). <xref:System.Windows.Markup.TrimSurroundingWhitespaceAttribute> ist vor allem relevant, für den Pfad, jedoch finden Sie im XAML-Typsystem im Ladepfad anhand <xref:System.Xaml.XamlType.TrimSurroundingWhitespace%2A?displayProperty=nameWithType>. Weitere Informationen finden Sie unter [White-Space-Verarbeitung in XAML](../../../docs/framework/xaml-services/whitespace-processing-in-xaml.md).  
  
### <a name="typeconverterattribute"></a>TypeConverterAttribute  
 **Referenzdokumentation:**  <xref:System.ComponentModel.TypeConverterAttribute>  
  
 **Gilt für:** -Klasse, Eigenschaft, Methode (das einzige gültige XAML Methode ist eine `get` Accessor, der einen anfügbaren Member unterstützt).  
  
 **Argumente:** der <xref:System.Type> von der <xref:System.ComponentModel.TypeConverter>.  
  
 <xref:System.ComponentModel.TypeConverterAttribute> in einer XAML Kontext verweist auf eine benutzerdefinierte <xref:System.ComponentModel.TypeConverter>. Dies <xref:System.ComponentModel.TypeConverter> Typkonvertierungsverhalten für benutzerdefinierte Typen oder Member dieses Typs bereitstellt.  
  
 Sie wenden die <xref:System.ComponentModel.TypeConverterAttribute> Attribut in den Typ, verweisen auf Ihre Typkonverter-Implementierung. Sie können den Typkonverter für XAML auf Klassen, Strukturen oder Schnittstellen definieren. Sie müssen keine typkonvertierung für Enumerationen, geben Sie die Konvertierung systemintern aktiviert ist.  
  
 Der Typkonverter muss aus einer Zeichenfolge zu konvertieren, die in Ihrem beabsichtigten Zieltyp für Attribute oder Initialisierungstext im Markup verwendet wird. Weitere Informationen finden Sie unter [TypeConverter und XAML](../../../docs/framework/wpf/advanced/typeconverters-and-xaml.md).  
  
 Anstatt auf alle Werte eines Typs anwenden, kann ein Typkonverterverhalten für XAML auch auf eine bestimmte Eigenschaft eingerichtet werden. In diesem Fall auf die Sie anwenden <xref:System.ComponentModel.TypeConverterAttribute> auf die Eigenschaftsdefinition (die äußere Definition, nicht die spezifischen `get` und `set` Definitionen).  
  
 Ein Typkonverterverhalten für XAML-Verwendung eines benutzerdefinierten anfügbaren Members kann zugewiesen werden, durch Anwenden von <xref:System.ComponentModel.TypeConverterAttribute> auf die `get` Accessor für die Methode, die die Verwendung von XAML unterstützt.  
  
 Ähnlich wie <xref:System.ComponentModel.TypeConverter>, <xref:System.ComponentModel.TypeConverterAttribute> war in .NET Framework vor das Vorhandensein von XAML und der Typ-Konverter-Modell verarbeitet, andere Zwecke. Um verweisen und <xref:System.ComponentModel.TypeConverterAttribute>, Sie müssen vollständig qualifizieren Sie ihn, oder geben Sie einen `using` -Anweisung für <xref:System.ComponentModel>. Sie müssen auch die Systemassembly in Ihrem Projekt einschließen.  
  
### <a name="uidpropertyattribute"></a>UidPropertyAttribute  
 **Referenzdokumentation:**  <xref:System.Windows.Markup.UidPropertyAttribute>  
  
 **Gilt für:** Klasse  
  
 **Argumente:** eine Zeichenfolge, die relevante Eigenschaft nach Namen verweist.  
  
 Gibt an, Aliase, der CLR-Eigenschaft einer Klasse die [X: Uid Directive](../../../docs/framework/xaml-services/x-uid-directive.md).  
  
### <a name="usableduringinitializationattribute"></a>UsableDuringInitializationAttribute  
 **Referenzdokumentation:**  <xref:System.Windows.Markup.UsableDuringInitializationAttribute>  
  
 **Gilt für:** Klasse  
  
 **Argumente:** ein boolescher Wert. Wenn für den beabsichtigten Zweck des Attributs verwendet wird, es muss immer angegeben werden als `true`.  
  
 Gibt an, ob dieser Typ beim Erstellen des XAML-Objektdiagramms von oben nach unten (Top-Down) erstellt wird. Dies ist ein erweitertes Konzept, bei der Definition des Programmiermodells wahrscheinlich eng verknüpft ist. Weitere Informationen finden Sie unter <xref:System.Windows.Markup.UsableDuringInitializationAttribute>.  
  
### <a name="valueserializerattribute"></a>ValueSerializerAttribute  
 **Referenzdokumentation:**  <xref:System.Windows.Markup.ValueSerializerAttribute>  
  
 **Gilt für:** -Klasse, Eigenschaft, Methode (das einzige gültige XAML Methode ist eine `get` Accessor, der einen anfügbaren Member unterstützt).  
  
 **Argumente:** ein <xref:System.Type> , die Unterstützungsklasse für Wert Serialisierungsprogramm verwenden, bei der Serialisierung alle Eigenschaften des attributierten Typs angibt oder die spezifischen attributierte Eigenschaft.  
  
 <xref:System.Windows.Markup.ValueSerializer> Gibt an, eine Wertklasse für die Serialisierung, die mehrere Status und Kontext als erfordert eine <xref:System.ComponentModel.TypeConverter> ist. <xref:System.Windows.Markup.ValueSerializer> kann ein anfügbarer Member zugeordnet werden, durch Anwenden der <xref:System.Windows.Markup.ValueSerializerAttribute> Attribut für die statische `get` Accessor-Methode für den abzurufenden anfügbaren Members. Wertserialisierung gilt auch für Enumerationen, Schnittstellen und Strukturen, jedoch nicht für Delegaten.  
  
### <a name="whitespacesignificantcollectionattribute"></a>WhitespaceSignificantCollectionAttribute  
 **Referenzdokumentation:**  <xref:System.Windows.Markup.WhitespaceSignificantCollectionAttribute>  
  
 **Gilt für:** -Klasse, insbesondere Auflistungstypen, die zum Hosten von gemischten Inhalts, in dem Leerräume um Object-Elemente für die Darstellung der Benutzeroberfläche von großer Bedeutung möglicherweise erwartet werden.  
  
 **Argumente:** None.  
  
 <xref:System.Windows.Markup.WhitespaceSignificantCollectionAttribute> Gibt an, dass vom Auflistungstyp als Leerzeichen erheblich von einem XAML-Prozessor verarbeitet werden sollen die beeinflusst, die zur Erstellung von der XAML-Knotenstream-Wert-Knoten in der Auflistung. Weitere Informationen finden Sie unter [White-Space-Verarbeitung in XAML](../../../docs/framework/xaml-services/whitespace-processing-in-xaml.md).  
  
### <a name="xamldeferloadattribute"></a>XamlDeferLoadAttribute  
 **Referenzdokumentation:**  <xref:System.Windows.Markup.XamlDeferLoadAttribute>  
  
 **Gilt für:** Klasse, Eigenschaft.  
  
 **Argumente:** unterstützt zwei Zuordnungstypen als Zeichenfolgen oder als Typen <xref:System.Type>. Siehe <xref:System.Windows.Markup.XamlDeferLoadAttribute>.  
  
 Gibt an, dass eine Klasse oder Eigenschaft verfügt über eine verzögerte Auslastungsverwendung für XAML (z. B. ein Vorlagenverhalten), und meldet die Klasse, die das verzögernde Verhalten und die Ziel-/Inhaltstyp aktiviert.  
  
### <a name="xamlsetmarkupextensionattribute"></a>XamlSetMarkupExtensionAttribute  
 **Referenzdokumentation:**  <xref:System.Windows.Markup.XamlSetMarkupExtensionAttribute>  
  
 **Gilt für:** Klasse  
  
 **Argumente:** benennt den Rückruf.  
  
 Gibt an, dass eine Klasse einer Markuperweiterung mithilfe kann einen Wert für eine oder mehrere Eigenschaften angeben, und verweist auf einen Handler, den ein XAML-Writer aufgerufen werden soll, vor dem Ausführen einer Markup Extension Set-Vorgang auf einer beliebigen Eigenschaft der Klasse.  
  
### <a name="xamlsettypeconverterattribute"></a>XamlSetTypeConverterAttribute  
 **Referenzdokumentation:**  <xref:System.Windows.Markup.XamlSetTypeConverterAttribute>  
  
 **Gilt für:** Klasse  
  
 **Argumente:** benennt den Rückruf.  
  
 Gibt an, dass eine Klasse eines Typkonverters mithilfe kann einen Wert für eine oder mehrere Eigenschaften angeben, und verweist auf einen Handler, den ein XAML-Writer aufgerufen werden soll, vor dem Ausführen von eines Typ-Konverter-Set-Vorgangs auf einer beliebigen Eigenschaft der Klasse.  
  
### <a name="xmllangpropertyattribute"></a>XmlLangPropertyAttribute  
 **Referenzdokumentation:**  <xref:System.Windows.Markup.XmlLangPropertyAttribute>  
  
 **Gilt für:** Klasse  
  
 **Argumente:** eine Zeichenfolge, die den Namen des Alias für die Eigenschaft gibt an, `xml:lang` des Attributtyps.  
  
 <xref:System.Windows.Markup.XmlLangPropertyAttribute> Gibt eine Eigenschaft des Attributtyps, der den XML-Code zugeordnet `lang` Richtlinie. Die Eigenschaft ist der Typ nicht unbedingt <xref:System.String>, jedoch muss aus einer Zeichenfolge (Dies kann erreicht werden durch einen Typkonverter zuordnen, den Typ der Eigenschaft oder mit spezifischen-Eigenschaft) zugeordnet werden können. Die Eigenschaft muss über Lese-/Schreibzugriff sein.  
  
 Das Szenario für die Zuordnung `xml:lang` ist, damit ein Laufzeit-Objektmodell den Zugriff auf XML angegebene Language-Informationen verfügt, ohne explizit mit einem XMLDOM verarbeiten.  
  
 Die Definition erbt für alle abgeleiteten Typen, die zu definierenden Typs zugewiesen werden können. Sie können die Definition für einen bestimmten abgeleiteten Typ durch Anwenden von überschreiben <xref:System.Windows.Markup.XmlLangPropertyAttribute> auf die jeweilige abgeleiteten Typ, obwohl dies ein ungewöhnliches Szenario ist.  
  
## <a name="xaml-related-clr-attributes-at-the-assembly-level"></a>XAML-bezogene CLR-Attribute auf Assemblyebene  
 Den folgenden Abschnitten werden die XAML-bezogene Attribute, die gelten nicht für Typen oder Memberdefinitionen, sondern werden stattdessen auf Assemblys angewendet werden. Diese Attribute sind für das Gesamtziel des Definieren einer Bibliothek, die benutzerdefinierte Typen in XAML verwenden enthält, relevant sind. Einige der Attribute beeinflussen nicht notwendigerweise den XAML-Knotenstream direkt, sondern im Knotenstream für andere Consumer zur Verwendung übergeben werden. Kunden, die Informationen umfassen entwurfsumgebungen oder Serialisierungsprozesse, die XAML-Namespaceinformationen und zugehörige Präfixinformationen. Ein XAML-Schemakontext (einschließlich des .NET Framework-XAML-Dienste) auch verwendet diese Informationen.  
  
### <a name="xmlnscompatiblewithattribute"></a>XmlnsCompatibleWithAttribute  
 **Referenzdokumentation:**  <xref:System.Windows.Markup.XmlnsCompatibleWithAttribute>  
  
 **Argumente:**  
  
-   Eine Zeichenfolge, die den Bezeichner des XAML-Namespace zur Klassifizierung angibt.  
  
-   Eine Zeichenfolge, die den Bezeichner des XAML-Namespace angibt, die den XAML-Namespace aus dem vorherigen Argument klassifizieren kann.  
  
 <xref:System.Windows.Markup.XmlnsCompatibleWithAttribute> Gibt an, dass ein XAML-Namespace durch einen anderen XAML-Namespace eingeordnet werden kann. Der zusammenfassende XAML-Namespace wird angegeben, in der Regel in einem zuvor definierten <xref:System.Windows.Markup.XmlnsDefinitionAttribute>. Diese Technik kann sein, ein XAML-Vokabular in einer Bibliothek und mit der zuvor definierten Markup für das zuvor mit versionsverwaltung durch das Vokabular kompatibel zu machen für die versionsverwaltung verwendet.  
  
### <a name="xmlnsdefinitionattribute"></a>XmlnsDefinitionAttribute  
 **Referenzdokumentation:**  <xref:System.Windows.Markup.XmlnsDefinitionAttribute>  
  
 **Argumente:**  
  
-   Eine Zeichenfolge, die den Bezeichner des XAML-Namespace definieren angibt.  
  
-   Eine Zeichenfolge, die Namen von einem CLR-Namespace. Der CLR-Namespace sollten öffentliche Typen definieren, in der Assembly, und mindestens eines der CLR-Namespace-Typen für XAML konzipiert sein sollte.  
  
 <xref:System.Windows.Markup.XmlnsDefinitionAttribute> Gibt eine Zuordnung einer Basis pro Assembly zwischen einem XAML-Namespace und einem CLR-Namespace, die dann von einem XAML-Objektwriter oder XAML-Schemakontext für die typauflösung verwendet wird.  
  
 Mehr als eine <xref:System.Windows.Markup.XmlnsDefinitionAttribute> kann auf eine Assembly angewendet werden. Dies kann für eine beliebige Kombination aus den folgenden Gründen erfolgen:  
  
-   Das Entwerfen von Klassenbibliotheken enthält mehrere CLR-Namespaces für die logische Organisation der Laufzeit-API-Zugriff. Allerdings möchten Sie alle Typen in diesen Namespaces XAML-verwendet werden kann durch Verweisen auf die gleiche XAML-Namespace. In diesem Fall wenden Sie mehrere <xref:System.Windows.Markup.XmlnsDefinitionAttribute> -Attribute mit dem gleichen <xref:System.Windows.Markup.XmlnsDefinitionAttribute.XmlNamespace%2A> -Wert aber unterschiedliche <xref:System.Windows.Markup.XmlnsDefinitionAttribute.ClrNamespace%2A> Werte. Dies ist besonders nützlich, wenn Sie Zuordnungen für den XAML-Namespace, die das Framework oder die Anwendung beabsichtigt definieren, häufige Verwendung der Standard-XAML-Namespace sein.  
  
-   Das Entwerfen von Klassenbibliotheken enthält mehrere CLR-Namespaces und eine absichtliche XAML-Namespace Trennung zwischen der Verwendung von Typen in die CLR-Namespaces werden sollen.  
  
-   Sie definieren einen CLR-Namespace, in der Assembly, und Sie über mehr als eine XAML-Namespace zugegriffen werden soll. Dieses Szenario tritt auf, wenn Sie mehrere Vokabulare, die mit der gleichen Codebasis unterstützen.  
  
-   XAML-sprachunterstützung definiert in einem oder mehreren CLR-Namespaces. Für diese die <xref:System.Windows.Markup.XmlnsDefinitionAttribute.XmlNamespace%2A> Wert sollte `http://schemas.microsoft.com/winfx/2006/xaml`.  
  
### <a name="xmlnsprefixattribute"></a>XmlnsPrefixAttribute  
 **Referenzdokumentation:**  <xref:System.Windows.Markup.XmlnsPrefixAttribute>  
  
 **Argumente:**  
  
-   Eine Zeichenfolge, die den Bezeichner für einen XAML-Namespace angibt.  
  
-   Eine Zeichenfolge, die ein empfohlenes Präfix angibt.  
  
 <xref:System.Windows.Markup.XmlnsDefinitionAttribute> Gibt ein empfohlenes Präfix, für einen XAML-Namespace verwendet. Das Präfix ist nützlich, wenn Elemente und Attribute in einer XAML-Datei zu schreiben, der durch die .NET Framework XAML Services serialisiert wird <xref:System.Xaml.XamlXmlWriter>, oder wenn eine Bibliothek mit XAML-Implementierung mit einer entwurfsumgebung interagiert, die XAML-Bearbeitungsfunktionen.  
  
 Mehr als eine <xref:System.Windows.Markup.XmlnsPrefixAttribute> kann auf eine Assembly angewendet werden. Dies kann für eine beliebige Kombination aus den folgenden Gründen erfolgen:  
  
-   Die Assembly definiert die Typen für mehr als eine XAML-Namespace. In diesem Fall sollten Sie verschiedene Werte für jeden XAML-Namespace definieren.  
  
-   Sie können mehrere Vokabulare werden unterstützt, und Sie unterschiedliche Präfixe für jedes Vokabular und die XAML-Namespace verwenden.  
  
-   Sie definieren Sie XAML-sprachunterstützung in der Assembly und eine <xref:System.Windows.Markup.XmlnsDefinitionAttribute> für `http://schemas.microsoft.com/winfx/2006/xaml`. In diesem Fall Sie in der Regel sollte höher stufen, das Präfix `x`.  
  
> [!NOTE]
>  .NET Framework XAML Services definiert auch die XAML-Attribut <xref:System.Windows.Markup.RootNamespaceAttribute>. Dieses Attribut ist ein Attribut auf Assemblyebene für projektsystemunterstützung, und es ist nicht relevant für XAML-benutzerdefinierte Typen.  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Attribute>  
 [Definieren von benutzerdefinierten Typen für die Verwendung mit .NET Framework-XAML-Diensten](../../../docs/framework/xaml-services/defining-custom-types-for-use-with-net-framework-xaml-services.md)
