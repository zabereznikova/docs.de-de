---
title: "Nachrichtensicherheit über einen Benutzernamenclient"
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
ms.assetid: 36335cb9-76b8-4443-92c7-44f081eabb21
caps.latest.revision: "15"
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.openlocfilehash: 429136ab3e01f3f53f662db02bbac6096be48d11
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="message-security-with-a-user-name-client"></a><span data-ttu-id="9f92e-102">Nachrichtensicherheit über einen Benutzernamenclient</span><span class="sxs-lookup"><span data-stu-id="9f92e-102">Message Security with a User Name Client</span></span>
<span data-ttu-id="9f92e-103">In der folgenden Abbildung wird dargestellt, wie ein [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]-Client und -Dienst mit dem Nachrichtensicherheitsmodus gesichert werden.</span><span class="sxs-lookup"><span data-stu-id="9f92e-103">The following illustration shows an [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] service and client secured using message-level security.</span></span> <span data-ttu-id="9f92e-104">Der Dienst wird über ein X.509-Zertifikat authentifiziert.</span><span class="sxs-lookup"><span data-stu-id="9f92e-104">The service is authenticated with an X.509 certificate.</span></span> <span data-ttu-id="9f92e-105">Der Client wird über den Benutzernamen und das Kennwort authentifiziert.</span><span class="sxs-lookup"><span data-stu-id="9f92e-105">The client authenticates using a user name and password.</span></span>  
  
 <span data-ttu-id="9f92e-106">Eine beispielanwendung finden Sie unter [Nachrichtensicherheit – Benutzername](../../../../docs/framework/wcf/samples/message-security-user-name.md).</span><span class="sxs-lookup"><span data-stu-id="9f92e-106">For a sample application, see [Message Security User Name](../../../../docs/framework/wcf/samples/message-security-user-name.md).</span></span>  
  
 <span data-ttu-id="9f92e-107">![Nachrichtensicherheit durch Benutzernamenauthentifizierung](../../../../docs/framework/wcf/feature-details/media/1fb10a61-7e1d-42f5-b1af-195bfee5b3c6.gif "1fb10a61-7e1d-42f5-b1af-195bfee5b3c6")</span><span class="sxs-lookup"><span data-stu-id="9f92e-107">![Message security using username authentication](../../../../docs/framework/wcf/feature-details/media/1fb10a61-7e1d-42f5-b1af-195bfee5b3c6.gif "1fb10a61-7e1d-42f5-b1af-195bfee5b3c6")</span></span>  
  
|<span data-ttu-id="9f92e-108">Merkmal</span><span class="sxs-lookup"><span data-stu-id="9f92e-108">Characteristic</span></span>|<span data-ttu-id="9f92e-109">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="9f92e-109">Description</span></span>|  
|--------------------|-----------------|  
|<span data-ttu-id="9f92e-110">Sicherheitsmodus</span><span class="sxs-lookup"><span data-stu-id="9f92e-110">Security Mode</span></span>|<span data-ttu-id="9f92e-111">Meldung</span><span class="sxs-lookup"><span data-stu-id="9f92e-111">Message</span></span>|  
|<span data-ttu-id="9f92e-112">Interoperabilität</span><span class="sxs-lookup"><span data-stu-id="9f92e-112">Interoperability</span></span>|<span data-ttu-id="9f92e-113">Nur [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9f92e-113">[!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] only</span></span>|  
|<span data-ttu-id="9f92e-114">Authentifizierung (Server)</span><span class="sxs-lookup"><span data-stu-id="9f92e-114">Authentication (Server)</span></span>|<span data-ttu-id="9f92e-115">Für die erste Aushandlung ist eine Serverauthentifizierung erforderlich</span><span class="sxs-lookup"><span data-stu-id="9f92e-115">Initial negotiation requires server authentication</span></span>|  
|<span data-ttu-id="9f92e-116">Authentifizierung (Client)</span><span class="sxs-lookup"><span data-stu-id="9f92e-116">Authentication (Client)</span></span>|<span data-ttu-id="9f92e-117">Benutzername/Kennwort</span><span class="sxs-lookup"><span data-stu-id="9f92e-117">User name/password</span></span>|  
|<span data-ttu-id="9f92e-118">Integrität</span><span class="sxs-lookup"><span data-stu-id="9f92e-118">Integrity</span></span>|<span data-ttu-id="9f92e-119">Ja, mit freigegebenem Sicherheitskontext</span><span class="sxs-lookup"><span data-stu-id="9f92e-119">Yes, using shared security context</span></span>|  
|<span data-ttu-id="9f92e-120">Vertraulichkeit</span><span class="sxs-lookup"><span data-stu-id="9f92e-120">Confidentiality</span></span>|<span data-ttu-id="9f92e-121">Ja, mit freigegebenem Sicherheitskontext</span><span class="sxs-lookup"><span data-stu-id="9f92e-121">Yes, using shared security context</span></span>|  
|<span data-ttu-id="9f92e-122">Transport</span><span class="sxs-lookup"><span data-stu-id="9f92e-122">Transport</span></span>|<span data-ttu-id="9f92e-123">HTTP</span><span class="sxs-lookup"><span data-stu-id="9f92e-123">HTTP</span></span>|  
|<span data-ttu-id="9f92e-124">Bindung</span><span class="sxs-lookup"><span data-stu-id="9f92e-124">Binding</span></span>|<xref:System.ServiceModel.WSHttpBinding>|  
  
## <a name="service"></a><span data-ttu-id="9f92e-125">Dienst</span><span class="sxs-lookup"><span data-stu-id="9f92e-125">Service</span></span>  
 <span data-ttu-id="9f92e-126">Der folgende Code und die folgende Konfiguration werden unabhängig voneinander ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="9f92e-126">The following code and configuration are meant to run independently.</span></span> <span data-ttu-id="9f92e-127">Führen Sie einen der folgenden Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="9f92e-127">Do one of the following:</span></span>  
  
-   <span data-ttu-id="9f92e-128">Erstellen Sie einen separaten Dienst, indem Sie den Code ohne Konfiguration verwenden.</span><span class="sxs-lookup"><span data-stu-id="9f92e-128">Create a stand-alone service using the code with no configuration.</span></span>  
  
-   <span data-ttu-id="9f92e-129">Erstellen Sie mit der angegebenen Konfiguration einen Dienst, aber definieren Sie keine Endpunkte.</span><span class="sxs-lookup"><span data-stu-id="9f92e-129">Create a service using the supplied configuration, but do not define any endpoints.</span></span>  
  
### <a name="code"></a><span data-ttu-id="9f92e-130">Code</span><span class="sxs-lookup"><span data-stu-id="9f92e-130">Code</span></span>  
 <span data-ttu-id="9f92e-131">Im folgenden Code wird gezeigt, wie ein Dienstendpunkt, der Nachrichtensicherheit verwendet, erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="9f92e-131">The following code shows how to create a service endpoint that uses message security.</span></span>  
  
 [!code-csharp[C_SecurityScenarios#9](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_securityscenarios/cs/source.cs#9)]
 [!code-vb[C_SecurityScenarios#9](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_securityscenarios/vb/source.vb#9)]  
  
### <a name="configuration"></a><span data-ttu-id="9f92e-132">Konfiguration</span><span class="sxs-lookup"><span data-stu-id="9f92e-132">Configuration</span></span>  
 <span data-ttu-id="9f92e-133">Die folgende Konfiguration kann statt des Codes verwendet werden:</span><span class="sxs-lookup"><span data-stu-id="9f92e-133">The following configuration can be used instead of the code:</span></span>  
  
```xml  
<?xml version="1.0" encoding="utf-8"?>  
<configuration>  
  <system.serviceModel>  
    <behaviors>  
      <serviceBehaviors>  
        <behavior name="ServiceCredentialsBehavior">  
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
      <service behaviorConfiguration="ServiceCredentialsBehavior"  
               name="ServiceModel.Calculator">  
        <endpoint address="http://localhost/Calculator"  
                  binding="wsHttpBinding"  
                  bindingConfiguration="MessageAndUserName"  
                  name="SecuredByTransportEndpoint"  
                  contract="ServiceModel.ICalculator" />  
      </service>  
    </services>  
    <bindings>  
      <wsHttpBinding>  
        <binding name="MessageAndUserName">  
          <security mode="Message">              
            <message clientCredentialType="UserName" />  
          </security>  
        </binding>  
      </wsHttpBinding>  
    </bindings>  
    <client />  
  </system.serviceModel>  
</configuration>  
```  
  
## <a name="client"></a><span data-ttu-id="9f92e-134">Client</span><span class="sxs-lookup"><span data-stu-id="9f92e-134">Client</span></span>  
  
### <a name="code"></a><span data-ttu-id="9f92e-135">Code</span><span class="sxs-lookup"><span data-stu-id="9f92e-135">Code</span></span>  
 <span data-ttu-id="9f92e-136">Der folgende Code erstellt den Client.</span><span class="sxs-lookup"><span data-stu-id="9f92e-136">The following code creates the client.</span></span> <span data-ttu-id="9f92e-137">Die Bindung bezieht sich auf den Nachrichtensicherheitsmodus, und der Clientanmeldeinformationstyp wird auf `UserName` festgelegt.</span><span class="sxs-lookup"><span data-stu-id="9f92e-137">The binding is to message mode security, and the client credential type is set to `UserName`.</span></span> <span data-ttu-id="9f92e-138">Der Benutzername und das Kennwort können nur mit Code (nicht konfigurierbar) angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="9f92e-138">The user name and password can only be specified using code (it is not configurable).</span></span> <span data-ttu-id="9f92e-139">Der Code zum Zurückgeben des Benutzernamens und des Kennworts ist hier nicht gezeigt, da dies auf Anwendungsebene erfolgen muss.</span><span class="sxs-lookup"><span data-stu-id="9f92e-139">The code to return the user name and password is not shown here because it must be done at the application level.</span></span> <span data-ttu-id="9f92e-140">Verwenden Sie z. B. ein Windows Forms-Dialogfeld, um vom Benutzer Daten abzufragen.</span><span class="sxs-lookup"><span data-stu-id="9f92e-140">For example, use a Windows Forms dialog box to query the user for the data.</span></span>  
  
 [!code-csharp[C_SecurityScenarios#16](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_securityscenarios/cs/source.cs#16)]
 [!code-vb[C_SecurityScenarios#16](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_securityscenarios/vb/source.vb#16)]  
  
### <a name="configuration"></a><span data-ttu-id="9f92e-141">Konfiguration</span><span class="sxs-lookup"><span data-stu-id="9f92e-141">Configuration</span></span>  
 <span data-ttu-id="9f92e-142">Der folgende Code dient zum Konfigurieren des Clients.</span><span class="sxs-lookup"><span data-stu-id="9f92e-142">The following code configures the client.</span></span> <span data-ttu-id="9f92e-143">Die Bindung bezieht sich auf den Nachrichtensicherheitsmodus, und der Clientanmeldeinformationstyp wird auf `UserName` festgelegt.</span><span class="sxs-lookup"><span data-stu-id="9f92e-143">The binding is to message mode security, and the client credential type is set to `UserName`.</span></span> <span data-ttu-id="9f92e-144">Der Benutzername und das Kennwort können nur mit Code (nicht konfigurierbar) angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="9f92e-144">The user name and password can only be specified using code (it is not configurable).</span></span>  
  
```xml  
<?xml version="1.0" encoding="utf-8"?>  
<configuration>  
  <system.serviceModel>  
    <bindings>  
      <wsHttpBinding>  
        <binding name="WSHttpBinding_ICalculator" >  
          <security mode="Message">  
            <message clientCredentialType="UserName" />  
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
          <dns value ="Contoso.com" />  
        </identity>  
      </endpoint>  
    </client>  
  </system.serviceModel>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="9f92e-145">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="9f92e-145">See Also</span></span>  
 [<span data-ttu-id="9f92e-146">Sicherheit (Übersicht)</span><span class="sxs-lookup"><span data-stu-id="9f92e-146">Security Overview</span></span>](../../../../docs/framework/wcf/feature-details/security-overview.md)  
 [<span data-ttu-id="9f92e-147">Nachrichtensicherheit – Benutzername</span><span class="sxs-lookup"><span data-stu-id="9f92e-147">Message Security User Name</span></span>](../../../../docs/framework/wcf/samples/message-security-user-name.md)  
 [<span data-ttu-id="9f92e-148">Dienstidentität und Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="9f92e-148">Service Identity and Authentication</span></span>](../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md)  
 [<span data-ttu-id="9f92e-149">\<Identität ></span><span class="sxs-lookup"><span data-stu-id="9f92e-149">\<identity></span></span>](../../../../docs/framework/configure-apps/file-schema/wcf/identity.md)  
 [<span data-ttu-id="9f92e-150">Sicherheitsmodell für Windows Server AppFabric</span><span class="sxs-lookup"><span data-stu-id="9f92e-150">Security Model for Windows Server App Fabric</span></span>](http://go.microsoft.com/fwlink/?LinkID=201279&clcid=0x409)
