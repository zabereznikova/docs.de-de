---
title: <transport> von <peerTransport>
ms.date: 03/30/2017
ms.assetid: d7116240-845c-4b6f-b203-262de6b597ef
ms.openlocfilehash: 3dbeda5d418c30f378515fa83979eaca289370f9
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/30/2019
ms.locfileid: "55284010"
---
# <a name="transport-of-peertransport"></a><span data-ttu-id="3d2e6-102">\<Transport > von \<PeerTransport ></span><span class="sxs-lookup"><span data-stu-id="3d2e6-102">\<transport> of \<peerTransport></span></span>
<span data-ttu-id="3d2e6-103">Definiert den Transporttyp für gesicherte Nachrichten, die von Peers gesendet werden, die mit dieser Bindung konfiguriert sind.</span><span class="sxs-lookup"><span data-stu-id="3d2e6-103">Specifies the transport type for secured messages sent by peers configured with this binding.</span></span>  
  
 <span data-ttu-id="3d2e6-104">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="3d2e6-104">\<system.serviceModel></span></span>  
<span data-ttu-id="3d2e6-105">\<bindings></span><span class="sxs-lookup"><span data-stu-id="3d2e6-105">\<bindings></span></span>  
<span data-ttu-id="3d2e6-106">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="3d2e6-106">\<customBinding></span></span>  
<span data-ttu-id="3d2e6-107">\<binding></span><span class="sxs-lookup"><span data-stu-id="3d2e6-107">\<binding></span></span>  
<span data-ttu-id="3d2e6-108">\<peerTransport></span><span class="sxs-lookup"><span data-stu-id="3d2e6-108">\<peerTransport></span></span>  
<span data-ttu-id="3d2e6-109">\<security></span><span class="sxs-lookup"><span data-stu-id="3d2e6-109">\<security></span></span>  
<span data-ttu-id="3d2e6-110">\<transport></span><span class="sxs-lookup"><span data-stu-id="3d2e6-110">\<transport></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3d2e6-111">Syntax</span><span class="sxs-lookup"><span data-stu-id="3d2e6-111">Syntax</span></span>  
  
```xml  
<security>
  <transport credentialType="Certificate/Password" />
</security>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="3d2e6-112">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="3d2e6-112">Attributes and Elements</span></span>  
 <span data-ttu-id="3d2e6-113">In den folgenden Abschnitten werden Attribute, untergeordnete Elemente sowie übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="3d2e6-113">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="3d2e6-114">Attribute</span><span class="sxs-lookup"><span data-stu-id="3d2e6-114">Attributes</span></span>  
  
|<span data-ttu-id="3d2e6-115">Attribut</span><span class="sxs-lookup"><span data-stu-id="3d2e6-115">Attribute</span></span>|<span data-ttu-id="3d2e6-116">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="3d2e6-116">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="3d2e6-117">credentialType</span><span class="sxs-lookup"><span data-stu-id="3d2e6-117">credentialType</span></span>|<span data-ttu-id="3d2e6-118">Dies ist optional.</span><span class="sxs-lookup"><span data-stu-id="3d2e6-118">Optional.</span></span> <span data-ttu-id="3d2e6-119">Gibt den Typ von Anmeldeinformationen an, die zum Überprüfen von über den Peertransport gesendeten Nachrichten verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="3d2e6-119">Specifies the type of credentials used to verify messages sent with the peer transport.</span></span> <span data-ttu-id="3d2e6-120">Dieses Attribut ist vom Typ <xref:System.ServiceModel.PeerTransportCredentialType>.</span><span class="sxs-lookup"><span data-stu-id="3d2e6-120">This attribute is of type <xref:System.ServiceModel.PeerTransportCredentialType>.</span></span>|  
  
## <a name="credentialtype-attribute"></a><span data-ttu-id="3d2e6-121">credentialType-Attribut</span><span class="sxs-lookup"><span data-stu-id="3d2e6-121">credentialType Attribute</span></span>  
  
|<span data-ttu-id="3d2e6-122">Wert</span><span class="sxs-lookup"><span data-stu-id="3d2e6-122">Value</span></span>|<span data-ttu-id="3d2e6-123">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="3d2e6-123">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="3d2e6-124">Zertifikat</span><span class="sxs-lookup"><span data-stu-id="3d2e6-124">Certificate</span></span>|<span data-ttu-id="3d2e6-125">Zur Authentifizierung des Peerkanaltransports ist ein X509-Zertifikat erforderlich.</span><span class="sxs-lookup"><span data-stu-id="3d2e6-125">Authentication of the peer channel transport requires an X509 certificate.</span></span>|  
|<span data-ttu-id="3d2e6-126">Kennwort</span><span class="sxs-lookup"><span data-stu-id="3d2e6-126">Password</span></span>|<span data-ttu-id="3d2e6-127">Zur Authentifizierung des Peerkanaltransports ist ein korrektes Kennwort erforderlich.</span><span class="sxs-lookup"><span data-stu-id="3d2e6-127">Authentication of the peer channel transport requires a correct password.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="3d2e6-128">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="3d2e6-128">Child Elements</span></span>  
 <span data-ttu-id="3d2e6-129">Keine</span><span class="sxs-lookup"><span data-stu-id="3d2e6-129">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="3d2e6-130">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="3d2e6-130">Parent Elements</span></span>  
  
|<span data-ttu-id="3d2e6-131">Element</span><span class="sxs-lookup"><span data-stu-id="3d2e6-131">Element</span></span>|<span data-ttu-id="3d2e6-132">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="3d2e6-132">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="3d2e6-133">\<security></span><span class="sxs-lookup"><span data-stu-id="3d2e6-133">\<security></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/security-of-peertransport.md)|<span data-ttu-id="3d2e6-134">Definiert die Sicherheitseinstellungen für einen Peertransport.</span><span class="sxs-lookup"><span data-stu-id="3d2e6-134">Defines the security settings for a peer transport.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3d2e6-135">Hinweise</span><span class="sxs-lookup"><span data-stu-id="3d2e6-135">Remarks</span></span>  
 <span data-ttu-id="3d2e6-136">Dieses Element wird nur festgelegt, wenn das Mode-Attribut des [ \<Sicherheit >](../../../../../docs/framework/configure-apps/file-schema/wcf/security-of-peertransport.md) nastaven NA hodnotu `Transport` oder `TransportWithMessageCredential`.</span><span class="sxs-lookup"><span data-stu-id="3d2e6-136">This element is set only if the mode attribute of [\<security>](../../../../../docs/framework/configure-apps/file-schema/wcf/security-of-peertransport.md) is set to `Transport` or `TransportWithMessageCredential`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3d2e6-137">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="3d2e6-137">See also</span></span>
- <xref:System.ServiceModel.Configuration.PeerTransportSecurityElement>
- <xref:System.ServiceModel.PeerSecuritySettings.Transport%2A>
- <xref:System.ServiceModel.PeerTransportSecuritySettings>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [<span data-ttu-id="3d2e6-138">Transportsicherheit</span><span class="sxs-lookup"><span data-stu-id="3d2e6-138">Transport Security</span></span>](../../../../../docs/framework/wcf/feature-details/transport-security.md)
- [<span data-ttu-id="3d2e6-139">Transportprotokolle</span><span class="sxs-lookup"><span data-stu-id="3d2e6-139">Transports</span></span>](../../../../../docs/framework/wcf/feature-details/transports.md)
- [<span data-ttu-id="3d2e6-140">Auswählen eines Transports</span><span class="sxs-lookup"><span data-stu-id="3d2e6-140">Choosing a Transport</span></span>](../../../../../docs/framework/wcf/feature-details/choosing-a-transport.md)
- [<span data-ttu-id="3d2e6-141">Bindungen</span><span class="sxs-lookup"><span data-stu-id="3d2e6-141">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)
- [<span data-ttu-id="3d2e6-142">Erweitern von Bindungen</span><span class="sxs-lookup"><span data-stu-id="3d2e6-142">Extending Bindings</span></span>](../../../../../docs/framework/wcf/extending/extending-bindings.md)
- [<span data-ttu-id="3d2e6-143">Benutzerdefinierte Bindungen</span><span class="sxs-lookup"><span data-stu-id="3d2e6-143">Custom Bindings</span></span>](../../../../../docs/framework/wcf/extending/custom-bindings.md)
- [<span data-ttu-id="3d2e6-144">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="3d2e6-144">\<customBinding></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)
