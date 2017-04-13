---
title: "&lt;ImpliesType&gt; Element (.NET Native) | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 3abd2071-0f28-40ba-b9a0-d52bd94cd2f6
caps.latest.revision: 7
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 7
---
# &lt;ImpliesType&gt; Element (.NET Native)
Wendet eine Richtlinie auf einen Typ an, wenn diese Richtlinie auf den enthaltenden Typ oder die enthaltende Methode angewendet wurde.  
  
## <a name="syntax"></a>Syntax  
  
```vb  
  
<ImpliesType Name="type_name"  
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
|`DataContractSerializer`|Serialisierung|Optionales Attribut. Steuert die Richtlinie für die Serialisierung, die mithilfe der <xref:System.Runtime.Serialization.DataContractSerializer?displayProperty=fullName> Klasse.|  
|`DataContractJsonSerializer`|Serialisierung|Optionales Attribut. Steuert die Richtlinie für die JSON-Serialisierung verwendet die <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer?displayProperty=fullName> Klasse.|  
|`XmlSerializer`|Serialisierung|Optionales Attribut. Steuert die Richtlinie für die XML-Serialisierung, die verwendet die <xref:System.Xml.Serialization.XmlSerializer?displayProperty=fullName> Klasse.|  
|`MarshalObject`|Interop|Optionales Attribut. Steuert die Richtlinie für das Marshalling von Verweistypen zu Windows-Runtime und COM.|  
|`MarshalDelegate`|Interop|Optionales Attribut. Steuert die Richtlinie für das Marshalling von Delegattypen als Funktionszeiger zu systemeigenem Code.|  
|`MarshalStructure`|Interop|Optionales Attribut. Steuert die Richtlinie für das Marshalling von Werttypen zu systemeigenem Code.|  
  
## <a name="name-attribute"></a>Namensattribut  
  
|Wert|Beschreibung|  
|-----------|-----------------|  
|*TYPE_NAME*|Der Typname. Wenn der Typ von diesem dargestellt `<ImpliesType>` Element befindet sich im selben Namespace wie das enthaltende `<Type>` Element *Type_name* zählen der Name des Typs ohne den Namespace. Andernfalls *Type_name* muss den vollqualifizierten Typnamen enthalten.|  
  
## <a name="all-other-attributes"></a>Alle anderen Attribute  
  
|Wert|Beschreibung|  
|-----------|-----------------|  
|*policy_setting*|Die Einstellung, die auf diesen Richtlinientyp angewendet werden soll. Mögliche Werte sind `All`, `Auto`, `Excluded`, `Public`, `PublicAndInternal`, `Required Public`, `Required PublicAndInternal` und `Required All`. Weitere Informationen finden Sie unter [Laufzeitrichtlinieneinstellungen der Richtlinie](../../../docs/framework/net-native/runtime-directive-policy-settings.md).|  
  
### <a name="child-elements"></a>Untergeordnete Elemente  
 Keine  
  
### <a name="parent-elements"></a>Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|[<>\>](../../../docs/framework/net-native/type-element-net-native.md)|Wendet die Reflektionsrichtlinie auf einen Typ und alle seine Member an.|  
|[<>\>](../../../docs/framework/net-native/typeinstantiation-element-net-native.md)|Wendet die Reflektionsrichtlinie auf einen konstruierten generischen Typ und alle seine Member an.|  
|[<>\>](../../../docs/framework/net-native/method-element-net-native.md)|Wendet die Reflektionsrichtlinie auf eine Methode an.|  
  
## <a name="remarks"></a>Hinweise  
 Das `<ImpliesType>`-Element dient in erster Linie der Verwendung durch Bibliotheken. Es wird in folgendem Szenario eingesetzt:  
  
-   Wenn eine Routine einen Typ reflektieren muss, muss sie unbedingt einen zweiten Typ reflektieren.  
  
-   Die Metadaten für die implizite Instanziierung des zweiten Typs ist andernfalls nicht verfügbar, da die statische Analyse nicht angibt, dass dies erforderlich ist.  
  
 In den meisten Fällen sind die beiden Typen generische Instanziierungen mit freigegebenen Typargumenten.  
  
 Das `<ImpliesType>`-Element wurde unter der Annahme definiert, dass die Notwendigkeit einer Reflektion für den Typ, der von seinem übergeordneten Element angegebenen wird, eine Notwendigkeit einer Reflektion für den Typ impliziert, der vom `<ImpliesType>`-Element angegeben wird. Die folgenden Reflektionsrichtlinien gelten z. B. für zwei Typen – `Explicit<T>` und `Implicit<T>`.  
  
```xml  
  
<Type Name=”Explicit{ET}”>  
    <ImpliesType Name=”Implicit{ET}” Dynamic=”Required Public” />  
</Type>  
  
```  
  
 Diese Richtlinie hat nur dann eine Auswirkungen, wenn eine Instanziierung von `Explicit` über eine definierte `Dynamic`-Richtlinieneinstellung verfügt. Wenn das z. B. für `Explicit<Int32>` der Fall ist, wird `Implicit<Int32>` mit den öffentlichen Membern instanziiert, und ihre Metadaten werden für die dynamische Programmierung verfügbar gemacht.  
  
 Folgendes ist ein praktisches Beispiel, das für mindestens ein Serialisierungsprogramm gilt. Das Aufzeichnen der Anforderung, die etwas reflektieren als eingegeben `IList<` *etwas* `>` umfasst auch die Reflektion des entsprechenden `List<` *etwas* `>` Typ ohne das anwendungsbasierte Anmerkungen erforderlich sind.  
  
```xml  
  
<Type Name=”System.Collections.Generic.IList{T}”>  
   <ImpliesType Name=”System.Collections.Generic.List{T}” Serialize=”Public” />  
</Type>  
  
```  
  
 Das `<ImpliesType>`-Element kann auch innerhalb eines `<Method>`-Element angezeigt werden, da in einigen Fällen das Instanziieren einer generischen Methode die Reflektion einer Typinstanziierung impliziert. Angenommen, eine generische Methode `IEnumerable<T> MakeEnumerable<T>(string` `spelling``, T` `defaultValue``)` , die auf eine angegebene Bibliothek wird zusammen mit den zugehörigen dynamisch zugreifen <xref:System.Collections.Generic.List%601> und <xref:System.Array> Typen. Dies kann folgendermaßen ausgedrückt werden:  
  
```xml  
  
<Type Name=”MyType”>  
    <Method Name=”MakeEnumerable{T}” Signature=”(System.String, T)” Dynamic=”Included”>  
        <ImpliesType Name=”T[]” Dynamic=”Public” />  
        <ImpliesType Name=”System.Collections.Generic.List{T}” Dynamic=”Public”>  
    </Method>  
</Type>  
  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Laufzeit-Konfigurationsdatei Laufzeitdirektiven (rd.xml) Referenz](../../../docs/framework/net-native/runtime-directives-rd-xml-configuration-file-reference.md)   
 [Elemente der Laufzeitrichtlinie](../../../docs/framework/net-native/runtime-directive-elements.md)   
 [Richtlinie für die Laufzeitrichtlinie](../../../docs/framework/net-native/runtime-directive-policy-settings.md)