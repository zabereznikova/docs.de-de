---
title: <parameter>
ms.date: 03/30/2017
ms.assetid: 0fb41e2d-64f7-44ab-993e-05892eac6d82
ms.openlocfilehash: 22ef3c3c6d23d6c68c27d6b5d1ed35b7c9910d48
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61783434"
---
# <a name="parameter"></a>\<parameter>
Gibt den generischen Parameter an, wenn ein deklarierter Typ ein generischer Typ ist.  
  
 \<system.runtime.serialization>  
\<dataContractSerializer>  
\<DeclaredTypes >-Element  
\<Hinzufügen >-Element für \<DeclaredTypes >  
\<KnownType >-Element  
\<Parameter >-Element  
  
## <a name="syntax"></a>Syntax  
  
```xml  
<parameter index="Integer"
           type="String" />
```  
  
## <a name="attributes-and-elements"></a>Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### <a name="attributes"></a>Attribute  
  
|Attribut|Beschreibung|  
|---------------|-----------------|  
|Index|Gibt den generischen Parameter an, der den bekannten Typ zurückgibt, wenn der deklarierte Typ ein generischer Typ ist.|  
|Typ|Eine Zeichenfolge, mit der der für die Serialisierung und Deserialisierung verwendete bekannte Typ beschrieben wird.|  
  
## <a name="index-attribute"></a>Indexattribut  
  
|Wert|Beschreibung|  
|-----------|-----------------|  
|"0"|Der erste Parameter im generischen Typ. Zum Beispiel verfügt <xref:System.Collections.Generic.List%601> nur über einen Parameter. Falls dieser als deklarierter Typ verwendet wird, wäre der Index auf "0" festgelegt.|  
|"1"|Der zweite Parameter in einem generischen Typ. Zum Beispiel verfügt <xref:System.Collections.Generic.Dictionary%602> über zwei Parameter. Falls der bekannte Typ vom zweiten Parameter zurückgegeben wird, legen Sie das Indexattribut auf "1" fest.|  
  
### <a name="child-elements"></a>Untergeordnete Elemente  
 Keine  
  
### <a name="parent-elements"></a>Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|[\<knownType>](../../../../../docs/framework/configure-apps/file-schema/wcf/knowntype.md)|Gibt einen bekannten Typ an, der von einem Feld oder einer Eigenschaft des deklarierten Typs zurückgegeben werden kann.|  
  
## <a name="remarks"></a>Hinweise  
 Weitere Informationen zu bekannten Typen finden Sie unter [Data Contract Known Types](../../../../../docs/framework/wcf/feature-details/data-contract-known-types.md) und <xref:System.Runtime.Serialization.DataContractSerializer>.  
  
 Finden Sie unter den [ \<DataContractSerializer >](../../../../../docs/framework/configure-apps/file-schema/wcf/datacontractserializer-element.md) ein Beispiel für die Verwendung dieses Elements.  
  
 Dieses Konfigurationselement darf nicht über zwei Attribute gleichzeitig verfügen. Falls beide Attribute festgelegt sind, tritt <xref:System.Configuration.ConfigurationErrorsException> auf.  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Runtime.Serialization.DataContractSerializer>
- [Bekannte Typen in Datenverträgen](../../../../../docs/framework/wcf/feature-details/data-contract-known-types.md)
- [\<dataContractSerializer>](../../../../../docs/framework/configure-apps/file-schema/wcf/datacontractserializer-element.md)
- [\<add>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-declaredtypes-element.md)
