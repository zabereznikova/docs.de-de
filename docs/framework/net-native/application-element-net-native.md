---
title: "&lt;Anwendung&gt; Element (.NET Native) | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: b4e9b37a-059b-4076-8f56-cb3f9cef0cd9
caps.latest.revision: 21
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 21
---
# &lt;Anwendung&gt; Element (.NET Native)
Dient als Container für anwendungsweite Typen und Typmember, deren Metadaten zur Laufzeit für die Reflektion verfügbar sind, und wendet Laufzeitreflektionsrichtlinien auf alle Programmelemente in einer App an.  
  
 <>\>Element  
<>\>-Element (rd.xml)  
  
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
|`DataContractSerializer`|Serialisierung|Optionales Attribut. Steuert die Richtlinie für die Serialisierung, die mithilfe der <xref:System.Runtime.Serialization.DataContractSerializer?displayProperty=fullName> Klasse.|  
|`DataContractJsonSerializer`|Serialisierung|Optionales Attribut. Steuert die Richtlinie für die JSON-Serialisierung verwendet die <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer?displayProperty=fullName> Klasse.|  
|`XmlSerializer`|Serialisierung|Optionales Attribut. Steuert die Richtlinie für die XML-Serialisierung, die verwendet die <xref:System.Xml.Serialization.XmlSerializer?displayProperty=fullName> Klasse.|  
|`MarshalObject`|Interop|Optionales Attribut. Steuert die Richtlinie für das Marshalling von Verweistypen zu Windows-Runtime und COM.|  
|`MarshalDelegate`|Interop|Optionales Attribut. Steuert die Richtlinie für das Marshalling von Delegattypen als Funktionszeiger zu systemeigenem Code.|  
|`MarshalStructure`|Interop|Optionales Attribut. Steuert die Richtlinie für das Marshalling von Strukturen zu systemeigenem Code.|  
  
## <a name="all-attributes"></a>Alle Attribute  
  
|Wert|Beschreibung|  
|-----------|-----------------|  
|*policy_setting*|Die Einstellung für diese Richtlinie, die auf die Typen in der App angewendet werden soll. Mögliche Werte sind `All`, `Auto`, `Excluded`, `Public`, `PublicAndInternal`, `Required Public`, `Required PublicAndInternal` und `Required All`. Weitere Informationen finden Sie unter [Laufzeitrichtlinieneinstellungen der Richtlinie](../../../docs/framework/net-native/runtime-directive-policy-settings.md).|  
  
### <a name="child-elements"></a>Untergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|[<>\>](../../../docs/framework/net-native/assembly-element-net-native.md)|Wendet die Richtlinie auf alle Typen in einer bestimmten Assembly an.|  
|[<>\>](../../../docs/framework/net-native/namespace-element-net-native.md)|Wendet die Richtlinie auf alle Typen in einem bestimmten Namespace an.|  
|[<>\>](../../../docs/framework/net-native/type-element-net-native.md)|Wendet die Richtlinie auf einen bestimmten Typ, z. B. eine Klasse oder Struktur, an.|  
|[<>\>](../../../docs/framework/net-native/typeinstantiation-element-net-native.md)|Wendet die Richtlinie auf einen konstruierten generischen Typ an. Z. B. eine [ <> \> ](../../../docs/framework/net-native/typeinstantiation-element-net-native.md) Element konnte verwendet werden, um die Richtlinie für das Definieren einer `List<String>` Typ.|  
|[<>\>](../../../docs/framework/net-native/method-element-net-native.md)|Wendet die Richtlinie auf eine Methode für einen bestimmten Typ an.|  
|[<>\>](../../../docs/framework/net-native/methodinstantiation-element-net-native.md)|Wendet die Richtlinie auf eine konstruierte generische Methode an.|  
|[<>\>](../../../docs/framework/net-native/property-element-net-native.md)|Wendet die Richtlinie auf eine Eigenschaft für einen bestimmten Typ an.|  
|[<>\>](../../../docs/framework/net-native/field-element-net-native.md)|Wendet die Richtlinie auf ein Feld für einen bestimmten Typ an.|  
|[<>\>](../../../docs/framework/net-native/event-element-net-native.md)|Wendet die Richtlinie auf ein Ereignis für einen bestimmten Typ an.|  
  
### <a name="parent-elements"></a>Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|[<>\>](../../../docs/framework/net-native/directives-element-net-native.md)|Das Stammelement einer Laufzeitdirektivendatei.|  
  
## <a name="remarks"></a>Hinweise  
 Die [ <> \> ](../../../docs/framework/net-native/directives-element-net-native.md) Element kann NULL oder eins enthalten `<Application>` Element. Mehrere `<Application>`-Elemente in einer einzigen Reflektionsrichtliniendatei werden nicht unterstützt.  
  
 Ein `<Application>`-Element kann auf zwei Arten verwendet werden:  
  
-   Als Container für die Definition der Programmelemente, deren Metadaten zur Laufzeit benötigt werden. In diesem Fall muss das `<Application>`-Element keine Attribute haben. Zum Zeitpunkt der Kompilierung durchsuchen Compilertools alle Bibliotheken, einschließlich der .NET Framework-Kernbibliotheken, nach Programmelementen, die durch untergeordnete Elemente des `<Application>`-Elements identifiziert werden. Im Gegensatz dazu durchsuchen Compilertools nur die bezeichnete Bibliothek der [ <> \> ](../../../docs/framework/net-native/library-element-net-native.md) Element nach Programmelementen, die durch die untergeordneten Elemente des [ <> \</> \> ](../../../docs/framework/net-native/library-element-net-native.md).  
  
-   Als ein Element, das anwendungsweite Richtlinien für Reflektion, Serialisierung und Interop festlegt. Die Attribute der `<Application>` -Element definieren eine anwendungsweite-Richtlinie, die von den untergeordneten Elementen definiert überschrieben werden kann, die `<Application>` oder [ <> \> ](../../../docs/framework/net-native/library-element-net-native.md) Element.  
  
## <a name="see-also"></a>Siehe auch  
 [<>\>Element](../../../docs/framework/net-native/library-element-net-native.md)   
 [<>\>Element](../../../docs/framework/net-native/directives-element-net-native.md)   
 [Elemente der Laufzeitrichtlinie](../../../docs/framework/net-native/runtime-directive-elements.md)   
 [Laufzeit-Konfigurationsdatei Laufzeitdirektiven (rd.xml) Referenz](../../../docs/framework/net-native/runtime-directives-rd-xml-configuration-file-reference.md)