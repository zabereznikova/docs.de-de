---
title: <transport> von <peerTransport>
ms.date: 03/30/2017
ms.assetid: d7116240-845c-4b6f-b203-262de6b597ef
ms.openlocfilehash: 3b2c7716727f58abb81bf4d58b13189ac170cf7c
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/06/2019
ms.locfileid: "70399288"
---
# <a name="transport-of-peertransport"></a><span data-ttu-id="3561d-102">\<Transport > von \<"Peer Transport" ></span><span class="sxs-lookup"><span data-stu-id="3561d-102">\<transport> of \<peerTransport></span></span>
<span data-ttu-id="3561d-103">Definiert den Transporttyp für gesicherte Nachrichten, die von Peers gesendet werden, die mit dieser Bindung konfiguriert sind.</span><span class="sxs-lookup"><span data-stu-id="3561d-103">Specifies the transport type for secured messages sent by peers configured with this binding.</span></span>  
  
<span data-ttu-id="3561d-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="3561d-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="3561d-105">&nbsp;&nbsp;[ **\<System. Service Model->** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="3561d-105">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="3561d-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Bindungen >** ](bindings.md)</span><span class="sxs-lookup"><span data-stu-id="3561d-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)</span></span>\
<span data-ttu-id="3561d-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<CustomBinding->** ](custombinding.md)</span><span class="sxs-lookup"><span data-stu-id="3561d-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<customBinding>**](custombinding.md)</span></span>\
<span data-ttu-id="3561d-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<Bindungs >** </span><span class="sxs-lookup"><span data-stu-id="3561d-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**</span></span>\
<span data-ttu-id="3561d-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Peer Transport->** ](peertransport.md)</span><span class="sxs-lookup"><span data-stu-id="3561d-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<peerTransport>**](peertransport.md)</span></span>\
<span data-ttu-id="3561d-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Sicherheits >** ](security-of-peertransport.md)</span><span class="sxs-lookup"><span data-stu-id="3561d-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<security>**](security-of-peertransport.md)</span></span>\
<span data-ttu-id="3561d-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<Transport >**</span><span class="sxs-lookup"><span data-stu-id="3561d-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<transport>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3561d-112">Syntax</span><span class="sxs-lookup"><span data-stu-id="3561d-112">Syntax</span></span>  
  
```xml  
<security>
  <transport credentialType="Certificate/Password" />
</security>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="3561d-113">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="3561d-113">Attributes and Elements</span></span>  
 <span data-ttu-id="3561d-114">In den folgenden Abschnitten werden Attribute, untergeordnete Elemente sowie übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="3561d-114">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="3561d-115">Attribute</span><span class="sxs-lookup"><span data-stu-id="3561d-115">Attributes</span></span>  
  
|<span data-ttu-id="3561d-116">Attribut</span><span class="sxs-lookup"><span data-stu-id="3561d-116">Attribute</span></span>|<span data-ttu-id="3561d-117">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="3561d-117">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="3561d-118">credentialType</span><span class="sxs-lookup"><span data-stu-id="3561d-118">credentialType</span></span>|<span data-ttu-id="3561d-119">Optional.</span><span class="sxs-lookup"><span data-stu-id="3561d-119">Optional.</span></span> <span data-ttu-id="3561d-120">Gibt den Typ von Anmeldeinformationen an, die zum Überprüfen von über den Peertransport gesendeten Nachrichten verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="3561d-120">Specifies the type of credentials used to verify messages sent with the peer transport.</span></span> <span data-ttu-id="3561d-121">Dieses Attribut ist vom Typ <xref:System.ServiceModel.PeerTransportCredentialType>.</span><span class="sxs-lookup"><span data-stu-id="3561d-121">This attribute is of type <xref:System.ServiceModel.PeerTransportCredentialType>.</span></span>|  
  
## <a name="credentialtype-attribute"></a><span data-ttu-id="3561d-122">credentialType-Attribut</span><span class="sxs-lookup"><span data-stu-id="3561d-122">credentialType Attribute</span></span>  
  
|<span data-ttu-id="3561d-123">Wert</span><span class="sxs-lookup"><span data-stu-id="3561d-123">Value</span></span>|<span data-ttu-id="3561d-124">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="3561d-124">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="3561d-125">Zertifikat</span><span class="sxs-lookup"><span data-stu-id="3561d-125">Certificate</span></span>|<span data-ttu-id="3561d-126">Zur Authentifizierung des Peerkanaltransports ist ein X509-Zertifikat erforderlich.</span><span class="sxs-lookup"><span data-stu-id="3561d-126">Authentication of the peer channel transport requires an X509 certificate.</span></span>|  
|<span data-ttu-id="3561d-127">Kennwort</span><span class="sxs-lookup"><span data-stu-id="3561d-127">Password</span></span>|<span data-ttu-id="3561d-128">Zur Authentifizierung des Peerkanaltransports ist ein korrektes Kennwort erforderlich.</span><span class="sxs-lookup"><span data-stu-id="3561d-128">Authentication of the peer channel transport requires a correct password.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="3561d-129">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="3561d-129">Child Elements</span></span>  
 <span data-ttu-id="3561d-130">None</span><span class="sxs-lookup"><span data-stu-id="3561d-130">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="3561d-131">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="3561d-131">Parent Elements</span></span>  
  
|<span data-ttu-id="3561d-132">Element</span><span class="sxs-lookup"><span data-stu-id="3561d-132">Element</span></span>|<span data-ttu-id="3561d-133">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="3561d-133">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="3561d-134">\<security></span><span class="sxs-lookup"><span data-stu-id="3561d-134">\<security></span></span>](security-of-peertransport.md)|<span data-ttu-id="3561d-135">Definiert die Sicherheitseinstellungen für einen Peertransport.</span><span class="sxs-lookup"><span data-stu-id="3561d-135">Defines the security settings for a peer transport.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3561d-136">Hinweise</span><span class="sxs-lookup"><span data-stu-id="3561d-136">Remarks</span></span>  
 <span data-ttu-id="3561d-137">Dieses Element wird nur festgelegt, wenn das Mode-Attribut von [ \<Security >](security-of-peertransport.md) auf `TransportWithMessageCredential` `Transport` oder festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="3561d-137">This element is set only if the mode attribute of [\<security>](security-of-peertransport.md) is set to `Transport` or `TransportWithMessageCredential`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3561d-138">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="3561d-138">See also</span></span>

- <xref:System.ServiceModel.Configuration.PeerTransportSecurityElement>
- <xref:System.ServiceModel.PeerSecuritySettings.Transport%2A>
- <xref:System.ServiceModel.PeerTransportSecuritySettings>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [<span data-ttu-id="3561d-139">Transportsicherheit</span><span class="sxs-lookup"><span data-stu-id="3561d-139">Transport Security</span></span>](../../../wcf/feature-details/transport-security.md)
- [<span data-ttu-id="3561d-140">Transportprotokolle</span><span class="sxs-lookup"><span data-stu-id="3561d-140">Transports</span></span>](../../../wcf/feature-details/transports.md)
- [<span data-ttu-id="3561d-141">Auswählen eines Transports</span><span class="sxs-lookup"><span data-stu-id="3561d-141">Choosing a Transport</span></span>](../../../wcf/feature-details/choosing-a-transport.md)
- [<span data-ttu-id="3561d-142">Bindungen</span><span class="sxs-lookup"><span data-stu-id="3561d-142">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="3561d-143">Erweitern von Bindungen</span><span class="sxs-lookup"><span data-stu-id="3561d-143">Extending Bindings</span></span>](../../../wcf/extending/extending-bindings.md)
- [<span data-ttu-id="3561d-144">Benutzerdefinierte Bindungen</span><span class="sxs-lookup"><span data-stu-id="3561d-144">Custom Bindings</span></span>](../../../wcf/extending/custom-bindings.md)
- [<span data-ttu-id="3561d-145">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="3561d-145">\<customBinding></span></span>](custombinding.md)
