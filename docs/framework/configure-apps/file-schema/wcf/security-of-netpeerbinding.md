---
title: <security> von <netPeerBinding>
ms.date: 03/30/2017
ms.assetid: 1ef40d8c-f903-4426-9b08-da81462766d8
ms.openlocfilehash: be5ebacec466caf8d8a77bf552f42da1861e77a1
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69936628"
---
# <a name="security-of-netpeerbinding"></a><span data-ttu-id="b8f1c-102">\<Sicherheits > von \<netperbinding ></span><span class="sxs-lookup"><span data-stu-id="b8f1c-102">\<security> of \<netPeerBinding></span></span>
<span data-ttu-id="b8f1c-103">Definiert die Sicherheitseinstellungen des [ \<netpeer ertcpbinding->](netpeertcpbinding.md), einschließlich des verwendeten Authentifizierungs Typs und der für den Nachrichten Transport verwendeten Sicherheit.</span><span class="sxs-lookup"><span data-stu-id="b8f1c-103">Defines the security settings of the [\<netPeerTcpBinding>](netpeertcpbinding.md), including the type of authentication used and the security used for the message transport.</span></span>  
  
 <span data-ttu-id="b8f1c-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="b8f1c-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="b8f1c-105">\<bindings></span><span class="sxs-lookup"><span data-stu-id="b8f1c-105">\<bindings></span></span>  
<span data-ttu-id="b8f1c-106">\<netPeerBinding></span><span class="sxs-lookup"><span data-stu-id="b8f1c-106">\<netPeerBinding></span></span>  
<span data-ttu-id="b8f1c-107">\<binding></span><span class="sxs-lookup"><span data-stu-id="b8f1c-107">\<binding></span></span>  
<span data-ttu-id="b8f1c-108">\<security></span><span class="sxs-lookup"><span data-stu-id="b8f1c-108">\<security></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b8f1c-109">Syntax</span><span class="sxs-lookup"><span data-stu-id="b8f1c-109">Syntax</span></span>  
  
```xml  
<netPeerBinding>
  <binding>
    <security mode="Message/None/Transport//TransportWithMessageCredential">
      <transport credentialType="Certificate/Password" />
    </security>
  </binding>
</netPeerBinding>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="b8f1c-110">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="b8f1c-110">Attributes and Elements</span></span>  
 <span data-ttu-id="b8f1c-111">In den folgenden Abschnitten werden Attribute, untergeordnete Elemente sowie übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="b8f1c-111">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="b8f1c-112">Attribute</span><span class="sxs-lookup"><span data-stu-id="b8f1c-112">Attributes</span></span>  
  
|<span data-ttu-id="b8f1c-113">Attribut</span><span class="sxs-lookup"><span data-stu-id="b8f1c-113">Attribute</span></span>|<span data-ttu-id="b8f1c-114">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="b8f1c-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="b8f1c-115">Modus</span><span class="sxs-lookup"><span data-stu-id="b8f1c-115">mode</span></span>|<span data-ttu-id="b8f1c-116">Optional.</span><span class="sxs-lookup"><span data-stu-id="b8f1c-116">Optional.</span></span> <span data-ttu-id="b8f1c-117">Gibt den Sicherheitstyp an, der von Peers verwendet wird, die mit dieser Bindung konfiguriert sind.</span><span class="sxs-lookup"><span data-stu-id="b8f1c-117">Specifies the type of security used by peers configured with this binding.</span></span> <span data-ttu-id="b8f1c-118">Der Standardwert ist `Message`.</span><span class="sxs-lookup"><span data-stu-id="b8f1c-118">The default value is `Message`.</span></span> <span data-ttu-id="b8f1c-119">Dieses Attribut ist vom Typ <xref:System.ServiceModel.SecurityMode>.</span><span class="sxs-lookup"><span data-stu-id="b8f1c-119">This attribute is of type <xref:System.ServiceModel.SecurityMode>.</span></span>|  
  
## <a name="mode-attribute"></a><span data-ttu-id="b8f1c-120">mode-Attribut</span><span class="sxs-lookup"><span data-stu-id="b8f1c-120">mode Attribute</span></span>  
  
|<span data-ttu-id="b8f1c-121">Wert</span><span class="sxs-lookup"><span data-stu-id="b8f1c-121">Value</span></span>|<span data-ttu-id="b8f1c-122">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="b8f1c-122">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="b8f1c-123">Meldung</span><span class="sxs-lookup"><span data-stu-id="b8f1c-123">Message</span></span>|<span data-ttu-id="b8f1c-124">Durch die SOAP-Sicherheit werden Authentifizierung, Integrität und Vertraulichkeit bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="b8f1c-124">SOAP security provides authentication, integrity and confidentiality.</span></span>|  
|<span data-ttu-id="b8f1c-125">None</span><span class="sxs-lookup"><span data-stu-id="b8f1c-125">None</span></span>|<span data-ttu-id="b8f1c-126">Die Sicherheitsfunktionen sind deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="b8f1c-126">Security is disabled.</span></span>|  
|<span data-ttu-id="b8f1c-127">Transport</span><span class="sxs-lookup"><span data-stu-id="b8f1c-127">Transport</span></span>|<span data-ttu-id="b8f1c-128">Die Sicherheit wird über HTTPS bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="b8f1c-128">Security is provided using HTTPS.</span></span>|  
|<span data-ttu-id="b8f1c-129">TransportWithMessageCredential</span><span class="sxs-lookup"><span data-stu-id="b8f1c-129">TransportWithMessageCredential</span></span>|<span data-ttu-id="b8f1c-130">HTTPS stellt Authentifizierung und Vertraulichkeit bereit.</span><span class="sxs-lookup"><span data-stu-id="b8f1c-130">HTTPS provides authentication and confidentiality.</span></span> <span data-ttu-id="b8f1c-131">Die SOAP-Nachrichten bieten umfassende Anmeldeinformationstypen.</span><span class="sxs-lookup"><span data-stu-id="b8f1c-131">SOAP messages provide rich credential types.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="b8f1c-132">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="b8f1c-132">Child Elements</span></span>  
  
|<span data-ttu-id="b8f1c-133">Element</span><span class="sxs-lookup"><span data-stu-id="b8f1c-133">Element</span></span>|<span data-ttu-id="b8f1c-134">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="b8f1c-134">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="b8f1c-135">\<transport></span><span class="sxs-lookup"><span data-stu-id="b8f1c-135">\<transport></span></span>](transport-of-netpeertcpbinding.md)|<span data-ttu-id="b8f1c-136">Definiert den Transporttyp für gesicherte Nachrichten, die von Peers gesendet werden, die mit dieser Bindung konfiguriert sind.</span><span class="sxs-lookup"><span data-stu-id="b8f1c-136">Defines the transport type for secured messages sent by peers configured with this binding.</span></span> <span data-ttu-id="b8f1c-137">Dieses Element ist vom Typ <xref:System.ServiceModel.Configuration.PeerTransportSecurityElement>.</span><span class="sxs-lookup"><span data-stu-id="b8f1c-137">This element is of type <xref:System.ServiceModel.Configuration.PeerTransportSecurityElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="b8f1c-138">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="b8f1c-138">Parent Elements</span></span>  
  
|<span data-ttu-id="b8f1c-139">Element</span><span class="sxs-lookup"><span data-stu-id="b8f1c-139">Element</span></span>|<span data-ttu-id="b8f1c-140">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="b8f1c-140">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="b8f1c-141">\<binding></span><span class="sxs-lookup"><span data-stu-id="b8f1c-141">\<binding></span></span>](../../../misc/binding.md)|<span data-ttu-id="b8f1c-142">Definiert alle Bindungsfunktionen des [ \<netpeer ertcpbinding->](netpeertcpbinding.md).</span><span class="sxs-lookup"><span data-stu-id="b8f1c-142">Defines all binding capabilities of the [\<netPeerTcpBinding>](netpeertcpbinding.md).</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b8f1c-143">Hinweise</span><span class="sxs-lookup"><span data-stu-id="b8f1c-143">Remarks</span></span>  
 <span data-ttu-id="b8f1c-144">Sicherheit kann entweder nachrichten- oder transportspezifisch sein.</span><span class="sxs-lookup"><span data-stu-id="b8f1c-144">Security can be either message- or transport-specific.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b8f1c-145">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b8f1c-145">See also</span></span>

- <xref:System.ServiceModel.Configuration.PeerSecurityElement>
- <xref:System.ServiceModel.NetPeerTcpBinding.Security%2A>
- <xref:System.ServiceModel.Configuration.NetPeerTcpBindingElement.Security%2A>
- <xref:System.ServiceModel.PeerSecuritySettings>
- [<span data-ttu-id="b8f1c-146">Sichern von Diensten und Clients</span><span class="sxs-lookup"><span data-stu-id="b8f1c-146">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="b8f1c-147">Ausählen eines Anmeldeinformationentyps</span><span class="sxs-lookup"><span data-stu-id="b8f1c-147">Selecting a Credential Type</span></span>](../../../wcf/feature-details/selecting-a-credential-type.md)
- [<span data-ttu-id="b8f1c-148">Bindungen</span><span class="sxs-lookup"><span data-stu-id="b8f1c-148">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="b8f1c-149">Konfigurieren der vom System bereitgestellten Bindungen</span><span class="sxs-lookup"><span data-stu-id="b8f1c-149">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="b8f1c-150">Verwenden von Bindungen, um Dienste und Clients zu konfigurieren</span><span class="sxs-lookup"><span data-stu-id="b8f1c-150">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [<span data-ttu-id="b8f1c-151">\<binding></span><span class="sxs-lookup"><span data-stu-id="b8f1c-151">\<binding></span></span>](../../../misc/binding.md)
