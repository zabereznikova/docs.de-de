---
title: XAML-bezogene CLR-Attribute für benutzerdefinierte Typen und Bibliotheken
ms.date: 03/30/2017
helpviewer_keywords:
- CLR attributes for custom types [XAML Services]
ms.assetid: 5dfb299a-b6e2-41b8-8694-e6ac987547f1
ms.openlocfilehash: 5481d02e4d393312fa0f0dd13b45c54acc567e13
ms.sourcegitcommit: c2d9718996402993cf31541f11e95531bc68bad0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/27/2020
ms.locfileid: "81432983"
---
# <a name="xaml-related-clr-attributes-for-custom-types-and-libraries"></a>XAML-bezogene CLR-Attribute für benutzerdefinierte Typen und Bibliotheken

In diesem Thema werden die CLR-Attribute (Common Language Runtime) beschrieben, die von .NET XAML Services definiert werden. Außerdem werden andere CLR-Attribute beschrieben, die in .NET definiert sind und ein XAML-bezogenes Szenario für die Anwendung auf Assemblys oder Typen aufweisen. Das Attributieren von Assemblys, -Typen oder -Membern mit diesen CLR-Attributen stellt Systeminformationen vom XAML-Typ zu Ihren Typen bereit. Informationen werden jedem XAML-Consumer zur Verfügung gestellt, der .NET XAML Services für die Verarbeitung des XAML-Knotenstreams direkt oder über die dedizierten XAML-Reader und XAML-Writer verwendet.

## <a name="xaml-related-clr-attributes-for-custom-types-and-custom-members"></a>XAML-bezogene CLR-Attribute für benutzerdefinierte Typen und benutzerdefinierte Elemente

Die Verwendung von CLR-Attributen bedeutet, dass Sie die gesamte CLR verwenden, um Ihre Typen zu definieren, da andernfalls solche Attribute nicht verfügbar sind. Wenn Sie die CLR zum Definieren der Typsicherung verwenden, kann der standardmäßige XAML-Schemakontext, der von .NET XAML Services XAML-Writern verwendet wird, die CLR-Attribution durch Reflektion für Sicherungsassemblys lesen.

In den folgenden Abschnitten werden die XAML-bezogenen Attribute beschrieben, die Sie auf benutzerdefinierte Typen oder benutzerdefinierte Member anwenden können. Jedes CLR-Attribut übermittelt Informationen, die für ein XAML-Typsystem relevant sind. Im Ladepfad helfen die attributierten Informationen entweder dem XAML-Reader, einen gültigen XAML-Knotenstream zu erstellen, oder es hilft dem XAML-Writer, ein gültiges Objektdiagramm zu erstellen. Im Speicherpfad helfen die attributierten Informationen dem XAML-Reader entweder, einen gültigen XAML-Knotenstream zu erstellen, der Die Systeminformationen vom Typ XAML neu bildet. oder es deklariert Serialisierungshinweise oder Anforderungen für den XAML-Writer oder andere XAML-Verbraucher.

### <a name="ambientattribute"></a>AmbientAttribute

**Referenzdokumentation:**<xref:System.Windows.Markup.AmbientAttribute>

**Gilt für:** Klassen-, Eigenschafts- oder `get` Accessormember, die anfügbisierbare Eigenschaften unterstützen.

**Argumente:** nichts

<xref:System.Windows.Markup.AmbientAttribute>gibt an, dass die Eigenschaft oder alle Eigenschaften, die den attributierten Typ annehmen, unter dem Umgebungseigenschaftskonzept in XAML interpretiert werden sollen. Das Umgebungskonzept bezieht sich darauf, wie XAML-Prozessoren Typbesitzer von Membern bestimmen. Eine ambient-Eigenschaft ist eine Eigenschaft, bei der der Wert voraussichtlich im Parserkontext verfügbar ist, wenn ein Objektdiagramm erstellt wird, wobei jedoch die typische Typelementsuche für den sofort erstellten XAML-Knotensatz angehalten wird.

Das Umgebungskonzept kann auf anfügbare Elemente angewendet werden, die nicht als <xref:System.AttributeTargets>Eigenschaften in Bezug auf die Definition der CLR-Attribution dargestellt werden. Die Methodenattributionsverwendung sollte nur für `get` einen Accessor angewendet werden, der die anfügbare Verwendung für XAML unterstützt.

### <a name="constructorargumentattribute"></a>KonstruktorArgumentAttribute

**Referenzdokumentation:**  <xref:System.Windows.Markup.ConstructorArgumentAttribute>

**Gilt für:** Klasse

**Argumente:** Eine Zeichenfolge, die den Namen der Eigenschaft angibt, die mit einem einzelnen Konstruktorargument übereinstimmt.

<xref:System.Windows.Markup.ConstructorArgumentAttribute>gibt an, dass ein Objekt mithilfe einer nicht parametrfreien Konstruktorsyntax initialisiert werden kann und dass eine Eigenschaft des angegebenen Namens Konstruktionsinformationen bereitstellt. Diese Informationen sind in erster Linie für die XAML-Serialisierung vorgesehen. Weitere Informationen finden Sie unter <xref:System.Windows.Markup.ConstructorArgumentAttribute>.

### <a name="contentpropertyattribute"></a>Contentpropertyattribute

**Referenzdokumentation:**  <xref:System.Windows.Markup.ContentPropertyAttribute>

**Gilt für:** Klasse

**Argumente:** Eine Zeichenfolge, die den Namen eines Members des attributierten Typs angibt.

<xref:System.Windows.Markup.ContentPropertyAttribute>gibt an, dass die Eigenschaft, die durch das Argument benannt wird, als XAML-Inhaltseigenschaft für diesen Typ dienen soll. Die XAML-Inhaltseigenschaftsdefinition erbt alle abgeleiteten Typen, die dem definierenden Typ zugewiesen werden können. Sie können die Definition für einen bestimmten <xref:System.Windows.Markup.ContentPropertyAttribute> abgeleiteten Typ überschreiben, indem Sie den bestimmten abgeleiteten Typ anwenden.

Für die Eigenschaft, die als XAML-Inhaltseigenschaft dient, kann die Eigenschaftenelement-Tagging für die Eigenschaft in der XAML-Nutzung weggelassen werden. In der Regel legen Sie XAML-Inhaltseigenschaften fest, die ein optimiertes XAML-Markup für Ihre Content- und Containment-Modelle heraufstufen. Da nur ein Member als XAML-Inhaltseigenschaft festgelegt werden kann, können Sie manchmal Entwurfsoptionen treffen, welche von mehreren Containereigenschaften eines Typs als XAML-Inhaltseigenschaft festgelegt werden sollen. Die anderen Containereigenschaften müssen mit expliziten Eigenschaftselementen verwendet werden.

Im XAML-Knotenstream erzeugen `StartMember` XAML-Inhaltseigenschaften weiterhin `EndMember` Knoten, indem der <xref:System.Xaml.XamlMember>Name der Eigenschaft für die verwendet wird. Um zu bestimmen, ob ein Member die <xref:System.Xaml.XamlType> XAML-Inhaltseigenschaft ist, untersuchen Sie den Wert aus der `StartObject` Position, und rufen Sie den Wert von ab. <xref:System.Xaml.XamlType.ContentProperty%2A>

### <a name="contentwrapperattribute"></a>Contentwrapperattribute

**Referenzdokumentation:**  <xref:System.Windows.Markup.ContentWrapperAttribute>

**Gilt für:** Klasse, insbesondere Auflistungstypen.

**Argumente:** A, <xref:System.Type> der den Typ angibt, der als Inhaltswrappertyp für fremde Inhalte verwendet werden soll.

<xref:System.Windows.Markup.ContentWrapperAttribute>gibt einen oder mehrere Typen für den zugeordneten Auflistungstyp an, der zum Umschließen von Fremdinhalten verwendet wird. Fremder Inhalt bezieht sich auf Fälle, in denen die Typsystemeinschränkungen für den Typ der Content-Eigenschaft nicht alle möglichen Inhaltsfälle erfassen, die XAML für den besitzenden Typ unterstützen würde. Beispielsweise kann die XAML-Unterstützung für Inhalte eines bestimmten Typs <xref:System.Collections.ObjectModel.Collection%601>Zeichenfolgen in einem stark typisierten generischen unterstützen. Inhaltswrapper sind nützlich, um bereits vorhandene Markupkonventionen in XAMLs Konzeption von zuweisbaren Werten für Auflistungen zu migrieren, z. B. das Migrieren textbezogener Inhaltsmodelle.

Um mehr als einen Inhaltswrappertyp anzugeben, wenden Sie das Attribut mehrmals an.

### <a name="dependsonattribute"></a>DependsonAttribute

**Referenzdokumentation:**  <xref:System.Windows.Markup.DependsOnAttribute>

**Gilt für:** Eigenschaft

**Argumente:** Eine Zeichenfolge, die den Namen eines anderen Members des attributierten Typs angibt.

<xref:System.Windows.Markup.DependsOnAttribute>gibt an, dass die attributierte Eigenschaft vom Wert einer anderen Eigenschaft abhängt. Durch das Anwenden dieses Attributs auf eine Eigenschaftsdefinition wird sichergestellt, dass die abhängigen Eigenschaften zuerst beim Schreiben von XAML-Objekten verarbeitet werden. Verwendungen <xref:System.Windows.Markup.DependsOnAttribute> von geben die Ausnahmefälle von Eigenschaften für Typen an, bei denen eine bestimmte Reihenfolge der Analyse für die gültige Objekterstellung befolgt werden muss.

Sie können <xref:System.Windows.Markup.DependsOnAttribute> mehrere Anfragen auf eine Eigenschaftsdefinition anwenden.

### <a name="markupextensionreturntypeattribute"></a>Markupextensionreturntypeattribute

**Referenzdokumentation:**  <xref:System.Windows.Markup.MarkupExtensionReturnTypeAttribute>

**Gilt für:** Klasse, die voraussichtlich ein <xref:System.Windows.Markup.MarkupExtension> abgeleiteter Typ ist.

**Argumente:** A, <xref:System.Type> das den genauesten Typ `ProvideValue` angibt, <xref:System.Windows.Markup.MarkupExtension>der als Ergebnis der attributierten erwartet werden soll.

Weitere Informationen finden Sie unter [Markuperweiterungen für XAML-Übersicht](markup-extensions-overview.md).

### <a name="namescopepropertyattribute"></a>Namescopepropertyattribute

**Referenzdokumentation:**  <xref:System.Windows.Markup.NameScopePropertyAttribute>

**Gilt für:** Klasse

**Argumente:** Unterstützt zwei Formen der Zuordnung:

- Eine Zeichenfolge, die den Namen einer Eigenschaft für den attributierten Typ angibt.

- Eine Zeichenfolge, die den Namen einer <xref:System.Type> Eigenschaft angibt, und eine für den Typ, der die benannte Eigenschaft definiert. Dieses Formular dient zum Angeben eines anfügbaren Elements als XAML-Namescope-Eigenschaft.

<xref:System.Windows.Markup.NameScopePropertyAttribute>gibt eine Eigenschaft an, die den XAML-Namescope-Wert für die attributierte Klasse bereitstellt. Es wird erwartet, dass die XAML-Namescope-Eigenschaft auf ein Objekt verweist, das das eigentliche XAML-Namescope, seinen Speicher und sein Verhalten implementiert <xref:System.Windows.Markup.INameScope> und enthält.

### <a name="runtimenamepropertyattribute"></a>RuntimeNamePropertyAttribute

**Referenzdokumentation:**  <xref:System.Windows.Markup.RuntimeNamePropertyAttribute>

**Gilt für:** Klasse

**Argumente:** Eine Zeichenfolge, die den Namen der Laufzeitnameneigenschaft für den attributierten Typ angibt.

<xref:System.Windows.Markup.RuntimeNamePropertyAttribute>meldet eine Eigenschaft des attributierten Typs, die der XAML [x:Name-Direktive](xname-directive.md)zugeordnet ist. Die Eigenschaft muss <xref:System.String> vom Typ sein und lesen/schreiben.

Die Definition erbt alle abgeleiteten Typen, die dem definierenden Typ zugewiesen werden können. Sie können die Definition für einen bestimmten <xref:System.Windows.Markup.RuntimeNamePropertyAttribute> abgeleiteten Typ überschreiben, indem Sie den bestimmten abgeleiteten Typ anwenden.

### <a name="trimsurroundingwhitespaceattribute"></a>Trimsurroundingwhitespaceattribute

**Referenzdokumentation:**  <xref:System.Windows.Markup.TrimSurroundingWhitespaceAttribute>

**Gilt für:** Typen

**Argumente:** nichts.

<xref:System.Windows.Markup.TrimSurroundingWhitespaceAttribute>wird auf bestimmte Typen angewendet, die als untergeordnete Elemente innerhalb von signifikanten <xref:System.Windows.Markup.WhitespaceSignificantCollectionAttribute>Leerrauminhalten angezeigt werden können (Inhalt, der von einer Auflistung mit enthält). <xref:System.Windows.Markup.TrimSurroundingWhitespaceAttribute>ist hauptsächlich für den Speicherpfad relevant, ist jedoch im XAML-Typsystem im Ladepfad verfügbar, indem untersucht <xref:System.Xaml.XamlType.TrimSurroundingWhitespace%2A?displayProperty=nameWithType>wird. Weitere Informationen finden Sie [unter Whitespace-Verarbeitung in XAML](white-space-processing.md).

### <a name="typeconverterattribute"></a>TypeConverterAttribute

**Referenzdokumentation:**  <xref:System.ComponentModel.TypeConverterAttribute>

**Gilt für:** Klasse, Eigenschaft, Methode (der einzige XAML-gültige Methodenfall ist ein `get` Accessor, der ein anfügbierbares Element unterstützt).

**Argumente:** Die <xref:System.Type> der <xref:System.ComponentModel.TypeConverter>.

<xref:System.ComponentModel.TypeConverterAttribute>in einem XAML-Kontext <xref:System.ComponentModel.TypeConverter>verweist auf eine benutzerdefinierte . Dadurch <xref:System.ComponentModel.TypeConverter> wird das Typkonvertierungsverhalten für benutzerdefinierte Typen oder Member dieses Typs angezeigt.

Wenden <xref:System.ComponentModel.TypeConverterAttribute> Sie das Attribut auf Ihren Typ an und verweisen Sie auf die Typkonverterimplementierung. Sie können Typkonverter für XAML für Klassen, Strukturen oder Schnittstellen definieren. Sie müssen keine Typkonvertierung für Enumerationen bereitstellen, diese Konvertierung ist nativ aktiviert.

Der Typkonverter sollte in der Lage sein, aus einer Zeichenfolge, die für Attribute oder Initialisierungstext in Markup verwendet wird, in den beabsichtigten Zieltyp zu konvertieren. Weitere Informationen finden Sie unter [TypeConverters und XAML](../../framework/wpf/advanced/typeconverters-and-xaml.md).

Anstatt auf alle Werte eines Typs anzuwenden, kann auch ein Typkonverterverhalten für XAML für eine bestimmte Eigenschaft festgelegt werden. In diesem Fall <xref:System.ComponentModel.TypeConverterAttribute> wenden Sie sich auf die Eigenschaftsdefinition (die äußere Definition, nicht die spezifische `get` und `set` Die Definitionen).

Ein Typkonverterverhalten für die XAML-Verwendung eines benutzerdefinierten <xref:System.ComponentModel.TypeConverterAttribute> anfügbaren Elements kann zugewiesen werden, indem auf den `get` Methodenaccessor angewendet wird, der die XAML-Verwendung unterstützt.

Ähnlich <xref:System.ComponentModel.TypeConverter>wie <xref:System.ComponentModel.TypeConverterAttribute> , existierte in .NET vor dem Vorhandensein von XAML, und das Typkonvertermodell diente anderen Zwecken. Um darauf zu <xref:System.ComponentModel.TypeConverterAttribute>verweisen und zu verwenden, `using` müssen <xref:System.ComponentModel>Sie es vollständig qualifizieren oder eine Anweisung für bereitstellen. Schließen Sie auch die Systemassembly in Ihr Projekt ein.

### <a name="uidpropertyattribute"></a>Uidpropertyattribute

**Referenzdokumentation:**  <xref:System.Windows.Markup.UidPropertyAttribute>

**Gilt für:** Klasse

**Argumente:** Eine Zeichenfolge, die auf die entsprechende Eigenschaft anhand des Namens verweist.

Gibt die CLR-Eigenschaft einer Klasse an, die die [x:Uid-Direktive](xuid-directive.md)aliast.

### <a name="usableduringinitializationattribute"></a>Usableduringinitializationattribute

**Referenzdokumentation:**  <xref:System.Windows.Markup.UsableDuringInitializationAttribute>

**Gilt für:** Klasse

**Argumente:** Ein boolescher. Wenn der Wert für den beabsichtigten Zweck des `true`Attributs verwendet wird, sollte er auf festgelegt werden.

Gibt an, ob der Typ bei der Erstellung von XAML-Objektdiagrammen von oben nach unten erstellt wird. Dies ist ein fortgeschrittenes Konzept, das wahrscheinlich eng mit der Definition Ihres Programmiermodells zusammenhängt. Weitere Informationen finden Sie unter <xref:System.Windows.Markup.UsableDuringInitializationAttribute>.

### <a name="valueserializerattribute"></a>Valueserializerattribute

**Referenzdokumentation:**  <xref:System.Windows.Markup.ValueSerializerAttribute>

**Gilt für:** Klasse, Eigenschaft, Methode (der einzige XAML-gültige Methodenfall ist ein `get` Accessor, der ein anfügbierbares Element unterstützt).

**Argumente:** A, <xref:System.Type> das die Unterstützungsklasse für wertserialisierende Datenandaten angibt, die beim Serialisieren aller Eigenschaften des attributierten Typs oder der spezifischen attributierten Eigenschaft verwendet werden soll.

<xref:System.Windows.Markup.ValueSerializer>gibt eine Wertserialisierungsklasse an, die <xref:System.ComponentModel.TypeConverter> mehr Status und Kontext erfordert als eine. <xref:System.Windows.Markup.ValueSerializer>kann einem anfügbaren Element <xref:System.Windows.Markup.ValueSerializerAttribute> zugeordnet werden, indem das Attribut auf die statische `get` Accessormethode für das anfügbierbare Element angewendet wird. Die Wertserialisierung ist auch für Enumerationen, Schnittstellen und Strukturen anwendbar, jedoch nicht für Delegaten.

### <a name="whitespacesignificantcollectionattribute"></a>Whitespacesignificantcollectionattribute

**Referenzdokumentation:**  <xref:System.Windows.Markup.WhitespaceSignificantCollectionAttribute>

**Gilt für:** Klasse, insbesondere Auflistungstypen, von denen erwartet wird, dass sie gemischten Inhalt hosten, wobei Leerraum um Objektelemente für die UI-Darstellung von Bedeutung sein kann.

**Argumente:** nichts.

<xref:System.Windows.Markup.WhitespaceSignificantCollectionAttribute>gibt an, dass ein Auflistungstyp als Leerraum verarbeitet werden soll, der von einem XAML-Prozessor signifikant ist, was die Konstruktion der Wertknoten des XAML-Knotenstreams innerhalb der Auflistung beeinflusst. Weitere Informationen finden Sie [unter Whitespace-Verarbeitung in XAML](white-space-processing.md).

### <a name="xamldeferloadattribute"></a>Xamldeferloadattribute

**Referenzdokumentation:**  <xref:System.Windows.Markup.XamlDeferLoadAttribute>

**Gilt für:** Klasse, Eigenschaft.

**Argumente:** Unterstützt zwei Attributionsformulartypen als Zeichenfolgen <xref:System.Type>oder Typen als . Siehe <xref:System.Windows.Markup.XamlDeferLoadAttribute>.

Gibt an, dass eine Klasse oder eine Eigenschaft über eine verzögerte Auslastungsverwendung für XAML (z. B. ein Vorlagenverhalten) verfügt, und meldet die Klasse, die das verzögernde Verhalten und seinen Ziel-/Inhaltstyp aktiviert.

### <a name="xamlsetmarkupextensionattribute"></a>XamlSetMarkupExtensionAttribute

**Referenzdokumentation:**  <xref:System.Windows.Markup.XamlSetMarkupExtensionAttribute>

**Gilt für:** Klasse

**Argumente:** Benennt den Rückruf.

Gibt an, dass eine Klasse eine Markuperweiterung verwenden kann, um einen Wert für eine oder mehrere ihrer Eigenschaften bereitzustellen, und verweist auf einen Handler, den ein XAML-Writer aufrufen soll, bevor er einen Markuperweiterungssatzvorgang für eine beliebige Eigenschaft der Klasse ausführt.

### <a name="xamlsettypeconverterattribute"></a>Xamlsettypeconverterattribute

**Referenzdokumentation:**  <xref:System.Windows.Markup.XamlSetTypeConverterAttribute>

**Gilt für:** Klasse

**Argumente:** Benennt den Rückruf.

Gibt an, dass eine Klasse einen Typkonverter verwenden kann, um einen Wert für eine oder mehrere ihrer Eigenschaften bereitzustellen, und verweist auf einen Handler, den ein XAML-Writer aufrufen soll, bevor er einen Typkonvertersatzvorgang für eine beliebige Eigenschaft der Klasse ausführt.

### <a name="xmllangpropertyattribute"></a>Xmllangpropertyattribute

**Referenzdokumentation:**  <xref:System.Windows.Markup.XmlLangPropertyAttribute>

**Gilt für:** Klasse

**Argumente:** Eine Zeichenfolge, die den Namen der `xml:lang` Eigenschaft für alias to für den attributierten Typ angibt.

<xref:System.Windows.Markup.XmlLangPropertyAttribute>meldet eine Eigenschaft des attributierten Typs, die der XML-Direktive `lang` zugeordnet ist. Die Eigenschaft ist nicht <xref:System.String> unbedingt vom Typ, sondern muss von einer Zeichenfolge zugewiesen werden können (die Zuweisung kann durch Zuordnen eines Typkonverters zum Typ der Eigenschaft oder mit der spezifischen Eigenschaft erfolgen). Die Eigenschaft muss gelesen/geschrieben werden.

Das Szenario `xml:lang` für die Zuordnung besteht so, dass ein Laufzeitobjektmodell Zugriff auf XML-angegebene Sprachinformationen hat, ohne speziell mit einem XMLDOM zu verarbeiten.

Die Definition erbt alle abgeleiteten Typen, die dem definierenden Typ zugewiesen werden können. Sie können die Definition für einen bestimmten <xref:System.Windows.Markup.XmlLangPropertyAttribute> abgeleiteten Typ überschreiben, indem Sie auf den bestimmten abgeleiteten Typ anwenden, obwohl dies ein ungewöhnliches Szenario ist.

## <a name="xaml-related-clr-attributes-at-the-assembly-level"></a>XAML-bezogene CLR-Attribute auf Baugruppenebene

In den folgenden Abschnitten werden die XAML-bezogenen Attribute beschrieben, die nicht auf Typen oder Elementdefinitionen angewendet werden, sondern auf Assemblys. Diese Attribute sind für das übergeordnete Ziel relevant, eine Bibliothek zu definieren, die benutzerdefinierte Typen enthält, die in XAML verwendet werden sollen. Einige der Attribute beeinflussen den XAML-Knotenstream nicht unbedingt direkt, sondern werden im Knotenstream für andere Consumer weitergegeben. Zu den Consumern für die Informationen gehören Entwurfsumgebungen oder Serialisierungsprozesse, die XAML-Namespaceinformationen und zugehörige Präfixinformationen benötigen. Ein XAML-Schemakontext (einschließlich der .NET XAML Services-Standardeinstellung) verwendet diese Informationen ebenfalls.

### <a name="xmlnscompatiblewithattribute"></a>Xmlnscompatiblewithattribute

**Referenzdokumentation:**  <xref:System.Windows.Markup.XmlnsCompatibleWithAttribute>

**Arguments:**

- Eine Zeichenfolge, die den Bezeichner des XAML-Namespace angibt, um subsume.

- Eine Zeichenfolge, die den Bezeichner des XAML-Namespace angibt, der den XAML-Namespace aus dem vorherigen Argument subsumieren kann.

  <xref:System.Windows.Markup.XmlnsCompatibleWithAttribute>gibt an, dass ein XAML-Namespace von einem anderen XAML-Namespace subsumiert werden kann. In der Regel wird der zusammenfassende XAML-Namespace in einem zuvor definierten <xref:System.Windows.Markup.XmlnsDefinitionAttribute> angegeben. Diese Technik kann zum Versionslernen eines XAML-Vokabulars in einer Bibliothek verwendet und mit zuvor definiertem Markup mit dem früheren versionierten Vokabular kompatibel gemacht werden.

### <a name="xmlnsdefinitionattribute"></a>XmlnsDefinitionAttribute

**Referenzdokumentation:**  <xref:System.Windows.Markup.XmlnsDefinitionAttribute>

**Arguments:**

- Eine Zeichenfolge, die den Bezeichner des zu definierenden XAML-Namespace angibt.

- Eine Zeichenfolge, die einen CLR-Namespace benennt. Der CLR-Namespace sollte öffentliche Typen in der Assembly definieren, und mindestens einer der CLR-Namespacetypen sollte für die XAML-Verwendung vorgesehen sein.

  <xref:System.Windows.Markup.XmlnsDefinitionAttribute>gibt eine Zuordnung pro Assembly zwischen einem XAML-Namespace und einem CLR-Namespace an, die dann für die Typauflösung durch einen XAML-Objektschreiber oder XAML-Schemakontext verwendet wird.

  Mehr als <xref:System.Windows.Markup.XmlnsDefinitionAttribute> eine kann auf eine Baugruppe angewendet werden. Dies kann aus einer beliebigen Kombination der folgenden Gründe erfolgen:

- Der Bibliotheksentwurf enthält mehrere CLR-Namespaces für die logische Organisation des Laufzeit-API-Zugriffs. Sie möchten jedoch, dass alle Typen in diesen Namespaces XAML-fähig sind, indem Sie auf denselben XAML-Namespace verweisen. In diesem Fall wenden <xref:System.Windows.Markup.XmlnsDefinitionAttribute> Sie mehrere <xref:System.Windows.Markup.XmlnsDefinitionAttribute.XmlNamespace%2A> Attribute mit <xref:System.Windows.Markup.XmlnsDefinitionAttribute.ClrNamespace%2A> demselben Wert, aber unterschiedlichen Werten an. Dies ist besonders nützlich, wenn Sie Zuordnungen für den XAML-Namespace definieren, für den Ihr Framework oder Ihre Anwendung den Standard-XAML-Namespace in gängiger Verwendung sein soll.

- Der Bibliotheksentwurf enthält mehrere CLR-Namespaces, und Sie möchten eine bewusste XAML-Namespace-Trennung zwischen den Verwendungen von Typen in diesen CLR-Namespaces.

- Sie definieren einen CLR-Namespace in der Assembly und möchten, dass über mehr als einen XAML-Namespace darauf zugegriffen werden kann. Dieses Szenario tritt auf, wenn Sie mehrere Vokabeln mit derselben Codebasis unterstützen.

- Sie definieren xAML-Sprachunterstützung in einem oder mehreren CLR-Namespaces. In diesem Fall <xref:System.Windows.Markup.XmlnsDefinitionAttribute.XmlNamespace%2A> sollte `http://schemas.microsoft.com/winfx/2006/xaml`der Wert .

### <a name="xmlnsprefixattribute"></a>Xmlnsprefixattribute

**Referenzdokumentation:**  <xref:System.Windows.Markup.XmlnsPrefixAttribute>

**Arguments:**

- Eine Zeichenfolge, die den Bezeichner eines XAML-Namespace angibt.

- Eine Zeichenfolge, die ein empfohlenes Präfix angibt.

  <xref:System.Windows.Markup.XmlnsDefinitionAttribute>gibt ein empfohlenes Präfix für einen XAML-Namespace an. Das Präfix ist nützlich, wenn Elemente und Attribute in einer XAML-Datei <xref:System.Xaml.XamlXmlWriter>geschrieben werden, die von .NET XAML Services serialisiert wird, oder wenn eine XAML-implementierende Bibliothek mit einer Entwurfsumgebung interagiert, die über XAML-Bearbeitungsfeatures verfügt.

  Mehr als <xref:System.Windows.Markup.XmlnsPrefixAttribute> eine kann auf eine Baugruppe angewendet werden. Dies kann aus einer beliebigen Kombination der folgenden Gründe erfolgen:

- Ihre Assembly definiert Typen für mehr als einen XAML-Namespace. Definieren Sie in diesem Fall für jeden XAML-Namespace unterschiedliche Präfixwerte.

- Sie unterstützen mehrere Vokabeln und verwenden für jedes Vokabular und jeden XAML-Namespace unterschiedliche Präfixe.

- Sie definieren XAML-Sprachunterstützung in <xref:System.Windows.Markup.XmlnsDefinitionAttribute> der `http://schemas.microsoft.com/winfx/2006/xaml`Assembly und verfügen über eine für . In diesem Fall sollten Sie in `x`der Regel das Präfix heraufstufen.

> [!NOTE]
> .NET XAML Services definiert auch das XAML-bezogene Attribut <xref:System.Windows.Markup.RootNamespaceAttribute>. Dieses Attribut ist ein Attribut auf Assemblyebene für die Projektsystemunterstützung und für benutzerdefinierte XAML-Typen nicht relevant.

## <a name="see-also"></a>Weitere Informationen

- <xref:System.Attribute>
- [Definieren benutzerdefinierter Typen für die Verwendung in .NET-XAML-Diensten](define-custom-types.md)
