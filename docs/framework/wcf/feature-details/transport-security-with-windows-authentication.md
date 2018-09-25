---
title: Transportsicherheit mit Windows-Authentifizierung
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 96dd26e2-46e7-4de0-9a29-4fcb05bf187b
author: BrucePerlerMS
ms.openlocfilehash: babafe369ee9f5c9261e3b5c8bc749d3d1d39ec4
ms.sourcegitcommit: 213292dfbb0c37d83f62709959ff55c50af5560d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/25/2018
ms.locfileid: "47079862"
---
# <a name="transport-security-with-windows-authentication"></a><span data-ttu-id="5ea28-102">Transportsicherheit mit Windows-Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="5ea28-102">Transport Security with Windows Authentication</span></span>
<span data-ttu-id="5ea28-103">Das folgende Szenario zeigt einen Windows Communication Foundation (WCF)-Client und Dienst, die durch die Windows-Sicherheit geschützt.</span><span class="sxs-lookup"><span data-stu-id="5ea28-103">The following scenario shows a Windows Communication Foundation (WCF) client and service secured by Windows security.</span></span> <span data-ttu-id="5ea28-104">Weitere Informationen zur Programmierung finden Sie unter [Vorgehensweise: Sichern eines Diensts mit Windows-Anmeldeinformationen](../../../../docs/framework/wcf/how-to-secure-a-service-with-windows-credentials.md).</span><span class="sxs-lookup"><span data-stu-id="5ea28-104">For more information about programming, see [How to: Secure a Service with Windows Credentials](../../../../docs/framework/wcf/how-to-secure-a-service-with-windows-credentials.md).</span></span>  
  
 <span data-ttu-id="5ea28-105">Ein Intranetwebdienst zeigt Personalinformationen an.</span><span class="sxs-lookup"><span data-stu-id="5ea28-105">An intranet Web service displays human resources information.</span></span> <span data-ttu-id="5ea28-106">Der Client ist eine Windows Forms-Anwendung.</span><span class="sxs-lookup"><span data-stu-id="5ea28-106">The client is a Windows Form application.</span></span> <span data-ttu-id="5ea28-107">Die Anwendung wird in einer Domäne mit einem Kerberos-Controller bereitgestellt, der die Domäne sichert.</span><span class="sxs-lookup"><span data-stu-id="5ea28-107">The application is deployed in a domain with a Kerberos controller securing the domain.</span></span>  
  
 <span data-ttu-id="5ea28-108">![Transportsicherheit mit Windows-Authentifizierung](../../../../docs/framework/wcf/feature-details/media/securedbywindows.gif "SecuredByWindows")</span><span class="sxs-lookup"><span data-stu-id="5ea28-108">![Transport security with Windows authentication](../../../../docs/framework/wcf/feature-details/media/securedbywindows.gif "SecuredByWindows")</span></span>  
  
|<span data-ttu-id="5ea28-109">Merkmal</span><span class="sxs-lookup"><span data-stu-id="5ea28-109">Characteristic</span></span>|<span data-ttu-id="5ea28-110">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="5ea28-110">Description</span></span>|  
|--------------------|-----------------|  
|<span data-ttu-id="5ea28-111">Sicherheitsmodus</span><span class="sxs-lookup"><span data-stu-id="5ea28-111">Security Mode</span></span>|<span data-ttu-id="5ea28-112">Transport</span><span class="sxs-lookup"><span data-stu-id="5ea28-112">Transport</span></span>|  
|<span data-ttu-id="5ea28-113">Interoperabilität</span><span class="sxs-lookup"><span data-stu-id="5ea28-113">Interoperability</span></span>|<span data-ttu-id="5ea28-114">Nur WCF</span><span class="sxs-lookup"><span data-stu-id="5ea28-114">WCF only</span></span>|  
|<span data-ttu-id="5ea28-115">Authentifizierung (Server)</span><span class="sxs-lookup"><span data-stu-id="5ea28-115">Authentication (Server)</span></span><br /><br /> <span data-ttu-id="5ea28-116">Authentifizierung (Client)</span><span class="sxs-lookup"><span data-stu-id="5ea28-116">Authentication (Client)</span></span>|<span data-ttu-id="5ea28-117">Ja (mithilfe der integrierten Windows-Authentifizierung)</span><span class="sxs-lookup"><span data-stu-id="5ea28-117">Yes (using Windows integrated authentication)</span></span><br /><br /> <span data-ttu-id="5ea28-118">Ja (mithilfe der integrierten Windows-Authentifizierung)</span><span class="sxs-lookup"><span data-stu-id="5ea28-118">Yes (using Windows integrated authentication)</span></span>|  
|<span data-ttu-id="5ea28-119">Integrität</span><span class="sxs-lookup"><span data-stu-id="5ea28-119">Integrity</span></span>|<span data-ttu-id="5ea28-120">Ja</span><span class="sxs-lookup"><span data-stu-id="5ea28-120">Yes</span></span>|  
|<span data-ttu-id="5ea28-121">Vertraulichkeit</span><span class="sxs-lookup"><span data-stu-id="5ea28-121">Confidentiality</span></span>|<span data-ttu-id="5ea28-122">Ja</span><span class="sxs-lookup"><span data-stu-id="5ea28-122">Yes</span></span>|  
|<span data-ttu-id="5ea28-123">Transport</span><span class="sxs-lookup"><span data-stu-id="5ea28-123">Transport</span></span>|<span data-ttu-id="5ea28-124">NET.TCP</span><span class="sxs-lookup"><span data-stu-id="5ea28-124">NET.TCP</span></span>|  
|<span data-ttu-id="5ea28-125">Bindung</span><span class="sxs-lookup"><span data-stu-id="5ea28-125">Binding</span></span>|<xref:System.ServiceModel.NetTcpBinding>|  
  
## <a name="service"></a><span data-ttu-id="5ea28-126">Dienst</span><span class="sxs-lookup"><span data-stu-id="5ea28-126">Service</span></span>  
 <span data-ttu-id="5ea28-127">Der folgende Code und die folgende Konfiguration werden unabhängig voneinander ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="5ea28-127">The following code and configuration are meant to run independently.</span></span> <span data-ttu-id="5ea28-128">Führen Sie einen der folgenden Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="5ea28-128">Do one of the following:</span></span>  
  
-   <span data-ttu-id="5ea28-129">Erstellen Sie einen separaten Dienst, indem Sie den Code ohne Konfiguration verwenden.</span><span class="sxs-lookup"><span data-stu-id="5ea28-129">Create a stand-alone service using the code with no configuration.</span></span>  
  
-   <span data-ttu-id="5ea28-130">Erstellen Sie mit der angegebenen Konfiguration einen Dienst, aber definieren Sie keine Endpunkte.</span><span class="sxs-lookup"><span data-stu-id="5ea28-130">Create a service using the supplied configuration, but do not define any endpoints.</span></span>  
  
### <a name="code"></a><span data-ttu-id="5ea28-131">Code</span><span class="sxs-lookup"><span data-stu-id="5ea28-131">Code</span></span>  
 <span data-ttu-id="5ea28-132">Im folgenden Code wird gezeigt, wie ein Dienstendpunkt, der Windows-Sicherheit verwendet, erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="5ea28-132">The following code shows how to create a service endpoint that uses a Windows security.</span></span>  
  
 [!code-csharp[C_SecurityScenarios#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_securityscenarios/cs/source.cs#3)]
 [!code-vb[C_SecurityScenarios#3](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_securityscenarios/vb/source.vb#3)]  
  
### <a name="configuration"></a><span data-ttu-id="5ea28-133">Konfiguration</span><span class="sxs-lookup"><span data-stu-id="5ea28-133">Configuration</span></span>  
 <span data-ttu-id="5ea28-134">Die folgende Konfiguration kann statt des Codes verwendet werden, um den Dienstendpunkt einzurichten:</span><span class="sxs-lookup"><span data-stu-id="5ea28-134">The following configuration can be used instead of the code to set up the service endpoint:</span></span>  
  
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
  
## <a name="client"></a><span data-ttu-id="5ea28-135">Client</span><span class="sxs-lookup"><span data-stu-id="5ea28-135">Client</span></span>  
 <span data-ttu-id="5ea28-136">Der folgende Code und die folgende Konfiguration werden unabhängig voneinander ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="5ea28-136">The following code and configuration are meant to run independently.</span></span> <span data-ttu-id="5ea28-137">Führen Sie einen der folgenden Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="5ea28-137">Do one of the following:</span></span>  
  
-   <span data-ttu-id="5ea28-138">Erstellen Sie mit dem Code (und Clientcode) einen eigenständigen Client.</span><span class="sxs-lookup"><span data-stu-id="5ea28-138">Create a stand-alone client using the code (and client code).</span></span>  
  
-   <span data-ttu-id="5ea28-139">Erstellen Sie einen Client, der keine Endpunktadressen definiert.</span><span class="sxs-lookup"><span data-stu-id="5ea28-139">Create a client that does not define any endpoint addresses.</span></span> <span data-ttu-id="5ea28-140">Verwenden Sie stattdessen den Clientkonstruktor, der den Konfigurationsnamen als Argument verwendet.</span><span class="sxs-lookup"><span data-stu-id="5ea28-140">Instead, use the client constructor that takes the configuration name as an argument.</span></span> <span data-ttu-id="5ea28-141">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="5ea28-141">For example:</span></span>  
  
     [!code-csharp[C_SecurityScenarios#0](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_securityscenarios/cs/source.cs#0)]
     [!code-vb[C_SecurityScenarios#0](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_securityscenarios/vb/source.vb#0)]  
  
### <a name="code"></a><span data-ttu-id="5ea28-142">Code</span><span class="sxs-lookup"><span data-stu-id="5ea28-142">Code</span></span>  
 <span data-ttu-id="5ea28-143">Der folgende Code erstellt den Client.</span><span class="sxs-lookup"><span data-stu-id="5ea28-143">The following code creates the client.</span></span> <span data-ttu-id="5ea28-144">Die Bindung ist für die Verwendung der Transportmodussicherheit mit dem TCP-Transport konfiguriert, wobei der Clientanmeldeinformationstyp auf Windows festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="5ea28-144">The binding is configured to use the Transport mode security, with the TCP transport, with the client credential type set to Windows.</span></span>  
  
 [!code-csharp[C_SecurityScenarios#4](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_securityscenarios/cs/source.cs#4)]
 [!code-vb[C_SecurityScenarios#4](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_securityscenarios/vb/source.vb#4)]  
  
### <a name="configuration"></a><span data-ttu-id="5ea28-145">Konfiguration</span><span class="sxs-lookup"><span data-stu-id="5ea28-145">Configuration</span></span>  
 <span data-ttu-id="5ea28-146">Die folgende Konfiguration kann statt des Codes verwendet werden, um den Client zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="5ea28-146">The following configuration can be used instead of the code to create the client.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="5ea28-147">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="5ea28-147">See Also</span></span>  
 [<span data-ttu-id="5ea28-148">Übersicht über die Sicherheit</span><span class="sxs-lookup"><span data-stu-id="5ea28-148">Security Overview</span></span>](../../../../docs/framework/wcf/feature-details/security-overview.md)  
 [<span data-ttu-id="5ea28-149">Vorgehensweise: Sichern eines Dienstes mit Windows-Anmeldeinformationen</span><span class="sxs-lookup"><span data-stu-id="5ea28-149">How to: Secure a Service with Windows Credentials</span></span>](../../../../docs/framework/wcf/how-to-secure-a-service-with-windows-credentials.md)  
 [<span data-ttu-id="5ea28-150">Sicherheitsmodell für Windows Server AppFabric</span><span class="sxs-lookup"><span data-stu-id="5ea28-150">Security Model for Windows Server App Fabric</span></span>](https://go.microsoft.com/fwlink/?LinkID=201279&clcid=0x409)
