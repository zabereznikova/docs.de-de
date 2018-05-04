---
title: dataContractSerializer
ms.date: 03/30/2017
ms.assetid: a47513a4-a96c-4350-8586-daacb05dee71
ms.openlocfilehash: 0528ae823db500da3c3a1efc6934951c4e41cea7
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
---
# <a name="datacontractserializer"></a>dataContractSerializer
Enthält Konfigurationsdaten für den <xref:System.Runtime.Serialization.DataContractSerializer>.  
  
 \<system.ServiceModel>  
\<behaviors>  
\<endpointBehaviors>  
\<Verhalten >  
\<"DataContractSerializer" >  
  
## <a name="syntax"></a>Syntax  
  
```xml  
<dataContractSerializer ignoreExtensionDataObject="Boolean"  
      maxItemsInObjectGraph="Integer" />  
```  
  
## <a name="attributes-and-elements"></a>Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### <a name="attributes"></a>Attribute  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|IgnoreExtensionDataObject|Ein boolescher Wert ab, der angibt, ob vom Endpunkt bereitgestellte Daten ignoriert werden sollen, wenn dieser serialisiert oder deserialisiert wird.|  
|maxItemsInObjectGraph|Eine ganze Zahl, die die maximale Anzahl der zu serialisierenden oder zu deserialisierenden Elemente angibt.|  
  
### <a name="child-elements"></a>Untergeordnete Elemente  
 Keine  
  
### <a name="parent-elements"></a>Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|[\<behavior>](../../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)|Gibt ein Endpunktverhalten an.|  
  
## <a name="remarks"></a>Hinweise  
 Weitere Informationen zu bekannten Typen finden Sie in der <xref:System.Runtime.Serialization.DataContractSerializer>-Dokumentation.  
  
> [!CAUTION]
>  Das `<dataContractSerializer>`-Verhaltenselement sollte, wenn vorhanden, in der Konfigurationsdatei immer vor dem `<enableWebScript>`-Verhaltenselement angegeben werden. Andernfalls ist das resultierende Verhalten nicht definiert.  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Runtime.Serialization.DataContractSerializer>  
 <xref:System.ServiceModel.Description.DataContractSerializerOperationBehavior>  
 <xref:System.ServiceModel.Configuration.DataContractSerializerElement>  
 [Bekannte Typen in Datenverträgen](../../../../../docs/framework/wcf/feature-details/data-contract-known-types.md)  
 [Datenübertragung und Serialisierung](../../../../../docs/framework/wcf/feature-details/data-transfer-and-serialization.md)
