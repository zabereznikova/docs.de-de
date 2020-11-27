---
title: <TypeInstantiation> -Element (.net Native)
ms.date: 03/30/2017
ms.assetid: a5eada64-075b-4162-9655-ded84e4681f2
ms.openlocfilehash: a1db497762b3dc8c135154086d72fb3ac92ff5a4
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96250748"
---
# <a name="typeinstantiation-element-net-native"></a>\<TypeInstantiation> -Element (.net Native)

Wendet eine Laufzeitreflektionsrichtlinie auf einen konstruierten generischen Typ an.  
  
## <a name="syntax"></a>Syntax  
  
```xml  
<TypeInstantiation Name="type_name"  
                   Arguments="type_arguments"  
                   Activate="policy_type"  
                   Browse="policy_type"  
                   Dynamic="policy_type"  
                   Serialize="policy_type"  
                   DataContractSerializer="policy_setting"  
                   DataContractJsonSerializer="policy_setting"  
                   XmlSerializer="policy_setting"  
                   MarshalObject="policy_setting"  
                   MarshalDelegate="policy_setting"  
                   MarshalStructure="policy_setting" />  
```  
  
## <a name="attributes-and-elements"></a>Attribute und Elemente  

 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### <a name="attributes"></a>Attribute  
  
|Attribut|Attributtyp|BESCHREIBUNG|  
|---------------|--------------------|-----------------|  
|`Name`|Allgemein|Erforderliches Attribut. Gibt den Namen des Typs an|  
|`Arguments`|Allgemein|Erforderliches Attribut. Gibt die generischen Typargumente an. Wenn mehrere Argumente vorhanden sind, werden sie durch Kommas getrennt.|  
|`Activate`|Spiegelung|Optionales Attribut. Steuert den Laufzeitzugriff auf Konstruktoren, um die Aktivierung von Instanzen zu ermöglichen.|  
|`Browse`|Spiegelung|Optionales Attribut. Steuert das Abfragen von Informationen über Programmelemente, ermöglicht jedoch keinen Laufzeitzugriff.|  
|`Dynamic`|Spiegelung|Optionales Attribut. Steuert den Laufzeitzugriff auf alle Typmember, einschließlich Konstruktoren, Methoden, Felder, Eigenschaften und Ereignisse, um die dynamische Programmierung zu ermöglichen.|  
|`Serialize`|Serialisierung|Optionales Attribut. Steuert den Laufzeitzugriff auf Konstruktoren, Felder und Eigenschaften, um Serialisierung und Deserialisierung von Typinstanzen durch Bibliotheken wie das Newtonsoft JSON-Serialisierungsprogramm zu ermöglichen.|  
|`DataContractSerializer`|Serialisierung|Optionales Attribut. Steuert die Richtlinie für die Serialisierung, die die <xref:System.Runtime.Serialization.DataContractSerializer?displayProperty=nameWithType>-Klasse verwendet.|  
|`DataContractJsonSerializer`|Serialisierung|Optionales Attribut. Steuert die Richtlinie für die JSON-Serialisierung, die die <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer?displayProperty=nameWithType>-Klasse verwendet.|  
|`XmlSerializer`|Serialisierung|Optionales Attribut. Steuert die Richtlinie für die XML-Serialisierung, die die <xref:System.Xml.Serialization.XmlSerializer?displayProperty=nameWithType>-Klasse verwendet.|  
|`MarshalObject`|Interop|Optionales Attribut. Steuert die Richtlinie für das Marshalling von Verweistypen zu Windows-Runtime und COM.|  
|`MarshalDelegate`|Interop|Optionales Attribut. Steuert die Richtlinie für das Marshalling von Delegattypen als Funktionszeiger zu systemeigenem Code.|  
|`MarshalStructure`|Interop|Optionales Attribut. Steuert die Richtlinie für das Marshalling von Strukturen zu nativem Code.|  
  
## <a name="name-attribute"></a>Namensattribut  
  
|Wert|BESCHREIBUNG|  
|-----------|-----------------|  
|*type_name*|Der Typname. Wenn dieses `<TypeInstantiation>` Element das untergeordnete Element eines- [\<Namespace>](namespace-element-net-native.md) Elements, eines- [\<Type>](type-element-net-native.md) Elements oder eines anderen- `<TypeInstantiation>` Elements ist, können *TYPE_NAME* den Namen des Typs ohne den Namespace angeben. Andernfalls muss *type_name* den vollqualifizierten Typnamen enthalten. Der Typname wird nicht ergänzt. Für ein <xref:System.Collections.Generic.List%601?displayProperty=nameWithType>-Objekt könnte das `<TypeInstantiation>`-Element z. B. wie folgt aussehen:<br /><br /> `\<TypeInstantiation Name=System.Collections.Generic.List Dynamic="Required Public" />`|  
  
## <a name="arguments-attribute"></a>Arguments-Attribut  
  
|Wert|BESCHREIBUNG|  
|-----------|-----------------|  
|*type_argument*|Gibt die generischen Typargumente an. Wenn mehrere Argumente vorhanden sind, werden sie durch Kommas getrennt. Jedes Argument muss aus dem vollqualifizierten Typnamen bestehen.|  
  
## <a name="all-other-attributes"></a>Alle anderen Attribute  
  
|Wert|BESCHREIBUNG|  
|-----------|-----------------|  
|*policy_setting*|Die Einstellung, die auf diesen Richtlinientyp für den konstruierten generischen Typ anzuwenden ist. Mögliche Werte sind `All`, `Auto`, `Excluded`, `Public`, `PublicAndInternal`, `Required Public`, `Required PublicAndInternal` und `Required All`. Weitere Informationen finden Sie unter [Richtlinieneinstellungen für die Laufzeitanweisung](runtime-directive-policy-settings.md).|  
  
### <a name="child-elements"></a>Untergeordnete Elemente  
  
|Element|BESCHREIBUNG|  
|-------------|-----------------|  
|[\<Event>](event-element-net-native.md)|Wendet die Reflektionsrichtlinie auf ein Ereignis dieses Typs an.|  
|[\<Field>](field-element-net-native.md)|Wendet die Reflektionsrichtlinie auf ein Feld dieses Typs an.|  
|[\<ImpliesType>](impliestype-element-net-native.md)|Wendet eine Richtlinie auf einen Typ an, wenn diese Richtlinie an den Typ angewendet wurde, der vom enthaltenden `<TypeInstantiation>`-Element dargestellt wird.|  
|[\<Method>](method-element-net-native.md)|Wendet die Reflektionsrichtlinie auf eine Methode dieses Typs an.|  
|[\<MethodInstantiation>](methodinstantiation-element-net-native.md)|Wendet die Reflektionsrichtlinie auf eine konstruierte generische Methode dieses Typs an.|  
|[\<Property>](property-element-net-native.md)|Wendet die Reflektionsrichtlinie auf eine Eigenschaft dieses Typs an.|  
|[\<Type>](type-element-net-native.md)|Wendet die Reflektionsrichtlinie auf einen geschachtelten Typ an.|  
|`<TypeInstantiation>`|Wendet die Reflektionsrichtlinie auf einen geschachtelten konstruierten generischen Typ an.|  
  
### <a name="parent-elements"></a>Übergeordnete Elemente  
  
|Element|BESCHREIBUNG|  
|-------------|-----------------|  
|[\<Application>](application-element-net-native.md)|Dient als Container für anwendungsweite Typen und Typmember, deren Metadaten zur Laufzeit für die Reflektion verfügbar sind.|  
|[\<Assembly>](assembly-element-net-native.md)|Wendet die Reflektionsrichtlinie auf alle Typen in einer angegebenen Assembly an.|  
|[\<Library>](library-element-net-native.md)|Definiert die Assembly, die Typen und Typmember enthält, deren Metadaten zur Laufzeit für die Reflektion verfügbar sind.|  
|[\<Namespace>](namespace-element-net-native.md)|Wendet die Reflektionsrichtlinie auf alle Typen in einem Namespace an.|  
|[\<Type>](type-element-net-native.md)|Wendet die Reflektionsrichtlinie auf einen Typ und alle seine Member an.|  
|`<TypeInstantiation>`|Wendet die Reflektionsrichtlinie auf einen konstruierten generischen Typ und alle seine Member an.|  
  
## <a name="remarks"></a>Hinweise  

 Die Reflektions-, Serialisierungs- und Interop-Attribute sind optional. Allerdings muss mindestens eines vorhanden sein.  
  
 Wenn ein-Element ein untergeordnetes Element eines-,- `<TypeInstantiation>` [\<Assembly>](assembly-element-net-native.md) oder-Elements ist [\<Namespace>](namespace-element-net-native.md) [\<Type>](type-element-net-native.md) , überschreibt es die vom übergeordneten Element definierten Richtlinien Einstellungen. Wenn ein- [\<Type>](type-element-net-native.md) Element eine entsprechende generische Typdefinition definiert, überschreibt das- `<TypeInstantiation>` Element die Lauf Zeit reflektionsrichtlinie nur für Instanziierungen des angegebenen konstruierten generischen Typs.  
  
## <a name="example"></a>Beispiel  

 Im folgenden Beispiel wird Reflektion zum Abrufen der generischen Typdefinition von einem konstruierten <xref:System.Collections.Generic.Dictionary%602>-Objekt verwendet. Außerdem wird Reflektion zum Anzeigen von Informationen über <xref:System.Type>-Objekte verwendet, die konstruierte generische Typen und generische Typdefinitionen darstellen. Die Variable `b` im Beispiel ist ein- <xref:Windows.UI.Xaml.Controls.TextBlock> Steuerelement.  
  
 [!code-csharp[ProjectN_Reflection#2](../../../samples/snippets/csharp/VS_Snippets_CLR/projectn_reflection/cs/makegenerictype1.cs#2)]  
  
 Nach der Kompilierung mit der .net Native-Toolkette löst das Beispiel eine [MissingMetadataException](missingmetadataexception-class-net-native.md) -Ausnahme in der Zeile aus, die die- <xref:System.Type.GetGenericTypeDefinition%2A?displayProperty=nameWithType> Methode aufruft. Sie können die Ausnahme eliminieren und die erforderlichen Metadaten bereitstellen, indem Sie folgendes `<TypeInstantiation>`-Element in der Laufzeitanweisungsdatei hinzufügen:  
  
```xml  
<Directives xmlns="http://schemas.microsoft.com/netfx/2013/01/metadata">  
  <Application>  
    <Assembly Name="*Application*" Dynamic="Required All" />  
     <TypeInstantiation Name="System.Collections.Generic.Dictionary"  
                        Arguments="System.String,GenericType.Example"  
                        Dynamic="Required Public" />  
  </Application>  
</Directives>  
```  
  
## <a name="see-also"></a>Weitere Informationen

- [Laufzeitanweisungs-Konfigurationsdatei (rd.xml) Referenz](runtime-directives-rd-xml-configuration-file-reference.md)
- [Elemente der Laufzeitanweisung](runtime-directive-elements.md)
- [Richtlinieneinstellungen für die Laufzeitanweisung](runtime-directive-policy-settings.md)
