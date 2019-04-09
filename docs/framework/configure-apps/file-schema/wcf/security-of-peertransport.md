---
title: <security> von <peerTransport>
ms.date: 03/30/2017
ms.assetid: f73634ed-f896-4968-bf74-5e5ac52d3b6b
ms.openlocfilehash: 1aff79bf5867a3a1ebe05e3f812475dac4b413e9
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59116858"
---
# <a name="security-of-peertransport"></a><span data-ttu-id="fe4af-102">\<Security > von \<PeerTransport ></span><span class="sxs-lookup"><span data-stu-id="fe4af-102">\<security> of \<peerTransport></span></span>
<span data-ttu-id="fe4af-103">Enthält die einem Peerkanal zugeordneten Sicherheitseinstellungen, einschließlich für den Nachrichtentransport verwendeter Authentifizierungstyp und verwendete Sicherheit.</span><span class="sxs-lookup"><span data-stu-id="fe4af-103">Contains the security settings associated with a peer channel, including the type of authentication used and the security used for the message transport.</span></span>  
  
 <span data-ttu-id="fe4af-104">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="fe4af-104">\<system.serviceModel></span></span>  
<span data-ttu-id="fe4af-105">\<bindings></span><span class="sxs-lookup"><span data-stu-id="fe4af-105">\<bindings></span></span>  
<span data-ttu-id="fe4af-106">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="fe4af-106">\<customBinding></span></span>  
<span data-ttu-id="fe4af-107">\<binding></span><span class="sxs-lookup"><span data-stu-id="fe4af-107">\<binding></span></span>  
<span data-ttu-id="fe4af-108">\<peerTransport></span><span class="sxs-lookup"><span data-stu-id="fe4af-108">\<peerTransport></span></span>  
<span data-ttu-id="fe4af-109">\<security></span><span class="sxs-lookup"><span data-stu-id="fe4af-109">\<security></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fe4af-110">Syntax</span><span class="sxs-lookup"><span data-stu-id="fe4af-110">Syntax</span></span>  
  
```xml  
<security mode="None/Transport/Message/TransportWithMessageCredential">
  <transport clientCredentialType="None/Windows/UserName/Certificate/CardSpace" />
</security
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="fe4af-111">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="fe4af-111">Attributes and Elements</span></span>  
 <span data-ttu-id="fe4af-112">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="fe4af-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="fe4af-113">Attribute</span><span class="sxs-lookup"><span data-stu-id="fe4af-113">Attributes</span></span>  
  
|<span data-ttu-id="fe4af-114">Attribut</span><span class="sxs-lookup"><span data-stu-id="fe4af-114">Attribute</span></span>|<span data-ttu-id="fe4af-115">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="fe4af-115">Description</span></span>|  
|---------------|-----------------|  
|`mode`|<span data-ttu-id="fe4af-116">Gibt den Typ der anzuwendenden Sicherheit an.</span><span class="sxs-lookup"><span data-stu-id="fe4af-116">Specifies the type of security to be applied.</span></span> <span data-ttu-id="fe4af-117">Der Standardwert ist Nachricht.</span><span class="sxs-lookup"><span data-stu-id="fe4af-117">The default value is Message.</span></span> <span data-ttu-id="fe4af-118">Dieses Attribut ist vom Typ <xref:System.ServiceModel.SecurityMode>.</span><span class="sxs-lookup"><span data-stu-id="fe4af-118">This attribute is of type <xref:System.ServiceModel.SecurityMode>.</span></span>|  
  
## <a name="mode-attribute"></a><span data-ttu-id="fe4af-119">mode-Attribut</span><span class="sxs-lookup"><span data-stu-id="fe4af-119">mode Attribute</span></span>  
  
|<span data-ttu-id="fe4af-120">Wert</span><span class="sxs-lookup"><span data-stu-id="fe4af-120">Value</span></span>|<span data-ttu-id="fe4af-121">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="fe4af-121">Description</span></span>|  
|-----------|-----------------|  
|`None`|<span data-ttu-id="fe4af-122">Die Sicherheitsfunktionen sind deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="fe4af-122">Security is disabled.</span></span>|  
|`Transport`|<span data-ttu-id="fe4af-123">Die Sicherheit wird über HTTPS bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="fe4af-123">Security is provided using HTTPS.</span></span>|  
|`Message`|<span data-ttu-id="fe4af-124">Durch die SOAP-Sicherheit werden Authentifizierung, Integrität und Vertraulichkeit bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="fe4af-124">SOAP security provides authentication, integrity and confidentiality.</span></span>|  
|`TransportWithMessageCredential`|<span data-ttu-id="fe4af-125">HTTPS stellt Authentifizierung und Vertraulichkeit bereit.</span><span class="sxs-lookup"><span data-stu-id="fe4af-125">HTTPS provides authentication and confidentiality.</span></span> <span data-ttu-id="fe4af-126">Die SOAP-Nachrichten bieten umfassende Anmeldeinformationstypen.</span><span class="sxs-lookup"><span data-stu-id="fe4af-126">SOAP messages provide rich credential types.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="fe4af-127">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="fe4af-127">Child Elements</span></span>  
  
|<span data-ttu-id="fe4af-128">Element</span><span class="sxs-lookup"><span data-stu-id="fe4af-128">Element</span></span>|<span data-ttu-id="fe4af-129">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="fe4af-129">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="fe4af-130">\<transport></span><span class="sxs-lookup"><span data-stu-id="fe4af-130">\<transport></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/transport-of-peertransport.md)|<span data-ttu-id="fe4af-131">Definiert einen Peertransport für eine benutzerdefinierte Bindung.</span><span class="sxs-lookup"><span data-stu-id="fe4af-131">Defines a peer transport for a custom binding.</span></span> <span data-ttu-id="fe4af-132">Dieses Element enthält ein `clientCredentialType`-Attribut, das die für die Interaktion mit einem Dienst zu verwendenden Anmeldeinformationen angibt.</span><span class="sxs-lookup"><span data-stu-id="fe4af-132">This element has a `clientCredentialType` attribute that specifies the credentials to be used when interacting with a service.</span></span> <span data-ttu-id="fe4af-133">Dieses Attribut ist vom Typ <xref:System.ServiceModel.PeerTransportCredentialType>.</span><span class="sxs-lookup"><span data-stu-id="fe4af-133">This attribute is of type <xref:System.ServiceModel.PeerTransportCredentialType>.</span></span><br /><br /> <span data-ttu-id="fe4af-134">Dieses Element ist vom Typ <xref:System.ServiceModel.Configuration.PeerTransportSecurityElement>.</span><span class="sxs-lookup"><span data-stu-id="fe4af-134">This element is of type <xref:System.ServiceModel.Configuration.PeerTransportSecurityElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="fe4af-135">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="fe4af-135">Parent Elements</span></span>  
  
|<span data-ttu-id="fe4af-136">Element</span><span class="sxs-lookup"><span data-stu-id="fe4af-136">Element</span></span>|<span data-ttu-id="fe4af-137">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="fe4af-137">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="fe4af-138">\<peerTransport></span><span class="sxs-lookup"><span data-stu-id="fe4af-138">\<peerTransport></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/peertransport.md)|<span data-ttu-id="fe4af-139">Definiert einen Peertransport für eine benutzerdefinierte Bindung.</span><span class="sxs-lookup"><span data-stu-id="fe4af-139">Defines a peer transport for a custom binding.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="fe4af-140">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="fe4af-140">See also</span></span>

- <xref:System.ServiceModel.Configuration.PeerSecurityElement>
- <xref:System.ServiceModel.PeerSecuritySettings>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [<span data-ttu-id="fe4af-141">Transportsicherheit</span><span class="sxs-lookup"><span data-stu-id="fe4af-141">Transport Security</span></span>](../../../../../docs/framework/wcf/feature-details/transport-security.md)
- [<span data-ttu-id="fe4af-142">Transportprotokolle</span><span class="sxs-lookup"><span data-stu-id="fe4af-142">Transports</span></span>](../../../../../docs/framework/wcf/feature-details/transports.md)
- [<span data-ttu-id="fe4af-143">Wählen eines Transports</span><span class="sxs-lookup"><span data-stu-id="fe4af-143">Choosing a Transport</span></span>](../../../../../docs/framework/wcf/feature-details/choosing-a-transport.md)
- [<span data-ttu-id="fe4af-144">Bindungen</span><span class="sxs-lookup"><span data-stu-id="fe4af-144">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)
- [<span data-ttu-id="fe4af-145">Erweitern von Bindungen</span><span class="sxs-lookup"><span data-stu-id="fe4af-145">Extending Bindings</span></span>](../../../../../docs/framework/wcf/extending/extending-bindings.md)
- [<span data-ttu-id="fe4af-146">Benutzerdefinierte Bindungen</span><span class="sxs-lookup"><span data-stu-id="fe4af-146">Custom Bindings</span></span>](../../../../../docs/framework/wcf/extending/custom-bindings.md)
- [<span data-ttu-id="fe4af-147">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="fe4af-147">\<customBinding></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)
