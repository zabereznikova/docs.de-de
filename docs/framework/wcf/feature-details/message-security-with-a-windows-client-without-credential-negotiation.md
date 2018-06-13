---
title: Nachrichtensicherheit mit einem Windows-Client ohne Anmeldeinformationen-Aushandlung
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: fc07a26c-cbee-41c5-8fb0-329085fef749
author: BrucePerlerMS
manager: mbaldwin
ms.openlocfilehash: 05ffe731a578f8b8d2cdbdf5e3c9229e2b03821c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33496600"
---
# <a name="message-security-with-a-windows-client-without-credential-negotiation"></a><span data-ttu-id="b8015-102">Nachrichtensicherheit mit einem Windows-Client ohne Anmeldeinformationen-Aushandlung</span><span class="sxs-lookup"><span data-stu-id="b8015-102">Message Security with a Windows Client without Credential Negotiation</span></span>
<span data-ttu-id="b8015-103">Das folgende Szenario zeigt einen Windows Communication Foundation (WCF)-Client und Dienst, die durch das Kerberos-Protokoll gesichert.</span><span class="sxs-lookup"><span data-stu-id="b8015-103">The following scenario shows a Windows Communication Foundation (WCF) client and service secured by the Kerberos protocol.</span></span>  
  
 <span data-ttu-id="b8015-104">Sowohl der Dienst als auch der Client befinden sich in der gleichen Domäne bzw. in den gleichen vertrauenswürdigen Domänen.</span><span class="sxs-lookup"><span data-stu-id="b8015-104">Both the service and the client are in the same domain or trusted domains.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="b8015-105">Der Unterschied zwischen diesem Szenario und [Nachrichtensicherheit mit einem Windows-Client](../../../../docs/framework/wcf/feature-details/message-security-with-a-windows-client.md) ist, dass dieses Szenario die Dienstanmeldeinformationen mit dem Dienst vor dem Senden der Anwendungsnachricht nicht verhandelt werden.</span><span class="sxs-lookup"><span data-stu-id="b8015-105">The difference between this scenario and [Message Security with a Windows Client](../../../../docs/framework/wcf/feature-details/message-security-with-a-windows-client.md) is that this scenario does not negotiate the service credential with the service prior to sending the application message.</span></span> <span data-ttu-id="b8015-106">Da hierzu das Kerberos-Protokoll erforderlich ist, muss für dieses Szenario auch eine Windows-Domänenumgebung vorhanden sein.</span><span class="sxs-lookup"><span data-stu-id="b8015-106">Additionally, because this requires the Kerberos protocol, this scenario requires a Windows domain environment.</span></span>  
  
 <span data-ttu-id="b8015-107">![Nachrichtensicherheit ohne Anmeldeinformationen-Aushandlung](../../../../docs/framework/wcf/feature-details/media/0c9f9baa-2439-4ef9-92f4-43c242d85d0d.gif "0c9f9baa-2439-4ef9-92f4-43c242d85d0d")</span><span class="sxs-lookup"><span data-stu-id="b8015-107">![Message security without credential negotiation](../../../../docs/framework/wcf/feature-details/media/0c9f9baa-2439-4ef9-92f4-43c242d85d0d.gif "0c9f9baa-2439-4ef9-92f4-43c242d85d0d")</span></span>  
  
|<span data-ttu-id="b8015-108">Merkmal</span><span class="sxs-lookup"><span data-stu-id="b8015-108">Characteristic</span></span>|<span data-ttu-id="b8015-109">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="b8015-109">Description</span></span>|  
|--------------------|-----------------|  
|<span data-ttu-id="b8015-110">Sicherheitsmodus</span><span class="sxs-lookup"><span data-stu-id="b8015-110">Security Mode</span></span>|<span data-ttu-id="b8015-111">Meldung</span><span class="sxs-lookup"><span data-stu-id="b8015-111">Message</span></span>|  
|<span data-ttu-id="b8015-112">Interoperabilität</span><span class="sxs-lookup"><span data-stu-id="b8015-112">Interoperability</span></span>|<span data-ttu-id="b8015-113">Ja, WS-Security mit Clients mit Kerberos-Tokenprofilkompatibilität</span><span class="sxs-lookup"><span data-stu-id="b8015-113">Yes, WS-Security with Kerberos token-profile compatible clients</span></span>|  
|<span data-ttu-id="b8015-114">Authentifizierung (Server)</span><span class="sxs-lookup"><span data-stu-id="b8015-114">Authentication (Server)</span></span>|<span data-ttu-id="b8015-115">Gegenseitige Authentifizierung des Servers und des Clients</span><span class="sxs-lookup"><span data-stu-id="b8015-115">Mutual authentication of the server and client</span></span>|  
|<span data-ttu-id="b8015-116">Authentifizierung (Client)</span><span class="sxs-lookup"><span data-stu-id="b8015-116">Authentication (Client)</span></span>|<span data-ttu-id="b8015-117">Gegenseitige Authentifizierung des Servers und des Clients</span><span class="sxs-lookup"><span data-stu-id="b8015-117">Mutual authentication of the server and client</span></span>|  
|<span data-ttu-id="b8015-118">Integrität</span><span class="sxs-lookup"><span data-stu-id="b8015-118">Integrity</span></span>|<span data-ttu-id="b8015-119">Ja</span><span class="sxs-lookup"><span data-stu-id="b8015-119">Yes</span></span>|  
|<span data-ttu-id="b8015-120">Vertraulichkeit</span><span class="sxs-lookup"><span data-stu-id="b8015-120">Confidentiality</span></span>|<span data-ttu-id="b8015-121">Ja</span><span class="sxs-lookup"><span data-stu-id="b8015-121">Yes</span></span>|  
|<span data-ttu-id="b8015-122">Transport</span><span class="sxs-lookup"><span data-stu-id="b8015-122">Transport</span></span>|<span data-ttu-id="b8015-123">HTTP</span><span class="sxs-lookup"><span data-stu-id="b8015-123">HTTP</span></span>|  
|<span data-ttu-id="b8015-124">Bindung</span><span class="sxs-lookup"><span data-stu-id="b8015-124">Binding</span></span>|<xref:System.ServiceModel.WSHttpBinding>|  
  
## <a name="service"></a><span data-ttu-id="b8015-125">Dienst</span><span class="sxs-lookup"><span data-stu-id="b8015-125">Service</span></span>  
 <span data-ttu-id="b8015-126">Der folgende Code und die folgende Konfiguration werden unabhängig voneinander ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="b8015-126">The following code and configuration are meant to run independently.</span></span> <span data-ttu-id="b8015-127">Führen Sie einen der folgenden Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="b8015-127">Do one of the following:</span></span>  
  
-   <span data-ttu-id="b8015-128">Erstellen Sie einen separaten Dienst, indem Sie den Code ohne Konfiguration verwenden.</span><span class="sxs-lookup"><span data-stu-id="b8015-128">Create a stand-alone service using the code with no configuration.</span></span>  
  
-   <span data-ttu-id="b8015-129">Erstellen Sie mit der angegebenen Konfiguration einen Dienst, aber definieren Sie keine Endpunkte.</span><span class="sxs-lookup"><span data-stu-id="b8015-129">Create a service using the supplied configuration, but do not define any endpoints.</span></span>  
  
### <a name="code"></a><span data-ttu-id="b8015-130">Code</span><span class="sxs-lookup"><span data-stu-id="b8015-130">Code</span></span>  
 <span data-ttu-id="b8015-131">Der folgende Code dient zum Erstellen eines Dienstendpunkts mit Nachrichtensicherheit.</span><span class="sxs-lookup"><span data-stu-id="b8015-131">The following code creates a service endpoint that uses message security.</span></span> <span data-ttu-id="b8015-132">Mit diesem Code wird das Aushandeln der Dienstanmeldeinformationen sowie das Einrichten eines Sicherheitskontexttokens (Security Context Token, SCT) deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="b8015-132">The code disables service credential negotiation, and the establishment of a security context token (SCT).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="b8015-133">Zur Verwendung des Windows-Anmeldeinformationstyps ohne Aushandlung muss das Benutzerkonto des Diensts Zugriff auf den bei der Active Directory-Domäne registrierten Dienstprinzipalnamen (Service Principal Name, SPN) haben.</span><span class="sxs-lookup"><span data-stu-id="b8015-133">To use the Windows credential type without negotiation, the service's user account must have access to service principal name (SPN) that is registered with the Active Directory domain.</span></span> <span data-ttu-id="b8015-134">Dazu gibt es zwei Möglichkeiten:</span><span class="sxs-lookup"><span data-stu-id="b8015-134">You can do this in two ways:</span></span>  
  
1.  <span data-ttu-id="b8015-135">Verwenden Sie das `NetworkService`-Konto oder das `LocalSystem`-Konto, um den Dienst auszuführen.</span><span class="sxs-lookup"><span data-stu-id="b8015-135">Use the `NetworkService` or `LocalSystem` account to run your service.</span></span> <span data-ttu-id="b8015-136">Da diese Konten Zugriff auf die Computer-SPN, die hergestellt wird haben, wenn der Computer die Active Directory-Domäne beitritt, generiert WCF automatisch den richtige SPN-Element im Endpunkt des Diensts in den Dienstmetadaten (Web Services Description Language oder WSDL).</span><span class="sxs-lookup"><span data-stu-id="b8015-136">Because those accounts have access to the machine SPN that is established when the machine joins the Active Directory domain, WCF automatically generates the proper SPN element inside the service's endpoint in the service's metadata (Web Services Description Language, or WSDL).</span></span>  
  
2.  <span data-ttu-id="b8015-137">Verwenden Sie ein beliebiges Active Directory-Domänenkonto, um den Dienst auszuführen.</span><span class="sxs-lookup"><span data-stu-id="b8015-137">Use an arbitrary Active Directory domain account to run your service.</span></span> <span data-ttu-id="b8015-138">In diesem Fall muss für das Domänenkonto ein SPN eingerichtet werden.</span><span class="sxs-lookup"><span data-stu-id="b8015-138">In this case, you need to establish an SPN for that domain account.</span></span> <span data-ttu-id="b8015-139">Eine mögliche Vorgehensweise hierzu besteht in der Verwendung des Tools Setspn.exe.</span><span class="sxs-lookup"><span data-stu-id="b8015-139">One way of doing this is to use the Setspn.exe utility tool.</span></span> <span data-ttu-id="b8015-140">Sobald der SPN für das Konto des Diensts erstellt wird, konfigurieren Sie WCF um, dass dieser SPN für den Dienst Clients über seine Metadaten (WSDL) veröffentlicht.</span><span class="sxs-lookup"><span data-stu-id="b8015-140">Once the SPN is created for the service's account, configure WCF to publish that SPN to the service's clients through its metadata (WSDL).</span></span> <span data-ttu-id="b8015-141">Legen Sie hierzu die Endpunktidentität für den angezeigten Endpunkt entweder mit einer Anwendungskonfigurationsdatei oder mit Code fest.</span><span class="sxs-lookup"><span data-stu-id="b8015-141">This is done by setting the endpoint identity for the exposed endpoint, either though an application configuration file or code.</span></span> <span data-ttu-id="b8015-142">Im folgenden Beispiel wird die Identität programmgesteuert veröffentlicht:</span><span class="sxs-lookup"><span data-stu-id="b8015-142">The following example publishes the identity programmatically.</span></span>  
  
 <span data-ttu-id="b8015-143">Weitere Informationen zu SPNs, die Kerberos-Protokoll und Active Directory finden Sie unter [technische Kerberos-Ergänzung für Windows](http://go.microsoft.com/fwlink/?LinkId=88330).</span><span class="sxs-lookup"><span data-stu-id="b8015-143">For more information about SPNs, the Kerberos protocol, and Active Directory, see [Kerberos Technical Supplement for Windows](http://go.microsoft.com/fwlink/?LinkId=88330).</span></span> <span data-ttu-id="b8015-144">Weitere Informationen über Identitäten Endpunkt finden Sie unter [SecurityBindingElement-Authentifizierungsmodi](../../../../docs/framework/wcf/feature-details/securitybindingelement-authentication-modes.md).</span><span class="sxs-lookup"><span data-stu-id="b8015-144">For more information about endpoint identities, see [SecurityBindingElement Authentication Modes](../../../../docs/framework/wcf/feature-details/securitybindingelement-authentication-modes.md).</span></span>  
  
 [!code-csharp[C_SecurityScenarios#12](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_securityscenarios/cs/source.cs#12)]
 [!code-vb[C_SecurityScenarios#12](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_securityscenarios/vb/source.vb#12)]  
  
### <a name="configuration"></a><span data-ttu-id="b8015-145">Konfiguration</span><span class="sxs-lookup"><span data-stu-id="b8015-145">Configuration</span></span>  
 <span data-ttu-id="b8015-146">Anstelle des Codes kann die folgende Konfiguration verwendet werden:</span><span class="sxs-lookup"><span data-stu-id="b8015-146">The following configuration can be used instead of the code.</span></span>  
  
```xml  
<?xml version="1.0" encoding="utf-8"?>  
<configuration>  
  <system.serviceModel>  
    <behaviors />  
    <services>  
      <service behaviorConfiguration="" name="ServiceModel.Calculator">  
        <endpoint address="http://localhost/Calculator"   
                  binding="wsHttpBinding"  
                  bindingConfiguration="KerberosBinding"  
                  name="WSHttpBinding_ICalculator"  
                  contract="ServiceModel.ICalculator"   
                  listenUri="net.tcp://localhost/metadata" >  
         <identity>  
            <servicePrincipalName value="service_spn_name" />  
         </identity>  
        </endpoint>  
      </service>  
    </services>  
    <bindings>  
      <wsHttpBinding>  
        <binding name="KerberosBinding">  
          <security>  
            <message negotiateServiceCredential="false"   
                     establishSecurityContext="false" />  
          </security>  
        </binding>  
      </wsHttpBinding>  
    </bindings>  
    <client />  
  </system.serviceModel>  
</configuration>  
```  
  
## <a name="client"></a><span data-ttu-id="b8015-147">Client</span><span class="sxs-lookup"><span data-stu-id="b8015-147">Client</span></span>  
 <span data-ttu-id="b8015-148">Der folgende Code und die folgende Konfiguration werden unabhängig voneinander ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="b8015-148">The following code and configuration are meant to run independently.</span></span> <span data-ttu-id="b8015-149">Führen Sie einen der folgenden Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="b8015-149">Do one of the following:</span></span>  
  
-   <span data-ttu-id="b8015-150">Erstellen Sie mit dem Code (und Clientcode) einen eigenständigen Client.</span><span class="sxs-lookup"><span data-stu-id="b8015-150">Create a stand-alone client using the code (and client code).</span></span>  
  
-   <span data-ttu-id="b8015-151">Erstellen Sie einen Client, der keine Endpunktadressen definiert.</span><span class="sxs-lookup"><span data-stu-id="b8015-151">Create a client that does not define any endpoint addresses.</span></span> <span data-ttu-id="b8015-152">Verwenden Sie stattdessen den Clientkonstruktor, der den Konfigurationsnamen als Argument verwendet.</span><span class="sxs-lookup"><span data-stu-id="b8015-152">Instead, use the client constructor that takes the configuration name as an argument.</span></span> <span data-ttu-id="b8015-153">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="b8015-153">For example:</span></span>  
  
     [!code-csharp[C_SecurityScenarios#0](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_securityscenarios/cs/source.cs#0)]
     [!code-vb[C_SecurityScenarios#0](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_securityscenarios/vb/source.vb#0)]  
  
### <a name="code"></a><span data-ttu-id="b8015-154">Code</span><span class="sxs-lookup"><span data-stu-id="b8015-154">Code</span></span>  
 <span data-ttu-id="b8015-155">Der folgende Code dient zum Konfigurieren des Clients.</span><span class="sxs-lookup"><span data-stu-id="b8015-155">The following code configures the client.</span></span> <span data-ttu-id="b8015-156">Der Sicherheitsmodus ist auf Nachrichtensicherheit, der Typ der Clientanmeldeinformationen auf Windows festgelegt.</span><span class="sxs-lookup"><span data-stu-id="b8015-156">The security mode is set to Message, and the client credential type is set to Windows.</span></span> <span data-ttu-id="b8015-157">Die Eigenschaften <xref:System.ServiceModel.MessageSecurityOverHttp.NegotiateServiceCredential%2A> und <xref:System.ServiceModel.NonDualMessageSecurityOverHttp.EstablishSecurityContext%2A> sind auf `false` festgelegt.</span><span class="sxs-lookup"><span data-stu-id="b8015-157">Note that the <xref:System.ServiceModel.MessageSecurityOverHttp.NegotiateServiceCredential%2A> and <xref:System.ServiceModel.NonDualMessageSecurityOverHttp.EstablishSecurityContext%2A> properties are set to `false`.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="b8015-158">Zur Verwendung des Windows-Anmeldeinformationstyps ohne Aushandlung muss der Client vor dem Starten der Kommunikation mit dem Dienst mit dem Konto-SPN des Diensts konfiguriert werden.</span><span class="sxs-lookup"><span data-stu-id="b8015-158">To use Windows credential type without negotiation, the client must be configured with the service's account SPN prior to commencing the communication with the service.</span></span> <span data-ttu-id="b8015-159">Der SPN wird vom Client zum Abrufen des Kerberos-Tokens verwendet, um damit die Kommunikation mit dem Dienst zu authentifizieren und zu sichern.</span><span class="sxs-lookup"><span data-stu-id="b8015-159">The client uses the SPN to get the Kerberos token to authenticate and secure the communication with the service.</span></span> <span data-ttu-id="b8015-160">Im folgenden Beispiel wird das Konfigurieren des Clients mit dem SPN des Diensts veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="b8015-160">The following sample shows how to configure the client with the service's SPN.</span></span> <span data-ttu-id="b8015-161">Bei Verwendung der [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) um den Client zu generieren, den SPN des Diensts wird automatisch weitergegeben werden an den Client aus Dienstmetadaten (WSDL), wenn die Metadaten des Diensts enthält Diese Informationen.</span><span class="sxs-lookup"><span data-stu-id="b8015-161">If you are using the [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) to generate the client, the service's SPN will be automatically propagated to the client from the service's metadata (WSDL), if the service's metadata contains that information.</span></span> <span data-ttu-id="b8015-162">Weitere Informationen zur Konfiguration des Diensts, um einen SPN in den Metadaten des Diensts eingeschlossen werden sollen finden Sie unter im Abschnitt "Dienst" weiter unten in diesem Thema.</span><span class="sxs-lookup"><span data-stu-id="b8015-162">For more information about how to configure the service to include its SPN in the service's metadata, see the "Service" section later in this topic .</span></span>  
>   
>  <span data-ttu-id="b8015-163">Weitere Informationen über SPNs, Kerberos und Active Directory finden Sie unter [technische Kerberos-Ergänzung für Windows](http://go.microsoft.com/fwlink/?LinkId=88330).</span><span class="sxs-lookup"><span data-stu-id="b8015-163">For more information about SPNs, Kerberos, and Active Directory, see [Kerberos Technical Supplement for Windows](http://go.microsoft.com/fwlink/?LinkId=88330).</span></span> <span data-ttu-id="b8015-164">Weitere Informationen über Identitäten Endpunkt finden Sie unter [SecurityBindingElement-Authentifizierungsmodi](../../../../docs/framework/wcf/feature-details/securitybindingelement-authentication-modes.md) Thema.</span><span class="sxs-lookup"><span data-stu-id="b8015-164">For more information about endpoint identities, see [SecurityBindingElement Authentication Modes](../../../../docs/framework/wcf/feature-details/securitybindingelement-authentication-modes.md) topic.</span></span>  
  
 [!code-csharp[C_SecurityScenarios#19](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_securityscenarios/cs/source.cs#19)]
 [!code-vb[C_SecurityScenarios#19](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_securityscenarios/vb/source.vb#19)]  
  
### <a name="configuration"></a><span data-ttu-id="b8015-165">Konfiguration</span><span class="sxs-lookup"><span data-stu-id="b8015-165">Configuration</span></span>  
 <span data-ttu-id="b8015-166">Der folgende Code dient zum Konfigurieren des Clients.</span><span class="sxs-lookup"><span data-stu-id="b8015-166">The following code configures the client.</span></span> <span data-ttu-id="b8015-167">Beachten Sie, dass die [ \<ServicePrincipalName >](../../../../docs/framework/configure-apps/file-schema/wcf/serviceprincipalname.md) Element muss festgelegt werden, um den SPN des Diensts überein, wie für das Dienstkonto in Active Directory-Domäne registriert.</span><span class="sxs-lookup"><span data-stu-id="b8015-167">Note that the [\<servicePrincipalName>](../../../../docs/framework/configure-apps/file-schema/wcf/serviceprincipalname.md) element must be set to match the service's SPN as registered for the service's account in the Active Directory domain.</span></span>  
  
```xml  
<?xml version="1.0" encoding="utf-8"?>  
<configuration>  
  <system.serviceModel>  
    <bindings>  
      <wsHttpBinding>  
        <binding name="WSHttpBinding_ICalculator" >  
          <security mode="Message">  
            <message clientCredentialType="Windows"   
                     negotiateServiceCredential="false"  
                     establishSecurityContext="false" />  
          </security>  
        </binding>  
      </wsHttpBinding>  
    </bindings>  
    <client>  
      <endpoint address="http://localhost/Calculator"   
                binding="wsHttpBinding"  
                bindingConfiguration="WSHttpBinding_ICalculator"  
                contract="ICalculator"  
                name="WSHttpBinding_ICalculator">  
        <identity>  
          <servicePrincipalName value="service_spn_name" />  
        </identity>  
      </endpoint>  
    </client>  
  </system.serviceModel>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="b8015-168">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b8015-168">See Also</span></span>  
 [<span data-ttu-id="b8015-169">Übersicht über die Sicherheit</span><span class="sxs-lookup"><span data-stu-id="b8015-169">Security Overview</span></span>](../../../../docs/framework/wcf/feature-details/security-overview.md)  
 [<span data-ttu-id="b8015-170">Dienstidentität und Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="b8015-170">Service Identity and Authentication</span></span>](../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md)  
 [<span data-ttu-id="b8015-171">Sicherheitsmodell für Windows Server AppFabric</span><span class="sxs-lookup"><span data-stu-id="b8015-171">Security Model for Windows Server App Fabric</span></span>](http://go.microsoft.com/fwlink/?LinkID=201279&clcid=0x409)
