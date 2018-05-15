---
title: '&lt;peer&gt; des &lt;clientCredentials&gt;-Elements'
ms.date: 03/30/2017
ms.assetid: 505bd987-0042-4622-b68e-94f439729d53
ms.openlocfilehash: 9d64f682f67dcc7c4f0c0f1600938f8ff9ac0dd6
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
---
# <a name="ltpeergt-of-ltclientcredentialsgt-element"></a><span data-ttu-id="0ca7a-102">&lt;peer&gt; des &lt;clientCredentials&gt;-Elements</span><span class="sxs-lookup"><span data-stu-id="0ca7a-102">&lt;peer&gt; of &lt;clientCredentials&gt; Element</span></span>
<span data-ttu-id="0ca7a-103">Gibt Anmeldeinformationen an, die bei der Authentifizierung von Peer-to-Peer-Clients verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="0ca7a-103">Specifies credentials used when authenticating peer-to-peer clients.</span></span>  
  
 <span data-ttu-id="0ca7a-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="0ca7a-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="0ca7a-105">\<behaviors></span><span class="sxs-lookup"><span data-stu-id="0ca7a-105">\<behaviors></span></span>  
<span data-ttu-id="0ca7a-106">\<endpointBehaviors></span><span class="sxs-lookup"><span data-stu-id="0ca7a-106">\<endpointBehaviors></span></span>  
<span data-ttu-id="0ca7a-107">\<Verhalten ></span><span class="sxs-lookup"><span data-stu-id="0ca7a-107">\<behavior></span></span>  
<span data-ttu-id="0ca7a-108">\<clientCredentials></span><span class="sxs-lookup"><span data-stu-id="0ca7a-108">\<clientCredentials></span></span>  
<span data-ttu-id="0ca7a-109">\<Peer ></span><span class="sxs-lookup"><span data-stu-id="0ca7a-109">\<peer></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0ca7a-110">Syntax</span><span class="sxs-lookup"><span data-stu-id="0ca7a-110">Syntax</span></span>  
  
```xml  
<peer>  
  <certificate/>  
  <peerAuthentication/>  
  <messageSenderAuthentication/>  
</peer>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="0ca7a-111">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="0ca7a-111">Attributes and Elements</span></span>  
 <span data-ttu-id="0ca7a-112">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="0ca7a-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="0ca7a-113">Attribute</span><span class="sxs-lookup"><span data-stu-id="0ca7a-113">Attributes</span></span>  
 <span data-ttu-id="0ca7a-114">Keine</span><span class="sxs-lookup"><span data-stu-id="0ca7a-114">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="0ca7a-115">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="0ca7a-115">Child Elements</span></span>  
  
|<span data-ttu-id="0ca7a-116">Element</span><span class="sxs-lookup"><span data-stu-id="0ca7a-116">Element</span></span>|<span data-ttu-id="0ca7a-117">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="0ca7a-117">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="0ca7a-118">\<certificate></span><span class="sxs-lookup"><span data-stu-id="0ca7a-118">\<certificate></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/certificate-element.md)|<span data-ttu-id="0ca7a-119">Gibt ein X.509-Zertifikat an, das zum Signieren und Verschlüsseln von Nachrichten für Peer-to-Peer-Clients verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="0ca7a-119">Specifies an X.509 certificate to use for signing and encrypting messages for peer-to-peer clients.</span></span> <span data-ttu-id="0ca7a-120">sein.</span><span class="sxs-lookup"><span data-stu-id="0ca7a-120">.</span></span>|  
|[<span data-ttu-id="0ca7a-121">\<peerAuthentication></span><span class="sxs-lookup"><span data-stu-id="0ca7a-121">\<peerAuthentication></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/peerauthentication-element.md)|<span data-ttu-id="0ca7a-122">Gibt die Authentifizierungsoptionen für Peer-Clients an.</span><span class="sxs-lookup"><span data-stu-id="0ca7a-122">Specifies authentication options for peer clients.</span></span>|  
|[<span data-ttu-id="0ca7a-123">\<messageSenderAuthentication></span><span class="sxs-lookup"><span data-stu-id="0ca7a-123">\<messageSenderAuthentication></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/messagesenderauthentication-element.md)|<span data-ttu-id="0ca7a-124">Gibt die Authentifizierungsoptionen für Nachrichtenabsender an.</span><span class="sxs-lookup"><span data-stu-id="0ca7a-124">Specifies authentication options for message senders.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="0ca7a-125">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="0ca7a-125">Parent Elements</span></span>  
  
|<span data-ttu-id="0ca7a-126">Element</span><span class="sxs-lookup"><span data-stu-id="0ca7a-126">Element</span></span>|<span data-ttu-id="0ca7a-127">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="0ca7a-127">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="0ca7a-128">\<clientCredentials></span><span class="sxs-lookup"><span data-stu-id="0ca7a-128">\<clientCredentials></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/clientcredentials.md)|<span data-ttu-id="0ca7a-129">Gibt die zum Authentifizieren des Clients beim Dienst verwendeten Anmeldeinformationen an.</span><span class="sxs-lookup"><span data-stu-id="0ca7a-129">Specifies the credentials used to authenticate a client to a service.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0ca7a-130">Hinweise</span><span class="sxs-lookup"><span data-stu-id="0ca7a-130">Remarks</span></span>  
 <span data-ttu-id="0ca7a-131">Dieses Konfigurationselement gibt die Anmeldeinformationen an, mit denen sich ein Peerknoten gegenüber anderen Knoten im Netz authentifiziert, sowie die Authentifizierungseinstellungen, mit denen ein Peerknoten andere Peerknoten authentifiziert.</span><span class="sxs-lookup"><span data-stu-id="0ca7a-131">This configuration element specifies the credentials that a peer node uses to authenticate itself to other nodes in the mesh, as well as authentication settings that a peer node uses to authenticate other peer nodes.</span></span> <span data-ttu-id="0ca7a-132">Weitere Informationen finden Sie unter [Peer Kanal Nachrichtenauthentifizierung](http://msdn.microsoft.com/library/80e73386-514e-4c30-9e4a-b9ca8c173a95) und [Sichern von Peer-Kanal Anwendungen](../../../../../docs/framework/wcf/feature-details/securing-peer-channel-applications.md).</span><span class="sxs-lookup"><span data-stu-id="0ca7a-132">For more information, see [Peer Channel Message Authentication](http://msdn.microsoft.com/library/80e73386-514e-4c30-9e4a-b9ca8c173a95) and [Securing Peer Channel Applications](../../../../../docs/framework/wcf/feature-details/securing-peer-channel-applications.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0ca7a-133">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="0ca7a-133">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.ClientCredentialsElement>  
 <xref:System.ServiceModel.Description.ClientCredentials>  
 <xref:System.ServiceModel.Configuration.PeerCredentialElement>  
 <xref:System.ServiceModel.Configuration.ClientCredentialsElement.Peer%2A>  
 <xref:System.ServiceModel.Description.ClientCredentials>  
 <xref:System.ServiceModel.Description.ClientCredentials.Peer%2A>  
 <xref:System.ServiceModel.Security.PeerCredential>  
 [<span data-ttu-id="0ca7a-134">Peer-to-Peer-Netzwerke</span><span class="sxs-lookup"><span data-stu-id="0ca7a-134">Peer-to-Peer Networking</span></span>](../../../../../docs/framework/wcf/feature-details/peer-to-peer-networking.md)  
 [<span data-ttu-id="0ca7a-135">Sichern von Clients</span><span class="sxs-lookup"><span data-stu-id="0ca7a-135">Securing Clients</span></span>](../../../../../docs/framework/wcf/securing-clients.md)  
 [<span data-ttu-id="0ca7a-136">Peerkanal Nachrichtenauthentifizierung</span><span class="sxs-lookup"><span data-stu-id="0ca7a-136">Peer Channel Message Authentication</span></span>](http://msdn.microsoft.com/library/80e73386-514e-4c30-9e4a-b9ca8c173a95)  
 [<span data-ttu-id="0ca7a-137">Benutzerdefinierter Peerkanal-Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="0ca7a-137">Peer Channel Custom Authentication</span></span>](http://msdn.microsoft.com/library/4aa8a82e-41a8-48e2-8621-7e1cbabdca7c)  
 [<span data-ttu-id="0ca7a-138">Sichern von Peerkanalanwendungen</span><span class="sxs-lookup"><span data-stu-id="0ca7a-138">Securing Peer Channel Applications</span></span>](../../../../../docs/framework/wcf/feature-details/securing-peer-channel-applications.md)  
 [<span data-ttu-id="0ca7a-139">Sichern von Diensten und Clients</span><span class="sxs-lookup"><span data-stu-id="0ca7a-139">Securing Services and Clients</span></span>](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)
