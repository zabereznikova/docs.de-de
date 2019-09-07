---
title: <add> von <issuerChannelBehaviors>
ms.date: 03/30/2017
ms.assetid: 50710506-e28f-45dd-ab7e-bff6f44173db
ms.openlocfilehash: cf7ac2691ad1c641352a8047373ced538b19e983
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/06/2019
ms.locfileid: "70398336"
---
# <a name="add-of-issuerchannelbehaviors"></a><span data-ttu-id="d2be8-102">\<> von \<issuerchannelverhaltensweisen hinzufügen ></span><span class="sxs-lookup"><span data-stu-id="d2be8-102">\<add> of \<issuerChannelBehaviors></span></span>

<span data-ttu-id="d2be8-103">Fügt ein zu verwendendes Endpunktverhalten bei der Kommunikation mit einem STS hinzu.</span><span class="sxs-lookup"><span data-stu-id="d2be8-103">Adds an endpoint behavior to be used when communicating with an STS.</span></span>

> [!NOTE]
> <span data-ttu-id="d2be8-104">Wenn ein Endpunkt Verhalten ein [ \<Clientanmelde->](clientcredentials.md) Element enthält, wird eine Ausnahme ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="d2be8-104">If any endpoint behavior contains a [\<clientCredentials>](clientcredentials.md) element, an exception will be thrown.</span></span>

<span data-ttu-id="d2be8-105">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="d2be8-105">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="d2be8-106">&nbsp;&nbsp;[ **\<System. Service Model->** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="d2be8-106">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="d2be8-107">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Verhaltens >** ](behaviors.md)</span><span class="sxs-lookup"><span data-stu-id="d2be8-107">&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)</span></span>\
<span data-ttu-id="d2be8-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<endpointverhaltens->** ](endpointbehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="d2be8-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpointBehaviors>**](endpointbehaviors.md)</span></span>\
<span data-ttu-id="d2be8-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Verhaltens >** ](behavior-of-endpointbehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="d2be8-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-endpointbehaviors.md)</span></span>\
<span data-ttu-id="d2be8-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Client Anmelde Informationen >** ](clientcredentials.md)</span><span class="sxs-lookup"><span data-stu-id="d2be8-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<clientCredentials>**](clientcredentials.md)</span></span>\
<span data-ttu-id="d2be8-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<IssuedToken->** ](issuedtoken.md)</span><span class="sxs-lookup"><span data-stu-id="d2be8-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<issuedToken>**](issuedtoken.md)</span></span>\
<span data-ttu-id="d2be8-112">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<issuerchannelverhaltens>** ](issuerchannelbehaviors-element.md)</span><span class="sxs-lookup"><span data-stu-id="d2be8-112">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<issuerChannelBehaviors>**](issuerchannelbehaviors-element.md)</span></span>\
<span data-ttu-id="d2be8-113">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<> Hinzufügen**</span><span class="sxs-lookup"><span data-stu-id="d2be8-113">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**</span></span>  

## <a name="syntax"></a><span data-ttu-id="d2be8-114">Syntax</span><span class="sxs-lookup"><span data-stu-id="d2be8-114">Syntax</span></span>

```xml
<add issuerAddress="string"
     behaviorConfiguration="string" />
```

## <a name="attributes-and-elements"></a><span data-ttu-id="d2be8-115">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="d2be8-115">Attributes and Elements</span></span>

<span data-ttu-id="d2be8-116">In den folgenden Abschnitten werden Attribute, untergeordnete Elemente sowie übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="d2be8-116">The following sections describe attributes, child elements, and parent elements</span></span>

### <a name="attributes"></a><span data-ttu-id="d2be8-117">Attribute</span><span class="sxs-lookup"><span data-stu-id="d2be8-117">Attributes</span></span>

|<span data-ttu-id="d2be8-118">Attribut</span><span class="sxs-lookup"><span data-stu-id="d2be8-118">Attribute</span></span>|<span data-ttu-id="d2be8-119">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="d2be8-119">Description</span></span>|
|---------------|-----------------|
|<span data-ttu-id="d2be8-120">issuerAddress</span><span class="sxs-lookup"><span data-stu-id="d2be8-120">issuerAddress</span></span>|<span data-ttu-id="d2be8-121">Der URI des Sicherheitstokenausstellers, mit dem kommuniziert wird.</span><span class="sxs-lookup"><span data-stu-id="d2be8-121">The URI of the security token issuer to communicate with.</span></span>|
|<span data-ttu-id="d2be8-122">behaviorConfiguration</span><span class="sxs-lookup"><span data-stu-id="d2be8-122">behaviorConfiguration</span></span>|<span data-ttu-id="d2be8-123">Der Name eines in derselben Konfigurationsdatei definierten Endpunktverhaltens.</span><span class="sxs-lookup"><span data-stu-id="d2be8-123">The name of an endpoint behavior defined in the same configuration file.</span></span>|

### <a name="child-elements"></a><span data-ttu-id="d2be8-124">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="d2be8-124">Child Elements</span></span>

<span data-ttu-id="d2be8-125">Keine</span><span class="sxs-lookup"><span data-stu-id="d2be8-125">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="d2be8-126">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="d2be8-126">Parent Elements</span></span>

|<span data-ttu-id="d2be8-127">Element</span><span class="sxs-lookup"><span data-stu-id="d2be8-127">Element</span></span>|<span data-ttu-id="d2be8-128">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="d2be8-128">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="d2be8-129">\<issuerChannelBehaviors></span><span class="sxs-lookup"><span data-stu-id="d2be8-129">\<issuerChannelBehaviors></span></span>](issuerchannelbehaviors-element.md)|<span data-ttu-id="d2be8-130">Enthält eine Auflistung von Windows Communication Foundation (WCF)-Client Endpunkt Verhalten, die bei der Kommunikation mit den angegebenen diensttokendiensten verwendet werden sollen.</span><span class="sxs-lookup"><span data-stu-id="d2be8-130">Contains a collection of Windows Communication Foundation (WCF) client endpoint behaviors to be used when communicating with the specified Service Token Services.</span></span>|

## <a name="remarks"></a><span data-ttu-id="d2be8-131">Hinweise</span><span class="sxs-lookup"><span data-stu-id="d2be8-131">Remarks</span></span>

<span data-ttu-id="d2be8-132">`issuerAddress` enthält den URI des Sicherheitstokendiensts, mit dem der Client kommunizieren möchte.</span><span class="sxs-lookup"><span data-stu-id="d2be8-132">`issuerAddress` contains the URI of the Security Token Service that the client wants to communicate with.</span></span> <span data-ttu-id="d2be8-133">`behaviorConfiguration`verweist auf ein Endpunkt Verhalten, das die Anwendung in den von Windows Communication Foundation (WCF) erstellten Kanälen verwendet, um die ausgestellten Token aus den Sicherheitstokendiensten zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="d2be8-133">`behaviorConfiguration` points to an endpoint behavior that the application uses in the channels created by Windows Communication Foundation (WCF) to get the issued tokens from the Security Token Services.</span></span>

## <a name="see-also"></a><span data-ttu-id="d2be8-134">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d2be8-134">See also</span></span>

- <xref:System.ServiceModel.Configuration.IssuedTokenClientElement.IssuerChannelBehaviors%2A>
- <xref:System.ServiceModel.Configuration.IssuedTokenClientBehaviorsElement>
- <xref:System.ServiceModel.Configuration.IssuedTokenClientBehaviorsElementCollection>
- <xref:System.ServiceModel.Security.IssuedTokenClientCredential.IssuerChannelBehaviors%2A>
- [<span data-ttu-id="d2be8-135">Dienstidentität und Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="d2be8-135">Service Identity and Authentication</span></span>](../../../wcf/feature-details/service-identity-and-authentication.md)
- [<span data-ttu-id="d2be8-136">Sicherheitsverhalten</span><span class="sxs-lookup"><span data-stu-id="d2be8-136">Security Behaviors</span></span>](../../../wcf/feature-details/security-behaviors-in-wcf.md)
- [<span data-ttu-id="d2be8-137">Verbund und ausgestellte Token</span><span class="sxs-lookup"><span data-stu-id="d2be8-137">Federation and Issued Tokens</span></span>](../../../wcf/feature-details/federation-and-issued-tokens.md)
- [<span data-ttu-id="d2be8-138">Sichern von Diensten und Clients</span><span class="sxs-lookup"><span data-stu-id="d2be8-138">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="d2be8-139">Sichern von Clients</span><span class="sxs-lookup"><span data-stu-id="d2be8-139">Securing Clients</span></span>](../../../wcf/securing-clients.md)
- [<span data-ttu-id="d2be8-140">Vorgehensweise: Erstellen eines Verbund Clients</span><span class="sxs-lookup"><span data-stu-id="d2be8-140">How to: Create a Federated Client</span></span>](../../../wcf/feature-details/how-to-create-a-federated-client.md)
- [<span data-ttu-id="d2be8-141">Vorgehensweise: Konfigurieren eines lokalen Ausstellers</span><span class="sxs-lookup"><span data-stu-id="d2be8-141">How to: Configure a Local Issuer</span></span>](../../../wcf/feature-details/how-to-configure-a-local-issuer.md)
- [<span data-ttu-id="d2be8-142">Verbund und ausgestellte Token</span><span class="sxs-lookup"><span data-stu-id="d2be8-142">Federation and Issued Tokens</span></span>](../../../wcf/feature-details/federation-and-issued-tokens.md)
- [<span data-ttu-id="d2be8-143">\<issuerChannelBehaviors></span><span class="sxs-lookup"><span data-stu-id="d2be8-143">\<issuerChannelBehaviors></span></span>](issuerchannelbehaviors-element.md)
