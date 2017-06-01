---
title: "&lt;system.runtime.serialization&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: a8cebf4c-06d2-4667-8f5b-c3e1fc90df6f
caps.latest.revision: 7
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 7
---
# &lt;system.runtime.serialization&gt;
Stellt das Stammelement für den <xref:System.Runtime.Serialization>\-Namespaceabschnitt dar und enthält Elemente zum Festlegen von <xref:System.Runtime.Serialization.DataContractSerializer>\-Optionen.  
  
 system.runtime.serialization  
  
## Syntax  
  
```  
  
<configuration>  
  <system.runtime.serialization>  
    <dataContractSerializer ignoreExtensionDataObject="Boolean"  
      maxItemsInObjectGraph="Integer">  
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
  
## Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute, untergeordnete Elemente sowie übergeordnete Elemente beschrieben.  
  
### Attribute  
 Keine  
  
### Untergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|------------------|  
|[\<dataContractSerializer\>](../../../../../docs/framework/configure-apps/file-schema/wcf/datacontractserializer-of-system-runtime-serialization.md)|Aktiviert die Hinzufügung bekannter, für die Deserialisierung verwendeter Typen.|  
  
### Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|------------------|  
|[\<configuration\>\-Element](../../../../../docs/framework/configure-apps/file-schema/configuration-element.md)|Das Element der obersten Ebene für die Konfiguration.|  
  
## Siehe auch  
 <xref:System.Runtime.Serialization>   
 [Verwenden von Datenverträgen](../../../../../docs/framework/wcf/feature-details/using-data-contracts.md)   
 [Bekannte Typen in Datenverträgen](../../../../../docs/framework/wcf/feature-details/data-contract-known-types.md)