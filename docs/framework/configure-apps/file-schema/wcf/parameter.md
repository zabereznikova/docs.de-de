---
title: '&lt;parameter&gt;'
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 0fb41e2d-64f7-44ab-993e-05892eac6d82
caps.latest.revision: 9
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: aa4b2c870864a4359ebca0a1ae47fc1c8aaebca0
ms.sourcegitcommit: 94d33cadc5ff81d2ac389bf5f26422c227832052
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/30/2018
---
# <a name="ltparametergt"></a>&lt;parameter&gt;
Gibt den generischen Parameter an, wenn ein deklarierter Typ ein generischer Typ ist.  
  
 \<System.Runtime.Serialization >  
\<"DataContractSerializer" >  
\<DeclaredTypes >-Element  
\<Hinzufügen >-Element für \<DeclaredTypes >  
\<KnownType >-Element  
\<Parameter >-Element  
  
## <a name="syntax"></a>Syntax  
  
```xml  
<parameter index="integer"  
                      type=String" />  
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
|[\<KnownType >](../../../../../docs/framework/configure-apps/file-schema/wcf/knowntype.md)|Gibt einen bekannten Typ an, der von einem Feld oder einer Eigenschaft des deklarierten Typs zurückgegeben werden kann.|  
  
## <a name="remarks"></a>Hinweise  
 Weitere Informationen über bekannte Typen finden Sie unter [Datenvertragstypen bezeichnet](../../../../../docs/framework/wcf/feature-details/data-contract-known-types.md) und <xref:System.Runtime.Serialization.DataContractSerializer>.  
  
 Finden Sie unter der [ \<"DataContractSerializer" >](../../../../../docs/framework/configure-apps/file-schema/wcf/datacontractserializer-element.md) für ein Beispiel für dieses Element.  
  
 Dieses Konfigurationselement darf nicht über zwei Attribute gleichzeitig verfügen. Falls beide Attribute festgelegt sind, tritt <xref:System.Configuration.ConfigurationErrorsException> auf.  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Runtime.Serialization.DataContractSerializer>  
 [Bekannte Typen in Datenverträgen](../../../../../docs/framework/wcf/feature-details/data-contract-known-types.md)  
 [\<"DataContractSerializer" >](../../../../../docs/framework/configure-apps/file-schema/wcf/datacontractserializer-element.md)  
 [\<add>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-declaredtypes-element.md)
