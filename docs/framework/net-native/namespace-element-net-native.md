---
title: "&lt;Namespace&gt; Element (.NET Native) | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 57c614e5-18a9-4e87-bfd5-d0fe3396a192
caps.latest.revision: 20
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 20
---
# &lt;Namespace&gt; Element (.NET Native)
Wendet die Laufzeitreflektionsrichtlinie auf alle Typen in einem angegebenen Namespace an.  
  
## <a name="syntax"></a>Syntax  
  
```xml  
  
<Namespace Name="namespace_name"   
           Activate="policy_type"   
           Browse="policy_type" />  
           Dynamic="policy_setting"  
           Serialize="policy_setting"  
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
|`Name`|Allgemein|Erforderliches Attribut. Gibt den Namen des Namespace an.|  
|`Activate`|Spiegelung|Optionales Attribut. Steuert den Laufzeitzugriff auf Konstruktoren, um die Aktivierung von Instanzen zu ermöglichen.|  
|`Browse`|Spiegelung|Optionales Attribut. Steuert das Abfragen von Informationen über Programmelemente, ermöglicht jedoch keinen Laufzeitzugriff.|  
|`Dynamic`|Spiegelung|Optionales Attribut. Steuert den Laufzeitzugriff auf alle Typmember, einschließlich Konstruktoren, Methoden, Felder, Eigenschaften und Ereignisse, um die dynamische Programmierung zu ermöglichen.|  
|`Serialize`|Serialisierung|Optionales Attribut. Steuert den Laufzeitzugriff auf Konstruktoren, Felder und Eigenschaften, um Serialisierung und Deserialisierung von Typinstanzen durch Bibliotheken wie das Newtonsoft JSON-Serialisierungsprogramm zu ermöglichen.|  
|`DataContractSerializer`|Serialisierung|Optionales Attribut. Steuert die Richtlinie für die Serialisierung, die mithilfe der <xref:System.Runtime.Serialization.DataContractSerializer?displayProperty=fullName> Klasse.|  
|`DataContractJsonSerializer`|Serialisierung|Optionales Attribut. Steuert die Richtlinie für die JSON-Serialisierung verwendet die <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer?displayProperty=fullName> Klasse.|  
|`XmlSerializer`|Serialisierung|Optionales Attribut. Steuert die Richtlinie für die XML-Serialisierung, die verwendet die <xref:System.Xml.Serialization.XmlSerializer?displayProperty=fullName> Klasse.|  
|`MarshalObject`|Interop|Optionales Attribut. Steuert die Richtlinie für das Marshalling von Verweistypen zu Windows-Runtime und COM.|  
|`MarshalDelegate`|Interop|Optionales Attribut. Steuert die Richtlinie für das Marshalling von Delegattypen als Funktionszeiger zu systemeigenem Code.|  
|`MarshalStructure`|Interop|Optionales Attribut. Steuert die Richtlinie für das Marshalling von Strukturen zu systemeigenem Code.|  
  
## <a name="name-attribute"></a>Namensattribut  
  
|Wert|Beschreibung|  
|-----------|-----------------|  
|*namespace_name*|Der Namespacename. Wenn die <> \> Element ist ein untergeordnetes Element des ein [ <> \</> \> ](../../../docs/framework/net-native/application-element-net-native.md), [ <> \</> \> ](../../../docs/framework/net-native/library-element-net-native.md), oder [ <> \> ](../../../docs/framework/net-native/assembly-element-net-native.md) Element *Namespace_name* muss ein vollqualifizierter Namespacename sein. Wenn die <> \> Element ist ein untergeordnetes Element eines anderen <> \> Element *Namespace_name* muss ein relativer Namespacename sein.|  
  
## <a name="all-other-attributes"></a>Alle anderen Attribute  
  
|Wert|Beschreibung|  
|-----------|-----------------|  
|*policy_setting*|Die Einstellung, die auf diesen Richtlinientyp für alle Typen im Namespace angewendet werden soll. Mögliche Werte sind `All`, `Auto`, `Excluded`, `Public`, `PublicAndInternal`, `Required Public`, `Required PublicAndInternal` und `Required All`. Weitere Informationen finden Sie unter [Laufzeitrichtlinieneinstellungen der Richtlinie](../../../docs/framework/net-native/runtime-directive-policy-settings.md).|  
  
### <a name="child-elements"></a>Untergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|`<Namespace>`|Wendet die Laufzeitreflektionsrichtlinie auf alle Typen in einem übergeordneten Namespace an.|  
|[<>\>](../../../docs/framework/net-native/type-element-net-native.md)|Wendet die Reflektionsrichtlinie auf einen Typ an.|  
|[<>\>](../../../docs/framework/net-native/typeinstantiation-element-net-native.md)|Wendet die Reflektionsrichtlinie auf einen konstruierten generischen Typ an.|  
  
### <a name="parent-elements"></a>Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|[<>\>](../../../docs/framework/net-native/application-element-net-native.md)|Dient als Container für anwendungsweite Typen und Typmember, deren Metadaten zur Laufzeit für die Reflektion verfügbar sind. Die [ <> \> ](../../../docs/framework/net-native/application-element-net-native.md) Element können&0; (null), ein oder mehrere [ <> \> ](../../../docs/framework/net-native/assembly-element-net-native.md) Elemente.|  
|[<>\>](../../../docs/framework/net-native/assembly-element-net-native.md)|Wendet die Laufzeitreflektionsrichtlinie auf alle Typen in einer angegebenen Assembly an.|  
|[<>\>](../../../docs/framework/net-native/library-element-net-native.md)|Definiert die Assembly, die Typen und Typmember enthält, deren Metadaten zur Laufzeit für die Reflektion verfügbar sind. Die [ <> \> ](../../../docs/framework/net-native/library-element-net-native.md) Element können&0; (null) oder eine [ <> \> ](../../../docs/framework/net-native/assembly-element-net-native.md) Element.|  
|`<Namespace>`|Wendet die Reflektionsrichtlinie auf alle Typen in einem übergeordneten Namespace an.|  
  
## <a name="remarks"></a>Hinweise  
 Die Attribute `Activate`, `Browse`, `Dynamic` und `Serialize` sind optional. Wenn keine vorhanden sind, dient das `<Namespace>`-Element nur als Container für untergeordnete Elemente. Wenn sie vorhanden sind, wendet das `<Namespace>`-Element eine Laufzeitreflektionsrichtlinie auf alle Typen im angegebenen Namespace an.  
  
 Wann ist das ein untergeordnetes Element des der [ <> \> ](../../../docs/framework/net-native/assembly-element-net-native.md) -Element, die `<Namespace>` -Element überschreibt die laufzeitreflektionsrichtlinie definiert die [ <> \> ](../../../docs/framework/net-native/assembly-element-net-native.md) Element.  
  
## <a name="see-also"></a>Siehe auch  
 [Richtlinie für die Laufzeitrichtlinie](../../../docs/framework/net-native/runtime-directive-policy-settings.md)   
 [Laufzeit-Konfigurationsdatei Laufzeitdirektiven (rd.xml) Referenz](../../../docs/framework/net-native/runtime-directives-rd-xml-configuration-file-reference.md)   
 [Elemente der Laufzeitrichtlinie](../../../docs/framework/net-native/runtime-directive-elements.md)