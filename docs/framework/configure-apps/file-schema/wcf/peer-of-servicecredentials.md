---
title: '&lt;peer&gt; von &lt;serviceCredentials&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: b134e21d-e5b5-458e-9309-626dbf8db4ed
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: d04c6121c5d106f5877517e9f72d1b533480dfb7
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="ltpeergt-of-ltservicecredentialsgt"></a><span data-ttu-id="5d42a-102">&lt;peer&gt; von &lt;serviceCredentials&gt;</span><span class="sxs-lookup"><span data-stu-id="5d42a-102">&lt;peer&gt; of &lt;serviceCredentials&gt;</span></span>
<span data-ttu-id="5d42a-103">Gibt die aktuellen Anmeldeinformationen für einen Peerknoten an.</span><span class="sxs-lookup"><span data-stu-id="5d42a-103">Specifies the current credentials for a peer node.</span></span>  
  
 <span data-ttu-id="5d42a-104">\<System. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="5d42a-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="5d42a-105">\<Verhalten ></span><span class="sxs-lookup"><span data-stu-id="5d42a-105">\<behaviors></span></span>  
<span data-ttu-id="5d42a-106">\<ServiceBehaviors ></span><span class="sxs-lookup"><span data-stu-id="5d42a-106">\<serviceBehaviors></span></span>  
<span data-ttu-id="5d42a-107">\<Verhalten ></span><span class="sxs-lookup"><span data-stu-id="5d42a-107">\<behavior></span></span>  
<span data-ttu-id="5d42a-108">\<ServiceCredentials ></span><span class="sxs-lookup"><span data-stu-id="5d42a-108">\<serviceCredentials></span></span>  
<span data-ttu-id="5d42a-109">\<Peer ></span><span class="sxs-lookup"><span data-stu-id="5d42a-109">\<peer></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5d42a-110">Syntax</span><span class="sxs-lookup"><span data-stu-id="5d42a-110">Syntax</span></span>  
  
```xml  
<peer>  
  <certificate/>  
  <peerAuthentication/>  
  <messageSenderAuthentication/>  
</peer>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="5d42a-111">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="5d42a-111">Attributes and Elements</span></span>  
 <span data-ttu-id="5d42a-112">In den folgenden Abschnitten werden Attribute, untergeordnete Elemente sowie übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="5d42a-112">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="5d42a-113">Attribute</span><span class="sxs-lookup"><span data-stu-id="5d42a-113">Attributes</span></span>  
 <span data-ttu-id="5d42a-114">Keine</span><span class="sxs-lookup"><span data-stu-id="5d42a-114">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="5d42a-115">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="5d42a-115">Child Elements</span></span>  
  
|<span data-ttu-id="5d42a-116">Element</span><span class="sxs-lookup"><span data-stu-id="5d42a-116">Element</span></span>|<span data-ttu-id="5d42a-117">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="5d42a-117">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="5d42a-118">\<Zertifikat ></span><span class="sxs-lookup"><span data-stu-id="5d42a-118">\<certificate></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/certificate-of-peer.md)|<span data-ttu-id="5d42a-119">Gibt ein X.509-Zertifikat an, das zum Signieren und Verschlüsseln von Nachrichten für Peer-to-Peer-Dienste verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="5d42a-119">Specifies an X.509 certificate to use for signing and encrypting messages for peer-to-peer services.</span></span> <span data-ttu-id="5d42a-120">sein.</span><span class="sxs-lookup"><span data-stu-id="5d42a-120">.</span></span>|  
|[<span data-ttu-id="5d42a-121">\<MessageSenderAuthentication ></span><span class="sxs-lookup"><span data-stu-id="5d42a-121">\<messageSenderAuthentication></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/messagesenderauthentication.md)|<span data-ttu-id="5d42a-122">Gibt die Authentifizierungsoptionen für Nachrichtenabsender an.</span><span class="sxs-lookup"><span data-stu-id="5d42a-122">Specifies authentication options for message senders.</span></span>|  
|[<span data-ttu-id="5d42a-123">\<PeerAuthentication ></span><span class="sxs-lookup"><span data-stu-id="5d42a-123">\<peerAuthentication></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/peerauthentication.md)|<span data-ttu-id="5d42a-124">Gibt die Authentifizierungsoptionen für Peerdienste an.</span><span class="sxs-lookup"><span data-stu-id="5d42a-124">Specifies authentication options for peer services.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="5d42a-125">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="5d42a-125">Parent Elements</span></span>  
  
|<span data-ttu-id="5d42a-126">Element</span><span class="sxs-lookup"><span data-stu-id="5d42a-126">Element</span></span>|<span data-ttu-id="5d42a-127">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="5d42a-127">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="5d42a-128">\<ServiceCredentials ></span><span class="sxs-lookup"><span data-stu-id="5d42a-128">\<serviceCredentials></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/servicecredentials.md)|<span data-ttu-id="5d42a-129">Gibt die Anmeldeinformationen an, die für die Authentifizierung des Diensts verwendet werden sollen, sowie die Einstellungen für die Validierung der Clientanmeldeinformationen.</span><span class="sxs-lookup"><span data-stu-id="5d42a-129">Specifies the credential to be used in authenticating the service, and the client credential validation-related settings.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="5d42a-130">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="5d42a-130">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.PeerCredentialElement>  
 <xref:System.ServiceModel.Configuration.ServiceCredentialsElement.Peer%2A>  
 <xref:System.ServiceModel.Description.ServiceCredentials.Peer%2A>  
 <xref:System.ServiceModel.Security.PeerCredential>  
 [<span data-ttu-id="5d42a-131">Peer-to-Peer-Netzwerke</span><span class="sxs-lookup"><span data-stu-id="5d42a-131">Peer-to-Peer Networking</span></span>](../../../../../docs/framework/wcf/feature-details/peer-to-peer-networking.md)  
 [<span data-ttu-id="5d42a-132">Peerkanal Nachrichtenauthentifizierung</span><span class="sxs-lookup"><span data-stu-id="5d42a-132">Peer Channel Message Authentication</span></span>](http://msdn.microsoft.com/en-us/80e73386-514e-4c30-9e4a-b9ca8c173a95)  
 [<span data-ttu-id="5d42a-133">Benutzerdefinierter Peerkanal-Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="5d42a-133">Peer Channel Custom Authentication</span></span>](http://msdn.microsoft.com/en-us/4aa8a82e-41a8-48e2-8621-7e1cbabdca7c)  
 [<span data-ttu-id="5d42a-134">Sichern von Peerkanalanwendungen</span><span class="sxs-lookup"><span data-stu-id="5d42a-134">Securing Peer Channel Applications</span></span>](../../../../../docs/framework/wcf/feature-details/securing-peer-channel-applications.md)  
 [<span data-ttu-id="5d42a-135">Sichern von Diensten und Clients</span><span class="sxs-lookup"><span data-stu-id="5d42a-135">Securing Services and Clients</span></span>](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)
