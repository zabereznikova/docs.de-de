---
title: <issuerChannelBehaviors>-Element
ms.date: 03/30/2017
ms.assetid: f7378673-8e9b-45b2-98d1-cf5dccdd8c40
no-loc:
- <system.serviceModel>
- <behaviors>
- <endpointBehaviors>
- <behavior>
- <clientCredentials>
- <issuedToken>
- <issuerChannelBehaviors>
- <dataContractSerializer>
ms.openlocfilehash: cbbfb9d3b5af47a360aa82cf837cd6749f61b641
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/06/2020
ms.locfileid: "70893157"
---
# <a name="issuerchannelbehaviors-element"></a><span data-ttu-id="aac81-102">\<issuerChannelBehaviors>-Element</span><span class="sxs-lookup"><span data-stu-id="aac81-102">\<issuerChannelBehaviors> Element</span></span>

<span data-ttu-id="aac81-103">Enthält eine Auflistung von Windows Communication Foundation (WCF)-clientend Punkt Verhaltensweisen (in der Konfiguration definiert), die bei der Kommunikation mit den angegebenen diensttokendiensten verwendet werden sollen.</span><span class="sxs-lookup"><span data-stu-id="aac81-103">Contains a collection of Windows Communication Foundation (WCF) client endpoint behaviors (defined in the configuration) to be used when communicating with the specified Service Token Services.</span></span> <span data-ttu-id="aac81-104">Die definierten Verhalten können keine [\<clientCredentials>](clientcredentials.md) Elemente enthalten.</span><span class="sxs-lookup"><span data-stu-id="aac81-104">The defined behaviors cannot include any [\<clientCredentials>](clientcredentials.md) elements.</span></span>

[\<configuration>](../configuration-element.md)\
&nbsp;&nbsp;[\<system.serviceModel>](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[\<behaviors>](behaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[\<endpointBehaviors>](endpointbehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[\<behavior>](behavior-of-endpointbehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[\<clientCredentials>](clientcredentials.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[\<issuedToken>](issuedtoken.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<issuerChannelBehaviors>

## <a name="syntax"></a><span data-ttu-id="aac81-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="aac81-105">Syntax</span></span>

```xml
<issuerChannelBehaviors>
  <add behaviorConfiguration="string"
       issuerAddress="string" />
</issuerChannelBehaviors>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="aac81-106">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="aac81-106">Attributes and elements</span></span>

<span data-ttu-id="aac81-107">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="aac81-107">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="aac81-108">Attribute</span><span class="sxs-lookup"><span data-stu-id="aac81-108">Attributes</span></span>

<span data-ttu-id="aac81-109">Keine</span><span class="sxs-lookup"><span data-stu-id="aac81-109">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="aac81-110">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="aac81-110">Child elements</span></span>

|<span data-ttu-id="aac81-111">Element</span><span class="sxs-lookup"><span data-stu-id="aac81-111">Element</span></span>|<span data-ttu-id="aac81-112">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="aac81-112">Description</span></span>|
|-------------|-----------------|
|[\<add>](add-of-issuerchannelbehaviors.md)|<span data-ttu-id="aac81-113">Fügt der Auflistung ein Verhalten hinzu.</span><span class="sxs-lookup"><span data-stu-id="aac81-113">Adds a behavior to the collection.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="aac81-114">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="aac81-114">Parent elements</span></span>

|<span data-ttu-id="aac81-115">Element</span><span class="sxs-lookup"><span data-stu-id="aac81-115">Element</span></span>|<span data-ttu-id="aac81-116">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="aac81-116">Description</span></span>|
|-------------|-----------------|
|[\<issuedToken>](issuedtoken.md)|<span data-ttu-id="aac81-117">Gibt ein benutzerdefiniertes Token an, das zum Authentifizieren eines Clients bei einem Dienst verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="aac81-117">Specifies a custom token used to authenticate a client to a service.</span></span>|

## <a name="remarks"></a><span data-ttu-id="aac81-118">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="aac81-118">Remarks</span></span>

<span data-ttu-id="aac81-119">Verwenden Sie dieses Element, wenn ein Verhalten (im Gegensatz zu Verhalten, die `<clientCredentials>`-Elemente umfassen) für die Kommunikation mit einem Dienst verwendet werden muss.</span><span class="sxs-lookup"><span data-stu-id="aac81-119">Use this element when any behaviors (other than behaviors that include `<clientCredentials>` elements) must be used to communicate with a service.</span></span> <span data-ttu-id="aac81-120">Beispielsweise, wenn ein [\<dataContractSerializer>](datacontractserializer-element.md) Verhaltens Element eingeschlossen werden muss.</span><span class="sxs-lookup"><span data-stu-id="aac81-120">For example, if a [\<dataContractSerializer>](datacontractserializer-element.md) behavior element must be included.</span></span>

## <a name="see-also"></a><span data-ttu-id="aac81-121">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="aac81-121">See also</span></span>

- <xref:System.ServiceModel.Configuration.IssuedTokenClientElement.IssuerChannelBehaviors%2A>
- <xref:System.ServiceModel.Configuration.IssuedTokenClientBehaviorsElement>
- <xref:System.ServiceModel.Configuration.IssuedTokenClientBehaviorsElementCollection>
- <xref:System.ServiceModel.Security.IssuedTokenClientCredential.IssuerChannelBehaviors%2A>
- [<span data-ttu-id="aac81-122">Dienstidentität und Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="aac81-122">Service Identity and Authentication</span></span>](../../../wcf/feature-details/service-identity-and-authentication.md)
- [<span data-ttu-id="aac81-123">Sicherheitsverhalten</span><span class="sxs-lookup"><span data-stu-id="aac81-123">Security Behaviors</span></span>](../../../wcf/feature-details/security-behaviors-in-wcf.md)
- [<span data-ttu-id="aac81-124">Verbund und ausgestellte Token</span><span class="sxs-lookup"><span data-stu-id="aac81-124">Federation and Issued Tokens</span></span>](../../../wcf/feature-details/federation-and-issued-tokens.md)
- [<span data-ttu-id="aac81-125">Sichern von Diensten und Clients</span><span class="sxs-lookup"><span data-stu-id="aac81-125">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="aac81-126">Sichern von Clients</span><span class="sxs-lookup"><span data-stu-id="aac81-126">Securing Clients</span></span>](../../../wcf/securing-clients.md)
- [<span data-ttu-id="aac81-127">Vorgehensweise: Erstellen eines Verbundclients</span><span class="sxs-lookup"><span data-stu-id="aac81-127">How to: Create a Federated Client</span></span>](../../../wcf/feature-details/how-to-create-a-federated-client.md)
- [<span data-ttu-id="aac81-128">Vorgehensweise: Konfigurieren eines lokalen Ausstellers</span><span class="sxs-lookup"><span data-stu-id="aac81-128">How to: Configure a Local Issuer</span></span>](../../../wcf/feature-details/how-to-configure-a-local-issuer.md)
- [<span data-ttu-id="aac81-129">Verbund und ausgestellte Token</span><span class="sxs-lookup"><span data-stu-id="aac81-129">Federation and Issued Tokens</span></span>](../../../wcf/feature-details/federation-and-issued-tokens.md)
