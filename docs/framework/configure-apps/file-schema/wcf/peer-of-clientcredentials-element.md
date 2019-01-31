---
title: <peer> der <clientCredentials> Element
ms.date: 03/30/2017
ms.assetid: 505bd987-0042-4622-b68e-94f439729d53
ms.openlocfilehash: 8970100b1ad3019ff4a639d835d1db1430968008
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/30/2019
ms.locfileid: "55275140"
---
# <a name="peer-of-clientcredentials-element"></a><span data-ttu-id="4028f-102">\<Peer > des \<ClientCredentials >-Element</span><span class="sxs-lookup"><span data-stu-id="4028f-102">\<peer> of \<clientCredentials> Element</span></span>
<span data-ttu-id="4028f-103">Gibt Anmeldeinformationen an, die bei der Authentifizierung von Peer-to-Peer-Clients verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="4028f-103">Specifies credentials used when authenticating peer-to-peer clients.</span></span>  
  
 <span data-ttu-id="4028f-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="4028f-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="4028f-105">\<behaviors></span><span class="sxs-lookup"><span data-stu-id="4028f-105">\<behaviors></span></span>  
<span data-ttu-id="4028f-106">\<endpointBehaviors></span><span class="sxs-lookup"><span data-stu-id="4028f-106">\<endpointBehaviors></span></span>  
<span data-ttu-id="4028f-107">\<behavior></span><span class="sxs-lookup"><span data-stu-id="4028f-107">\<behavior></span></span>  
<span data-ttu-id="4028f-108">\<clientCredentials></span><span class="sxs-lookup"><span data-stu-id="4028f-108">\<clientCredentials></span></span>  
<span data-ttu-id="4028f-109">\<peer></span><span class="sxs-lookup"><span data-stu-id="4028f-109">\<peer></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4028f-110">Syntax</span><span class="sxs-lookup"><span data-stu-id="4028f-110">Syntax</span></span>  
  
```xml  
<peer>
  <certificate />
  <peerAuthentication />
  <messageSenderAuthentication />
</peer>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="4028f-111">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="4028f-111">Attributes and Elements</span></span>  
 <span data-ttu-id="4028f-112">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="4028f-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="4028f-113">Attribute</span><span class="sxs-lookup"><span data-stu-id="4028f-113">Attributes</span></span>  
 <span data-ttu-id="4028f-114">Keine</span><span class="sxs-lookup"><span data-stu-id="4028f-114">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="4028f-115">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="4028f-115">Child Elements</span></span>  
  
|<span data-ttu-id="4028f-116">Element</span><span class="sxs-lookup"><span data-stu-id="4028f-116">Element</span></span>|<span data-ttu-id="4028f-117">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="4028f-117">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="4028f-118">\<certificate></span><span class="sxs-lookup"><span data-stu-id="4028f-118">\<certificate></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/certificate-element.md)|<span data-ttu-id="4028f-119">Gibt ein X.509-Zertifikat an, das zum Signieren und Verschlüsseln von Nachrichten für Peer-to-Peer-Clients verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="4028f-119">Specifies an X.509 certificate to use for signing and encrypting messages for peer-to-peer clients.</span></span> <span data-ttu-id="4028f-120">sein.</span><span class="sxs-lookup"><span data-stu-id="4028f-120">.</span></span>|  
|[<span data-ttu-id="4028f-121">\<peerAuthentication></span><span class="sxs-lookup"><span data-stu-id="4028f-121">\<peerAuthentication></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/peerauthentication-element.md)|<span data-ttu-id="4028f-122">Gibt die Authentifizierungsoptionen für Peer-Clients an.</span><span class="sxs-lookup"><span data-stu-id="4028f-122">Specifies authentication options for peer clients.</span></span>|  
|[<span data-ttu-id="4028f-123">\<messageSenderAuthentication></span><span class="sxs-lookup"><span data-stu-id="4028f-123">\<messageSenderAuthentication></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/messagesenderauthentication-element.md)|<span data-ttu-id="4028f-124">Gibt die Authentifizierungsoptionen für Nachrichtenabsender an.</span><span class="sxs-lookup"><span data-stu-id="4028f-124">Specifies authentication options for message senders.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="4028f-125">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="4028f-125">Parent Elements</span></span>  
  
|<span data-ttu-id="4028f-126">Element</span><span class="sxs-lookup"><span data-stu-id="4028f-126">Element</span></span>|<span data-ttu-id="4028f-127">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="4028f-127">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="4028f-128">\<clientCredentials></span><span class="sxs-lookup"><span data-stu-id="4028f-128">\<clientCredentials></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/clientcredentials.md)|<span data-ttu-id="4028f-129">Gibt die zum Authentifizieren des Clients beim Dienst verwendeten Anmeldeinformationen an.</span><span class="sxs-lookup"><span data-stu-id="4028f-129">Specifies the credentials used to authenticate a client to a service.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4028f-130">Hinweise</span><span class="sxs-lookup"><span data-stu-id="4028f-130">Remarks</span></span>  
 <span data-ttu-id="4028f-131">Dieses Konfigurationselement gibt die Anmeldeinformationen an, mit denen sich ein Peerknoten gegenüber anderen Knoten im Netz authentifiziert, sowie die Authentifizierungseinstellungen, mit denen ein Peerknoten andere Peerknoten authentifiziert.</span><span class="sxs-lookup"><span data-stu-id="4028f-131">This configuration element specifies the credentials that a peer node uses to authenticate itself to other nodes in the mesh, as well as authentication settings that a peer node uses to authenticate other peer nodes.</span></span> <span data-ttu-id="4028f-132">Weitere Informationen finden Sie unter [Peerkanal-Nachrichtenauthentifizierung](https://msdn.microsoft.com/library/80e73386-514e-4c30-9e4a-b9ca8c173a95) und [Sichern von Peerkanalanwendungen](../../../../../docs/framework/wcf/feature-details/securing-peer-channel-applications.md).</span><span class="sxs-lookup"><span data-stu-id="4028f-132">For more information, see [Peer Channel Message Authentication](https://msdn.microsoft.com/library/80e73386-514e-4c30-9e4a-b9ca8c173a95) and [Securing Peer Channel Applications](../../../../../docs/framework/wcf/feature-details/securing-peer-channel-applications.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4028f-133">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="4028f-133">See also</span></span>
- <xref:System.ServiceModel.Configuration.ClientCredentialsElement>
- <xref:System.ServiceModel.Description.ClientCredentials>
- <xref:System.ServiceModel.Configuration.PeerCredentialElement>
- <xref:System.ServiceModel.Configuration.ClientCredentialsElement.Peer%2A>
- <xref:System.ServiceModel.Description.ClientCredentials>
- <xref:System.ServiceModel.Description.ClientCredentials.Peer%2A>
- <xref:System.ServiceModel.Security.PeerCredential>
- [<span data-ttu-id="4028f-134">Peer-to-Peer-Netzwerke</span><span class="sxs-lookup"><span data-stu-id="4028f-134">Peer-to-Peer Networking</span></span>](../../../../../docs/framework/wcf/feature-details/peer-to-peer-networking.md)
- [<span data-ttu-id="4028f-135">Sichern von Clients</span><span class="sxs-lookup"><span data-stu-id="4028f-135">Securing Clients</span></span>](../../../../../docs/framework/wcf/securing-clients.md)
- [<span data-ttu-id="4028f-136">Peerkanal-Nachrichtenauthentifizierung</span><span class="sxs-lookup"><span data-stu-id="4028f-136">Peer Channel Message Authentication</span></span>](https://msdn.microsoft.com/library/80e73386-514e-4c30-9e4a-b9ca8c173a95)
- [<span data-ttu-id="4028f-137">Benutzerdefinierter Peerkanal-Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="4028f-137">Peer Channel Custom Authentication</span></span>](https://msdn.microsoft.com/library/4aa8a82e-41a8-48e2-8621-7e1cbabdca7c)
- [<span data-ttu-id="4028f-138">Sichern von Peerkanalanwendungen</span><span class="sxs-lookup"><span data-stu-id="4028f-138">Securing Peer Channel Applications</span></span>](../../../../../docs/framework/wcf/feature-details/securing-peer-channel-applications.md)
- [<span data-ttu-id="4028f-139">Sichern von Diensten und Clients</span><span class="sxs-lookup"><span data-stu-id="4028f-139">Securing Services and Clients</span></span>](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)
