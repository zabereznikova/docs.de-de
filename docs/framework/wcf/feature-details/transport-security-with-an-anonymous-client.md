---
title: Mit einem anonymen Client - WCF-transportsicherheit
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 056653a5-384e-4a02-ae3c-1b0157d2ccb4
ms.openlocfilehash: aac3b2ac6cfcca137bddaefafd290e744ee991eb
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/15/2019
ms.locfileid: "65637442"
---
# <a name="transport-security-with-an-anonymous-client"></a><span data-ttu-id="98bcc-102">Transportsicherheit mit einem anonymen client</span><span class="sxs-lookup"><span data-stu-id="98bcc-102">Transport security with an anonymous client</span></span>

<span data-ttu-id="98bcc-103">Das Windows Communication Foundation (WCF)-Szenario verwendet transportsicherheit (HTTPS), um Vertraulichkeit und Integrität sicherzustellen.</span><span class="sxs-lookup"><span data-stu-id="98bcc-103">This Windows Communication Foundation (WCF) scenario uses transport security (HTTPS) to ensure confidentiality and integrity.</span></span> <span data-ttu-id="98bcc-104">Der Server muss mit einem SSL-Zertifikat authentifiziert werden, und die Clients müssen das Zertifikat des Servers als vertrauenswürdig ansehen.</span><span class="sxs-lookup"><span data-stu-id="98bcc-104">The server must be authenticated with a Secure Sockets Layer (SSL) certificate, and the clients must trust the server's certificate.</span></span> <span data-ttu-id="98bcc-105">Der Client wird von keinem Mechanismus authentifiziert und ist deshalb anonym.</span><span class="sxs-lookup"><span data-stu-id="98bcc-105">The client is not authenticated by any mechanism and is, therefore, anonymous.</span></span>

<span data-ttu-id="98bcc-106">Eine beispielanwendung finden Sie unter [WS-Transportsicherheit](../samples/ws-transport-security.md).</span><span class="sxs-lookup"><span data-stu-id="98bcc-106">For a sample application, see [WS Transport Security](../samples/ws-transport-security.md).</span></span> <span data-ttu-id="98bcc-107">Weitere Informationen zur transportsicherheit finden Sie unter [Transport Sicherheitsübersicht](transport-security-overview.md).</span><span class="sxs-lookup"><span data-stu-id="98bcc-107">For more information about transport security, see [Transport Security Overview](transport-security-overview.md).</span></span>

<span data-ttu-id="98bcc-108">Weitere Informationen zur Verwendung eines Zertifikats mit einem Dienst finden Sie unter [arbeiten mit Zertifikaten](working-with-certificates.md) und [Vorgehensweise: Konfigurieren eines Anschlusses mit einem SSL-Zertifikat](how-to-configure-a-port-with-an-ssl-certificate.md).</span><span class="sxs-lookup"><span data-stu-id="98bcc-108">For more information about using a certificate with a service, see [Working with Certificates](working-with-certificates.md) and [How to: Configure a Port with an SSL Certificate](how-to-configure-a-port-with-an-ssl-certificate.md).</span></span>

![Verwenden von Transportsicherheit mit einem anonymen Client](./media/8fa2e931-0cfb-4aaa-9272-91d652b85d8d.gif)

|<span data-ttu-id="98bcc-110">Merkmal</span><span class="sxs-lookup"><span data-stu-id="98bcc-110">Characteristic</span></span>|<span data-ttu-id="98bcc-111">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="98bcc-111">Description</span></span>|
|--------------------|-----------------|
|<span data-ttu-id="98bcc-112">Sicherheitsmodus</span><span class="sxs-lookup"><span data-stu-id="98bcc-112">Security Mode</span></span>|<span data-ttu-id="98bcc-113">Transport</span><span class="sxs-lookup"><span data-stu-id="98bcc-113">Transport</span></span>|
|<span data-ttu-id="98bcc-114">Interoperabilität</span><span class="sxs-lookup"><span data-stu-id="98bcc-114">Interoperability</span></span>|<span data-ttu-id="98bcc-115">Mit vorhandenen Webdiensten und Webclients</span><span class="sxs-lookup"><span data-stu-id="98bcc-115">With existing Web services and clients</span></span>|
|<span data-ttu-id="98bcc-116">Authentifizierung (Server)</span><span class="sxs-lookup"><span data-stu-id="98bcc-116">Authentication (Server)</span></span><br /><br /> <span data-ttu-id="98bcc-117">Authentifizierung (Client)</span><span class="sxs-lookup"><span data-stu-id="98bcc-117">Authentication (Client)</span></span>|<span data-ttu-id="98bcc-118">Ja</span><span class="sxs-lookup"><span data-stu-id="98bcc-118">Yes</span></span><br /><br /> <span data-ttu-id="98bcc-119">Die Anwendungsebene (keine WCF-Unterstützung)</span><span class="sxs-lookup"><span data-stu-id="98bcc-119">Application level (no WCF support)</span></span>|
|<span data-ttu-id="98bcc-120">Integrität</span><span class="sxs-lookup"><span data-stu-id="98bcc-120">Integrity</span></span>|<span data-ttu-id="98bcc-121">Ja</span><span class="sxs-lookup"><span data-stu-id="98bcc-121">Yes</span></span>|
|<span data-ttu-id="98bcc-122">Vertraulichkeit</span><span class="sxs-lookup"><span data-stu-id="98bcc-122">Confidentiality</span></span>|<span data-ttu-id="98bcc-123">Ja</span><span class="sxs-lookup"><span data-stu-id="98bcc-123">Yes</span></span>|
|<span data-ttu-id="98bcc-124">Transport</span><span class="sxs-lookup"><span data-stu-id="98bcc-124">Transport</span></span>|<span data-ttu-id="98bcc-125">HTTPS</span><span class="sxs-lookup"><span data-stu-id="98bcc-125">HTTPS</span></span>|
|<span data-ttu-id="98bcc-126">Bindung</span><span class="sxs-lookup"><span data-stu-id="98bcc-126">Binding</span></span>|<xref:System.ServiceModel.WSHttpBinding>|

## <a name="service"></a><span data-ttu-id="98bcc-127">Dienst</span><span class="sxs-lookup"><span data-stu-id="98bcc-127">Service</span></span>

<span data-ttu-id="98bcc-128">Der folgende Code und die folgende Konfiguration werden unabhängig voneinander ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="98bcc-128">The following code and configuration are meant to run independently.</span></span> <span data-ttu-id="98bcc-129">Führen Sie einen der folgenden Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="98bcc-129">Do one of the following:</span></span>

- <span data-ttu-id="98bcc-130">Erstellen Sie einen separaten Dienst, indem Sie den Code ohne Konfiguration verwenden.</span><span class="sxs-lookup"><span data-stu-id="98bcc-130">Create a stand-alone service using the code with no configuration.</span></span>

- <span data-ttu-id="98bcc-131">Erstellen Sie mit der angegebenen Konfiguration einen Dienst, aber definieren Sie keine Endpunkte.</span><span class="sxs-lookup"><span data-stu-id="98bcc-131">Create a service using the supplied configuration, but do not define any endpoints.</span></span>

### <a name="code"></a><span data-ttu-id="98bcc-132">Code</span><span class="sxs-lookup"><span data-stu-id="98bcc-132">Code</span></span>

<span data-ttu-id="98bcc-133">Im folgenden Code wird gezeigt, wie ein Endpunkt mit Transportsicherheit erstellt wird:</span><span class="sxs-lookup"><span data-stu-id="98bcc-133">The following code shows how to create an endpoint using transport security:</span></span>

[!code-csharp[c_SecurityScenarios#5](~/samples/snippets/csharp/VS_Snippets_CFX/c_securityscenarios/cs/source.cs#5)]
[!code-vb[c_SecurityScenarios#5](~/samples/snippets/visualbasic/VS_Snippets_CFX/c_securityscenarios/vb/source.vb#5)]

### <a name="configuration"></a><span data-ttu-id="98bcc-134">Konfiguration</span><span class="sxs-lookup"><span data-stu-id="98bcc-134">Configuration</span></span>

<span data-ttu-id="98bcc-135">Mit dem folgenden Code wird derselbe Endpunkt mithilfe von Konfiguration eingerichtet.</span><span class="sxs-lookup"><span data-stu-id="98bcc-135">The following code sets up the same endpoint using configuration.</span></span> <span data-ttu-id="98bcc-136">Der Client wird von keinem Mechanismus authentifiziert und ist deshalb anonym.</span><span class="sxs-lookup"><span data-stu-id="98bcc-136">The client is not authenticated by any mechanism, and is therefore anonymous.</span></span>

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

## <a name="client"></a><span data-ttu-id="98bcc-137">Client</span><span class="sxs-lookup"><span data-stu-id="98bcc-137">Client</span></span>

<span data-ttu-id="98bcc-138">Der folgende Code und die folgende Konfiguration werden unabhängig voneinander ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="98bcc-138">The following code and configuration are meant to run independently.</span></span> <span data-ttu-id="98bcc-139">Führen Sie einen der folgenden Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="98bcc-139">Do one of the following:</span></span>

- <span data-ttu-id="98bcc-140">Erstellen Sie mit dem Code (und Clientcode) einen eigenständigen Client.</span><span class="sxs-lookup"><span data-stu-id="98bcc-140">Create a stand-alone client using the code (and client code).</span></span>

- <span data-ttu-id="98bcc-141">Erstellen Sie einen Client, der keine Endpunktadressen definiert.</span><span class="sxs-lookup"><span data-stu-id="98bcc-141">Create a client that does not define any endpoint addresses.</span></span> <span data-ttu-id="98bcc-142">Verwenden Sie stattdessen den Clientkonstruktor, der den Konfigurationsnamen als Argument verwendet.</span><span class="sxs-lookup"><span data-stu-id="98bcc-142">Instead, use the client constructor that takes the configuration name as an argument.</span></span> <span data-ttu-id="98bcc-143">Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="98bcc-143">For example:</span></span>

     [!code-csharp[C_SecurityScenarios#0](~/samples/snippets/csharp/VS_Snippets_CFX/c_securityscenarios/cs/source.cs#0)]
     [!code-vb[C_SecurityScenarios#0](~/samples/snippets/visualbasic/VS_Snippets_CFX/c_securityscenarios/vb/source.vb#0)]

### <a name="code"></a><span data-ttu-id="98bcc-144">Code</span><span class="sxs-lookup"><span data-stu-id="98bcc-144">Code</span></span>

[!code-csharp[c_SecurityScenarios#6](~/samples/snippets/csharp/VS_Snippets_CFX/c_securityscenarios/cs/source.cs#6)]
[!code-vb[c_SecurityScenarios#6](~/samples/snippets/visualbasic/VS_Snippets_CFX/c_securityscenarios/vb/source.vb#6)]

### <a name="configuration"></a><span data-ttu-id="98bcc-145">Konfiguration</span><span class="sxs-lookup"><span data-stu-id="98bcc-145">Configuration</span></span>

<span data-ttu-id="98bcc-146">Die folgende Konfiguration kann statt des Codes verwendet werden, um den Dienst einzurichten.</span><span class="sxs-lookup"><span data-stu-id="98bcc-146">The following configuration can be used instead of the code to set up the service.</span></span>

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

## <a name="see-also"></a><span data-ttu-id="98bcc-147">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="98bcc-147">See also</span></span>

- [<span data-ttu-id="98bcc-148">Übersicht über die Sicherheit</span><span class="sxs-lookup"><span data-stu-id="98bcc-148">Security Overview</span></span>](security-overview.md)
- [<span data-ttu-id="98bcc-149">WS-Transportsicherheit</span><span class="sxs-lookup"><span data-stu-id="98bcc-149">WS Transport Security</span></span>](../samples/ws-transport-security.md)
- [<span data-ttu-id="98bcc-150">Übersicht über die Transportsicherheit</span><span class="sxs-lookup"><span data-stu-id="98bcc-150">Transport Security Overview</span></span>](transport-security-overview.md)
- <span data-ttu-id="98bcc-151">[Sicherheitsmodell für Windows Server AppFabric](https://docs.microsoft.com/previous-versions/appfabric/ee677202(v=azure.10))</span><span class="sxs-lookup"><span data-stu-id="98bcc-151">[Security Model for Windows Server App Fabric](https://docs.microsoft.com/previous-versions/appfabric/ee677202(v=azure.10))</span></span>
