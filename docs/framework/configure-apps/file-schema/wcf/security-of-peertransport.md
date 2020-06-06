---
title: <security> von <peerTransport>
ms.date: 03/30/2017
ms.assetid: f73634ed-f896-4968-bf74-5e5ac52d3b6b
ms.openlocfilehash: 270ca844f586be256b6483653c868d1cc4396657
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/06/2020
ms.locfileid: "70399764"
---
# <a name="security-of-peertransport"></a><span data-ttu-id="29138-102">\<security> von \<peerTransport></span><span class="sxs-lookup"><span data-stu-id="29138-102">\<security> of \<peerTransport></span></span>
<span data-ttu-id="29138-103">Enthält die einem Peerkanal zugeordneten Sicherheitseinstellungen, einschließlich für den Nachrichtentransport verwendeter Authentifizierungstyp und verwendete Sicherheit.</span><span class="sxs-lookup"><span data-stu-id="29138-103">Contains the security settings associated with a peer channel, including the type of authentication used and the security used for the message transport.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<customBinding>**](custombinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<peerTransport>**](peertransport.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<security>**  
  
## <a name="syntax"></a><span data-ttu-id="29138-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="29138-104">Syntax</span></span>  
  
```xml  
<security mode="None/Transport/Message/TransportWithMessageCredential">
  <transport clientCredentialType="None/Windows/UserName/Certificate/CardSpace" />
</security
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="29138-105">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="29138-105">Attributes and Elements</span></span>  
 <span data-ttu-id="29138-106">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="29138-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="29138-107">Attribute</span><span class="sxs-lookup"><span data-stu-id="29138-107">Attributes</span></span>  
  
|<span data-ttu-id="29138-108">attribute</span><span class="sxs-lookup"><span data-stu-id="29138-108">Attribute</span></span>|<span data-ttu-id="29138-109">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="29138-109">Description</span></span>|  
|---------------|-----------------|  
|`mode`|<span data-ttu-id="29138-110">Gibt den Typ der anzuwendenden Sicherheit an.</span><span class="sxs-lookup"><span data-stu-id="29138-110">Specifies the type of security to be applied.</span></span> <span data-ttu-id="29138-111">Der Standardwert ist Nachricht.</span><span class="sxs-lookup"><span data-stu-id="29138-111">The default value is Message.</span></span> <span data-ttu-id="29138-112">Dieses Attribut ist vom Typ <xref:System.ServiceModel.SecurityMode>.</span><span class="sxs-lookup"><span data-stu-id="29138-112">This attribute is of type <xref:System.ServiceModel.SecurityMode>.</span></span>|  
  
## <a name="mode-attribute"></a><span data-ttu-id="29138-113">mode-Attribut</span><span class="sxs-lookup"><span data-stu-id="29138-113">mode Attribute</span></span>  
  
|<span data-ttu-id="29138-114">Wert</span><span class="sxs-lookup"><span data-stu-id="29138-114">Value</span></span>|<span data-ttu-id="29138-115">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="29138-115">Description</span></span>|  
|-----------|-----------------|  
|`None`|<span data-ttu-id="29138-116">Die Sicherheitsfunktionen sind deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="29138-116">Security is disabled.</span></span>|  
|`Transport`|<span data-ttu-id="29138-117">Die Sicherheit wird über HTTPS bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="29138-117">Security is provided using HTTPS.</span></span>|  
|`Message`|<span data-ttu-id="29138-118">Durch die SOAP-Sicherheit werden Authentifizierung, Integrität und Vertraulichkeit bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="29138-118">SOAP security provides authentication, integrity and confidentiality.</span></span>|  
|`TransportWithMessageCredential`|<span data-ttu-id="29138-119">HTTPS stellt Authentifizierung und Vertraulichkeit bereit.</span><span class="sxs-lookup"><span data-stu-id="29138-119">HTTPS provides authentication and confidentiality.</span></span> <span data-ttu-id="29138-120">Die SOAP-Nachrichten bieten umfassende Anmeldeinformationstypen.</span><span class="sxs-lookup"><span data-stu-id="29138-120">SOAP messages provide rich credential types.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="29138-121">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="29138-121">Child Elements</span></span>  
  
|<span data-ttu-id="29138-122">Element</span><span class="sxs-lookup"><span data-stu-id="29138-122">Element</span></span>|<span data-ttu-id="29138-123">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="29138-123">Description</span></span>|  
|-------------|-----------------|  
|[\<transport>](transport-of-peertransport.md)|<span data-ttu-id="29138-124">Definiert einen Peertransport für eine benutzerdefinierte Bindung.</span><span class="sxs-lookup"><span data-stu-id="29138-124">Defines a peer transport for a custom binding.</span></span> <span data-ttu-id="29138-125">Dieses Element enthält ein `clientCredentialType`-Attribut, das die für die Interaktion mit einem Dienst zu verwendenden Anmeldeinformationen angibt.</span><span class="sxs-lookup"><span data-stu-id="29138-125">This element has a `clientCredentialType` attribute that specifies the credentials to be used when interacting with a service.</span></span> <span data-ttu-id="29138-126">Dieses Attribut ist vom Typ <xref:System.ServiceModel.PeerTransportCredentialType>.</span><span class="sxs-lookup"><span data-stu-id="29138-126">This attribute is of type <xref:System.ServiceModel.PeerTransportCredentialType>.</span></span><br /><br /> <span data-ttu-id="29138-127">Dieses Element ist vom Typ <xref:System.ServiceModel.Configuration.PeerTransportSecurityElement>.</span><span class="sxs-lookup"><span data-stu-id="29138-127">This element is of type <xref:System.ServiceModel.Configuration.PeerTransportSecurityElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="29138-128">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="29138-128">Parent Elements</span></span>  
  
|<span data-ttu-id="29138-129">Element</span><span class="sxs-lookup"><span data-stu-id="29138-129">Element</span></span>|<span data-ttu-id="29138-130">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="29138-130">Description</span></span>|  
|-------------|-----------------|  
|[\<peerTransport>](peertransport.md)|<span data-ttu-id="29138-131">Definiert einen Peertransport für eine benutzerdefinierte Bindung.</span><span class="sxs-lookup"><span data-stu-id="29138-131">Defines a peer transport for a custom binding.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="29138-132">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="29138-132">See also</span></span>

- <xref:System.ServiceModel.Configuration.PeerSecurityElement>
- <xref:System.ServiceModel.PeerSecuritySettings>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [<span data-ttu-id="29138-133">Transport Sicherheit</span><span class="sxs-lookup"><span data-stu-id="29138-133">Transport Security</span></span>](../../../wcf/feature-details/transport-security.md)
- [<span data-ttu-id="29138-134">Transportprotokolle</span><span class="sxs-lookup"><span data-stu-id="29138-134">Transports</span></span>](../../../wcf/feature-details/transports.md)
- [<span data-ttu-id="29138-135">Wählen eines Transports</span><span class="sxs-lookup"><span data-stu-id="29138-135">Choosing a Transport</span></span>](../../../wcf/feature-details/choosing-a-transport.md)
- [<span data-ttu-id="29138-136">Bindungen</span><span class="sxs-lookup"><span data-stu-id="29138-136">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="29138-137">Erweitern von Bindungen</span><span class="sxs-lookup"><span data-stu-id="29138-137">Extending Bindings</span></span>](../../../wcf/extending/extending-bindings.md)
- [<span data-ttu-id="29138-138">Benutzerdefinierte Bindungen</span><span class="sxs-lookup"><span data-stu-id="29138-138">Custom Bindings</span></span>](../../../wcf/extending/custom-bindings.md)
- [\<customBinding>](custombinding.md)
