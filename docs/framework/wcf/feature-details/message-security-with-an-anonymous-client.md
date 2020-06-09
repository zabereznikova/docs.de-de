---
title: Nachrichtensicherheit mit einem anonymen Client
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: cad53e1a-b7c9-4064-bc87-508c3d1dce49
ms.openlocfilehash: 058163c96bba036c3183695bf986b4d0424271ac
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/09/2020
ms.locfileid: "84595218"
---
# <a name="message-security-with-an-anonymous-client"></a><span data-ttu-id="0d1de-102">Nachrichtensicherheit mit einem anonymen Client</span><span class="sxs-lookup"><span data-stu-id="0d1de-102">Message Security with an Anonymous Client</span></span>

<span data-ttu-id="0d1de-103">Das folgende Szenario zeigt einen-Client und-Dienst, der durch Windows Communication Foundation (WCF)-Nachrichten Sicherheit geschützt wird.</span><span class="sxs-lookup"><span data-stu-id="0d1de-103">The following scenario shows a client and service secured by Windows Communication Foundation (WCF) message security.</span></span> <span data-ttu-id="0d1de-104">Ein Entwurfsziel ist die Verwendung von Nachrichtensicherheit statt Transportsicherheit, sodass zu einem späteren Zeitpunkt ein komplexeres anspruchsbasierter Modell unterstützt werden kann.</span><span class="sxs-lookup"><span data-stu-id="0d1de-104">A design goal is to use message security rather than transport security, so that in the future it can support a richer claims-based model.</span></span> <span data-ttu-id="0d1de-105">Weitere Informationen zur Verwendung umfangreicher Autorisierungs Ansprüche finden Sie unter [Verwalten von Ansprüchen und Autorisierung mit dem Identitäts Modell](managing-claims-and-authorization-with-the-identity-model.md).</span><span class="sxs-lookup"><span data-stu-id="0d1de-105">For more information about using rich claims for authorization, see [Managing Claims and Authorization with the Identity Model](managing-claims-and-authorization-with-the-identity-model.md).</span></span>

<span data-ttu-id="0d1de-106">Eine Beispielanwendung finden Sie unter [Nachrichten Sicherheit anonym](../samples/message-security-anonymous.md).</span><span class="sxs-lookup"><span data-stu-id="0d1de-106">For a sample application, see [Message Security Anonymous](../samples/message-security-anonymous.md).</span></span>

<span data-ttu-id="0d1de-107">![Nachrichten Sicherheit mit einem anonymen Client](media/b361a565-831c-4c10-90d7-66d8eeece0a1.gif "b361a565-831c-4c10-90d7-66d8eeece0a1")</span><span class="sxs-lookup"><span data-stu-id="0d1de-107">![Message security with an anonymous client](media/b361a565-831c-4c10-90d7-66d8eeece0a1.gif "b361a565-831c-4c10-90d7-66d8eeece0a1")</span></span>

|<span data-ttu-id="0d1de-108">Merkmal</span><span class="sxs-lookup"><span data-stu-id="0d1de-108">Characteristic</span></span>|<span data-ttu-id="0d1de-109">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="0d1de-109">Description</span></span>|
|--------------------|-----------------|
|<span data-ttu-id="0d1de-110">Sicherheitsmodus</span><span class="sxs-lookup"><span data-stu-id="0d1de-110">Security Mode</span></span>|<span data-ttu-id="0d1de-111">`Message`</span><span class="sxs-lookup"><span data-stu-id="0d1de-111">Message</span></span>|
|<span data-ttu-id="0d1de-112">Interoperabilität</span><span class="sxs-lookup"><span data-stu-id="0d1de-112">Interoperability</span></span>|<span data-ttu-id="0d1de-113">Nur WCF</span><span class="sxs-lookup"><span data-stu-id="0d1de-113">WCF only</span></span>|
|<span data-ttu-id="0d1de-114">Authentifizierung (Server)</span><span class="sxs-lookup"><span data-stu-id="0d1de-114">Authentication (Server)</span></span>|<span data-ttu-id="0d1de-115">Die erste Aushandlung erfordert die Serverauthentifizierung, jedoch keine Clientauthentifizierung</span><span class="sxs-lookup"><span data-stu-id="0d1de-115">Initial negotiation requires server authentication, but not client authentication</span></span>|
|<span data-ttu-id="0d1de-116">Authentifizierung (Client)</span><span class="sxs-lookup"><span data-stu-id="0d1de-116">Authentication (Client)</span></span>|<span data-ttu-id="0d1de-117">Keine</span><span class="sxs-lookup"><span data-stu-id="0d1de-117">None</span></span>|
|<span data-ttu-id="0d1de-118">Integrität</span><span class="sxs-lookup"><span data-stu-id="0d1de-118">Integrity</span></span>|<span data-ttu-id="0d1de-119">Ja, mit freigegebenem Sicherheitskontext</span><span class="sxs-lookup"><span data-stu-id="0d1de-119">Yes, using shared security context</span></span>|
|<span data-ttu-id="0d1de-120">Vertraulichkeit</span><span class="sxs-lookup"><span data-stu-id="0d1de-120">Confidentiality</span></span>|<span data-ttu-id="0d1de-121">Ja, mit freigegebenem Sicherheitskontext</span><span class="sxs-lookup"><span data-stu-id="0d1de-121">Yes, using shared security context</span></span>|
|<span data-ttu-id="0d1de-122">Transport</span><span class="sxs-lookup"><span data-stu-id="0d1de-122">Transport</span></span>|<span data-ttu-id="0d1de-123">HTTP</span><span class="sxs-lookup"><span data-stu-id="0d1de-123">HTTP</span></span>|

## <a name="service"></a><span data-ttu-id="0d1de-124">Dienst</span><span class="sxs-lookup"><span data-stu-id="0d1de-124">Service</span></span>

<span data-ttu-id="0d1de-125">Der folgende Code und die folgende Konfiguration werden unabhängig voneinander ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="0d1de-125">The following code and configuration are meant to run independently.</span></span> <span data-ttu-id="0d1de-126">Führen Sie einen der folgenden Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="0d1de-126">Do one of the following:</span></span>

- <span data-ttu-id="0d1de-127">Erstellen Sie einen separaten Dienst, indem Sie den Code ohne Konfiguration verwenden.</span><span class="sxs-lookup"><span data-stu-id="0d1de-127">Create a stand-alone service using the code with no configuration.</span></span>

- <span data-ttu-id="0d1de-128">Erstellen Sie mit der angegebenen Konfiguration einen Dienst, aber definieren Sie keine Endpunkte.</span><span class="sxs-lookup"><span data-stu-id="0d1de-128">Create a service using the supplied configuration, but do not define any endpoints.</span></span>

### <a name="code"></a><span data-ttu-id="0d1de-129">Code</span><span class="sxs-lookup"><span data-stu-id="0d1de-129">Code</span></span>

<span data-ttu-id="0d1de-130">Im folgenden Code wird gezeigt, wie ein Dienstendpunkt, der Nachrichtensicherheit verwendet, erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="0d1de-130">The following code shows how to create a service endpoint that uses message security.</span></span>

[!code-csharp[C_SecurityScenarios#8](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_securityscenarios/cs/source.cs#8)]
[!code-vb[C_SecurityScenarios#8](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_securityscenarios/vb/source.vb#8)]

### <a name="configuration"></a><span data-ttu-id="0d1de-131">Konfiguration</span><span class="sxs-lookup"><span data-stu-id="0d1de-131">Configuration</span></span>

<span data-ttu-id="0d1de-132">Anstelle des Codes kann die folgende Konfiguration verwendet werden:</span><span class="sxs-lookup"><span data-stu-id="0d1de-132">The following configuration can be used instead of the code.</span></span> <span data-ttu-id="0d1de-133">Mit dem Element für das Dienstverhalten wird ein Zertifikat angegeben, mit dem der Dienst gegenüber dem Client authentifiziert wird.</span><span class="sxs-lookup"><span data-stu-id="0d1de-133">The service behavior element is used to specify a certificate that is used to authenticate the service to the client.</span></span> <span data-ttu-id="0d1de-134">Das Dienstelement muss das Verhalten mit dem `behaviorConfiguration`-Attribut angeben.</span><span class="sxs-lookup"><span data-stu-id="0d1de-134">The service element must specify the behavior using the `behaviorConfiguration` attribute.</span></span> <span data-ttu-id="0d1de-135">Das Bindungselement gibt an, dass der Clientanmeldeinformationstyp `None` ist, sodass anonyme Clients den Dienst verwenden können.</span><span class="sxs-lookup"><span data-stu-id="0d1de-135">The binding element specifies that the client credential type is `None`, allowing anonymous clients to use the service.</span></span>

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

## <a name="client"></a><span data-ttu-id="0d1de-136">Client</span><span class="sxs-lookup"><span data-stu-id="0d1de-136">Client</span></span>

<span data-ttu-id="0d1de-137">Der folgende Code und die folgende Konfiguration werden unabhängig voneinander ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="0d1de-137">The following code and configuration are meant to run independently.</span></span> <span data-ttu-id="0d1de-138">Führen Sie einen der folgenden Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="0d1de-138">Do one of the following:</span></span>

- <span data-ttu-id="0d1de-139">Erstellen Sie mit dem Code (und Clientcode) einen eigenständigen Client.</span><span class="sxs-lookup"><span data-stu-id="0d1de-139">Create a stand-alone client using the code (and client code).</span></span>

- <span data-ttu-id="0d1de-140">Erstellen Sie einen Client, der keine Endpunktadressen definiert.</span><span class="sxs-lookup"><span data-stu-id="0d1de-140">Create a client that does not define any endpoint addresses.</span></span> <span data-ttu-id="0d1de-141">Verwenden Sie stattdessen den Clientkonstruktor, der den Konfigurationsnamen als Argument verwendet.</span><span class="sxs-lookup"><span data-stu-id="0d1de-141">Instead, use the client constructor that takes the configuration name as an argument.</span></span> <span data-ttu-id="0d1de-142">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="0d1de-142">For example:</span></span>

    [!code-csharp[C_SecurityScenarios#0](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_securityscenarios/cs/source.cs#0)]
    [!code-vb[C_SecurityScenarios#0](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_securityscenarios/vb/source.vb#0)]

### <a name="code"></a><span data-ttu-id="0d1de-143">Code</span><span class="sxs-lookup"><span data-stu-id="0d1de-143">Code</span></span>

<span data-ttu-id="0d1de-144">Der folgende Code erstellt eine Instanz des Clients.</span><span class="sxs-lookup"><span data-stu-id="0d1de-144">The following code creates an instance of the client.</span></span> <span data-ttu-id="0d1de-145">Die Bindung verwendet den Nachrichtensicherheitsmodus, und der Clientanmeldeinformationstyp wird auf „none“ festgelegt.</span><span class="sxs-lookup"><span data-stu-id="0d1de-145">The binding uses message mode security, and the client credential type is set to none.</span></span>

[!code-csharp[C_SecurityScenarios#15](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_securityscenarios/cs/source.cs#15)]
[!code-vb[C_SecurityScenarios#15](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_securityscenarios/vb/source.vb#15)]

### <a name="configuration"></a><span data-ttu-id="0d1de-146">Konfiguration</span><span class="sxs-lookup"><span data-stu-id="0d1de-146">Configuration</span></span>

<span data-ttu-id="0d1de-147">Der folgende Code dient zum Konfigurieren des Clients.</span><span class="sxs-lookup"><span data-stu-id="0d1de-147">The following code configures the client.</span></span>

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

## <a name="see-also"></a><span data-ttu-id="0d1de-148">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="0d1de-148">See also</span></span>

- [<span data-ttu-id="0d1de-149">Sicherheitsübersicht</span><span class="sxs-lookup"><span data-stu-id="0d1de-149">Security Overview</span></span>](security-overview.md)
- [<span data-ttu-id="0d1de-150">Sicherheit bei verteilten Anwendungen</span><span class="sxs-lookup"><span data-stu-id="0d1de-150">Distributed Application Security</span></span>](distributed-application-security.md)
- [<span data-ttu-id="0d1de-151">Nachrichtensicherheit – anonym</span><span class="sxs-lookup"><span data-stu-id="0d1de-151">Message Security Anonymous</span></span>](../samples/message-security-anonymous.md)
- [<span data-ttu-id="0d1de-152">Dienstidentität und Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="0d1de-152">Service Identity and Authentication</span></span>](service-identity-and-authentication.md)
- <span data-ttu-id="0d1de-153">[Sicherheitsmodell für Windows Server AppFabric](https://docs.microsoft.com/previous-versions/appfabric/ee677202(v=azure.10))</span><span class="sxs-lookup"><span data-stu-id="0d1de-153">[Security Model for Windows Server App Fabric](https://docs.microsoft.com/previous-versions/appfabric/ee677202(v=azure.10))</span></span>
