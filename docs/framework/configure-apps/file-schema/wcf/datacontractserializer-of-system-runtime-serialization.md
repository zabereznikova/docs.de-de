---
title: '&lt;dataContractSerializer&gt; von &lt;system.runtime.serialization&gt;'
ms.date: 03/30/2017
ms.assetid: d9b3d625-be3f-4768-8e0d-1b7e6929f6a8
ms.openlocfilehash: f31dd8479f3bd6b36915b3ff00ff53babe3c0248
ms.sourcegitcommit: 4ac80713f6faa220e5a119d5165308a58f7ccdc8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/09/2019
ms.locfileid: "54150174"
---
# <a name="ltdatacontractserializergt-of-ltsystemruntimeserializationgt"></a>&lt;dataContractSerializer&gt; von &lt;system.runtime.serialization&gt;
Enthält Konfigurationsdaten für den <xref:System.Runtime.Serialization.DataContractSerializer>.  
  
 \<System.Runtime.Serialization >  
\<DataContractSerializer >  
  
## <a name="syntax"></a>Syntax  
  
```xml  
<configuration>
  <system.runtime.serialization>
    <dataContractSerializer ignoreExtensionDataObject="Boolean"
                            maxItemsInObjectGraph="Integer">
      <declaredTypes>
        <add type="String">
          <knownType type="String">
            <parameter index="Integer"
                       type="String" />
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
  
|Element|Beschreibung|  
|-------------|-----------------|  
|IgnoreExtensionDataObject|Ein boolescher Wert, der angibt, ob vom Endpunkt bereitgestellte Daten ignoriert werden sollen, wenn dieser serialisiert oder deserialisiert wird. Dieses Attribut kann nur im `<dataContractSerializer>` unter dem `<behavior>`-Element festgelegt werden.|  
|maxItemsInObjectGraph|Eine ganze Zahl, die die maximale Anzahl der zu serialisierenden oder zu deserialisierenden Elemente angibt. Dieses Attribut hat den Wert 65536.|  
  
### <a name="child-elements"></a>Untergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|[\<DeclaredTypes >](../../../../../docs/framework/configure-apps/file-schema/wcf/declaredtypes.md)|Enthält die bekannten Typen, die der <xref:System.Runtime.Serialization.DataContractSerializer> bei der Deserialisierung verwendet.<br /><br /> Weitere Informationen über Datenverträge und bekannte Typen finden Sie unter [Data Contract Known Types](../../../../../docs/framework/wcf/feature-details/data-contract-known-types.md).|  
  
### <a name="parent-elements"></a>Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|[\<system.runtime.serialization>](../../../../../docs/framework/configure-apps/file-schema/wcf/system-runtime-serialization.md)|Stellt das Stammelement für den <xref:System.Runtime.Serialization>-Namespaceabschnitt dar und enthält Elemente zum Festlegen von <xref:System.Runtime.Serialization.DataContractSerializer>-Optionen.|  
  
## <a name="remarks"></a>Hinweise  
 Weitere Informationen zu bekannten Typen finden Sie unter <xref:System.Runtime.Serialization.DataContractSerializer> und [Data Contract Known Types](../../../../../docs/framework/wcf/feature-details/data-contract-known-types.md).  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Runtime.Serialization.DataContractSerializer>  
 <xref:System.ServiceModel.Description.DataContractSerializerOperationBehavior>  
 [Bekannte Typen in Datenverträgen](../../../../../docs/framework/wcf/feature-details/data-contract-known-types.md)
