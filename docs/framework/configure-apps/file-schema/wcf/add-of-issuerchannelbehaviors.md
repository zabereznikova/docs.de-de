---
title: <add> von <issuerChannelBehaviors>
ms.date: 03/30/2017
ms.assetid: 50710506-e28f-45dd-ab7e-bff6f44173db
ms.openlocfilehash: 325d6b8111115384b18547bd11ccec8a4a8af711
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69920116"
---
# <a name="add-of-issuerchannelbehaviors"></a><span data-ttu-id="3c978-102">\<> von \<issuerchannelverhaltensweisen hinzufügen ></span><span class="sxs-lookup"><span data-stu-id="3c978-102">\<add> of \<issuerChannelBehaviors></span></span>

<span data-ttu-id="3c978-103">Fügt ein zu verwendendes Endpunktverhalten bei der Kommunikation mit einem STS hinzu.</span><span class="sxs-lookup"><span data-stu-id="3c978-103">Adds an endpoint behavior to be used when communicating with an STS.</span></span>

> [!NOTE]
> <span data-ttu-id="3c978-104">Wenn ein Endpunkt Verhalten ein [ \<Clientanmelde->](clientcredentials.md) Element enthält, wird eine Ausnahme ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="3c978-104">If any endpoint behavior contains a [\<clientCredentials>](clientcredentials.md) element, an exception will be thrown.</span></span>

<span data-ttu-id="3c978-105">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="3c978-105">\<system.ServiceModel></span></span>\
<span data-ttu-id="3c978-106">\<Verhalten > </span><span class="sxs-lookup"><span data-stu-id="3c978-106">\<behaviors></span></span>\
<span data-ttu-id="3c978-107">Verhalten des endpointBehavior-Abschnitts \<> </span><span class="sxs-lookup"><span data-stu-id="3c978-107">endpointBehaviors section \<behavior></span></span>\
<span data-ttu-id="3c978-108">\<clientCredentials></span><span class="sxs-lookup"><span data-stu-id="3c978-108">\<clientCredentials></span></span>\
<span data-ttu-id="3c978-109">\<issuedToken></span><span class="sxs-lookup"><span data-stu-id="3c978-109">\<issuedToken></span></span>\
<span data-ttu-id="3c978-110">\<issuerchannelverhaltensweisen > Element </span><span class="sxs-lookup"><span data-stu-id="3c978-110">\<issuerChannelBehaviors> Element</span></span>\
<span data-ttu-id="3c978-111">\<add></span><span class="sxs-lookup"><span data-stu-id="3c978-111">\<add></span></span>

## <a name="syntax"></a><span data-ttu-id="3c978-112">Syntax</span><span class="sxs-lookup"><span data-stu-id="3c978-112">Syntax</span></span>

```xml
<add issuerAddress="string"
     behaviorConfiguration="string" />
```

## <a name="attributes-and-elements"></a><span data-ttu-id="3c978-113">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="3c978-113">Attributes and Elements</span></span>

<span data-ttu-id="3c978-114">In den folgenden Abschnitten werden Attribute, untergeordnete Elemente sowie übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="3c978-114">The following sections describe attributes, child elements, and parent elements</span></span>

### <a name="attributes"></a><span data-ttu-id="3c978-115">Attribute</span><span class="sxs-lookup"><span data-stu-id="3c978-115">Attributes</span></span>

|<span data-ttu-id="3c978-116">Attribut</span><span class="sxs-lookup"><span data-stu-id="3c978-116">Attribute</span></span>|<span data-ttu-id="3c978-117">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="3c978-117">Description</span></span>|
|---------------|-----------------|
|<span data-ttu-id="3c978-118">issuerAddress</span><span class="sxs-lookup"><span data-stu-id="3c978-118">issuerAddress</span></span>|<span data-ttu-id="3c978-119">Der URI des Sicherheitstokenausstellers, mit dem kommuniziert wird.</span><span class="sxs-lookup"><span data-stu-id="3c978-119">The URI of the security token issuer to communicate with.</span></span>|
|<span data-ttu-id="3c978-120">behaviorConfiguration</span><span class="sxs-lookup"><span data-stu-id="3c978-120">behaviorConfiguration</span></span>|<span data-ttu-id="3c978-121">Der Name eines in derselben Konfigurationsdatei definierten Endpunktverhaltens.</span><span class="sxs-lookup"><span data-stu-id="3c978-121">The name of an endpoint behavior defined in the same configuration file.</span></span>|

### <a name="child-elements"></a><span data-ttu-id="3c978-122">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="3c978-122">Child Elements</span></span>

<span data-ttu-id="3c978-123">Keine</span><span class="sxs-lookup"><span data-stu-id="3c978-123">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="3c978-124">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="3c978-124">Parent Elements</span></span>

|<span data-ttu-id="3c978-125">Element</span><span class="sxs-lookup"><span data-stu-id="3c978-125">Element</span></span>|<span data-ttu-id="3c978-126">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="3c978-126">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="3c978-127">\<issuerChannelBehaviors></span><span class="sxs-lookup"><span data-stu-id="3c978-127">\<issuerChannelBehaviors></span></span>](issuerchannelbehaviors-element.md)|<span data-ttu-id="3c978-128">Enthält eine Auflistung von Windows Communication Foundation (WCF)-Client Endpunkt Verhalten, die bei der Kommunikation mit den angegebenen diensttokendiensten verwendet werden sollen.</span><span class="sxs-lookup"><span data-stu-id="3c978-128">Contains a collection of Windows Communication Foundation (WCF) client endpoint behaviors to be used when communicating with the specified Service Token Services.</span></span>|

## <a name="remarks"></a><span data-ttu-id="3c978-129">Hinweise</span><span class="sxs-lookup"><span data-stu-id="3c978-129">Remarks</span></span>

<span data-ttu-id="3c978-130">`issuerAddress` enthält den URI des Sicherheitstokendiensts, mit dem der Client kommunizieren möchte.</span><span class="sxs-lookup"><span data-stu-id="3c978-130">`issuerAddress` contains the URI of the Security Token Service that the client wants to communicate with.</span></span> <span data-ttu-id="3c978-131">`behaviorConfiguration`verweist auf ein Endpunkt Verhalten, das die Anwendung in den von Windows Communication Foundation (WCF) erstellten Kanälen verwendet, um die ausgestellten Token aus den Sicherheitstokendiensten zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="3c978-131">`behaviorConfiguration` points to an endpoint behavior that the application uses in the channels created by Windows Communication Foundation (WCF) to get the issued tokens from the Security Token Services.</span></span>

## <a name="see-also"></a><span data-ttu-id="3c978-132">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="3c978-132">See also</span></span>

- <xref:System.ServiceModel.Configuration.IssuedTokenClientElement.IssuerChannelBehaviors%2A>
- <xref:System.ServiceModel.Configuration.IssuedTokenClientBehaviorsElement>
- <xref:System.ServiceModel.Configuration.IssuedTokenClientBehaviorsElementCollection>
- <xref:System.ServiceModel.Security.IssuedTokenClientCredential.IssuerChannelBehaviors%2A>
- [<span data-ttu-id="3c978-133">Dienstidentität und Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="3c978-133">Service Identity and Authentication</span></span>](../../../wcf/feature-details/service-identity-and-authentication.md)
- [<span data-ttu-id="3c978-134">Sicherheitsverhalten</span><span class="sxs-lookup"><span data-stu-id="3c978-134">Security Behaviors</span></span>](../../../wcf/feature-details/security-behaviors-in-wcf.md)
- [<span data-ttu-id="3c978-135">Verbund und ausgestellte Token</span><span class="sxs-lookup"><span data-stu-id="3c978-135">Federation and Issued Tokens</span></span>](../../../wcf/feature-details/federation-and-issued-tokens.md)
- [<span data-ttu-id="3c978-136">Sichern von Diensten und Clients</span><span class="sxs-lookup"><span data-stu-id="3c978-136">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="3c978-137">Sichern von Clients</span><span class="sxs-lookup"><span data-stu-id="3c978-137">Securing Clients</span></span>](../../../wcf/securing-clients.md)
- [<span data-ttu-id="3c978-138">Vorgehensweise: Erstellen eines Verbund Clients</span><span class="sxs-lookup"><span data-stu-id="3c978-138">How to: Create a Federated Client</span></span>](../../../wcf/feature-details/how-to-create-a-federated-client.md)
- [<span data-ttu-id="3c978-139">Vorgehensweise: Konfigurieren eines lokalen Ausstellers</span><span class="sxs-lookup"><span data-stu-id="3c978-139">How to: Configure a Local Issuer</span></span>](../../../wcf/feature-details/how-to-configure-a-local-issuer.md)
- [<span data-ttu-id="3c978-140">Verbund und ausgestellte Token</span><span class="sxs-lookup"><span data-stu-id="3c978-140">Federation and Issued Tokens</span></span>](../../../wcf/feature-details/federation-and-issued-tokens.md)
- [<span data-ttu-id="3c978-141">\<issuerChannelBehaviors></span><span class="sxs-lookup"><span data-stu-id="3c978-141">\<issuerChannelBehaviors></span></span>](issuerchannelbehaviors-element.md)
