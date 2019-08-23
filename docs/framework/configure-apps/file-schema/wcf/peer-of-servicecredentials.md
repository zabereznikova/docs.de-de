---
title: <peer> von <serviceCredentials>
ms.date: 03/30/2017
ms.assetid: b134e21d-e5b5-458e-9309-626dbf8db4ed
ms.openlocfilehash: 50415cb9b35d2a2053efa3313a415de518b7e36e
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69933774"
---
# <a name="peer-of-servicecredentials"></a><span data-ttu-id="8868d-102">\<Peer > von \<servicecreden-></span><span class="sxs-lookup"><span data-stu-id="8868d-102">\<peer> of \<serviceCredentials></span></span>
<span data-ttu-id="8868d-103">Gibt die aktuellen Anmeldeinformationen für einen Peerknoten an.</span><span class="sxs-lookup"><span data-stu-id="8868d-103">Specifies the current credentials for a peer node.</span></span>  
  
 <span data-ttu-id="8868d-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="8868d-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="8868d-105">\<behaviors></span><span class="sxs-lookup"><span data-stu-id="8868d-105">\<behaviors></span></span>  
<span data-ttu-id="8868d-106">\<serviceBehaviors></span><span class="sxs-lookup"><span data-stu-id="8868d-106">\<serviceBehaviors></span></span>  
<span data-ttu-id="8868d-107">\<behavior></span><span class="sxs-lookup"><span data-stu-id="8868d-107">\<behavior></span></span>  
<span data-ttu-id="8868d-108">\<serviceCredentials></span><span class="sxs-lookup"><span data-stu-id="8868d-108">\<serviceCredentials></span></span>  
<span data-ttu-id="8868d-109">\<Peer ></span><span class="sxs-lookup"><span data-stu-id="8868d-109">\<peer></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8868d-110">Syntax</span><span class="sxs-lookup"><span data-stu-id="8868d-110">Syntax</span></span>  
  
```xml  
<peer>
  <certificate />
  <peerAuthentication />
  <messageSenderAuthentication />
</peer>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="8868d-111">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="8868d-111">Attributes and Elements</span></span>  
 <span data-ttu-id="8868d-112">In den folgenden Abschnitten werden Attribute, untergeordnete Elemente sowie übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="8868d-112">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="8868d-113">Attribute</span><span class="sxs-lookup"><span data-stu-id="8868d-113">Attributes</span></span>  
 <span data-ttu-id="8868d-114">Keine</span><span class="sxs-lookup"><span data-stu-id="8868d-114">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="8868d-115">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="8868d-115">Child Elements</span></span>  
  
|<span data-ttu-id="8868d-116">Element</span><span class="sxs-lookup"><span data-stu-id="8868d-116">Element</span></span>|<span data-ttu-id="8868d-117">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="8868d-117">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="8868d-118">\<certificate></span><span class="sxs-lookup"><span data-stu-id="8868d-118">\<certificate></span></span>](certificate-of-peer.md)|<span data-ttu-id="8868d-119">Gibt ein X.509-Zertifikat an, das zum Signieren und Verschlüsseln von Nachrichten für Peer-to-Peer-Dienste verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="8868d-119">Specifies an X.509 certificate to use for signing and encrypting messages for peer-to-peer services.</span></span> <span data-ttu-id="8868d-120">.</span><span class="sxs-lookup"><span data-stu-id="8868d-120">.</span></span>|  
|[<span data-ttu-id="8868d-121">\<messageSenderAuthentication></span><span class="sxs-lookup"><span data-stu-id="8868d-121">\<messageSenderAuthentication></span></span>](messagesenderauthentication.md)|<span data-ttu-id="8868d-122">Gibt die Authentifizierungsoptionen für Nachrichtenabsender an.</span><span class="sxs-lookup"><span data-stu-id="8868d-122">Specifies authentication options for message senders.</span></span>|  
|[<span data-ttu-id="8868d-123">\<peerAuthentication></span><span class="sxs-lookup"><span data-stu-id="8868d-123">\<peerAuthentication></span></span>](peerauthentication.md)|<span data-ttu-id="8868d-124">Gibt die Authentifizierungsoptionen für Peerdienste an.</span><span class="sxs-lookup"><span data-stu-id="8868d-124">Specifies authentication options for peer services.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="8868d-125">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="8868d-125">Parent Elements</span></span>  
  
|<span data-ttu-id="8868d-126">Element</span><span class="sxs-lookup"><span data-stu-id="8868d-126">Element</span></span>|<span data-ttu-id="8868d-127">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="8868d-127">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="8868d-128">\<serviceCredentials></span><span class="sxs-lookup"><span data-stu-id="8868d-128">\<serviceCredentials></span></span>](servicecredentials.md)|<span data-ttu-id="8868d-129">Gibt die Anmeldeinformationen an, die für die Authentifizierung des Diensts verwendet werden sollen, sowie die Einstellungen für die Validierung der Clientanmeldeinformationen.</span><span class="sxs-lookup"><span data-stu-id="8868d-129">Specifies the credential to be used in authenticating the service, and the client credential validation-related settings.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="8868d-130">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="8868d-130">See also</span></span>

- <xref:System.ServiceModel.Configuration.PeerCredentialElement>
- <xref:System.ServiceModel.Configuration.ServiceCredentialsElement.Peer%2A>
- <xref:System.ServiceModel.Description.ServiceCredentials.Peer%2A>
- <xref:System.ServiceModel.Security.PeerCredential>
- [<span data-ttu-id="8868d-131">Peer-to-Peer-Netzwerke</span><span class="sxs-lookup"><span data-stu-id="8868d-131">Peer-to-Peer Networking</span></span>](../../../wcf/feature-details/peer-to-peer-networking.md)
- <span data-ttu-id="8868d-132">[Peer Kanalnachrichten-Authentifizierung](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/aa967730(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="8868d-132">[Peer Channel Message Authentication](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/aa967730(v=vs.90))</span></span>
- <span data-ttu-id="8868d-133">[Benutzerdefinierte Peer Kanal Authentifizierung](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms751447(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="8868d-133">[Peer Channel Custom Authentication](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms751447(v=vs.90))</span></span>
- [<span data-ttu-id="8868d-134">Sichern von Peerkanalanwendungen</span><span class="sxs-lookup"><span data-stu-id="8868d-134">Securing Peer Channel Applications</span></span>](../../../wcf/feature-details/securing-peer-channel-applications.md)
- [<span data-ttu-id="8868d-135">Sichern von Diensten und Clients</span><span class="sxs-lookup"><span data-stu-id="8868d-135">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
