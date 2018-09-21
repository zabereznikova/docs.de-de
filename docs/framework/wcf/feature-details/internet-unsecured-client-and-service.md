---
title: 'Internet: Ungesicherter Client und Dienst'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 97a10d79-3e7d-4bd1-9a99-fd9807fd70bc
author: BrucePerlerMS
manager: mbaldwin
ms.openlocfilehash: b2c71af169018f272a6ca538bba9191f9ddbc0dd
ms.sourcegitcommit: dfb2a100cfb4d3902c042f17b3204f49bc7635e7
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/21/2018
ms.locfileid: "46507988"
---
# <a name="internet-unsecured-client-and-service"></a><span data-ttu-id="d6fcc-102">Internet: Ungesicherter Client und Dienst</span><span class="sxs-lookup"><span data-stu-id="d6fcc-102">Internet Unsecured Client and Service</span></span>
<span data-ttu-id="d6fcc-103">Die folgende Abbildung zeigt ein Beispiel für einen öffentlichen, ungesicherten Windows Communication Foundation (WCF)-Client und Dienst.</span><span class="sxs-lookup"><span data-stu-id="d6fcc-103">The following illustration shows an example of a public, unsecured Windows Communication Foundation (WCF) client and service.</span></span>  
  
 <span data-ttu-id="d6fcc-104">![Unsichere Internetszenario und Dienstszenario](../../../../docs/framework/wcf/feature-details/media/publicunsecured.gif "PublicUnsecured")</span><span class="sxs-lookup"><span data-stu-id="d6fcc-104">![Unsecured Internet cleint and service scenario](../../../../docs/framework/wcf/feature-details/media/publicunsecured.gif "publicUnsecured")</span></span>  
  
|<span data-ttu-id="d6fcc-105">Merkmal</span><span class="sxs-lookup"><span data-stu-id="d6fcc-105">Characteristic</span></span>|<span data-ttu-id="d6fcc-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="d6fcc-106">Description</span></span>|  
|--------------------|-----------------|  
|<span data-ttu-id="d6fcc-107">Sicherheitsmodus</span><span class="sxs-lookup"><span data-stu-id="d6fcc-107">Security Mode</span></span>|<span data-ttu-id="d6fcc-108">Keine</span><span class="sxs-lookup"><span data-stu-id="d6fcc-108">None</span></span>|  
|<span data-ttu-id="d6fcc-109">Transport</span><span class="sxs-lookup"><span data-stu-id="d6fcc-109">Transport</span></span>|<span data-ttu-id="d6fcc-110">HTTP</span><span class="sxs-lookup"><span data-stu-id="d6fcc-110">HTTP</span></span>|  
|<span data-ttu-id="d6fcc-111">Bindung</span><span class="sxs-lookup"><span data-stu-id="d6fcc-111">Binding</span></span>|<span data-ttu-id="d6fcc-112"><xref:System.ServiceModel.BasicHttpBinding> im Code oder die [ \<BasicHttpBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/basichttpbinding.md) Element in der Konfiguration.</span><span class="sxs-lookup"><span data-stu-id="d6fcc-112"><xref:System.ServiceModel.BasicHttpBinding> in code, or the [\<basicHttpBinding>](../../../../docs/framework/configure-apps/file-schema/wcf/basichttpbinding.md) element in configuration.</span></span>|  
|<span data-ttu-id="d6fcc-113">Interoperabilität</span><span class="sxs-lookup"><span data-stu-id="d6fcc-113">Interoperability</span></span>|<span data-ttu-id="d6fcc-114">Mit vorhandenen Webdienstclients und Diensten</span><span class="sxs-lookup"><span data-stu-id="d6fcc-114">With existing Web service clients and services</span></span>|  
|<span data-ttu-id="d6fcc-115">Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="d6fcc-115">Authentication</span></span>|<span data-ttu-id="d6fcc-116">Keine</span><span class="sxs-lookup"><span data-stu-id="d6fcc-116">None</span></span>|  
|<span data-ttu-id="d6fcc-117">Integrität</span><span class="sxs-lookup"><span data-stu-id="d6fcc-117">Integrity</span></span>|<span data-ttu-id="d6fcc-118">Keine</span><span class="sxs-lookup"><span data-stu-id="d6fcc-118">None</span></span>|  
|<span data-ttu-id="d6fcc-119">Vertraulichkeit</span><span class="sxs-lookup"><span data-stu-id="d6fcc-119">Confidentiality</span></span>|<span data-ttu-id="d6fcc-120">Keine</span><span class="sxs-lookup"><span data-stu-id="d6fcc-120">None</span></span>|  
  
## <a name="service"></a><span data-ttu-id="d6fcc-121">Dienst</span><span class="sxs-lookup"><span data-stu-id="d6fcc-121">Service</span></span>  
 <span data-ttu-id="d6fcc-122">Der folgende Code und die folgende Konfiguration werden unabhängig voneinander ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="d6fcc-122">The following code and configuration are meant to run independently.</span></span> <span data-ttu-id="d6fcc-123">Führen Sie einen der folgenden Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="d6fcc-123">Do one of the following:</span></span>  
  
-   <span data-ttu-id="d6fcc-124">Erstellen Sie einen separaten Dienst, indem Sie den Code ohne Konfiguration verwenden.</span><span class="sxs-lookup"><span data-stu-id="d6fcc-124">Create a stand-alone service using the code with no configuration.</span></span>  
  
-   <span data-ttu-id="d6fcc-125">Erstellen Sie mit der angegebenen Konfiguration einen Dienst, aber definieren Sie keine Endpunkte.</span><span class="sxs-lookup"><span data-stu-id="d6fcc-125">Create a service using the supplied configuration, but do not define any endpoints.</span></span>  
  
### <a name="code"></a><span data-ttu-id="d6fcc-126">Code</span><span class="sxs-lookup"><span data-stu-id="d6fcc-126">Code</span></span>  
 <span data-ttu-id="d6fcc-127">Im folgenden Code wird gezeigt, wie ein Endpunkt ohne Sicherheit erstellt wird:</span><span class="sxs-lookup"><span data-stu-id="d6fcc-127">The following code shows how to create an endpoint with no security.</span></span> <span data-ttu-id="d6fcc-128">Standardmäßig verfügt die <xref:System.ServiceModel.BasicHttpBinding> über den Sicherheitsmodus <xref:System.ServiceModel.BasicHttpSecurityMode.None>.</span><span class="sxs-lookup"><span data-stu-id="d6fcc-128">By default, the <xref:System.ServiceModel.BasicHttpBinding> has the security mode set to <xref:System.ServiceModel.BasicHttpSecurityMode.None>.</span></span>  
  
 [!code-csharp[C_UnsecuredService#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_unsecuredservice/cs/source.cs#1)]
 [!code-vb[C_UnsecuredService#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_unsecuredservice/vb/source.vb#1)]  
  
### <a name="service-configuration"></a><span data-ttu-id="d6fcc-129">Dienstkonfiguration</span><span class="sxs-lookup"><span data-stu-id="d6fcc-129">Service Configuration</span></span>  
 <span data-ttu-id="d6fcc-130">Mit dem folgenden Code wird derselbe Endpunkt mithilfe von Konfiguration eingerichtet.</span><span class="sxs-lookup"><span data-stu-id="d6fcc-130">The following code sets up the same endpoint using configuration.</span></span>  
  
```xml  
<?xml version="1.0" encoding="utf-8"?>  
<configuration>  
  <system.serviceModel>  
    <behaviors />  
    <services>  
      <service behaviorConfiguration="" name="ServiceModel.Calculator">  
        <endpoint address="http://localhost/Calculator"   
                  binding="basicHttpBinding"  
                  bindingConfiguration="Basic_Unsecured"   
                  name="BasicHttp_ICalculator"  
                  contract="ServiceModel.ICalculator" />  
      </service>  
    </services>  
    <bindings>  
      <basicHttpBinding>  
        <binding name="Basic_Unsecured" />  
      </basicHttpBinding>  
    </bindings>  
    <client />  
  </system.serviceModel>  
</configuration>  
```  
  
## <a name="client"></a><span data-ttu-id="d6fcc-131">Client</span><span class="sxs-lookup"><span data-stu-id="d6fcc-131">Client</span></span>  
 <span data-ttu-id="d6fcc-132">Der folgende Code und die folgende Konfiguration werden unabhängig voneinander ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="d6fcc-132">The following code and configuration are meant to run independently.</span></span> <span data-ttu-id="d6fcc-133">Führen Sie einen der folgenden Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="d6fcc-133">Do one of the following:</span></span>  
  
-   <span data-ttu-id="d6fcc-134">Erstellen Sie mit dem Code (und Clientcode) einen eigenständigen Client.</span><span class="sxs-lookup"><span data-stu-id="d6fcc-134">Create a stand-alone client using the code (and client code).</span></span>  
  
-   <span data-ttu-id="d6fcc-135">Erstellen Sie einen Client, der keine Endpunktadressen definiert.</span><span class="sxs-lookup"><span data-stu-id="d6fcc-135">Create a client that does not define any endpoint addresses.</span></span> <span data-ttu-id="d6fcc-136">Verwenden Sie stattdessen den Clientkonstruktor, der den Konfigurationsnamen als Argument verwendet.</span><span class="sxs-lookup"><span data-stu-id="d6fcc-136">Instead, use the client constructor that takes the configuration name as an argument.</span></span> <span data-ttu-id="d6fcc-137">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="d6fcc-137">For example:</span></span>  
  
     [!code-csharp[C_SecurityScenarios#0](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_securityscenarios/cs/source.cs#0)]
     [!code-vb[C_SecurityScenarios#0](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_securityscenarios/vb/source.vb#0)]  
  
### <a name="code"></a><span data-ttu-id="d6fcc-138">Code</span><span class="sxs-lookup"><span data-stu-id="d6fcc-138">Code</span></span>  
 <span data-ttu-id="d6fcc-139">Der folgende Code zeigt einen grundlegenden WCF-Client, der auf einen ungesicherten Endpunkt zugreift.</span><span class="sxs-lookup"><span data-stu-id="d6fcc-139">The following code shows a basic WCF client that accesses an unsecured endpoint.</span></span>  
  
 [!code-csharp[C_UnsecuredClient#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_unsecuredclient/cs/source.cs#1)]
 [!code-vb[C_UnsecuredClient#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_unsecuredclient/vb/source.vb#1)]  
  
### <a name="client-configuration"></a><span data-ttu-id="d6fcc-140">Clientkonfiguration</span><span class="sxs-lookup"><span data-stu-id="d6fcc-140">Client Configuration</span></span>  
 <span data-ttu-id="d6fcc-141">Der folgende Code dient zum Konfigurieren des Clients.</span><span class="sxs-lookup"><span data-stu-id="d6fcc-141">The following code configures the client.</span></span>  
  
```xml  
<?xml version="1.0" encoding="utf-8"?>  
<configuration>  
  <system.serviceModel>  
    <bindings>  
      <basicHttpBinding>  
        <binding name="BasicHttpBinding_ICalculator" >  
          <security mode="None">  
          </security>  
        </binding>  
      </basicHttpBinding>  
    </bindings>  
    <client>  
      <endpoint address="http://localhost/Calculator/Unsecured"  
          binding="basicHttpBinding"   
          bindingConfiguration="BasicHttpBinding_ICalculator"  
          contract="ICalculator"   
          name="BasicHttpBinding_ICalculator" />  
    </client>  
  </system.serviceModel>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="d6fcc-142">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d6fcc-142">See Also</span></span>  
 [<span data-ttu-id="d6fcc-143">Häufige Sicherheitsszenarien</span><span class="sxs-lookup"><span data-stu-id="d6fcc-143">Common Security Scenarios</span></span>](../../../../docs/framework/wcf/feature-details/common-security-scenarios.md)  
 [<span data-ttu-id="d6fcc-144">Übersicht über die Sicherheit</span><span class="sxs-lookup"><span data-stu-id="d6fcc-144">Security Overview</span></span>](../../../../docs/framework/wcf/feature-details/security-overview.md)  
 [<span data-ttu-id="d6fcc-145">Sicherheitsmodell für Windows Server AppFabric</span><span class="sxs-lookup"><span data-stu-id="d6fcc-145">Security Model for Windows Server App Fabric</span></span>](https://go.microsoft.com/fwlink/?LinkID=201279&clcid=0x409)
