---
title: '&lt;transport&gt; von &lt;netPeerTcpBinding&gt;'
ms.date: 03/30/2017
ms.assetid: c44d86d2-1160-44d7-9c7a-297b12eccc7f
ms.openlocfilehash: 2b89ae090d24ff6aad1aae1b39a0a18961bd2537
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/05/2018
ms.locfileid: "43735318"
---
# <a name="lttransportgt-of-ltnetpeertcpbindinggt"></a><span data-ttu-id="c5123-102">&lt;transport&gt; von &lt;netPeerTcpBinding&gt;</span><span class="sxs-lookup"><span data-stu-id="c5123-102">&lt;transport&gt; of &lt;netPeerTcpBinding&gt;</span></span>
<span data-ttu-id="c5123-103">Gibt die Einstellungen für Sicherheit auf Transportebene bei Verwendung der [ \<NetPeerTcpBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/netpeertcpbinding.md).</span><span class="sxs-lookup"><span data-stu-id="c5123-103">Specifies settings for transport level security when using the [\<netPeerTcpBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/netpeertcpbinding.md).</span></span>  
  
 <span data-ttu-id="c5123-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="c5123-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="c5123-105">\<bindings></span><span class="sxs-lookup"><span data-stu-id="c5123-105">\<bindings></span></span>  
<span data-ttu-id="c5123-106">\<netPeerTcpBinding></span><span class="sxs-lookup"><span data-stu-id="c5123-106">\<netPeerTcpBinding></span></span>  
<span data-ttu-id="c5123-107">\<binding></span><span class="sxs-lookup"><span data-stu-id="c5123-107">\<binding></span></span>  
<span data-ttu-id="c5123-108">\<Sicherheit ></span><span class="sxs-lookup"><span data-stu-id="c5123-108">\<security></span></span>  
<span data-ttu-id="c5123-109">\<Transport ></span><span class="sxs-lookup"><span data-stu-id="c5123-109">\<transport></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c5123-110">Syntax</span><span class="sxs-lookup"><span data-stu-id="c5123-110">Syntax</span></span>  
  
```xml  
<netPeerTcpBinding>  
    <binding>  
        <security>  
            <transport credentialType="Certificate/Password" />  
        </security>         
    </binding>  
</netPeerTcpBinding>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="c5123-111">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="c5123-111">Attributes and Elements</span></span>  
 <span data-ttu-id="c5123-112">In den folgenden Abschnitten werden Attribute, untergeordnete Elemente sowie übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="c5123-112">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="c5123-113">Attribute</span><span class="sxs-lookup"><span data-stu-id="c5123-113">Attributes</span></span>  
  
|<span data-ttu-id="c5123-114">Attribut</span><span class="sxs-lookup"><span data-stu-id="c5123-114">Attribute</span></span>|<span data-ttu-id="c5123-115">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="c5123-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="c5123-116">credentialType</span><span class="sxs-lookup"><span data-stu-id="c5123-116">credentialType</span></span>|<span data-ttu-id="c5123-117">Dies ist optional.</span><span class="sxs-lookup"><span data-stu-id="c5123-117">Optional.</span></span> <span data-ttu-id="c5123-118">Gibt den Typ von Anmeldeinformationen an, die zum Überprüfen von über den Peertransport gesendeten Nachrichten verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="c5123-118">Specifies the type of credentials used to verify messages sent with the peer transport.</span></span> <span data-ttu-id="c5123-119">Dieses Attribut ist vom Typ <xref:System.ServiceModel.PeerTransportCredentialType>.</span><span class="sxs-lookup"><span data-stu-id="c5123-119">This attribute is of type <xref:System.ServiceModel.PeerTransportCredentialType>.</span></span>|  
  
## <a name="credentialtype-attribute"></a><span data-ttu-id="c5123-120">credentialType-Attribut</span><span class="sxs-lookup"><span data-stu-id="c5123-120">credentialType Attribute</span></span>  
  
|<span data-ttu-id="c5123-121">Wert</span><span class="sxs-lookup"><span data-stu-id="c5123-121">Value</span></span>|<span data-ttu-id="c5123-122">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="c5123-122">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="c5123-123">Zertifikat</span><span class="sxs-lookup"><span data-stu-id="c5123-123">Certificate</span></span>|<span data-ttu-id="c5123-124">Zur Authentifizierung des Peerkanaltransports ist ein X509-Zertifikat erforderlich.</span><span class="sxs-lookup"><span data-stu-id="c5123-124">Authentication of the peer channel transport requires an X509 certificate.</span></span>|  
|<span data-ttu-id="c5123-125">Kennwort</span><span class="sxs-lookup"><span data-stu-id="c5123-125">Password</span></span>|<span data-ttu-id="c5123-126">Zur Authentifizierung des Peerkanaltransports ist ein korrektes Kennwort erforderlich.</span><span class="sxs-lookup"><span data-stu-id="c5123-126">Authentication of the peer channel transport requires a correct password.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="c5123-127">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="c5123-127">Child Elements</span></span>  
 <span data-ttu-id="c5123-128">Keiner</span><span class="sxs-lookup"><span data-stu-id="c5123-128">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="c5123-129">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="c5123-129">Parent Elements</span></span>  
  
|<span data-ttu-id="c5123-130">Element</span><span class="sxs-lookup"><span data-stu-id="c5123-130">Element</span></span>|<span data-ttu-id="c5123-131">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="c5123-131">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="c5123-132">\<security></span><span class="sxs-lookup"><span data-stu-id="c5123-132">\<security></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/security-of-netpeerbinding.md)|<span data-ttu-id="c5123-133">Definiert die Sicherheitseinstellungen für die [ \<NetPeerTcpBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/netpeertcpbinding.md).</span><span class="sxs-lookup"><span data-stu-id="c5123-133">Defines the security settings for the [\<netPeerTcpBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/netpeertcpbinding.md).</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="c5123-134">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c5123-134">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.PeerTransportSecurityElement>  
 <xref:System.ServiceModel.PeerSecuritySettings.Transport%2A>  
 <xref:System.ServiceModel.Configuration.PeerSecurityElement.Transport%2A>  
 <xref:System.ServiceModel.PeerTransportSecuritySettings>  
 [<span data-ttu-id="c5123-135">Sichern von Diensten und Clients</span><span class="sxs-lookup"><span data-stu-id="c5123-135">Securing Services and Clients</span></span>](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)  
 [<span data-ttu-id="c5123-136">Bindungen</span><span class="sxs-lookup"><span data-stu-id="c5123-136">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)  
 [<span data-ttu-id="c5123-137">Konfigurieren der vom System bereitgestellten Bindungen</span><span class="sxs-lookup"><span data-stu-id="c5123-137">Configuring System-Provided Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)  
 [<span data-ttu-id="c5123-138">Verwenden von Bindungen, um Windows Communication Foundation-Dienste und Clients konfigurieren</span><span class="sxs-lookup"><span data-stu-id="c5123-138">Using Bindings to Configure Windows Communication Foundation Services and Clients</span></span>](https://msdn.microsoft.com/library/bd8b277b-932f-472f-a42a-b02bb5257dfb)  
 [<span data-ttu-id="c5123-139">\<binding></span><span class="sxs-lookup"><span data-stu-id="c5123-139">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)
