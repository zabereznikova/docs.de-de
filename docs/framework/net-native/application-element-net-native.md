---
title: '&lt;Anwendung&gt; Element (.NET Native)'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: b4e9b37a-059b-4076-8f56-cb3f9cef0cd9
caps.latest.revision: "21"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: c486faf43a1109b0391f40072ab267b72e1d07d8
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="ltapplicationgt-element-net-native"></a>&lt;Anwendung&gt; Element (.NET Native)
Dient als Container für anwendungsweite Typen und Typmember, deren Metadaten zur Laufzeit für die Reflektion verfügbar sind, und wendet Laufzeitreflektionsrichtlinien auf alle Programmelemente in einer App an.  
  
 \<Directives>-Element  
\<Anwendung>-Element (rd.xml)  
  
## <a name="syntax"></a>Syntax  
  
```xml  
<Application Activate="policy_setting"  
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
 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben. In der Tabelle der untergeordneten Elemente bezieht sich die Richtlinie auf die Art von Metadaten, die für bestimmte Programmelemente zur Laufzeit verfügbar gemacht werden.  
  
### <a name="attributes"></a>Attribute  
  
|Attribut|Attributtyp|Beschreibung|  
|---------------|--------------------|-----------------|  
|`Activate`|Spiegelung|Optionales Attribut. Steuert den Laufzeitzugriff auf Konstruktoren, um die Aktivierung von Instanzen zu ermöglichen.|  
|`Browse`|Spiegelung|Optionales Attribut. Steuert das Abfragen nach Informationen über die Typen oder das Auflisten der Typen, aber ermöglicht keinen dynamischen Zugriff zur Laufzeit.|  
|`Dynamic`|Spiegelung|Optionales Attribut. Steuert den Laufzeitzugriff auf alle Typmember, einschließlich Konstruktoren, Methoden, Felder, Eigenschaften und Ereignisse, um die dynamische Programmierung zu ermöglichen.|  
|`Serialize`|Serialisierung|Optionales Attribut. Steuert den Laufzeitzugriff auf Konstruktoren, Felder und Eigenschaften, um Serialisierung und Deserialisierung von Typinstanzen durch Bibliotheken wie das Newtonsoft JSON-Serialisierungsprogramm zu ermöglichen.|  
|`DataContractSerializer`|Serialisierung|Optionales Attribut. Steuert die Richtlinie für die Serialisierung, die die <xref:System.Runtime.Serialization.DataContractSerializer?displayProperty=nameWithType>-Klasse verwendet.|  
|`DataContractJsonSerializer`|Serialisierung|Optionales Attribut. Steuert die Richtlinie für die JSON-Serialisierung, die die <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer?displayProperty=nameWithType>-Klasse verwendet.|  
|`XmlSerializer`|Serialisierung|Optionales Attribut. Steuert die Richtlinie für die XML-Serialisierung, die die <xref:System.Xml.Serialization.XmlSerializer?displayProperty=nameWithType>-Klasse verwendet.|  
|`MarshalObject`|Interop|Optionales Attribut. Steuert die Richtlinie für das Marshalling von Verweistypen zu Windows-Runtime und COM.|  
|`MarshalDelegate`|Interop|Optionales Attribut. Steuert die Richtlinie für das Marshalling von Delegattypen als Funktionszeiger zu systemeigenem Code.|  
|`MarshalStructure`|Interop|Optionales Attribut. Steuert die Richtlinie für das Marshalling von Strukturen zu systemeigenem Code.|  
  
## <a name="all-attributes"></a>Alle Attribute  
  
|Wert|Beschreibung|  
|-----------|-----------------|  
|*policy_setting*|Die Einstellung für diese Richtlinie, die auf die Typen in der App angewendet werden soll. Mögliche Werte sind `All`, `Auto`, `Excluded`, `Public`, `PublicAndInternal`, `Required Public`, `Required PublicAndInternal` und `Required All`. Weitere Informationen finden Sie unter [Richtlinieneinstellungen für die Laufzeitanweisung](../../../docs/framework/net-native/runtime-directive-policy-settings.md).|  
  
### <a name="child-elements"></a>Untergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|[\<Assembly>](../../../docs/framework/net-native/assembly-element-net-native.md)|Wendet die Richtlinie auf alle Typen in einer bestimmten Assembly an.|  
|[\<Namespace>](../../../docs/framework/net-native/namespace-element-net-native.md)|Wendet die Richtlinie auf alle Typen in einem bestimmten Namespace an.|  
|[\<Type>](../../../docs/framework/net-native/type-element-net-native.md)|Wendet die Richtlinie auf einen bestimmten Typ, z. B. eine Klasse oder Struktur, an.|  
|[\<TypeInstantiation>](../../../docs/framework/net-native/typeinstantiation-element-net-native.md)|Wendet die Richtlinie auf einen konstruierten generischen Typ an. Zum Beispiel kann ein [\<TypeInstantiation>](../../../docs/framework/net-native/typeinstantiation-element-net-native.md)-Element verwendet werden, um Richtlinien für einen `List<String>`-Typ zu definieren.|  
|[\<Method>](../../../docs/framework/net-native/method-element-net-native.md)|Wendet die Richtlinie auf eine Methode für einen bestimmten Typ an.|  
|[\<MethodInstantiation>](../../../docs/framework/net-native/methodinstantiation-element-net-native.md)|Wendet die Richtlinie auf eine konstruierte generische Methode an.|  
|[\<Property>](../../../docs/framework/net-native/property-element-net-native.md)|Wendet die Richtlinie auf eine Eigenschaft für einen bestimmten Typ an.|  
|[\<Field>](../../../docs/framework/net-native/field-element-net-native.md)|Wendet die Richtlinie auf ein Feld für einen bestimmten Typ an.|  
|[\<Event>](../../../docs/framework/net-native/event-element-net-native.md)|Wendet die Richtlinie auf ein Ereignis für einen bestimmten Typ an.|  
  
### <a name="parent-elements"></a>Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|[\<Directives>](../../../docs/framework/net-native/directives-element-net-native.md)|Das Stammelement einer Laufzeitanweisungsdatei.|  
  
## <a name="remarks"></a>Hinweise  
 Das [\<Richtlinien>](../../../docs/framework/net-native/directives-element-net-native.md)-Element kann null oder ein `<Application>`-Element enthalten. Mehrere `<Application>`-Elemente in einer einzigen Reflektionsrichtliniendatei werden nicht unterstützt.  
  
 Ein `<Application>`-Element kann auf zwei Arten verwendet werden:  
  
-   Als Container für die Definition der Programmelemente, deren Metadaten zur Laufzeit benötigt werden. In diesem Fall muss das `<Application>`-Element keine Attribute haben. Zum Zeitpunkt der Kompilierung durchsuchen Compilertools alle Bibliotheken, einschließlich der .NET Framework-Kernbibliotheken, nach Programmelementen, die durch untergeordnete Elemente des `<Application>`-Elements identifiziert werden. Im Gegensatz dazu durchsuchen Compilertools nur die vom [\<Library>](../../../docs/framework/net-native/library-element-net-native.md)-Element benannte Bibliothek nach Programmelementen, die durch die untergeordneten Elemente von [\<Library>](../../../docs/framework/net-native/library-element-net-native.md) identifiziert werden.  
  
-   Als ein Element, das anwendungsweite Richtlinien für Reflektion, Serialisierung und Interop festlegt. Die Attribute des `<Application>`-Elements definieren eine anwendungsweite Richtlinie, die von den durch das `<Application>`- oder [\<Library>](../../../docs/framework/net-native/library-element-net-native.md)-Element definierten untergeordneten Elementen überschrieben werden kann.  
  
## <a name="see-also"></a>Siehe auch  
 [\<Bibliothek > Element](../../../docs/framework/net-native/library-element-net-native.md)  
 [\<Richtlinien > Element](../../../docs/framework/net-native/directives-element-net-native.md)  
 [Elemente der Laufzeitanweisung](../../../docs/framework/net-native/runtime-directive-elements.md)  
 [Runtime Directives (rd.xml) Configuration File Reference (Referenz zur Laufzeitanweisungs-Konfigurationsdatei (rd.xml))](../../../docs/framework/net-native/runtime-directives-rd-xml-configuration-file-reference.md)
