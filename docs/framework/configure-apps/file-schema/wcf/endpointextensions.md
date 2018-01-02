---
title: '&lt;endpointExtensions&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 33396e0a-1fae-4616-b822-923584eebfd1
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 47aad13591e3a35433cafea3e49fff7fa6e7b7c2
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="ltendpointextensionsgt"></a>&lt;endpointExtensions&gt;
Dieser Abschnitt registriert einen neuen Standardendpunkt im Erweiterungsabschnitt einer Konfigurationsdatei auf Computer- oder Anwendungsebene. Sie können dieser Auflistung einen Standardendpunkt hinzufügen, indem Sie das `add`-Schlüsselwort verwenden und das `type`-Attribut des Elements auf den Endpunkttyp sowie das `name`-Attribut auf den Namen des Standardendpunkts festlegen.  
  
 Im folgenden Beispiel werden das `add`-Element sowie das `name`-Attribut zum Hinzufügen eines Standardendpunkts zum `<endpointExtensions>`-Abschnitt der Konfigurationsdatei verwendet.  
  
```xml  
<system.serviceModel>  
    <extensions>  
        <endpointExtensions>  
           <add name="udpDiscoveryEndpoint"  
                type="System.Discovery.UdpEndpointCollectionElement, System.Discovery.dll, Version=1.0.0.0, Culture=neutral, PublicKeyToken=ffffffffffffffff"/>  
        </endpointExtensions>   
    </extensions>  
</system.serviceModel>  
```  
  
 Nachdem der Standardendpunkt registriert wurde, können Sie ihn verwenden wie im folgenden Beispiel gezeigt. In der [ \<Endpunkt >](../../../../../docs/framework/configure-apps/file-schema/wcf/endpoint-element.md) Element, das `kind` Attribut gibt den Standardendpunkt im registriert wurde, die `<endpointExtensions>` Abschnitt. Die `endpointConfiguration` Attribut wird mit identisch sein, die `name` Attribut des Konfigurationselements für den Standardendpunkt im die `<standardEndpoints>` Abschnitt.  
  
```xml  
<system.serviceModel>  
    <services>  
      <service name="Service1">  
        <endpoint kind="udpDiscoveryEndpoint"  
                  endpointConfiguration="udpConfig" />  
      </service>  
    </services>  
    <standardEndpoints>  
      <udpDiscoveryEndpoint>  
        <standardEndpoint  
                  name="udpConfig"  
                  multicastAddress="soap.udp://239.255.255.250:3703"  
                  ... />  
      </udpDiscoveryEndpoint>  
    </standardEndpoints>  
  </system.serviceModel>  
```
