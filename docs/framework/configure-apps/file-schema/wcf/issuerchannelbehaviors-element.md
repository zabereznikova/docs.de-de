---
title: '&lt;issuerChannelBehaviors&gt;-Element'
ms.date: 03/30/2017
ms.assetid: f7378673-8e9b-45b2-98d1-cf5dccdd8c40
ms.openlocfilehash: 7e5b8ace06a224db3abcc6b9d0ec87ccbc1a6a77
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
---
# <a name="ltissuerchannelbehaviorsgt-element"></a><span data-ttu-id="aa449-102">&lt;issuerChannelBehaviors&gt;-Element</span><span class="sxs-lookup"><span data-stu-id="aa449-102">&lt;issuerChannelBehaviors&gt; Element</span></span>
<span data-ttu-id="aa449-103">Enthält eine Auflistung von Windows Communication Foundation (WCF)-Client-Endpunktverhalten (definiert in der Konfiguration), die bei der Kommunikation mit den angegebenen Sicherheitstokendiensten verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="aa449-103">Contains a collection of Windows Communication Foundation (WCF) client endpoint behaviors (defined in the configuration) to be used when communicating with the specified Service Token Services.</span></span> <span data-ttu-id="aa449-104">Die definierten Verhaltensweisen nicht enthalten [ \<ClientCredentials >](../../../../../docs/framework/configure-apps/file-schema/wcf/clientcredentials.md) Elemente.</span><span class="sxs-lookup"><span data-stu-id="aa449-104">The defined behaviors cannot include any [\<clientCredentials>](../../../../../docs/framework/configure-apps/file-schema/wcf/clientcredentials.md) elements.</span></span>  
  
 <span data-ttu-id="aa449-105">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="aa449-105">\<system.ServiceModel></span></span>  
<span data-ttu-id="aa449-106">\<behaviors></span><span class="sxs-lookup"><span data-stu-id="aa449-106">\<behaviors></span></span>  
<span data-ttu-id="aa449-107">EndpointBehaviors-Abschnitt</span><span class="sxs-lookup"><span data-stu-id="aa449-107">endpointBehaviors section</span></span>  
<span data-ttu-id="aa449-108">\<Verhalten ></span><span class="sxs-lookup"><span data-stu-id="aa449-108">\<behavior></span></span>  
<span data-ttu-id="aa449-109">\<clientCredentials></span><span class="sxs-lookup"><span data-stu-id="aa449-109">\<clientCredentials></span></span>  
<span data-ttu-id="aa449-110">\<IssuedToken ></span><span class="sxs-lookup"><span data-stu-id="aa449-110">\<issuedToken></span></span>  
<span data-ttu-id="aa449-111">\<IssuerChannelBehaviors ></span><span class="sxs-lookup"><span data-stu-id="aa449-111">\<issuerChannelBehaviors></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="aa449-112">Syntax</span><span class="sxs-lookup"><span data-stu-id="aa449-112">Syntax</span></span>  
  
```xml  
<issuerChannelBehaviors>  
      <add behaviorConfiguraton="string"  
                issuerAddress="string" />  
</issuerChannelBehaviors>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="aa449-113">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="aa449-113">Attributes and Elements</span></span>  
 <span data-ttu-id="aa449-114">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="aa449-114">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="aa449-115">Attribute</span><span class="sxs-lookup"><span data-stu-id="aa449-115">Attributes</span></span>  
 <span data-ttu-id="aa449-116">Keine</span><span class="sxs-lookup"><span data-stu-id="aa449-116">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="aa449-117">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="aa449-117">Child Elements</span></span>  
  
|<span data-ttu-id="aa449-118">Element</span><span class="sxs-lookup"><span data-stu-id="aa449-118">Element</span></span>|<span data-ttu-id="aa449-119">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="aa449-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="aa449-120">\<add></span><span class="sxs-lookup"><span data-stu-id="aa449-120">\<add></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-issuerchannelbehaviors.md)|<span data-ttu-id="aa449-121">Fügt der Auflistung ein Verhalten hinzu.</span><span class="sxs-lookup"><span data-stu-id="aa449-121">Adds a behavior to the collection.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="aa449-122">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="aa449-122">Parent Elements</span></span>  
  
|<span data-ttu-id="aa449-123">Element</span><span class="sxs-lookup"><span data-stu-id="aa449-123">Element</span></span>|<span data-ttu-id="aa449-124">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="aa449-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="aa449-125">\<IssuedToken ></span><span class="sxs-lookup"><span data-stu-id="aa449-125">\<issuedToken></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/issuedtoken.md)|<span data-ttu-id="aa449-126">Gibt ein benutzerdefiniertes Token an, das zum Authentifizieren eines Clients bei einem Dienst verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="aa449-126">Specifies a custom token used to authenticate a client to a service.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="aa449-127">Hinweise</span><span class="sxs-lookup"><span data-stu-id="aa449-127">Remarks</span></span>  
 <span data-ttu-id="aa449-128">Verwenden Sie dieses Element, wenn ein Verhalten (im Gegensatz zu Verhalten, die `<clientCredentials>`-Elemente umfassen) für die Kommunikation mit einem Dienst verwendet werden muss.</span><span class="sxs-lookup"><span data-stu-id="aa449-128">Use this element when any behaviors (other than behaviors that include `<clientCredentials>` elements) must be used to communicate with a service.</span></span> <span data-ttu-id="aa449-129">Z. B. wenn ein [ \<"DataContractSerializer" >](../../../../../docs/framework/configure-apps/file-schema/wcf/datacontractserializer-element.md) verhaltenselement eingeschlossen werden muss.</span><span class="sxs-lookup"><span data-stu-id="aa449-129">For example, if a [\<dataContractSerializer>](../../../../../docs/framework/configure-apps/file-schema/wcf/datacontractserializer-element.md) behavior element must be included.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="aa449-130">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="aa449-130">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.IssuedTokenClientElement.IssuerChannelBehaviors%2A>  
 <xref:System.ServiceModel.Configuration.IssuedTokenClientBehaviorsElement>  
 <xref:System.ServiceModel.Configuration.IssuedTokenClientBehaviorsElementCollection>  
 <xref:System.ServiceModel.Security.IssuedTokenClientCredential.IssuerChannelBehaviors%2A>  
 [<span data-ttu-id="aa449-131">Dienstidentität und Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="aa449-131">Service Identity and Authentication</span></span>](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md)  
 [<span data-ttu-id="aa449-132">Sicherheitsverhalten</span><span class="sxs-lookup"><span data-stu-id="aa449-132">Security Behaviors</span></span>](../../../../../docs/framework/wcf/feature-details/security-behaviors-in-wcf.md)  
 [<span data-ttu-id="aa449-133">Verbund und ausgestellte Token</span><span class="sxs-lookup"><span data-stu-id="aa449-133">Federation and Issued Tokens</span></span>](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)  
 [<span data-ttu-id="aa449-134">Sichern von Diensten und Clients</span><span class="sxs-lookup"><span data-stu-id="aa449-134">Securing Services and Clients</span></span>](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)  
 [<span data-ttu-id="aa449-135">Sichern von Clients</span><span class="sxs-lookup"><span data-stu-id="aa449-135">Securing Clients</span></span>](../../../../../docs/framework/wcf/securing-clients.md)  
 [<span data-ttu-id="aa449-136">Vorgehensweise: Erstellen eines Verbundclients</span><span class="sxs-lookup"><span data-stu-id="aa449-136">How to: Create a Federated Client</span></span>](../../../../../docs/framework/wcf/feature-details/how-to-create-a-federated-client.md)  
 [<span data-ttu-id="aa449-137">Vorgehensweise: Konfigurieren eines lokalen Ausstellers</span><span class="sxs-lookup"><span data-stu-id="aa449-137">How to: Configure a Local Issuer</span></span>](../../../../../docs/framework/wcf/feature-details/how-to-configure-a-local-issuer.md)  
 [<span data-ttu-id="aa449-138">Verbund und ausgestellte Token</span><span class="sxs-lookup"><span data-stu-id="aa449-138">Federation and Issued Tokens</span></span>](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)
