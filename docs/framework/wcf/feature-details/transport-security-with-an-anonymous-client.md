---
title: Transport Sicherheit mit einem anonymen Client
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 056653a5-384e-4a02-ae3c-1b0157d2ccb4
ms.openlocfilehash: c3e44c87dfa70ac3a7acc5a83ac596efc22b6155
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/25/2019
ms.locfileid: "75344759"
---
# <a name="transport-security-with-an-anonymous-client"></a><span data-ttu-id="4db22-102">Transport Sicherheit mit einem anonymen Client</span><span class="sxs-lookup"><span data-stu-id="4db22-102">Transport security with an anonymous client</span></span>

<span data-ttu-id="4db22-103">Dieses Windows Communication Foundation (WCF)-Szenario verwendet Transportsicherheit (HTTPS), um Vertraulichkeit und Integrität sicherzustellen.</span><span class="sxs-lookup"><span data-stu-id="4db22-103">This Windows Communication Foundation (WCF) scenario uses transport security (HTTPS) to ensure confidentiality and integrity.</span></span> <span data-ttu-id="4db22-104">Der Server muss mit einem SSL-Zertifikat authentifiziert werden, und die Clients müssen das Zertifikat des Servers als vertrauenswürdig ansehen.</span><span class="sxs-lookup"><span data-stu-id="4db22-104">The server must be authenticated with a Secure Sockets Layer (SSL) certificate, and the clients must trust the server's certificate.</span></span> <span data-ttu-id="4db22-105">Der Client wird von keinem Mechanismus authentifiziert und ist deshalb anonym.</span><span class="sxs-lookup"><span data-stu-id="4db22-105">The client is not authenticated by any mechanism and is, therefore, anonymous.</span></span>

<span data-ttu-id="4db22-106">Eine Beispielanwendung finden Sie unter [WS-Transport Sicherheit](../samples/ws-transport-security.md).</span><span class="sxs-lookup"><span data-stu-id="4db22-106">For a sample application, see [WS Transport Security](../samples/ws-transport-security.md).</span></span> <span data-ttu-id="4db22-107">Weitere Informationen zur Transportsicherheit finden Sie unter [Übersicht über die Transportsicherheit](transport-security-overview.md).</span><span class="sxs-lookup"><span data-stu-id="4db22-107">For more information about transport security, see [Transport Security Overview](transport-security-overview.md).</span></span>

<span data-ttu-id="4db22-108">Weitere Informationen zum Verwenden eines Zertifikats mit einem Dienst finden Sie unter [Arbeiten mit Zertifikaten](working-with-certificates.md) und Gewusst [wie: Konfigurieren eines Ports mit einem SSL-Zertifikat](how-to-configure-a-port-with-an-ssl-certificate.md).</span><span class="sxs-lookup"><span data-stu-id="4db22-108">For more information about using a certificate with a service, see [Working with Certificates](working-with-certificates.md) and [How to: Configure a Port with an SSL Certificate](how-to-configure-a-port-with-an-ssl-certificate.md).</span></span>

![Verwenden von Transportsicherheit mit einem anonymen Client](./media/8fa2e931-0cfb-4aaa-9272-91d652b85d8d.gif)

|<span data-ttu-id="4db22-110">Merkmal</span><span class="sxs-lookup"><span data-stu-id="4db22-110">Characteristic</span></span>|<span data-ttu-id="4db22-111">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="4db22-111">Description</span></span>|
|--------------------|-----------------|
|<span data-ttu-id="4db22-112">Sicherheitsmodus</span><span class="sxs-lookup"><span data-stu-id="4db22-112">Security Mode</span></span>|<span data-ttu-id="4db22-113">Transport</span><span class="sxs-lookup"><span data-stu-id="4db22-113">Transport</span></span>|
|<span data-ttu-id="4db22-114">Interoperabilität</span><span class="sxs-lookup"><span data-stu-id="4db22-114">Interoperability</span></span>|<span data-ttu-id="4db22-115">Mit vorhandenen Webdiensten und Webclients</span><span class="sxs-lookup"><span data-stu-id="4db22-115">With existing Web services and clients</span></span>|
|<span data-ttu-id="4db22-116">Authentifizierung (Server)</span><span class="sxs-lookup"><span data-stu-id="4db22-116">Authentication (Server)</span></span><br /><br /> <span data-ttu-id="4db22-117">Authentifizierung (Client)</span><span class="sxs-lookup"><span data-stu-id="4db22-117">Authentication (Client)</span></span>|<span data-ttu-id="4db22-118">Ja</span><span class="sxs-lookup"><span data-stu-id="4db22-118">Yes</span></span><br /><br /> <span data-ttu-id="4db22-119">Anwendungsebene (keine WCF-Unterstützung)</span><span class="sxs-lookup"><span data-stu-id="4db22-119">Application level (no WCF support)</span></span>|
|<span data-ttu-id="4db22-120">Integrität</span><span class="sxs-lookup"><span data-stu-id="4db22-120">Integrity</span></span>|<span data-ttu-id="4db22-121">Ja</span><span class="sxs-lookup"><span data-stu-id="4db22-121">Yes</span></span>|
|<span data-ttu-id="4db22-122">Vertraulichkeit</span><span class="sxs-lookup"><span data-stu-id="4db22-122">Confidentiality</span></span>|<span data-ttu-id="4db22-123">Ja</span><span class="sxs-lookup"><span data-stu-id="4db22-123">Yes</span></span>|
|<span data-ttu-id="4db22-124">Transport</span><span class="sxs-lookup"><span data-stu-id="4db22-124">Transport</span></span>|<span data-ttu-id="4db22-125">HTTPS</span><span class="sxs-lookup"><span data-stu-id="4db22-125">HTTPS</span></span>|
|<span data-ttu-id="4db22-126">Bindung</span><span class="sxs-lookup"><span data-stu-id="4db22-126">Binding</span></span>|<xref:System.ServiceModel.WSHttpBinding>|

## <a name="service"></a><span data-ttu-id="4db22-127">Dienst</span><span class="sxs-lookup"><span data-stu-id="4db22-127">Service</span></span>

<span data-ttu-id="4db22-128">Der folgende Code und die folgende Konfiguration werden unabhängig voneinander ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="4db22-128">The following code and configuration are meant to run independently.</span></span> <span data-ttu-id="4db22-129">Führen Sie eine der folgenden Aktionen aus:</span><span class="sxs-lookup"><span data-stu-id="4db22-129">Do one of the following:</span></span>

- <span data-ttu-id="4db22-130">Erstellen Sie einen separaten Dienst, indem Sie den Code ohne Konfiguration verwenden.</span><span class="sxs-lookup"><span data-stu-id="4db22-130">Create a stand-alone service using the code with no configuration.</span></span>

- <span data-ttu-id="4db22-131">Erstellen Sie mit der angegebenen Konfiguration einen Dienst, aber definieren Sie keine Endpunkte.</span><span class="sxs-lookup"><span data-stu-id="4db22-131">Create a service using the supplied configuration, but do not define any endpoints.</span></span>

### <a name="code"></a><span data-ttu-id="4db22-132">Code</span><span class="sxs-lookup"><span data-stu-id="4db22-132">Code</span></span>

<span data-ttu-id="4db22-133">Im folgenden Code wird gezeigt, wie ein Endpunkt mit Transportsicherheit erstellt wird:</span><span class="sxs-lookup"><span data-stu-id="4db22-133">The following code shows how to create an endpoint using transport security:</span></span>

[!code-csharp[c_SecurityScenarios#5](~/samples/snippets/csharp/VS_Snippets_CFX/c_securityscenarios/cs/source.cs#5)]
[!code-vb[c_SecurityScenarios#5](~/samples/snippets/visualbasic/VS_Snippets_CFX/c_securityscenarios/vb/source.vb#5)]

### <a name="configuration"></a><span data-ttu-id="4db22-134">-Konfiguration</span><span class="sxs-lookup"><span data-stu-id="4db22-134">Configuration</span></span>

<span data-ttu-id="4db22-135">Mit dem folgenden Code wird derselbe Endpunkt mithilfe von Konfiguration eingerichtet.</span><span class="sxs-lookup"><span data-stu-id="4db22-135">The following code sets up the same endpoint using configuration.</span></span> <span data-ttu-id="4db22-136">Der Client wird von keinem Mechanismus authentifiziert und ist deshalb anonym.</span><span class="sxs-lookup"><span data-stu-id="4db22-136">The client is not authenticated by any mechanism, and is therefore anonymous.</span></span>

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

## <a name="client"></a><span data-ttu-id="4db22-137">Client</span><span class="sxs-lookup"><span data-stu-id="4db22-137">Client</span></span>

<span data-ttu-id="4db22-138">Der folgende Code und die folgende Konfiguration werden unabhängig voneinander ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="4db22-138">The following code and configuration are meant to run independently.</span></span> <span data-ttu-id="4db22-139">Führen Sie eine der folgenden Aktionen aus:</span><span class="sxs-lookup"><span data-stu-id="4db22-139">Do one of the following:</span></span>

- <span data-ttu-id="4db22-140">Erstellen Sie mit dem Code (und Clientcode) einen eigenständigen Client.</span><span class="sxs-lookup"><span data-stu-id="4db22-140">Create a stand-alone client using the code (and client code).</span></span>

- <span data-ttu-id="4db22-141">Erstellen Sie einen Client, der keine Endpunktadressen definiert.</span><span class="sxs-lookup"><span data-stu-id="4db22-141">Create a client that does not define any endpoint addresses.</span></span> <span data-ttu-id="4db22-142">Verwenden Sie stattdessen den Clientkonstruktor, der den Konfigurationsnamen als Argument verwendet.</span><span class="sxs-lookup"><span data-stu-id="4db22-142">Instead, use the client constructor that takes the configuration name as an argument.</span></span> <span data-ttu-id="4db22-143">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="4db22-143">For example:</span></span>

     [!code-csharp[C_SecurityScenarios#0](~/samples/snippets/csharp/VS_Snippets_CFX/c_securityscenarios/cs/source.cs#0)]
     [!code-vb[C_SecurityScenarios#0](~/samples/snippets/visualbasic/VS_Snippets_CFX/c_securityscenarios/vb/source.vb#0)]

### <a name="code"></a><span data-ttu-id="4db22-144">Code</span><span class="sxs-lookup"><span data-stu-id="4db22-144">Code</span></span>

[!code-csharp[c_SecurityScenarios#6](~/samples/snippets/csharp/VS_Snippets_CFX/c_securityscenarios/cs/source.cs#6)]
[!code-vb[c_SecurityScenarios#6](~/samples/snippets/visualbasic/VS_Snippets_CFX/c_securityscenarios/vb/source.vb#6)]

### <a name="configuration"></a><span data-ttu-id="4db22-145">-Konfiguration</span><span class="sxs-lookup"><span data-stu-id="4db22-145">Configuration</span></span>

<span data-ttu-id="4db22-146">Die folgende Konfiguration kann statt des Codes verwendet werden, um den Dienst einzurichten.</span><span class="sxs-lookup"><span data-stu-id="4db22-146">The following configuration can be used instead of the code to set up the service.</span></span>

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

## <a name="see-also"></a><span data-ttu-id="4db22-147">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="4db22-147">See also</span></span>

- [<span data-ttu-id="4db22-148">Übersicht über die Sicherheit</span><span class="sxs-lookup"><span data-stu-id="4db22-148">Security Overview</span></span>](security-overview.md)
- [<span data-ttu-id="4db22-149">WS-Transportsicherheit</span><span class="sxs-lookup"><span data-stu-id="4db22-149">WS Transport Security</span></span>](../samples/ws-transport-security.md)
- [<span data-ttu-id="4db22-150">Übersicht über die Transportsicherheit</span><span class="sxs-lookup"><span data-stu-id="4db22-150">Transport Security Overview</span></span>](transport-security-overview.md)
- <span data-ttu-id="4db22-151">[Sicherheitsmodell für Windows Server-App-Fabric](https://docs.microsoft.com/previous-versions/appfabric/ee677202(v=azure.10))</span><span class="sxs-lookup"><span data-stu-id="4db22-151">[Security Model for Windows Server App Fabric](https://docs.microsoft.com/previous-versions/appfabric/ee677202(v=azure.10))</span></span>
