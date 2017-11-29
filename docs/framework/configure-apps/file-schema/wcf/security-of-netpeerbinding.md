---
title: '&lt;security&gt; von &lt;netPeerBinding&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 1ef40d8c-f903-4426-9b08-da81462766d8
caps.latest.revision: "14"
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.openlocfilehash: aac60b8502789e92c23072d139bf892ff055f9b4
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="ltsecuritygt-of-ltnetpeerbindinggt"></a><span data-ttu-id="a13b3-102">&lt;security&gt; von &lt;netPeerBinding&gt;</span><span class="sxs-lookup"><span data-stu-id="a13b3-102">&lt;security&gt; of &lt;netPeerBinding&gt;</span></span>
<span data-ttu-id="a13b3-103">Definiert die Sicherheitseinstellungen für die [ \<NetPeerTcpBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/netpeertcpbinding.md), z. B. den Typ der Authentifizierung verwendet und die Sicherheit für den Nachrichtentransport verwendet.</span><span class="sxs-lookup"><span data-stu-id="a13b3-103">Defines the security settings of the [\<netPeerTcpBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/netpeertcpbinding.md), including the type of authentication used and the security used for the message transport.</span></span>  
  
 <span data-ttu-id="a13b3-104">\<System. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="a13b3-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="a13b3-105">\<Bindungen ></span><span class="sxs-lookup"><span data-stu-id="a13b3-105">\<bindings></span></span>  
<span data-ttu-id="a13b3-106">\<NetPeerBinding ></span><span class="sxs-lookup"><span data-stu-id="a13b3-106">\<netPeerBinding></span></span>  
<span data-ttu-id="a13b3-107">\<Binden von ></span><span class="sxs-lookup"><span data-stu-id="a13b3-107">\<binding></span></span>  
<span data-ttu-id="a13b3-108">\<Sicherheit ></span><span class="sxs-lookup"><span data-stu-id="a13b3-108">\<security></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a13b3-109">Syntax</span><span class="sxs-lookup"><span data-stu-id="a13b3-109">Syntax</span></span>  
  
```xml  
<netPeerBinding>  
    <binding>  
        <security mode="Message/None/Transport//TransportWithMessageCredential">  
            <transport credentialType="Certificate/Password" />  
        </security>  
    </binding>  
</netPeerBinding>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="a13b3-110">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="a13b3-110">Attributes and Elements</span></span>  
 <span data-ttu-id="a13b3-111">In den folgenden Abschnitten werden Attribute, untergeordnete Elemente sowie übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="a13b3-111">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="a13b3-112">Attribute</span><span class="sxs-lookup"><span data-stu-id="a13b3-112">Attributes</span></span>  
  
|<span data-ttu-id="a13b3-113">Attribut</span><span class="sxs-lookup"><span data-stu-id="a13b3-113">Attribute</span></span>|<span data-ttu-id="a13b3-114">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="a13b3-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="a13b3-115">Modus</span><span class="sxs-lookup"><span data-stu-id="a13b3-115">mode</span></span>|<span data-ttu-id="a13b3-116">Dies ist optional.</span><span class="sxs-lookup"><span data-stu-id="a13b3-116">Optional.</span></span> <span data-ttu-id="a13b3-117">Gibt den Sicherheitstyp an, der von Peers verwendet wird, die mit dieser Bindung konfiguriert sind.</span><span class="sxs-lookup"><span data-stu-id="a13b3-117">Specifies the type of security used by peers configured with this binding.</span></span> <span data-ttu-id="a13b3-118">Der Standardwert ist `Message`.</span><span class="sxs-lookup"><span data-stu-id="a13b3-118">The default value is `Message`.</span></span> <span data-ttu-id="a13b3-119">Dieses Attribut ist vom Typ <xref:System.ServiceModel.SecurityMode>.</span><span class="sxs-lookup"><span data-stu-id="a13b3-119">This attribute is of type <xref:System.ServiceModel.SecurityMode>.</span></span>|  
  
## <a name="mode-attribute"></a><span data-ttu-id="a13b3-120">mode-Attribut</span><span class="sxs-lookup"><span data-stu-id="a13b3-120">mode Attribute</span></span>  
  
|<span data-ttu-id="a13b3-121">Wert</span><span class="sxs-lookup"><span data-stu-id="a13b3-121">Value</span></span>|<span data-ttu-id="a13b3-122">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="a13b3-122">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="a13b3-123">Meldung</span><span class="sxs-lookup"><span data-stu-id="a13b3-123">Message</span></span>|<span data-ttu-id="a13b3-124">Durch die SOAP-Sicherheit werden Authentifizierung, Integrität und Vertraulichkeit bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="a13b3-124">SOAP security provides authentication, integrity and confidentiality.</span></span>|  
|<span data-ttu-id="a13b3-125">Keine</span><span class="sxs-lookup"><span data-stu-id="a13b3-125">None</span></span>|<span data-ttu-id="a13b3-126">Die Sicherheitsfunktionen sind deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="a13b3-126">Security is disabled.</span></span>|  
|<span data-ttu-id="a13b3-127">Transport</span><span class="sxs-lookup"><span data-stu-id="a13b3-127">Transport</span></span>|<span data-ttu-id="a13b3-128">Die Sicherheit wird über HTTPS bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="a13b3-128">Security is provided using HTTPS.</span></span>|  
|<span data-ttu-id="a13b3-129">TransportWithMessageCredential</span><span class="sxs-lookup"><span data-stu-id="a13b3-129">TransportWithMessageCredential</span></span>|<span data-ttu-id="a13b3-130">HTTPS stellt Authentifizierung und Vertraulichkeit bereit.</span><span class="sxs-lookup"><span data-stu-id="a13b3-130">HTTPS provides authentication and confidentiality.</span></span> <span data-ttu-id="a13b3-131">Die SOAP-Nachrichten bieten umfassende Anmeldeinformationstypen.</span><span class="sxs-lookup"><span data-stu-id="a13b3-131">SOAP messages provide rich credential types.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="a13b3-132">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="a13b3-132">Child Elements</span></span>  
  
|<span data-ttu-id="a13b3-133">Element</span><span class="sxs-lookup"><span data-stu-id="a13b3-133">Element</span></span>|<span data-ttu-id="a13b3-134">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="a13b3-134">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="a13b3-135">\<Transport ></span><span class="sxs-lookup"><span data-stu-id="a13b3-135">\<transport></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/transport-of-netpeertcpbinding.md)|<span data-ttu-id="a13b3-136">Definiert den Transporttyp für gesicherte Nachrichten, die von Peers gesendet werden, die mit dieser Bindung konfiguriert sind.</span><span class="sxs-lookup"><span data-stu-id="a13b3-136">Defines the transport type for secured messages sent by peers configured with this binding.</span></span> <span data-ttu-id="a13b3-137">Dieses Element ist vom Typ <xref:System.ServiceModel.Configuration.PeerTransportSecurityElement>.</span><span class="sxs-lookup"><span data-stu-id="a13b3-137">This element is of type <xref:System.ServiceModel.Configuration.PeerTransportSecurityElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="a13b3-138">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="a13b3-138">Parent Elements</span></span>  
  
|<span data-ttu-id="a13b3-139">Element</span><span class="sxs-lookup"><span data-stu-id="a13b3-139">Element</span></span>|<span data-ttu-id="a13b3-140">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="a13b3-140">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="a13b3-141">\<Binden von ></span><span class="sxs-lookup"><span data-stu-id="a13b3-141">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)|<span data-ttu-id="a13b3-142">Definiert alle bindungsmöglichkeiten der [ \<NetPeerTcpBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/netpeertcpbinding.md).</span><span class="sxs-lookup"><span data-stu-id="a13b3-142">Defines all binding capabilities of the [\<netPeerTcpBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/netpeertcpbinding.md).</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a13b3-143">Hinweise</span><span class="sxs-lookup"><span data-stu-id="a13b3-143">Remarks</span></span>  
 <span data-ttu-id="a13b3-144">Sicherheit kann entweder nachrichten- oder transportspezifisch sein.</span><span class="sxs-lookup"><span data-stu-id="a13b3-144">Security can be either message- or transport-specific.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a13b3-145">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a13b3-145">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.PeerSecurityElement>  
 <xref:System.ServiceModel.NetPeerTcpBinding.Security%2A>  
 <xref:System.ServiceModel.Configuration.NetPeerTcpBindingElement.Security%2A>  
 <xref:System.ServiceModel.PeerSecuritySettings>  
 [<span data-ttu-id="a13b3-146">Sichern von Diensten und Clients</span><span class="sxs-lookup"><span data-stu-id="a13b3-146">Securing Services and Clients</span></span>](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)  
 [<span data-ttu-id="a13b3-147">Auswählen eines Anmeldeinformationentyps</span><span class="sxs-lookup"><span data-stu-id="a13b3-147">Selecting a Credential Type</span></span>](../../../../../docs/framework/wcf/feature-details/selecting-a-credential-type.md)  
 [<span data-ttu-id="a13b3-148">Bindungen</span><span class="sxs-lookup"><span data-stu-id="a13b3-148">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)  
 [<span data-ttu-id="a13b3-149">Konfigurieren der vom System bereitgestellte Bindungen</span><span class="sxs-lookup"><span data-stu-id="a13b3-149">Configuring System-Provided Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)  
 [<span data-ttu-id="a13b3-150">Verwenden von Bindungen, um Windows Communication Foundation-Dienste und Clients konfigurieren</span><span class="sxs-lookup"><span data-stu-id="a13b3-150">Using Bindings to Configure Windows Communication Foundation Services and Clients</span></span>](http://msdn.microsoft.com/en-us/bd8b277b-932f-472f-a42a-b02bb5257dfb)  
 [<span data-ttu-id="a13b3-151">\<Binden von ></span><span class="sxs-lookup"><span data-stu-id="a13b3-151">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)
