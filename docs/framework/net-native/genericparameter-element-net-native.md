---
title: "&lt;GenericParameter&gt; Element (.NET Native) | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: cbd49732-3615-49a5-a900-f96947cdc3e6
caps.latest.revision: 11
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 11
---
# &lt;GenericParameter&gt; Element (.NET Native)
Wendet die Richtlinie auf den Parametertyp eines generischen Typs oder einer generischen Methode an.  
  
## <a name="syntax"></a>Syntax  
  
```xml  
  
<GenericParameter Name="generic_parameter_name"  
                  Activate="policy_type"  
                  Browse="policy_type"  
                  Dynamic="policy_type"  
                  Serialize="policy_type" />  
                  DataContractSerializer="policy_type"  
                  DataContractJsonSerializer="policy_type"  
                  XmlSerializer="policy_type"  
                  MarshalObject="policy_type"  
                  MarshalDelegate="policy_type"  
                  MarshalStructure="policy_type"  
  
```  
  
## <a name="attributes-and-elements"></a>Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### <a name="attributes"></a>Attribute  
  
|Attribut|Attributtyp|Beschreibung|  
|---------------|--------------------|-----------------|  
|`Name`|Allgemein|Erforderliches Attribut. Der Name des generischen Parameters. Z. B. für den generischen Delegaten <xref:System.Func%603>, den Wert der `Name` -Attribut ist "TResult" Rückgabewert des Delegaten Laufzeitrichtlinie zuweisen.\</T1, T2, TResult>|  
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
|*generic_parameter_name*|Erforderliches Attribut. Der Name des generischen Typparameters. Zum Beispiel für den generischen Delegaten <xref:System.Func%603>, *Generic_parameter_name* -Wert "TResult" die Laufzeitrichtlinie auf den Rückgabewert des Delegaten.\</T1, T2, TResult>|  
  
## <a name="all-other-attributes"></a>Alle anderen Attribute  
  
|Wert|Beschreibung|  
|-----------|-----------------|  
|*policy_setting*|Die Einstellung, die auf diesen Richtlinientyp angewendet werden soll. Mögliche Werte sind `All`, `Public`, `PublicAndInternal`, `Required Public`, `Required PublicAndInternal` und `Required All`. Weitere Informationen finden Sie unter [Laufzeitrichtlinieneinstellungen der Richtlinie](../../../docs/framework/net-native/runtime-directive-policy-settings.md).|  
  
### <a name="child-elements"></a>Untergeordnete Elemente  
 Keine  
  
### <a name="parent-elements"></a>Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|[<>\>](../../../docs/framework/net-native/method-element-net-native.md)|Wendet die Laufzeitreflektionsrichtlinie auf einen Konstruktor oder eine Methode an.|  
|[<>\>](../../../docs/framework/net-native/type-element-net-native.md)|Wendet eine Laufzeitreflektionsrichtlinie auf einen bestimmten Typ, z. B. eine Klasse oder Struktur, an.|  
  
## <a name="remarks"></a>Hinweise  
 Die `<GenericParameter>` Element ist ein untergeordnetes Element von der [ <> \> ](../../../docs/framework/net-native/method-element-net-native.md) oder [ <> \> ](../../../docs/framework/net-native/type-element-net-native.md) Element und wird verwendet, um die Richtlinie auf einen bestimmten generischen Typparameter angewendet, der durch seinen Namen im generischen Typ oder eine Methode der Methodensignatur angegeben ist.  
  
 Das `<GenericParameter>`-Element ist am nützlichsten, wenn es mit Serialisierungsprogrammen verwendet wird. Im folgenden Beispiel wird die `<GenericParameter>` Element Richtlinie auf den Typ angewendet `T` in Aufrufen an des NewtonSoft JSON-Serialisierungsprogramms [JsonConvert.DeserializeObject<>\>(String)](http://james.newtonking.com/json/help/index.html?topic=html/T_Newtonsoft_Json_JsonConvert.htm) überladene Methoden.  
  
```xml  
  
<Directives xmlns="http://schemas.microsoft.com/netfx/2013/01/metadata">  
   <Type Name="Newtonsoft.Json.JsonConvert" >  
      <Method Name="DeserializeObject{T}">  
         <GenericParameter Name="T" Serialize="Required All" />  
      </Method>  
   </Type>  
</Directives>  
  
```  
  
## <a name="see-also"></a>Siehe auch  
 [<>\>Element](../../../docs/framework/net-native/method-element-net-native.md)   
 [<>\>Element](../../../docs/framework/net-native/type-element-net-native.md)   
 [Laufzeit-Konfigurationsdatei Laufzeitdirektiven (rd.xml) Referenz](../../../docs/framework/net-native/runtime-directives-rd-xml-configuration-file-reference.md)   
 [Richtlinie für die Laufzeitrichtlinie](../../../docs/framework/net-native/runtime-directive-policy-settings.md)   
 [Elemente der Laufzeitrichtlinie](../../../docs/framework/net-native/runtime-directive-elements.md)