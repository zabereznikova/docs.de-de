---
title: Nachrichtensicherheit mit einem anonymen Client
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
ms.assetid: cad53e1a-b7c9-4064-bc87-508c3d1dce49
caps.latest.revision: "15"
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.workload: dotnet
ms.openlocfilehash: e8c10c9d4838a2b6c9d3a021d22d2dfd4dc865da
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="message-security-with-an-anonymous-client"></a><span data-ttu-id="70693-102">Nachrichtensicherheit mit einem anonymen Client</span><span class="sxs-lookup"><span data-stu-id="70693-102">Message Security with an Anonymous Client</span></span>
<span data-ttu-id="70693-103">Das folgende Szenario zeigt, wie ein Client und ein Dienst mit [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]-Nachrichtensicherheit gesichert werden.</span><span class="sxs-lookup"><span data-stu-id="70693-103">The following scenario shows a client and service secured by [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] message security.</span></span> <span data-ttu-id="70693-104">Ein Entwurfsziel ist die Verwendung von Nachrichtensicherheit statt Transportsicherheit, sodass zu einem späteren Zeitpunkt ein komplexeres anspruchsbasierter Modell unterstützt werden kann.</span><span class="sxs-lookup"><span data-stu-id="70693-104">A design goal is to use message security rather than transport security, so that in the future it can support a richer claims-based model.</span></span> [!INCLUDE[crabout](../../../../includes/crabout-md.md)]<span data-ttu-id="70693-105">umfangreiche Ansprüche für die Autorisierung, finden Sie unter [Verwalten von Ansprüchen und Autorisierung mit dem Identitätsmodell](../../../../docs/framework/wcf/feature-details/managing-claims-and-authorization-with-the-identity-model.md).</span><span class="sxs-lookup"><span data-stu-id="70693-105"> using rich claims for authorization, see [Managing Claims and Authorization with the Identity Model](../../../../docs/framework/wcf/feature-details/managing-claims-and-authorization-with-the-identity-model.md).</span></span>  
  
 <span data-ttu-id="70693-106">Eine beispielanwendung finden Sie unter [Nachrichtensicherheit – anonym](../../../../docs/framework/wcf/samples/message-security-anonymous.md).</span><span class="sxs-lookup"><span data-stu-id="70693-106">For a sample application, see [Message Security Anonymous](../../../../docs/framework/wcf/samples/message-security-anonymous.md).</span></span>  
  
 <span data-ttu-id="70693-107">![Nachrichtensicherheit mit einem anonymen Client](../../../../docs/framework/wcf/feature-details/media/b361a565-831c-4c10-90d7-66d8eeece0a1.gif "b361a565-831c-4c10-90d7-66d8eeece0a1")</span><span class="sxs-lookup"><span data-stu-id="70693-107">![Message security with an anynymous client](../../../../docs/framework/wcf/feature-details/media/b361a565-831c-4c10-90d7-66d8eeece0a1.gif "b361a565-831c-4c10-90d7-66d8eeece0a1")</span></span>  
  
|<span data-ttu-id="70693-108">Merkmal</span><span class="sxs-lookup"><span data-stu-id="70693-108">Characteristic</span></span>|<span data-ttu-id="70693-109">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="70693-109">Description</span></span>|  
|--------------------|-----------------|  
|<span data-ttu-id="70693-110">Sicherheitsmodus</span><span class="sxs-lookup"><span data-stu-id="70693-110">Security Mode</span></span>|<span data-ttu-id="70693-111">Meldung</span><span class="sxs-lookup"><span data-stu-id="70693-111">Message</span></span>|  
|<span data-ttu-id="70693-112">Interoperabilität</span><span class="sxs-lookup"><span data-stu-id="70693-112">Interoperability</span></span>|<span data-ttu-id="70693-113">Nur [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]</span><span class="sxs-lookup"><span data-stu-id="70693-113">[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] only</span></span>|  
|<span data-ttu-id="70693-114">Authentifizierung (Server)</span><span class="sxs-lookup"><span data-stu-id="70693-114">Authentication (Server)</span></span>|<span data-ttu-id="70693-115">Die erste Aushandlung erfordert die Serverauthentifizierung, jedoch keine Clientauthentifizierung</span><span class="sxs-lookup"><span data-stu-id="70693-115">Initial negotiation requires server authentication, but not client authentication</span></span>|  
|<span data-ttu-id="70693-116">Authentifizierung (Client)</span><span class="sxs-lookup"><span data-stu-id="70693-116">Authentication (Client)</span></span>|<span data-ttu-id="70693-117">Keine</span><span class="sxs-lookup"><span data-stu-id="70693-117">None</span></span>|  
|<span data-ttu-id="70693-118">Integrität</span><span class="sxs-lookup"><span data-stu-id="70693-118">Integrity</span></span>|<span data-ttu-id="70693-119">Ja, mit freigegebenem Sicherheitskontext</span><span class="sxs-lookup"><span data-stu-id="70693-119">Yes, using shared security context</span></span>|  
|<span data-ttu-id="70693-120">Vertraulichkeit</span><span class="sxs-lookup"><span data-stu-id="70693-120">Confidentiality</span></span>|<span data-ttu-id="70693-121">Ja, mit freigegebenem Sicherheitskontext</span><span class="sxs-lookup"><span data-stu-id="70693-121">Yes, using shared security context</span></span>|  
|<span data-ttu-id="70693-122">Transport</span><span class="sxs-lookup"><span data-stu-id="70693-122">Transport</span></span>|<span data-ttu-id="70693-123">HTTP</span><span class="sxs-lookup"><span data-stu-id="70693-123">HTTP</span></span>|  
  
## <a name="service"></a><span data-ttu-id="70693-124">Dienst</span><span class="sxs-lookup"><span data-stu-id="70693-124">Service</span></span>  
 <span data-ttu-id="70693-125">Der folgende Code und die folgende Konfiguration werden unabhängig voneinander ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="70693-125">The following code and configuration are meant to run independently.</span></span> <span data-ttu-id="70693-126">Führen Sie einen der folgenden Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="70693-126">Do one of the following:</span></span>  
  
-   <span data-ttu-id="70693-127">Erstellen Sie einen separaten Dienst, indem Sie den Code ohne Konfiguration verwenden.</span><span class="sxs-lookup"><span data-stu-id="70693-127">Create a stand-alone service using the code with no configuration.</span></span>  
  
-   <span data-ttu-id="70693-128">Erstellen Sie mit der angegebenen Konfiguration einen Dienst, aber definieren Sie keine Endpunkte.</span><span class="sxs-lookup"><span data-stu-id="70693-128">Create a service using the supplied configuration, but do not define any endpoints.</span></span>  
  
### <a name="code"></a><span data-ttu-id="70693-129">Code</span><span class="sxs-lookup"><span data-stu-id="70693-129">Code</span></span>  
 <span data-ttu-id="70693-130">Im folgenden Code wird gezeigt, wie ein Dienstendpunkt, der Nachrichtensicherheit verwendet, erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="70693-130">The following code shows how to create a service endpoint that uses message security.</span></span>  
  
 [!code-csharp[C_SecurityScenarios#8](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_securityscenarios/cs/source.cs#8)]
 [!code-vb[C_SecurityScenarios#8](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_securityscenarios/vb/source.vb#8)]  
  
### <a name="configuration"></a><span data-ttu-id="70693-131">Konfiguration</span><span class="sxs-lookup"><span data-stu-id="70693-131">Configuration</span></span>  
 <span data-ttu-id="70693-132">Anstelle des Codes kann die folgende Konfiguration verwendet werden:</span><span class="sxs-lookup"><span data-stu-id="70693-132">The following configuration can be used instead of the code.</span></span> <span data-ttu-id="70693-133">Mit dem Element für das Dienstverhalten wird ein Zertifikat angegeben, mit dem der Dienst gegenüber dem Client authentifiziert wird.</span><span class="sxs-lookup"><span data-stu-id="70693-133">The service behavior element is used to specify a certificate that is used to authenticate the service to the client.</span></span> <span data-ttu-id="70693-134">Das Dienstelement muss das Verhalten mit dem `behaviorConfiguration`-Attribut angeben.</span><span class="sxs-lookup"><span data-stu-id="70693-134">The service element must specify the behavior using the `behaviorConfiguration` attribute.</span></span> <span data-ttu-id="70693-135">Das Bindungselement gibt an, dass der Clientanmeldeinformationstyp `None` ist, sodass anonyme Clients den Dienst verwenden können.</span><span class="sxs-lookup"><span data-stu-id="70693-135">The binding element specifies that the client credential type is `None`, allowing anonymous clients to use the service.</span></span>  
  
```xml  
<?xml version="1.0" encoding="utf-8"?>  
<configuration>  
  <system.serviceModel>  
    <behaviors>  
      <serviceBehaviors>  
        <behavior name="ServiceCredentialsBehavior">  
          <serviceCredentials>  
            <serviceCertificate findValue="contoso.com"   
                                storeLocation="LocalMachine"  
                                storeName="My" />  
          </serviceCredentials>  
        </behavior>  
      </serviceBehaviors>  
    </behaviors>  
    <services>  
      <service behaviorConfiguration="ServiceCredentialsBehavior"   
               name="ServiceModel.Calculator">  
        <endpoint address="http://localhost/Calculator"   
                  binding="wsHttpBinding"  
                  bindingConfiguration="WSHttpBinding_ICalculator"   
                  name="CalculatorService"  
                  contract="ServiceModel.ICalculator" />  
      </service>  
    </services>  
    <bindings>  
      <wsHttpBinding>  
        <binding name="WSHttpBinding_ICalculator" >  
          <security mode="Message">  
            <message clientCredentialType="None" />  
          </security>  
        </binding>  
      </wsHttpBinding>  
    </bindings>  
    <client />  
  </system.serviceModel>  
</configuration>  
```  
  
## <a name="client"></a><span data-ttu-id="70693-136">Client</span><span class="sxs-lookup"><span data-stu-id="70693-136">Client</span></span>  
 <span data-ttu-id="70693-137">Der folgende Code und die folgende Konfiguration werden unabhängig voneinander ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="70693-137">The following code and configuration are meant to run independently.</span></span> <span data-ttu-id="70693-138">Führen Sie einen der folgenden Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="70693-138">Do one of the following:</span></span>  
  
-   <span data-ttu-id="70693-139">Erstellen Sie mit dem Code (und Clientcode) einen eigenständigen Client.</span><span class="sxs-lookup"><span data-stu-id="70693-139">Create a stand-alone client using the code (and client code).</span></span>  
  
-   <span data-ttu-id="70693-140">Erstellen Sie einen Client, der keine Endpunktadressen definiert.</span><span class="sxs-lookup"><span data-stu-id="70693-140">Create a client that does not define any endpoint addresses.</span></span> <span data-ttu-id="70693-141">Verwenden Sie stattdessen den Clientkonstruktor, der den Konfigurationsnamen als Argument verwendet.</span><span class="sxs-lookup"><span data-stu-id="70693-141">Instead, use the client constructor that takes the configuration name as an argument.</span></span> <span data-ttu-id="70693-142">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="70693-142">For example:</span></span>  
  
     [!code-csharp[C_SecurityScenarios#0](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_securityscenarios/cs/source.cs#0)]
     [!code-vb[C_SecurityScenarios#0](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_securityscenarios/vb/source.vb#0)]  
  
### <a name="code"></a><span data-ttu-id="70693-143">Code</span><span class="sxs-lookup"><span data-stu-id="70693-143">Code</span></span>  
 <span data-ttu-id="70693-144">Der folgende Code erstellt eine Instanz des Clients.</span><span class="sxs-lookup"><span data-stu-id="70693-144">The following code creates an instance of the client.</span></span> <span data-ttu-id="70693-145">Die Bindung verwendet den Nachrichtensicherheitsmodus, und der Clientanmeldeinformationstyp wird auf "none" festgelegt.</span><span class="sxs-lookup"><span data-stu-id="70693-145">The binding uses message mode security, and the client credential type is set to none.</span></span>  
  
 [!code-csharp[C_SecurityScenarios#15](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_securityscenarios/cs/source.cs#15)]
 [!code-vb[C_SecurityScenarios#15](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_securityscenarios/vb/source.vb#15)]  
  
### <a name="configuration"></a><span data-ttu-id="70693-146">Konfiguration</span><span class="sxs-lookup"><span data-stu-id="70693-146">Configuration</span></span>  
 <span data-ttu-id="70693-147">Der folgende Code dient zum Konfigurieren des Clients.</span><span class="sxs-lookup"><span data-stu-id="70693-147">The following code configures the client.</span></span>  
  
```xml  
<?xml version="1.0" encoding="utf-8"?>  
<configuration>  
  <system.serviceModel>  
    <bindings>  
      <wsHttpBinding>  
        <binding name="WSHttpBinding_ICalculator" >  
          <security mode="Message">  
            <message clientCredentialType="None" />  
          </security>  
        </binding>  
      </wsHttpBinding>  
    </bindings>  
    <client>  
      <endpoint address="http://machineName/Calculator"  
        binding="wsHttpBinding"  
        bindingConfiguration="WSHttpBinding_ICalculator"   
        contract="ICalculator"  
        name="WSHttpBinding_ICalculator">  
        <identity>  
          <dns value="contoso.com" />  
        </identity>  
      </endpoint>  
    </client>  
  </system.serviceModel>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="70693-148">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="70693-148">See Also</span></span>  
 [<span data-ttu-id="70693-149">Übersicht über die Sicherheit</span><span class="sxs-lookup"><span data-stu-id="70693-149">Security Overview</span></span>](../../../../docs/framework/wcf/feature-details/security-overview.md)  
 [<span data-ttu-id="70693-150">Sicherheit bei verteilten Anwendungen</span><span class="sxs-lookup"><span data-stu-id="70693-150">Distributed Application Security</span></span>](../../../../docs/framework/wcf/feature-details/distributed-application-security.md)  
 [<span data-ttu-id="70693-151">Nachrichtensicherheit – anonym</span><span class="sxs-lookup"><span data-stu-id="70693-151">Message Security Anonymous</span></span>](../../../../docs/framework/wcf/samples/message-security-anonymous.md)  
 [<span data-ttu-id="70693-152">Dienstidentität und Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="70693-152">Service Identity and Authentication</span></span>](../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md)  
 [<span data-ttu-id="70693-153">Sicherheitsmodell für Windows Server AppFabric</span><span class="sxs-lookup"><span data-stu-id="70693-153">Security Model for Windows Server App Fabric</span></span>](http://go.microsoft.com/fwlink/?LinkID=201279&clcid=0x409)
