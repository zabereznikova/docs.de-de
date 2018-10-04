---
title: '&lt;security&gt; von &lt;netPeerBinding&gt;'
ms.date: 03/30/2017
ms.assetid: 1ef40d8c-f903-4426-9b08-da81462766d8
author: BrucePerlerMS
ms.openlocfilehash: 1d7ffaf72e34b700f4702b2e531afbf7e842de09
ms.sourcegitcommit: 69229651598b427c550223d3c58aba82e47b3f82
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/04/2018
ms.locfileid: "48776852"
---
# <a name="ltsecuritygt-of-ltnetpeerbindinggt"></a><span data-ttu-id="92c03-102">&lt;security&gt; von &lt;netPeerBinding&gt;</span><span class="sxs-lookup"><span data-stu-id="92c03-102">&lt;security&gt; of &lt;netPeerBinding&gt;</span></span>
<span data-ttu-id="92c03-103">Definiert die Sicherheitseinstellungen der [ \<NetPeerTcpBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/netpeertcpbinding.md), z. B. den Typ der Authentifizierung verwendet und die Sicherheit für den Nachrichtentransport verwendet.</span><span class="sxs-lookup"><span data-stu-id="92c03-103">Defines the security settings of the [\<netPeerTcpBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/netpeertcpbinding.md), including the type of authentication used and the security used for the message transport.</span></span>  
  
 <span data-ttu-id="92c03-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="92c03-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="92c03-105">\<bindings></span><span class="sxs-lookup"><span data-stu-id="92c03-105">\<bindings></span></span>  
<span data-ttu-id="92c03-106">\<netPeerBinding></span><span class="sxs-lookup"><span data-stu-id="92c03-106">\<netPeerBinding></span></span>  
<span data-ttu-id="92c03-107">\<binding></span><span class="sxs-lookup"><span data-stu-id="92c03-107">\<binding></span></span>  
<span data-ttu-id="92c03-108">\<Sicherheit ></span><span class="sxs-lookup"><span data-stu-id="92c03-108">\<security></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="92c03-109">Syntax</span><span class="sxs-lookup"><span data-stu-id="92c03-109">Syntax</span></span>  
  
```xml  
<netPeerBinding>  
    <binding>  
        <security mode="Message/None/Transport//TransportWithMessageCredential">  
            <transport credentialType="Certificate/Password" />  
        </security>  
    </binding>  
</netPeerBinding>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="92c03-110">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="92c03-110">Attributes and Elements</span></span>  
 <span data-ttu-id="92c03-111">In den folgenden Abschnitten werden Attribute, untergeordnete Elemente sowie übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="92c03-111">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="92c03-112">Attribute</span><span class="sxs-lookup"><span data-stu-id="92c03-112">Attributes</span></span>  
  
|<span data-ttu-id="92c03-113">Attribut</span><span class="sxs-lookup"><span data-stu-id="92c03-113">Attribute</span></span>|<span data-ttu-id="92c03-114">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="92c03-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="92c03-115">Modus</span><span class="sxs-lookup"><span data-stu-id="92c03-115">mode</span></span>|<span data-ttu-id="92c03-116">Dies ist optional.</span><span class="sxs-lookup"><span data-stu-id="92c03-116">Optional.</span></span> <span data-ttu-id="92c03-117">Gibt den Sicherheitstyp an, der von Peers verwendet wird, die mit dieser Bindung konfiguriert sind.</span><span class="sxs-lookup"><span data-stu-id="92c03-117">Specifies the type of security used by peers configured with this binding.</span></span> <span data-ttu-id="92c03-118">Der Standardwert ist `Message`.</span><span class="sxs-lookup"><span data-stu-id="92c03-118">The default value is `Message`.</span></span> <span data-ttu-id="92c03-119">Dieses Attribut ist vom Typ <xref:System.ServiceModel.SecurityMode>.</span><span class="sxs-lookup"><span data-stu-id="92c03-119">This attribute is of type <xref:System.ServiceModel.SecurityMode>.</span></span>|  
  
## <a name="mode-attribute"></a><span data-ttu-id="92c03-120">mode-Attribut</span><span class="sxs-lookup"><span data-stu-id="92c03-120">mode Attribute</span></span>  
  
|<span data-ttu-id="92c03-121">Wert</span><span class="sxs-lookup"><span data-stu-id="92c03-121">Value</span></span>|<span data-ttu-id="92c03-122">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="92c03-122">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="92c03-123">Meldung</span><span class="sxs-lookup"><span data-stu-id="92c03-123">Message</span></span>|<span data-ttu-id="92c03-124">Durch die SOAP-Sicherheit werden Authentifizierung, Integrität und Vertraulichkeit bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="92c03-124">SOAP security provides authentication, integrity and confidentiality.</span></span>|  
|<span data-ttu-id="92c03-125">Keine</span><span class="sxs-lookup"><span data-stu-id="92c03-125">None</span></span>|<span data-ttu-id="92c03-126">Die Sicherheitsfunktionen sind deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="92c03-126">Security is disabled.</span></span>|  
|<span data-ttu-id="92c03-127">Transport</span><span class="sxs-lookup"><span data-stu-id="92c03-127">Transport</span></span>|<span data-ttu-id="92c03-128">Die Sicherheit wird über HTTPS bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="92c03-128">Security is provided using HTTPS.</span></span>|  
|<span data-ttu-id="92c03-129">TransportWithMessageCredential</span><span class="sxs-lookup"><span data-stu-id="92c03-129">TransportWithMessageCredential</span></span>|<span data-ttu-id="92c03-130">HTTPS stellt Authentifizierung und Vertraulichkeit bereit.</span><span class="sxs-lookup"><span data-stu-id="92c03-130">HTTPS provides authentication and confidentiality.</span></span> <span data-ttu-id="92c03-131">Die SOAP-Nachrichten bieten umfassende Anmeldeinformationstypen.</span><span class="sxs-lookup"><span data-stu-id="92c03-131">SOAP messages provide rich credential types.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="92c03-132">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="92c03-132">Child Elements</span></span>  
  
|<span data-ttu-id="92c03-133">Element</span><span class="sxs-lookup"><span data-stu-id="92c03-133">Element</span></span>|<span data-ttu-id="92c03-134">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="92c03-134">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="92c03-135">\<Transport ></span><span class="sxs-lookup"><span data-stu-id="92c03-135">\<transport></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/transport-of-netpeertcpbinding.md)|<span data-ttu-id="92c03-136">Definiert den Transporttyp für gesicherte Nachrichten, die von Peers gesendet werden, die mit dieser Bindung konfiguriert sind.</span><span class="sxs-lookup"><span data-stu-id="92c03-136">Defines the transport type for secured messages sent by peers configured with this binding.</span></span> <span data-ttu-id="92c03-137">Dieses Element ist vom Typ <xref:System.ServiceModel.Configuration.PeerTransportSecurityElement>.</span><span class="sxs-lookup"><span data-stu-id="92c03-137">This element is of type <xref:System.ServiceModel.Configuration.PeerTransportSecurityElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="92c03-138">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="92c03-138">Parent Elements</span></span>  
  
|<span data-ttu-id="92c03-139">Element</span><span class="sxs-lookup"><span data-stu-id="92c03-139">Element</span></span>|<span data-ttu-id="92c03-140">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="92c03-140">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="92c03-141">\<binding></span><span class="sxs-lookup"><span data-stu-id="92c03-141">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)|<span data-ttu-id="92c03-142">Definiert alle bindungsfähigkeiten von der [ \<NetPeerTcpBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/netpeertcpbinding.md).</span><span class="sxs-lookup"><span data-stu-id="92c03-142">Defines all binding capabilities of the [\<netPeerTcpBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/netpeertcpbinding.md).</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="92c03-143">Hinweise</span><span class="sxs-lookup"><span data-stu-id="92c03-143">Remarks</span></span>  
 <span data-ttu-id="92c03-144">Sicherheit kann entweder nachrichten- oder transportspezifisch sein.</span><span class="sxs-lookup"><span data-stu-id="92c03-144">Security can be either message- or transport-specific.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="92c03-145">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="92c03-145">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.PeerSecurityElement>  
 <xref:System.ServiceModel.NetPeerTcpBinding.Security%2A>  
 <xref:System.ServiceModel.Configuration.NetPeerTcpBindingElement.Security%2A>  
 <xref:System.ServiceModel.PeerSecuritySettings>  
 [<span data-ttu-id="92c03-146">Sichern von Diensten und Clients</span><span class="sxs-lookup"><span data-stu-id="92c03-146">Securing Services and Clients</span></span>](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)  
 [<span data-ttu-id="92c03-147">Ausählen eines Anmeldeinformationentyps</span><span class="sxs-lookup"><span data-stu-id="92c03-147">Selecting a Credential Type</span></span>](../../../../../docs/framework/wcf/feature-details/selecting-a-credential-type.md)  
 [<span data-ttu-id="92c03-148">Bindungen</span><span class="sxs-lookup"><span data-stu-id="92c03-148">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)  
 [<span data-ttu-id="92c03-149">Konfigurieren der vom System bereitgestellten Bindungen</span><span class="sxs-lookup"><span data-stu-id="92c03-149">Configuring System-Provided Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)  
 [<span data-ttu-id="92c03-150">Verwenden von Bindungen, um Dienste und Clients zu konfigurieren</span><span class="sxs-lookup"><span data-stu-id="92c03-150">Using Bindings to Configure Services and Clients</span></span>](../../../../../docs/framework/wcf/using-bindings-to-configure-services-and-clients.md)  
 [<span data-ttu-id="92c03-151">\<binding></span><span class="sxs-lookup"><span data-stu-id="92c03-151">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)
