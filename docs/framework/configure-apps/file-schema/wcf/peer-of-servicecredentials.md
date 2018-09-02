---
title: '&lt;peer&gt; von &lt;serviceCredentials&gt;'
ms.date: 03/30/2017
ms.assetid: b134e21d-e5b5-458e-9309-626dbf8db4ed
ms.openlocfilehash: 94f93a7955af3bff1c17e59a11af3fad85c9134d
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/01/2018
ms.locfileid: "43399842"
---
# <a name="ltpeergt-of-ltservicecredentialsgt"></a><span data-ttu-id="ae9a0-102">&lt;peer&gt; von &lt;serviceCredentials&gt;</span><span class="sxs-lookup"><span data-stu-id="ae9a0-102">&lt;peer&gt; of &lt;serviceCredentials&gt;</span></span>
<span data-ttu-id="ae9a0-103">Gibt die aktuellen Anmeldeinformationen für einen Peerknoten an.</span><span class="sxs-lookup"><span data-stu-id="ae9a0-103">Specifies the current credentials for a peer node.</span></span>  
  
 <span data-ttu-id="ae9a0-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="ae9a0-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="ae9a0-105">\<behaviors></span><span class="sxs-lookup"><span data-stu-id="ae9a0-105">\<behaviors></span></span>  
<span data-ttu-id="ae9a0-106">\<serviceBehaviors></span><span class="sxs-lookup"><span data-stu-id="ae9a0-106">\<serviceBehaviors></span></span>  
<span data-ttu-id="ae9a0-107">\<Verhalten ></span><span class="sxs-lookup"><span data-stu-id="ae9a0-107">\<behavior></span></span>  
<span data-ttu-id="ae9a0-108">\<serviceCredentials></span><span class="sxs-lookup"><span data-stu-id="ae9a0-108">\<serviceCredentials></span></span>  
<span data-ttu-id="ae9a0-109">\<Peer ></span><span class="sxs-lookup"><span data-stu-id="ae9a0-109">\<peer></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ae9a0-110">Syntax</span><span class="sxs-lookup"><span data-stu-id="ae9a0-110">Syntax</span></span>  
  
```xml  
<peer>  
  <certificate/>  
  <peerAuthentication/>  
  <messageSenderAuthentication/>  
</peer>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="ae9a0-111">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="ae9a0-111">Attributes and Elements</span></span>  
 <span data-ttu-id="ae9a0-112">In den folgenden Abschnitten werden Attribute, untergeordnete Elemente sowie übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="ae9a0-112">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="ae9a0-113">Attribute</span><span class="sxs-lookup"><span data-stu-id="ae9a0-113">Attributes</span></span>  
 <span data-ttu-id="ae9a0-114">Keine</span><span class="sxs-lookup"><span data-stu-id="ae9a0-114">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="ae9a0-115">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="ae9a0-115">Child Elements</span></span>  
  
|<span data-ttu-id="ae9a0-116">Element</span><span class="sxs-lookup"><span data-stu-id="ae9a0-116">Element</span></span>|<span data-ttu-id="ae9a0-117">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="ae9a0-117">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="ae9a0-118">\<certificate></span><span class="sxs-lookup"><span data-stu-id="ae9a0-118">\<certificate></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/certificate-of-peer.md)|<span data-ttu-id="ae9a0-119">Gibt ein X.509-Zertifikat an, das zum Signieren und Verschlüsseln von Nachrichten für Peer-to-Peer-Dienste verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="ae9a0-119">Specifies an X.509 certificate to use for signing and encrypting messages for peer-to-peer services.</span></span> <span data-ttu-id="ae9a0-120">sein.</span><span class="sxs-lookup"><span data-stu-id="ae9a0-120">.</span></span>|  
|[<span data-ttu-id="ae9a0-121">\<messageSenderAuthentication></span><span class="sxs-lookup"><span data-stu-id="ae9a0-121">\<messageSenderAuthentication></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/messagesenderauthentication.md)|<span data-ttu-id="ae9a0-122">Gibt die Authentifizierungsoptionen für Nachrichtenabsender an.</span><span class="sxs-lookup"><span data-stu-id="ae9a0-122">Specifies authentication options for message senders.</span></span>|  
|[<span data-ttu-id="ae9a0-123">\<peerAuthentication></span><span class="sxs-lookup"><span data-stu-id="ae9a0-123">\<peerAuthentication></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/peerauthentication.md)|<span data-ttu-id="ae9a0-124">Gibt die Authentifizierungsoptionen für Peerdienste an.</span><span class="sxs-lookup"><span data-stu-id="ae9a0-124">Specifies authentication options for peer services.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="ae9a0-125">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="ae9a0-125">Parent Elements</span></span>  
  
|<span data-ttu-id="ae9a0-126">Element</span><span class="sxs-lookup"><span data-stu-id="ae9a0-126">Element</span></span>|<span data-ttu-id="ae9a0-127">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="ae9a0-127">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="ae9a0-128">\<serviceCredentials></span><span class="sxs-lookup"><span data-stu-id="ae9a0-128">\<serviceCredentials></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/servicecredentials.md)|<span data-ttu-id="ae9a0-129">Gibt die Anmeldeinformationen an, die für die Authentifizierung des Diensts verwendet werden sollen, sowie die Einstellungen für die Validierung der Clientanmeldeinformationen.</span><span class="sxs-lookup"><span data-stu-id="ae9a0-129">Specifies the credential to be used in authenticating the service, and the client credential validation-related settings.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="ae9a0-130">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ae9a0-130">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.PeerCredentialElement>  
 <xref:System.ServiceModel.Configuration.ServiceCredentialsElement.Peer%2A>  
 <xref:System.ServiceModel.Description.ServiceCredentials.Peer%2A>  
 <xref:System.ServiceModel.Security.PeerCredential>  
 [<span data-ttu-id="ae9a0-131">Peer-to-Peer-Netzwerke</span><span class="sxs-lookup"><span data-stu-id="ae9a0-131">Peer-to-Peer Networking</span></span>](../../../../../docs/framework/wcf/feature-details/peer-to-peer-networking.md)  
 [<span data-ttu-id="ae9a0-132">Peerkanal-Nachrichtenauthentifizierung</span><span class="sxs-lookup"><span data-stu-id="ae9a0-132">Peer Channel Message Authentication</span></span>](https://msdn.microsoft.com/library/80e73386-514e-4c30-9e4a-b9ca8c173a95)  
 [<span data-ttu-id="ae9a0-133">Benutzerdefinierter Peerkanal-Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="ae9a0-133">Peer Channel Custom Authentication</span></span>](https://msdn.microsoft.com/library/4aa8a82e-41a8-48e2-8621-7e1cbabdca7c)  
 [<span data-ttu-id="ae9a0-134">Sichern von Peerkanalanwendungen</span><span class="sxs-lookup"><span data-stu-id="ae9a0-134">Securing Peer Channel Applications</span></span>](../../../../../docs/framework/wcf/feature-details/securing-peer-channel-applications.md)  
 [<span data-ttu-id="ae9a0-135">Sichern von Diensten und Clients</span><span class="sxs-lookup"><span data-stu-id="ae9a0-135">Securing Services and Clients</span></span>](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)
