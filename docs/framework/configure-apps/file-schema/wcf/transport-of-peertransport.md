---
title: <transport> von <peerTransport>
ms.date: 03/30/2017
ms.assetid: d7116240-845c-4b6f-b203-262de6b597ef
ms.openlocfilehash: 9b6f548515afbba5068659bd5c6f7f2b33f80cda
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59076002"
---
# <a name="transport-of-peertransport"></a><span data-ttu-id="ed671-102">\<Transport > von \<PeerTransport ></span><span class="sxs-lookup"><span data-stu-id="ed671-102">\<transport> of \<peerTransport></span></span>
<span data-ttu-id="ed671-103">Definiert den Transporttyp für gesicherte Nachrichten, die von Peers gesendet werden, die mit dieser Bindung konfiguriert sind.</span><span class="sxs-lookup"><span data-stu-id="ed671-103">Specifies the transport type for secured messages sent by peers configured with this binding.</span></span>  
  
 <span data-ttu-id="ed671-104">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="ed671-104">\<system.serviceModel></span></span>  
<span data-ttu-id="ed671-105">\<bindings></span><span class="sxs-lookup"><span data-stu-id="ed671-105">\<bindings></span></span>  
<span data-ttu-id="ed671-106">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="ed671-106">\<customBinding></span></span>  
<span data-ttu-id="ed671-107">\<binding></span><span class="sxs-lookup"><span data-stu-id="ed671-107">\<binding></span></span>  
<span data-ttu-id="ed671-108">\<peerTransport></span><span class="sxs-lookup"><span data-stu-id="ed671-108">\<peerTransport></span></span>  
<span data-ttu-id="ed671-109">\<security></span><span class="sxs-lookup"><span data-stu-id="ed671-109">\<security></span></span>  
<span data-ttu-id="ed671-110">\<transport></span><span class="sxs-lookup"><span data-stu-id="ed671-110">\<transport></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ed671-111">Syntax</span><span class="sxs-lookup"><span data-stu-id="ed671-111">Syntax</span></span>  
  
```xml  
<security>
  <transport credentialType="Certificate/Password" />
</security>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="ed671-112">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="ed671-112">Attributes and Elements</span></span>  
 <span data-ttu-id="ed671-113">In den folgenden Abschnitten werden Attribute, untergeordnete Elemente sowie übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="ed671-113">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="ed671-114">Attribute</span><span class="sxs-lookup"><span data-stu-id="ed671-114">Attributes</span></span>  
  
|<span data-ttu-id="ed671-115">Attribut</span><span class="sxs-lookup"><span data-stu-id="ed671-115">Attribute</span></span>|<span data-ttu-id="ed671-116">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="ed671-116">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="ed671-117">credentialType</span><span class="sxs-lookup"><span data-stu-id="ed671-117">credentialType</span></span>|<span data-ttu-id="ed671-118">Dies ist optional.</span><span class="sxs-lookup"><span data-stu-id="ed671-118">Optional.</span></span> <span data-ttu-id="ed671-119">Gibt den Typ von Anmeldeinformationen an, die zum Überprüfen von über den Peertransport gesendeten Nachrichten verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="ed671-119">Specifies the type of credentials used to verify messages sent with the peer transport.</span></span> <span data-ttu-id="ed671-120">Dieses Attribut ist vom Typ <xref:System.ServiceModel.PeerTransportCredentialType>.</span><span class="sxs-lookup"><span data-stu-id="ed671-120">This attribute is of type <xref:System.ServiceModel.PeerTransportCredentialType>.</span></span>|  
  
## <a name="credentialtype-attribute"></a><span data-ttu-id="ed671-121">credentialType-Attribut</span><span class="sxs-lookup"><span data-stu-id="ed671-121">credentialType Attribute</span></span>  
  
|<span data-ttu-id="ed671-122">Wert</span><span class="sxs-lookup"><span data-stu-id="ed671-122">Value</span></span>|<span data-ttu-id="ed671-123">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="ed671-123">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="ed671-124">Zertifikat</span><span class="sxs-lookup"><span data-stu-id="ed671-124">Certificate</span></span>|<span data-ttu-id="ed671-125">Zur Authentifizierung des Peerkanaltransports ist ein X509-Zertifikat erforderlich.</span><span class="sxs-lookup"><span data-stu-id="ed671-125">Authentication of the peer channel transport requires an X509 certificate.</span></span>|  
|<span data-ttu-id="ed671-126">Kennwort</span><span class="sxs-lookup"><span data-stu-id="ed671-126">Password</span></span>|<span data-ttu-id="ed671-127">Zur Authentifizierung des Peerkanaltransports ist ein korrektes Kennwort erforderlich.</span><span class="sxs-lookup"><span data-stu-id="ed671-127">Authentication of the peer channel transport requires a correct password.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="ed671-128">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="ed671-128">Child Elements</span></span>  
 <span data-ttu-id="ed671-129">Keiner</span><span class="sxs-lookup"><span data-stu-id="ed671-129">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="ed671-130">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="ed671-130">Parent Elements</span></span>  
  
|<span data-ttu-id="ed671-131">Element</span><span class="sxs-lookup"><span data-stu-id="ed671-131">Element</span></span>|<span data-ttu-id="ed671-132">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="ed671-132">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="ed671-133">\<security></span><span class="sxs-lookup"><span data-stu-id="ed671-133">\<security></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/security-of-peertransport.md)|<span data-ttu-id="ed671-134">Definiert die Sicherheitseinstellungen für einen Peertransport.</span><span class="sxs-lookup"><span data-stu-id="ed671-134">Defines the security settings for a peer transport.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ed671-135">Hinweise</span><span class="sxs-lookup"><span data-stu-id="ed671-135">Remarks</span></span>  
 <span data-ttu-id="ed671-136">Dieses Element wird nur festgelegt, wenn das Mode-Attribut des [ \<Sicherheit >](../../../../../docs/framework/configure-apps/file-schema/wcf/security-of-peertransport.md) nastaven NA hodnotu `Transport` oder `TransportWithMessageCredential`.</span><span class="sxs-lookup"><span data-stu-id="ed671-136">This element is set only if the mode attribute of [\<security>](../../../../../docs/framework/configure-apps/file-schema/wcf/security-of-peertransport.md) is set to `Transport` or `TransportWithMessageCredential`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ed671-137">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ed671-137">See also</span></span>

- <xref:System.ServiceModel.Configuration.PeerTransportSecurityElement>
- <xref:System.ServiceModel.PeerSecuritySettings.Transport%2A>
- <xref:System.ServiceModel.PeerTransportSecuritySettings>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [<span data-ttu-id="ed671-138">Transportsicherheit</span><span class="sxs-lookup"><span data-stu-id="ed671-138">Transport Security</span></span>](../../../../../docs/framework/wcf/feature-details/transport-security.md)
- [<span data-ttu-id="ed671-139">Transportprotokolle</span><span class="sxs-lookup"><span data-stu-id="ed671-139">Transports</span></span>](../../../../../docs/framework/wcf/feature-details/transports.md)
- [<span data-ttu-id="ed671-140">Wählen eines Transports</span><span class="sxs-lookup"><span data-stu-id="ed671-140">Choosing a Transport</span></span>](../../../../../docs/framework/wcf/feature-details/choosing-a-transport.md)
- [<span data-ttu-id="ed671-141">Bindungen</span><span class="sxs-lookup"><span data-stu-id="ed671-141">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)
- [<span data-ttu-id="ed671-142">Erweitern von Bindungen</span><span class="sxs-lookup"><span data-stu-id="ed671-142">Extending Bindings</span></span>](../../../../../docs/framework/wcf/extending/extending-bindings.md)
- [<span data-ttu-id="ed671-143">Benutzerdefinierte Bindungen</span><span class="sxs-lookup"><span data-stu-id="ed671-143">Custom Bindings</span></span>](../../../../../docs/framework/wcf/extending/custom-bindings.md)
- [<span data-ttu-id="ed671-144">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="ed671-144">\<customBinding></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)
