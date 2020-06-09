---
title: Nachrichtensicherheit über einen Benutzernamenclient
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 36335cb9-76b8-4443-92c7-44f081eabb21
ms.openlocfilehash: 9447487012cae370d35880e5b780465f9434051b
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/09/2020
ms.locfileid: "84602621"
---
# <a name="message-security-with-a-user-name-client"></a><span data-ttu-id="ac58e-102">Nachrichtensicherheit über einen Benutzernamenclient</span><span class="sxs-lookup"><span data-stu-id="ac58e-102">Message Security with a User Name Client</span></span>
<span data-ttu-id="ac58e-103">Die folgende Abbildung zeigt einen Windows Communication Foundation (WCF)-Dienst und einen Client, der mithilfe der Sicherheit auf Nachrichten Ebene gesichert wird.</span><span class="sxs-lookup"><span data-stu-id="ac58e-103">The following illustration shows an Windows Communication Foundation (WCF) service and client secured using message-level security.</span></span> <span data-ttu-id="ac58e-104">Der Dienst wird über ein X.509-Zertifikat authentifiziert.</span><span class="sxs-lookup"><span data-stu-id="ac58e-104">The service is authenticated with an X.509 certificate.</span></span> <span data-ttu-id="ac58e-105">Der Client wird über den Benutzernamen und das Kennwort authentifiziert.</span><span class="sxs-lookup"><span data-stu-id="ac58e-105">The client authenticates using a user name and password.</span></span>  
  
 <span data-ttu-id="ac58e-106">Eine Beispielanwendung finden Sie unter [Message Security User Name](../samples/message-security-user-name.md).</span><span class="sxs-lookup"><span data-stu-id="ac58e-106">For a sample application, see [Message Security User Name](../samples/message-security-user-name.md).</span></span>  
  
 <span data-ttu-id="ac58e-107">![Nachrichtensicherheit durch Benutzernamenauthentifizierung](media/1fb10a61-7e1d-42f5-b1af-195bfee5b3c6.gif "1b10a61-7e1d-42b5-B1AF-195bfee5b3c6")</span><span class="sxs-lookup"><span data-stu-id="ac58e-107">![Message security using username authentication](media/1fb10a61-7e1d-42f5-b1af-195bfee5b3c6.gif "1fb10a61-7e1d-42f5-b1af-195bfee5b3c6")</span></span>  
  
|<span data-ttu-id="ac58e-108">Merkmal</span><span class="sxs-lookup"><span data-stu-id="ac58e-108">Characteristic</span></span>|<span data-ttu-id="ac58e-109">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="ac58e-109">Description</span></span>|  
|--------------------|-----------------|  
|<span data-ttu-id="ac58e-110">Sicherheitsmodus</span><span class="sxs-lookup"><span data-stu-id="ac58e-110">Security Mode</span></span>|<span data-ttu-id="ac58e-111">`Message`</span><span class="sxs-lookup"><span data-stu-id="ac58e-111">Message</span></span>|  
|<span data-ttu-id="ac58e-112">Interoperabilität</span><span class="sxs-lookup"><span data-stu-id="ac58e-112">Interoperability</span></span>|<span data-ttu-id="ac58e-113">Nur Windows Communication Foundation (WCF)</span><span class="sxs-lookup"><span data-stu-id="ac58e-113">Windows Communication Foundation (WCF) only</span></span>|  
|<span data-ttu-id="ac58e-114">Authentifizierung (Server)</span><span class="sxs-lookup"><span data-stu-id="ac58e-114">Authentication (Server)</span></span>|<span data-ttu-id="ac58e-115">Für die erste Aushandlung ist eine Serverauthentifizierung erforderlich</span><span class="sxs-lookup"><span data-stu-id="ac58e-115">Initial negotiation requires server authentication</span></span>|  
|<span data-ttu-id="ac58e-116">Authentifizierung (Client)</span><span class="sxs-lookup"><span data-stu-id="ac58e-116">Authentication (Client)</span></span>|<span data-ttu-id="ac58e-117">Benutzername/Kennwort</span><span class="sxs-lookup"><span data-stu-id="ac58e-117">User name/password</span></span>|  
|<span data-ttu-id="ac58e-118">Integrität</span><span class="sxs-lookup"><span data-stu-id="ac58e-118">Integrity</span></span>|<span data-ttu-id="ac58e-119">Ja, mit freigegebenem Sicherheitskontext</span><span class="sxs-lookup"><span data-stu-id="ac58e-119">Yes, using shared security context</span></span>|  
|<span data-ttu-id="ac58e-120">Vertraulichkeit</span><span class="sxs-lookup"><span data-stu-id="ac58e-120">Confidentiality</span></span>|<span data-ttu-id="ac58e-121">Ja, mit freigegebenem Sicherheitskontext</span><span class="sxs-lookup"><span data-stu-id="ac58e-121">Yes, using shared security context</span></span>|  
|<span data-ttu-id="ac58e-122">Transport</span><span class="sxs-lookup"><span data-stu-id="ac58e-122">Transport</span></span>|<span data-ttu-id="ac58e-123">HTTP</span><span class="sxs-lookup"><span data-stu-id="ac58e-123">HTTP</span></span>|  
|<span data-ttu-id="ac58e-124">Bindung</span><span class="sxs-lookup"><span data-stu-id="ac58e-124">Binding</span></span>|<xref:System.ServiceModel.WSHttpBinding>|  
  
## <a name="service"></a><span data-ttu-id="ac58e-125">Dienst</span><span class="sxs-lookup"><span data-stu-id="ac58e-125">Service</span></span>  
 <span data-ttu-id="ac58e-126">Der folgende Code und die folgende Konfiguration werden unabhängig voneinander ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="ac58e-126">The following code and configuration are meant to run independently.</span></span> <span data-ttu-id="ac58e-127">Führen Sie einen der folgenden Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="ac58e-127">Do one of the following:</span></span>  
  
- <span data-ttu-id="ac58e-128">Erstellen Sie einen separaten Dienst, indem Sie den Code ohne Konfiguration verwenden.</span><span class="sxs-lookup"><span data-stu-id="ac58e-128">Create a stand-alone service using the code with no configuration.</span></span>  
  
- <span data-ttu-id="ac58e-129">Erstellen Sie mit der angegebenen Konfiguration einen Dienst, aber definieren Sie keine Endpunkte.</span><span class="sxs-lookup"><span data-stu-id="ac58e-129">Create a service using the supplied configuration, but do not define any endpoints.</span></span>  
  
### <a name="code"></a><span data-ttu-id="ac58e-130">Code</span><span class="sxs-lookup"><span data-stu-id="ac58e-130">Code</span></span>  
 <span data-ttu-id="ac58e-131">Im folgenden Code wird gezeigt, wie ein Dienstendpunkt, der Nachrichtensicherheit verwendet, erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="ac58e-131">The following code shows how to create a service endpoint that uses message security.</span></span>  
  
 [!code-csharp[C_SecurityScenarios#9](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_securityscenarios/cs/source.cs#9)]
 [!code-vb[C_SecurityScenarios#9](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_securityscenarios/vb/source.vb#9)]  
  
### <a name="configuration"></a><span data-ttu-id="ac58e-132">Konfiguration</span><span class="sxs-lookup"><span data-stu-id="ac58e-132">Configuration</span></span>  
 <span data-ttu-id="ac58e-133">Die folgende Konfiguration kann statt des Codes verwendet werden:</span><span class="sxs-lookup"><span data-stu-id="ac58e-133">The following configuration can be used instead of the code:</span></span>  
  
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
  
## <a name="client"></a><span data-ttu-id="ac58e-134">Client</span><span class="sxs-lookup"><span data-stu-id="ac58e-134">Client</span></span>  
  
### <a name="code"></a><span data-ttu-id="ac58e-135">Code</span><span class="sxs-lookup"><span data-stu-id="ac58e-135">Code</span></span>  
 <span data-ttu-id="ac58e-136">Der folgende Code erstellt den Client.</span><span class="sxs-lookup"><span data-stu-id="ac58e-136">The following code creates the client.</span></span> <span data-ttu-id="ac58e-137">Die Bindung bezieht sich auf den Nachrichtensicherheitsmodus, und der Clientanmeldeinformationstyp wird auf `UserName` festgelegt.</span><span class="sxs-lookup"><span data-stu-id="ac58e-137">The binding is to message mode security, and the client credential type is set to `UserName`.</span></span> <span data-ttu-id="ac58e-138">Der Benutzername und das Kennwort können nur mit Code (nicht konfigurierbar) angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="ac58e-138">The user name and password can only be specified using code (it is not configurable).</span></span> <span data-ttu-id="ac58e-139">Der Code zum Zurückgeben des Benutzernamens und des Kennworts ist hier nicht gezeigt, da dies auf Anwendungsebene erfolgen muss.</span><span class="sxs-lookup"><span data-stu-id="ac58e-139">The code to return the user name and password is not shown here because it must be done at the application level.</span></span> <span data-ttu-id="ac58e-140">Verwenden Sie z. B. ein Windows Forms-Dialogfeld, um vom Benutzer Daten abzufragen.</span><span class="sxs-lookup"><span data-stu-id="ac58e-140">For example, use a Windows Forms dialog box to query the user for the data.</span></span>  
  
 [!code-csharp[C_SecurityScenarios#16](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_securityscenarios/cs/source.cs#16)]
 [!code-vb[C_SecurityScenarios#16](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_securityscenarios/vb/source.vb#16)]  
  
### <a name="configuration"></a><span data-ttu-id="ac58e-141">Konfiguration</span><span class="sxs-lookup"><span data-stu-id="ac58e-141">Configuration</span></span>  
 <span data-ttu-id="ac58e-142">Der folgende Code dient zum Konfigurieren des Clients.</span><span class="sxs-lookup"><span data-stu-id="ac58e-142">The following code configures the client.</span></span> <span data-ttu-id="ac58e-143">Die Bindung bezieht sich auf den Nachrichtensicherheitsmodus, und der Clientanmeldeinformationstyp wird auf `UserName` festgelegt.</span><span class="sxs-lookup"><span data-stu-id="ac58e-143">The binding is to message mode security, and the client credential type is set to `UserName`.</span></span> <span data-ttu-id="ac58e-144">Der Benutzername und das Kennwort können nur mit Code (nicht konfigurierbar) angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="ac58e-144">The user name and password can only be specified using code (it is not configurable).</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="ac58e-145">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="ac58e-145">See also</span></span>

- [<span data-ttu-id="ac58e-146">Sicherheitsübersicht</span><span class="sxs-lookup"><span data-stu-id="ac58e-146">Security Overview</span></span>](security-overview.md)
- [<span data-ttu-id="ac58e-147">Nachrichtensicherheit – Benutzername</span><span class="sxs-lookup"><span data-stu-id="ac58e-147">Message Security User Name</span></span>](../samples/message-security-user-name.md)
- [<span data-ttu-id="ac58e-148">Dienstidentität und Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="ac58e-148">Service Identity and Authentication</span></span>](service-identity-and-authentication.md)
- [\<identity>](../../configure-apps/file-schema/wcf/identity.md)
- <span data-ttu-id="ac58e-149">[Sicherheitsmodell für Windows Server AppFabric](https://docs.microsoft.com/previous-versions/appfabric/ee677202(v=azure.10))</span><span class="sxs-lookup"><span data-stu-id="ac58e-149">[Security Model for Windows Server App Fabric](https://docs.microsoft.com/previous-versions/appfabric/ee677202(v=azure.10))</span></span>
