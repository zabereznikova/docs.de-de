---
title: "&lt;Host&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: be566d55-9d50-4b2e-985d-52a5cc26cbbb
caps.latest.revision: 7
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 7
---
# &lt;Host&gt;
Gibt die Einstellungen für einen Diensthost an.  
  
## Syntax  
  
```  
  
<host>  
      <baseAddresses>  
         <baseAddress baseAddress="string" />  
      </baseAddresses>  
      <timeOuts closeTimeout="TimeSpan"  
         openTimeout="TimeSpan" >  
</host>  
```  
  
## Typ  
 `Type`  
  
## Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### Attribute  
 Keine  
  
### Untergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|------------------|  
|[\<baseAddresses\>](../../../../../docs/framework/configure-apps/file-schema/wcf/baseaddresses.md)|Eine Auflistung an `baseAddress`\-Elementen, die die vom Diensthost verwendeten Basisadressen angeben.|  
|[\<timeOuts\>](../../../../../docs/framework/configure-apps/file-schema/wcf/timeouts.md)|Ein Konfigurationselement, das das für das Öffnen und Schließen des Diensthosts zulässige Zeitintervall angibt.|  
  
### Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|------------------|  
|[\<service\>](../../../../../docs/framework/configure-apps/file-schema/wcf/service.md)|Gibt die Einstellungen für einen [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)]\-Dienst an.|  
  
## Siehe auch  
 <xref:System.ServiceModel.Configuration.HostElement>   
 <xref:System.ServiceModel.ServiceHost>   
 [Hosting](../../../../../docs/framework/wcf/feature-details/hosting.md)