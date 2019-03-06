---
title: <issuerChannelBehaviors>-Element
ms.date: 03/30/2017
ms.assetid: f7378673-8e9b-45b2-98d1-cf5dccdd8c40
ms.openlocfilehash: 3386a287d577681b67bd3ad54a75b0276e29da1f
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/05/2019
ms.locfileid: "57357247"
---
# <a name="issuerchannelbehaviors-element"></a><span data-ttu-id="8d8a3-102">\<IssuerChannelBehaviors >-Element</span><span class="sxs-lookup"><span data-stu-id="8d8a3-102">\<issuerChannelBehaviors> Element</span></span>

<span data-ttu-id="8d8a3-103">Enthält eine Auflistung von Windows Communication Foundation (WCF) Client-Endpunktverhalten (definiert in der Konfiguration), bei der Kommunikation mit den angegebenen Sicherheitstokendiensten verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="8d8a3-103">Contains a collection of Windows Communication Foundation (WCF) client endpoint behaviors (defined in the configuration) to be used when communicating with the specified Service Token Services.</span></span> <span data-ttu-id="8d8a3-104">Die definierten Verhalten nicht enthalten [ \<ClientCredentials >](../../../../../docs/framework/configure-apps/file-schema/wcf/clientcredentials.md) Elemente.</span><span class="sxs-lookup"><span data-stu-id="8d8a3-104">The defined behaviors cannot include any [\<clientCredentials>](../../../../../docs/framework/configure-apps/file-schema/wcf/clientcredentials.md) elements.</span></span>

<span data-ttu-id="8d8a3-105">\<system.ServiceModel>\\</span><span class="sxs-lookup"><span data-stu-id="8d8a3-105">\<system.ServiceModel>\\</span></span>
<span data-ttu-id="8d8a3-106">\<behaviors>\\</span><span class="sxs-lookup"><span data-stu-id="8d8a3-106">\<behaviors>\\</span></span>
<span data-ttu-id="8d8a3-107">EndpointBehaviors section\\</span><span class="sxs-lookup"><span data-stu-id="8d8a3-107">endpointBehaviors section\\</span></span>
<span data-ttu-id="8d8a3-108">\<behavior>\\</span><span class="sxs-lookup"><span data-stu-id="8d8a3-108">\<behavior>\\</span></span>
<span data-ttu-id="8d8a3-109">\<clientCredentials>\\</span><span class="sxs-lookup"><span data-stu-id="8d8a3-109">\<clientCredentials>\\</span></span>
<span data-ttu-id="8d8a3-110">\<issuedToken>\\</span><span class="sxs-lookup"><span data-stu-id="8d8a3-110">\<issuedToken>\\</span></span>
<span data-ttu-id="8d8a3-111">\<issuerChannelBehaviors></span><span class="sxs-lookup"><span data-stu-id="8d8a3-111">\<issuerChannelBehaviors></span></span>

## <a name="syntax"></a><span data-ttu-id="8d8a3-112">Syntax</span><span class="sxs-lookup"><span data-stu-id="8d8a3-112">Syntax</span></span>

```xml
<issuerChannelBehaviors>
  <add behaviorConfiguration="string"
       issuerAddress="string" />
</issuerChannelBehaviors>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="8d8a3-113">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="8d8a3-113">Attributes and Elements</span></span>

<span data-ttu-id="8d8a3-114">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="8d8a3-114">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="8d8a3-115">Attribute</span><span class="sxs-lookup"><span data-stu-id="8d8a3-115">Attributes</span></span>

<span data-ttu-id="8d8a3-116">Keine</span><span class="sxs-lookup"><span data-stu-id="8d8a3-116">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="8d8a3-117">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="8d8a3-117">Child Elements</span></span>

|<span data-ttu-id="8d8a3-118">Element</span><span class="sxs-lookup"><span data-stu-id="8d8a3-118">Element</span></span>|<span data-ttu-id="8d8a3-119">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="8d8a3-119">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="8d8a3-120">\<add></span><span class="sxs-lookup"><span data-stu-id="8d8a3-120">\<add></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-issuerchannelbehaviors.md)|<span data-ttu-id="8d8a3-121">Fügt der Auflistung ein Verhalten hinzu.</span><span class="sxs-lookup"><span data-stu-id="8d8a3-121">Adds a behavior to the collection.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="8d8a3-122">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="8d8a3-122">Parent Elements</span></span>

|<span data-ttu-id="8d8a3-123">Element</span><span class="sxs-lookup"><span data-stu-id="8d8a3-123">Element</span></span>|<span data-ttu-id="8d8a3-124">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="8d8a3-124">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="8d8a3-125">\<issuedToken></span><span class="sxs-lookup"><span data-stu-id="8d8a3-125">\<issuedToken></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/issuedtoken.md)|<span data-ttu-id="8d8a3-126">Gibt ein benutzerdefiniertes Token an, das zum Authentifizieren eines Clients bei einem Dienst verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="8d8a3-126">Specifies a custom token used to authenticate a client to a service.</span></span>|

## <a name="remarks"></a><span data-ttu-id="8d8a3-127">Hinweise</span><span class="sxs-lookup"><span data-stu-id="8d8a3-127">Remarks</span></span>

<span data-ttu-id="8d8a3-128">Verwenden Sie dieses Element, wenn ein Verhalten (im Gegensatz zu Verhalten, die `<clientCredentials>`-Elemente umfassen) für die Kommunikation mit einem Dienst verwendet werden muss.</span><span class="sxs-lookup"><span data-stu-id="8d8a3-128">Use this element when any behaviors (other than behaviors that include `<clientCredentials>` elements) must be used to communicate with a service.</span></span> <span data-ttu-id="8d8a3-129">Z. B. wenn ein [ \<DataContractSerializer >](../../../../../docs/framework/configure-apps/file-schema/wcf/datacontractserializer-element.md) -verhaltenselement eingeschlossen werden muss.</span><span class="sxs-lookup"><span data-stu-id="8d8a3-129">For example, if a [\<dataContractSerializer>](../../../../../docs/framework/configure-apps/file-schema/wcf/datacontractserializer-element.md) behavior element must be included.</span></span>

## <a name="see-also"></a><span data-ttu-id="8d8a3-130">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="8d8a3-130">See also</span></span>

- <xref:System.ServiceModel.Configuration.IssuedTokenClientElement.IssuerChannelBehaviors%2A>
- <xref:System.ServiceModel.Configuration.IssuedTokenClientBehaviorsElement>
- <xref:System.ServiceModel.Configuration.IssuedTokenClientBehaviorsElementCollection>
- <xref:System.ServiceModel.Security.IssuedTokenClientCredential.IssuerChannelBehaviors%2A>
- [<span data-ttu-id="8d8a3-131">Dienstidentität und Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="8d8a3-131">Service Identity and Authentication</span></span>](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md)
- [<span data-ttu-id="8d8a3-132">Sicherheitsverhalten</span><span class="sxs-lookup"><span data-stu-id="8d8a3-132">Security Behaviors</span></span>](../../../../../docs/framework/wcf/feature-details/security-behaviors-in-wcf.md)
- [<span data-ttu-id="8d8a3-133">Verbund und ausgestellte Token</span><span class="sxs-lookup"><span data-stu-id="8d8a3-133">Federation and Issued Tokens</span></span>](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)
- [<span data-ttu-id="8d8a3-134">Sichern von Diensten und Clients</span><span class="sxs-lookup"><span data-stu-id="8d8a3-134">Securing Services and Clients</span></span>](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="8d8a3-135">Sichern von Clients</span><span class="sxs-lookup"><span data-stu-id="8d8a3-135">Securing Clients</span></span>](../../../../../docs/framework/wcf/securing-clients.md)
- [<span data-ttu-id="8d8a3-136">Vorgehensweise: Erstellen eines Verbundclients</span><span class="sxs-lookup"><span data-stu-id="8d8a3-136">How to: Create a Federated Client</span></span>](../../../../../docs/framework/wcf/feature-details/how-to-create-a-federated-client.md)
- [<span data-ttu-id="8d8a3-137">Vorgehensweise: Konfigurieren eines lokalen Ausstellers</span><span class="sxs-lookup"><span data-stu-id="8d8a3-137">How to: Configure a Local Issuer</span></span>](../../../../../docs/framework/wcf/feature-details/how-to-configure-a-local-issuer.md)
- [<span data-ttu-id="8d8a3-138">Verbund und ausgestellte Token</span><span class="sxs-lookup"><span data-stu-id="8d8a3-138">Federation and Issued Tokens</span></span>](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)
