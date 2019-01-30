---
title: <peer> von <serviceCredentials>
ms.date: 03/30/2017
ms.assetid: b134e21d-e5b5-458e-9309-626dbf8db4ed
ms.openlocfilehash: 2090e79e6affe8ade6e2e52b94d2c4e1dafe8fa1
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/30/2019
ms.locfileid: "55266025"
---
# <a name="peer-of-servicecredentials"></a><span data-ttu-id="beb4b-102">\<Peer > des \<ServiceCredentials ></span><span class="sxs-lookup"><span data-stu-id="beb4b-102">\<peer> of \<serviceCredentials></span></span>
<span data-ttu-id="beb4b-103">Gibt die aktuellen Anmeldeinformationen für einen Peerknoten an.</span><span class="sxs-lookup"><span data-stu-id="beb4b-103">Specifies the current credentials for a peer node.</span></span>  
  
 <span data-ttu-id="beb4b-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="beb4b-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="beb4b-105">\<behaviors></span><span class="sxs-lookup"><span data-stu-id="beb4b-105">\<behaviors></span></span>  
<span data-ttu-id="beb4b-106">\<serviceBehaviors></span><span class="sxs-lookup"><span data-stu-id="beb4b-106">\<serviceBehaviors></span></span>  
<span data-ttu-id="beb4b-107">\<behavior></span><span class="sxs-lookup"><span data-stu-id="beb4b-107">\<behavior></span></span>  
<span data-ttu-id="beb4b-108">\<serviceCredentials></span><span class="sxs-lookup"><span data-stu-id="beb4b-108">\<serviceCredentials></span></span>  
<span data-ttu-id="beb4b-109">\<peer></span><span class="sxs-lookup"><span data-stu-id="beb4b-109">\<peer></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="beb4b-110">Syntax</span><span class="sxs-lookup"><span data-stu-id="beb4b-110">Syntax</span></span>  
  
```xml  
<peer>
  <certificate />
  <peerAuthentication />
  <messageSenderAuthentication />
</peer>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="beb4b-111">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="beb4b-111">Attributes and Elements</span></span>  
 <span data-ttu-id="beb4b-112">In den folgenden Abschnitten werden Attribute, untergeordnete Elemente sowie übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="beb4b-112">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="beb4b-113">Attribute</span><span class="sxs-lookup"><span data-stu-id="beb4b-113">Attributes</span></span>  
 <span data-ttu-id="beb4b-114">Keine</span><span class="sxs-lookup"><span data-stu-id="beb4b-114">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="beb4b-115">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="beb4b-115">Child Elements</span></span>  
  
|<span data-ttu-id="beb4b-116">Element</span><span class="sxs-lookup"><span data-stu-id="beb4b-116">Element</span></span>|<span data-ttu-id="beb4b-117">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="beb4b-117">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="beb4b-118">\<certificate></span><span class="sxs-lookup"><span data-stu-id="beb4b-118">\<certificate></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/certificate-of-peer.md)|<span data-ttu-id="beb4b-119">Gibt ein X.509-Zertifikat an, das zum Signieren und Verschlüsseln von Nachrichten für Peer-to-Peer-Dienste verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="beb4b-119">Specifies an X.509 certificate to use for signing and encrypting messages for peer-to-peer services.</span></span> <span data-ttu-id="beb4b-120">sein.</span><span class="sxs-lookup"><span data-stu-id="beb4b-120">.</span></span>|  
|[<span data-ttu-id="beb4b-121">\<messageSenderAuthentication></span><span class="sxs-lookup"><span data-stu-id="beb4b-121">\<messageSenderAuthentication></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/messagesenderauthentication.md)|<span data-ttu-id="beb4b-122">Gibt die Authentifizierungsoptionen für Nachrichtenabsender an.</span><span class="sxs-lookup"><span data-stu-id="beb4b-122">Specifies authentication options for message senders.</span></span>|  
|[<span data-ttu-id="beb4b-123">\<peerAuthentication></span><span class="sxs-lookup"><span data-stu-id="beb4b-123">\<peerAuthentication></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/peerauthentication.md)|<span data-ttu-id="beb4b-124">Gibt die Authentifizierungsoptionen für Peerdienste an.</span><span class="sxs-lookup"><span data-stu-id="beb4b-124">Specifies authentication options for peer services.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="beb4b-125">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="beb4b-125">Parent Elements</span></span>  
  
|<span data-ttu-id="beb4b-126">Element</span><span class="sxs-lookup"><span data-stu-id="beb4b-126">Element</span></span>|<span data-ttu-id="beb4b-127">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="beb4b-127">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="beb4b-128">\<serviceCredentials></span><span class="sxs-lookup"><span data-stu-id="beb4b-128">\<serviceCredentials></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/servicecredentials.md)|<span data-ttu-id="beb4b-129">Gibt die Anmeldeinformationen an, die für die Authentifizierung des Diensts verwendet werden sollen, sowie die Einstellungen für die Validierung der Clientanmeldeinformationen.</span><span class="sxs-lookup"><span data-stu-id="beb4b-129">Specifies the credential to be used in authenticating the service, and the client credential validation-related settings.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="beb4b-130">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="beb4b-130">See also</span></span>
- <xref:System.ServiceModel.Configuration.PeerCredentialElement>
- <xref:System.ServiceModel.Configuration.ServiceCredentialsElement.Peer%2A>
- <xref:System.ServiceModel.Description.ServiceCredentials.Peer%2A>
- <xref:System.ServiceModel.Security.PeerCredential>
- [<span data-ttu-id="beb4b-131">Peer-to-Peer-Netzwerke</span><span class="sxs-lookup"><span data-stu-id="beb4b-131">Peer-to-Peer Networking</span></span>](../../../../../docs/framework/wcf/feature-details/peer-to-peer-networking.md)
- [<span data-ttu-id="beb4b-132">Peerkanal-Nachrichtenauthentifizierung</span><span class="sxs-lookup"><span data-stu-id="beb4b-132">Peer Channel Message Authentication</span></span>](https://msdn.microsoft.com/library/80e73386-514e-4c30-9e4a-b9ca8c173a95)
- [<span data-ttu-id="beb4b-133">Benutzerdefinierter Peerkanal-Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="beb4b-133">Peer Channel Custom Authentication</span></span>](https://msdn.microsoft.com/library/4aa8a82e-41a8-48e2-8621-7e1cbabdca7c)
- [<span data-ttu-id="beb4b-134">Sichern von Peerkanalanwendungen</span><span class="sxs-lookup"><span data-stu-id="beb4b-134">Securing Peer Channel Applications</span></span>](../../../../../docs/framework/wcf/feature-details/securing-peer-channel-applications.md)
- [<span data-ttu-id="beb4b-135">Sichern von Diensten und Clients</span><span class="sxs-lookup"><span data-stu-id="beb4b-135">Securing Services and Clients</span></span>](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)
