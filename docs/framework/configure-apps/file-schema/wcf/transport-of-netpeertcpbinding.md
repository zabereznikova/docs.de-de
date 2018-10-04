---
title: '&lt;transport&gt; von &lt;netPeerTcpBinding&gt;'
ms.date: 03/30/2017
ms.assetid: c44d86d2-1160-44d7-9c7a-297b12eccc7f
ms.openlocfilehash: 62ba3b27b10afe182623f3be0f6738940e194579
ms.sourcegitcommit: 69229651598b427c550223d3c58aba82e47b3f82
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/04/2018
ms.locfileid: "48579789"
---
# <a name="lttransportgt-of-ltnetpeertcpbindinggt"></a><span data-ttu-id="afd1a-102">&lt;transport&gt; von &lt;netPeerTcpBinding&gt;</span><span class="sxs-lookup"><span data-stu-id="afd1a-102">&lt;transport&gt; of &lt;netPeerTcpBinding&gt;</span></span>
<span data-ttu-id="afd1a-103">Gibt die Einstellungen für Sicherheit auf Transportebene bei Verwendung der [ \<NetPeerTcpBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/netpeertcpbinding.md).</span><span class="sxs-lookup"><span data-stu-id="afd1a-103">Specifies settings for transport level security when using the [\<netPeerTcpBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/netpeertcpbinding.md).</span></span>  
  
 <span data-ttu-id="afd1a-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="afd1a-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="afd1a-105">\<bindings></span><span class="sxs-lookup"><span data-stu-id="afd1a-105">\<bindings></span></span>  
<span data-ttu-id="afd1a-106">\<netPeerTcpBinding></span><span class="sxs-lookup"><span data-stu-id="afd1a-106">\<netPeerTcpBinding></span></span>  
<span data-ttu-id="afd1a-107">\<binding></span><span class="sxs-lookup"><span data-stu-id="afd1a-107">\<binding></span></span>  
<span data-ttu-id="afd1a-108">\<Sicherheit ></span><span class="sxs-lookup"><span data-stu-id="afd1a-108">\<security></span></span>  
<span data-ttu-id="afd1a-109">\<Transport ></span><span class="sxs-lookup"><span data-stu-id="afd1a-109">\<transport></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="afd1a-110">Syntax</span><span class="sxs-lookup"><span data-stu-id="afd1a-110">Syntax</span></span>  
  
```xml  
<netPeerTcpBinding>  
    <binding>  
        <security>  
            <transport credentialType="Certificate/Password" />  
        </security>         
    </binding>  
</netPeerTcpBinding>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="afd1a-111">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="afd1a-111">Attributes and Elements</span></span>  
 <span data-ttu-id="afd1a-112">In den folgenden Abschnitten werden Attribute, untergeordnete Elemente sowie übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="afd1a-112">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="afd1a-113">Attribute</span><span class="sxs-lookup"><span data-stu-id="afd1a-113">Attributes</span></span>  
  
|<span data-ttu-id="afd1a-114">Attribut</span><span class="sxs-lookup"><span data-stu-id="afd1a-114">Attribute</span></span>|<span data-ttu-id="afd1a-115">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="afd1a-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="afd1a-116">credentialType</span><span class="sxs-lookup"><span data-stu-id="afd1a-116">credentialType</span></span>|<span data-ttu-id="afd1a-117">Dies ist optional.</span><span class="sxs-lookup"><span data-stu-id="afd1a-117">Optional.</span></span> <span data-ttu-id="afd1a-118">Gibt den Typ von Anmeldeinformationen an, die zum Überprüfen von über den Peertransport gesendeten Nachrichten verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="afd1a-118">Specifies the type of credentials used to verify messages sent with the peer transport.</span></span> <span data-ttu-id="afd1a-119">Dieses Attribut ist vom Typ <xref:System.ServiceModel.PeerTransportCredentialType>.</span><span class="sxs-lookup"><span data-stu-id="afd1a-119">This attribute is of type <xref:System.ServiceModel.PeerTransportCredentialType>.</span></span>|  
  
## <a name="credentialtype-attribute"></a><span data-ttu-id="afd1a-120">credentialType-Attribut</span><span class="sxs-lookup"><span data-stu-id="afd1a-120">credentialType Attribute</span></span>  
  
|<span data-ttu-id="afd1a-121">Wert</span><span class="sxs-lookup"><span data-stu-id="afd1a-121">Value</span></span>|<span data-ttu-id="afd1a-122">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="afd1a-122">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="afd1a-123">Zertifikat</span><span class="sxs-lookup"><span data-stu-id="afd1a-123">Certificate</span></span>|<span data-ttu-id="afd1a-124">Zur Authentifizierung des Peerkanaltransports ist ein X509-Zertifikat erforderlich.</span><span class="sxs-lookup"><span data-stu-id="afd1a-124">Authentication of the peer channel transport requires an X509 certificate.</span></span>|  
|<span data-ttu-id="afd1a-125">Kennwort</span><span class="sxs-lookup"><span data-stu-id="afd1a-125">Password</span></span>|<span data-ttu-id="afd1a-126">Zur Authentifizierung des Peerkanaltransports ist ein korrektes Kennwort erforderlich.</span><span class="sxs-lookup"><span data-stu-id="afd1a-126">Authentication of the peer channel transport requires a correct password.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="afd1a-127">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="afd1a-127">Child Elements</span></span>  
 <span data-ttu-id="afd1a-128">Keiner</span><span class="sxs-lookup"><span data-stu-id="afd1a-128">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="afd1a-129">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="afd1a-129">Parent Elements</span></span>  
  
|<span data-ttu-id="afd1a-130">Element</span><span class="sxs-lookup"><span data-stu-id="afd1a-130">Element</span></span>|<span data-ttu-id="afd1a-131">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="afd1a-131">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="afd1a-132">\<security></span><span class="sxs-lookup"><span data-stu-id="afd1a-132">\<security></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/security-of-netpeerbinding.md)|<span data-ttu-id="afd1a-133">Definiert die Sicherheitseinstellungen für die [ \<NetPeerTcpBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/netpeertcpbinding.md).</span><span class="sxs-lookup"><span data-stu-id="afd1a-133">Defines the security settings for the [\<netPeerTcpBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/netpeertcpbinding.md).</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="afd1a-134">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="afd1a-134">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.PeerTransportSecurityElement>  
 <xref:System.ServiceModel.PeerSecuritySettings.Transport%2A>  
 <xref:System.ServiceModel.Configuration.PeerSecurityElement.Transport%2A>  
 <xref:System.ServiceModel.PeerTransportSecuritySettings>  
 [<span data-ttu-id="afd1a-135">Sichern von Diensten und Clients</span><span class="sxs-lookup"><span data-stu-id="afd1a-135">Securing Services and Clients</span></span>](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)  
 [<span data-ttu-id="afd1a-136">Bindungen</span><span class="sxs-lookup"><span data-stu-id="afd1a-136">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)  
 [<span data-ttu-id="afd1a-137">Konfigurieren der vom System bereitgestellten Bindungen</span><span class="sxs-lookup"><span data-stu-id="afd1a-137">Configuring System-Provided Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)  
 [<span data-ttu-id="afd1a-138">Verwenden von Bindungen, um Dienste und Clients zu konfigurieren</span><span class="sxs-lookup"><span data-stu-id="afd1a-138">Using Bindings to Configure Services and Clients</span></span>](../../../../../docs/framework/wcf/using-bindings-to-configure-services-and-clients.md)  
 [<span data-ttu-id="afd1a-139">\<binding></span><span class="sxs-lookup"><span data-stu-id="afd1a-139">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)
