---
title: <GenericParameter> (Element (.NET Native)
ms.date: 03/30/2017
ms.assetid: cbd49732-3615-49a5-a900-f96947cdc3e6
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 40fef845a55412e5731ec08bd1e038d6b311694c
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61868604"
---
# <a name="genericparameter-element-net-native"></a>\<GenericParameter > (Element (.NET Native)
Wendet die Richtlinie auf den Parametertyp eines generischen Typs oder einer generischen Methode an.  
  
## <a name="syntax"></a>Syntax  
  
```xml  
<GenericParameter Name="generic_parameter_name"  
                  Activate="policy_type"  
                  Browse="policy_type"  
                  Dynamic="policy_type"  
                  Serialize="policy_type"  
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
|`Name`|Allgemein|Erforderliches Attribut. Der Name des generischen Parameters. Z. B. muss für den generischen Delegaten <xref:System.Func%603> der Wert des `Name`-Attributs "TResult" lauten, um die Laufzeitrichtlinie auf den Rückgabewert des Delegaten anzuwenden.|  
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
|*generic_parameter_name*|Erforderliches Attribut. Der Name des generischen Typparameters. Wendet z.B. für den generischen Delegaten <xref:System.Func%603> der *generic_parameter_name*-Wert „TResult“ die Laufzeitrichtlinie auf den Rückgabewert des Delegaten an.|  
  
## <a name="all-other-attributes"></a>Alle anderen Attribute  
  
|Wert|Beschreibung|  
|-----------|-----------------|  
|*policy_setting*|Die Einstellung, die auf diesen Richtlinientyp angewendet werden soll. Mögliche Werte sind `All`, `Public`, `PublicAndInternal`, `Required Public`, `Required PublicAndInternal` und `Required All`. Weitere Informationen finden Sie unter [Richtlinieneinstellungen für die Laufzeitanweisung](../../../docs/framework/net-native/runtime-directive-policy-settings.md).|  
  
### <a name="child-elements"></a>Untergeordnete Elemente  
 Keine  
  
### <a name="parent-elements"></a>Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|[\<Method>](../../../docs/framework/net-native/method-element-net-native.md)|Wendet die Laufzeitreflektionsrichtlinie auf einen Konstruktor oder eine Methode an.|  
|[\<Type>](../../../docs/framework/net-native/type-element-net-native.md)|Wendet eine Laufzeitreflektionsrichtlinie auf einen bestimmten Typ, z. B. eine Klasse oder Struktur, an.|  
  
## <a name="remarks"></a>Hinweise  
 Das `<GenericParameter>`-Element ist ein untergeordnetes Element des [\<Method>](../../../docs/framework/net-native/method-element-net-native.md)- oder [\<Type>](../../../docs/framework/net-native/type-element-net-native.md)-Elements und dient zur Anwendung der Richtlinie auf einen bestimmten generischen Typparameter, der durch seinen Namen im generischen Typ oder der Methodensignatur angegeben ist.  
  
 Das `<GenericParameter>`-Element ist am nützlichsten, wenn es mit Serialisierungsprogrammen verwendet wird. Im folgenden Beispiel wird das Element `<GenericParameter>` verwendet, um die Richtlinie auf den Typ `T` in Aufrufen von Überladungen der Methode [JsonConvert.DeserializeObject\<T>(String)](https://www.newtonsoft.com/json/help/html/M_Newtonsoft_Json_JsonConvert_DeserializeObject__1.htm) des NewtonSoft JSON-Serialisierungsprogramms anzuwenden.  
  
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

- [\<Method> Element (Element <Method>)](../../../docs/framework/net-native/method-element-net-native.md)
- [\<Type >-Element](../../../docs/framework/net-native/type-element-net-native.md)
- [Runtime Directives (rd.xml) Configuration File Reference (Referenz zur Laufzeitanweisungs-Konfigurationsdatei (rd.xml))](../../../docs/framework/net-native/runtime-directives-rd-xml-configuration-file-reference.md)
- [Richtlinieneinstellungen für die Laufzeitanweisung](../../../docs/framework/net-native/runtime-directive-policy-settings.md)
- [Elemente der Laufzeitanweisung](../../../docs/framework/net-native/runtime-directive-elements.md)
