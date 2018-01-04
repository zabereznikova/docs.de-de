---
title: 'Intranet: Ungesicherter Client und Dienst'
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
ms.assetid: f450f5d4-3547-47ec-9320-2809e6a12634
caps.latest.revision: "20"
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.workload: dotnet
ms.openlocfilehash: 0cfd98d401921c47bd85f8d4089e3efb437ca6b7
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="intranet-unsecured-client-and-service"></a><span data-ttu-id="40aff-102">Intranet: Ungesicherter Client und Dienst</span><span class="sxs-lookup"><span data-stu-id="40aff-102">Intranet Unsecured Client and Service</span></span>
<span data-ttu-id="40aff-103">In der folgenden Darstellung sehen Sie einen einfachen [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]-Dienst, mit dem einer [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-Anwendung Informationen in einem sicheren privaten Netzwerk zur Verfügung gestellt werden.</span><span class="sxs-lookup"><span data-stu-id="40aff-103">The following illustration depicts a simple [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] service developed to provide information on a secure private network to a [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] application.</span></span> <span data-ttu-id="40aff-104">Sicherheit ist nicht erforderlich, da die Daten eher unwichtig sind, das Netzwerk als grundsätzlich sicher eingestuft wird oder Sicherheit durch eine Ebene unterhalb der [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-Infrastruktur bereitgestellt wird.</span><span class="sxs-lookup"><span data-stu-id="40aff-104">Security is not required because the data is of low importance, the network is expected to be inherently secure, or security is provided by a layer below the [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] infrastructure.</span></span>  
  
 <span data-ttu-id="40aff-105">![Intranet: ungesicherter Client und Dienstszenario](../../../../docs/framework/wcf/feature-details/media/unsecuredwebservice.gif "UnsecuredWebService")</span><span class="sxs-lookup"><span data-stu-id="40aff-105">![Intranet unsecured client and service scenario](../../../../docs/framework/wcf/feature-details/media/unsecuredwebservice.gif "UnsecuredWebService")</span></span>  
  
|<span data-ttu-id="40aff-106">Merkmal</span><span class="sxs-lookup"><span data-stu-id="40aff-106">Characteristic</span></span>|<span data-ttu-id="40aff-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="40aff-107">Description</span></span>|  
|--------------------|-----------------|  
|<span data-ttu-id="40aff-108">Sicherheitsmodus</span><span class="sxs-lookup"><span data-stu-id="40aff-108">Security Mode</span></span>|<span data-ttu-id="40aff-109">Keine</span><span class="sxs-lookup"><span data-stu-id="40aff-109">None</span></span>|  
|<span data-ttu-id="40aff-110">Transport</span><span class="sxs-lookup"><span data-stu-id="40aff-110">Transport</span></span>|<span data-ttu-id="40aff-111">TCP</span><span class="sxs-lookup"><span data-stu-id="40aff-111">TCP</span></span>|  
|<span data-ttu-id="40aff-112">Bindung</span><span class="sxs-lookup"><span data-stu-id="40aff-112">Binding</span></span>|<xref:System.ServiceModel.NetTcpBinding>|  
|<span data-ttu-id="40aff-113">Interoperabilität</span><span class="sxs-lookup"><span data-stu-id="40aff-113">Interoperability</span></span>|<span data-ttu-id="40aff-114">Nur [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]</span><span class="sxs-lookup"><span data-stu-id="40aff-114">[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] only</span></span>|  
|<span data-ttu-id="40aff-115">Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="40aff-115">Authentication</span></span>|<span data-ttu-id="40aff-116">Keine</span><span class="sxs-lookup"><span data-stu-id="40aff-116">None</span></span>|  
|<span data-ttu-id="40aff-117">Integrität</span><span class="sxs-lookup"><span data-stu-id="40aff-117">Integrity</span></span>|<span data-ttu-id="40aff-118">Keine</span><span class="sxs-lookup"><span data-stu-id="40aff-118">None</span></span>|  
|<span data-ttu-id="40aff-119">Vertraulichkeit</span><span class="sxs-lookup"><span data-stu-id="40aff-119">Confidentiality</span></span>|<span data-ttu-id="40aff-120">Keine</span><span class="sxs-lookup"><span data-stu-id="40aff-120">None</span></span>|  
  
## <a name="service"></a><span data-ttu-id="40aff-121">Dienst</span><span class="sxs-lookup"><span data-stu-id="40aff-121">Service</span></span>  
 <span data-ttu-id="40aff-122">Der folgende Code und die folgende Konfiguration werden unabhängig voneinander ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="40aff-122">The following code and configuration are meant to run independently.</span></span> <span data-ttu-id="40aff-123">Führen Sie einen der folgenden Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="40aff-123">Do one of the following:</span></span>  
  
-   <span data-ttu-id="40aff-124">Erstellen Sie einen separaten Dienst, indem Sie den Code ohne Konfiguration verwenden.</span><span class="sxs-lookup"><span data-stu-id="40aff-124">Create a stand-alone service using the code with no configuration.</span></span>  
  
-   <span data-ttu-id="40aff-125">Erstellen Sie mit der angegebenen Konfiguration einen Dienst, aber definieren Sie keine Endpunkte.</span><span class="sxs-lookup"><span data-stu-id="40aff-125">Create a service using the supplied configuration, but do not define any endpoints.</span></span>  
  
### <a name="code"></a><span data-ttu-id="40aff-126">Code</span><span class="sxs-lookup"><span data-stu-id="40aff-126">Code</span></span>  
 <span data-ttu-id="40aff-127">Im folgenden Code wird gezeigt, wie ein Endpunkt ohne Sicherheit erstellt wird:</span><span class="sxs-lookup"><span data-stu-id="40aff-127">The following code shows how to create an endpoint with no security:</span></span>  
  
 [!code-csharp[C_UnsecuredService#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_unsecuredservice/cs/source.cs#2)]
 [!code-vb[C_UnsecuredService#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_unsecuredservice/vb/source.vb#2)]  
  
### <a name="configuration"></a><span data-ttu-id="40aff-128">Konfiguration</span><span class="sxs-lookup"><span data-stu-id="40aff-128">Configuration</span></span>  
 <span data-ttu-id="40aff-129">Mit dem folgenden Code wird derselbe Endpunkt mithilfe von Konfiguration eingerichtet:</span><span class="sxs-lookup"><span data-stu-id="40aff-129">The following code sets up the same endpoint using configuration:</span></span>  
  
```xml  
<?xml version="1.0" encoding="utf-8"?>  
<configuration>  
  <system.serviceModel>  
    <behaviors />  
    <services>  
      <service behaviorConfiguration=""   
               name="ServiceModel.Calculator">  
        <endpoint address="net.tcp://localhost:8008/Calculator"   
                  binding="netTcpBinding"  
                  bindingConfiguration="tcp_Unsecured"   
                  name="netTcp_ICalculator"  
                  contract="ServiceModel.ICalculator" />  
      </service>  
    </services>  
    <bindings>  
      <netTcpBinding>  
        <binding name="tcp_Unsecured">  
          <security mode="None" />  
        </binding>  
      </netTcpBinding>  
    </bindings>  
    <client />  
  </system.serviceModel>  
</configuration>  
```  
  
## <a name="client"></a><span data-ttu-id="40aff-130">Client</span><span class="sxs-lookup"><span data-stu-id="40aff-130">Client</span></span>  
 <span data-ttu-id="40aff-131">Der folgende Code und die folgende Konfiguration werden unabhängig voneinander ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="40aff-131">The following code and configuration are meant to run independently.</span></span> <span data-ttu-id="40aff-132">Führen Sie einen der folgenden Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="40aff-132">Do one of the following:</span></span>  
  
-   <span data-ttu-id="40aff-133">Erstellen Sie mit dem Code (und Clientcode) einen eigenständigen Client.</span><span class="sxs-lookup"><span data-stu-id="40aff-133">Create a stand-alone client using the code (and client code).</span></span>  
  
-   <span data-ttu-id="40aff-134">Erstellen Sie einen Client, der keine Endpunktadressen definiert.</span><span class="sxs-lookup"><span data-stu-id="40aff-134">Create a client that does not define any endpoint addresses.</span></span> <span data-ttu-id="40aff-135">Verwenden Sie stattdessen den Clientkonstruktor, der den Konfigurationsnamen als Argument verwendet.</span><span class="sxs-lookup"><span data-stu-id="40aff-135">Instead, use the client constructor that takes the configuration name as an argument.</span></span> <span data-ttu-id="40aff-136">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="40aff-136">For example:</span></span>  
  
     [!code-csharp[C_SecurityScenarios#0](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_securityscenarios/cs/source.cs#0)]
     [!code-vb[C_SecurityScenarios#0](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_securityscenarios/vb/source.vb#0)]  
  
### <a name="code"></a><span data-ttu-id="40aff-137">Code</span><span class="sxs-lookup"><span data-stu-id="40aff-137">Code</span></span>  
 <span data-ttu-id="40aff-138">Im folgenden Code wird ein Basis-[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-Client gezeigt, der mit dem TCP-Protokoll auf einen ungesicherten Endpunkt zugreift.</span><span class="sxs-lookup"><span data-stu-id="40aff-138">The following code shows a basic [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] client that accesses an unsecured endpoint using the TCP protocol.</span></span>  
  
 [!code-csharp[C_UnsecuredClient#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_unsecuredclient/cs/source.cs#2)]
 [!code-vb[C_UnsecuredClient#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_unsecuredclient/vb/source.vb#2)]  
  
### <a name="configuration"></a><span data-ttu-id="40aff-139">Konfiguration</span><span class="sxs-lookup"><span data-stu-id="40aff-139">Configuration</span></span>  
 <span data-ttu-id="40aff-140">Der folgende Konfigurationscode gilt für den Client:</span><span class="sxs-lookup"><span data-stu-id="40aff-140">The following configuration code applies to the client:</span></span>  
  
```xml  
<?xml version="1.0" encoding="utf-8"?>  
<configuration>  
  <system.serviceModel>  
    <bindings>  
      <netTcpBinding>  
        <binding name="NetTcpBinding_ICalculator" >  
          <security mode="None">  
          </security>  
        </binding>  
      </netTcpBinding>  
    </bindings>  
    <client>  
      <endpoint address="net.tcp://machineName:8008/Calculator "  
                binding="netTcpBinding"   
                bindingConfiguration="NetTcpBinding_ICalculator"  
                contract="ICalculator"   
                name="NetTcpBinding_ICalculator" />  
    </client>  
  </system.serviceModel>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="40aff-141">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="40aff-141">See Also</span></span>  
 <xref:System.ServiceModel.NetTcpBinding>  
 [<span data-ttu-id="40aff-142">Übersicht über die Sicherheit</span><span class="sxs-lookup"><span data-stu-id="40aff-142">Security Overview</span></span>](../../../../docs/framework/wcf/feature-details/security-overview.md)  
 [<span data-ttu-id="40aff-143">Sicherheitsmodell für Windows Server AppFabric</span><span class="sxs-lookup"><span data-stu-id="40aff-143">Security Model for Windows Server App Fabric</span></span>](http://go.microsoft.com/fwlink/?LinkID=201279&clcid=0x409)
