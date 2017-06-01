---
title: "&lt;endpointExtensions&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 33396e0a-1fae-4616-b822-923584eebfd1
caps.latest.revision: 3
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 3
---
# &lt;endpointExtensions&gt;
Dieser Abschnitt registriert einen neuen Standardendpunkt im Erweiterungsabschnitt einer Konfigurationsdatei auf Computer\- oder Anwendungsebene.  Sie können dieser Auflistung einen Standardendpunkt hinzufügen, indem Sie das `add`\-Schlüsselwort verwenden und das `type`\-Attribut des Elements auf den Endpunkttyp sowie das `name`\-Attribut auf den Namen des Standardendpunkts festlegen.  
  
 Im folgenden Beispiel werden das `add`\-Element sowie das `name`\-Attribut zum Hinzufügen eines Standardendpunkts zum `<endpointExtensions>`\-Abschnitt der Konfigurationsdatei verwendet.  
  
```  
<system.serviceModel>  
    <extensions>  
        <endpointExtensions>  
           <add name="udpDiscoveryEndpoint"  
                type="System.Discovery.UdpEndpointCollectionElement, System.Discovery.dll, Version=1.0.0.0, Culture=neutral, PublicKeyToken=ffffffffffffffff"/>  
        </endpointExtensions>   
    </extensions>  
</system.serviceModel>  
```  
  
 Nachdem der Standardendpunkt registriert wurde, können Sie ihn verwenden wie im folgenden Beispiel gezeigt.  Im [\<Endpunkt \(endpoint\)\>](../../../../../docs/framework/configure-apps/file-schema/wcf/endpoint-element.md)\-Element gibt das `kind`\-Attribut den Standardendpunkttyp an, der im Abschnitt `<endpointExtensions>` registriert wurde.  Das `endpointConfiguration`\-Attribut entspricht dem `name`\-Attribut des Konfigurationselements für den Standardendpunkt im Abschnitt `<standardEndpoints>`.  
  
```  
  
<system.serviceModel>  
    <services>  
      <service name="Service1">  
        <endpoint kind="udpDiscoveryEndpoint"  
                  endpointConfiguration="udpConfig" />  
      </service>  
    </services>  
    <standardEndpoints>  
      <udpDiscoveryEndpoint>  
        <standardEndpoint  
                  name="udpConfig"  
                  multicastAddress="soap.udp://239.255.255.250:3703"  
                  ... />  
      </udpDiscoveryEndpoint>  
    </standardEndpoints>  
  </system.serviceModel>  
  
```