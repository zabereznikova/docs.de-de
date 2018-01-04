---
title: 'Internet: Ungesicherter Client und Dienst'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: 97a10d79-3e7d-4bd1-9a99-fd9807fd70bc
caps.latest.revision: "17"
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.workload: dotnet
ms.openlocfilehash: b202c4d67b48a9559afe035dc6b7bc95f6cc7779
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="internet-unsecured-client-and-service"></a><span data-ttu-id="6f03f-102">Internet: Ungesicherter Client und Dienst</span><span class="sxs-lookup"><span data-stu-id="6f03f-102">Internet Unsecured Client and Service</span></span>
<span data-ttu-id="6f03f-103">Die folgende Illustration zeigt ein Beispiel eines öffentlichen, ungesicherten [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]-Clients und eines Diensts an.</span><span class="sxs-lookup"><span data-stu-id="6f03f-103">The following illustration shows an example of a public, unsecured [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] client and service.</span></span>  
  
 <span data-ttu-id="6f03f-104">![Unsichere Internet Internetclient und Dienstszenario](../../../../docs/framework/wcf/feature-details/media/publicunsecured.gif "PublicUnsecured")</span><span class="sxs-lookup"><span data-stu-id="6f03f-104">![Unsecured Internet cleint and service scenario](../../../../docs/framework/wcf/feature-details/media/publicunsecured.gif "publicUnsecured")</span></span>  
  
|<span data-ttu-id="6f03f-105">Merkmal</span><span class="sxs-lookup"><span data-stu-id="6f03f-105">Characteristic</span></span>|<span data-ttu-id="6f03f-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="6f03f-106">Description</span></span>|  
|--------------------|-----------------|  
|<span data-ttu-id="6f03f-107">Sicherheitsmodus</span><span class="sxs-lookup"><span data-stu-id="6f03f-107">Security Mode</span></span>|<span data-ttu-id="6f03f-108">Keine</span><span class="sxs-lookup"><span data-stu-id="6f03f-108">None</span></span>|  
|<span data-ttu-id="6f03f-109">Transport</span><span class="sxs-lookup"><span data-stu-id="6f03f-109">Transport</span></span>|<span data-ttu-id="6f03f-110">HTTP</span><span class="sxs-lookup"><span data-stu-id="6f03f-110">HTTP</span></span>|  
|<span data-ttu-id="6f03f-111">Bindung</span><span class="sxs-lookup"><span data-stu-id="6f03f-111">Binding</span></span>|<span data-ttu-id="6f03f-112"><xref:System.ServiceModel.BasicHttpBinding>im Code oder die [ \<BasicHttpBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/basichttpbinding.md) Element in der Konfiguration.</span><span class="sxs-lookup"><span data-stu-id="6f03f-112"><xref:System.ServiceModel.BasicHttpBinding> in code, or the [\<basicHttpBinding>](../../../../docs/framework/configure-apps/file-schema/wcf/basichttpbinding.md) element in configuration.</span></span>|  
|<span data-ttu-id="6f03f-113">Interoperabilität</span><span class="sxs-lookup"><span data-stu-id="6f03f-113">Interoperability</span></span>|<span data-ttu-id="6f03f-114">Mit vorhandenen Webdienstclients und Diensten</span><span class="sxs-lookup"><span data-stu-id="6f03f-114">With existing Web service clients and services</span></span>|  
|<span data-ttu-id="6f03f-115">Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="6f03f-115">Authentication</span></span>|<span data-ttu-id="6f03f-116">Keine</span><span class="sxs-lookup"><span data-stu-id="6f03f-116">None</span></span>|  
|<span data-ttu-id="6f03f-117">Integrität</span><span class="sxs-lookup"><span data-stu-id="6f03f-117">Integrity</span></span>|<span data-ttu-id="6f03f-118">Keine</span><span class="sxs-lookup"><span data-stu-id="6f03f-118">None</span></span>|  
|<span data-ttu-id="6f03f-119">Vertraulichkeit</span><span class="sxs-lookup"><span data-stu-id="6f03f-119">Confidentiality</span></span>|<span data-ttu-id="6f03f-120">Keine</span><span class="sxs-lookup"><span data-stu-id="6f03f-120">None</span></span>|  
  
## <a name="service"></a><span data-ttu-id="6f03f-121">Dienst</span><span class="sxs-lookup"><span data-stu-id="6f03f-121">Service</span></span>  
 <span data-ttu-id="6f03f-122">Der folgende Code und die folgende Konfiguration werden unabhängig voneinander ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="6f03f-122">The following code and configuration are meant to run independently.</span></span> <span data-ttu-id="6f03f-123">Führen Sie einen der folgenden Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="6f03f-123">Do one of the following:</span></span>  
  
-   <span data-ttu-id="6f03f-124">Erstellen Sie einen separaten Dienst, indem Sie den Code ohne Konfiguration verwenden.</span><span class="sxs-lookup"><span data-stu-id="6f03f-124">Create a stand-alone service using the code with no configuration.</span></span>  
  
-   <span data-ttu-id="6f03f-125">Erstellen Sie mit der angegebenen Konfiguration einen Dienst, aber definieren Sie keine Endpunkte.</span><span class="sxs-lookup"><span data-stu-id="6f03f-125">Create a service using the supplied configuration, but do not define any endpoints.</span></span>  
  
### <a name="code"></a><span data-ttu-id="6f03f-126">Code</span><span class="sxs-lookup"><span data-stu-id="6f03f-126">Code</span></span>  
 <span data-ttu-id="6f03f-127">Im folgenden Code wird gezeigt, wie ein Endpunkt ohne Sicherheit erstellt wird:</span><span class="sxs-lookup"><span data-stu-id="6f03f-127">The following code shows how to create an endpoint with no security.</span></span> <span data-ttu-id="6f03f-128">Standardmäßig verfügt die <xref:System.ServiceModel.BasicHttpBinding> über den Sicherheitsmodus <xref:System.ServiceModel.BasicHttpSecurityMode.None>.</span><span class="sxs-lookup"><span data-stu-id="6f03f-128">By default, the <xref:System.ServiceModel.BasicHttpBinding> has the security mode set to <xref:System.ServiceModel.BasicHttpSecurityMode.None>.</span></span>  
  
 [!code-csharp[C_UnsecuredService#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_unsecuredservice/cs/source.cs#1)]
 [!code-vb[C_UnsecuredService#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_unsecuredservice/vb/source.vb#1)]  
  
### <a name="service-configuration"></a><span data-ttu-id="6f03f-129">Dienstkonfiguration</span><span class="sxs-lookup"><span data-stu-id="6f03f-129">Service Configuration</span></span>  
 <span data-ttu-id="6f03f-130">Mit dem folgenden Code wird derselbe Endpunkt mithilfe von Konfiguration eingerichtet.</span><span class="sxs-lookup"><span data-stu-id="6f03f-130">The following code sets up the same endpoint using configuration.</span></span>  
  
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
  
## <a name="client"></a><span data-ttu-id="6f03f-131">Client</span><span class="sxs-lookup"><span data-stu-id="6f03f-131">Client</span></span>  
 <span data-ttu-id="6f03f-132">Der folgende Code und die folgende Konfiguration werden unabhängig voneinander ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="6f03f-132">The following code and configuration are meant to run independently.</span></span> <span data-ttu-id="6f03f-133">Führen Sie einen der folgenden Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="6f03f-133">Do one of the following:</span></span>  
  
-   <span data-ttu-id="6f03f-134">Erstellen Sie mit dem Code (und Clientcode) einen eigenständigen Client.</span><span class="sxs-lookup"><span data-stu-id="6f03f-134">Create a stand-alone client using the code (and client code).</span></span>  
  
-   <span data-ttu-id="6f03f-135">Erstellen Sie einen Client, der keine Endpunktadressen definiert.</span><span class="sxs-lookup"><span data-stu-id="6f03f-135">Create a client that does not define any endpoint addresses.</span></span> <span data-ttu-id="6f03f-136">Verwenden Sie stattdessen den Clientkonstruktor, der den Konfigurationsnamen als Argument verwendet.</span><span class="sxs-lookup"><span data-stu-id="6f03f-136">Instead, use the client constructor that takes the configuration name as an argument.</span></span> <span data-ttu-id="6f03f-137">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="6f03f-137">For example:</span></span>  
  
     [!code-csharp[C_SecurityScenarios#0](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_securityscenarios/cs/source.cs#0)]
     [!code-vb[C_SecurityScenarios#0](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_securityscenarios/vb/source.vb#0)]  
  
### <a name="code"></a><span data-ttu-id="6f03f-138">Code</span><span class="sxs-lookup"><span data-stu-id="6f03f-138">Code</span></span>  
 <span data-ttu-id="6f03f-139">Im folgenden Code wird ein grundlegender [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-Client gezeigt, der auf einen ungesicherten Endpunkt zugreift.</span><span class="sxs-lookup"><span data-stu-id="6f03f-139">The following code shows a basic [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] client that accesses an unsecured endpoint.</span></span>  
  
 [!code-csharp[C_UnsecuredClient#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_unsecuredclient/cs/source.cs#1)]
 [!code-vb[C_UnsecuredClient#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_unsecuredclient/vb/source.vb#1)]  
  
### <a name="client-configuration"></a><span data-ttu-id="6f03f-140">Clientkonfiguration</span><span class="sxs-lookup"><span data-stu-id="6f03f-140">Client Configuration</span></span>  
 <span data-ttu-id="6f03f-141">Der folgende Code dient zum Konfigurieren des Clients.</span><span class="sxs-lookup"><span data-stu-id="6f03f-141">The following code configures the client.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="6f03f-142">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="6f03f-142">See Also</span></span>  
 [<span data-ttu-id="6f03f-143">Häufige Sicherheitsszenarien</span><span class="sxs-lookup"><span data-stu-id="6f03f-143">Common Security Scenarios</span></span>](../../../../docs/framework/wcf/feature-details/common-security-scenarios.md)  
 [<span data-ttu-id="6f03f-144">Übersicht über die Sicherheit</span><span class="sxs-lookup"><span data-stu-id="6f03f-144">Security Overview</span></span>](../../../../docs/framework/wcf/feature-details/security-overview.md)  
 [<span data-ttu-id="6f03f-145">Sicherheitsmodell für Windows Server AppFabric</span><span class="sxs-lookup"><span data-stu-id="6f03f-145">Security Model for Windows Server App Fabric</span></span>](http://go.microsoft.com/fwlink/?LinkID=201279&clcid=0x409)
