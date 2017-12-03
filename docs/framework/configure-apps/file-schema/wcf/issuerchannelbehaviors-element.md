---
title: '&lt;issuerChannelBehaviors&gt;-Element'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: f7378673-8e9b-45b2-98d1-cf5dccdd8c40
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: b73d090aa47e18792d313b3d086e7a667e74bb08
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/02/2017
---
# <a name="ltissuerchannelbehaviorsgt-element"></a><span data-ttu-id="67c1a-102">&lt;issuerChannelBehaviors&gt;-Element</span><span class="sxs-lookup"><span data-stu-id="67c1a-102">&lt;issuerChannelBehaviors&gt; Element</span></span>
<span data-ttu-id="67c1a-103">Enthält eine Auflistung der [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)]-Client-Endpunktverhalten (definiert in der Konfiguration), die für die Kommunikation mit den angegebenen Sicherheitstokendiensten verwendet werden sollen.</span><span class="sxs-lookup"><span data-stu-id="67c1a-103">Contains a collection of [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] client endpoint behaviors (defined in the configuration) to be used when communicating with the specified Service Token Services.</span></span> <span data-ttu-id="67c1a-104">Die definierten Verhaltensweisen nicht enthalten [ \<ClientCredentials >](../../../../../docs/framework/configure-apps/file-schema/wcf/clientcredentials.md) Elemente.</span><span class="sxs-lookup"><span data-stu-id="67c1a-104">The defined behaviors cannot include any [\<clientCredentials>](../../../../../docs/framework/configure-apps/file-schema/wcf/clientcredentials.md) elements.</span></span>  
  
 <span data-ttu-id="67c1a-105">\<System. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="67c1a-105">\<system.ServiceModel></span></span>  
<span data-ttu-id="67c1a-106">\<Verhalten ></span><span class="sxs-lookup"><span data-stu-id="67c1a-106">\<behaviors></span></span>  
<span data-ttu-id="67c1a-107">EndpointBehaviors-Abschnitt</span><span class="sxs-lookup"><span data-stu-id="67c1a-107">endpointBehaviors section</span></span>  
<span data-ttu-id="67c1a-108">\<Verhalten ></span><span class="sxs-lookup"><span data-stu-id="67c1a-108">\<behavior></span></span>  
<span data-ttu-id="67c1a-109">\<ClientCredentials ></span><span class="sxs-lookup"><span data-stu-id="67c1a-109">\<clientCredentials></span></span>  
<span data-ttu-id="67c1a-110">\<IssuedToken ></span><span class="sxs-lookup"><span data-stu-id="67c1a-110">\<issuedToken></span></span>  
<span data-ttu-id="67c1a-111">\<IssuerChannelBehaviors ></span><span class="sxs-lookup"><span data-stu-id="67c1a-111">\<issuerChannelBehaviors></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="67c1a-112">Syntax</span><span class="sxs-lookup"><span data-stu-id="67c1a-112">Syntax</span></span>  
  
```xml  
<issuerChannelBehaviors>  
      <add behaviorConfiguraton="string"  
                issuerAddress="string" />  
</issuerChannelBehaviors>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="67c1a-113">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="67c1a-113">Attributes and Elements</span></span>  
 <span data-ttu-id="67c1a-114">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="67c1a-114">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="67c1a-115">Attribute</span><span class="sxs-lookup"><span data-stu-id="67c1a-115">Attributes</span></span>  
 <span data-ttu-id="67c1a-116">Keine.</span><span class="sxs-lookup"><span data-stu-id="67c1a-116">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="67c1a-117">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="67c1a-117">Child Elements</span></span>  
  
|<span data-ttu-id="67c1a-118">Element</span><span class="sxs-lookup"><span data-stu-id="67c1a-118">Element</span></span>|<span data-ttu-id="67c1a-119">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="67c1a-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="67c1a-120">\<add></span><span class="sxs-lookup"><span data-stu-id="67c1a-120">\<add></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-issuerchannelbehaviors.md)|<span data-ttu-id="67c1a-121">Fügt der Auflistung ein Verhalten hinzu.</span><span class="sxs-lookup"><span data-stu-id="67c1a-121">Adds a behavior to the collection.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="67c1a-122">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="67c1a-122">Parent Elements</span></span>  
  
|<span data-ttu-id="67c1a-123">Element</span><span class="sxs-lookup"><span data-stu-id="67c1a-123">Element</span></span>|<span data-ttu-id="67c1a-124">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="67c1a-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="67c1a-125">\<IssuedToken ></span><span class="sxs-lookup"><span data-stu-id="67c1a-125">\<issuedToken></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/issuedtoken.md)|<span data-ttu-id="67c1a-126">Gibt ein benutzerdefiniertes Token an, das zum Authentifizieren eines Clients bei einem Dienst verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="67c1a-126">Specifies a custom token used to authenticate a client to a service.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="67c1a-127">Hinweise</span><span class="sxs-lookup"><span data-stu-id="67c1a-127">Remarks</span></span>  
 <span data-ttu-id="67c1a-128">Verwenden Sie dieses Element, wenn ein Verhalten (im Gegensatz zu Verhalten, die `<clientCredentials>`-Elemente umfassen) für die Kommunikation mit einem Dienst verwendet werden muss.</span><span class="sxs-lookup"><span data-stu-id="67c1a-128">Use this element when any behaviors (other than behaviors that include `<clientCredentials>` elements) must be used to communicate with a service.</span></span> <span data-ttu-id="67c1a-129">Z. B. wenn ein [ \<"DataContractSerializer" >](../../../../../docs/framework/configure-apps/file-schema/wcf/datacontractserializer-element.md) verhaltenselement eingeschlossen werden muss.</span><span class="sxs-lookup"><span data-stu-id="67c1a-129">For example, if a [\<dataContractSerializer>](../../../../../docs/framework/configure-apps/file-schema/wcf/datacontractserializer-element.md) behavior element must be included.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="67c1a-130">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="67c1a-130">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.IssuedTokenClientElement.IssuerChannelBehaviors%2A>  
 <xref:System.ServiceModel.Configuration.IssuedTokenClientBehaviorsElement>  
 <xref:System.ServiceModel.Configuration.IssuedTokenClientBehaviorsElementCollection>  
 <xref:System.ServiceModel.Security.IssuedTokenClientCredential.IssuerChannelBehaviors%2A>  
 [<span data-ttu-id="67c1a-131">Dienstidentität und Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="67c1a-131">Service Identity and Authentication</span></span>](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md)  
 [<span data-ttu-id="67c1a-132">Sicherheitsverhalten</span><span class="sxs-lookup"><span data-stu-id="67c1a-132">Security Behaviors</span></span>](../../../../../docs/framework/wcf/feature-details/security-behaviors-in-wcf.md)  
 [<span data-ttu-id="67c1a-133">Verbund und ausgestellte Token</span><span class="sxs-lookup"><span data-stu-id="67c1a-133">Federation and Issued Tokens</span></span>](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)  
 [<span data-ttu-id="67c1a-134">Sichern von Diensten und Clients</span><span class="sxs-lookup"><span data-stu-id="67c1a-134">Securing Services and Clients</span></span>](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)  
 [<span data-ttu-id="67c1a-135">Sichern von Clients</span><span class="sxs-lookup"><span data-stu-id="67c1a-135">Securing Clients</span></span>](../../../../../docs/framework/wcf/securing-clients.md)  
 [<span data-ttu-id="67c1a-136">Vorgehensweise: Erstellen eines Verbundclients</span><span class="sxs-lookup"><span data-stu-id="67c1a-136">How to: Create a Federated Client</span></span>](../../../../../docs/framework/wcf/feature-details/how-to-create-a-federated-client.md)  
 [<span data-ttu-id="67c1a-137">Vorgehensweise: Konfigurieren eines lokalen Ausstellers</span><span class="sxs-lookup"><span data-stu-id="67c1a-137">How to: Configure a Local Issuer</span></span>](../../../../../docs/framework/wcf/feature-details/how-to-configure-a-local-issuer.md)  
 [<span data-ttu-id="67c1a-138">Verbund und ausgestellte Token</span><span class="sxs-lookup"><span data-stu-id="67c1a-138">Federation and Issued Tokens</span></span>](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)
