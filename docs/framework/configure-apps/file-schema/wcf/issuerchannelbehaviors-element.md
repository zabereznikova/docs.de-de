---
title: <issuerChannelBehaviors>-Element
ms.date: 03/30/2017
ms.assetid: f7378673-8e9b-45b2-98d1-cf5dccdd8c40
ms.openlocfilehash: e0e41b4f6d66cd4455c43dda7c77798553f2b58f
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69929930"
---
# <a name="issuerchannelbehaviors-element"></a><span data-ttu-id="edcbf-102">\<issuerchannelverhaltens>-Element</span><span class="sxs-lookup"><span data-stu-id="edcbf-102">\<issuerChannelBehaviors> Element</span></span>

<span data-ttu-id="edcbf-103">Enthält eine Auflistung von Windows Communication Foundation (WCF)-clientend Punkt Verhaltensweisen (in der Konfiguration definiert), die bei der Kommunikation mit den angegebenen diensttokendiensten verwendet werden sollen.</span><span class="sxs-lookup"><span data-stu-id="edcbf-103">Contains a collection of Windows Communication Foundation (WCF) client endpoint behaviors (defined in the configuration) to be used when communicating with the specified Service Token Services.</span></span> <span data-ttu-id="edcbf-104">Das definierte Verhalten kann keine [ \<Clientanmelde->](clientcredentials.md) Elemente enthalten.</span><span class="sxs-lookup"><span data-stu-id="edcbf-104">The defined behaviors cannot include any [\<clientCredentials>](clientcredentials.md) elements.</span></span>

```xml
<system.ServiceModel>
  <behaviors>
    <endpointBehaviors>
      <behavior>
        <clientCredentials>
          <issuedToken>
            <issuerChannelBehaviors>
```

## <a name="syntax"></a><span data-ttu-id="edcbf-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="edcbf-105">Syntax</span></span>

```xml
<issuerChannelBehaviors>
  <add behaviorConfiguration="string"
       issuerAddress="string" />
</issuerChannelBehaviors>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="edcbf-106">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="edcbf-106">Attributes and Elements</span></span>

<span data-ttu-id="edcbf-107">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="edcbf-107">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="edcbf-108">Attribute</span><span class="sxs-lookup"><span data-stu-id="edcbf-108">Attributes</span></span>

<span data-ttu-id="edcbf-109">Keine</span><span class="sxs-lookup"><span data-stu-id="edcbf-109">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="edcbf-110">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="edcbf-110">Child Elements</span></span>

|<span data-ttu-id="edcbf-111">Element</span><span class="sxs-lookup"><span data-stu-id="edcbf-111">Element</span></span>|<span data-ttu-id="edcbf-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="edcbf-112">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="edcbf-113">\<add></span><span class="sxs-lookup"><span data-stu-id="edcbf-113">\<add></span></span>](add-of-issuerchannelbehaviors.md)|<span data-ttu-id="edcbf-114">Fügt der Auflistung ein Verhalten hinzu.</span><span class="sxs-lookup"><span data-stu-id="edcbf-114">Adds a behavior to the collection.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="edcbf-115">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="edcbf-115">Parent Elements</span></span>

|<span data-ttu-id="edcbf-116">Element</span><span class="sxs-lookup"><span data-stu-id="edcbf-116">Element</span></span>|<span data-ttu-id="edcbf-117">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="edcbf-117">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="edcbf-118">\<issuedToken></span><span class="sxs-lookup"><span data-stu-id="edcbf-118">\<issuedToken></span></span>](issuedtoken.md)|<span data-ttu-id="edcbf-119">Gibt ein benutzerdefiniertes Token an, das zum Authentifizieren eines Clients bei einem Dienst verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="edcbf-119">Specifies a custom token used to authenticate a client to a service.</span></span>|

## <a name="remarks"></a><span data-ttu-id="edcbf-120">Hinweise</span><span class="sxs-lookup"><span data-stu-id="edcbf-120">Remarks</span></span>

<span data-ttu-id="edcbf-121">Verwenden Sie dieses Element, wenn ein Verhalten (im Gegensatz zu Verhalten, die `<clientCredentials>`-Elemente umfassen) für die Kommunikation mit einem Dienst verwendet werden muss.</span><span class="sxs-lookup"><span data-stu-id="edcbf-121">Use this element when any behaviors (other than behaviors that include `<clientCredentials>` elements) must be used to communicate with a service.</span></span> <span data-ttu-id="edcbf-122">Beispielsweise, wenn ein [ \<DataContractSerializer->](datacontractserializer-element.md) Behavior-Element eingeschlossen werden muss.</span><span class="sxs-lookup"><span data-stu-id="edcbf-122">For example, if a [\<dataContractSerializer>](datacontractserializer-element.md) behavior element must be included.</span></span>

## <a name="see-also"></a><span data-ttu-id="edcbf-123">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="edcbf-123">See also</span></span>

- <xref:System.ServiceModel.Configuration.IssuedTokenClientElement.IssuerChannelBehaviors%2A>
- <xref:System.ServiceModel.Configuration.IssuedTokenClientBehaviorsElement>
- <xref:System.ServiceModel.Configuration.IssuedTokenClientBehaviorsElementCollection>
- <xref:System.ServiceModel.Security.IssuedTokenClientCredential.IssuerChannelBehaviors%2A>
- [<span data-ttu-id="edcbf-124">Dienstidentität und Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="edcbf-124">Service Identity and Authentication</span></span>](../../../wcf/feature-details/service-identity-and-authentication.md)
- [<span data-ttu-id="edcbf-125">Sicherheitsverhalten</span><span class="sxs-lookup"><span data-stu-id="edcbf-125">Security Behaviors</span></span>](../../../wcf/feature-details/security-behaviors-in-wcf.md)
- [<span data-ttu-id="edcbf-126">Verbund und ausgestellte Token</span><span class="sxs-lookup"><span data-stu-id="edcbf-126">Federation and Issued Tokens</span></span>](../../../wcf/feature-details/federation-and-issued-tokens.md)
- [<span data-ttu-id="edcbf-127">Sichern von Diensten und Clients</span><span class="sxs-lookup"><span data-stu-id="edcbf-127">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="edcbf-128">Sichern von Clients</span><span class="sxs-lookup"><span data-stu-id="edcbf-128">Securing Clients</span></span>](../../../wcf/securing-clients.md)
- [<span data-ttu-id="edcbf-129">Vorgehensweise: Erstellen eines Verbund Clients</span><span class="sxs-lookup"><span data-stu-id="edcbf-129">How to: Create a Federated Client</span></span>](../../../wcf/feature-details/how-to-create-a-federated-client.md)
- [<span data-ttu-id="edcbf-130">Vorgehensweise: Konfigurieren eines lokalen Ausstellers</span><span class="sxs-lookup"><span data-stu-id="edcbf-130">How to: Configure a Local Issuer</span></span>](../../../wcf/feature-details/how-to-configure-a-local-issuer.md)
- [<span data-ttu-id="edcbf-131">Verbund und ausgestellte Token</span><span class="sxs-lookup"><span data-stu-id="edcbf-131">Federation and Issued Tokens</span></span>](../../../wcf/feature-details/federation-and-issued-tokens.md)
