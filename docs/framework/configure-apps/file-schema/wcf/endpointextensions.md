---
title: '&lt;endpointExtensions&gt;'
ms.date: 03/30/2017
ms.assetid: 33396e0a-1fae-4616-b822-923584eebfd1
ms.openlocfilehash: 3883a23c679abc83d7cfe9011b7cdb7e4154adfe
ms.sourcegitcommit: 4ac80713f6faa220e5a119d5165308a58f7ccdc8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/09/2019
ms.locfileid: "54146445"
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
  
 Nachdem der Standardendpunkt registriert wurde, können Sie ihn verwenden wie im folgenden Beispiel gezeigt. In der [ \<Endpunkt >](../../../../../docs/framework/configure-apps/file-schema/wcf/endpoint-element.md) -Element, das `kind` Attribut gibt an, den standardendpunkttyp an, die in registriert wurde die `<endpointExtensions>` Abschnitt. Die `endpointConfiguration` Attribut werden identisch mit der `name` Attribut des Konfigurationselements für den Standardendpunkt im der `<standardEndpoints>` Abschnitt.  
  
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
      <standardEndpoint name="udpConfig"
                        multicastAddress="soap.udp://239.255.255.250:3703"
                        ... />
    </udpDiscoveryEndpoint>
  </standardEndpoints>
</system.serviceModel>
```  
  
