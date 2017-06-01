---
title: "&lt;-Parameter von &gt; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 0fb41e2d-64f7-44ab-993e-05892eac6d82
caps.latest.revision: 9
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 9
---
# &lt;-Parameter von &gt;
Gibt den generischen Parameter an, wenn ein deklarierter Typ ein generischer Typ ist.  
  
## Syntax  
  
```  
  
<parameter index="integer"  
                      type=String" />  
```  
  
## Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### Attribute  
  
|Attribut|Beschreibung|  
|--------------|------------------|  
|Index|Gibt den generischen Parameter an, der den bekannten Typ zurückgibt, wenn der deklarierte Typ ein generischer Typ ist.|  
|Typ|Eine Zeichenfolge, mit der der für die Serialisierung und Deserialisierung verwendete bekannte Typ beschrieben wird.|  
  
## Indexattribut  
  
|Wert|Beschreibung|  
|----------|------------------|  
|"0"|Der erste Parameter im generischen Typ.  Zum Beispiel verfügt <xref:System.Collections.Generic.List%601> nur über einen Parameter.  Falls dieser als deklarierter Typ verwendet wird, wäre der Index auf "0" festgelegt.|  
|"1"|Der zweite Parameter in einem generischen Typ.  Zum Beispiel verfügt <xref:System.Collections.Generic.Dictionary%602> über zwei Parameter.  Falls der bekannte Typ vom zweiten Parameter zurückgegeben wird, legen Sie das Indexattribut auf "1" fest.|  
  
### Untergeordnete Elemente  
 Keine  
  
### Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|------------------|  
|[\<knownType\>](../../../../../docs/framework/configure-apps/file-schema/wcf/knowntype.md)|Gibt einen bekannten Typ an, der von einem Feld oder einer Eigenschaft des deklarierten Typs zurückgegeben werden kann.|  
  
## Hinweise  
 [!INCLUDE[crabout](../../../../../includes/crabout-md.md)] zu bekannten Typen finden Sie unter [Bekannte Typen in Datenverträgen](../../../../../docs/framework/wcf/feature-details/data-contract-known-types.md) und <xref:System.Runtime.Serialization.DataContractSerializer>.  
  
 Ein Beispiel zur Verwendung dieses Elements finden Sie unter [\<dataContractSerializer\>](../../../../../docs/framework/configure-apps/file-schema/wcf/datacontractserializer-element.md).  
  
 Dieses Konfigurationselement darf nicht über zwei Attribute gleichzeitig verfügen.  Falls beide Attribute festgelegt sind, tritt <xref:System.Configuration.ConfigurationErrorsException> auf.  
  
## Siehe auch  
 <xref:System.Runtime.Serialization.DataContractSerializer>   
 [Bekannte Typen in Datenverträgen](../../../../../docs/framework/wcf/feature-details/data-contract-known-types.md)   
 [\<dataContractSerializer\>](../../../../../docs/framework/configure-apps/file-schema/wcf/datacontractserializer-element.md)   
 [\<add\>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-declaredtypes-element.md)