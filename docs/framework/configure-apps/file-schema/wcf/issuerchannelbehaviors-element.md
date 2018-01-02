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
ms.workload: dotnet
ms.openlocfilehash: bb90b318f99816a3886056394559fdc80fa986ef
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="ltissuerchannelbehaviorsgt-element"></a><span data-ttu-id="a1066-102">&lt;issuerChannelBehaviors&gt;-Element</span><span class="sxs-lookup"><span data-stu-id="a1066-102">&lt;issuerChannelBehaviors&gt; Element</span></span>
<span data-ttu-id="a1066-103">Enthält eine Auflistung der [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)]-Client-Endpunktverhalten (definiert in der Konfiguration), die für die Kommunikation mit den angegebenen Sicherheitstokendiensten verwendet werden sollen.</span><span class="sxs-lookup"><span data-stu-id="a1066-103">Contains a collection of [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] client endpoint behaviors (defined in the configuration) to be used when communicating with the specified Service Token Services.</span></span> <span data-ttu-id="a1066-104">Die definierten Verhaltensweisen nicht enthalten [ \<ClientCredentials >](../../../../../docs/framework/configure-apps/file-schema/wcf/clientcredentials.md) Elemente.</span><span class="sxs-lookup"><span data-stu-id="a1066-104">The defined behaviors cannot include any [\<clientCredentials>](../../../../../docs/framework/configure-apps/file-schema/wcf/clientcredentials.md) elements.</span></span>  
  
 <span data-ttu-id="a1066-105">\<System. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="a1066-105">\<system.ServiceModel></span></span>  
<span data-ttu-id="a1066-106">\<Verhalten ></span><span class="sxs-lookup"><span data-stu-id="a1066-106">\<behaviors></span></span>  
<span data-ttu-id="a1066-107">EndpointBehaviors-Abschnitt</span><span class="sxs-lookup"><span data-stu-id="a1066-107">endpointBehaviors section</span></span>  
<span data-ttu-id="a1066-108">\<Verhalten ></span><span class="sxs-lookup"><span data-stu-id="a1066-108">\<behavior></span></span>  
<span data-ttu-id="a1066-109">\<ClientCredentials ></span><span class="sxs-lookup"><span data-stu-id="a1066-109">\<clientCredentials></span></span>  
<span data-ttu-id="a1066-110">\<IssuedToken ></span><span class="sxs-lookup"><span data-stu-id="a1066-110">\<issuedToken></span></span>  
<span data-ttu-id="a1066-111">\<IssuerChannelBehaviors ></span><span class="sxs-lookup"><span data-stu-id="a1066-111">\<issuerChannelBehaviors></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a1066-112">Syntax</span><span class="sxs-lookup"><span data-stu-id="a1066-112">Syntax</span></span>  
  
```xml  
<issuerChannelBehaviors>  
      <add behaviorConfiguraton="string"  
                issuerAddress="string" />  
</issuerChannelBehaviors>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="a1066-113">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="a1066-113">Attributes and Elements</span></span>  
 <span data-ttu-id="a1066-114">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="a1066-114">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="a1066-115">Attribute</span><span class="sxs-lookup"><span data-stu-id="a1066-115">Attributes</span></span>  
 <span data-ttu-id="a1066-116">Keine</span><span class="sxs-lookup"><span data-stu-id="a1066-116">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="a1066-117">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="a1066-117">Child Elements</span></span>  
  
|<span data-ttu-id="a1066-118">Element</span><span class="sxs-lookup"><span data-stu-id="a1066-118">Element</span></span>|<span data-ttu-id="a1066-119">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="a1066-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="a1066-120">\<add></span><span class="sxs-lookup"><span data-stu-id="a1066-120">\<add></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-issuerchannelbehaviors.md)|<span data-ttu-id="a1066-121">Fügt der Auflistung ein Verhalten hinzu.</span><span class="sxs-lookup"><span data-stu-id="a1066-121">Adds a behavior to the collection.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="a1066-122">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="a1066-122">Parent Elements</span></span>  
  
|<span data-ttu-id="a1066-123">Element</span><span class="sxs-lookup"><span data-stu-id="a1066-123">Element</span></span>|<span data-ttu-id="a1066-124">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="a1066-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="a1066-125">\<IssuedToken ></span><span class="sxs-lookup"><span data-stu-id="a1066-125">\<issuedToken></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/issuedtoken.md)|<span data-ttu-id="a1066-126">Gibt ein benutzerdefiniertes Token an, das zum Authentifizieren eines Clients bei einem Dienst verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="a1066-126">Specifies a custom token used to authenticate a client to a service.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a1066-127">Hinweise</span><span class="sxs-lookup"><span data-stu-id="a1066-127">Remarks</span></span>  
 <span data-ttu-id="a1066-128">Verwenden Sie dieses Element, wenn ein Verhalten (im Gegensatz zu Verhalten, die `<clientCredentials>`-Elemente umfassen) für die Kommunikation mit einem Dienst verwendet werden muss.</span><span class="sxs-lookup"><span data-stu-id="a1066-128">Use this element when any behaviors (other than behaviors that include `<clientCredentials>` elements) must be used to communicate with a service.</span></span> <span data-ttu-id="a1066-129">Z. B. wenn ein [ \<"DataContractSerializer" >](../../../../../docs/framework/configure-apps/file-schema/wcf/datacontractserializer-element.md) verhaltenselement eingeschlossen werden muss.</span><span class="sxs-lookup"><span data-stu-id="a1066-129">For example, if a [\<dataContractSerializer>](../../../../../docs/framework/configure-apps/file-schema/wcf/datacontractserializer-element.md) behavior element must be included.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a1066-130">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a1066-130">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.IssuedTokenClientElement.IssuerChannelBehaviors%2A>  
 <xref:System.ServiceModel.Configuration.IssuedTokenClientBehaviorsElement>  
 <xref:System.ServiceModel.Configuration.IssuedTokenClientBehaviorsElementCollection>  
 <xref:System.ServiceModel.Security.IssuedTokenClientCredential.IssuerChannelBehaviors%2A>  
 [<span data-ttu-id="a1066-131">Dienstidentität und Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="a1066-131">Service Identity and Authentication</span></span>](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md)  
 [<span data-ttu-id="a1066-132">Sicherheitsverhalten</span><span class="sxs-lookup"><span data-stu-id="a1066-132">Security Behaviors</span></span>](../../../../../docs/framework/wcf/feature-details/security-behaviors-in-wcf.md)  
 [<span data-ttu-id="a1066-133">Verbund und ausgestellte Token</span><span class="sxs-lookup"><span data-stu-id="a1066-133">Federation and Issued Tokens</span></span>](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)  
 [<span data-ttu-id="a1066-134">Sichern von Diensten und Clients</span><span class="sxs-lookup"><span data-stu-id="a1066-134">Securing Services and Clients</span></span>](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)  
 [<span data-ttu-id="a1066-135">Sichern von Clients</span><span class="sxs-lookup"><span data-stu-id="a1066-135">Securing Clients</span></span>](../../../../../docs/framework/wcf/securing-clients.md)  
 [<span data-ttu-id="a1066-136">Vorgehensweise: Erstellen eines Verbundclients</span><span class="sxs-lookup"><span data-stu-id="a1066-136">How to: Create a Federated Client</span></span>](../../../../../docs/framework/wcf/feature-details/how-to-create-a-federated-client.md)  
 [<span data-ttu-id="a1066-137">Vorgehensweise: Konfigurieren eines lokalen Ausstellers</span><span class="sxs-lookup"><span data-stu-id="a1066-137">How to: Configure a Local Issuer</span></span>](../../../../../docs/framework/wcf/feature-details/how-to-configure-a-local-issuer.md)  
 [<span data-ttu-id="a1066-138">Verbund und ausgestellte Token</span><span class="sxs-lookup"><span data-stu-id="a1066-138">Federation and Issued Tokens</span></span>](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)
