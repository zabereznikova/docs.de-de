---
title: <transport> von <netPeerTcpBinding>
ms.date: 03/30/2017
ms.assetid: c44d86d2-1160-44d7-9c7a-297b12eccc7f
ms.openlocfilehash: 5df47b1bfc149b524fc9b90eacffa832817f653c
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91172865"
---
# <a name="transport-of-netpeertcpbinding"></a><span data-ttu-id="34241-102">\<transport> von \<netPeerTcpBinding></span><span class="sxs-lookup"><span data-stu-id="34241-102">\<transport> of \<netPeerTcpBinding></span></span>

<span data-ttu-id="34241-103">Gibt Einstellungen für die Sicherheit auf Transport Ebene an, wenn verwendet wird [\<netPeerTcpBinding>](netpeertcpbinding.md) .</span><span class="sxs-lookup"><span data-stu-id="34241-103">Specifies settings for transport level security when using the [\<netPeerTcpBinding>](netpeertcpbinding.md).</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<netPeerTcpBinding>**](netpeertcpbinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<security>**](security-of-netpeerbinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<transport>**  
  
## <a name="syntax"></a><span data-ttu-id="34241-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="34241-104">Syntax</span></span>  
  
```xml  
<netPeerTcpBinding>
  <binding>
    <security>
      <transport credentialType="Certificate/Password" />
    </security>
  </binding>
</netPeerTcpBinding>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="34241-105">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="34241-105">Attributes and Elements</span></span>  

 <span data-ttu-id="34241-106">In den folgenden Abschnitten werden Attribute, untergeordnete Elemente sowie übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="34241-106">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="34241-107">Attributes</span><span class="sxs-lookup"><span data-stu-id="34241-107">Attributes</span></span>  
  
|<span data-ttu-id="34241-108">attribute</span><span class="sxs-lookup"><span data-stu-id="34241-108">Attribute</span></span>|<span data-ttu-id="34241-109">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="34241-109">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="34241-110">credentialType</span><span class="sxs-lookup"><span data-stu-id="34241-110">credentialType</span></span>|<span data-ttu-id="34241-111">Dies ist optional.</span><span class="sxs-lookup"><span data-stu-id="34241-111">Optional.</span></span> <span data-ttu-id="34241-112">Gibt den Typ von Anmeldeinformationen an, die zum Überprüfen von über den Peertransport gesendeten Nachrichten verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="34241-112">Specifies the type of credentials used to verify messages sent with the peer transport.</span></span> <span data-ttu-id="34241-113">Dieses Attribut ist vom Typ <xref:System.ServiceModel.PeerTransportCredentialType>.</span><span class="sxs-lookup"><span data-stu-id="34241-113">This attribute is of type <xref:System.ServiceModel.PeerTransportCredentialType>.</span></span>|  
  
## <a name="credentialtype-attribute"></a><span data-ttu-id="34241-114">credentialType-Attribut</span><span class="sxs-lookup"><span data-stu-id="34241-114">credentialType Attribute</span></span>  
  
|<span data-ttu-id="34241-115">Wert</span><span class="sxs-lookup"><span data-stu-id="34241-115">Value</span></span>|<span data-ttu-id="34241-116">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="34241-116">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="34241-117">Zertifikat</span><span class="sxs-lookup"><span data-stu-id="34241-117">Certificate</span></span>|<span data-ttu-id="34241-118">Zur Authentifizierung des Peerkanaltransports ist ein X509-Zertifikat erforderlich.</span><span class="sxs-lookup"><span data-stu-id="34241-118">Authentication of the peer channel transport requires an X509 certificate.</span></span>|  
|<span data-ttu-id="34241-119">Kennwort</span><span class="sxs-lookup"><span data-stu-id="34241-119">Password</span></span>|<span data-ttu-id="34241-120">Zur Authentifizierung des Peerkanaltransports ist ein korrektes Kennwort erforderlich.</span><span class="sxs-lookup"><span data-stu-id="34241-120">Authentication of the peer channel transport requires a correct password.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="34241-121">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="34241-121">Child Elements</span></span>  

 <span data-ttu-id="34241-122">Keine</span><span class="sxs-lookup"><span data-stu-id="34241-122">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="34241-123">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="34241-123">Parent Elements</span></span>  
  
|<span data-ttu-id="34241-124">Element</span><span class="sxs-lookup"><span data-stu-id="34241-124">Element</span></span>|<span data-ttu-id="34241-125">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="34241-125">Description</span></span>|  
|-------------|-----------------|  
|[\<security>](security-of-netpeerbinding.md)|<span data-ttu-id="34241-126">Definiert die Sicherheitseinstellungen für [\<netPeerTcpBinding>](netpeertcpbinding.md) .</span><span class="sxs-lookup"><span data-stu-id="34241-126">Defines the security settings for the [\<netPeerTcpBinding>](netpeertcpbinding.md).</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="34241-127">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="34241-127">See also</span></span>

- <xref:System.ServiceModel.Configuration.PeerTransportSecurityElement>
- <xref:System.ServiceModel.PeerSecuritySettings.Transport%2A>
- <xref:System.ServiceModel.Configuration.PeerSecurityElement.Transport%2A>
- <xref:System.ServiceModel.PeerTransportSecuritySettings>
- [<span data-ttu-id="34241-128">Sichern von Diensten und Clients</span><span class="sxs-lookup"><span data-stu-id="34241-128">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="34241-129">Bindungen</span><span class="sxs-lookup"><span data-stu-id="34241-129">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="34241-130">Konfigurieren der vom System bereitgestellten Bindungen</span><span class="sxs-lookup"><span data-stu-id="34241-130">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="34241-131">Verwenden von Bindungen, um Dienste und Clients zu konfigurieren</span><span class="sxs-lookup"><span data-stu-id="34241-131">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [\<binding>](bindings.md)
