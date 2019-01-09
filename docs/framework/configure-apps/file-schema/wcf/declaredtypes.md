---
title: '&lt;declaredTypes&gt;'
ms.date: 03/30/2017
helpviewer_keywords:
- dataContractSerializer element
- declaredTypes element
- DataContractSerializer
- KnownTypes
- <declaredTypes> element
ms.assetid: f35184e4-9d9e-4d37-8fb4-d5b58220eb3e
ms.openlocfilehash: 0fadb13d4fcfbe87eb2c08fc35323c726c0ac2a6
ms.sourcegitcommit: 4ac80713f6faa220e5a119d5165308a58f7ccdc8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/09/2019
ms.locfileid: "54146419"
---
# <a name="ltdeclaredtypesgt"></a>&lt;declaredTypes&gt;
Enthält die bekannten Typen, die der <xref:System.Runtime.Serialization.DataContractSerializer> bei der Deserialisierung verwendet.  
  
 Weitere Informationen über Datenverträge und bekannte Typen finden Sie unter [Data Contract Known Types](../../../../../docs/framework/wcf/feature-details/data-contract-known-types.md).  
  
 system.runtime.serialization  
\<DataContractSerializer >  
\<DeclaredTypes >  
  
## <a name="syntax"></a>Syntax  
  
```xml  
<configuration>
  <system.runtime.serialization>
    <dataContractSerializer>
      <declaredTypes>
        <add type="String ">
          <knownType type="String">
            <parameter index="Integer"/>
          </knownType>
        </add>
      </declaredTypes>
    <dataContractSerializer>
  </system.runtime.serialization>
</configuration>
```  
  
## <a name="attributes-and-elements"></a>Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### <a name="attributes"></a>Attribute  
 Keine  
  
### <a name="child-elements"></a>Untergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|[\<add>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-declaredtypes-element.md)|Fügt Typen hinzu, die bekannte Typen erfordern.|  
  
### <a name="parent-elements"></a>Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|[\<DataContractSerializer >](../../../../../docs/framework/configure-apps/file-schema/wcf/datacontractserializer-of-system-runtime-serialization.md)|Enthält Konfigurationsdaten für den <xref:System.Runtime.Serialization.DataContractSerializer>.|  
  
## <a name="remarks"></a>Hinweise  
 Weitere Informationen zu bekannten Typen finden Sie unter [Data Contract Known Types](../../../../../docs/framework/wcf/feature-details/data-contract-known-types.md) und <xref:System.Runtime.Serialization.DataContractSerializer>.  
  
## <a name="example"></a>Beispiel  
 Der folgende XML-Code zeigt deklarierte Typen und bekannte Typen hinzugefügt, ein `DataContractSerializer` Element. Im Beispiel werden drei hinzugefügte Typen dargestellt. Der erste ist ein benutzerdefinierter Typ mit dem Namen "Orders", der einen bekannten Typ mit dem Namen "Item" verwendet. Der zweite deklarierte Typ ist <xref:System.Collections.Generic.List%601> und verwendet `Item` als bekannten Typ. Der dritte deklarierte Typ ist <xref:System.Collections.Generic.Dictionary%602>. Der <xref:System.Collections.Generic.Dictionary%602>-Klassentyp ist ein generischer Typ mit zwei Typparametern. Der erste stellt den Schlüssel dar und der zweite den Wert. Im folgenden Beispiel wird ein <xref:System.Collections.Generic.List%601> des zweiten Typs (der Wert) zur Liste bekannter Typen hinzugefügt. Sie müssen das `index`-Attribut verwenden, um anzugeben, welcher Typparameter im bekannten Typ verwendet werden soll. In diesem Fall wird der Werttyp über das Indexattribut angegeben, das auf "1" festgelegt ist (die Auflistung ist nullbasiert).  
  
```xml  
<configuration>
  <system.runtime.serialization>
    <dataContractSerializer>
      <declaredTypes>
        <add type="Examples.Types.Orders, SerializationTypes, Version = 2.0.0.0, Culture = neutral, PublicKeyToken=null">
          <knownType type="Examples.Types.Item, SerializationTypes, Version=2.0.0.0, Culture=neutral, PublicKey=null" />
        </add>
        <add type="System.Collections.Generic.List`1, SerializationTypes, Version = 2.0.0.0, Culture = neutral, PublicKeyToken=null">
          <knownType type="Examples.Types.Item, SerializationTypes, Version=2.0.0.0, Culture=neutral, PublicKey=null" />
        </add>
        <add type="System.Collections.Generic.Dictionary`2, SerializationTypes, Version = 2.0.0.0, Culture = neutral, PublicKeyToken=null">
          <knownType type="System.Collections.Generic.List`1, SerializationTypes, Version = 2.0.0.0, Culture = neutral, PublicKeyToken=null">
            <parameter index="1"/>
          </knownType>
        </add>
      </declaredTypes>
    <dataContractSerializer>
  </system.runtime.serialization>
</configuration>
```  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Runtime.Serialization.DataContractSerializer>  
 [\<DataContractSerializer >](../../../../../docs/framework/configure-apps/file-schema/wcf/datacontractserializer-element.md)  
 [Bekannte Typen in Datenverträgen](../../../../../docs/framework/wcf/feature-details/data-contract-known-types.md)  
 [\<add>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-declaredtypes-element.md)
