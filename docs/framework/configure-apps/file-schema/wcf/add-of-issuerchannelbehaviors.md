---
title: <add> von <issuerChannelBehaviors>
ms.date: 03/30/2017
ms.assetid: 50710506-e28f-45dd-ab7e-bff6f44173db
ms.openlocfilehash: cf7ac2691ad1c641352a8047373ced538b19e983
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/06/2020
ms.locfileid: "70398336"
---
# <a name="add-of-issuerchannelbehaviors"></a><span data-ttu-id="ecca2-102">\<add> von \<issuerChannelBehaviors></span><span class="sxs-lookup"><span data-stu-id="ecca2-102">\<add> of \<issuerChannelBehaviors></span></span>

<span data-ttu-id="ecca2-103">Fügt ein zu verwendendes Endpunktverhalten bei der Kommunikation mit einem STS hinzu.</span><span class="sxs-lookup"><span data-stu-id="ecca2-103">Adds an endpoint behavior to be used when communicating with an STS.</span></span>

> [!NOTE]
> <span data-ttu-id="ecca2-104">Wenn ein Endpunkt Verhalten ein- [\<clientCredentials>](clientcredentials.md) Element enthält, wird eine Ausnahme ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="ecca2-104">If any endpoint behavior contains a [\<clientCredentials>](clientcredentials.md) element, an exception will be thrown.</span></span>

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpointBehaviors>**](endpointbehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-endpointbehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<clientCredentials>**](clientcredentials.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<issuedToken>**](issuedtoken.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<issuerChannelBehaviors>**](issuerchannelbehaviors-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**  

## <a name="syntax"></a><span data-ttu-id="ecca2-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="ecca2-105">Syntax</span></span>

```xml
<add issuerAddress="string"
     behaviorConfiguration="string" />
```

## <a name="attributes-and-elements"></a><span data-ttu-id="ecca2-106">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="ecca2-106">Attributes and Elements</span></span>

<span data-ttu-id="ecca2-107">In den folgenden Abschnitten werden Attribute, untergeordnete Elemente sowie übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="ecca2-107">The following sections describe attributes, child elements, and parent elements</span></span>

### <a name="attributes"></a><span data-ttu-id="ecca2-108">Attribute</span><span class="sxs-lookup"><span data-stu-id="ecca2-108">Attributes</span></span>

|<span data-ttu-id="ecca2-109">attribute</span><span class="sxs-lookup"><span data-stu-id="ecca2-109">Attribute</span></span>|<span data-ttu-id="ecca2-110">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="ecca2-110">Description</span></span>|
|---------------|-----------------|
|<span data-ttu-id="ecca2-111">issuerAddress</span><span class="sxs-lookup"><span data-stu-id="ecca2-111">issuerAddress</span></span>|<span data-ttu-id="ecca2-112">Der URI des Sicherheitstokenausstellers, mit dem kommuniziert wird.</span><span class="sxs-lookup"><span data-stu-id="ecca2-112">The URI of the security token issuer to communicate with.</span></span>|
|<span data-ttu-id="ecca2-113">behaviorConfiguration</span><span class="sxs-lookup"><span data-stu-id="ecca2-113">behaviorConfiguration</span></span>|<span data-ttu-id="ecca2-114">Der Name eines in derselben Konfigurationsdatei definierten Endpunktverhaltens.</span><span class="sxs-lookup"><span data-stu-id="ecca2-114">The name of an endpoint behavior defined in the same configuration file.</span></span>|

### <a name="child-elements"></a><span data-ttu-id="ecca2-115">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="ecca2-115">Child Elements</span></span>

<span data-ttu-id="ecca2-116">Keine</span><span class="sxs-lookup"><span data-stu-id="ecca2-116">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="ecca2-117">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="ecca2-117">Parent Elements</span></span>

|<span data-ttu-id="ecca2-118">Element</span><span class="sxs-lookup"><span data-stu-id="ecca2-118">Element</span></span>|<span data-ttu-id="ecca2-119">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="ecca2-119">Description</span></span>|
|-------------|-----------------|
|[\<issuerChannelBehaviors>](issuerchannelbehaviors-element.md)|<span data-ttu-id="ecca2-120">Enthält eine Auflistung von Windows Communication Foundation (WCF)-Client Endpunkt Verhalten, die bei der Kommunikation mit den angegebenen diensttokendiensten verwendet werden sollen.</span><span class="sxs-lookup"><span data-stu-id="ecca2-120">Contains a collection of Windows Communication Foundation (WCF) client endpoint behaviors to be used when communicating with the specified Service Token Services.</span></span>|

## <a name="remarks"></a><span data-ttu-id="ecca2-121">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="ecca2-121">Remarks</span></span>

<span data-ttu-id="ecca2-122">`issuerAddress` enthält den URI des Sicherheitstokendiensts, mit dem der Client kommunizieren möchte.</span><span class="sxs-lookup"><span data-stu-id="ecca2-122">`issuerAddress` contains the URI of the Security Token Service that the client wants to communicate with.</span></span> <span data-ttu-id="ecca2-123">`behaviorConfiguration`verweist auf ein Endpunkt Verhalten, das die Anwendung in den von Windows Communication Foundation (WCF) erstellten Kanälen verwendet, um die ausgestellten Token aus den Sicherheitstokendiensten zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="ecca2-123">`behaviorConfiguration` points to an endpoint behavior that the application uses in the channels created by Windows Communication Foundation (WCF) to get the issued tokens from the Security Token Services.</span></span>

## <a name="see-also"></a><span data-ttu-id="ecca2-124">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="ecca2-124">See also</span></span>

- <xref:System.ServiceModel.Configuration.IssuedTokenClientElement.IssuerChannelBehaviors%2A>
- <xref:System.ServiceModel.Configuration.IssuedTokenClientBehaviorsElement>
- <xref:System.ServiceModel.Configuration.IssuedTokenClientBehaviorsElementCollection>
- <xref:System.ServiceModel.Security.IssuedTokenClientCredential.IssuerChannelBehaviors%2A>
- [<span data-ttu-id="ecca2-125">Dienstidentität und Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="ecca2-125">Service Identity and Authentication</span></span>](../../../wcf/feature-details/service-identity-and-authentication.md)
- [<span data-ttu-id="ecca2-126">Sicherheitsverhalten</span><span class="sxs-lookup"><span data-stu-id="ecca2-126">Security Behaviors</span></span>](../../../wcf/feature-details/security-behaviors-in-wcf.md)
- [<span data-ttu-id="ecca2-127">Verbund und ausgestellte Token</span><span class="sxs-lookup"><span data-stu-id="ecca2-127">Federation and Issued Tokens</span></span>](../../../wcf/feature-details/federation-and-issued-tokens.md)
- [<span data-ttu-id="ecca2-128">Sichern von Diensten und Clients</span><span class="sxs-lookup"><span data-stu-id="ecca2-128">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="ecca2-129">Sichern von Clients</span><span class="sxs-lookup"><span data-stu-id="ecca2-129">Securing Clients</span></span>](../../../wcf/securing-clients.md)
- [<span data-ttu-id="ecca2-130">Vorgehensweise: Erstellen eines Verbundclients</span><span class="sxs-lookup"><span data-stu-id="ecca2-130">How to: Create a Federated Client</span></span>](../../../wcf/feature-details/how-to-create-a-federated-client.md)
- [<span data-ttu-id="ecca2-131">Vorgehensweise: Konfigurieren eines lokalen Ausstellers</span><span class="sxs-lookup"><span data-stu-id="ecca2-131">How to: Configure a Local Issuer</span></span>](../../../wcf/feature-details/how-to-configure-a-local-issuer.md)
- [<span data-ttu-id="ecca2-132">Verbund und ausgestellte Token</span><span class="sxs-lookup"><span data-stu-id="ecca2-132">Federation and Issued Tokens</span></span>](../../../wcf/feature-details/federation-and-issued-tokens.md)
- [\<issuerChannelBehaviors>](issuerchannelbehaviors-element.md)
