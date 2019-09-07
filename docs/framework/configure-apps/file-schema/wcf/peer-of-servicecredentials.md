---
title: <peer> von <serviceCredentials>
ms.date: 03/30/2017
ms.assetid: b134e21d-e5b5-458e-9309-626dbf8db4ed
ms.openlocfilehash: ca97be7b1ab562382895fea4f1d1fc716151b70b
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/06/2019
ms.locfileid: "70397646"
---
# <a name="peer-of-servicecredentials"></a><span data-ttu-id="3a10d-102">\<Peer > von \<servicecreden-></span><span class="sxs-lookup"><span data-stu-id="3a10d-102">\<peer> of \<serviceCredentials></span></span>
<span data-ttu-id="3a10d-103">Gibt die aktuellen Anmeldeinformationen für einen Peerknoten an.</span><span class="sxs-lookup"><span data-stu-id="3a10d-103">Specifies the current credentials for a peer node.</span></span>  
  
<span data-ttu-id="3a10d-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="3a10d-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="3a10d-105">&nbsp;&nbsp;[ **\<System. Service Model->** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="3a10d-105">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="3a10d-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Verhaltens >** ](behaviors.md)</span><span class="sxs-lookup"><span data-stu-id="3a10d-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)</span></span>\
<span data-ttu-id="3a10d-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<serviceverhaltens>** ](servicebehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="3a10d-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceBehaviors>**](servicebehaviors.md)</span></span>\
<span data-ttu-id="3a10d-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Verhaltens >** ](behavior-of-servicebehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="3a10d-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-servicebehaviors.md)</span></span>\
<span data-ttu-id="3a10d-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<servicecreden->** ](servicecredentials.md)</span><span class="sxs-lookup"><span data-stu-id="3a10d-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceCredentials>**](servicecredentials.md)</span></span>\
<span data-ttu-id="3a10d-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<Peer >**</span><span class="sxs-lookup"><span data-stu-id="3a10d-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<peer>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3a10d-111">Syntax</span><span class="sxs-lookup"><span data-stu-id="3a10d-111">Syntax</span></span>  
  
```xml  
<peer>
  <certificate />
  <peerAuthentication />
  <messageSenderAuthentication />
</peer>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="3a10d-112">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="3a10d-112">Attributes and Elements</span></span>  
 <span data-ttu-id="3a10d-113">In den folgenden Abschnitten werden Attribute, untergeordnete Elemente sowie übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="3a10d-113">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="3a10d-114">Attribute</span><span class="sxs-lookup"><span data-stu-id="3a10d-114">Attributes</span></span>  
 <span data-ttu-id="3a10d-115">Keine</span><span class="sxs-lookup"><span data-stu-id="3a10d-115">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="3a10d-116">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="3a10d-116">Child Elements</span></span>  
  
|<span data-ttu-id="3a10d-117">Element</span><span class="sxs-lookup"><span data-stu-id="3a10d-117">Element</span></span>|<span data-ttu-id="3a10d-118">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="3a10d-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="3a10d-119">\<certificate></span><span class="sxs-lookup"><span data-stu-id="3a10d-119">\<certificate></span></span>](certificate-of-peer.md)|<span data-ttu-id="3a10d-120">Gibt ein X.509-Zertifikat an, das zum Signieren und Verschlüsseln von Nachrichten für Peer-to-Peer-Dienste verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="3a10d-120">Specifies an X.509 certificate to use for signing and encrypting messages for peer-to-peer services.</span></span> <span data-ttu-id="3a10d-121">.</span><span class="sxs-lookup"><span data-stu-id="3a10d-121">.</span></span>|  
|[<span data-ttu-id="3a10d-122">\<messageSenderAuthentication></span><span class="sxs-lookup"><span data-stu-id="3a10d-122">\<messageSenderAuthentication></span></span>](messagesenderauthentication.md)|<span data-ttu-id="3a10d-123">Gibt die Authentifizierungsoptionen für Nachrichtenabsender an.</span><span class="sxs-lookup"><span data-stu-id="3a10d-123">Specifies authentication options for message senders.</span></span>|  
|[<span data-ttu-id="3a10d-124">\<peerAuthentication></span><span class="sxs-lookup"><span data-stu-id="3a10d-124">\<peerAuthentication></span></span>](peerauthentication.md)|<span data-ttu-id="3a10d-125">Gibt die Authentifizierungsoptionen für Peerdienste an.</span><span class="sxs-lookup"><span data-stu-id="3a10d-125">Specifies authentication options for peer services.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="3a10d-126">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="3a10d-126">Parent Elements</span></span>  
  
|<span data-ttu-id="3a10d-127">Element</span><span class="sxs-lookup"><span data-stu-id="3a10d-127">Element</span></span>|<span data-ttu-id="3a10d-128">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="3a10d-128">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="3a10d-129">\<serviceCredentials></span><span class="sxs-lookup"><span data-stu-id="3a10d-129">\<serviceCredentials></span></span>](servicecredentials.md)|<span data-ttu-id="3a10d-130">Gibt die Anmeldeinformationen an, die für die Authentifizierung des Diensts verwendet werden sollen, sowie die Einstellungen für die Validierung der Clientanmeldeinformationen.</span><span class="sxs-lookup"><span data-stu-id="3a10d-130">Specifies the credential to be used in authenticating the service, and the client credential validation-related settings.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="3a10d-131">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="3a10d-131">See also</span></span>

- <xref:System.ServiceModel.Configuration.PeerCredentialElement>
- <xref:System.ServiceModel.Configuration.ServiceCredentialsElement.Peer%2A>
- <xref:System.ServiceModel.Description.ServiceCredentials.Peer%2A>
- <xref:System.ServiceModel.Security.PeerCredential>
- [<span data-ttu-id="3a10d-132">Peer-to-Peer-Netzwerke</span><span class="sxs-lookup"><span data-stu-id="3a10d-132">Peer-to-Peer Networking</span></span>](../../../wcf/feature-details/peer-to-peer-networking.md)
- <span data-ttu-id="3a10d-133">[Peer Kanalnachrichten-Authentifizierung](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/aa967730(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="3a10d-133">[Peer Channel Message Authentication](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/aa967730(v=vs.90))</span></span>
- <span data-ttu-id="3a10d-134">[Benutzerdefinierte Peer Kanal Authentifizierung](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms751447(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="3a10d-134">[Peer Channel Custom Authentication](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms751447(v=vs.90))</span></span>
- [<span data-ttu-id="3a10d-135">Sichern von Peerkanalanwendungen</span><span class="sxs-lookup"><span data-stu-id="3a10d-135">Securing Peer Channel Applications</span></span>](../../../wcf/feature-details/securing-peer-channel-applications.md)
- [<span data-ttu-id="3a10d-136">Sichern von Diensten und Clients</span><span class="sxs-lookup"><span data-stu-id="3a10d-136">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
