---
title: <security> von <peerTransport>
ms.date: 03/30/2017
ms.assetid: f73634ed-f896-4968-bf74-5e5ac52d3b6b
ms.openlocfilehash: 270ca844f586be256b6483653c868d1cc4396657
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/06/2019
ms.locfileid: "70399764"
---
# <a name="security-of-peertransport"></a><span data-ttu-id="d01ba-102">\<Sicherheits > von \<"Peer Transport" ></span><span class="sxs-lookup"><span data-stu-id="d01ba-102">\<security> of \<peerTransport></span></span>
<span data-ttu-id="d01ba-103">Enthält die einem Peerkanal zugeordneten Sicherheitseinstellungen, einschließlich für den Nachrichtentransport verwendeter Authentifizierungstyp und verwendete Sicherheit.</span><span class="sxs-lookup"><span data-stu-id="d01ba-103">Contains the security settings associated with a peer channel, including the type of authentication used and the security used for the message transport.</span></span>  
  
<span data-ttu-id="d01ba-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="d01ba-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="d01ba-105">&nbsp;&nbsp;[ **\<System. Service Model->** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="d01ba-105">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="d01ba-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Bindungen >** ](bindings.md)</span><span class="sxs-lookup"><span data-stu-id="d01ba-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)</span></span>\
<span data-ttu-id="d01ba-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<CustomBinding->** ](custombinding.md)</span><span class="sxs-lookup"><span data-stu-id="d01ba-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<customBinding>**](custombinding.md)</span></span>\
<span data-ttu-id="d01ba-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<Bindungs >** </span><span class="sxs-lookup"><span data-stu-id="d01ba-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**</span></span>\
<span data-ttu-id="d01ba-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Peer Transport->** ](peertransport.md)</span><span class="sxs-lookup"><span data-stu-id="d01ba-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<peerTransport>**](peertransport.md)</span></span>\
<span data-ttu-id="d01ba-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<Sicherheits >**</span><span class="sxs-lookup"><span data-stu-id="d01ba-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<security>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d01ba-111">Syntax</span><span class="sxs-lookup"><span data-stu-id="d01ba-111">Syntax</span></span>  
  
```xml  
<security mode="None/Transport/Message/TransportWithMessageCredential">
  <transport clientCredentialType="None/Windows/UserName/Certificate/CardSpace" />
</security
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="d01ba-112">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="d01ba-112">Attributes and Elements</span></span>  
 <span data-ttu-id="d01ba-113">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="d01ba-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="d01ba-114">Attribute</span><span class="sxs-lookup"><span data-stu-id="d01ba-114">Attributes</span></span>  
  
|<span data-ttu-id="d01ba-115">Attribut</span><span class="sxs-lookup"><span data-stu-id="d01ba-115">Attribute</span></span>|<span data-ttu-id="d01ba-116">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="d01ba-116">Description</span></span>|  
|---------------|-----------------|  
|`mode`|<span data-ttu-id="d01ba-117">Gibt den Typ der anzuwendenden Sicherheit an.</span><span class="sxs-lookup"><span data-stu-id="d01ba-117">Specifies the type of security to be applied.</span></span> <span data-ttu-id="d01ba-118">Der Standardwert ist Nachricht.</span><span class="sxs-lookup"><span data-stu-id="d01ba-118">The default value is Message.</span></span> <span data-ttu-id="d01ba-119">Dieses Attribut ist vom Typ <xref:System.ServiceModel.SecurityMode>.</span><span class="sxs-lookup"><span data-stu-id="d01ba-119">This attribute is of type <xref:System.ServiceModel.SecurityMode>.</span></span>|  
  
## <a name="mode-attribute"></a><span data-ttu-id="d01ba-120">mode-Attribut</span><span class="sxs-lookup"><span data-stu-id="d01ba-120">mode Attribute</span></span>  
  
|<span data-ttu-id="d01ba-121">Wert</span><span class="sxs-lookup"><span data-stu-id="d01ba-121">Value</span></span>|<span data-ttu-id="d01ba-122">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="d01ba-122">Description</span></span>|  
|-----------|-----------------|  
|`None`|<span data-ttu-id="d01ba-123">Die Sicherheitsfunktionen sind deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="d01ba-123">Security is disabled.</span></span>|  
|`Transport`|<span data-ttu-id="d01ba-124">Die Sicherheit wird über HTTPS bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="d01ba-124">Security is provided using HTTPS.</span></span>|  
|`Message`|<span data-ttu-id="d01ba-125">Durch die SOAP-Sicherheit werden Authentifizierung, Integrität und Vertraulichkeit bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="d01ba-125">SOAP security provides authentication, integrity and confidentiality.</span></span>|  
|`TransportWithMessageCredential`|<span data-ttu-id="d01ba-126">HTTPS stellt Authentifizierung und Vertraulichkeit bereit.</span><span class="sxs-lookup"><span data-stu-id="d01ba-126">HTTPS provides authentication and confidentiality.</span></span> <span data-ttu-id="d01ba-127">Die SOAP-Nachrichten bieten umfassende Anmeldeinformationstypen.</span><span class="sxs-lookup"><span data-stu-id="d01ba-127">SOAP messages provide rich credential types.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="d01ba-128">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="d01ba-128">Child Elements</span></span>  
  
|<span data-ttu-id="d01ba-129">Element</span><span class="sxs-lookup"><span data-stu-id="d01ba-129">Element</span></span>|<span data-ttu-id="d01ba-130">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="d01ba-130">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="d01ba-131">\<transport></span><span class="sxs-lookup"><span data-stu-id="d01ba-131">\<transport></span></span>](transport-of-peertransport.md)|<span data-ttu-id="d01ba-132">Definiert einen Peertransport für eine benutzerdefinierte Bindung.</span><span class="sxs-lookup"><span data-stu-id="d01ba-132">Defines a peer transport for a custom binding.</span></span> <span data-ttu-id="d01ba-133">Dieses Element enthält ein `clientCredentialType`-Attribut, das die für die Interaktion mit einem Dienst zu verwendenden Anmeldeinformationen angibt.</span><span class="sxs-lookup"><span data-stu-id="d01ba-133">This element has a `clientCredentialType` attribute that specifies the credentials to be used when interacting with a service.</span></span> <span data-ttu-id="d01ba-134">Dieses Attribut ist vom Typ <xref:System.ServiceModel.PeerTransportCredentialType>.</span><span class="sxs-lookup"><span data-stu-id="d01ba-134">This attribute is of type <xref:System.ServiceModel.PeerTransportCredentialType>.</span></span><br /><br /> <span data-ttu-id="d01ba-135">Dieses Element ist vom Typ <xref:System.ServiceModel.Configuration.PeerTransportSecurityElement>.</span><span class="sxs-lookup"><span data-stu-id="d01ba-135">This element is of type <xref:System.ServiceModel.Configuration.PeerTransportSecurityElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="d01ba-136">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="d01ba-136">Parent Elements</span></span>  
  
|<span data-ttu-id="d01ba-137">Element</span><span class="sxs-lookup"><span data-stu-id="d01ba-137">Element</span></span>|<span data-ttu-id="d01ba-138">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="d01ba-138">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="d01ba-139">\<peerTransport></span><span class="sxs-lookup"><span data-stu-id="d01ba-139">\<peerTransport></span></span>](peertransport.md)|<span data-ttu-id="d01ba-140">Definiert einen Peertransport für eine benutzerdefinierte Bindung.</span><span class="sxs-lookup"><span data-stu-id="d01ba-140">Defines a peer transport for a custom binding.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="d01ba-141">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d01ba-141">See also</span></span>

- <xref:System.ServiceModel.Configuration.PeerSecurityElement>
- <xref:System.ServiceModel.PeerSecuritySettings>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [<span data-ttu-id="d01ba-142">Transportsicherheit</span><span class="sxs-lookup"><span data-stu-id="d01ba-142">Transport Security</span></span>](../../../wcf/feature-details/transport-security.md)
- [<span data-ttu-id="d01ba-143">Transportprotokolle</span><span class="sxs-lookup"><span data-stu-id="d01ba-143">Transports</span></span>](../../../wcf/feature-details/transports.md)
- [<span data-ttu-id="d01ba-144">Auswählen eines Transports</span><span class="sxs-lookup"><span data-stu-id="d01ba-144">Choosing a Transport</span></span>](../../../wcf/feature-details/choosing-a-transport.md)
- [<span data-ttu-id="d01ba-145">Bindungen</span><span class="sxs-lookup"><span data-stu-id="d01ba-145">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="d01ba-146">Erweitern von Bindungen</span><span class="sxs-lookup"><span data-stu-id="d01ba-146">Extending Bindings</span></span>](../../../wcf/extending/extending-bindings.md)
- [<span data-ttu-id="d01ba-147">Benutzerdefinierte Bindungen</span><span class="sxs-lookup"><span data-stu-id="d01ba-147">Custom Bindings</span></span>](../../../wcf/extending/custom-bindings.md)
- [<span data-ttu-id="d01ba-148">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="d01ba-148">\<customBinding></span></span>](custombinding.md)
