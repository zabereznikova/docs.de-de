---
title: '&lt;security&gt; von &lt;peerTransport&gt;'
ms.date: 03/30/2017
ms.assetid: f73634ed-f896-4968-bf74-5e5ac52d3b6b
ms.openlocfilehash: 901a1d0b29fa6ea7d9e520b379dc7c7ff1d1e522
ms.sourcegitcommit: 4ac80713f6faa220e5a119d5165308a58f7ccdc8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/09/2019
ms.locfileid: "54151955"
---
# <a name="ltsecuritygt-of-ltpeertransportgt"></a><span data-ttu-id="afaa8-102">&lt;security&gt; von &lt;peerTransport&gt;</span><span class="sxs-lookup"><span data-stu-id="afaa8-102">&lt;security&gt; of &lt;peerTransport&gt;</span></span>
<span data-ttu-id="afaa8-103">Enthält die einem Peerkanal zugeordneten Sicherheitseinstellungen, einschließlich für den Nachrichtentransport verwendeter Authentifizierungstyp und verwendete Sicherheit.</span><span class="sxs-lookup"><span data-stu-id="afaa8-103">Contains the security settings associated with a peer channel, including the type of authentication used and the security used for the message transport.</span></span>  
  
 <span data-ttu-id="afaa8-104">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="afaa8-104">\<system.serviceModel></span></span>  
<span data-ttu-id="afaa8-105">\<bindings></span><span class="sxs-lookup"><span data-stu-id="afaa8-105">\<bindings></span></span>  
<span data-ttu-id="afaa8-106">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="afaa8-106">\<customBinding></span></span>  
<span data-ttu-id="afaa8-107">\<binding></span><span class="sxs-lookup"><span data-stu-id="afaa8-107">\<binding></span></span>  
<span data-ttu-id="afaa8-108">\<PeerTransport ></span><span class="sxs-lookup"><span data-stu-id="afaa8-108">\<peerTransport></span></span>  
<span data-ttu-id="afaa8-109">\<Sicherheit ></span><span class="sxs-lookup"><span data-stu-id="afaa8-109">\<security></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="afaa8-110">Syntax</span><span class="sxs-lookup"><span data-stu-id="afaa8-110">Syntax</span></span>  
  
```xml  
<security mode="None/Transport/Message/TransportWithMessageCredential">
  <transport clientCredentialType="None/Windows/UserName/Certificate/CardSpace" />
</security
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="afaa8-111">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="afaa8-111">Attributes and Elements</span></span>  
 <span data-ttu-id="afaa8-112">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="afaa8-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="afaa8-113">Attribute</span><span class="sxs-lookup"><span data-stu-id="afaa8-113">Attributes</span></span>  
  
|<span data-ttu-id="afaa8-114">Attribut</span><span class="sxs-lookup"><span data-stu-id="afaa8-114">Attribute</span></span>|<span data-ttu-id="afaa8-115">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="afaa8-115">Description</span></span>|  
|---------------|-----------------|  
|`mode`|<span data-ttu-id="afaa8-116">Gibt den Typ der anzuwendenden Sicherheit an.</span><span class="sxs-lookup"><span data-stu-id="afaa8-116">Specifies the type of security to be applied.</span></span> <span data-ttu-id="afaa8-117">Der Standardwert ist Nachricht.</span><span class="sxs-lookup"><span data-stu-id="afaa8-117">The default value is Message.</span></span> <span data-ttu-id="afaa8-118">Dieses Attribut ist vom Typ <xref:System.ServiceModel.SecurityMode>.</span><span class="sxs-lookup"><span data-stu-id="afaa8-118">This attribute is of type <xref:System.ServiceModel.SecurityMode>.</span></span>|  
  
## <a name="mode-attribute"></a><span data-ttu-id="afaa8-119">mode-Attribut</span><span class="sxs-lookup"><span data-stu-id="afaa8-119">mode Attribute</span></span>  
  
|<span data-ttu-id="afaa8-120">Wert</span><span class="sxs-lookup"><span data-stu-id="afaa8-120">Value</span></span>|<span data-ttu-id="afaa8-121">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="afaa8-121">Description</span></span>|  
|-----------|-----------------|  
|`None`|<span data-ttu-id="afaa8-122">Die Sicherheitsfunktionen sind deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="afaa8-122">Security is disabled.</span></span>|  
|`Transport`|<span data-ttu-id="afaa8-123">Die Sicherheit wird über HTTPS bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="afaa8-123">Security is provided using HTTPS.</span></span>|  
|`Message`|<span data-ttu-id="afaa8-124">Durch die SOAP-Sicherheit werden Authentifizierung, Integrität und Vertraulichkeit bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="afaa8-124">SOAP security provides authentication, integrity and confidentiality.</span></span>|  
|`TransportWithMessageCredential`|<span data-ttu-id="afaa8-125">HTTPS stellt Authentifizierung und Vertraulichkeit bereit.</span><span class="sxs-lookup"><span data-stu-id="afaa8-125">HTTPS provides authentication and confidentiality.</span></span> <span data-ttu-id="afaa8-126">Die SOAP-Nachrichten bieten umfassende Anmeldeinformationstypen.</span><span class="sxs-lookup"><span data-stu-id="afaa8-126">SOAP messages provide rich credential types.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="afaa8-127">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="afaa8-127">Child Elements</span></span>  
  
|<span data-ttu-id="afaa8-128">Element</span><span class="sxs-lookup"><span data-stu-id="afaa8-128">Element</span></span>|<span data-ttu-id="afaa8-129">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="afaa8-129">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="afaa8-130">\<Transport ></span><span class="sxs-lookup"><span data-stu-id="afaa8-130">\<transport></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/transport-of-peertransport.md)|<span data-ttu-id="afaa8-131">Definiert einen Peertransport für eine benutzerdefinierte Bindung.</span><span class="sxs-lookup"><span data-stu-id="afaa8-131">Defines a peer transport for a custom binding.</span></span> <span data-ttu-id="afaa8-132">Dieses Element enthält ein `clientCredentialType`-Attribut, das die für die Interaktion mit einem Dienst zu verwendenden Anmeldeinformationen angibt.</span><span class="sxs-lookup"><span data-stu-id="afaa8-132">This element has a `clientCredentialType` attribute that specifies the credentials to be used when interacting with a service.</span></span> <span data-ttu-id="afaa8-133">Dieses Attribut ist vom Typ <xref:System.ServiceModel.PeerTransportCredentialType>.</span><span class="sxs-lookup"><span data-stu-id="afaa8-133">This attribute is of type <xref:System.ServiceModel.PeerTransportCredentialType>.</span></span><br /><br /> <span data-ttu-id="afaa8-134">Dieses Element ist vom Typ <xref:System.ServiceModel.Configuration.PeerTransportSecurityElement>.</span><span class="sxs-lookup"><span data-stu-id="afaa8-134">This element is of type <xref:System.ServiceModel.Configuration.PeerTransportSecurityElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="afaa8-135">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="afaa8-135">Parent Elements</span></span>  
  
|<span data-ttu-id="afaa8-136">Element</span><span class="sxs-lookup"><span data-stu-id="afaa8-136">Element</span></span>|<span data-ttu-id="afaa8-137">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="afaa8-137">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="afaa8-138">\<PeerTransport ></span><span class="sxs-lookup"><span data-stu-id="afaa8-138">\<peerTransport></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/peertransport.md)|<span data-ttu-id="afaa8-139">Definiert einen Peertransport für eine benutzerdefinierte Bindung.</span><span class="sxs-lookup"><span data-stu-id="afaa8-139">Defines a peer transport for a custom binding.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="afaa8-140">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="afaa8-140">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.PeerSecurityElement>  
 <xref:System.ServiceModel.PeerSecuritySettings>  
 <xref:System.ServiceModel.Channels.CustomBinding>  
 [<span data-ttu-id="afaa8-141">Transportsicherheit</span><span class="sxs-lookup"><span data-stu-id="afaa8-141">Transport Security</span></span>](../../../../../docs/framework/wcf/feature-details/transport-security.md)  
 [<span data-ttu-id="afaa8-142">Transportprotokolle</span><span class="sxs-lookup"><span data-stu-id="afaa8-142">Transports</span></span>](../../../../../docs/framework/wcf/feature-details/transports.md)  
 [<span data-ttu-id="afaa8-143">Auswählen eines Transports</span><span class="sxs-lookup"><span data-stu-id="afaa8-143">Choosing a Transport</span></span>](../../../../../docs/framework/wcf/feature-details/choosing-a-transport.md)  
 [<span data-ttu-id="afaa8-144">Bindungen</span><span class="sxs-lookup"><span data-stu-id="afaa8-144">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)  
 [<span data-ttu-id="afaa8-145">Erweitern von Bindungen</span><span class="sxs-lookup"><span data-stu-id="afaa8-145">Extending Bindings</span></span>](../../../../../docs/framework/wcf/extending/extending-bindings.md)  
 [<span data-ttu-id="afaa8-146">Benutzerdefinierte Bindungen</span><span class="sxs-lookup"><span data-stu-id="afaa8-146">Custom Bindings</span></span>](../../../../../docs/framework/wcf/extending/custom-bindings.md)  
 [<span data-ttu-id="afaa8-147">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="afaa8-147">\<customBinding></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)
