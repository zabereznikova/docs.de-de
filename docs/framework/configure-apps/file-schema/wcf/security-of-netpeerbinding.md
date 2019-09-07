---
title: <security> von <netPeerBinding>
ms.date: 03/30/2017
ms.assetid: 1ef40d8c-f903-4426-9b08-da81462766d8
ms.openlocfilehash: 88aa2898472c20c9e52cfd5830c0e41e8ea9ba21
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/06/2019
ms.locfileid: "70399818"
---
# <a name="security-of-netpeerbinding"></a><span data-ttu-id="89565-102">\<Sicherheits > von \<netperbinding ></span><span class="sxs-lookup"><span data-stu-id="89565-102">\<security> of \<netPeerBinding></span></span>
<span data-ttu-id="89565-103">Definiert die Sicherheitseinstellungen des [ \<netpeer ertcpbinding->](netpeertcpbinding.md), einschließlich des verwendeten Authentifizierungs Typs und der für den Nachrichten Transport verwendeten Sicherheit.</span><span class="sxs-lookup"><span data-stu-id="89565-103">Defines the security settings of the [\<netPeerTcpBinding>](netpeertcpbinding.md), including the type of authentication used and the security used for the message transport.</span></span>  
  
<span data-ttu-id="89565-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="89565-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="89565-105">&nbsp;&nbsp;[ **\<System. Service Model->** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="89565-105">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="89565-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Bindungen >** ](bindings.md)</span><span class="sxs-lookup"><span data-stu-id="89565-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)</span></span>\
<span data-ttu-id="89565-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<netpertcpbinding->** ](netpeertcpbinding.md)</span><span class="sxs-lookup"><span data-stu-id="89565-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<netPeerTcpBinding>**](netpeertcpbinding.md)</span></span>\
<span data-ttu-id="89565-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<Bindungs >** </span><span class="sxs-lookup"><span data-stu-id="89565-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**</span></span>\
<span data-ttu-id="89565-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<Sicherheits >**</span><span class="sxs-lookup"><span data-stu-id="89565-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<security>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="89565-110">Syntax</span><span class="sxs-lookup"><span data-stu-id="89565-110">Syntax</span></span>  
  
```xml  
<netPeerBinding>
  <binding>
    <security mode="Message/None/Transport//TransportWithMessageCredential">
      <transport credentialType="Certificate/Password" />
    </security>
  </binding>
</netPeerBinding>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="89565-111">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="89565-111">Attributes and Elements</span></span>  
 <span data-ttu-id="89565-112">In den folgenden Abschnitten werden Attribute, untergeordnete Elemente sowie übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="89565-112">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="89565-113">Attribute</span><span class="sxs-lookup"><span data-stu-id="89565-113">Attributes</span></span>  
  
|<span data-ttu-id="89565-114">Attribut</span><span class="sxs-lookup"><span data-stu-id="89565-114">Attribute</span></span>|<span data-ttu-id="89565-115">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="89565-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="89565-116">Modus</span><span class="sxs-lookup"><span data-stu-id="89565-116">mode</span></span>|<span data-ttu-id="89565-117">Optional.</span><span class="sxs-lookup"><span data-stu-id="89565-117">Optional.</span></span> <span data-ttu-id="89565-118">Gibt den Sicherheitstyp an, der von Peers verwendet wird, die mit dieser Bindung konfiguriert sind.</span><span class="sxs-lookup"><span data-stu-id="89565-118">Specifies the type of security used by peers configured with this binding.</span></span> <span data-ttu-id="89565-119">Der Standardwert ist `Message`.</span><span class="sxs-lookup"><span data-stu-id="89565-119">The default value is `Message`.</span></span> <span data-ttu-id="89565-120">Dieses Attribut ist vom Typ <xref:System.ServiceModel.SecurityMode>.</span><span class="sxs-lookup"><span data-stu-id="89565-120">This attribute is of type <xref:System.ServiceModel.SecurityMode>.</span></span>|  
  
## <a name="mode-attribute"></a><span data-ttu-id="89565-121">mode-Attribut</span><span class="sxs-lookup"><span data-stu-id="89565-121">mode Attribute</span></span>  
  
|<span data-ttu-id="89565-122">Wert</span><span class="sxs-lookup"><span data-stu-id="89565-122">Value</span></span>|<span data-ttu-id="89565-123">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="89565-123">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="89565-124">Meldung</span><span class="sxs-lookup"><span data-stu-id="89565-124">Message</span></span>|<span data-ttu-id="89565-125">Durch die SOAP-Sicherheit werden Authentifizierung, Integrität und Vertraulichkeit bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="89565-125">SOAP security provides authentication, integrity and confidentiality.</span></span>|  
|<span data-ttu-id="89565-126">None</span><span class="sxs-lookup"><span data-stu-id="89565-126">None</span></span>|<span data-ttu-id="89565-127">Die Sicherheitsfunktionen sind deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="89565-127">Security is disabled.</span></span>|  
|<span data-ttu-id="89565-128">Transport</span><span class="sxs-lookup"><span data-stu-id="89565-128">Transport</span></span>|<span data-ttu-id="89565-129">Die Sicherheit wird über HTTPS bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="89565-129">Security is provided using HTTPS.</span></span>|  
|<span data-ttu-id="89565-130">TransportWithMessageCredential</span><span class="sxs-lookup"><span data-stu-id="89565-130">TransportWithMessageCredential</span></span>|<span data-ttu-id="89565-131">HTTPS stellt Authentifizierung und Vertraulichkeit bereit.</span><span class="sxs-lookup"><span data-stu-id="89565-131">HTTPS provides authentication and confidentiality.</span></span> <span data-ttu-id="89565-132">Die SOAP-Nachrichten bieten umfassende Anmeldeinformationstypen.</span><span class="sxs-lookup"><span data-stu-id="89565-132">SOAP messages provide rich credential types.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="89565-133">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="89565-133">Child Elements</span></span>  
  
|<span data-ttu-id="89565-134">Element</span><span class="sxs-lookup"><span data-stu-id="89565-134">Element</span></span>|<span data-ttu-id="89565-135">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="89565-135">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="89565-136">\<transport></span><span class="sxs-lookup"><span data-stu-id="89565-136">\<transport></span></span>](transport-of-netpeertcpbinding.md)|<span data-ttu-id="89565-137">Definiert den Transporttyp für gesicherte Nachrichten, die von Peers gesendet werden, die mit dieser Bindung konfiguriert sind.</span><span class="sxs-lookup"><span data-stu-id="89565-137">Defines the transport type for secured messages sent by peers configured with this binding.</span></span> <span data-ttu-id="89565-138">Dieses Element ist vom Typ <xref:System.ServiceModel.Configuration.PeerTransportSecurityElement>.</span><span class="sxs-lookup"><span data-stu-id="89565-138">This element is of type <xref:System.ServiceModel.Configuration.PeerTransportSecurityElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="89565-139">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="89565-139">Parent Elements</span></span>  
  
|<span data-ttu-id="89565-140">Element</span><span class="sxs-lookup"><span data-stu-id="89565-140">Element</span></span>|<span data-ttu-id="89565-141">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="89565-141">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="89565-142">\<binding></span><span class="sxs-lookup"><span data-stu-id="89565-142">\<binding></span></span>](../../../misc/binding.md)|<span data-ttu-id="89565-143">Definiert alle Bindungsfunktionen des [ \<netpeer ertcpbinding->](netpeertcpbinding.md).</span><span class="sxs-lookup"><span data-stu-id="89565-143">Defines all binding capabilities of the [\<netPeerTcpBinding>](netpeertcpbinding.md).</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="89565-144">Hinweise</span><span class="sxs-lookup"><span data-stu-id="89565-144">Remarks</span></span>  
 <span data-ttu-id="89565-145">Sicherheit kann entweder nachrichten- oder transportspezifisch sein.</span><span class="sxs-lookup"><span data-stu-id="89565-145">Security can be either message- or transport-specific.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="89565-146">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="89565-146">See also</span></span>

- <xref:System.ServiceModel.Configuration.PeerSecurityElement>
- <xref:System.ServiceModel.NetPeerTcpBinding.Security%2A>
- <xref:System.ServiceModel.Configuration.NetPeerTcpBindingElement.Security%2A>
- <xref:System.ServiceModel.PeerSecuritySettings>
- [<span data-ttu-id="89565-147">Sichern von Diensten und Clients</span><span class="sxs-lookup"><span data-stu-id="89565-147">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="89565-148">Ausählen eines Anmeldeinformationentyps</span><span class="sxs-lookup"><span data-stu-id="89565-148">Selecting a Credential Type</span></span>](../../../wcf/feature-details/selecting-a-credential-type.md)
- [<span data-ttu-id="89565-149">Bindungen</span><span class="sxs-lookup"><span data-stu-id="89565-149">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="89565-150">Konfigurieren der vom System bereitgestellten Bindungen</span><span class="sxs-lookup"><span data-stu-id="89565-150">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="89565-151">Verwenden von Bindungen, um Dienste und Clients zu konfigurieren</span><span class="sxs-lookup"><span data-stu-id="89565-151">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [<span data-ttu-id="89565-152">\<binding></span><span class="sxs-lookup"><span data-stu-id="89565-152">\<binding></span></span>](../../../misc/binding.md)
