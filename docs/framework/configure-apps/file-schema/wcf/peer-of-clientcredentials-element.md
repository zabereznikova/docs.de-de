---
title: '&lt;peer&gt; des &lt;clientCredentials&gt;-Elements'
ms.date: 03/30/2017
ms.assetid: 505bd987-0042-4622-b68e-94f439729d53
ms.openlocfilehash: 9d63aaaa6404b791559d1288730098075f1fd8eb
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/01/2018
ms.locfileid: "43385475"
---
# <a name="ltpeergt-of-ltclientcredentialsgt-element"></a><span data-ttu-id="20a2e-102">&lt;peer&gt; des &lt;clientCredentials&gt;-Elements</span><span class="sxs-lookup"><span data-stu-id="20a2e-102">&lt;peer&gt; of &lt;clientCredentials&gt; Element</span></span>
<span data-ttu-id="20a2e-103">Gibt Anmeldeinformationen an, die bei der Authentifizierung von Peer-to-Peer-Clients verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="20a2e-103">Specifies credentials used when authenticating peer-to-peer clients.</span></span>  
  
 <span data-ttu-id="20a2e-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="20a2e-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="20a2e-105">\<behaviors></span><span class="sxs-lookup"><span data-stu-id="20a2e-105">\<behaviors></span></span>  
<span data-ttu-id="20a2e-106">\<endpointBehaviors></span><span class="sxs-lookup"><span data-stu-id="20a2e-106">\<endpointBehaviors></span></span>  
<span data-ttu-id="20a2e-107">\<Verhalten ></span><span class="sxs-lookup"><span data-stu-id="20a2e-107">\<behavior></span></span>  
<span data-ttu-id="20a2e-108">\<clientCredentials></span><span class="sxs-lookup"><span data-stu-id="20a2e-108">\<clientCredentials></span></span>  
<span data-ttu-id="20a2e-109">\<Peer ></span><span class="sxs-lookup"><span data-stu-id="20a2e-109">\<peer></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="20a2e-110">Syntax</span><span class="sxs-lookup"><span data-stu-id="20a2e-110">Syntax</span></span>  
  
```xml  
<peer>  
  <certificate/>  
  <peerAuthentication/>  
  <messageSenderAuthentication/>  
</peer>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="20a2e-111">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="20a2e-111">Attributes and Elements</span></span>  
 <span data-ttu-id="20a2e-112">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="20a2e-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="20a2e-113">Attribute</span><span class="sxs-lookup"><span data-stu-id="20a2e-113">Attributes</span></span>  
 <span data-ttu-id="20a2e-114">Keine</span><span class="sxs-lookup"><span data-stu-id="20a2e-114">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="20a2e-115">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="20a2e-115">Child Elements</span></span>  
  
|<span data-ttu-id="20a2e-116">Element</span><span class="sxs-lookup"><span data-stu-id="20a2e-116">Element</span></span>|<span data-ttu-id="20a2e-117">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="20a2e-117">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="20a2e-118">\<certificate></span><span class="sxs-lookup"><span data-stu-id="20a2e-118">\<certificate></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/certificate-element.md)|<span data-ttu-id="20a2e-119">Gibt ein X.509-Zertifikat an, das zum Signieren und Verschlüsseln von Nachrichten für Peer-to-Peer-Clients verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="20a2e-119">Specifies an X.509 certificate to use for signing and encrypting messages for peer-to-peer clients.</span></span> <span data-ttu-id="20a2e-120">sein.</span><span class="sxs-lookup"><span data-stu-id="20a2e-120">.</span></span>|  
|[<span data-ttu-id="20a2e-121">\<peerAuthentication></span><span class="sxs-lookup"><span data-stu-id="20a2e-121">\<peerAuthentication></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/peerauthentication-element.md)|<span data-ttu-id="20a2e-122">Gibt die Authentifizierungsoptionen für Peer-Clients an.</span><span class="sxs-lookup"><span data-stu-id="20a2e-122">Specifies authentication options for peer clients.</span></span>|  
|[<span data-ttu-id="20a2e-123">\<messageSenderAuthentication></span><span class="sxs-lookup"><span data-stu-id="20a2e-123">\<messageSenderAuthentication></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/messagesenderauthentication-element.md)|<span data-ttu-id="20a2e-124">Gibt die Authentifizierungsoptionen für Nachrichtenabsender an.</span><span class="sxs-lookup"><span data-stu-id="20a2e-124">Specifies authentication options for message senders.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="20a2e-125">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="20a2e-125">Parent Elements</span></span>  
  
|<span data-ttu-id="20a2e-126">Element</span><span class="sxs-lookup"><span data-stu-id="20a2e-126">Element</span></span>|<span data-ttu-id="20a2e-127">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="20a2e-127">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="20a2e-128">\<clientCredentials></span><span class="sxs-lookup"><span data-stu-id="20a2e-128">\<clientCredentials></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/clientcredentials.md)|<span data-ttu-id="20a2e-129">Gibt die zum Authentifizieren des Clients beim Dienst verwendeten Anmeldeinformationen an.</span><span class="sxs-lookup"><span data-stu-id="20a2e-129">Specifies the credentials used to authenticate a client to a service.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="20a2e-130">Hinweise</span><span class="sxs-lookup"><span data-stu-id="20a2e-130">Remarks</span></span>  
 <span data-ttu-id="20a2e-131">Dieses Konfigurationselement gibt die Anmeldeinformationen an, mit denen sich ein Peerknoten gegenüber anderen Knoten im Netz authentifiziert, sowie die Authentifizierungseinstellungen, mit denen ein Peerknoten andere Peerknoten authentifiziert.</span><span class="sxs-lookup"><span data-stu-id="20a2e-131">This configuration element specifies the credentials that a peer node uses to authenticate itself to other nodes in the mesh, as well as authentication settings that a peer node uses to authenticate other peer nodes.</span></span> <span data-ttu-id="20a2e-132">Weitere Informationen finden Sie unter [Peerkanal-Nachrichtenauthentifizierung](https://msdn.microsoft.com/library/80e73386-514e-4c30-9e4a-b9ca8c173a95) und [Sichern von Peerkanalanwendungen](../../../../../docs/framework/wcf/feature-details/securing-peer-channel-applications.md).</span><span class="sxs-lookup"><span data-stu-id="20a2e-132">For more information, see [Peer Channel Message Authentication](https://msdn.microsoft.com/library/80e73386-514e-4c30-9e4a-b9ca8c173a95) and [Securing Peer Channel Applications](../../../../../docs/framework/wcf/feature-details/securing-peer-channel-applications.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="20a2e-133">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="20a2e-133">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.ClientCredentialsElement>  
 <xref:System.ServiceModel.Description.ClientCredentials>  
 <xref:System.ServiceModel.Configuration.PeerCredentialElement>  
 <xref:System.ServiceModel.Configuration.ClientCredentialsElement.Peer%2A>  
 <xref:System.ServiceModel.Description.ClientCredentials>  
 <xref:System.ServiceModel.Description.ClientCredentials.Peer%2A>  
 <xref:System.ServiceModel.Security.PeerCredential>  
 [<span data-ttu-id="20a2e-134">Peer-to-Peer-Netzwerke</span><span class="sxs-lookup"><span data-stu-id="20a2e-134">Peer-to-Peer Networking</span></span>](../../../../../docs/framework/wcf/feature-details/peer-to-peer-networking.md)  
 [<span data-ttu-id="20a2e-135">Sichern von Clients</span><span class="sxs-lookup"><span data-stu-id="20a2e-135">Securing Clients</span></span>](../../../../../docs/framework/wcf/securing-clients.md)  
 [<span data-ttu-id="20a2e-136">Peerkanal-Nachrichtenauthentifizierung</span><span class="sxs-lookup"><span data-stu-id="20a2e-136">Peer Channel Message Authentication</span></span>](https://msdn.microsoft.com/library/80e73386-514e-4c30-9e4a-b9ca8c173a95)  
 [<span data-ttu-id="20a2e-137">Benutzerdefinierter Peerkanal-Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="20a2e-137">Peer Channel Custom Authentication</span></span>](https://msdn.microsoft.com/library/4aa8a82e-41a8-48e2-8621-7e1cbabdca7c)  
 [<span data-ttu-id="20a2e-138">Sichern von Peerkanalanwendungen</span><span class="sxs-lookup"><span data-stu-id="20a2e-138">Securing Peer Channel Applications</span></span>](../../../../../docs/framework/wcf/feature-details/securing-peer-channel-applications.md)  
 [<span data-ttu-id="20a2e-139">Sichern von Diensten und Clients</span><span class="sxs-lookup"><span data-stu-id="20a2e-139">Securing Services and Clients</span></span>](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)
