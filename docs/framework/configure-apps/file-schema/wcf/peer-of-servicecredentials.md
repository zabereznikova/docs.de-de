---
title: <peer> von <serviceCredentials>
ms.date: 03/30/2017
ms.assetid: b134e21d-e5b5-458e-9309-626dbf8db4ed
ms.openlocfilehash: ca97be7b1ab562382895fea4f1d1fc716151b70b
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/06/2020
ms.locfileid: "70397646"
---
# <a name="peer-of-servicecredentials"></a><span data-ttu-id="50af1-102">\<peer> von \<serviceCredentials></span><span class="sxs-lookup"><span data-stu-id="50af1-102">\<peer> of \<serviceCredentials></span></span>
<span data-ttu-id="50af1-103">Gibt die aktuellen Anmeldeinformationen für einen Peerknoten an.</span><span class="sxs-lookup"><span data-stu-id="50af1-103">Specifies the current credentials for a peer node.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceBehaviors>**](servicebehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-servicebehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceCredentials>**](servicecredentials.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<peer>**  
  
## <a name="syntax"></a><span data-ttu-id="50af1-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="50af1-104">Syntax</span></span>  
  
```xml  
<peer>
  <certificate />
  <peerAuthentication />
  <messageSenderAuthentication />
</peer>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="50af1-105">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="50af1-105">Attributes and Elements</span></span>  
 <span data-ttu-id="50af1-106">In den folgenden Abschnitten werden Attribute, untergeordnete Elemente sowie übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="50af1-106">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="50af1-107">Attribute</span><span class="sxs-lookup"><span data-stu-id="50af1-107">Attributes</span></span>  
 <span data-ttu-id="50af1-108">Keine</span><span class="sxs-lookup"><span data-stu-id="50af1-108">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="50af1-109">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="50af1-109">Child Elements</span></span>  
  
|<span data-ttu-id="50af1-110">Element</span><span class="sxs-lookup"><span data-stu-id="50af1-110">Element</span></span>|<span data-ttu-id="50af1-111">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="50af1-111">Description</span></span>|  
|-------------|-----------------|  
|[\<certificate>](certificate-of-peer.md)|<span data-ttu-id="50af1-112">Gibt ein X.509-Zertifikat an, das zum Signieren und Verschlüsseln von Nachrichten für Peer-to-Peer-Dienste verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="50af1-112">Specifies an X.509 certificate to use for signing and encrypting messages for peer-to-peer services.</span></span> <span data-ttu-id="50af1-113">.</span><span class="sxs-lookup"><span data-stu-id="50af1-113">.</span></span>|  
|[\<messageSenderAuthentication>](messagesenderauthentication.md)|<span data-ttu-id="50af1-114">Gibt die Authentifizierungsoptionen für Nachrichtenabsender an.</span><span class="sxs-lookup"><span data-stu-id="50af1-114">Specifies authentication options for message senders.</span></span>|  
|[\<peerAuthentication>](peerauthentication.md)|<span data-ttu-id="50af1-115">Gibt die Authentifizierungsoptionen für Peerdienste an.</span><span class="sxs-lookup"><span data-stu-id="50af1-115">Specifies authentication options for peer services.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="50af1-116">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="50af1-116">Parent Elements</span></span>  
  
|<span data-ttu-id="50af1-117">Element</span><span class="sxs-lookup"><span data-stu-id="50af1-117">Element</span></span>|<span data-ttu-id="50af1-118">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="50af1-118">Description</span></span>|  
|-------------|-----------------|  
|[\<serviceCredentials>](servicecredentials.md)|<span data-ttu-id="50af1-119">Gibt die Anmeldeinformationen an, die für die Authentifizierung des Diensts verwendet werden sollen, sowie die Einstellungen für die Validierung der Clientanmeldeinformationen.</span><span class="sxs-lookup"><span data-stu-id="50af1-119">Specifies the credential to be used in authenticating the service, and the client credential validation-related settings.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="50af1-120">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="50af1-120">See also</span></span>

- <xref:System.ServiceModel.Configuration.PeerCredentialElement>
- <xref:System.ServiceModel.Configuration.ServiceCredentialsElement.Peer%2A>
- <xref:System.ServiceModel.Description.ServiceCredentials.Peer%2A>
- <xref:System.ServiceModel.Security.PeerCredential>
- [<span data-ttu-id="50af1-121">Peer-to-Peer-Netzwerke</span><span class="sxs-lookup"><span data-stu-id="50af1-121">Peer-to-Peer Networking</span></span>](../../../wcf/feature-details/peer-to-peer-networking.md)
- <span data-ttu-id="50af1-122">[Peerkanal-Nachrichtenauthentifizierung](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/aa967730(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="50af1-122">[Peer Channel Message Authentication](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/aa967730(v=vs.90))</span></span>
- <span data-ttu-id="50af1-123">[Benutzerdefinierte Peerkanal-Authentifizierung](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms751447(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="50af1-123">[Peer Channel Custom Authentication](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms751447(v=vs.90))</span></span>
- [<span data-ttu-id="50af1-124">Sichern von Peerkanalanwendungen</span><span class="sxs-lookup"><span data-stu-id="50af1-124">Securing Peer Channel Applications</span></span>](../../../wcf/feature-details/securing-peer-channel-applications.md)
- [<span data-ttu-id="50af1-125">Sichern von Diensten und Clients</span><span class="sxs-lookup"><span data-stu-id="50af1-125">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
