---
title: <issuerChannelBehaviors>-Element
ms.date: 03/30/2017
ms.assetid: f7378673-8e9b-45b2-98d1-cf5dccdd8c40
ms.openlocfilehash: 7cbd50daa82b0ca937a1bba93786545898b03c8b
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61760726"
---
# <a name="issuerchannelbehaviors-element"></a><span data-ttu-id="de240-102">\<IssuerChannelBehaviors >-Element</span><span class="sxs-lookup"><span data-stu-id="de240-102">\<issuerChannelBehaviors> Element</span></span>

<span data-ttu-id="de240-103">Enthält eine Auflistung von Windows Communication Foundation (WCF) Client-Endpunktverhalten (definiert in der Konfiguration), bei der Kommunikation mit den angegebenen Sicherheitstokendiensten verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="de240-103">Contains a collection of Windows Communication Foundation (WCF) client endpoint behaviors (defined in the configuration) to be used when communicating with the specified Service Token Services.</span></span> <span data-ttu-id="de240-104">Die definierten Verhalten nicht enthalten [ \<ClientCredentials >](../../../../../docs/framework/configure-apps/file-schema/wcf/clientcredentials.md) Elemente.</span><span class="sxs-lookup"><span data-stu-id="de240-104">The defined behaviors cannot include any [\<clientCredentials>](../../../../../docs/framework/configure-apps/file-schema/wcf/clientcredentials.md) elements.</span></span>

```xml
<system.ServiceModel>
  <behaviors>
    <endpointBehaviors>
      <behavior>
        <clientCredentials>
          <issuedToken>
            <issuerChannelBehaviors>
```

## <a name="syntax"></a><span data-ttu-id="de240-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="de240-105">Syntax</span></span>

```xml
<issuerChannelBehaviors>
  <add behaviorConfiguration="string"
       issuerAddress="string" />
</issuerChannelBehaviors>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="de240-106">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="de240-106">Attributes and Elements</span></span>

<span data-ttu-id="de240-107">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="de240-107">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="de240-108">Attribute</span><span class="sxs-lookup"><span data-stu-id="de240-108">Attributes</span></span>

<span data-ttu-id="de240-109">Keine</span><span class="sxs-lookup"><span data-stu-id="de240-109">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="de240-110">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="de240-110">Child Elements</span></span>

|<span data-ttu-id="de240-111">Element</span><span class="sxs-lookup"><span data-stu-id="de240-111">Element</span></span>|<span data-ttu-id="de240-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="de240-112">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="de240-113">\<add></span><span class="sxs-lookup"><span data-stu-id="de240-113">\<add></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-issuerchannelbehaviors.md)|<span data-ttu-id="de240-114">Fügt der Auflistung ein Verhalten hinzu.</span><span class="sxs-lookup"><span data-stu-id="de240-114">Adds a behavior to the collection.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="de240-115">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="de240-115">Parent Elements</span></span>

|<span data-ttu-id="de240-116">Element</span><span class="sxs-lookup"><span data-stu-id="de240-116">Element</span></span>|<span data-ttu-id="de240-117">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="de240-117">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="de240-118">\<issuedToken></span><span class="sxs-lookup"><span data-stu-id="de240-118">\<issuedToken></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/issuedtoken.md)|<span data-ttu-id="de240-119">Gibt ein benutzerdefiniertes Token an, das zum Authentifizieren eines Clients bei einem Dienst verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="de240-119">Specifies a custom token used to authenticate a client to a service.</span></span>|

## <a name="remarks"></a><span data-ttu-id="de240-120">Hinweise</span><span class="sxs-lookup"><span data-stu-id="de240-120">Remarks</span></span>

<span data-ttu-id="de240-121">Verwenden Sie dieses Element, wenn ein Verhalten (im Gegensatz zu Verhalten, die `<clientCredentials>`-Elemente umfassen) für die Kommunikation mit einem Dienst verwendet werden muss.</span><span class="sxs-lookup"><span data-stu-id="de240-121">Use this element when any behaviors (other than behaviors that include `<clientCredentials>` elements) must be used to communicate with a service.</span></span> <span data-ttu-id="de240-122">Z. B. wenn ein [ \<DataContractSerializer >](../../../../../docs/framework/configure-apps/file-schema/wcf/datacontractserializer-element.md) -verhaltenselement eingeschlossen werden muss.</span><span class="sxs-lookup"><span data-stu-id="de240-122">For example, if a [\<dataContractSerializer>](../../../../../docs/framework/configure-apps/file-schema/wcf/datacontractserializer-element.md) behavior element must be included.</span></span>

## <a name="see-also"></a><span data-ttu-id="de240-123">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="de240-123">See also</span></span>

- <xref:System.ServiceModel.Configuration.IssuedTokenClientElement.IssuerChannelBehaviors%2A>
- <xref:System.ServiceModel.Configuration.IssuedTokenClientBehaviorsElement>
- <xref:System.ServiceModel.Configuration.IssuedTokenClientBehaviorsElementCollection>
- <xref:System.ServiceModel.Security.IssuedTokenClientCredential.IssuerChannelBehaviors%2A>
- [<span data-ttu-id="de240-124">Dienstidentität und Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="de240-124">Service Identity and Authentication</span></span>](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md)
- [<span data-ttu-id="de240-125">Sicherheitsverhalten</span><span class="sxs-lookup"><span data-stu-id="de240-125">Security Behaviors</span></span>](../../../../../docs/framework/wcf/feature-details/security-behaviors-in-wcf.md)
- [<span data-ttu-id="de240-126">Verbund und ausgestellte Token</span><span class="sxs-lookup"><span data-stu-id="de240-126">Federation and Issued Tokens</span></span>](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)
- [<span data-ttu-id="de240-127">Sichern von Diensten und Clients</span><span class="sxs-lookup"><span data-stu-id="de240-127">Securing Services and Clients</span></span>](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="de240-128">Sichern von Clients</span><span class="sxs-lookup"><span data-stu-id="de240-128">Securing Clients</span></span>](../../../../../docs/framework/wcf/securing-clients.md)
- [<span data-ttu-id="de240-129">Vorgehensweise: Erstellen eines Verbundclients</span><span class="sxs-lookup"><span data-stu-id="de240-129">How to: Create a Federated Client</span></span>](../../../../../docs/framework/wcf/feature-details/how-to-create-a-federated-client.md)
- [<span data-ttu-id="de240-130">Vorgehensweise: Konfigurieren eines lokalen Ausstellers</span><span class="sxs-lookup"><span data-stu-id="de240-130">How to: Configure a Local Issuer</span></span>](../../../../../docs/framework/wcf/feature-details/how-to-configure-a-local-issuer.md)
- [<span data-ttu-id="de240-131">Verbund und ausgestellte Token</span><span class="sxs-lookup"><span data-stu-id="de240-131">Federation and Issued Tokens</span></span>](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)
