---
title: <extensions>
ms.date: 03/30/2017
ms.assetid: bcfe5c44-04ef-4a20-96a5-90bfadf39623
ms.openlocfilehash: c811162c17417144432f97fd9a47b2e02ecafbe2
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91151180"
---
# \<extensions>

<span data-ttu-id="e092f-101">Dieses Konfigurationselement enthält eine Auflistung von XML-Elementen mit benutzerdefinierten Metadaten, die mit den standardmäßigen sichtbaren Metadaten (EPR, ContractTypeName, BindingName, Bereich und ListenURI) veröffentlicht werden sollen.</span><span class="sxs-lookup"><span data-stu-id="e092f-101">This configuration element contains a collection of XML elements that contain custom metadata to be published along with the standard discoverable metadata (EPR, ContractTypeName, BindingName, Scope and ListenURI).</span></span> <span data-ttu-id="e092f-102">Es folgt ein Beispiel zur Verwendung dieses Konfigurationselements.</span><span class="sxs-lookup"><span data-stu-id="e092f-102">The following is an example of using this configuration element.</span></span>  
  
```xml  
<services>
  <service name="CalculatorService"
           behaviorConfiguration="CalculatorServiceBehavior">
    <endpoint binding="basicHttpBinding"
              address="calculator"
              contract="ICalculatorService"
              behaviorConfiguration="calculatorEndpointBehavior" />
  </service>
</services>
<behaviors>
  <serviceBehaviors>
    <behavior name="CalculatorServiceBehavior">
      <serviceDiscovery />
    </behavior>
  </serviceBehaviors>
  <endpointBehaviors>
    <behavior name="calculatorEndpointBehavior">
      <endpointDiscovery enable="true">
        <extensions>
          <e:Publisher xmlns:e="http://example.org">
            <e:Name>The Example Organization</e:Name>
            <e:Address>One Example Way, ExampleTown, EX 12345</e:Address>
            <e:Contact>support@example.org</e:Contact>
          </e:Publisher>
          <AnotherCustomMetadata>Custom Metadata</AnotherCustomMetadata>
        </extensions>
      </endpointDiscovery>
    </behavior>
  </endpointBehaviors>
</behaviors>
```  
  
## <a name="see-also"></a><span data-ttu-id="e092f-103">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="e092f-103">See also</span></span>

- <xref:System.ServiceModel.Discovery.EndpointDiscoveryBehavior>
