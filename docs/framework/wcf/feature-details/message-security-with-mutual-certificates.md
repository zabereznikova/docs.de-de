---
title: Nachrichtensicherheit durch gegenseitige Zertifikate
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 99d7a528-7ae4-4d39-a0f9-3066ea237de0
ms.openlocfilehash: 44d06762bf66950ea0cc06986c61ecd548ae2e0c
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/09/2020
ms.locfileid: "84576407"
---
# <a name="message-security-with-mutual-certificates"></a><span data-ttu-id="c9802-102">Nachrichtensicherheit durch gegenseitige Zertifikate</span><span class="sxs-lookup"><span data-stu-id="c9802-102">Message Security with Mutual Certificates</span></span>
<span data-ttu-id="c9802-103">Das folgende Szenario zeigt einen Windows Communication Foundation (WCF)-Dienst und einen Client, der mithilfe des Nachrichten Sicherheitsmodus gesichert wurde.</span><span class="sxs-lookup"><span data-stu-id="c9802-103">The following scenario shows a Windows Communication Foundation (WCF) service and client secured using message security mode.</span></span> <span data-ttu-id="c9802-104">Sowohl der Client als auch der Dienst werden mit Zertifikaten authentifiziert.</span><span class="sxs-lookup"><span data-stu-id="c9802-104">The client and the service are authenticated with certificates.</span></span>  
  
 <span data-ttu-id="c9802-105">Dieses Szenario ist interoperabel, da es WS-Sicherheit mit dem X.509-Zertifikatstokenprofil verwendet.</span><span class="sxs-lookup"><span data-stu-id="c9802-105">This scenario is interoperable because it uses WS-Security with the X.509 certificate token profile.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="c9802-106">Dieses Szenario führt keine Aushandlung für das Dienstzertifikat aus.</span><span class="sxs-lookup"><span data-stu-id="c9802-106">This scenario does not perform negotiation of the service certificate.</span></span> <span data-ttu-id="c9802-107">Das Dienstzertifikat muss dem Client vor jeder Kommunikation bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="c9802-107">The service certificate must be provided to the client in advance of any communication.</span></span> <span data-ttu-id="c9802-108">Das Serverzertifikat kann mit der Anwendung oder im Rahmen einer Out-of-Band-Kommunikation bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="c9802-108">The server certificate can be distributed with the application or provided in an out-of-band communication.</span></span>  
  
 <span data-ttu-id="c9802-109">![Nachrichten Sicherheit mit gegenseitigen Zertifikaten](media/f4157312-b17c-416c-a5ee-fa7b54db211b.gif "f4157312-b17c-416c-a5ee-fa7b54db211b")</span><span class="sxs-lookup"><span data-stu-id="c9802-109">![Message security with mutual certificates](media/f4157312-b17c-416c-a5ee-fa7b54db211b.gif "f4157312-b17c-416c-a5ee-fa7b54db211b")</span></span>  
  
|<span data-ttu-id="c9802-110">Merkmal</span><span class="sxs-lookup"><span data-stu-id="c9802-110">Characteristic</span></span>|<span data-ttu-id="c9802-111">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="c9802-111">Description</span></span>|  
|--------------------|-----------------|  
|<span data-ttu-id="c9802-112">Sicherheitsmodus</span><span class="sxs-lookup"><span data-stu-id="c9802-112">Security Mode</span></span>|<span data-ttu-id="c9802-113">`Message`</span><span class="sxs-lookup"><span data-stu-id="c9802-113">Message</span></span>|  
|<span data-ttu-id="c9802-114">Interoperabilität</span><span class="sxs-lookup"><span data-stu-id="c9802-114">Interoperability</span></span>|<span data-ttu-id="c9802-115">Ja, mit WS-Sicherheit und X.509-Zertifikatstokenprofil kompatible Clients und Dienste.</span><span class="sxs-lookup"><span data-stu-id="c9802-115">Yes, with WS-Security and X.509 certificate token profile compatible clients and services.</span></span>|  
|<span data-ttu-id="c9802-116">Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="c9802-116">Authentication</span></span>|<span data-ttu-id="c9802-117">Gegenseitige Authentifizierung des Servers und des Clients.</span><span class="sxs-lookup"><span data-stu-id="c9802-117">Mutual authentication of the server and client.</span></span>|  
|<span data-ttu-id="c9802-118">Integrität</span><span class="sxs-lookup"><span data-stu-id="c9802-118">Integrity</span></span>|<span data-ttu-id="c9802-119">Ja</span><span class="sxs-lookup"><span data-stu-id="c9802-119">Yes</span></span>|  
|<span data-ttu-id="c9802-120">Vertraulichkeit</span><span class="sxs-lookup"><span data-stu-id="c9802-120">Confidentiality</span></span>|<span data-ttu-id="c9802-121">Ja</span><span class="sxs-lookup"><span data-stu-id="c9802-121">Yes</span></span>|  
|<span data-ttu-id="c9802-122">Transport</span><span class="sxs-lookup"><span data-stu-id="c9802-122">Transport</span></span>|<span data-ttu-id="c9802-123">HTTP</span><span class="sxs-lookup"><span data-stu-id="c9802-123">HTTP</span></span>|  
|<span data-ttu-id="c9802-124">Bindung</span><span class="sxs-lookup"><span data-stu-id="c9802-124">Binding</span></span>|<xref:System.ServiceModel.WSHttpBinding>|  
  
## <a name="service"></a><span data-ttu-id="c9802-125">Dienst</span><span class="sxs-lookup"><span data-stu-id="c9802-125">Service</span></span>  
 <span data-ttu-id="c9802-126">Der folgende Code und die folgende Konfiguration werden unabhängig voneinander ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="c9802-126">The following code and configuration are meant to run independently.</span></span> <span data-ttu-id="c9802-127">Führen Sie einen der folgenden Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="c9802-127">Do one of the following:</span></span>  
  
- <span data-ttu-id="c9802-128">Erstellen Sie einen separaten Dienst, indem Sie den Code ohne Konfiguration verwenden.</span><span class="sxs-lookup"><span data-stu-id="c9802-128">Create a stand-alone service using the code with no configuration.</span></span>  
  
- <span data-ttu-id="c9802-129">Erstellen Sie mit der angegebenen Konfiguration einen Dienst, aber definieren Sie keine Endpunkte.</span><span class="sxs-lookup"><span data-stu-id="c9802-129">Create a service using the supplied configuration, but do not define any endpoints.</span></span>  
  
### <a name="code"></a><span data-ttu-id="c9802-130">Code</span><span class="sxs-lookup"><span data-stu-id="c9802-130">Code</span></span>  
 <span data-ttu-id="c9802-131">Im folgenden Code wird gezeigt, wie ein Dienstendpunkt, der Nachrichtensicherheit verwendet, erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="c9802-131">The following code shows creates a service endpoint that uses message security.</span></span> <span data-ttu-id="c9802-132">Der Dienst benötigt ein Zertifikat, um sich zu authentifizieren.</span><span class="sxs-lookup"><span data-stu-id="c9802-132">The service requires a certificate to authenticate itself.</span></span>  
  
 [!code-csharp[C_SecurityScenarios#13](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_securityscenarios/cs/source.cs#13)]
 [!code-vb[C_SecurityScenarios#13](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_securityscenarios/vb/source.vb#13)]  
  
### <a name="configuration"></a><span data-ttu-id="c9802-133">Konfiguration</span><span class="sxs-lookup"><span data-stu-id="c9802-133">Configuration</span></span>  
 <span data-ttu-id="c9802-134">Die folgende Konfiguration kann statt des Codes verwendet werden, um denselben Dienst einzurichten.</span><span class="sxs-lookup"><span data-stu-id="c9802-134">The following configuration can be used instead of the code to create the same service.</span></span>  
  
```xml  
<?xml version="1.0" encoding="utf-8"?>  
<configuration>  
  <system.serviceModel>  
    <behaviors>  
      <serviceBehaviors>  
        <behavior name="serviceCredentialBehavior">  
          <serviceCredentials>  
            <serviceCertificate findValue="Contoso.com"
                                storeLocation="LocalMachine"  
                                storeName="My"
                                x509FindType="FindBySubjectName" />  
          </serviceCredentials>  
        </behavior>  
      </serviceBehaviors>  
    </behaviors>  
    <services>  
      <service behaviorConfiguration="serviceCredentialBehavior"
               name="ServiceModel.Calculator">  
        <endpoint address="http://localhost/Calculator"
                  binding="wsHttpBinding"  
                  bindingConfiguration="InteropCertificateBinding"  
                  name="WSHttpBinding_ICalculator"  
                  contract="ServiceModel.ICalculator" />  
      </service>  
    </services>  
    <bindings>  
      <wsHttpBinding>  
        <binding name="InteropCertificateBinding">  
          <security mode="Message">  
            <message clientCredentialType="Certificate"  
                     negotiateServiceCredential="false"  
                     establishSecurityContext="false" />  
          </security>  
        </binding>  
      </wsHttpBinding>  
    </bindings>  
    <client />  
  </system.serviceModel>  
</configuration>  
```  
  
## <a name="client"></a><span data-ttu-id="c9802-135">Client</span><span class="sxs-lookup"><span data-stu-id="c9802-135">Client</span></span>  
 <span data-ttu-id="c9802-136">Der folgende Code und die folgende Konfiguration werden unabhängig voneinander ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="c9802-136">The following code and configuration are meant to run independently.</span></span> <span data-ttu-id="c9802-137">Führen Sie einen der folgenden Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="c9802-137">Do one of the following:</span></span>  
  
- <span data-ttu-id="c9802-138">Erstellen Sie mit dem Code (und Clientcode) einen eigenständigen Client.</span><span class="sxs-lookup"><span data-stu-id="c9802-138">Create a stand-alone client using the code (and client code).</span></span>  
  
- <span data-ttu-id="c9802-139">Erstellen Sie einen Client, der keine Endpunktadressen definiert.</span><span class="sxs-lookup"><span data-stu-id="c9802-139">Create a client that does not define any endpoint addresses.</span></span> <span data-ttu-id="c9802-140">Verwenden Sie stattdessen den Clientkonstruktor, der den Konfigurationsnamen als Argument verwendet.</span><span class="sxs-lookup"><span data-stu-id="c9802-140">Instead, use the client constructor that takes the configuration name as an argument.</span></span> <span data-ttu-id="c9802-141">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="c9802-141">For example:</span></span>  
  
     [!code-csharp[C_SecurityScenarios#0](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_securityscenarios/cs/source.cs#0)]
     [!code-vb[C_SecurityScenarios#0](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_securityscenarios/vb/source.vb#0)]  
  
### <a name="code"></a><span data-ttu-id="c9802-142">Code</span><span class="sxs-lookup"><span data-stu-id="c9802-142">Code</span></span>  
 <span data-ttu-id="c9802-143">Der folgende Code erstellt den Client.</span><span class="sxs-lookup"><span data-stu-id="c9802-143">The following code creates the client.</span></span> <span data-ttu-id="c9802-144">Der Sicherheitsmodus wird auf "Nachricht" und der Clientanmeldeinformationstyp wird auf "Zertifikat" eingestellt.</span><span class="sxs-lookup"><span data-stu-id="c9802-144">The security mode is set to Message, and the client credential type is set to Certificate.</span></span>  
  
 [!code-csharp[C_SecurityScenarios#20](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_securityscenarios/cs/source.cs#20)]
 [!code-vb[C_SecurityScenarios#20](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_securityscenarios/vb/source.vb#20)]  
  
### <a name="configuration"></a><span data-ttu-id="c9802-145">Konfiguration</span><span class="sxs-lookup"><span data-stu-id="c9802-145">Configuration</span></span>  
 <span data-ttu-id="c9802-146">Der Client wird wie folgt konfiguriert.</span><span class="sxs-lookup"><span data-stu-id="c9802-146">The following configures the client.</span></span> <span data-ttu-id="c9802-147">Ein Client Zertifikat muss mithilfe von angegeben werden [\<clientCertificate>](../../configure-apps/file-schema/wcf/clientcertificate-of-clientcredentials-element.md) .</span><span class="sxs-lookup"><span data-stu-id="c9802-147">A client certificate must be specified using the [\<clientCertificate>](../../configure-apps/file-schema/wcf/clientcertificate-of-clientcredentials-element.md).</span></span> <span data-ttu-id="c9802-148">Außerdem wird das Dienst Zertifikat mithilfe von angegeben [\<defaultCertificate>](../../configure-apps/file-schema/wcf/defaultcertificate-element.md) .</span><span class="sxs-lookup"><span data-stu-id="c9802-148">Also, the service certificate is specified using the [\<defaultCertificate>](../../configure-apps/file-schema/wcf/defaultcertificate-element.md).</span></span>  
  
```xml  
<?xml version="1.0" encoding="utf-8"?>  
<configuration>  
  <system.serviceModel>  
    <behaviors>  
      <endpointBehaviors>  
        <behavior name="ClientCredentialsBehavior">  
          <clientCredentials>  
            <clientCertificate findValue="Cohowinery.com"
                 storeLocation="CurrentUser"  
                 storeName="My"  
                 x509FindType="FindBySubjectName" />  
            <serviceCertificate>  
              <defaultCertificate findValue="Contoso.com"
                                  storeLocation="CurrentUser"  
                                  storeName="TrustedPeople"  
                                  x509FindType="FindBySubjectName" />  
            </serviceCertificate>  
          </clientCredentials>  
        </behavior>  
      </endpointBehaviors>  
    </behaviors>  
    <bindings>  
      <wsHttpBinding>  
        <binding name="WSHttpBinding_ICalculator" >  
          <security mode="Message">  
            <message clientCredentialType="Certificate"
                     negotiateServiceCredential="false"  
                     establishSecurityContext="false" />  
          </security>  
        </binding>  
      </wsHttpBinding>  
    </bindings>  
    <client>  
      <endpoint address="http://machineName/Calculator"
                behaviorConfiguration="ClientCredentialsBehavior"  
                binding="wsHttpBinding"
                bindingConfiguration="WSHttpBinding_ICalculator"  
                contract="ICalculator"  
                name="WSHttpBinding_ICalculator">  
        <identity>  
          <certificate encodedValue="Encoded_Value_Not_Shown" />  
        </identity>  
      </endpoint>  
    </client>  
  </system.serviceModel>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="c9802-149">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="c9802-149">See also</span></span>

- [<span data-ttu-id="c9802-150">Sicherheitsübersicht</span><span class="sxs-lookup"><span data-stu-id="c9802-150">Security Overview</span></span>](security-overview.md)
- <span data-ttu-id="c9802-151">[Sicherheitsmodell für Windows Server AppFabric](https://docs.microsoft.com/previous-versions/appfabric/ee677202(v=azure.10))</span><span class="sxs-lookup"><span data-stu-id="c9802-151">[Security Model for Windows Server App Fabric](https://docs.microsoft.com/previous-versions/appfabric/ee677202(v=azure.10))</span></span>
- <span data-ttu-id="c9802-152">[Vorgehensweise: Erstellen und installieren temporärer Zertifikate in WCF für die Transport Sicherheit während der Entwicklung](https://docs.microsoft.com/previous-versions/msp-n-p/ff648498(v=pandp.10))</span><span class="sxs-lookup"><span data-stu-id="c9802-152">[How to: Create and Install Temporary Certificates in WCF for Transport Security During Development](https://docs.microsoft.com/previous-versions/msp-n-p/ff648498(v=pandp.10))</span></span>
