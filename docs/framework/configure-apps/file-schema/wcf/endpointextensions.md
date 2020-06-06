---
title: <endpointExtensions>
ms.date: 03/30/2017
ms.assetid: 33396e0a-1fae-4616-b822-923584eebfd1
ms.openlocfilehash: fe57cb84cfa70b1f6b92abf1dbac89ddad9d4dc8
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/06/2020
ms.locfileid: "69925700"
---
# \<endpointExtensions>
<span data-ttu-id="23ca2-101">Dieser Abschnitt registriert einen neuen Standardendpunkt im Erweiterungsabschnitt einer Konfigurationsdatei auf Computer- oder Anwendungsebene.</span><span class="sxs-lookup"><span data-stu-id="23ca2-101">This section registers a new standard endpoint in the extensions section in a machine or application configuration file.</span></span> <span data-ttu-id="23ca2-102">Sie können dieser Auflistung einen Standardendpunkt hinzufügen, indem Sie das `add`-Schlüsselwort verwenden und das `type`-Attribut des Elements auf den Endpunkttyp sowie das `name`-Attribut auf den Namen des Standardendpunkts festlegen.</span><span class="sxs-lookup"><span data-stu-id="23ca2-102">You can add a standard endpoint to this collection by using the `add` keyword, and setting the `type` attribute of the element to the endpoint type, as well as the `name` attribute to the name of the standard endpoint.</span></span>  
  
 <span data-ttu-id="23ca2-103">Im folgenden Beispiel werden das `add`-Element sowie das `name`-Attribut zum Hinzufügen eines Standardendpunkts zum `<endpointExtensions>`-Abschnitt der Konfigurationsdatei verwendet.</span><span class="sxs-lookup"><span data-stu-id="23ca2-103">The following example uses the `add` element, as well as the `name` attribute to add a standard endpoint to the `<endpointExtensions>` section of the configuration file.</span></span>  
  
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
  
 <span data-ttu-id="23ca2-104">Nachdem der Standardendpunkt registriert wurde, können Sie ihn verwenden wie im folgenden Beispiel gezeigt.</span><span class="sxs-lookup"><span data-stu-id="23ca2-104">After the standard endpoint has been registered, you can use it as shown in the following example.</span></span> <span data-ttu-id="23ca2-105">Im- [\<endpoint>](endpoint-element.md) Element gibt das- `kind` Attribut den standardend Punkttyp an, der im-Abschnitt registriert wurde `<endpointExtensions>` .</span><span class="sxs-lookup"><span data-stu-id="23ca2-105">In the [\<endpoint>](endpoint-element.md) element, the `kind` attribute specifies the standard endpoint type that has been registered in the `<endpointExtensions>` section.</span></span> <span data-ttu-id="23ca2-106">Das- `endpointConfiguration` Attribut ist mit dem- `name` Attribut des-Konfigurations Elements des Standard Endpunkts im- `<standardEndpoints>` Abschnitt identisch.</span><span class="sxs-lookup"><span data-stu-id="23ca2-106">The `endpointConfiguration` attribute will be identical to the `name` attribute of the configuration element of the standard endpoint in the `<standardEndpoints>` section.</span></span>  
  
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
