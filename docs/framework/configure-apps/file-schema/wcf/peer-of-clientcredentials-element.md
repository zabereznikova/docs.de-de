---
title: <peer>of <clientCredentials> -Element
ms.date: 03/30/2017
ms.assetid: 505bd987-0042-4622-b68e-94f439729d53
ms.openlocfilehash: 2f1cb5689125e2483a74dcac515beb07abbb7c70
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69934036"
---
# <a name="peer-of-clientcredentials-element"></a><span data-ttu-id="754f8-102">\<Peer > von \<Clientanmelde Informationen > Element</span><span class="sxs-lookup"><span data-stu-id="754f8-102">\<peer> of \<clientCredentials> Element</span></span>
<span data-ttu-id="754f8-103">Gibt Anmeldeinformationen an, die bei der Authentifizierung von Peer-to-Peer-Clients verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="754f8-103">Specifies credentials used when authenticating peer-to-peer clients.</span></span>  
  
 <span data-ttu-id="754f8-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="754f8-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="754f8-105">\<behaviors></span><span class="sxs-lookup"><span data-stu-id="754f8-105">\<behaviors></span></span>  
<span data-ttu-id="754f8-106">\<endpointBehaviors></span><span class="sxs-lookup"><span data-stu-id="754f8-106">\<endpointBehaviors></span></span>  
<span data-ttu-id="754f8-107">\<behavior></span><span class="sxs-lookup"><span data-stu-id="754f8-107">\<behavior></span></span>  
<span data-ttu-id="754f8-108">\<clientCredentials></span><span class="sxs-lookup"><span data-stu-id="754f8-108">\<clientCredentials></span></span>  
<span data-ttu-id="754f8-109">\<Peer ></span><span class="sxs-lookup"><span data-stu-id="754f8-109">\<peer></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="754f8-110">Syntax</span><span class="sxs-lookup"><span data-stu-id="754f8-110">Syntax</span></span>  
  
```xml  
<peer>
  <certificate />
  <peerAuthentication />
  <messageSenderAuthentication />
</peer>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="754f8-111">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="754f8-111">Attributes and Elements</span></span>  
 <span data-ttu-id="754f8-112">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="754f8-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="754f8-113">Attribute</span><span class="sxs-lookup"><span data-stu-id="754f8-113">Attributes</span></span>  
 <span data-ttu-id="754f8-114">Keine</span><span class="sxs-lookup"><span data-stu-id="754f8-114">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="754f8-115">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="754f8-115">Child Elements</span></span>  
  
|<span data-ttu-id="754f8-116">Element</span><span class="sxs-lookup"><span data-stu-id="754f8-116">Element</span></span>|<span data-ttu-id="754f8-117">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="754f8-117">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="754f8-118">\<certificate></span><span class="sxs-lookup"><span data-stu-id="754f8-118">\<certificate></span></span>](certificate-element.md)|<span data-ttu-id="754f8-119">Gibt ein X.509-Zertifikat an, das zum Signieren und Verschlüsseln von Nachrichten für Peer-to-Peer-Clients verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="754f8-119">Specifies an X.509 certificate to use for signing and encrypting messages for peer-to-peer clients.</span></span> <span data-ttu-id="754f8-120">.</span><span class="sxs-lookup"><span data-stu-id="754f8-120">.</span></span>|  
|[<span data-ttu-id="754f8-121">\<peerAuthentication></span><span class="sxs-lookup"><span data-stu-id="754f8-121">\<peerAuthentication></span></span>](peerauthentication-element.md)|<span data-ttu-id="754f8-122">Gibt die Authentifizierungsoptionen für Peer-Clients an.</span><span class="sxs-lookup"><span data-stu-id="754f8-122">Specifies authentication options for peer clients.</span></span>|  
|[<span data-ttu-id="754f8-123">\<messageSenderAuthentication></span><span class="sxs-lookup"><span data-stu-id="754f8-123">\<messageSenderAuthentication></span></span>](messagesenderauthentication-element.md)|<span data-ttu-id="754f8-124">Gibt die Authentifizierungsoptionen für Nachrichtenabsender an.</span><span class="sxs-lookup"><span data-stu-id="754f8-124">Specifies authentication options for message senders.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="754f8-125">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="754f8-125">Parent Elements</span></span>  
  
|<span data-ttu-id="754f8-126">Element</span><span class="sxs-lookup"><span data-stu-id="754f8-126">Element</span></span>|<span data-ttu-id="754f8-127">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="754f8-127">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="754f8-128">\<clientCredentials></span><span class="sxs-lookup"><span data-stu-id="754f8-128">\<clientCredentials></span></span>](clientcredentials.md)|<span data-ttu-id="754f8-129">Gibt die zum Authentifizieren des Clients beim Dienst verwendeten Anmeldeinformationen an.</span><span class="sxs-lookup"><span data-stu-id="754f8-129">Specifies the credentials used to authenticate a client to a service.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="754f8-130">Hinweise</span><span class="sxs-lookup"><span data-stu-id="754f8-130">Remarks</span></span>  
 <span data-ttu-id="754f8-131">Dieses Konfigurationselement gibt die Anmeldeinformationen an, mit denen sich ein Peerknoten gegenüber anderen Knoten im Netz authentifiziert, sowie die Authentifizierungseinstellungen, mit denen ein Peerknoten andere Peerknoten authentifiziert.</span><span class="sxs-lookup"><span data-stu-id="754f8-131">This configuration element specifies the credentials that a peer node uses to authenticate itself to other nodes in the mesh, as well as authentication settings that a peer node uses to authenticate other peer nodes.</span></span> <span data-ttu-id="754f8-132">Weitere Informationen finden Sie unter [Peer Channel Message Authentication](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/aa967730(v=vs.90)) und [Sichern von Peer Kanal Anwendungen](../../../wcf/feature-details/securing-peer-channel-applications.md).</span><span class="sxs-lookup"><span data-stu-id="754f8-132">For more information, see [Peer Channel Message Authentication](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/aa967730(v=vs.90)) and [Securing Peer Channel Applications](../../../wcf/feature-details/securing-peer-channel-applications.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="754f8-133">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="754f8-133">See also</span></span>

- <xref:System.ServiceModel.Configuration.ClientCredentialsElement>
- <xref:System.ServiceModel.Description.ClientCredentials>
- <xref:System.ServiceModel.Configuration.PeerCredentialElement>
- <xref:System.ServiceModel.Configuration.ClientCredentialsElement.Peer%2A>
- <xref:System.ServiceModel.Description.ClientCredentials>
- <xref:System.ServiceModel.Description.ClientCredentials.Peer%2A>
- <xref:System.ServiceModel.Security.PeerCredential>
- [<span data-ttu-id="754f8-134">Peer-to-Peer-Netzwerke</span><span class="sxs-lookup"><span data-stu-id="754f8-134">Peer-to-Peer Networking</span></span>](../../../wcf/feature-details/peer-to-peer-networking.md)
- [<span data-ttu-id="754f8-135">Sichern von Clients</span><span class="sxs-lookup"><span data-stu-id="754f8-135">Securing Clients</span></span>](../../../wcf/securing-clients.md)
- <span data-ttu-id="754f8-136">[Peer Kanalnachrichten-Authentifizierung](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/aa967730(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="754f8-136">[Peer Channel Message Authentication](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/aa967730(v=vs.90))</span></span>
- <span data-ttu-id="754f8-137">[Benutzerdefinierte Peer Kanal Authentifizierung](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms751447(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="754f8-137">[Peer Channel Custom Authentication](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms751447(v=vs.90))</span></span>
- [<span data-ttu-id="754f8-138">Sichern von Peerkanalanwendungen</span><span class="sxs-lookup"><span data-stu-id="754f8-138">Securing Peer Channel Applications</span></span>](../../../wcf/feature-details/securing-peer-channel-applications.md)
- [<span data-ttu-id="754f8-139">Sichern von Diensten und Clients</span><span class="sxs-lookup"><span data-stu-id="754f8-139">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
