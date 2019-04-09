---
title: <security> von <netPeerBinding>
ms.date: 03/30/2017
ms.assetid: 1ef40d8c-f903-4426-9b08-da81462766d8
ms.openlocfilehash: 6348bc6f6c0d3a9656fbe57bf71f531d1287a949
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59170091"
---
# <a name="security-of-netpeerbinding"></a><span data-ttu-id="7ef60-102">\<security> of \<netPeerBinding></span><span class="sxs-lookup"><span data-stu-id="7ef60-102">\<security> of \<netPeerBinding></span></span>
<span data-ttu-id="7ef60-103">Definiert die Sicherheitseinstellungen der [ \<NetPeerTcpBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/netpeertcpbinding.md), z. B. den Typ der Authentifizierung verwendet und die Sicherheit für den Nachrichtentransport verwendet.</span><span class="sxs-lookup"><span data-stu-id="7ef60-103">Defines the security settings of the [\<netPeerTcpBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/netpeertcpbinding.md), including the type of authentication used and the security used for the message transport.</span></span>  
  
 <span data-ttu-id="7ef60-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="7ef60-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="7ef60-105">\<bindings></span><span class="sxs-lookup"><span data-stu-id="7ef60-105">\<bindings></span></span>  
<span data-ttu-id="7ef60-106">\<netPeerBinding></span><span class="sxs-lookup"><span data-stu-id="7ef60-106">\<netPeerBinding></span></span>  
<span data-ttu-id="7ef60-107">\<binding></span><span class="sxs-lookup"><span data-stu-id="7ef60-107">\<binding></span></span>  
<span data-ttu-id="7ef60-108">\<security></span><span class="sxs-lookup"><span data-stu-id="7ef60-108">\<security></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7ef60-109">Syntax</span><span class="sxs-lookup"><span data-stu-id="7ef60-109">Syntax</span></span>  
  
```xml  
<netPeerBinding>
  <binding>
    <security mode="Message/None/Transport//TransportWithMessageCredential">
      <transport credentialType="Certificate/Password" />
    </security>
  </binding>
</netPeerBinding>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="7ef60-110">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="7ef60-110">Attributes and Elements</span></span>  
 <span data-ttu-id="7ef60-111">In den folgenden Abschnitten werden Attribute, untergeordnete Elemente sowie übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="7ef60-111">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="7ef60-112">Attribute</span><span class="sxs-lookup"><span data-stu-id="7ef60-112">Attributes</span></span>  
  
|<span data-ttu-id="7ef60-113">Attribut</span><span class="sxs-lookup"><span data-stu-id="7ef60-113">Attribute</span></span>|<span data-ttu-id="7ef60-114">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="7ef60-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="7ef60-115">Modus</span><span class="sxs-lookup"><span data-stu-id="7ef60-115">mode</span></span>|<span data-ttu-id="7ef60-116">Dies ist optional.</span><span class="sxs-lookup"><span data-stu-id="7ef60-116">Optional.</span></span> <span data-ttu-id="7ef60-117">Gibt den Sicherheitstyp an, der von Peers verwendet wird, die mit dieser Bindung konfiguriert sind.</span><span class="sxs-lookup"><span data-stu-id="7ef60-117">Specifies the type of security used by peers configured with this binding.</span></span> <span data-ttu-id="7ef60-118">Der Standardwert ist `Message`.</span><span class="sxs-lookup"><span data-stu-id="7ef60-118">The default value is `Message`.</span></span> <span data-ttu-id="7ef60-119">Dieses Attribut ist vom Typ <xref:System.ServiceModel.SecurityMode>.</span><span class="sxs-lookup"><span data-stu-id="7ef60-119">This attribute is of type <xref:System.ServiceModel.SecurityMode>.</span></span>|  
  
## <a name="mode-attribute"></a><span data-ttu-id="7ef60-120">mode-Attribut</span><span class="sxs-lookup"><span data-stu-id="7ef60-120">mode Attribute</span></span>  
  
|<span data-ttu-id="7ef60-121">Wert</span><span class="sxs-lookup"><span data-stu-id="7ef60-121">Value</span></span>|<span data-ttu-id="7ef60-122">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="7ef60-122">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="7ef60-123">Meldung</span><span class="sxs-lookup"><span data-stu-id="7ef60-123">Message</span></span>|<span data-ttu-id="7ef60-124">Durch die SOAP-Sicherheit werden Authentifizierung, Integrität und Vertraulichkeit bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="7ef60-124">SOAP security provides authentication, integrity and confidentiality.</span></span>|  
|<span data-ttu-id="7ef60-125">Keiner</span><span class="sxs-lookup"><span data-stu-id="7ef60-125">None</span></span>|<span data-ttu-id="7ef60-126">Die Sicherheitsfunktionen sind deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="7ef60-126">Security is disabled.</span></span>|  
|<span data-ttu-id="7ef60-127">Transport</span><span class="sxs-lookup"><span data-stu-id="7ef60-127">Transport</span></span>|<span data-ttu-id="7ef60-128">Die Sicherheit wird über HTTPS bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="7ef60-128">Security is provided using HTTPS.</span></span>|  
|<span data-ttu-id="7ef60-129">TransportWithMessageCredential</span><span class="sxs-lookup"><span data-stu-id="7ef60-129">TransportWithMessageCredential</span></span>|<span data-ttu-id="7ef60-130">HTTPS stellt Authentifizierung und Vertraulichkeit bereit.</span><span class="sxs-lookup"><span data-stu-id="7ef60-130">HTTPS provides authentication and confidentiality.</span></span> <span data-ttu-id="7ef60-131">Die SOAP-Nachrichten bieten umfassende Anmeldeinformationstypen.</span><span class="sxs-lookup"><span data-stu-id="7ef60-131">SOAP messages provide rich credential types.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="7ef60-132">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="7ef60-132">Child Elements</span></span>  
  
|<span data-ttu-id="7ef60-133">Element</span><span class="sxs-lookup"><span data-stu-id="7ef60-133">Element</span></span>|<span data-ttu-id="7ef60-134">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="7ef60-134">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="7ef60-135">\<transport></span><span class="sxs-lookup"><span data-stu-id="7ef60-135">\<transport></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/transport-of-netpeertcpbinding.md)|<span data-ttu-id="7ef60-136">Definiert den Transporttyp für gesicherte Nachrichten, die von Peers gesendet werden, die mit dieser Bindung konfiguriert sind.</span><span class="sxs-lookup"><span data-stu-id="7ef60-136">Defines the transport type for secured messages sent by peers configured with this binding.</span></span> <span data-ttu-id="7ef60-137">Dieses Element ist vom Typ <xref:System.ServiceModel.Configuration.PeerTransportSecurityElement>.</span><span class="sxs-lookup"><span data-stu-id="7ef60-137">This element is of type <xref:System.ServiceModel.Configuration.PeerTransportSecurityElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="7ef60-138">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="7ef60-138">Parent Elements</span></span>  
  
|<span data-ttu-id="7ef60-139">Element</span><span class="sxs-lookup"><span data-stu-id="7ef60-139">Element</span></span>|<span data-ttu-id="7ef60-140">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="7ef60-140">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="7ef60-141">\<binding></span><span class="sxs-lookup"><span data-stu-id="7ef60-141">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)|<span data-ttu-id="7ef60-142">Definiert alle bindungsfähigkeiten von der [ \<NetPeerTcpBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/netpeertcpbinding.md).</span><span class="sxs-lookup"><span data-stu-id="7ef60-142">Defines all binding capabilities of the [\<netPeerTcpBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/netpeertcpbinding.md).</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="7ef60-143">Hinweise</span><span class="sxs-lookup"><span data-stu-id="7ef60-143">Remarks</span></span>  
 <span data-ttu-id="7ef60-144">Sicherheit kann entweder nachrichten- oder transportspezifisch sein.</span><span class="sxs-lookup"><span data-stu-id="7ef60-144">Security can be either message- or transport-specific.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7ef60-145">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="7ef60-145">See also</span></span>

- <xref:System.ServiceModel.Configuration.PeerSecurityElement>
- <xref:System.ServiceModel.NetPeerTcpBinding.Security%2A>
- <xref:System.ServiceModel.Configuration.NetPeerTcpBindingElement.Security%2A>
- <xref:System.ServiceModel.PeerSecuritySettings>
- [<span data-ttu-id="7ef60-146">Sichern von Diensten und Clients</span><span class="sxs-lookup"><span data-stu-id="7ef60-146">Securing Services and Clients</span></span>](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="7ef60-147">Wählen eines Typs von Anmeldeinformationen</span><span class="sxs-lookup"><span data-stu-id="7ef60-147">Selecting a Credential Type</span></span>](../../../../../docs/framework/wcf/feature-details/selecting-a-credential-type.md)
- [<span data-ttu-id="7ef60-148">Bindungen</span><span class="sxs-lookup"><span data-stu-id="7ef60-148">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)
- [<span data-ttu-id="7ef60-149">Konfigurieren der vom System bereitgestellten Bindungen</span><span class="sxs-lookup"><span data-stu-id="7ef60-149">Configuring System-Provided Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="7ef60-150">Verwenden von Bindungen, um Dienste und Clients zu konfigurieren</span><span class="sxs-lookup"><span data-stu-id="7ef60-150">Using Bindings to Configure Services and Clients</span></span>](../../../../../docs/framework/wcf/using-bindings-to-configure-services-and-clients.md)
- [<span data-ttu-id="7ef60-151">\<binding></span><span class="sxs-lookup"><span data-stu-id="7ef60-151">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)
