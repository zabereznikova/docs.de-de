---
title: <peer>of- <clientCredentials> Element
ms.date: 03/30/2017
ms.assetid: 505bd987-0042-4622-b68e-94f439729d53
ms.openlocfilehash: dce7ef64de1e3eb248e3553c97cbce8e9b205b4c
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/06/2020
ms.locfileid: "70400095"
---
# <a name="peer-of-clientcredentials-element"></a><span data-ttu-id="c60bb-102">\<peer>of- \<clientCredentials> Element</span><span class="sxs-lookup"><span data-stu-id="c60bb-102">\<peer> of \<clientCredentials> Element</span></span>
<span data-ttu-id="c60bb-103">Gibt Anmeldeinformationen an, die bei der Authentifizierung von Peer-to-Peer-Clients verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="c60bb-103">Specifies credentials used when authenticating peer-to-peer clients.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpointBehaviors>**](endpointbehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-endpointbehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<clientCredentials>**](clientcredentials.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<peer>**  
  
## <a name="syntax"></a><span data-ttu-id="c60bb-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="c60bb-104">Syntax</span></span>  
  
```xml  
<peer>
  <certificate />
  <peerAuthentication />
  <messageSenderAuthentication />
</peer>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="c60bb-105">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="c60bb-105">Attributes and Elements</span></span>  
 <span data-ttu-id="c60bb-106">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="c60bb-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="c60bb-107">Attribute</span><span class="sxs-lookup"><span data-stu-id="c60bb-107">Attributes</span></span>  
 <span data-ttu-id="c60bb-108">Keine</span><span class="sxs-lookup"><span data-stu-id="c60bb-108">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="c60bb-109">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="c60bb-109">Child Elements</span></span>  
  
|<span data-ttu-id="c60bb-110">Element</span><span class="sxs-lookup"><span data-stu-id="c60bb-110">Element</span></span>|<span data-ttu-id="c60bb-111">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="c60bb-111">Description</span></span>|  
|-------------|-----------------|  
|[\<certificate>](certificate-element.md)|<span data-ttu-id="c60bb-112">Gibt ein X.509-Zertifikat an, das zum Signieren und Verschlüsseln von Nachrichten für Peer-to-Peer-Clients verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="c60bb-112">Specifies an X.509 certificate to use for signing and encrypting messages for peer-to-peer clients.</span></span> <span data-ttu-id="c60bb-113">.</span><span class="sxs-lookup"><span data-stu-id="c60bb-113">.</span></span>|  
|[\<peerAuthentication>](peerauthentication-element.md)|<span data-ttu-id="c60bb-114">Gibt die Authentifizierungsoptionen für Peer-Clients an.</span><span class="sxs-lookup"><span data-stu-id="c60bb-114">Specifies authentication options for peer clients.</span></span>|  
|[\<messageSenderAuthentication>](messagesenderauthentication-element.md)|<span data-ttu-id="c60bb-115">Gibt die Authentifizierungsoptionen für Nachrichtenabsender an.</span><span class="sxs-lookup"><span data-stu-id="c60bb-115">Specifies authentication options for message senders.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="c60bb-116">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="c60bb-116">Parent Elements</span></span>  
  
|<span data-ttu-id="c60bb-117">Element</span><span class="sxs-lookup"><span data-stu-id="c60bb-117">Element</span></span>|<span data-ttu-id="c60bb-118">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="c60bb-118">Description</span></span>|  
|-------------|-----------------|  
|[\<clientCredentials>](clientcredentials.md)|<span data-ttu-id="c60bb-119">Gibt die zum Authentifizieren des Clients beim Dienst verwendeten Anmeldeinformationen an.</span><span class="sxs-lookup"><span data-stu-id="c60bb-119">Specifies the credentials used to authenticate a client to a service.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c60bb-120">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="c60bb-120">Remarks</span></span>  
 <span data-ttu-id="c60bb-121">Dieses Konfigurationselement gibt die Anmeldeinformationen an, mit denen sich ein Peerknoten gegenüber anderen Knoten im Netz authentifiziert, sowie die Authentifizierungseinstellungen, mit denen ein Peerknoten andere Peerknoten authentifiziert.</span><span class="sxs-lookup"><span data-stu-id="c60bb-121">This configuration element specifies the credentials that a peer node uses to authenticate itself to other nodes in the mesh, as well as authentication settings that a peer node uses to authenticate other peer nodes.</span></span> <span data-ttu-id="c60bb-122">Weitere Informationen finden Sie unter [Peer Channel Message Authentication](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/aa967730(v=vs.90)) und [Sichern von Peer Kanal Anwendungen](../../../wcf/feature-details/securing-peer-channel-applications.md).</span><span class="sxs-lookup"><span data-stu-id="c60bb-122">For more information, see [Peer Channel Message Authentication](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/aa967730(v=vs.90)) and [Securing Peer Channel Applications](../../../wcf/feature-details/securing-peer-channel-applications.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c60bb-123">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="c60bb-123">See also</span></span>

- <xref:System.ServiceModel.Configuration.ClientCredentialsElement>
- <xref:System.ServiceModel.Description.ClientCredentials>
- <xref:System.ServiceModel.Configuration.PeerCredentialElement>
- <xref:System.ServiceModel.Configuration.ClientCredentialsElement.Peer%2A>
- <xref:System.ServiceModel.Description.ClientCredentials>
- <xref:System.ServiceModel.Description.ClientCredentials.Peer%2A>
- <xref:System.ServiceModel.Security.PeerCredential>
- [<span data-ttu-id="c60bb-124">Peer-to-Peer-Netzwerke</span><span class="sxs-lookup"><span data-stu-id="c60bb-124">Peer-to-Peer Networking</span></span>](../../../wcf/feature-details/peer-to-peer-networking.md)
- [<span data-ttu-id="c60bb-125">Sichern von Clients</span><span class="sxs-lookup"><span data-stu-id="c60bb-125">Securing Clients</span></span>](../../../wcf/securing-clients.md)
- <span data-ttu-id="c60bb-126">[Peerkanal-Nachrichtenauthentifizierung](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/aa967730(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="c60bb-126">[Peer Channel Message Authentication](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/aa967730(v=vs.90))</span></span>
- <span data-ttu-id="c60bb-127">[Benutzerdefinierte Peerkanal-Authentifizierung](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms751447(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="c60bb-127">[Peer Channel Custom Authentication](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms751447(v=vs.90))</span></span>
- [<span data-ttu-id="c60bb-128">Sichern von Peerkanalanwendungen</span><span class="sxs-lookup"><span data-stu-id="c60bb-128">Securing Peer Channel Applications</span></span>](../../../wcf/feature-details/securing-peer-channel-applications.md)
- [<span data-ttu-id="c60bb-129">Sichern von Diensten und Clients</span><span class="sxs-lookup"><span data-stu-id="c60bb-129">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
