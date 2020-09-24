---
title: <peer> von <serviceCredentials>
ms.date: 03/30/2017
ms.assetid: b134e21d-e5b5-458e-9309-626dbf8db4ed
ms.openlocfilehash: 7f6669d3f53a6ee0d189786fa9ca3625fdedd127
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91162477"
---
# <a name="peer-of-servicecredentials"></a><span data-ttu-id="597ef-102">\<peer> von \<serviceCredentials></span><span class="sxs-lookup"><span data-stu-id="597ef-102">\<peer> of \<serviceCredentials></span></span>

<span data-ttu-id="597ef-103">Gibt die aktuellen Anmeldeinformationen für einen Peerknoten an.</span><span class="sxs-lookup"><span data-stu-id="597ef-103">Specifies the current credentials for a peer node.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceBehaviors>**](servicebehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-servicebehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceCredentials>**](servicecredentials.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<peer>**  
  
## <a name="syntax"></a><span data-ttu-id="597ef-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="597ef-104">Syntax</span></span>  
  
```xml  
<peer>
  <certificate />
  <peerAuthentication />
  <messageSenderAuthentication />
</peer>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="597ef-105">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="597ef-105">Attributes and Elements</span></span>  

 <span data-ttu-id="597ef-106">In den folgenden Abschnitten werden Attribute, untergeordnete Elemente sowie übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="597ef-106">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="597ef-107">Attribute</span><span class="sxs-lookup"><span data-stu-id="597ef-107">Attributes</span></span>  

 <span data-ttu-id="597ef-108">Keine</span><span class="sxs-lookup"><span data-stu-id="597ef-108">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="597ef-109">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="597ef-109">Child Elements</span></span>  
  
|<span data-ttu-id="597ef-110">Element</span><span class="sxs-lookup"><span data-stu-id="597ef-110">Element</span></span>|<span data-ttu-id="597ef-111">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="597ef-111">Description</span></span>|  
|-------------|-----------------|  
|[\<certificate>](certificate-of-peer.md)|<span data-ttu-id="597ef-112">Gibt ein X.509-Zertifikat an, das zum Signieren und Verschlüsseln von Nachrichten für Peer-to-Peer-Dienste verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="597ef-112">Specifies an X.509 certificate to use for signing and encrypting messages for peer-to-peer services.</span></span> <span data-ttu-id="597ef-113">.</span><span class="sxs-lookup"><span data-stu-id="597ef-113">.</span></span>|  
|[\<messageSenderAuthentication>](messagesenderauthentication.md)|<span data-ttu-id="597ef-114">Gibt die Authentifizierungsoptionen für Nachrichtenabsender an.</span><span class="sxs-lookup"><span data-stu-id="597ef-114">Specifies authentication options for message senders.</span></span>|  
|[\<peerAuthentication>](peerauthentication.md)|<span data-ttu-id="597ef-115">Gibt die Authentifizierungsoptionen für Peerdienste an.</span><span class="sxs-lookup"><span data-stu-id="597ef-115">Specifies authentication options for peer services.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="597ef-116">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="597ef-116">Parent Elements</span></span>  
  
|<span data-ttu-id="597ef-117">Element</span><span class="sxs-lookup"><span data-stu-id="597ef-117">Element</span></span>|<span data-ttu-id="597ef-118">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="597ef-118">Description</span></span>|  
|-------------|-----------------|  
|[\<serviceCredentials>](servicecredentials.md)|<span data-ttu-id="597ef-119">Gibt die Anmeldeinformationen an, die für die Authentifizierung des Diensts verwendet werden sollen, sowie die Einstellungen für die Validierung der Clientanmeldeinformationen.</span><span class="sxs-lookup"><span data-stu-id="597ef-119">Specifies the credential to be used in authenticating the service, and the client credential validation-related settings.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="597ef-120">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="597ef-120">See also</span></span>

- <xref:System.ServiceModel.Configuration.PeerCredentialElement>
- <xref:System.ServiceModel.Configuration.ServiceCredentialsElement.Peer%2A>
- <xref:System.ServiceModel.Description.ServiceCredentials.Peer%2A>
- <xref:System.ServiceModel.Security.PeerCredential>
- [<span data-ttu-id="597ef-121">Peer-to-Peer-Netzwerke</span><span class="sxs-lookup"><span data-stu-id="597ef-121">Peer-to-Peer Networking</span></span>](../../../wcf/feature-details/peer-to-peer-networking.md)
- <span data-ttu-id="597ef-122">[Peerkanal-Nachrichtenauthentifizierung](/previous-versions/dotnet/netframework-3.5/aa967730(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="597ef-122">[Peer Channel Message Authentication](/previous-versions/dotnet/netframework-3.5/aa967730(v=vs.90))</span></span>
- <span data-ttu-id="597ef-123">[Benutzerdefinierte Peerkanal-Authentifizierung](/previous-versions/dotnet/netframework-3.5/ms751447(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="597ef-123">[Peer Channel Custom Authentication](/previous-versions/dotnet/netframework-3.5/ms751447(v=vs.90))</span></span>
- [<span data-ttu-id="597ef-124">Sichern von Peerkanalanwendungen</span><span class="sxs-lookup"><span data-stu-id="597ef-124">Securing Peer Channel Applications</span></span>](../../../wcf/feature-details/securing-peer-channel-applications.md)
- [<span data-ttu-id="597ef-125">Sichern von Diensten und Clients</span><span class="sxs-lookup"><span data-stu-id="597ef-125">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
