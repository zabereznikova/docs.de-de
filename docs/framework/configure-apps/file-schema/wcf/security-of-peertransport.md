---
title: '&lt;security&gt; von &lt;peerTransport&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: f73634ed-f896-4968-bf74-5e5ac52d3b6b
caps.latest.revision: "7"
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.workload: dotnet
ms.openlocfilehash: d08d839d0eb80c23b96f87cf26d3d68db7d358f6
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="ltsecuritygt-of-ltpeertransportgt"></a><span data-ttu-id="d5f30-102">&lt;security&gt; von &lt;peerTransport&gt;</span><span class="sxs-lookup"><span data-stu-id="d5f30-102">&lt;security&gt; of &lt;peerTransport&gt;</span></span>
<span data-ttu-id="d5f30-103">Enthält die einem Peerkanal zugeordneten Sicherheitseinstellungen, einschließlich für den Nachrichtentransport verwendeter Authentifizierungstyp und verwendete Sicherheit.</span><span class="sxs-lookup"><span data-stu-id="d5f30-103">Contains the security settings associated with a peer channel, including the type of authentication used and the security used for the message transport.</span></span>  
  
 <span data-ttu-id="d5f30-104">\<system.serviceModel ></span><span class="sxs-lookup"><span data-stu-id="d5f30-104">\<system.serviceModel></span></span>  
<span data-ttu-id="d5f30-105">\<Bindungen ></span><span class="sxs-lookup"><span data-stu-id="d5f30-105">\<bindings></span></span>  
<span data-ttu-id="d5f30-106">\<CustomBinding ></span><span class="sxs-lookup"><span data-stu-id="d5f30-106">\<customBinding></span></span>  
<span data-ttu-id="d5f30-107">\<Binden von ></span><span class="sxs-lookup"><span data-stu-id="d5f30-107">\<binding></span></span>  
<span data-ttu-id="d5f30-108">\<PeerTransport ></span><span class="sxs-lookup"><span data-stu-id="d5f30-108">\<peerTransport></span></span>  
<span data-ttu-id="d5f30-109">\<Sicherheit ></span><span class="sxs-lookup"><span data-stu-id="d5f30-109">\<security></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d5f30-110">Syntax</span><span class="sxs-lookup"><span data-stu-id="d5f30-110">Syntax</span></span>  
  
```xml  
<security mode="None/Transport/Message/TransportWithMessageCredential">  
    <transport clientCredentialType="None/Windows/UserName/Certificate/CardSpace" />  
</security  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="d5f30-111">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="d5f30-111">Attributes and Elements</span></span>  
 <span data-ttu-id="d5f30-112">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="d5f30-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="d5f30-113">Attribute</span><span class="sxs-lookup"><span data-stu-id="d5f30-113">Attributes</span></span>  
  
|<span data-ttu-id="d5f30-114">Attribut</span><span class="sxs-lookup"><span data-stu-id="d5f30-114">Attribute</span></span>|<span data-ttu-id="d5f30-115">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="d5f30-115">Description</span></span>|  
|---------------|-----------------|  
|`mode`|<span data-ttu-id="d5f30-116">Gibt den Typ der anzuwendenden Sicherheit an.</span><span class="sxs-lookup"><span data-stu-id="d5f30-116">Specifies the type of security to be applied.</span></span> <span data-ttu-id="d5f30-117">Der Standardwert ist Nachricht.</span><span class="sxs-lookup"><span data-stu-id="d5f30-117">The default value is Message.</span></span> <span data-ttu-id="d5f30-118">Dieses Attribut ist vom Typ <xref:System.ServiceModel.SecurityMode>.</span><span class="sxs-lookup"><span data-stu-id="d5f30-118">This attribute is of type <xref:System.ServiceModel.SecurityMode>.</span></span>|  
  
## <a name="mode-attribute"></a><span data-ttu-id="d5f30-119">mode-Attribut</span><span class="sxs-lookup"><span data-stu-id="d5f30-119">mode Attribute</span></span>  
  
|<span data-ttu-id="d5f30-120">Wert</span><span class="sxs-lookup"><span data-stu-id="d5f30-120">Value</span></span>|<span data-ttu-id="d5f30-121">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="d5f30-121">Description</span></span>|  
|-----------|-----------------|  
|`None`|<span data-ttu-id="d5f30-122">Die Sicherheitsfunktionen sind deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="d5f30-122">Security is disabled.</span></span>|  
|`Transport`|<span data-ttu-id="d5f30-123">Die Sicherheit wird über HTTPS bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="d5f30-123">Security is provided using HTTPS.</span></span>|  
|`Message`|<span data-ttu-id="d5f30-124">Durch die SOAP-Sicherheit werden Authentifizierung, Integrität und Vertraulichkeit bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="d5f30-124">SOAP security provides authentication, integrity and confidentiality.</span></span>|  
|`TransportWithMessageCredential`|<span data-ttu-id="d5f30-125">HTTPS stellt Authentifizierung und Vertraulichkeit bereit.</span><span class="sxs-lookup"><span data-stu-id="d5f30-125">HTTPS provides authentication and confidentiality.</span></span> <span data-ttu-id="d5f30-126">Die SOAP-Nachrichten bieten umfassende Anmeldeinformationstypen.</span><span class="sxs-lookup"><span data-stu-id="d5f30-126">SOAP messages provide rich credential types.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="d5f30-127">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="d5f30-127">Child Elements</span></span>  
  
|<span data-ttu-id="d5f30-128">Element</span><span class="sxs-lookup"><span data-stu-id="d5f30-128">Element</span></span>|<span data-ttu-id="d5f30-129">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="d5f30-129">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="d5f30-130">\<Transport ></span><span class="sxs-lookup"><span data-stu-id="d5f30-130">\<transport></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/transport-of-peertransport.md)|<span data-ttu-id="d5f30-131">Definiert einen Peertransport für eine benutzerdefinierte Bindung.</span><span class="sxs-lookup"><span data-stu-id="d5f30-131">Defines a peer transport for a custom binding.</span></span> <span data-ttu-id="d5f30-132">Dieses Element enthält ein `clientCredentialType`-Attribut, das die für die Interaktion mit einem Dienst zu verwendenden Anmeldeinformationen angibt.</span><span class="sxs-lookup"><span data-stu-id="d5f30-132">This element has a `clientCredentialType` attribute that specifies the credentials to be used when interacting with a service.</span></span> <span data-ttu-id="d5f30-133">Dieses Attribut ist vom Typ <xref:System.ServiceModel.PeerTransportCredentialType>.</span><span class="sxs-lookup"><span data-stu-id="d5f30-133">This attribute is of type <xref:System.ServiceModel.PeerTransportCredentialType>.</span></span><br /><br /> <span data-ttu-id="d5f30-134">Dieses Element ist vom Typ <xref:System.ServiceModel.Configuration.PeerTransportSecurityElement>.</span><span class="sxs-lookup"><span data-stu-id="d5f30-134">This element is of type <xref:System.ServiceModel.Configuration.PeerTransportSecurityElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="d5f30-135">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="d5f30-135">Parent Elements</span></span>  
  
|<span data-ttu-id="d5f30-136">Element</span><span class="sxs-lookup"><span data-stu-id="d5f30-136">Element</span></span>|<span data-ttu-id="d5f30-137">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="d5f30-137">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="d5f30-138">\<PeerTransport ></span><span class="sxs-lookup"><span data-stu-id="d5f30-138">\<peerTransport></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/peertransport.md)|<span data-ttu-id="d5f30-139">Definiert einen Peertransport für eine benutzerdefinierte Bindung.</span><span class="sxs-lookup"><span data-stu-id="d5f30-139">Defines a peer transport for a custom binding.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="d5f30-140">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d5f30-140">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.PeerSecurityElement>  
 <xref:System.ServiceModel.PeerSecuritySettings>  
 <xref:System.ServiceModel.Channels.CustomBinding>  
 [<span data-ttu-id="d5f30-141">Transportsicherheit</span><span class="sxs-lookup"><span data-stu-id="d5f30-141">Transport Security</span></span>](../../../../../docs/framework/wcf/feature-details/transport-security.md)  
 [<span data-ttu-id="d5f30-142">Transportprotokolle</span><span class="sxs-lookup"><span data-stu-id="d5f30-142">Transports</span></span>](../../../../../docs/framework/wcf/feature-details/transports.md)  
 [<span data-ttu-id="d5f30-143">Auswählen eines Transports</span><span class="sxs-lookup"><span data-stu-id="d5f30-143">Choosing a Transport</span></span>](../../../../../docs/framework/wcf/feature-details/choosing-a-transport.md)  
 [<span data-ttu-id="d5f30-144">Bindungen</span><span class="sxs-lookup"><span data-stu-id="d5f30-144">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)  
 [<span data-ttu-id="d5f30-145">Erweitern von Bindungen</span><span class="sxs-lookup"><span data-stu-id="d5f30-145">Extending Bindings</span></span>](../../../../../docs/framework/wcf/extending/extending-bindings.md)  
 [<span data-ttu-id="d5f30-146">Benutzerdefinierte Bindungen</span><span class="sxs-lookup"><span data-stu-id="d5f30-146">Custom Bindings</span></span>](../../../../../docs/framework/wcf/extending/custom-bindings.md)  
 [<span data-ttu-id="d5f30-147">\<CustomBinding ></span><span class="sxs-lookup"><span data-stu-id="d5f30-147">\<customBinding></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)
