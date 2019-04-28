---
title: <transport> von <netPeerTcpBinding>
ms.date: 03/30/2017
ms.assetid: c44d86d2-1160-44d7-9c7a-297b12eccc7f
ms.openlocfilehash: 157637615abafbd5913e4d90b702bb0224d5f121
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61788322"
---
# <a name="transport-of-netpeertcpbinding"></a><span data-ttu-id="76d3e-102">\<transport> of \<netPeerTcpBinding></span><span class="sxs-lookup"><span data-stu-id="76d3e-102">\<transport> of \<netPeerTcpBinding></span></span>
<span data-ttu-id="76d3e-103">Gibt die Einstellungen für Sicherheit auf Transportebene bei Verwendung der [ \<NetPeerTcpBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/netpeertcpbinding.md).</span><span class="sxs-lookup"><span data-stu-id="76d3e-103">Specifies settings for transport level security when using the [\<netPeerTcpBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/netpeertcpbinding.md).</span></span>  
  
 <span data-ttu-id="76d3e-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="76d3e-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="76d3e-105">\<bindings></span><span class="sxs-lookup"><span data-stu-id="76d3e-105">\<bindings></span></span>  
<span data-ttu-id="76d3e-106">\<netPeerTcpBinding></span><span class="sxs-lookup"><span data-stu-id="76d3e-106">\<netPeerTcpBinding></span></span>  
<span data-ttu-id="76d3e-107">\<binding></span><span class="sxs-lookup"><span data-stu-id="76d3e-107">\<binding></span></span>  
<span data-ttu-id="76d3e-108">\<security></span><span class="sxs-lookup"><span data-stu-id="76d3e-108">\<security></span></span>  
<span data-ttu-id="76d3e-109">\<transport></span><span class="sxs-lookup"><span data-stu-id="76d3e-109">\<transport></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="76d3e-110">Syntax</span><span class="sxs-lookup"><span data-stu-id="76d3e-110">Syntax</span></span>  
  
```xml  
<netPeerTcpBinding>
  <binding>
    <security>
      <transport credentialType="Certificate/Password" />
    </security>
  </binding>
</netPeerTcpBinding>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="76d3e-111">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="76d3e-111">Attributes and Elements</span></span>  
 <span data-ttu-id="76d3e-112">In den folgenden Abschnitten werden Attribute, untergeordnete Elemente sowie übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="76d3e-112">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="76d3e-113">Attribute</span><span class="sxs-lookup"><span data-stu-id="76d3e-113">Attributes</span></span>  
  
|<span data-ttu-id="76d3e-114">Attribut</span><span class="sxs-lookup"><span data-stu-id="76d3e-114">Attribute</span></span>|<span data-ttu-id="76d3e-115">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="76d3e-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="76d3e-116">credentialType</span><span class="sxs-lookup"><span data-stu-id="76d3e-116">credentialType</span></span>|<span data-ttu-id="76d3e-117">Dies ist optional.</span><span class="sxs-lookup"><span data-stu-id="76d3e-117">Optional.</span></span> <span data-ttu-id="76d3e-118">Gibt den Typ von Anmeldeinformationen an, die zum Überprüfen von über den Peertransport gesendeten Nachrichten verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="76d3e-118">Specifies the type of credentials used to verify messages sent with the peer transport.</span></span> <span data-ttu-id="76d3e-119">Dieses Attribut ist vom Typ <xref:System.ServiceModel.PeerTransportCredentialType>.</span><span class="sxs-lookup"><span data-stu-id="76d3e-119">This attribute is of type <xref:System.ServiceModel.PeerTransportCredentialType>.</span></span>|  
  
## <a name="credentialtype-attribute"></a><span data-ttu-id="76d3e-120">credentialType-Attribut</span><span class="sxs-lookup"><span data-stu-id="76d3e-120">credentialType Attribute</span></span>  
  
|<span data-ttu-id="76d3e-121">Wert</span><span class="sxs-lookup"><span data-stu-id="76d3e-121">Value</span></span>|<span data-ttu-id="76d3e-122">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="76d3e-122">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="76d3e-123">Zertifikat</span><span class="sxs-lookup"><span data-stu-id="76d3e-123">Certificate</span></span>|<span data-ttu-id="76d3e-124">Zur Authentifizierung des Peerkanaltransports ist ein X509-Zertifikat erforderlich.</span><span class="sxs-lookup"><span data-stu-id="76d3e-124">Authentication of the peer channel transport requires an X509 certificate.</span></span>|  
|<span data-ttu-id="76d3e-125">Kennwort</span><span class="sxs-lookup"><span data-stu-id="76d3e-125">Password</span></span>|<span data-ttu-id="76d3e-126">Zur Authentifizierung des Peerkanaltransports ist ein korrektes Kennwort erforderlich.</span><span class="sxs-lookup"><span data-stu-id="76d3e-126">Authentication of the peer channel transport requires a correct password.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="76d3e-127">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="76d3e-127">Child Elements</span></span>  
 <span data-ttu-id="76d3e-128">Keiner</span><span class="sxs-lookup"><span data-stu-id="76d3e-128">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="76d3e-129">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="76d3e-129">Parent Elements</span></span>  
  
|<span data-ttu-id="76d3e-130">Element</span><span class="sxs-lookup"><span data-stu-id="76d3e-130">Element</span></span>|<span data-ttu-id="76d3e-131">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="76d3e-131">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="76d3e-132">\<security></span><span class="sxs-lookup"><span data-stu-id="76d3e-132">\<security></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/security-of-netpeerbinding.md)|<span data-ttu-id="76d3e-133">Definiert die Sicherheitseinstellungen für die [ \<NetPeerTcpBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/netpeertcpbinding.md).</span><span class="sxs-lookup"><span data-stu-id="76d3e-133">Defines the security settings for the [\<netPeerTcpBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/netpeertcpbinding.md).</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="76d3e-134">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="76d3e-134">See also</span></span>

- <xref:System.ServiceModel.Configuration.PeerTransportSecurityElement>
- <xref:System.ServiceModel.PeerSecuritySettings.Transport%2A>
- <xref:System.ServiceModel.Configuration.PeerSecurityElement.Transport%2A>
- <xref:System.ServiceModel.PeerTransportSecuritySettings>
- [<span data-ttu-id="76d3e-135">Sichern von Diensten und Clients</span><span class="sxs-lookup"><span data-stu-id="76d3e-135">Securing Services and Clients</span></span>](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="76d3e-136">Bindungen</span><span class="sxs-lookup"><span data-stu-id="76d3e-136">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)
- [<span data-ttu-id="76d3e-137">Konfigurieren der vom System bereitgestellten Bindungen</span><span class="sxs-lookup"><span data-stu-id="76d3e-137">Configuring System-Provided Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="76d3e-138">Verwenden von Bindungen, um Dienste und Clients zu konfigurieren</span><span class="sxs-lookup"><span data-stu-id="76d3e-138">Using Bindings to Configure Services and Clients</span></span>](../../../../../docs/framework/wcf/using-bindings-to-configure-services-and-clients.md)
- [<span data-ttu-id="76d3e-139">\<binding></span><span class="sxs-lookup"><span data-stu-id="76d3e-139">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)
