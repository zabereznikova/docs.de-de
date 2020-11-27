---
title: <Assembly> -Element (.net Native)
ms.date: 03/30/2017
ms.assetid: cfe629eb-1106-4113-86e1-052f402d8d8b
ms.openlocfilehash: 9d1556d8d414386d3f350a96396381bd7b66ffc5
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96251125"
---
# <a name="assembly-element-net-native"></a>\<Assembly> -Element (.net Native)

Wendet die Laufzeitreflektionsrichtlinie auf alle Typen in einer angegebenen Assembly an.  
  
## <a name="syntax"></a>Syntax  
  
```xml  
<Assembly Name="assembly_name"
          Activate="policy_setting"  
          Browse="policy_setting"  
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
  
|Attribut|Attributtyp|BESCHREIBUNG|  
|---------------|--------------------|-----------------|  
|`Name`|Allgemein|Erforderliches Attribut. Gibt den einfachen Namen einer Assembly an.|  
|`Activate`|Spiegelung|Optionales Attribut. Steuert den Laufzeitzugriff auf Konstruktoren, um die Aktivierung von Instanzen zu ermöglichen.|  
|`Browse`|Spiegelung|Optionales Attribut. Steuert das Abfragen nach Informationen über die Typen oder das Auflisten der Typen in der Assembly, aber ermöglicht keinen dynamischen Zugriff zur Laufzeit.|  
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
|*assembly_name*|Der einfache Name der Assembly ohne Dateierweiterung. Dieses Attribut entspricht der <xref:System.Reflection.AssemblyName.Name%2A?displayProperty=nameWithType>-Eigenschaft. Der Name einer Assembly namens Extensions.dll lautet beispielsweise "Extensions".<br /><br /> Sie können auch die Literalzeichenfolge `*Application*` angeben, um die Richtlinie auf alle Assemblys im App-Paket anzuwenden, egal, ob diese Assemblys geladen sind oder nicht. `*Application*` wendet die Richtlinie nie auf .NET Framework-Assemblys an.|  
  
## <a name="all-other-attributes"></a>Alle anderen Attribute  
  
|Wert|BESCHREIBUNG|  
|-----------|-----------------|  
|*policy_setting*|Die Einstellung, die auf diesen Richtlinientyp für alle Typen in der Assembly anzuwenden ist. Mögliche Werte sind `All`, `Auto`, `Excluded`, `Public`, `PublicAndInternal`, `Required Public`, `Required PublicAndInternal` und `Required All`. Weitere Informationen finden Sie unter [Richtlinieneinstellungen für die Laufzeitanweisung](runtime-directive-policy-settings.md).|  
  
### <a name="child-elements"></a>Untergeordnete Elemente  
  
|Element|BESCHREIBUNG|  
|-------------|-----------------|  
|[\<Namespace>](namespace-element-net-native.md)|Wendet die Reflektionsrichtlinie auf alle Typen in einem untergeordneten Namespace an.|  
|[\<Type>](type-element-net-native.md)|Wendet die Reflektionsrichtlinie auf einen Typ an.|  
|[\<TypeInstantiation>](typeinstantiation-element-net-native.md)|Wendet die Reflektionsrichtlinie auf einen konstruierten generischen Typ an.|  
  
### <a name="parent-elements"></a>Übergeordnete Elemente  
  
|Element|BESCHREIBUNG|  
|-------------|-----------------|  
|[\<Application>](application-element-net-native.md)|Dient als Container für anwendungsweite Typen und Typmember, deren Metadaten zur Laufzeit für die Reflektion verfügbar sind. Das- [\<Application>](application-element-net-native.md) Element kann über 0 (null), ein oder mehrere- `<Assembly>` Elemente verfügen.|  
|[\<Library>](library-element-net-native.md)|Definiert die Assembly, die Typen und Typmember enthält, deren Metadaten zur Laufzeit für die Reflektion verfügbar sind. Das- [\<Library>](library-element-net-native.md) Element kann kein oder ein- `<Assembly>` Element aufweisen.|  
  
## <a name="remarks"></a>Hinweise  

 Das `<Assembly>`-Element definiert eine Laufzeitrichtlinie für alle Typen in einer Assembly. Es unterscheidet sich vom- [\<Library>](library-element-net-native.md) Element, das eine Bibliothek angibt, aber von seinen untergeordneten Elementen abhängt, um die laufzeitreflektionsrichtlinie Das `<Assembly>`-Element gilt für alle Typen in einer Assembly, sofern sie nicht von einem untergeordneten Element überschrieben werden.  
  
 Das folgende Beispiel zeigt, wie Sie eine Laufzeitrichtlinie auf alle Typen in Assemblys in Ihrem App-Paket anwenden, indem Sie dem `Name`-Attribut den Wert "*Anwendung\*" zuweisen. Das- `<Assembly>` Element muss ein untergeordnetes Element des- [\<Application>](application-element-net-native.md) Elements sein.  
  
```xml  
<Directives xmlns="http://schemas.microsoft.com/netfx/2013/01/metadata">
  <Application>
     <Assembly Name="*Application*" Dynamic="Required All" />
  </Application>
</Directives>  
```  
  
 Die Attribute `Activate`, `Browse`, `Dynamic` und `Serialize` sind optional. Allerdings muss das `<Assembly>`-Element mindestens eines dieser Attribute enthalten.  
  
## <a name="see-also"></a>Weitere Informationen

- [Richtlinieneinstellungen für die Laufzeitanweisung](runtime-directive-policy-settings.md)
- [Laufzeitanweisungs-Konfigurationsdatei (rd.xml) Referenz](runtime-directives-rd-xml-configuration-file-reference.md)
- [Elemente der Laufzeitanweisung](runtime-directive-elements.md)
