---
title: "&lt;dataContractSerializer&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "<dataContractSerializer>-Element"
  - "DataContractSerializer"
  - "dataContractSerializer-Element"
  - "Bekannte Typen"
ms.assetid: f41fb4d5-24e7-4059-8010-286a30bfea93
caps.latest.revision: 17
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 17
---
# &lt;dataContractSerializer&gt;
Enthält Konfigurationsdaten für den <xref:System.Runtime.Serialization.DataContractSerializer>.  Dieses Element befindet sich in zwei verschiedenen Hierarchien.  Eine wird im folgenden Abschnitt "Schemahierarchie" aufgeführt, die andere im Abschnitt "Hinweise".  
  
## Syntax  
  
```  
  
<dataContractSerializer ignoreExtensionDataObject="Boolean"  
   maxItemsInObjectGraph="Integer" />  
```  
  
## Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### Attribute  
  
|Element|Beschreibung|  
|-------------|------------------|  
|IgnoreExtensionDataObject|Ein boolescher Wert, der angibt, ob vom Endpunkt bereitgestellte Daten ignoriert werden sollen, wenn dieser serialisiert oder deserialisiert wird.  Dieses Attribut kann nur im `<dataContractSerializer>` unter dem `<behavior>`\-Element festgelegt werden.|  
|maxItemsInObjectGraph|Eine ganze Zahl, die die maximale Anzahl der zu serialisierenden oder zu deserialisierenden Elemente angibt.  Dieses Attribut hat den Wert 65536.|  
  
### Untergeordnete Elemente  
 Keine  
  
### Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|------------------|  
|[\<Verhalten\>](../../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-servicebehaviors.md)|Eine Auflistung der Einstellungen für das Verhalten eines Diensts.|  
|[\<system.runtime.serialization\>](../../../../../docs/framework/configure-apps/file-schema/wcf/system-runtime-serialization.md)|Stellt das Stammelement für den <xref:System.Runtime.Serialization>\-Namespaceabschnitt dar und enthält Elemente zum Festlegen von <xref:System.Runtime.Serialization.DataContractSerializer>\-Optionen.|  
  
## Hinweise  
 Wie in der Einführung dieses Themas erwähnt, ist dies die zweite Hierarchie, in der sich das \<X509Extension\>\-Element befindet.  
  
 [\<system.runtime.serialization\>](../../../../../docs/framework/configure-apps/file-schema/wcf/system-runtime-serialization.md)  
  
 [\<dataContractSerializer\>](../../../../../docs/framework/configure-apps/file-schema/wcf/datacontractserializer-element.md)  
  
 Weitere Informationen über bekannte Typen finden Sie unter <xref:System.Runtime.Serialization.DataContractSerializer>.  
  
## Siehe auch  
 <xref:System.Runtime.Serialization.DataContractSerializer>   
 <xref:System.ServiceModel.Description.DataContractSerializerOperationBehavior>   
 <xref:System.ServiceModel.Configuration.DataContractSerializerElement>   
 [Bekannte Typen in Datenverträgen](../../../../../docs/framework/wcf/feature-details/data-contract-known-types.md)   
 [Datenübertragung und Serialisierung](../../../../../docs/framework/wcf/feature-details/data-transfer-and-serialization.md)