---
title: XAML-bezogene CLR-Attribute für benutzerdefinierte Typen und Bibliotheken
ms.date: 03/30/2017
helpviewer_keywords:
- CLR attributes for custom types [XAML Services]
ms.assetid: 5dfb299a-b6e2-41b8-8694-e6ac987547f1
ms.openlocfilehash: 2f907d097f52f13e733713d8ad68cc2390b051ed
ms.sourcegitcommit: 30a83efb57c468da74e9e218de26cf88d3254597
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/20/2019
ms.locfileid: "68364232"
---
# <a name="xaml-related-clr-attributes-for-custom-types-and-libraries"></a>XAML-bezogene CLR-Attribute für benutzerdefinierte Typen und Bibliotheken
In diesem Thema werden die Common Language Runtime (CLR)-Attribute beschrieben, die durch .NET Framework XAML-Dienste definiert werden. Außerdem werden andere CLR-Attribute beschrieben, die in den .NET Framework definiert sind, die ein XAML-bezogenes Szenario für die Anwendung auf Assemblys oder Typen aufweisen. Das Zuweisen von Assemblys, Typen oder Membern mit diesen CLR-Attributen bietet XAML-typsysteminformationen, die sich auf Ihre Typen beziehen. Informationen werden für alle XAML-Consumer bereitgestellt, die .NET Framework XAML-Dienste verwenden, um den XAML-knotenstream direkt oder über die dedizierten XAML-Reader und XAML-Writer zu verarbeiten.  
  
## <a name="xaml-related-clr-attributes-for-custom-types-and-custom-members"></a>XAML-bezogene CLR-Attribute für benutzerdefinierte Typen und benutzerdefinierte Member  
 Die Verwendung von CLR-Attributen erfordert, dass Sie die allgemeine CLR zum Definieren von Typen verwenden. andernfalls sind solche Attribute nicht verfügbar. Wenn Sie die CLR verwenden, um die Typunterstützung zu definieren, kann der XAML-Standardschema Kontext, der von XAML-Writern von .NET Framework XAML-Diensten verwendet wird, die CLR-Zuordnung durch Reflektion gegen das unterstützen  
  
 In den folgenden Abschnitten werden die XAML-bezogenen Attribute beschrieben, die Sie auf benutzerdefinierte Typen oder benutzerdefinierte Member anwenden können. Jedes CLR-Attribut kommuniziert Informationen, die für ein XAML-Typsystem relevant sind. Im Ladepfad können die attributierten Informationen entweder dazu beitragen, dass der XAML-Reader einen gültigen XAML-knotenstream bildet, oder der XAML-Writer erzeugt ein gültiges Objekt Diagramm. Im Speicherpfad helfen die attributierten Informationen entweder dem XAML-Reader, einen gültigen XAML-knotenstream zu bilden, der XAML-typsysteminformationen wieder bildet. oder es werden serialisierungshinweise oder Anforderungen für den XAML-Writer oder andere XAML-Consumer deklariert.  
  
### <a name="ambientattribute"></a>Ambientattribute  
 **Referenz Dokumentation:**  <xref:System.Windows.Markup.AmbientAttribute>  
  
 **Gilt für:** Klassen-, Eigenschaften- `get` oder Accessor-Member, die anfügbare Eigenschaften unterstützen.  
  
 **Argumentation** None  
  
 <xref:System.Windows.Markup.AmbientAttribute>Gibt an, dass die-Eigenschaft oder alle Eigenschaften, die den attributierten Typ annehmen, unter dem Ambient-Eigenschafts Konzept in XAML interpretiert werden sollen. Das Umgebungskonzept bezieht sich darauf, wie XAML-Prozessoren Typbesitzer von Membern bestimmen. Eine Ambient-Eigenschaft ist eine Eigenschaft, bei der beim Erstellen eines Objekt Diagramms erwartet wird, dass der Wert im Parserkontext verfügbar ist, wobei jedoch für die direkt erstellte XAML-Knotengruppe eine typische Typmember-Suche angehalten wird.  
  
 Das Ambient-Konzept kann auf anfügbare Member angewendet werden, die nicht als Eigenschaften in Bezug auf die Definition der CLR-Zuordnung <xref:System.AttributeTargets>dargestellt werden. Die Verwendung der Methoden Zuordnung sollte nur bei einem `get` -Accessor angewendet werden, der die anfügbare Verwendung für XAML unterstützt.  
  
### <a name="constructorargumentattribute"></a>ConstructorArgumentAttribute  
 **Referenz Dokumentation:**  <xref:System.Windows.Markup.ConstructorArgumentAttribute>  
  
 **Gilt für:** Klasse  
  
 **Argumentation** Eine Zeichenfolge, die den Namen der Eigenschaft angibt, die mit einem einzelnen Konstruktorargument übereinstimmt.  
  
 <xref:System.Windows.Markup.ConstructorArgumentAttribute>Gibt an, dass ein Objekt mithilfe einer nicht parameterlosen Konstruktorsyntax initialisiert werden kann und dass eine Eigenschaft mit dem angegebenen Namen Informationen zur Erstellung bereitstellt. Diese Informationen sind in erster Linie für die XAML-Serialisierung vorgesehen. Weitere Informationen finden Sie unter <xref:System.Windows.Markup.ConstructorArgumentAttribute>.  
  
### <a name="contentpropertyattribute"></a>ContentPropertyAttribute  
 **Referenz Dokumentation:**  <xref:System.Windows.Markup.ContentPropertyAttribute>  
  
 **Gilt für:** Klasse  
  
 **Argumentation** Eine Zeichenfolge, die den Namen eines Members des attributierten Typs angibt.  
  
 <xref:System.Windows.Markup.ContentPropertyAttribute>Gibt an, dass die Eigenschaft, die vom-Argument benannt wird, als XAML-Inhalts Eigenschaft für diesen Typ fungieren soll. Die Definition der XAML-Inhalts Eigenschaft erbt alle abgeleiteten Typen, die dem definierenden Typ zugewiesen werden können. Sie können die Definition für einen bestimmten abgeleiteten Typ überschreiben <xref:System.Windows.Markup.ContentPropertyAttribute> , indem Sie auf den spezifischen abgeleiteten Typ anwenden.  
  
 Für die Eigenschaft, die als XAML-Inhalts Eigenschaft fungiert, kann das Tagging von Eigenschaften Elementen für die Eigenschaft in der XAML-Verwendung weggelassen werden. In der Regel legen Sie XAML-Inhalts Eigenschaften fest, die ein optimiertes XAML-Markup für Ihre Inhalts-und Containment-Modelle herauf Stufen. Da nur ein Member als XAML-Inhalts Eigenschaft festgelegt werden kann, haben Sie manchmal Entwurfs Optionen, um zu entscheiden, welche von mehreren Container Eigenschaften eines Typs als XAML-Inhalts Eigenschaft festgelegt werden sollen. Die anderen Container Eigenschaften müssen mit expliziten Eigenschafts Elementen verwendet werden.  
  
 Im XAML-knotenstream werden in XAML-Inhalts Eigenschaften `StartMember` weiterhin `EndMember` -und-Knoten mit dem Namen der-Eigenschaft <xref:System.Xaml.XamlMember>für das erzeugt. Um zu ermitteln, ob ein Member die XAML-Inhalts Eigenschaft ist <xref:System.Xaml.XamlType> , überprüfen `StartObject` Sie den Wert von der Position <xref:System.Xaml.XamlType.ContentProperty%2A>, und rufen Sie den Wert von ab.  
  
### <a name="contentwrapperattribute"></a>ContentWrapperAttribute  
 **Referenz Dokumentation:**  <xref:System.Windows.Markup.ContentWrapperAttribute>  
  
 **Gilt für:** -Klasse, speziell Auflistungs Typen.  
  
 **Argumentation** Ein <xref:System.Type> , der den Typ angibt, der als Inhaltstyp für den Inhalt eines fremden Inhalts verwendet werden soll.  
  
 <xref:System.Windows.Markup.ContentWrapperAttribute>gibt mindestens einen Typ für den zugeordneten Sammlungstyp an, der zum Einschließen von fremd Inhalten verwendet wird. Foreign Content bezieht sich auf Fälle, in denen die Typsystem Einschränkungen für den Typ der Content-Eigenschaft nicht alle möglichen Inhalts Fälle erfassen, die die XAML-Verwendung für den besitzenden Typ unterstützen würde. Beispielsweise kann die XAML-Unterstützung für den Inhalt eines bestimmten Typs Zeichen folgen in einem stark <xref:System.Collections.ObjectModel.Collection%601>typisierten generischen-Typ unterstützen. Inhalts Wrapper sind nützlich für die Migration von bereits vorhandenen Markup Konventionen in das XAML-Konzept der zustellbaren Werte für Auflistungen, z. b. die Migration Text bezogener Inhalts Modelle.  
  
 Um mehr als einen Inhaltstyp für den Inhalt anzugeben, wenden Sie das Attribut mehrmals an.  
  
### <a name="dependsonattribute"></a>Dependsonattribute  
 **Referenz Dokumentation:**  <xref:System.Windows.Markup.DependsOnAttribute>  
  
 **Gilt für:** Eigenschaft  
  
 **Argumentation** Eine Zeichenfolge, die den Namen eines anderen Members des attributierten Typs angibt.  
  
 <xref:System.Windows.Markup.DependsOnAttribute>Gibt an, dass die attributierte Eigenschaft vom Wert einer anderen Eigenschaft abhängt. Wenn Sie dieses Attribut auf eine Eigenschafts Definition anwenden, wird sichergestellt, dass die abhängigen Eigenschaften zuerst in einem XAML-Objekt verarbeitet werden. Verwendung von <xref:System.Windows.Markup.DependsOnAttribute> geben Sie die Ausnahmefälle von Eigenschaften für Typen an, bei denen eine bestimmte Reihenfolge der Verarbeitung für eine gültige Objekt Erstellung befolgt werden muss.  
  
 Sie können mehrere <xref:System.Windows.Markup.DependsOnAttribute> Fälle auf eine Eigenschafts Definition anwenden.  
  
### <a name="markupextensionreturntypeattribute"></a>MarkupExtensionReturnTypeAttribute  
 **Referenz Dokumentation:**  <xref:System.Windows.Markup.MarkupExtensionReturnTypeAttribute>  
  
 **Gilt für:** Klasse, die als <xref:System.Windows.Markup.MarkupExtension> abgeleiteter Typ erwartet wird.  
  
 **Argumentation** Ein <xref:System.Type> , der den genauesten Typ angibt, der `ProvideValue` als Ergebnis des attributierten <xref:System.Windows.Markup.MarkupExtension>erwartet wird.  
  
 Weitere Informationen finden Sie unter [Übersicht über Markup Erweiterungen für XAML](markup-extensions-for-xaml-overview.md).  
  
### <a name="namescopepropertyattribute"></a>NameScopePropertyAttribute  
 **Referenz Dokumentation:**  <xref:System.Windows.Markup.NameScopePropertyAttribute>  
  
 **Gilt für:** Klasse  
  
 **Argumentation** Unterstützt zwei Formen der Zuordnung:  
  
- Eine Zeichenfolge, die den Namen einer Eigenschaft für den attributierten Typ angibt.  
  
- Eine Zeichenfolge, die den Namen einer Eigenschaft angibt, und <xref:System.Type> ein-Objekt für den Typ, der die benannte Eigenschaft definiert. Dieses Formular dient zum Angeben eines anfügbaren Members als XAML-Namescope-Eigenschaft.  
  
 <xref:System.Windows.Markup.NameScopePropertyAttribute>gibt eine Eigenschaft an, die den XAML-Namescope-Wert für die attributierte Klasse bereitstellt. Es wird erwartet, dass die XAML-Namescope-Eigenschaft auf <xref:System.Windows.Markup.INameScope> ein Objekt verweist, das implementiert und den tatsächlichen XAML-Namescope, seinen Speicher und sein Verhalten enthält.  
  
### <a name="runtimenamepropertyattribute"></a>RuntimeNamePropertyAttribute  
 **Referenz Dokumentation:**  <xref:System.Windows.Markup.RuntimeNamePropertyAttribute>  
  
 **Gilt für:** Klasse  
  
 **Argumentation** Eine Zeichenfolge, die den Namen der Lauf Zeit Namen Eigenschaft für den attributierten Typ angibt.  
  
 <xref:System.Windows.Markup.RuntimeNamePropertyAttribute>meldet eine Eigenschaft des attributierten Typs, der der x:Name- [Direktive](x-name-directive.md)von XAML zugeordnet ist. Die-Eigenschaft muss vom Typ <xref:System.String> sein und muss über Lese-/Schreibzugriff verfügen.  
  
 Die Definition erbt alle abgeleiteten Typen, die dem definierenden Typ zugewiesen werden können. Sie können die Definition für einen bestimmten abgeleiteten Typ überschreiben <xref:System.Windows.Markup.RuntimeNamePropertyAttribute> , indem Sie auf den spezifischen abgeleiteten Typ anwenden.  
  
### <a name="trimsurroundingwhitespaceattribute"></a>TrimSurroundingWhitespaceAttribute  
 **Referenz Dokumentation:**  <xref:System.Windows.Markup.TrimSurroundingWhitespaceAttribute>  
  
 **Gilt für:** Typen  
  
 **Argumentation** Keine  
  
 <xref:System.Windows.Markup.TrimSurroundingWhitespaceAttribute>wird auf bestimmte Typen angewendet, die möglicherweise als untergeordnete Elemente in signifikantem Leerraum (Inhalt, <xref:System.Windows.Markup.WhitespaceSignificantCollectionAttribute>der von einer Auflistung mit verwendet wird) angezeigt werden. <xref:System.Windows.Markup.TrimSurroundingWhitespaceAttribute>ist hauptsächlich für den Speicherpfad relevant, aber im XAML-Typsystem im Ladepfad durch untersuchen <xref:System.Xaml.XamlType.TrimSurroundingWhitespace%2A?displayProperty=nameWithType>von verfügbar. Weitere Informationen finden Sie unter [Leerraum Verarbeitung in XAML](whitespace-processing-in-xaml.md).  
  
### <a name="typeconverterattribute"></a>TypeConverterAttribute  
 **Referenz Dokumentation:**  <xref:System.ComponentModel.TypeConverterAttribute>  
  
 **Gilt für:** Class, Property, Method (der einzige XAML-gültige Methoden Fall ist ein `get` -Accessor, der einen anfügbaren Member unterstützt).  
  
 **Argumentation** Die <xref:System.Type> des <xref:System.ComponentModel.TypeConverter>.  
  
 <xref:System.ComponentModel.TypeConverterAttribute>in einem XAML-Kontext verweist auf <xref:System.ComponentModel.TypeConverter>ein benutzerdefiniertes. Dies <xref:System.ComponentModel.TypeConverter> stellt ein Typkonvertierungs Verhalten für benutzerdefinierte Typen oder Member dieses Typs bereit.  
  
 Sie wenden das <xref:System.ComponentModel.TypeConverterAttribute> -Attribut auf den Typ an und verweisen auf Ihre typkonverterimplementierung. Sie können Typkonverter für XAML für Klassen, Strukturen oder Schnittstellen definieren. Sie müssen keine Typkonvertierung für Enumerationen durchführen, da diese Konvertierung nativ aktiviert ist.  
  
 Ihr Typkonverter sollte in der Lage sein, von einer Zeichenfolge, die für Attribute oder Initialisierungs Text in Markup verwendet wird, in den gewünschten Zieltyp zu konvertieren. Weitere Informationen finden Sie unter [TypeConverter und XAML](../wpf/advanced/typeconverters-and-xaml.md).  
  
 Anstatt auf alle Werte eines Typs anzuwenden, kann auch ein Typkonverterverhalten für XAML für eine bestimmte Eigenschaft festgelegt werden. In diesem Fall wenden <xref:System.ComponentModel.TypeConverterAttribute> Sie auf die Eigenschafts Definition an (die äußere Definition, nicht die spezifischen `set` `get` -und-Definitionen).  
  
 Ein Typkonverterverhalten für die XAML-Verwendung eines benutzerdefinierten anfügbaren Members <xref:System.ComponentModel.TypeConverterAttribute> kann zugewiesen `get` werden, indem auf den Methoden Accessor angewendet wird, der die XAML-Verwendung unterstützt.  
  
 Ähnlich wie <xref:System.ComponentModel.TypeConverterAttribute> , war im .NET Framework vor dem vorhanden sein von XAML vorhanden, und das typkonvertermodell diente anderen Zwecken. <xref:System.ComponentModel.TypeConverter> Um auf zu verweisen und zu <xref:System.ComponentModel.TypeConverterAttribute>verwenden, müssen Sie es vollständig qualifizieren oder `using` eine- <xref:System.ComponentModel>Anweisung für angeben. Sie müssen auch die Systemassembly in das Projekt einschließen.  
  
### <a name="uidpropertyattribute"></a>UidPropertyAttribute  
 **Referenz Dokumentation:**  <xref:System.Windows.Markup.UidPropertyAttribute>  
  
 **Gilt für:** Klasse  
  
 **Argumentation** Eine Zeichenfolge, die anhand des Namens auf die relevante Eigenschaft verweist.  
  
 Gibt die CLR-Eigenschaft einer Klasse an, die die [x:UID-Direktive](x-uid-directive.md)Aliase.  
  
### <a name="usableduringinitializationattribute"></a>UsableDuringInitializationAttribute  
 **Referenz Dokumentation:**  <xref:System.Windows.Markup.UsableDuringInitializationAttribute>  
  
 **Gilt für:** Klasse  
  
 **Argumentation** Ein boolescher Wert. Wenn Sie für den beabsichtigten Zweck des Attributs verwendet wird, sollte dies immer `true`als angegeben werden.  
  
 Gibt an, ob dieser Typ beim Erstellen des XAML-Objektdiagramms von oben nach unten (Top-Down) erstellt wird. Dabei handelt es sich um ein erweitertes Konzept, das wahrscheinlich eng mit der Definition des Programmiermodells verknüpft ist. Weitere Informationen finden Sie unter <xref:System.Windows.Markup.UsableDuringInitializationAttribute>.  
  
### <a name="valueserializerattribute"></a>ValueSerializerAttribute  
 **Referenz Dokumentation:**  <xref:System.Windows.Markup.ValueSerializerAttribute>  
  
 **Gilt für:** Class, Property, Method (der einzige XAML-gültige Methoden Fall ist ein `get` -Accessor, der einen anfügbaren Member unterstützt).  
  
 **Argumentation** Eine <xref:System.Type> , die die Unterstützung der Serialisierungsprogramme angibt, die beim Serialisieren aller Eigenschaften des attributierten Typs oder der spezifischen attributierten Eigenschaft verwendet werden soll.  
  
 <xref:System.Windows.Markup.ValueSerializer>gibt eine wertserialisierungsklasse an, die mehr Zustand und Kontext <xref:System.ComponentModel.TypeConverter> erfordert, als ein. <xref:System.Windows.Markup.ValueSerializer>kann einem anfügbaren Member zugeordnet werden, indem <xref:System.Windows.Markup.ValueSerializerAttribute> das-Attribut auf `get` die statische Accessormethode für den anfügbaren Member angewendet wird. Die wertserialisierung gilt auch für Enumerationen, Schnittstellen und Strukturen, jedoch nicht für Delegaten.  
  
### <a name="whitespacesignificantcollectionattribute"></a>WhitespaceSignificantCollectionAttribute  
 **Referenz Dokumentation:**  <xref:System.Windows.Markup.WhitespaceSignificantCollectionAttribute>  
  
 **Gilt für:** -Klasse, insbesondere Sammlungs Typen, die als Host für gemischte Inhalte erwartet werden, wobei Leerraum um Objekt Elemente für die Darstellung der Benutzeroberfläche möglicherweise wichtig ist.  
  
 **Argumentation** Keine  
  
 <xref:System.Windows.Markup.WhitespaceSignificantCollectionAttribute>Gibt an, dass ein Auflistungstyp als von einem XAML-Prozessor signifikanter Leerraum verarbeitet werden soll, der sich auf die Konstruktion der Wert Knoten des XAML-knotenstreams in der Auflistung auswirkt. Weitere Informationen finden Sie unter [Leerraum Verarbeitung in XAML](whitespace-processing-in-xaml.md).  
  
### <a name="xamldeferloadattribute"></a>XamlDeferLoadAttribute  
 **Referenz Dokumentation:**  <xref:System.Windows.Markup.XamlDeferLoadAttribute>  
  
 **Gilt für:** -Klasse,-Eigenschaft.  
  
 **Argumentation** Unterstützt zwei Zuweisungs Formular Typen als Zeichen folgen oder <xref:System.Type>Typen als. Siehe <xref:System.Windows.Markup.XamlDeferLoadAttribute>.  
  
 Gibt an, dass eine Klasse oder Eigenschaft eine verzögerte Lade Verwendung für XAML (z. b. ein Vorlagen Verhalten) aufweist, und meldet die Klasse, die das Verzögerungs Verhalten und den Ziel-/Inhaltstyp ermöglicht.  
  
### <a name="xamlsetmarkupextensionattribute"></a>XamlSetMarkupExtensionAttribute  
 **Referenz Dokumentation:**  <xref:System.Windows.Markup.XamlSetMarkupExtensionAttribute>  
  
 **Gilt für:** Klasse  
  
 **Argumentation** Benennt den Rückruf.  
  
 Gibt an, dass eine Klasse eine Markup Erweiterung verwenden kann, um einen Wert für eine oder mehrere Eigenschaften bereitzustellen, und verweist auf einen Handler, der von einem XAML-Writer aufgerufen werden soll, bevor ein Markup Erweiterungs Satz-Vorgang für eine beliebige Eigenschaft der Klasse durchgeführt wird.  
  
### <a name="xamlsettypeconverterattribute"></a>XamlSetTypeConverterAttribute  
 **Referenz Dokumentation:**  <xref:System.Windows.Markup.XamlSetTypeConverterAttribute>  
  
 **Gilt für:** Klasse  
  
 **Argumentation** Benennt den Rückruf.  
  
 Gibt an, dass eine Klasse einen Typkonverter verwenden kann, um einen Wert für eine oder mehrere Eigenschaften bereitzustellen, und verweist auf einen Handler, der von einem XAML-Writer aufgerufen werden soll, bevor ein typkonverterset-Vorgang für eine beliebige Eigenschaft der Klasse durchgeführt wird.  
  
### <a name="xmllangpropertyattribute"></a>XmlLangPropertyAttribute  
 **Referenz Dokumentation:**  <xref:System.Windows.Markup.XmlLangPropertyAttribute>  
  
 **Gilt für:** Klasse  
  
 **Argumentation** Eine Zeichenfolge, die den Namen der Eigenschaft angibt, die `xml:lang` für den attributierten Typ als Alias angegeben wird.  
  
 <xref:System.Windows.Markup.XmlLangPropertyAttribute>meldet eine Eigenschaft des attributierten Typs, der der XML `lang` -Direktive zugeordnet wird. Die-Eigenschaft ist nicht notwendigerweise vom <xref:System.String>Typ, muss jedoch von einer Zeichenfolge zugewiesen werden können (Dies kann durch Zuordnen eines Typkonverters zum Eigenschaftentyp oder mit der spezifischen Eigenschaft erreicht werden). Die-Eigenschaft muss Lese-/Schreibzugriff aufweisen.  
  
 Das Szenario für die `xml:lang` Zuordnung besteht darin, dass ein Laufzeitobjekt Modell auf XML-spezifische Sprachinformationen zugreifen kann, ohne dass eine spezielle Verarbeitung mit einem XMLDOM erfolgt.  
  
 Die Definition erbt alle abgeleiteten Typen, die dem definierenden Typ zugewiesen werden können. Sie können die Definition für einen bestimmten abgeleiteten Typ überschreiben <xref:System.Windows.Markup.XmlLangPropertyAttribute> , indem Sie auf den spezifischen abgeleiteten Typ anwenden, obwohl dies ein ungewöhnliches Szenario ist.  
  
## <a name="xaml-related-clr-attributes-at-the-assembly-level"></a>XAML-bezogene CLR-Attribute auf Assemblyebene  
 In den folgenden Abschnitten werden die XAML-bezogenen Attribute beschrieben, die nicht auf Typen oder Element Definitionen angewendet werden, sondern stattdessen auf Assemblys angewendet werden. Diese Attribute sind für das Gesamtziel definiert, eine Bibliothek zu definieren, die benutzerdefinierte Typen enthält, die in XAML verwendet werden sollen. Einige der Attribute beeinflussen den XAML-knotenstream nicht unbedingt direkt, sondern werden im knotenstream weitergegeben, damit andere Consumer Sie verwenden können. Consumer der Informationen umfassen Entwurfs Umgebungen oder Serialisierungsprozesse, die XAML-Namespace Informationen und zugehörige Präfix Informationen benötigen. Ein XAML-Schema Kontext (einschließlich der standardmäßigen .NET Framework XAML-Dienste) verwendet diese Informationen ebenfalls.  
  
### <a name="xmlnscompatiblewithattribute"></a>XmlnsCompatibleWithAttribute  
 **Referenz Dokumentation:**  <xref:System.Windows.Markup.XmlnsCompatibleWithAttribute>  
  
 **Argumentation**  
  
- Eine Zeichenfolge, die den Bezeichner des zu unter suschenden XAML-Namespace angibt.  
  
- Eine Zeichenfolge, die den Bezeichner des XAML-Namespace angibt, der den XAML-Namespace aus dem vorherigen Argument unterteilen kann.  
  
 <xref:System.Windows.Markup.XmlnsCompatibleWithAttribute>Gibt an, dass ein XAML-Namespace von einem anderen XAML-Namespace subsudiert werden kann. In der Regel wird der zusammenfassende XAML-Namespace in einem zuvor definierten <xref:System.Windows.Markup.XmlnsDefinitionAttribute> angegeben. Diese Technik kann für die Versionierung eines XAML-Vokabulars in einer Bibliothek verwendet werden, um die Kompatibilität mit dem zuvor definierten Markup anhand des vorherigen vokabularvokabulars herzustellen.  
  
### <a name="xmlnsdefinitionattribute"></a>XmlnsDefinitionAttribute  
 **Referenz Dokumentation:**  <xref:System.Windows.Markup.XmlnsDefinitionAttribute>  
  
 **Argumentation**  
  
- Eine Zeichenfolge, die den Bezeichner des zu definierenden XAML-Namespace angibt.  
  
- Eine Zeichenfolge, die einen CLR-Namespace benennt. Der CLR-Namespace sollte öffentliche Typen in der Assembly definieren, und mindestens einer der CLR-Namespace Typen sollte für die XAML-Verwendung vorgesehen sein.  
  
 <xref:System.Windows.Markup.XmlnsDefinitionAttribute>gibt eine Zuordnung pro Assembly zwischen einem XAML-Namespace und einem CLR-Namespace an, der dann für die Typauflösung durch einen XAML-objektwriter oder XAML-Schema Kontext verwendet wird.  
  
 <xref:System.Windows.Markup.XmlnsDefinitionAttribute> Es können mehrere auf eine Assembly angewendet werden. Dies kann aus einer beliebigen Kombination aus den folgenden Gründen erfolgen:  
  
- Der Bibliotheks Entwurf enthält mehrere CLR-Namespaces für die logische Organisation des Laufzeit-API-Zugriffs. Allerdings möchten Sie, dass alle Typen in diesen Namespaces XAML-verwendbar sind, indem Sie auf denselben XAML-Namespace verweisen. In diesem Fall wenden Sie mehrere <xref:System.Windows.Markup.XmlnsDefinitionAttribute> Attribute mit demselben <xref:System.Windows.Markup.XmlnsDefinitionAttribute.XmlNamespace%2A> Wert an, aber unter <xref:System.Windows.Markup.XmlnsDefinitionAttribute.ClrNamespace%2A> schiedliche Werte. Dies ist besonders nützlich, wenn Sie Zuordnungen für den XAML-Namespace definieren, dass Ihr Framework oder Ihre Anwendung als standardmäßiger XAML-Namespace bei allgemeiner Verwendung festgelegt ist.  
  
- Der Bibliotheks Entwurf enthält mehrere CLR-Namespaces, und Sie möchten eine bewusste XAML-Namespace Trennung zwischen der Verwendung von Typen in diesen CLR-Namespaces.  
  
- Sie definieren einen CLR-Namespace in der Assembly, und Sie möchten über mehr als einen XAML-Namespace darauf zugreifen können. Dieses Szenario tritt auf, wenn Sie mehrere vokabare mit derselben CodeBase unterstützen.  
  
- Sie definieren die XAML-Sprachunterstützung in einem oder mehreren CLR-Namespaces. Dafür sollte der <xref:System.Windows.Markup.XmlnsDefinitionAttribute.XmlNamespace%2A> Wert lauten `http://schemas.microsoft.com/winfx/2006/xaml`.  
  
### <a name="xmlnsprefixattribute"></a>XmlnsPrefixAttribute  
 **Referenz Dokumentation:**  <xref:System.Windows.Markup.XmlnsPrefixAttribute>  
  
 **Argumentation**  
  
- Eine Zeichenfolge, die den Bezeichner eines XAML-Namespace angibt.  
  
- Eine Zeichenfolge, die das empfohlene Präfix angibt.  
  
 <xref:System.Windows.Markup.XmlnsDefinitionAttribute>Gibt ein empfohlenes Präfix für einen XAML-Namespace an. Das Präfix ist nützlich, wenn Elemente und Attribute in eine XAML-Datei geschrieben werden, die von den .NET Framework XAML-Diensten <xref:System.Xaml.XamlXmlWriter>serialisiert wird, oder wenn eine XAML-implementierende Bibliothek mit einer Entwurfs Umgebung interagiert, die über XAML-Bearbeitungsfunktionen verfügt.  
  
 <xref:System.Windows.Markup.XmlnsPrefixAttribute> Es können mehrere auf eine Assembly angewendet werden. Dies kann aus einer beliebigen Kombination aus den folgenden Gründen erfolgen:  
  
- Die Assembly definiert Typen für mehr als einen XAML-Namespace. In diesem Fall sollten Sie für jeden XAML-Namespace unterschiedliche Präfix Werte definieren.  
  
- Sie unterstützen mehrere Vokabulare, und für jedes Vokabular und jeden XAML-Namespace werden unterschiedliche Präfixe verwendet.  
  
- Sie definieren die XAML-Sprachunterstützung in der Assembly und <xref:System.Windows.Markup.XmlnsDefinitionAttribute> verfügen `http://schemas.microsoft.com/winfx/2006/xaml`über eine für. In diesem Fall sollten Sie das Präfix `x`in der Regel höher stufen.  
  
> [!NOTE]
>  .NET Framework XAML-Dienste definieren auch das XAML-bezogene <xref:System.Windows.Markup.RootNamespaceAttribute>Attribut. Dieses Attribut ist ein Attribut auf Assemblyebene für die Unterstützung von Project System und ist für benutzerdefinierte XAML-Typen nicht relevant.  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Attribute>
- [Definieren von benutzerdefinierten Typen für die Verwendung mit .NET Framework-XAML-Diensten](defining-custom-types-for-use-with-net-framework-xaml-services.md)
