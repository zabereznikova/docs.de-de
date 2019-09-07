---
title: <issuerChannelBehaviors>-Element
ms.date: 03/30/2017
ms.assetid: f7378673-8e9b-45b2-98d1-cf5dccdd8c40
ms.openlocfilehash: 2c0e0d8d041565edd25c4b2c2802bfd2a589b4f7
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/06/2019
ms.locfileid: "70397903"
---
# <a name="issuerchannelbehaviors-element"></a><span data-ttu-id="00397-102">\<issuerchannelverhaltens>-Element</span><span class="sxs-lookup"><span data-stu-id="00397-102">\<issuerChannelBehaviors> Element</span></span>

<span data-ttu-id="00397-103">Enthält eine Auflistung von Windows Communication Foundation (WCF)-clientend Punkt Verhaltensweisen (in der Konfiguration definiert), die bei der Kommunikation mit den angegebenen diensttokendiensten verwendet werden sollen.</span><span class="sxs-lookup"><span data-stu-id="00397-103">Contains a collection of Windows Communication Foundation (WCF) client endpoint behaviors (defined in the configuration) to be used when communicating with the specified Service Token Services.</span></span> <span data-ttu-id="00397-104">Das definierte Verhalten kann keine [ \<Clientanmelde->](clientcredentials.md) Elemente enthalten.</span><span class="sxs-lookup"><span data-stu-id="00397-104">The defined behaviors cannot include any [\<clientCredentials>](clientcredentials.md) elements.</span></span>

<span data-ttu-id="00397-105">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="00397-105">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="00397-106">&nbsp;&nbsp;[ **\<System. Service Model->** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="00397-106">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="00397-107">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Verhaltens >** ](behaviors.md)</span><span class="sxs-lookup"><span data-stu-id="00397-107">&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)</span></span>\
<span data-ttu-id="00397-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<endpointverhaltens->** ](endpointbehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="00397-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpointBehaviors>**](endpointbehaviors.md)</span></span>\
<span data-ttu-id="00397-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Verhaltens >** ](behavior-of-endpointbehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="00397-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-endpointbehaviors.md)</span></span>\
<span data-ttu-id="00397-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Client Anmelde Informationen >** ](clientcredentials.md)</span><span class="sxs-lookup"><span data-stu-id="00397-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<clientCredentials>**](clientcredentials.md)</span></span>\
<span data-ttu-id="00397-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<IssuedToken->** ](issuedtoken.md)</span><span class="sxs-lookup"><span data-stu-id="00397-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<issuedToken>**](issuedtoken.md)</span></span>\
<span data-ttu-id="00397-112">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<issuerchannelverhaltens>**</span><span class="sxs-lookup"><span data-stu-id="00397-112">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<issuerChannelBehaviors>**</span></span>  

## <a name="syntax"></a><span data-ttu-id="00397-113">Syntax</span><span class="sxs-lookup"><span data-stu-id="00397-113">Syntax</span></span>

```xml
<issuerChannelBehaviors>
  <add behaviorConfiguration="string"
       issuerAddress="string" />
</issuerChannelBehaviors>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="00397-114">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="00397-114">Attributes and Elements</span></span>

<span data-ttu-id="00397-115">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="00397-115">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="00397-116">Attribute</span><span class="sxs-lookup"><span data-stu-id="00397-116">Attributes</span></span>

<span data-ttu-id="00397-117">Keine</span><span class="sxs-lookup"><span data-stu-id="00397-117">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="00397-118">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="00397-118">Child Elements</span></span>

|<span data-ttu-id="00397-119">Element</span><span class="sxs-lookup"><span data-stu-id="00397-119">Element</span></span>|<span data-ttu-id="00397-120">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="00397-120">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="00397-121">\<add></span><span class="sxs-lookup"><span data-stu-id="00397-121">\<add></span></span>](add-of-issuerchannelbehaviors.md)|<span data-ttu-id="00397-122">Fügt der Auflistung ein Verhalten hinzu.</span><span class="sxs-lookup"><span data-stu-id="00397-122">Adds a behavior to the collection.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="00397-123">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="00397-123">Parent Elements</span></span>

|<span data-ttu-id="00397-124">Element</span><span class="sxs-lookup"><span data-stu-id="00397-124">Element</span></span>|<span data-ttu-id="00397-125">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="00397-125">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="00397-126">\<issuedToken></span><span class="sxs-lookup"><span data-stu-id="00397-126">\<issuedToken></span></span>](issuedtoken.md)|<span data-ttu-id="00397-127">Gibt ein benutzerdefiniertes Token an, das zum Authentifizieren eines Clients bei einem Dienst verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="00397-127">Specifies a custom token used to authenticate a client to a service.</span></span>|

## <a name="remarks"></a><span data-ttu-id="00397-128">Hinweise</span><span class="sxs-lookup"><span data-stu-id="00397-128">Remarks</span></span>

<span data-ttu-id="00397-129">Verwenden Sie dieses Element, wenn ein Verhalten (im Gegensatz zu Verhalten, die `<clientCredentials>`-Elemente umfassen) für die Kommunikation mit einem Dienst verwendet werden muss.</span><span class="sxs-lookup"><span data-stu-id="00397-129">Use this element when any behaviors (other than behaviors that include `<clientCredentials>` elements) must be used to communicate with a service.</span></span> <span data-ttu-id="00397-130">Beispielsweise, wenn ein [ \<DataContractSerializer->](datacontractserializer-element.md) Behavior-Element eingeschlossen werden muss.</span><span class="sxs-lookup"><span data-stu-id="00397-130">For example, if a [\<dataContractSerializer>](datacontractserializer-element.md) behavior element must be included.</span></span>

## <a name="see-also"></a><span data-ttu-id="00397-131">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="00397-131">See also</span></span>

- <xref:System.ServiceModel.Configuration.IssuedTokenClientElement.IssuerChannelBehaviors%2A>
- <xref:System.ServiceModel.Configuration.IssuedTokenClientBehaviorsElement>
- <xref:System.ServiceModel.Configuration.IssuedTokenClientBehaviorsElementCollection>
- <xref:System.ServiceModel.Security.IssuedTokenClientCredential.IssuerChannelBehaviors%2A>
- [<span data-ttu-id="00397-132">Dienstidentität und Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="00397-132">Service Identity and Authentication</span></span>](../../../wcf/feature-details/service-identity-and-authentication.md)
- [<span data-ttu-id="00397-133">Sicherheitsverhalten</span><span class="sxs-lookup"><span data-stu-id="00397-133">Security Behaviors</span></span>](../../../wcf/feature-details/security-behaviors-in-wcf.md)
- [<span data-ttu-id="00397-134">Verbund und ausgestellte Token</span><span class="sxs-lookup"><span data-stu-id="00397-134">Federation and Issued Tokens</span></span>](../../../wcf/feature-details/federation-and-issued-tokens.md)
- [<span data-ttu-id="00397-135">Sichern von Diensten und Clients</span><span class="sxs-lookup"><span data-stu-id="00397-135">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="00397-136">Sichern von Clients</span><span class="sxs-lookup"><span data-stu-id="00397-136">Securing Clients</span></span>](../../../wcf/securing-clients.md)
- [<span data-ttu-id="00397-137">Vorgehensweise: Erstellen eines Verbund Clients</span><span class="sxs-lookup"><span data-stu-id="00397-137">How to: Create a Federated Client</span></span>](../../../wcf/feature-details/how-to-create-a-federated-client.md)
- [<span data-ttu-id="00397-138">Vorgehensweise: Konfigurieren eines lokalen Ausstellers</span><span class="sxs-lookup"><span data-stu-id="00397-138">How to: Configure a Local Issuer</span></span>](../../../wcf/feature-details/how-to-configure-a-local-issuer.md)
- [<span data-ttu-id="00397-139">Verbund und ausgestellte Token</span><span class="sxs-lookup"><span data-stu-id="00397-139">Federation and Issued Tokens</span></span>](../../../wcf/feature-details/federation-and-issued-tokens.md)
