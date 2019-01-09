---
title: '&lt;knownType&gt;'
ms.date: 03/30/2017
ms.assetid: ee2b7be3-7148-4a3a-b861-48e7330615e5
ms.openlocfilehash: 6156f102573333ec0d5533b8f1a8506d91215f47
ms.sourcegitcommit: 4ac80713f6faa220e5a119d5165308a58f7ccdc8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/09/2019
ms.locfileid: "54151929"
---
# <a name="ltknowntypegt"></a>&lt;knownType&gt;
Gibt einen Typ an, der vom <xref:System.Runtime.Serialization.DataContractSerializer> während der Deserialisierung verwendet werden sollte. Dieses Element gibt einen "bekannten Typ" an, der von einem Feld oder einer Eigenschaft eines "deklarierten Typs" zurückgegeben werden kann. Weitere Informationen finden Sie unter [Data Contract Known Types](../../../../../docs/framework/wcf/feature-details/data-contract-known-types.md).  
  
 \<System.Runtime.Serialization >  
\<DataContractSerializer >  
\<DeclaredTypes >-Element  
\<Hinzufügen > der \<DeclaredTypes >  
\<KnownType >-Element  
  
## <a name="syntax"></a>Syntax  
  
```xml  
<knownType type="String">
  <parameter index="Integer"
             type="String" />
</knownType>
```  
  
## <a name="type"></a>Typ  
 `string`  
  
## <a name="attributes-and-elements"></a>Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### <a name="attributes"></a>Attribute  
  
|Attribut|Beschreibung|  
|---------------|-----------------|  
|Typ|Gibt den Typ (einschließlich Namespace), den Assemblynamen, die Version, die Kultur und das öffentliche Schlüsseltoken an.|  
  
### <a name="child-elements"></a>Untergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|[\<Parameter >](../../../../../docs/framework/configure-apps/file-schema/wcf/parameter.md)|Gibt einen Parameterindex an, wenn der deklarierte Typ ein generischer Typ ist.|  
  
### <a name="parent-elements"></a>Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|[\<add>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-declaredtypes-element.md)|Fügt der Auflistung deklarierter Typen einen deklarierten Typ hinzu.|  
  
## <a name="remarks"></a>Hinweise  
 Weitere Informationen zu bekannten Typen finden Sie unter [Data Contract Known Types](../../../../../docs/framework/wcf/feature-details/data-contract-known-types.md) und <xref:System.Runtime.Serialization.DataContractSerializer>.  
  
 Finden Sie unter den [ \<DataContractSerializer >](../../../../../docs/framework/configure-apps/file-schema/wcf/datacontractserializer-element.md) ein Beispiel für die Verwendung dieses Elements.  
  
## <a name="example"></a>Beispiel  
  
```xml  
<add type="MyCompany.Library.Shape,
           MyAssembly, Version=2.0.0.0, Culture=neutral,
           PublicKeyToken=XXXXXX, processorArchitecture=MSIL">
  <knownType type="MyCompany.Library.Circle,
                   MyAssembly, Version=2.0.0.0, Culture=neutral,
                   PublicKeyToken=XXXXXX,
                   processorArchitecture=MSIL"/>
</add>
```  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Runtime.Serialization.DataContractSerializer>  
 [Bekannte Typen in Datenverträgen](../../../../../docs/framework/wcf/feature-details/data-contract-known-types.md)  
 [\<DataContractSerializer >](../../../../../docs/framework/configure-apps/file-schema/wcf/datacontractserializer-element.md)  
 [\<add>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-declaredtypes-element.md)
