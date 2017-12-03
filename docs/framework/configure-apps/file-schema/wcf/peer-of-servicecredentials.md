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
ms.openlocfilehash: 3754964d07dd80442fbffd7c632304ef9d83ab1d
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/02/2017
---
# <a name="ltpeergt-of-ltservicecredentialsgt"></a><span data-ttu-id="a6d83-102">&lt;peer&gt; von &lt;serviceCredentials&gt;</span><span class="sxs-lookup"><span data-stu-id="a6d83-102">&lt;peer&gt; of &lt;serviceCredentials&gt;</span></span>
<span data-ttu-id="a6d83-103">Gibt die aktuellen Anmeldeinformationen für einen Peerknoten an.</span><span class="sxs-lookup"><span data-stu-id="a6d83-103">Specifies the current credentials for a peer node.</span></span>  
  
 <span data-ttu-id="a6d83-104">\<System. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="a6d83-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="a6d83-105">\<Verhalten ></span><span class="sxs-lookup"><span data-stu-id="a6d83-105">\<behaviors></span></span>  
<span data-ttu-id="a6d83-106">\<ServiceBehaviors ></span><span class="sxs-lookup"><span data-stu-id="a6d83-106">\<serviceBehaviors></span></span>  
<span data-ttu-id="a6d83-107">\<Verhalten ></span><span class="sxs-lookup"><span data-stu-id="a6d83-107">\<behavior></span></span>  
<span data-ttu-id="a6d83-108">\<ServiceCredentials ></span><span class="sxs-lookup"><span data-stu-id="a6d83-108">\<serviceCredentials></span></span>  
<span data-ttu-id="a6d83-109">\<Peer ></span><span class="sxs-lookup"><span data-stu-id="a6d83-109">\<peer></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a6d83-110">Syntax</span><span class="sxs-lookup"><span data-stu-id="a6d83-110">Syntax</span></span>  
  
```xml  
<peer>  
  <certificate/>  
  <peerAuthentication/>  
  <messageSenderAuthentication/>  
</peer>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="a6d83-111">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="a6d83-111">Attributes and Elements</span></span>  
 <span data-ttu-id="a6d83-112">In den folgenden Abschnitten werden Attribute, untergeordnete Elemente sowie übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="a6d83-112">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="a6d83-113">Attribute</span><span class="sxs-lookup"><span data-stu-id="a6d83-113">Attributes</span></span>  
 <span data-ttu-id="a6d83-114">Keine.</span><span class="sxs-lookup"><span data-stu-id="a6d83-114">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="a6d83-115">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="a6d83-115">Child Elements</span></span>  
  
|<span data-ttu-id="a6d83-116">Element</span><span class="sxs-lookup"><span data-stu-id="a6d83-116">Element</span></span>|<span data-ttu-id="a6d83-117">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="a6d83-117">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="a6d83-118">\<Zertifikat ></span><span class="sxs-lookup"><span data-stu-id="a6d83-118">\<certificate></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/certificate-of-peer.md)|<span data-ttu-id="a6d83-119">Gibt ein X.509-Zertifikat an, das zum Signieren und Verschlüsseln von Nachrichten für Peer-to-Peer-Dienste verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="a6d83-119">Specifies an X.509 certificate to use for signing and encrypting messages for peer-to-peer services.</span></span> <span data-ttu-id="a6d83-120">.</span><span class="sxs-lookup"><span data-stu-id="a6d83-120">.</span></span>|  
|[<span data-ttu-id="a6d83-121">\<MessageSenderAuthentication ></span><span class="sxs-lookup"><span data-stu-id="a6d83-121">\<messageSenderAuthentication></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/messagesenderauthentication.md)|<span data-ttu-id="a6d83-122">Gibt die Authentifizierungsoptionen für Nachrichtenabsender an.</span><span class="sxs-lookup"><span data-stu-id="a6d83-122">Specifies authentication options for message senders.</span></span>|  
|[<span data-ttu-id="a6d83-123">\<PeerAuthentication ></span><span class="sxs-lookup"><span data-stu-id="a6d83-123">\<peerAuthentication></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/peerauthentication.md)|<span data-ttu-id="a6d83-124">Gibt die Authentifizierungsoptionen für Peerdienste an.</span><span class="sxs-lookup"><span data-stu-id="a6d83-124">Specifies authentication options for peer services.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="a6d83-125">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="a6d83-125">Parent Elements</span></span>  
  
|<span data-ttu-id="a6d83-126">Element</span><span class="sxs-lookup"><span data-stu-id="a6d83-126">Element</span></span>|<span data-ttu-id="a6d83-127">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="a6d83-127">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="a6d83-128">\<ServiceCredentials ></span><span class="sxs-lookup"><span data-stu-id="a6d83-128">\<serviceCredentials></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/servicecredentials.md)|<span data-ttu-id="a6d83-129">Gibt die Anmeldeinformationen an, die für die Authentifizierung des Diensts verwendet werden sollen, sowie die Einstellungen für die Validierung der Clientanmeldeinformationen.</span><span class="sxs-lookup"><span data-stu-id="a6d83-129">Specifies the credential to be used in authenticating the service, and the client credential validation-related settings.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="a6d83-130">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a6d83-130">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.PeerCredentialElement>  
 <xref:System.ServiceModel.Configuration.ServiceCredentialsElement.Peer%2A>  
 <xref:System.ServiceModel.Description.ServiceCredentials.Peer%2A>  
 <xref:System.ServiceModel.Security.PeerCredential>  
 [<span data-ttu-id="a6d83-131">Peer-zu-Peer-Netzwerken</span><span class="sxs-lookup"><span data-stu-id="a6d83-131">Peer-to-Peer Networking</span></span>](../../../../../docs/framework/wcf/feature-details/peer-to-peer-networking.md)  
 [<span data-ttu-id="a6d83-132">Peerkanal Nachrichtenauthentifizierung</span><span class="sxs-lookup"><span data-stu-id="a6d83-132">Peer Channel Message Authentication</span></span>](http://msdn.microsoft.com/en-us/80e73386-514e-4c30-9e4a-b9ca8c173a95)  
 [<span data-ttu-id="a6d83-133">Benutzerdefinierter Peerkanal-Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="a6d83-133">Peer Channel Custom Authentication</span></span>](http://msdn.microsoft.com/en-us/4aa8a82e-41a8-48e2-8621-7e1cbabdca7c)  
 [<span data-ttu-id="a6d83-134">Sichern von Peerkanalanwendungen</span><span class="sxs-lookup"><span data-stu-id="a6d83-134">Securing Peer Channel Applications</span></span>](../../../../../docs/framework/wcf/feature-details/securing-peer-channel-applications.md)  
 [<span data-ttu-id="a6d83-135">Sichern von Diensten und Clients</span><span class="sxs-lookup"><span data-stu-id="a6d83-135">Securing Services and Clients</span></span>](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)
