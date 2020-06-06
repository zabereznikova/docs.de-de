---
title: <Namespace>-Element (.net Native)
ms.date: 03/30/2017
ms.assetid: 57c614e5-18a9-4e87-bfd5-d0fe3396a192
ms.openlocfilehash: 06d88a7b0f95c7c1dbe98818b847c92e08a57a19
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/06/2020
ms.locfileid: "79180958"
---
# <a name="namespace-element-net-native"></a>\<Namespace>-Element (.net Native)
Wendet die Laufzeitreflektionsrichtlinie auf alle Typen in einem angegebenen Namespace an.  
  
## <a name="syntax"></a>Syntax  
  
```xml  
<Namespace Name="namespace_name"
           Activate="policy_type"
           Browse="policy_type"  
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
  
|attribute|Attributtyp|BESCHREIBUNG|  
|---------------|--------------------|-----------------|  
|`Name`|Allgemein|Erforderliches Attribut. Gibt den Namen des Namespace an.|  
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
|*namespace_name*|Der Namespacename. Wenn das-Element ein untergeordnetes Element \<Namespace> eines-,-oder- [\<Application>](application-element-net-native.md) Elements ist [\<Library>](library-element-net-native.md) [\<Assembly>](assembly-element-net-native.md) , muss *namespace_name* ein voll qualifizierter Namespace Name sein. Wenn das \<Namespace> Element ein untergeordnetes Element eines anderen \<Namespace> Elements ist, muss *namespace_name* ein relativer Namespace Name sein.|  
  
## <a name="all-other-attributes"></a>Alle anderen Attribute  
  
|Wert|BESCHREIBUNG|  
|-----------|-----------------|  
|*policy_setting*|Die Einstellung, die auf diesen Richtlinientyp für alle Typen im Namespace angewendet werden soll. Mögliche Werte sind `All`, `Auto`, `Excluded`, `Public`, `PublicAndInternal`, `Required Public`, `Required PublicAndInternal` und `Required All`. Weitere Informationen finden Sie unter [Richtlinieneinstellungen für die Laufzeitanweisung](runtime-directive-policy-settings.md).|  
  
### <a name="child-elements"></a>Untergeordnete Elemente  
  
|Element|BESCHREIBUNG|  
|-------------|-----------------|  
|`<Namespace>`|Wendet die Laufzeitreflektionsrichtlinie auf alle Typen in einem übergeordneten Namespace an.|  
|[\<Type>](type-element-net-native.md)|Wendet die Reflektionsrichtlinie auf einen Typ an.|  
|[\<TypeInstantiation>](typeinstantiation-element-net-native.md)|Wendet die Reflektionsrichtlinie auf einen konstruierten generischen Typ an.|  
  
### <a name="parent-elements"></a>Übergeordnete Elemente  
  
|Element|BESCHREIBUNG|  
|-------------|-----------------|  
|[\<Application>](application-element-net-native.md)|Dient als Container für anwendungsweite Typen und Typmember, deren Metadaten zur Laufzeit für die Reflektion verfügbar sind. Das- [\<Application>](application-element-net-native.md) Element kann über 0 (null), ein oder mehrere- [\<Assembly>](assembly-element-net-native.md) Elemente verfügen.|  
|[\<Assembly>](assembly-element-net-native.md)|Wendet die Laufzeitreflektionsrichtlinie auf alle Typen in einer angegebenen Assembly an.|  
|[\<Library>](library-element-net-native.md)|Definiert die Assembly, die Typen und Typmember enthält, deren Metadaten zur Laufzeit für die Reflektion verfügbar sind. Das- [\<Library>](library-element-net-native.md) Element kann kein oder ein- [\<Assembly>](assembly-element-net-native.md) Element aufweisen.|  
|`<Namespace>`|Wendet die Reflektionsrichtlinie auf alle Typen in einem übergeordneten Namespace an.|  
  
## <a name="remarks"></a>Bemerkungen  
 Die Attribute `Activate`, `Browse`, `Dynamic` und `Serialize` sind optional. Wenn keine vorhanden sind, dient das `<Namespace>`-Element nur als Container für untergeordnete Elemente. Wenn sie vorhanden sind, wendet das `<Namespace>`-Element eine Laufzeitreflektionsrichtlinie auf alle Typen im angegebenen Namespace an.  
  
 Wenn es sich um ein untergeordnetes [\<Assembly>](assembly-element-net-native.md) Element des-Elements handelt, überschreibt das- `<Namespace>` Element die Lauf Zeit reflektionsrichtlinie, die vom- [\<Assembly>](assembly-element-net-native.md) Element  
  
## <a name="see-also"></a>Weitere Informationen

- [Richtlinieneinstellungen für die Laufzeitanweisung](runtime-directive-policy-settings.md)
- [Laufzeitanweisungs-Konfigurationsdatei (rd.xml) Referenz](runtime-directives-rd-xml-configuration-file-reference.md)
- [Elemente der Laufzeitanweisung](runtime-directive-elements.md)
