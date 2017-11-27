---
title: Transportsicherheit mit Windows-Authentifizierung
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
ms.assetid: 96dd26e2-46e7-4de0-9a29-4fcb05bf187b
caps.latest.revision: "17"
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.openlocfilehash: 68550646f806b30f072b4270a336698011db54d6
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="transport-security-with-windows-authentication"></a><span data-ttu-id="60eb0-102">Transportsicherheit mit Windows-Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="60eb0-102">Transport Security with Windows Authentication</span></span>
<span data-ttu-id="60eb0-103">Das folgende Szenario zeigt, wie ein [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]-Client und ein Dienst mit Windows-Sicherheit gesichert werden.</span><span class="sxs-lookup"><span data-stu-id="60eb0-103">The following scenario shows a [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] client and service secured by Windows security.</span></span> [!INCLUDE[crabout](../../../../includes/crabout-md.md)]<span data-ttu-id="60eb0-104">Programmierung, finden Sie unter [Vorgehensweise: Sichern eines Diensts mit Windows-Anmeldeinformationen](../../../../docs/framework/wcf/how-to-secure-a-service-with-windows-credentials.md).</span><span class="sxs-lookup"><span data-stu-id="60eb0-104"> programming, see [How to: Secure a Service with Windows Credentials](../../../../docs/framework/wcf/how-to-secure-a-service-with-windows-credentials.md).</span></span>  
  
 <span data-ttu-id="60eb0-105">Ein Intranetwebdienst zeigt Personalinformationen an.</span><span class="sxs-lookup"><span data-stu-id="60eb0-105">An intranet Web service displays human resources information.</span></span> <span data-ttu-id="60eb0-106">Der Client ist eine Windows Forms-Anwendung.</span><span class="sxs-lookup"><span data-stu-id="60eb0-106">The client is a Windows Form application.</span></span> <span data-ttu-id="60eb0-107">Die Anwendung wird in einer Domäne mit einem Kerberos-Controller bereitgestellt, der die Domäne sichert.</span><span class="sxs-lookup"><span data-stu-id="60eb0-107">The application is deployed in a domain with a Kerberos controller securing the domain.</span></span>  
  
 <span data-ttu-id="60eb0-108">![Transportsicherheit mit Windows-Authentifizierung](../../../../docs/framework/wcf/feature-details/media/securedbywindows.gif "SecuredByWindows")</span><span class="sxs-lookup"><span data-stu-id="60eb0-108">![Transport security with Windows authentication](../../../../docs/framework/wcf/feature-details/media/securedbywindows.gif "SecuredByWindows")</span></span>  
  
|<span data-ttu-id="60eb0-109">Merkmal</span><span class="sxs-lookup"><span data-stu-id="60eb0-109">Characteristic</span></span>|<span data-ttu-id="60eb0-110">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="60eb0-110">Description</span></span>|  
|--------------------|-----------------|  
|<span data-ttu-id="60eb0-111">Sicherheitsmodus</span><span class="sxs-lookup"><span data-stu-id="60eb0-111">Security Mode</span></span>|<span data-ttu-id="60eb0-112">Transport</span><span class="sxs-lookup"><span data-stu-id="60eb0-112">Transport</span></span>|  
|<span data-ttu-id="60eb0-113">Interoperabilität</span><span class="sxs-lookup"><span data-stu-id="60eb0-113">Interoperability</span></span>|<span data-ttu-id="60eb0-114">Nur [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]</span><span class="sxs-lookup"><span data-stu-id="60eb0-114">[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] only</span></span>|  
|<span data-ttu-id="60eb0-115">Authentifizierung (Server)</span><span class="sxs-lookup"><span data-stu-id="60eb0-115">Authentication (Server)</span></span><br /><br /> <span data-ttu-id="60eb0-116">Authentifizierung (Client)</span><span class="sxs-lookup"><span data-stu-id="60eb0-116">Authentication (Client)</span></span>|<span data-ttu-id="60eb0-117">Ja (mithilfe der integrierten Windows-Authentifizierung)</span><span class="sxs-lookup"><span data-stu-id="60eb0-117">Yes (using Windows integrated authentication)</span></span><br /><br /> <span data-ttu-id="60eb0-118">Ja (mithilfe der integrierten Windows-Authentifizierung)</span><span class="sxs-lookup"><span data-stu-id="60eb0-118">Yes (using Windows integrated authentication)</span></span>|  
|<span data-ttu-id="60eb0-119">Integrität</span><span class="sxs-lookup"><span data-stu-id="60eb0-119">Integrity</span></span>|<span data-ttu-id="60eb0-120">Ja</span><span class="sxs-lookup"><span data-stu-id="60eb0-120">Yes</span></span>|  
|<span data-ttu-id="60eb0-121">Vertraulichkeit</span><span class="sxs-lookup"><span data-stu-id="60eb0-121">Confidentiality</span></span>|<span data-ttu-id="60eb0-122">Ja</span><span class="sxs-lookup"><span data-stu-id="60eb0-122">Yes</span></span>|  
|<span data-ttu-id="60eb0-123">Transport</span><span class="sxs-lookup"><span data-stu-id="60eb0-123">Transport</span></span>|<span data-ttu-id="60eb0-124">NET.TCP</span><span class="sxs-lookup"><span data-stu-id="60eb0-124">NET.TCP</span></span>|  
|<span data-ttu-id="60eb0-125">Bindung</span><span class="sxs-lookup"><span data-stu-id="60eb0-125">Binding</span></span>|<xref:System.ServiceModel.NetTcpBinding>|  
  
## <a name="service"></a><span data-ttu-id="60eb0-126">Dienst</span><span class="sxs-lookup"><span data-stu-id="60eb0-126">Service</span></span>  
 <span data-ttu-id="60eb0-127">Der folgende Code und die folgende Konfiguration werden unabhängig voneinander ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="60eb0-127">The following code and configuration are meant to run independently.</span></span> <span data-ttu-id="60eb0-128">Führen Sie einen der folgenden Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="60eb0-128">Do one of the following:</span></span>  
  
-   <span data-ttu-id="60eb0-129">Erstellen Sie einen separaten Dienst, indem Sie den Code ohne Konfiguration verwenden.</span><span class="sxs-lookup"><span data-stu-id="60eb0-129">Create a stand-alone service using the code with no configuration.</span></span>  
  
-   <span data-ttu-id="60eb0-130">Erstellen Sie mit der angegebenen Konfiguration einen Dienst, aber definieren Sie keine Endpunkte.</span><span class="sxs-lookup"><span data-stu-id="60eb0-130">Create a service using the supplied configuration, but do not define any endpoints.</span></span>  
  
### <a name="code"></a><span data-ttu-id="60eb0-131">Code</span><span class="sxs-lookup"><span data-stu-id="60eb0-131">Code</span></span>  
 <span data-ttu-id="60eb0-132">Im folgenden Code wird gezeigt, wie ein Dienstendpunkt, der Windows-Sicherheit verwendet, erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="60eb0-132">The following code shows how to create a service endpoint that uses a Windows security.</span></span>  
  
 [!code-csharp[C_SecurityScenarios#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_securityscenarios/cs/source.cs#3)]
 [!code-vb[C_SecurityScenarios#3](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_securityscenarios/vb/source.vb#3)]  
  
### <a name="configuration"></a><span data-ttu-id="60eb0-133">Konfiguration</span><span class="sxs-lookup"><span data-stu-id="60eb0-133">Configuration</span></span>  
 <span data-ttu-id="60eb0-134">Die folgende Konfiguration kann statt des Codes verwendet werden, um den Dienstendpunkt einzurichten:</span><span class="sxs-lookup"><span data-stu-id="60eb0-134">The following configuration can be used instead of the code to set up the service endpoint:</span></span>  
  
```xml  
<?xml version="1.0" encoding="utf-8"?>  
<configuration>  
  <system.serviceModel>  
    <behaviors />  
    <services>  
      <service behaviorConfiguration="" name="ServiceModel.Calculator">  
        <endpoint address="net.tcp://localhost:8008/Calculator"   
                  binding="netTcpBinding"  
          bindingConfiguration="WindowsClientOverTcp"   
                  name="WindowsClientOverTcp"  
                  contract="ServiceModel.ICalculator" />  
      </service>  
    </services>  
    <bindings>  
      <netTcpBinding>  
        <binding name="WindowsClientOverTcp">  
          <security mode="Transport">  
            <transport clientCredentialType="Windows" />  
          </security>  
        </binding>  
      </netTcpBinding>  
    </bindings>  
    <client />  
  </system.serviceModel>  
</configuration>  
```  
  
## <a name="client"></a><span data-ttu-id="60eb0-135">Client</span><span class="sxs-lookup"><span data-stu-id="60eb0-135">Client</span></span>  
 <span data-ttu-id="60eb0-136">Der folgende Code und die folgende Konfiguration werden unabhängig voneinander ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="60eb0-136">The following code and configuration are meant to run independently.</span></span> <span data-ttu-id="60eb0-137">Führen Sie einen der folgenden Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="60eb0-137">Do one of the following:</span></span>  
  
-   <span data-ttu-id="60eb0-138">Erstellen Sie mit dem Code (und Clientcode) einen eigenständigen Client.</span><span class="sxs-lookup"><span data-stu-id="60eb0-138">Create a stand-alone client using the code (and client code).</span></span>  
  
-   <span data-ttu-id="60eb0-139">Erstellen Sie einen Client, der keine Endpunktadressen definiert.</span><span class="sxs-lookup"><span data-stu-id="60eb0-139">Create a client that does not define any endpoint addresses.</span></span> <span data-ttu-id="60eb0-140">Verwenden Sie stattdessen den Clientkonstruktor, der den Konfigurationsnamen als Argument verwendet.</span><span class="sxs-lookup"><span data-stu-id="60eb0-140">Instead, use the client constructor that takes the configuration name as an argument.</span></span> <span data-ttu-id="60eb0-141">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="60eb0-141">For example:</span></span>  
  
     [!code-csharp[C_SecurityScenarios#0](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_securityscenarios/cs/source.cs#0)]
     [!code-vb[C_SecurityScenarios#0](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_securityscenarios/vb/source.vb#0)]  
  
### <a name="code"></a><span data-ttu-id="60eb0-142">Code</span><span class="sxs-lookup"><span data-stu-id="60eb0-142">Code</span></span>  
 <span data-ttu-id="60eb0-143">Der folgende Code erstellt den Client.</span><span class="sxs-lookup"><span data-stu-id="60eb0-143">The following code creates the client.</span></span> <span data-ttu-id="60eb0-144">Die Bindung ist für die Verwendung der Transportmodussicherheit mit dem TCP-Transport konfiguriert, wobei der Clientanmeldeinformationstyp auf Windows festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="60eb0-144">The binding is configured to use the Transport mode security, with the TCP transport, with the client credential type set to Windows.</span></span>  
  
 [!code-csharp[C_SecurityScenarios#4](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_securityscenarios/cs/source.cs#4)]
 [!code-vb[C_SecurityScenarios#4](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_securityscenarios/vb/source.vb#4)]  
  
### <a name="configuration"></a><span data-ttu-id="60eb0-145">Konfiguration</span><span class="sxs-lookup"><span data-stu-id="60eb0-145">Configuration</span></span>  
 <span data-ttu-id="60eb0-146">Die folgende Konfiguration kann statt des Codes verwendet werden, um den Client zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="60eb0-146">The following configuration can be used instead of the code to create the client.</span></span>  
  
```xml  
<?xml version="1.0" encoding="utf-8"?>  
<configuration>  
  <system.serviceModel>  
    <bindings>  
      <netTcpBinding>  
        <binding name="NetTcpBinding_ICalculator" >  
          <security mode="Transport">  
            <transport clientCredentialType="Windows" />  
          </security>  
        </binding>  
      </netTcpBinding>  
    </bindings>  
    <client>  
      <endpoint address="net.tcp://localhost:8008/Calculator"   
                binding="netTcpBinding"            
                bindingConfiguration="NetTcpBinding_ICalculator"   
                contract="ICalculator"  
                name="NetTcpBinding_ICalculator">  
      </endpoint>  
    </client>  
  </system.serviceModel>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="60eb0-147">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="60eb0-147">See Also</span></span>  
 [<span data-ttu-id="60eb0-148">Sicherheit (Übersicht)</span><span class="sxs-lookup"><span data-stu-id="60eb0-148">Security Overview</span></span>](../../../../docs/framework/wcf/feature-details/security-overview.md)  
 [<span data-ttu-id="60eb0-149">Vorgehensweise: Sichern eines Dienstes mit Windows-Anmeldeinformationen</span><span class="sxs-lookup"><span data-stu-id="60eb0-149">How to: Secure a Service with Windows Credentials</span></span>](../../../../docs/framework/wcf/how-to-secure-a-service-with-windows-credentials.md)  
 [<span data-ttu-id="60eb0-150">Sicherheitsmodell für Windows Server AppFabric</span><span class="sxs-lookup"><span data-stu-id="60eb0-150">Security Model for Windows Server App Fabric</span></span>](http://go.microsoft.com/fwlink/?LinkID=201279&clcid=0x409)
