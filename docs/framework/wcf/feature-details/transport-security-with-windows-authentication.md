---
title: Transportsicherheit mit Windows-Authentifizierung
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: 96dd26e2-46e7-4de0-9a29-4fcb05bf187b
caps.latest.revision: 17
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.workload:
- dotnet
ms.openlocfilehash: 5effb18435241b00c3036fd23e15ef5ce485b646
ms.sourcegitcommit: 94d33cadc5ff81d2ac389bf5f26422c227832052
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/30/2018
---
# <a name="transport-security-with-windows-authentication"></a><span data-ttu-id="15941-102">Transportsicherheit mit Windows-Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="15941-102">Transport Security with Windows Authentication</span></span>
<span data-ttu-id="15941-103">Das folgende Szenario zeigt, wie ein [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]-Client und ein Dienst mit Windows-Sicherheit gesichert werden.</span><span class="sxs-lookup"><span data-stu-id="15941-103">The following scenario shows a [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] client and service secured by Windows security.</span></span> <span data-ttu-id="15941-104">Weitere Informationen zur Programmierung finden Sie unter [Vorgehensweise: Sichern eines Diensts mit Windows-Anmeldeinformationen](../../../../docs/framework/wcf/how-to-secure-a-service-with-windows-credentials.md).</span><span class="sxs-lookup"><span data-stu-id="15941-104">For more information about programming, see [How to: Secure a Service with Windows Credentials](../../../../docs/framework/wcf/how-to-secure-a-service-with-windows-credentials.md).</span></span>  
  
 <span data-ttu-id="15941-105">Ein Intranetwebdienst zeigt Personalinformationen an.</span><span class="sxs-lookup"><span data-stu-id="15941-105">An intranet Web service displays human resources information.</span></span> <span data-ttu-id="15941-106">Der Client ist eine Windows Forms-Anwendung.</span><span class="sxs-lookup"><span data-stu-id="15941-106">The client is a Windows Form application.</span></span> <span data-ttu-id="15941-107">Die Anwendung wird in einer Domäne mit einem Kerberos-Controller bereitgestellt, der die Domäne sichert.</span><span class="sxs-lookup"><span data-stu-id="15941-107">The application is deployed in a domain with a Kerberos controller securing the domain.</span></span>  
  
 <span data-ttu-id="15941-108">![Transportsicherheit mit Windows-Authentifizierung](../../../../docs/framework/wcf/feature-details/media/securedbywindows.gif "SecuredByWindows")</span><span class="sxs-lookup"><span data-stu-id="15941-108">![Transport security with Windows authentication](../../../../docs/framework/wcf/feature-details/media/securedbywindows.gif "SecuredByWindows")</span></span>  
  
|<span data-ttu-id="15941-109">Merkmal</span><span class="sxs-lookup"><span data-stu-id="15941-109">Characteristic</span></span>|<span data-ttu-id="15941-110">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="15941-110">Description</span></span>|  
|--------------------|-----------------|  
|<span data-ttu-id="15941-111">Sicherheitsmodus</span><span class="sxs-lookup"><span data-stu-id="15941-111">Security Mode</span></span>|<span data-ttu-id="15941-112">Transport</span><span class="sxs-lookup"><span data-stu-id="15941-112">Transport</span></span>|  
|<span data-ttu-id="15941-113">Interoperabilität</span><span class="sxs-lookup"><span data-stu-id="15941-113">Interoperability</span></span>|<span data-ttu-id="15941-114">Nur [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]</span><span class="sxs-lookup"><span data-stu-id="15941-114">[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] only</span></span>|  
|<span data-ttu-id="15941-115">Authentifizierung (Server)</span><span class="sxs-lookup"><span data-stu-id="15941-115">Authentication (Server)</span></span><br /><br /> <span data-ttu-id="15941-116">Authentifizierung (Client)</span><span class="sxs-lookup"><span data-stu-id="15941-116">Authentication (Client)</span></span>|<span data-ttu-id="15941-117">Ja (mithilfe der integrierten Windows-Authentifizierung)</span><span class="sxs-lookup"><span data-stu-id="15941-117">Yes (using Windows integrated authentication)</span></span><br /><br /> <span data-ttu-id="15941-118">Ja (mithilfe der integrierten Windows-Authentifizierung)</span><span class="sxs-lookup"><span data-stu-id="15941-118">Yes (using Windows integrated authentication)</span></span>|  
|<span data-ttu-id="15941-119">Integrität</span><span class="sxs-lookup"><span data-stu-id="15941-119">Integrity</span></span>|<span data-ttu-id="15941-120">Ja</span><span class="sxs-lookup"><span data-stu-id="15941-120">Yes</span></span>|  
|<span data-ttu-id="15941-121">Vertraulichkeit</span><span class="sxs-lookup"><span data-stu-id="15941-121">Confidentiality</span></span>|<span data-ttu-id="15941-122">Ja</span><span class="sxs-lookup"><span data-stu-id="15941-122">Yes</span></span>|  
|<span data-ttu-id="15941-123">Transport</span><span class="sxs-lookup"><span data-stu-id="15941-123">Transport</span></span>|<span data-ttu-id="15941-124">NET.TCP</span><span class="sxs-lookup"><span data-stu-id="15941-124">NET.TCP</span></span>|  
|<span data-ttu-id="15941-125">Bindung</span><span class="sxs-lookup"><span data-stu-id="15941-125">Binding</span></span>|<xref:System.ServiceModel.NetTcpBinding>|  
  
## <a name="service"></a><span data-ttu-id="15941-126">Dienst</span><span class="sxs-lookup"><span data-stu-id="15941-126">Service</span></span>  
 <span data-ttu-id="15941-127">Der folgende Code und die folgende Konfiguration werden unabhängig voneinander ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="15941-127">The following code and configuration are meant to run independently.</span></span> <span data-ttu-id="15941-128">Führen Sie einen der folgenden Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="15941-128">Do one of the following:</span></span>  
  
-   <span data-ttu-id="15941-129">Erstellen Sie einen separaten Dienst, indem Sie den Code ohne Konfiguration verwenden.</span><span class="sxs-lookup"><span data-stu-id="15941-129">Create a stand-alone service using the code with no configuration.</span></span>  
  
-   <span data-ttu-id="15941-130">Erstellen Sie mit der angegebenen Konfiguration einen Dienst, aber definieren Sie keine Endpunkte.</span><span class="sxs-lookup"><span data-stu-id="15941-130">Create a service using the supplied configuration, but do not define any endpoints.</span></span>  
  
### <a name="code"></a><span data-ttu-id="15941-131">Code</span><span class="sxs-lookup"><span data-stu-id="15941-131">Code</span></span>  
 <span data-ttu-id="15941-132">Im folgenden Code wird gezeigt, wie ein Dienstendpunkt, der Windows-Sicherheit verwendet, erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="15941-132">The following code shows how to create a service endpoint that uses a Windows security.</span></span>  
  
 [!code-csharp[C_SecurityScenarios#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_securityscenarios/cs/source.cs#3)]
 [!code-vb[C_SecurityScenarios#3](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_securityscenarios/vb/source.vb#3)]  
  
### <a name="configuration"></a><span data-ttu-id="15941-133">Konfiguration</span><span class="sxs-lookup"><span data-stu-id="15941-133">Configuration</span></span>  
 <span data-ttu-id="15941-134">Die folgende Konfiguration kann statt des Codes verwendet werden, um den Dienstendpunkt einzurichten:</span><span class="sxs-lookup"><span data-stu-id="15941-134">The following configuration can be used instead of the code to set up the service endpoint:</span></span>  
  
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
  
## <a name="client"></a><span data-ttu-id="15941-135">Client</span><span class="sxs-lookup"><span data-stu-id="15941-135">Client</span></span>  
 <span data-ttu-id="15941-136">Der folgende Code und die folgende Konfiguration werden unabhängig voneinander ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="15941-136">The following code and configuration are meant to run independently.</span></span> <span data-ttu-id="15941-137">Führen Sie einen der folgenden Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="15941-137">Do one of the following:</span></span>  
  
-   <span data-ttu-id="15941-138">Erstellen Sie mit dem Code (und Clientcode) einen eigenständigen Client.</span><span class="sxs-lookup"><span data-stu-id="15941-138">Create a stand-alone client using the code (and client code).</span></span>  
  
-   <span data-ttu-id="15941-139">Erstellen Sie einen Client, der keine Endpunktadressen definiert.</span><span class="sxs-lookup"><span data-stu-id="15941-139">Create a client that does not define any endpoint addresses.</span></span> <span data-ttu-id="15941-140">Verwenden Sie stattdessen den Clientkonstruktor, der den Konfigurationsnamen als Argument verwendet.</span><span class="sxs-lookup"><span data-stu-id="15941-140">Instead, use the client constructor that takes the configuration name as an argument.</span></span> <span data-ttu-id="15941-141">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="15941-141">For example:</span></span>  
  
     [!code-csharp[C_SecurityScenarios#0](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_securityscenarios/cs/source.cs#0)]
     [!code-vb[C_SecurityScenarios#0](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_securityscenarios/vb/source.vb#0)]  
  
### <a name="code"></a><span data-ttu-id="15941-142">Code</span><span class="sxs-lookup"><span data-stu-id="15941-142">Code</span></span>  
 <span data-ttu-id="15941-143">Der folgende Code erstellt den Client.</span><span class="sxs-lookup"><span data-stu-id="15941-143">The following code creates the client.</span></span> <span data-ttu-id="15941-144">Die Bindung ist für die Verwendung der Transportmodussicherheit mit dem TCP-Transport konfiguriert, wobei der Clientanmeldeinformationstyp auf Windows festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="15941-144">The binding is configured to use the Transport mode security, with the TCP transport, with the client credential type set to Windows.</span></span>  
  
 [!code-csharp[C_SecurityScenarios#4](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_securityscenarios/cs/source.cs#4)]
 [!code-vb[C_SecurityScenarios#4](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_securityscenarios/vb/source.vb#4)]  
  
### <a name="configuration"></a><span data-ttu-id="15941-145">Konfiguration</span><span class="sxs-lookup"><span data-stu-id="15941-145">Configuration</span></span>  
 <span data-ttu-id="15941-146">Die folgende Konfiguration kann statt des Codes verwendet werden, um den Client zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="15941-146">The following configuration can be used instead of the code to create the client.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="15941-147">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="15941-147">See Also</span></span>  
 [<span data-ttu-id="15941-148">Übersicht über die Sicherheit</span><span class="sxs-lookup"><span data-stu-id="15941-148">Security Overview</span></span>](../../../../docs/framework/wcf/feature-details/security-overview.md)  
 [<span data-ttu-id="15941-149">Vorgehensweise: Sichern eines Dienstes mit Windows-Anmeldeinformationen</span><span class="sxs-lookup"><span data-stu-id="15941-149">How to: Secure a Service with Windows Credentials</span></span>](../../../../docs/framework/wcf/how-to-secure-a-service-with-windows-credentials.md)  
 [<span data-ttu-id="15941-150">Sicherheitsmodell für Windows Server AppFabric</span><span class="sxs-lookup"><span data-stu-id="15941-150">Security Model for Windows Server App Fabric</span></span>](http://go.microsoft.com/fwlink/?LinkID=201279&clcid=0x409)
