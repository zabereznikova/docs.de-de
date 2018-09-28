---
title: '&lt;security&gt; von &lt;netPeerBinding&gt;'
ms.date: 03/30/2017
ms.assetid: 1ef40d8c-f903-4426-9b08-da81462766d8
author: BrucePerlerMS
ms.openlocfilehash: d17d063ffdd354327c2523415b7d9394e723135a
ms.sourcegitcommit: fb78d8abbdb87144a3872cf154930157090dd933
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/28/2018
ms.locfileid: "47436296"
---
# <a name="ltsecuritygt-of-ltnetpeerbindinggt"></a><span data-ttu-id="62190-102">&lt;security&gt; von &lt;netPeerBinding&gt;</span><span class="sxs-lookup"><span data-stu-id="62190-102">&lt;security&gt; of &lt;netPeerBinding&gt;</span></span>
<span data-ttu-id="62190-103">Definiert die Sicherheitseinstellungen der [ \<NetPeerTcpBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/netpeertcpbinding.md), z. B. den Typ der Authentifizierung verwendet und die Sicherheit für den Nachrichtentransport verwendet.</span><span class="sxs-lookup"><span data-stu-id="62190-103">Defines the security settings of the [\<netPeerTcpBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/netpeertcpbinding.md), including the type of authentication used and the security used for the message transport.</span></span>  
  
 <span data-ttu-id="62190-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="62190-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="62190-105">\<bindings></span><span class="sxs-lookup"><span data-stu-id="62190-105">\<bindings></span></span>  
<span data-ttu-id="62190-106">\<netPeerBinding></span><span class="sxs-lookup"><span data-stu-id="62190-106">\<netPeerBinding></span></span>  
<span data-ttu-id="62190-107">\<binding></span><span class="sxs-lookup"><span data-stu-id="62190-107">\<binding></span></span>  
<span data-ttu-id="62190-108">\<Sicherheit ></span><span class="sxs-lookup"><span data-stu-id="62190-108">\<security></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="62190-109">Syntax</span><span class="sxs-lookup"><span data-stu-id="62190-109">Syntax</span></span>  
  
```xml  
<netPeerBinding>  
    <binding>  
        <security mode="Message/None/Transport//TransportWithMessageCredential">  
            <transport credentialType="Certificate/Password" />  
        </security>  
    </binding>  
</netPeerBinding>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="62190-110">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="62190-110">Attributes and Elements</span></span>  
 <span data-ttu-id="62190-111">In den folgenden Abschnitten werden Attribute, untergeordnete Elemente sowie übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="62190-111">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="62190-112">Attribute</span><span class="sxs-lookup"><span data-stu-id="62190-112">Attributes</span></span>  
  
|<span data-ttu-id="62190-113">Attribut</span><span class="sxs-lookup"><span data-stu-id="62190-113">Attribute</span></span>|<span data-ttu-id="62190-114">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="62190-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="62190-115">Modus</span><span class="sxs-lookup"><span data-stu-id="62190-115">mode</span></span>|<span data-ttu-id="62190-116">Dies ist optional.</span><span class="sxs-lookup"><span data-stu-id="62190-116">Optional.</span></span> <span data-ttu-id="62190-117">Gibt den Sicherheitstyp an, der von Peers verwendet wird, die mit dieser Bindung konfiguriert sind.</span><span class="sxs-lookup"><span data-stu-id="62190-117">Specifies the type of security used by peers configured with this binding.</span></span> <span data-ttu-id="62190-118">Der Standardwert ist `Message`.</span><span class="sxs-lookup"><span data-stu-id="62190-118">The default value is `Message`.</span></span> <span data-ttu-id="62190-119">Dieses Attribut ist vom Typ <xref:System.ServiceModel.SecurityMode>.</span><span class="sxs-lookup"><span data-stu-id="62190-119">This attribute is of type <xref:System.ServiceModel.SecurityMode>.</span></span>|  
  
## <a name="mode-attribute"></a><span data-ttu-id="62190-120">mode-Attribut</span><span class="sxs-lookup"><span data-stu-id="62190-120">mode Attribute</span></span>  
  
|<span data-ttu-id="62190-121">Wert</span><span class="sxs-lookup"><span data-stu-id="62190-121">Value</span></span>|<span data-ttu-id="62190-122">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="62190-122">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="62190-123">Meldung</span><span class="sxs-lookup"><span data-stu-id="62190-123">Message</span></span>|<span data-ttu-id="62190-124">Durch die SOAP-Sicherheit werden Authentifizierung, Integrität und Vertraulichkeit bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="62190-124">SOAP security provides authentication, integrity and confidentiality.</span></span>|  
|<span data-ttu-id="62190-125">Keine</span><span class="sxs-lookup"><span data-stu-id="62190-125">None</span></span>|<span data-ttu-id="62190-126">Die Sicherheitsfunktionen sind deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="62190-126">Security is disabled.</span></span>|  
|<span data-ttu-id="62190-127">Transport</span><span class="sxs-lookup"><span data-stu-id="62190-127">Transport</span></span>|<span data-ttu-id="62190-128">Die Sicherheit wird über HTTPS bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="62190-128">Security is provided using HTTPS.</span></span>|  
|<span data-ttu-id="62190-129">TransportWithMessageCredential</span><span class="sxs-lookup"><span data-stu-id="62190-129">TransportWithMessageCredential</span></span>|<span data-ttu-id="62190-130">HTTPS stellt Authentifizierung und Vertraulichkeit bereit.</span><span class="sxs-lookup"><span data-stu-id="62190-130">HTTPS provides authentication and confidentiality.</span></span> <span data-ttu-id="62190-131">Die SOAP-Nachrichten bieten umfassende Anmeldeinformationstypen.</span><span class="sxs-lookup"><span data-stu-id="62190-131">SOAP messages provide rich credential types.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="62190-132">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="62190-132">Child Elements</span></span>  
  
|<span data-ttu-id="62190-133">Element</span><span class="sxs-lookup"><span data-stu-id="62190-133">Element</span></span>|<span data-ttu-id="62190-134">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="62190-134">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="62190-135">\<Transport ></span><span class="sxs-lookup"><span data-stu-id="62190-135">\<transport></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/transport-of-netpeertcpbinding.md)|<span data-ttu-id="62190-136">Definiert den Transporttyp für gesicherte Nachrichten, die von Peers gesendet werden, die mit dieser Bindung konfiguriert sind.</span><span class="sxs-lookup"><span data-stu-id="62190-136">Defines the transport type for secured messages sent by peers configured with this binding.</span></span> <span data-ttu-id="62190-137">Dieses Element ist vom Typ <xref:System.ServiceModel.Configuration.PeerTransportSecurityElement>.</span><span class="sxs-lookup"><span data-stu-id="62190-137">This element is of type <xref:System.ServiceModel.Configuration.PeerTransportSecurityElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="62190-138">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="62190-138">Parent Elements</span></span>  
  
|<span data-ttu-id="62190-139">Element</span><span class="sxs-lookup"><span data-stu-id="62190-139">Element</span></span>|<span data-ttu-id="62190-140">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="62190-140">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="62190-141">\<binding></span><span class="sxs-lookup"><span data-stu-id="62190-141">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)|<span data-ttu-id="62190-142">Definiert alle bindungsfähigkeiten von der [ \<NetPeerTcpBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/netpeertcpbinding.md).</span><span class="sxs-lookup"><span data-stu-id="62190-142">Defines all binding capabilities of the [\<netPeerTcpBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/netpeertcpbinding.md).</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="62190-143">Hinweise</span><span class="sxs-lookup"><span data-stu-id="62190-143">Remarks</span></span>  
 <span data-ttu-id="62190-144">Sicherheit kann entweder nachrichten- oder transportspezifisch sein.</span><span class="sxs-lookup"><span data-stu-id="62190-144">Security can be either message- or transport-specific.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="62190-145">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="62190-145">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.PeerSecurityElement>  
 <xref:System.ServiceModel.NetPeerTcpBinding.Security%2A>  
 <xref:System.ServiceModel.Configuration.NetPeerTcpBindingElement.Security%2A>  
 <xref:System.ServiceModel.PeerSecuritySettings>  
 [<span data-ttu-id="62190-146">Sichern von Diensten und Clients</span><span class="sxs-lookup"><span data-stu-id="62190-146">Securing Services and Clients</span></span>](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)  
 [<span data-ttu-id="62190-147">Ausählen eines Anmeldeinformationentyps</span><span class="sxs-lookup"><span data-stu-id="62190-147">Selecting a Credential Type</span></span>](../../../../../docs/framework/wcf/feature-details/selecting-a-credential-type.md)  
 [<span data-ttu-id="62190-148">Bindungen</span><span class="sxs-lookup"><span data-stu-id="62190-148">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)  
 [<span data-ttu-id="62190-149">Konfigurieren der vom System bereitgestellten Bindungen</span><span class="sxs-lookup"><span data-stu-id="62190-149">Configuring System-Provided Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)  
 [<span data-ttu-id="62190-150">Verwenden von Bindungen, um Windows Communication Foundation-Dienste und Clients konfigurieren</span><span class="sxs-lookup"><span data-stu-id="62190-150">Using Bindings to Configure Windows Communication Foundation Services and Clients</span></span>](https://msdn.microsoft.com/library/bd8b277b-932f-472f-a42a-b02bb5257dfb)  
 [<span data-ttu-id="62190-151">\<binding></span><span class="sxs-lookup"><span data-stu-id="62190-151">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)
