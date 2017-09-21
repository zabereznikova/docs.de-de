---
title: '&lt;Namespace&gt; Element (.NET Native)'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 57c614e5-18a9-4e87-bfd5-d0fe3396a192
caps.latest.revision: 20
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: f92797e9c06762602c30d7c3ed8e6b0d6e579bbf
ms.contentlocale: de-de
ms.lasthandoff: 08/21/2017

---
# <a name="ltnamespacegt-element-net-native"></a>&lt;Namespace&gt; Element (.NET Native)
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
|`DataContractSerializer`|Serialisierung|Optionales Attribut. Steuert die Richtlinie für die Serialisierung, die die <xref:System.Runtime.Serialization.DataContractSerializer?displayProperty=fullName>-Klasse verwendet.|  
|`DataContractJsonSerializer`|Serialisierung|Optionales Attribut. Steuert die Richtlinie für die JSON-Serialisierung, die die <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer?displayProperty=fullName>-Klasse verwendet.|  
|`XmlSerializer`|Serialisierung|Optionales Attribut. Steuert die Richtlinie für die XML-Serialisierung, die die <xref:System.Xml.Serialization.XmlSerializer?displayProperty=fullName>-Klasse verwendet.|  
|`MarshalObject`|Interop|Optionales Attribut. Steuert die Richtlinie für das Marshalling von Verweistypen zu Windows-Runtime und COM.|  
|`MarshalDelegate`|Interop|Optionales Attribut. Steuert die Richtlinie für das Marshalling von Delegattypen als Funktionszeiger zu systemeigenem Code.|  
|`MarshalStructure`|Interop|Optionales Attribut. Steuert die Richtlinie für das Marshalling von Strukturen zu systemeigenem Code.|  
  
## <a name="name-attribute"></a>Namensattribut  
  
|Wert|Beschreibung|  
|-----------|-----------------|  
|*namespace_name*|Der Namespacename. Wenn das \<Namespace>-Element ein untergeordnetes Element des [\<Application>](../../../docs/framework/net-native/application-element-net-native.md), [\<Library>](../../../docs/framework/net-native/library-element-net-native.md)- oder [\<Assembly>](../../../docs/framework/net-native/assembly-element-net-native.md)-Elements ist, muss *namespace_name* ein vollqualifizierter Namespacename sein. Wenn das \<Namespace>-Element ein untergeordnetes Element eines anderen \<Namespace>-Elements ist, muss *namespace_name* ein relativer Namespacename sein.|  
  
## <a name="all-other-attributes"></a>Alle anderen Attribute  
  
|Wert|Beschreibung|  
|-----------|-----------------|  
|*policy_setting*|Die Einstellung, die auf diesen Richtlinientyp für alle Typen im Namespace angewendet werden soll. Mögliche Werte sind `All`, `Auto`, `Excluded`, `Public`, `PublicAndInternal`, `Required Public`, `Required PublicAndInternal` und `Required All`. Weitere Informationen finden Sie unter [Richtlinieneinstellungen für die Laufzeitanweisung](../../../docs/framework/net-native/runtime-directive-policy-settings.md).|  
  
### <a name="child-elements"></a>Untergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|`<Namespace>`|Wendet die Laufzeitreflektionsrichtlinie auf alle Typen in einem übergeordneten Namespace an.|  
|[\<Type>](../../../docs/framework/net-native/type-element-net-native.md)|Wendet die Reflektionsrichtlinie auf einen Typ an.|  
|[\<TypeInstantiation>](../../../docs/framework/net-native/typeinstantiation-element-net-native.md)|Wendet die Reflektionsrichtlinie auf einen konstruierten generischen Typ an.|  
  
### <a name="parent-elements"></a>Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|[\<Application>](../../../docs/framework/net-native/application-element-net-native.md)|Dient als Container für anwendungsweite Typen und Typmember, deren Metadaten zur Laufzeit für die Reflektion verfügbar sind. Das [\<Application>](../../../docs/framework/net-native/application-element-net-native.md)-Element kann 0, ein oder mehrere [\<Assembly>](../../../docs/framework/net-native/assembly-element-net-native.md)-Elemente aufweisen.|  
|[\<Assembly>](../../../docs/framework/net-native/assembly-element-net-native.md)|Wendet die Laufzeitreflektionsrichtlinie auf alle Typen in einer angegebenen Assembly an.|  
|[\<Library>](../../../docs/framework/net-native/library-element-net-native.md)|Definiert die Assembly, die Typen und Typmember enthält, deren Metadaten zur Laufzeit für die Reflektion verfügbar sind. Das [\<Library>](../../../docs/framework/net-native/library-element-net-native.md)-Element kann 0 oder ein [\<Assembly>](../../../docs/framework/net-native/assembly-element-net-native.md)-Element aufweisen.|  
|`<Namespace>`|Wendet die Reflektionsrichtlinie auf alle Typen in einem übergeordneten Namespace an.|  
  
## <a name="remarks"></a>Hinweise  
 Die Attribute `Activate`, `Browse`, `Dynamic` und `Serialize` sind optional. Wenn keine vorhanden sind, dient das `<Namespace>`-Element nur als Container für untergeordnete Elemente. Wenn sie vorhanden sind, wendet das `<Namespace>`-Element eine Laufzeitreflektionsrichtlinie auf alle Typen im angegebenen Namespace an.  
  
 Wenn es sich um ein untergeordnetes Element des [\<Assembly>](../../../docs/framework/net-native/assembly-element-net-native.md)-Elements handelt, überschreibt das `<Namespace>`-Element die Laufzeitreflektionsrichtlinie, die vom [\<Assembly>](../../../docs/framework/net-native/assembly-element-net-native.md)-Element definiert wird.  
  
## <a name="see-also"></a>Siehe auch  
 [Richtlinieneinstellungen für die Laufzeitanweisung](../../../docs/framework/net-native/runtime-directive-policy-settings.md)   
 [Runtime Directives (rd.xml) Configuration File Reference (Verweis auf die Konfigurationsdatei der Laufzeitanweisungen (rd.xml))](../../../docs/framework/net-native/runtime-directives-rd-xml-configuration-file-reference.md)   
 [Runtime Directive Elements (Elemente der Laufzeitanweisung)](../../../docs/framework/net-native/runtime-directive-elements.md)

