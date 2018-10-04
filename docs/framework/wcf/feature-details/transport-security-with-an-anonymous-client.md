---
title: Transportsicherheit mit einem anonymen Client
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 056653a5-384e-4a02-ae3c-1b0157d2ccb4
author: BrucePerlerMS
ms.openlocfilehash: 54391356648a8f4a8c7175f690b00fd88393b712
ms.sourcegitcommit: 69229651598b427c550223d3c58aba82e47b3f82
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/04/2018
ms.locfileid: "48780725"
---
# <a name="transport-security-with-an-anonymous-client"></a><span data-ttu-id="67c26-102">Transportsicherheit mit einem anonymen Client</span><span class="sxs-lookup"><span data-stu-id="67c26-102">Transport Security with an Anonymous Client</span></span>
<span data-ttu-id="67c26-103">Das Windows Communication Foundation (WCF)-Szenario verwendet transportsicherheit (HTTPS), um Vertraulichkeit und Integrität sicherzustellen.</span><span class="sxs-lookup"><span data-stu-id="67c26-103">This Windows Communication Foundation (WCF) scenario uses transport security (HTTPS) to ensure confidentiality and integrity.</span></span> <span data-ttu-id="67c26-104">Der Server muss mit einem SSL-Zertifikat authentifiziert werden, und die Clients müssen das Zertifikat des Servers als vertrauenswürdig ansehen.</span><span class="sxs-lookup"><span data-stu-id="67c26-104">The server must be authenticated with a Secure Sockets Layer (SSL) certificate, and the clients must trust the server's certificate.</span></span> <span data-ttu-id="67c26-105">Der Client wird von keinem Mechanismus authentifiziert und ist deshalb anonym.</span><span class="sxs-lookup"><span data-stu-id="67c26-105">The client is not authenticated by any mechanism and is, therefore, anonymous.</span></span>  
  
 <span data-ttu-id="67c26-106">Eine beispielanwendung finden Sie unter [WS-Transportsicherheit](../../../../docs/framework/wcf/samples/ws-transport-security.md).</span><span class="sxs-lookup"><span data-stu-id="67c26-106">For a sample application, see [WS Transport Security](../../../../docs/framework/wcf/samples/ws-transport-security.md).</span></span> <span data-ttu-id="67c26-107">Weitere Informationen zur transportsicherheit finden Sie unter [Transport Sicherheitsübersicht](../../../../docs/framework/wcf/feature-details/transport-security-overview.md).</span><span class="sxs-lookup"><span data-stu-id="67c26-107">For more information about transport security, see [Transport Security Overview](../../../../docs/framework/wcf/feature-details/transport-security-overview.md).</span></span>  
  
 <span data-ttu-id="67c26-108">Weitere Informationen zur Verwendung eines Zertifikats mit einem Dienst finden Sie unter [arbeiten mit Zertifikaten](../../../../docs/framework/wcf/feature-details/working-with-certificates.md) und [Vorgehensweise: Konfigurieren eines Anschlusses mit einem SSL-Zertifikat](../../../../docs/framework/wcf/feature-details/how-to-configure-a-port-with-an-ssl-certificate.md).</span><span class="sxs-lookup"><span data-stu-id="67c26-108">For more information about using a certificate with a service, see [Working with Certificates](../../../../docs/framework/wcf/feature-details/working-with-certificates.md) and [How to: Configure a Port with an SSL Certificate](../../../../docs/framework/wcf/feature-details/how-to-configure-a-port-with-an-ssl-certificate.md).</span></span>  
  
 <span data-ttu-id="67c26-109">![Mit der transportsicherheit mit einem anonymen Client](../../../../docs/framework/wcf/feature-details/media/8fa2e931-0cfb-4aaa-9272-91d652b85d8d.gif "8fa2e931-0cfb-4aaa-9272-91d652b85d8d")</span><span class="sxs-lookup"><span data-stu-id="67c26-109">![Using transport security with an anonymous client](../../../../docs/framework/wcf/feature-details/media/8fa2e931-0cfb-4aaa-9272-91d652b85d8d.gif "8fa2e931-0cfb-4aaa-9272-91d652b85d8d")</span></span>  
  
|<span data-ttu-id="67c26-110">Merkmal</span><span class="sxs-lookup"><span data-stu-id="67c26-110">Characteristic</span></span>|<span data-ttu-id="67c26-111">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="67c26-111">Description</span></span>|  
|--------------------|-----------------|  
|<span data-ttu-id="67c26-112">Sicherheitsmodus</span><span class="sxs-lookup"><span data-stu-id="67c26-112">Security Mode</span></span>|<span data-ttu-id="67c26-113">Transport</span><span class="sxs-lookup"><span data-stu-id="67c26-113">Transport</span></span>|  
|<span data-ttu-id="67c26-114">Interoperabilität</span><span class="sxs-lookup"><span data-stu-id="67c26-114">Interoperability</span></span>|<span data-ttu-id="67c26-115">Mit vorhandenen Webdiensten und Webclients</span><span class="sxs-lookup"><span data-stu-id="67c26-115">With existing Web services and clients</span></span>|  
|<span data-ttu-id="67c26-116">Authentifizierung (Server)</span><span class="sxs-lookup"><span data-stu-id="67c26-116">Authentication (Server)</span></span><br /><br /> <span data-ttu-id="67c26-117">Authentifizierung (Client)</span><span class="sxs-lookup"><span data-stu-id="67c26-117">Authentication (Client)</span></span>|<span data-ttu-id="67c26-118">Ja</span><span class="sxs-lookup"><span data-stu-id="67c26-118">Yes</span></span><br /><br /> <span data-ttu-id="67c26-119">Die Anwendungsebene (keine WCF-Unterstützung)</span><span class="sxs-lookup"><span data-stu-id="67c26-119">Application level (no WCF support)</span></span>|  
|<span data-ttu-id="67c26-120">Integrität</span><span class="sxs-lookup"><span data-stu-id="67c26-120">Integrity</span></span>|<span data-ttu-id="67c26-121">Ja</span><span class="sxs-lookup"><span data-stu-id="67c26-121">Yes</span></span>|  
|<span data-ttu-id="67c26-122">Vertraulichkeit</span><span class="sxs-lookup"><span data-stu-id="67c26-122">Confidentiality</span></span>|<span data-ttu-id="67c26-123">Ja</span><span class="sxs-lookup"><span data-stu-id="67c26-123">Yes</span></span>|  
|<span data-ttu-id="67c26-124">Transport</span><span class="sxs-lookup"><span data-stu-id="67c26-124">Transport</span></span>|<span data-ttu-id="67c26-125">HTTPS</span><span class="sxs-lookup"><span data-stu-id="67c26-125">HTTPS</span></span>|  
|<span data-ttu-id="67c26-126">Bindung</span><span class="sxs-lookup"><span data-stu-id="67c26-126">Binding</span></span>|<span data-ttu-id="67c26-127"><<!--zz xref:System.ServiceModel.WsHttpBinding --> `xref:System.ServiceModel.WsHttpBinding`></span><span class="sxs-lookup"><span data-stu-id="67c26-127"><<!--zz xref:System.ServiceModel.WsHttpBinding --> `xref:System.ServiceModel.WsHttpBinding`></span></span>|  
  
## <a name="service"></a><span data-ttu-id="67c26-128">Dienst</span><span class="sxs-lookup"><span data-stu-id="67c26-128">Service</span></span>  
 <span data-ttu-id="67c26-129">Der folgende Code und die folgende Konfiguration werden unabhängig voneinander ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="67c26-129">The following code and configuration are meant to run independently.</span></span> <span data-ttu-id="67c26-130">Führen Sie einen der folgenden Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="67c26-130">Do one of the following:</span></span>  
  
-   <span data-ttu-id="67c26-131">Erstellen Sie einen separaten Dienst, indem Sie den Code ohne Konfiguration verwenden.</span><span class="sxs-lookup"><span data-stu-id="67c26-131">Create a stand-alone service using the code with no configuration.</span></span>  
  
-   <span data-ttu-id="67c26-132">Erstellen Sie mit der angegebenen Konfiguration einen Dienst, aber definieren Sie keine Endpunkte.</span><span class="sxs-lookup"><span data-stu-id="67c26-132">Create a service using the supplied configuration, but do not define any endpoints.</span></span>  
  
### <a name="code"></a><span data-ttu-id="67c26-133">Code</span><span class="sxs-lookup"><span data-stu-id="67c26-133">Code</span></span>  
 <span data-ttu-id="67c26-134">Im folgenden Code wird gezeigt, wie ein Endpunkt mit Transportsicherheit erstellt wird:</span><span class="sxs-lookup"><span data-stu-id="67c26-134">The following code shows how to create an endpoint using transport security:</span></span>  
  
 [!code-csharp[c_SecurityScenarios#5](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_securityscenarios/cs/source.cs#5)]
 [!code-vb[c_SecurityScenarios#5](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_securityscenarios/vb/source.vb#5)]  
  
### <a name="configuration"></a><span data-ttu-id="67c26-135">Konfiguration</span><span class="sxs-lookup"><span data-stu-id="67c26-135">Configuration</span></span>  
 <span data-ttu-id="67c26-136">Mit dem folgenden Code wird derselbe Endpunkt mithilfe von Konfiguration eingerichtet.</span><span class="sxs-lookup"><span data-stu-id="67c26-136">The following code sets up the same endpoint using configuration.</span></span> <span data-ttu-id="67c26-137">Der Client wird von keinem Mechanismus authentifiziert und ist deshalb anonym.</span><span class="sxs-lookup"><span data-stu-id="67c26-137">The client is not authenticated by any mechanism, and is therefore anonymous.</span></span>  
  
```xml  
<?xml version="1.0" encoding="utf-8"?>  
<configuration>  
  <system.serviceModel>  
    <services>  
      <service name="ServiceModel.Calculator">  
        <endpoint address="https://localhost/Calculator"   
                  binding="wsHttpBinding"  
                  bindingConfiguration="WSHttpBinding_ICalculator"   
                  name="SecuredByTransportEndpoint"  
                  contract="ServiceModel.ICalculator" />  
      </service>  
    </services>  
    <bindings>  
      <wsHttpBinding>  
        <binding name="WSHttpBinding_ICalculator">  
          <security mode="Transport">  
            <transport clientCredentialType="None" />  
          </security>  
        </binding>  
      </wsHttpBinding>  
    </bindings>  
    <client />  
  </system.serviceModel>  
</configuration>  
```  
  
## <a name="client"></a><span data-ttu-id="67c26-138">Client</span><span class="sxs-lookup"><span data-stu-id="67c26-138">Client</span></span>  
 <span data-ttu-id="67c26-139">Der folgende Code und die folgende Konfiguration werden unabhängig voneinander ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="67c26-139">The following code and configuration are meant to run independently.</span></span> <span data-ttu-id="67c26-140">Führen Sie einen der folgenden Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="67c26-140">Do one of the following:</span></span>  
  
-   <span data-ttu-id="67c26-141">Erstellen Sie mit dem Code (und Clientcode) einen eigenständigen Client.</span><span class="sxs-lookup"><span data-stu-id="67c26-141">Create a stand-alone client using the code (and client code).</span></span>  
  
-   <span data-ttu-id="67c26-142">Erstellen Sie einen Client, der keine Endpunktadressen definiert.</span><span class="sxs-lookup"><span data-stu-id="67c26-142">Create a client that does not define any endpoint addresses.</span></span> <span data-ttu-id="67c26-143">Verwenden Sie stattdessen den Clientkonstruktor, der den Konfigurationsnamen als Argument verwendet.</span><span class="sxs-lookup"><span data-stu-id="67c26-143">Instead, use the client constructor that takes the configuration name as an argument.</span></span> <span data-ttu-id="67c26-144">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="67c26-144">For example:</span></span>  
  
     [!code-csharp[C_SecurityScenarios#0](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_securityscenarios/cs/source.cs#0)]
     [!code-vb[C_SecurityScenarios#0](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_securityscenarios/vb/source.vb#0)]  
  
### <a name="code"></a><span data-ttu-id="67c26-145">Code</span><span class="sxs-lookup"><span data-stu-id="67c26-145">Code</span></span>  
 [!code-csharp[c_SecurityScenarios#6](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_securityscenarios/cs/source.cs#6)]
 [!code-vb[c_SecurityScenarios#6](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_securityscenarios/vb/source.vb#6)]  
  
### <a name="configuration"></a><span data-ttu-id="67c26-146">Konfiguration</span><span class="sxs-lookup"><span data-stu-id="67c26-146">Configuration</span></span>  
 <span data-ttu-id="67c26-147">Die folgende Konfiguration kann statt des Codes verwendet werden, um den Dienst einzurichten.</span><span class="sxs-lookup"><span data-stu-id="67c26-147">The following configuration can be used instead of the code to set up the service.</span></span>  
  
```xml  
<configuration>  
  <system.serviceModel>  
    <bindings>  
      <wsHttpBinding>  
        <binding name="WSHttpBinding_ICalculator" >  
          <security mode="Transport">  
            <transport clientCredentialType="None" />  
          </security>  
        </binding>  
      </wsHttpBinding>  
    </bindings>  
    <client>  
      <endpoint address="https://machineName/Calculator"   
                binding="wsHttpBinding"  
                bindingConfiguration="WSHttpBinding_ICalculator"   
                contract="ICalculator"  
                name="WSHttpBinding_ICalculator" />  
    </client>  
  </system.serviceModel>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="67c26-148">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="67c26-148">See Also</span></span>  
 [<span data-ttu-id="67c26-149">Übersicht über die Sicherheit</span><span class="sxs-lookup"><span data-stu-id="67c26-149">Security Overview</span></span>](../../../../docs/framework/wcf/feature-details/security-overview.md)  
 [<span data-ttu-id="67c26-150">WS-Transportsicherheit</span><span class="sxs-lookup"><span data-stu-id="67c26-150">WS Transport Security</span></span>](../../../../docs/framework/wcf/samples/ws-transport-security.md)  
 [<span data-ttu-id="67c26-151">Übersicht über die Transportsicherheit</span><span class="sxs-lookup"><span data-stu-id="67c26-151">Transport Security Overview</span></span>](../../../../docs/framework/wcf/feature-details/transport-security-overview.md)  
 [<span data-ttu-id="67c26-152">Sicherheitsmodell für Windows Server AppFabric</span><span class="sxs-lookup"><span data-stu-id="67c26-152">Security Model for Windows Server App Fabric</span></span>](https://go.microsoft.com/fwlink/?LinkID=201279&clcid=0x409)
