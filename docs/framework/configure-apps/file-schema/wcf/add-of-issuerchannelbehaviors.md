---
title: <add> von <issuerChannelBehaviors>
ms.date: 03/30/2017
ms.assetid: 50710506-e28f-45dd-ab7e-bff6f44173db
ms.openlocfilehash: 5c9937cb6302a194228461f3e2e06ecdf4d43269
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61673614"
---
# <a name="add-of-issuerchannelbehaviors"></a><span data-ttu-id="f53be-102">\<Hinzufügen > der \<IssuerChannelBehaviors ></span><span class="sxs-lookup"><span data-stu-id="f53be-102">\<add> of \<issuerChannelBehaviors></span></span>

<span data-ttu-id="f53be-103">Fügt ein zu verwendendes Endpunktverhalten bei der Kommunikation mit einem STS hinzu.</span><span class="sxs-lookup"><span data-stu-id="f53be-103">Adds an endpoint behavior to be used when communicating with an STS.</span></span>

> [!NOTE]
> <span data-ttu-id="f53be-104">Wenn ein Endpunktverhalten enthält eine [ \<ClientCredentials >](../../../../../docs/framework/configure-apps/file-schema/wcf/clientcredentials.md) -Element, eine Ausnahme ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="f53be-104">If any endpoint behavior contains a [\<clientCredentials>](../../../../../docs/framework/configure-apps/file-schema/wcf/clientcredentials.md) element, an exception will be thrown.</span></span>

<span data-ttu-id="f53be-105">\<system.ServiceModel>\\</span><span class="sxs-lookup"><span data-stu-id="f53be-105">\<system.ServiceModel>\\</span></span>
<span data-ttu-id="f53be-106">\<behaviors>\\</span><span class="sxs-lookup"><span data-stu-id="f53be-106">\<behaviors>\\</span></span>
<span data-ttu-id="f53be-107">EndpointBehaviors Abschnitt \<Verhalten > \\</span><span class="sxs-lookup"><span data-stu-id="f53be-107">endpointBehaviors section \<behavior>\\</span></span>
<span data-ttu-id="f53be-108">\<clientCredentials>\\</span><span class="sxs-lookup"><span data-stu-id="f53be-108">\<clientCredentials>\\</span></span>
<span data-ttu-id="f53be-109">\<issuedToken>\\</span><span class="sxs-lookup"><span data-stu-id="f53be-109">\<issuedToken>\\</span></span>
<span data-ttu-id="f53be-110">\<IssuerChannelBehaviors > Element\\</span><span class="sxs-lookup"><span data-stu-id="f53be-110">\<issuerChannelBehaviors> Element\\</span></span>
<span data-ttu-id="f53be-111">\<add></span><span class="sxs-lookup"><span data-stu-id="f53be-111">\<add></span></span>

## <a name="syntax"></a><span data-ttu-id="f53be-112">Syntax</span><span class="sxs-lookup"><span data-stu-id="f53be-112">Syntax</span></span>

```xml
<add issuerAddress="string"
     behaviorConfiguration="string" />
```

## <a name="attributes-and-elements"></a><span data-ttu-id="f53be-113">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="f53be-113">Attributes and Elements</span></span>

<span data-ttu-id="f53be-114">In den folgenden Abschnitten werden Attribute, untergeordnete Elemente sowie übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="f53be-114">The following sections describe attributes, child elements, and parent elements</span></span>

### <a name="attributes"></a><span data-ttu-id="f53be-115">Attribute</span><span class="sxs-lookup"><span data-stu-id="f53be-115">Attributes</span></span>

|<span data-ttu-id="f53be-116">Attribut</span><span class="sxs-lookup"><span data-stu-id="f53be-116">Attribute</span></span>|<span data-ttu-id="f53be-117">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="f53be-117">Description</span></span>|
|---------------|-----------------|
|<span data-ttu-id="f53be-118">issuerAddress</span><span class="sxs-lookup"><span data-stu-id="f53be-118">issuerAddress</span></span>|<span data-ttu-id="f53be-119">Der URI des Sicherheitstokenausstellers, mit dem kommuniziert wird.</span><span class="sxs-lookup"><span data-stu-id="f53be-119">The URI of the security token issuer to communicate with.</span></span>|
|<span data-ttu-id="f53be-120">behaviorConfiguration</span><span class="sxs-lookup"><span data-stu-id="f53be-120">behaviorConfiguration</span></span>|<span data-ttu-id="f53be-121">Der Name eines in derselben Konfigurationsdatei definierten Endpunktverhaltens.</span><span class="sxs-lookup"><span data-stu-id="f53be-121">The name of an endpoint behavior defined in the same configuration file.</span></span>|

### <a name="child-elements"></a><span data-ttu-id="f53be-122">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="f53be-122">Child Elements</span></span>

<span data-ttu-id="f53be-123">Keine</span><span class="sxs-lookup"><span data-stu-id="f53be-123">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="f53be-124">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="f53be-124">Parent Elements</span></span>

|<span data-ttu-id="f53be-125">Element</span><span class="sxs-lookup"><span data-stu-id="f53be-125">Element</span></span>|<span data-ttu-id="f53be-126">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="f53be-126">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="f53be-127">\<issuerChannelBehaviors></span><span class="sxs-lookup"><span data-stu-id="f53be-127">\<issuerChannelBehaviors></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/issuerchannelbehaviors-element.md)|<span data-ttu-id="f53be-128">Enthält eine Auflistung von Windows Communication Foundation (WCF) Client-Endpunktverhalten, die bei der Kommunikation mit den angegebenen Sicherheitstokendiensten verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="f53be-128">Contains a collection of Windows Communication Foundation (WCF) client endpoint behaviors to be used when communicating with the specified Service Token Services.</span></span>|

## <a name="remarks"></a><span data-ttu-id="f53be-129">Hinweise</span><span class="sxs-lookup"><span data-stu-id="f53be-129">Remarks</span></span>

<span data-ttu-id="f53be-130">`issuerAddress` enthält den URI des Sicherheitstokendiensts, mit dem der Client kommunizieren möchte.</span><span class="sxs-lookup"><span data-stu-id="f53be-130">`issuerAddress` contains the URI of the Security Token Service that the client wants to communicate with.</span></span> <span data-ttu-id="f53be-131">`behaviorConfiguration` verweist auf ein Endpunktverhalten, die die Anwendung in die Channels, die von Windows Communication Foundation (WCF) verwendet werden, um die ausgestellten Token aus den Sicherheitstokendiensten abzurufen.</span><span class="sxs-lookup"><span data-stu-id="f53be-131">`behaviorConfiguration` points to an endpoint behavior that the application uses in the channels created by Windows Communication Foundation (WCF) to get the issued tokens from the Security Token Services.</span></span>

## <a name="see-also"></a><span data-ttu-id="f53be-132">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f53be-132">See also</span></span>

- <xref:System.ServiceModel.Configuration.IssuedTokenClientElement.IssuerChannelBehaviors%2A>
- <xref:System.ServiceModel.Configuration.IssuedTokenClientBehaviorsElement>
- <xref:System.ServiceModel.Configuration.IssuedTokenClientBehaviorsElementCollection>
- <xref:System.ServiceModel.Security.IssuedTokenClientCredential.IssuerChannelBehaviors%2A>
- [<span data-ttu-id="f53be-133">Dienstidentität und Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="f53be-133">Service Identity and Authentication</span></span>](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md)
- [<span data-ttu-id="f53be-134">Sicherheitsverhalten</span><span class="sxs-lookup"><span data-stu-id="f53be-134">Security Behaviors</span></span>](../../../../../docs/framework/wcf/feature-details/security-behaviors-in-wcf.md)
- [<span data-ttu-id="f53be-135">Verbund und ausgestellte Token</span><span class="sxs-lookup"><span data-stu-id="f53be-135">Federation and Issued Tokens</span></span>](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)
- [<span data-ttu-id="f53be-136">Sichern von Diensten und Clients</span><span class="sxs-lookup"><span data-stu-id="f53be-136">Securing Services and Clients</span></span>](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="f53be-137">Sichern von Clients</span><span class="sxs-lookup"><span data-stu-id="f53be-137">Securing Clients</span></span>](../../../../../docs/framework/wcf/securing-clients.md)
- [<span data-ttu-id="f53be-138">Vorgehensweise: Erstellen eines Verbundclients</span><span class="sxs-lookup"><span data-stu-id="f53be-138">How to: Create a Federated Client</span></span>](../../../../../docs/framework/wcf/feature-details/how-to-create-a-federated-client.md)
- [<span data-ttu-id="f53be-139">Vorgehensweise: Konfigurieren eines lokalen Ausstellers</span><span class="sxs-lookup"><span data-stu-id="f53be-139">How to: Configure a Local Issuer</span></span>](../../../../../docs/framework/wcf/feature-details/how-to-configure-a-local-issuer.md)
- [<span data-ttu-id="f53be-140">Verbund und ausgestellte Token</span><span class="sxs-lookup"><span data-stu-id="f53be-140">Federation and Issued Tokens</span></span>](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)
- [<span data-ttu-id="f53be-141">\<issuerChannelBehaviors></span><span class="sxs-lookup"><span data-stu-id="f53be-141">\<issuerChannelBehaviors></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/issuerchannelbehaviors-element.md)
