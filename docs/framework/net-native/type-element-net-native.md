---
title: <Type> (Element (.NET Native)
ms.date: 03/30/2017
ms.assetid: 1e88d368-a886-4f1e-8eb6-6127979a9fce
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: a92e6627ba937b10b183a833a005792f0a51f921
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59162697"
---
# <a name="type-element-net-native"></a>\<Typ > (Element (.NET Native)
Wendet eine Laufzeitrichtlinie auf einen bestimmten Typ an, z. B. eine Klasse oder Struktur.  
  
## <a name="syntax"></a>Syntax  
  
```xml  
<Type Name="type_name"  
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
  
|Attribut|Attributtyp|Beschreibung|  
|---------------|--------------------|-----------------|  
|`Name`|Allgemein|Erforderliches Attribut. Gibt den Typnamen an.|  
|`Activate`|Spiegelung|Optionales Attribut. Steuert den Laufzeitzugriff auf Konstruktoren, um die Aktivierung von Instanzen zu ermöglichen.|  
|`Browse`|Spiegelung|Optionales Attribut. Steuert das Abfragen von Informationen über Programmelemente, ermöglicht jedoch keinen Laufzeitzugriff.|  
|`Dynamic`|Spiegelung|Optionales Attribut. Steuert den Laufzeitzugriff auf alle Typmember, einschließlich Konstruktoren, Methoden, Felder, Eigenschaften und Ereignisse, um die dynamische Programmierung zu ermöglichen.|  
|`Serialize`|Serialisierung|Optionales Attribut. Steuert den Laufzeitzugriff auf Konstruktoren, Felder und Eigenschaften, um Serialisierung und Deserialisierung von Typinstanzen durch Bibliotheken wie das Newtonsoft JSON-Serialisierungsprogramm zu ermöglichen.|  
|`DataContractSerializer`|Serialisierung|Optionales Attribut. Steuert die Richtlinie für die Serialisierung, die die <xref:System.Runtime.Serialization.DataContractSerializer?displayProperty=nameWithType>-Klasse verwendet.|  
|`DataContractJsonSerializer`|Serialisierung|Optionales Attribut. Steuert die Richtlinie für die JSON-Serialisierung, die die <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer?displayProperty=nameWithType>-Klasse verwendet.|  
|`XmlSerializer`|Serialisierung|Optionales Attribut. Steuert die Richtlinie für die XML-Serialisierung, die die <xref:System.Xml.Serialization.XmlSerializer?displayProperty=nameWithType>-Klasse verwendet.|  
|`MarshalObject`|Interop|Optionales Attribut. Steuert die Richtlinie für das Marshalling von Verweistypen zu Windows-Runtime und COM.|  
|`MarshalDelegate`|Interop|Optionales Attribut. Steuert die Richtlinie für das Marshalling von Delegattypen als Funktionszeiger zu systemeigenem Code.|  
|`MarshalStructure`|Interop|Optionales Attribut. Steuert die Richtlinie für das Marshalling von Werttypen zu systemeigenem Code.|  
  
## <a name="name-attribute"></a>Namensattribut  
  
|Wert|Beschreibung|  
|-----------|-----------------|  
|*type_name*|Der Typname. Ist dieses `<Type>`-Element das untergeordnete Element eines [\<Namespace>](../../../docs/framework/net-native/namespace-element-net-native.md)-Elements oder eines anderen `<Type>`-Elements, kann *type_name* den Namen des Typs ohne den Namespace enthalten. Andernfalls muss *type_name* den vollqualifizierten Typnamen enthalten.|  
  
## <a name="all-other-attributes"></a>Alle anderen Attribute  
  
|Wert|Beschreibung|  
|-----------|-----------------|  
|*policy_setting*|Die Einstellung, die auf diesen Richtlinientyp angewendet werden soll. Mögliche Werte sind `All`, `Auto`, `Excluded`, `Public`, `PublicAndInternal`, `Required Public`, `Required PublicAndInternal` und `Required All`. Weitere Informationen finden Sie unter [Richtlinieneinstellungen für die Laufzeitanweisung](../../../docs/framework/net-native/runtime-directive-policy-settings.md).|  
  
### <a name="child-elements"></a>Untergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|[\<AttributeImplies>](../../../docs/framework/net-native/attributeimplies-element-net-native.md)|Wenn der enthaltende Typ ein Attribut ist, wird die Laufzeitrichtlinie für Codeelemente definiert, auf die das Attribut angewendet wird.|  
|[\<Event>](../../../docs/framework/net-native/event-element-net-native.md)|Wendet die Reflektionsrichtlinie auf ein Ereignis dieses Typs an.|  
|[\<Field>](../../../docs/framework/net-native/field-element-net-native.md)|Wendet die Reflektionsrichtlinie auf ein Feld dieses Typs an.|  
|[\<GenericParameter>](../../../docs/framework/net-native/genericparameter-element-net-native.md)|Wendet eine Richtlinie auf den Parametertyp eines generischen Typs an.|  
|[\<ImpliesType>](../../../docs/framework/net-native/impliestype-element-net-native.md)|Wendet eine Richtlinie auf einen Typ an, wenn diese Richtlinie an den Typ angewendet wurde, der vom enthaltenden `<Type>`-Element dargestellt wird.|  
|[\<Method>](../../../docs/framework/net-native/method-element-net-native.md)|Wendet die Reflektionsrichtlinie auf eine Methode dieses Typs an.|  
|[\<MethodInstantiation>](../../../docs/framework/net-native/methodinstantiation-element-net-native.md)|Wendet die Reflektionsrichtlinie auf eine konstruierte generische Methode dieses Typs an.|  
|[\<Property>](../../../docs/framework/net-native/property-element-net-native.md)|Wendet die Reflektionsrichtlinie auf eine Eigenschaft dieses Typs an.|  
|[\<Subtypes>](../../../docs/framework/net-native/subtypes-element-net-native.md)|Wendet eine Laufzeitrichtlinie auf alle vom enthaltenden Typ geerbten Klassen an.|  
|`<Type>`|Wendet die Reflektionsrichtlinie auf einen geschachtelten Typ an.|  
|[\<TypeInstantiation>](../../../docs/framework/net-native/typeinstantiation-element-net-native.md)|Wendet die Reflektionsrichtlinie auf einen konstruierten generischen Typ an.|  
  
### <a name="parent-elements"></a>Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|[\<Application>](../../../docs/framework/net-native/application-element-net-native.md)|Dient als Container für anwendungsweite Typen und Typmember, deren Metadaten zur Laufzeit für die Reflektion verfügbar sind.|  
|[\<Assembly>](../../../docs/framework/net-native/assembly-element-net-native.md)|Wendet die Reflektionsrichtlinie auf alle Typen in einer angegebenen Assembly an.|  
|[\<Library>](../../../docs/framework/net-native/library-element-net-native.md)|Definiert die Assembly, die Typen und Typmember enthält, deren Metadaten zur Laufzeit für die Reflektion verfügbar sind.|  
|[\<Namespace>](../../../docs/framework/net-native/namespace-element-net-native.md)|Wendet die Reflektionsrichtlinie auf alle Typen in einem Namespace an.|  
|`<Type>`|Wendet die Reflektionsrichtlinie auf einen Typ und alle seine Member an.|  
|[\<TypeInstantiation>](../../../docs/framework/net-native/typeinstantiation-element-net-native.md)|Wendet die Reflektionsrichtlinie auf einen konstruierten generischen Typ und alle seine Member an.|  
  
## <a name="remarks"></a>Hinweise  
 Die Reflektions-, Serialisierungs- und Interop-Attribute sind optional. Wenn keine vorhanden sind, dient das `<Type>`-Element als Container, dessen untergeordneten Typen Richtlinie für einzelne Member definieren.  
  
 Wenn ein `<Type>`-Element das untergeordnete Element eines [\<Assembly>](../../../docs/framework/net-native/assembly-element-net-native.md)-, [\<Namespace>](../../../docs/framework/net-native/namespace-element-net-native.md)-, `<Type>`- oder [\<TypeInstantiation>](../../../docs/framework/net-native/typeinstantiation-element-net-native.md)-Elements ist, setzt es die Richtlinieneinstellungen, die vom übergeordneten Element definiert werden, außer Kraft.  
  
 Ein `<Type>`-Element eines generischen Typs wendet seine Richtlinie auf alle Instanziierungen an, die keine eigene Richtlinie haben. Die Richtlinie der konstruierten generischen Typen wird durch das [\<TypeInstantiation>](../../../docs/framework/net-native/typeinstantiation-element-net-native.md)-Element definiert.  
  
 Wenn der Typ ein generischer Typ ist, wird sein Name mit einem Gravis-Akzentsymbol (\`) gefolgt von der Anzahl der generischen Parameter versehen. Das `Name`-Attribut eines `<Type>`-Elements wird für die <xref:System.Collections.Generic.List%601?displayProperty=nameWithType>-Klasse beispielsweise als ``Name="System.Collections.Generic.List`1"`` angezeigt.
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird Reflektion zum Anzeigen von Informationen zu den Feldern, Eigenschaften und Methoden der <xref:System.Collections.Generic.List%601?displayProperty=nameWithType>-Klasse verwendet. Die Variable `b` in diesem Beispiel ist eine <xref:Windows.UI.Xaml.Controls.TextBlock> Steuerelement. Da im Beispiel einfach Typinformationen abgerufen werden, wird die Verfügbarkeit von Metadaten über die `Browse`-Richtlinieneinstellung gesteuert.  
  
 [!code-csharp[ProjectN_Reflection#3](../../../samples/snippets/csharp/VS_Snippets_CLR/projectn_reflection/cs/browsegenerictype1.cs#3)]  
  
 Da Metadaten für die <xref:System.Collections.Generic.List%601>-Klasse nicht automatisch von der [!INCLUDE[net_native](../../../includes/net-native-md.md)]-Toolkette eingeschlossen werden, können im Beispiel keine angeforderten Memberinformationen zur Laufzeit angezeigt werden. Um die erforderlichen Metadaten bereitzustellen, fügen Sie das folgende `<Type>`-Element der Laufzeitanweisungsdatei hinzu. Beachten Sie, dass wir, da wir ein übergeordnetes [<Namespace\>](../../../docs/framework/net-native/namespace-element-net-native.md)-Element bereitgestellt haben, keinen vollqualifizierten Typnamen im `<Type>`-Element bereitstellen müssen.  
  
```xml  
<Directives xmlns="http://schemas.microsoft.com/netfx/2013/01/metadata">  
   <Application>  
      <Assembly Name="*Application*" Dynamic="Required All" />  
      <Namespace Name ="System.Collections.Generic" >  
        <Type Name="List`1" Browse="Required All" />   
     </Namespace>  
   </Application>  
</Directives>  
```  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird Reflektion zum Abrufen eines <xref:System.Reflection.PropertyInfo>-Objekts verwendet, das die <xref:System.String.Chars%2A?displayProperty=nameWithType>-Eigenschaft darstellt. Anschließend wird mithilfe der <xref:System.Reflection.PropertyInfo.GetValue%28System.Object%2CSystem.Object%5B%5D%29?displayProperty=nameWithType>-Methode der Wert des siebten Zeichens in einer Zeichenfolge abgerufen, und alle Zeichen in der Zeichenfolge werden angezeigt. Die Variable `b` in diesem Beispiel ist eine <xref:Windows.UI.Xaml.Controls.TextBlock> Steuerelement.  
  
 [!code-csharp[ProjectN_Reflection#1](../../../samples/snippets/csharp/VS_Snippets_CLR/projectn_reflection/cs/propertyinfo1.cs#1)]  
  
 Da keine Metdaten für das <xref:System.String>-Objekt verfügbar sind, löst der Aufruf der <xref:System.Reflection.PropertyInfo.GetValue%28System.Object%2CSystem.Object%5B%5D%29?displayProperty=nameWithType>-Methode eine <xref:System.NullReferenceException>-Ausnahme zur Laufzeit aus, wenn die Kompilierung mit der [!INCLUDE[net_native](../../../includes/net-native-md.md)]-Toolkette erfolgt. Fügen Sie folgendes `<Type>`-Element zur Laufzeitanweisungsdatei hinzu, um die Ausnahme zu eliminieren und die erforderlichen Metadaten bereitzustellen:  
  
```xml  
<Directives xmlns="http://schemas.microsoft.com/netfx/2013/01/metadata">  
  <Application>  
    <Assembly Name="*Application*" Dynamic="Required All" />  
    <Type Name="System.String" Dynamic="Required Public"/> -->  
  </Application>  
</Directives>  
```  
  
## <a name="see-also"></a>Siehe auch

- [Runtime Directives (rd.xml) Configuration File Reference (Referenz zur Laufzeitanweisungs-Konfigurationsdatei (rd.xml))](../../../docs/framework/net-native/runtime-directives-rd-xml-configuration-file-reference.md)
- [Elemente der Laufzeitanweisung](../../../docs/framework/net-native/runtime-directive-elements.md)
- [Richtlinieneinstellungen für die Laufzeitanweisung](../../../docs/framework/net-native/runtime-directive-policy-settings.md)
