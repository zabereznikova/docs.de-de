---
title: <security> von <netPeerBinding>
ms.date: 03/30/2017
ms.assetid: 1ef40d8c-f903-4426-9b08-da81462766d8
ms.openlocfilehash: 543c57d6b2dba1ff5934b49e0e219cf2e5cad153
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91170024"
---
# <a name="security-of-netpeerbinding"></a><span data-ttu-id="faf31-102">\<security> von \<netPeerBinding></span><span class="sxs-lookup"><span data-stu-id="faf31-102">\<security> of \<netPeerBinding></span></span>

<span data-ttu-id="faf31-103">Definiert die Sicherheitseinstellungen von [\<netPeerTcpBinding>](netpeertcpbinding.md) , einschließlich der Art der verwendeten Authentifizierung und der für den Nachrichten Transport verwendeten Sicherheit.</span><span class="sxs-lookup"><span data-stu-id="faf31-103">Defines the security settings of the [\<netPeerTcpBinding>](netpeertcpbinding.md), including the type of authentication used and the security used for the message transport.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<netPeerTcpBinding>**](netpeertcpbinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<security>**  
  
## <a name="syntax"></a><span data-ttu-id="faf31-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="faf31-104">Syntax</span></span>  
  
```xml  
<netPeerBinding>
  <binding>
    <security mode="Message/None/Transport//TransportWithMessageCredential">
      <transport credentialType="Certificate/Password" />
    </security>
  </binding>
</netPeerBinding>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="faf31-105">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="faf31-105">Attributes and Elements</span></span>  

 <span data-ttu-id="faf31-106">In den folgenden Abschnitten werden Attribute, untergeordnete Elemente sowie übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="faf31-106">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="faf31-107">Attributes</span><span class="sxs-lookup"><span data-stu-id="faf31-107">Attributes</span></span>  
  
|<span data-ttu-id="faf31-108">attribute</span><span class="sxs-lookup"><span data-stu-id="faf31-108">Attribute</span></span>|<span data-ttu-id="faf31-109">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="faf31-109">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="faf31-110">Modus</span><span class="sxs-lookup"><span data-stu-id="faf31-110">mode</span></span>|<span data-ttu-id="faf31-111">Dies ist optional.</span><span class="sxs-lookup"><span data-stu-id="faf31-111">Optional.</span></span> <span data-ttu-id="faf31-112">Gibt den Sicherheitstyp an, der von Peers verwendet wird, die mit dieser Bindung konfiguriert sind.</span><span class="sxs-lookup"><span data-stu-id="faf31-112">Specifies the type of security used by peers configured with this binding.</span></span> <span data-ttu-id="faf31-113">Standardwert: `Message`.</span><span class="sxs-lookup"><span data-stu-id="faf31-113">The default value is `Message`.</span></span> <span data-ttu-id="faf31-114">Dieses Attribut ist vom Typ <xref:System.ServiceModel.SecurityMode>.</span><span class="sxs-lookup"><span data-stu-id="faf31-114">This attribute is of type <xref:System.ServiceModel.SecurityMode>.</span></span>|  
  
## <a name="mode-attribute"></a><span data-ttu-id="faf31-115">mode-Attribut</span><span class="sxs-lookup"><span data-stu-id="faf31-115">mode Attribute</span></span>  
  
|<span data-ttu-id="faf31-116">Wert</span><span class="sxs-lookup"><span data-stu-id="faf31-116">Value</span></span>|<span data-ttu-id="faf31-117">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="faf31-117">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="faf31-118">`Message`</span><span class="sxs-lookup"><span data-stu-id="faf31-118">Message</span></span>|<span data-ttu-id="faf31-119">Durch die SOAP-Sicherheit werden Authentifizierung, Integrität und Vertraulichkeit bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="faf31-119">SOAP security provides authentication, integrity and confidentiality.</span></span>|  
|<span data-ttu-id="faf31-120">Keine</span><span class="sxs-lookup"><span data-stu-id="faf31-120">None</span></span>|<span data-ttu-id="faf31-121">Die Sicherheitsfunktionen sind deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="faf31-121">Security is disabled.</span></span>|  
|<span data-ttu-id="faf31-122">Transport</span><span class="sxs-lookup"><span data-stu-id="faf31-122">Transport</span></span>|<span data-ttu-id="faf31-123">Die Sicherheit wird über HTTPS bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="faf31-123">Security is provided using HTTPS.</span></span>|  
|<span data-ttu-id="faf31-124">TransportWithMessageCredential</span><span class="sxs-lookup"><span data-stu-id="faf31-124">TransportWithMessageCredential</span></span>|<span data-ttu-id="faf31-125">HTTPS stellt Authentifizierung und Vertraulichkeit bereit.</span><span class="sxs-lookup"><span data-stu-id="faf31-125">HTTPS provides authentication and confidentiality.</span></span> <span data-ttu-id="faf31-126">Die SOAP-Nachrichten bieten umfassende Anmeldeinformationstypen.</span><span class="sxs-lookup"><span data-stu-id="faf31-126">SOAP messages provide rich credential types.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="faf31-127">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="faf31-127">Child Elements</span></span>  
  
|<span data-ttu-id="faf31-128">Element</span><span class="sxs-lookup"><span data-stu-id="faf31-128">Element</span></span>|<span data-ttu-id="faf31-129">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="faf31-129">Description</span></span>|  
|-------------|-----------------|  
|[\<transport>](transport-of-netpeertcpbinding.md)|<span data-ttu-id="faf31-130">Definiert den Transporttyp für gesicherte Nachrichten, die von Peers gesendet werden, die mit dieser Bindung konfiguriert sind.</span><span class="sxs-lookup"><span data-stu-id="faf31-130">Defines the transport type for secured messages sent by peers configured with this binding.</span></span> <span data-ttu-id="faf31-131">Dieses Element ist vom Typ <xref:System.ServiceModel.Configuration.PeerTransportSecurityElement>.</span><span class="sxs-lookup"><span data-stu-id="faf31-131">This element is of type <xref:System.ServiceModel.Configuration.PeerTransportSecurityElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="faf31-132">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="faf31-132">Parent Elements</span></span>  
  
|<span data-ttu-id="faf31-133">Element</span><span class="sxs-lookup"><span data-stu-id="faf31-133">Element</span></span>|<span data-ttu-id="faf31-134">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="faf31-134">Description</span></span>|  
|-------------|-----------------|  
|[\<binding>](bindings.md)|<span data-ttu-id="faf31-135">Definiert alle Bindungsfunktionen von [\<netPeerTcpBinding>](netpeertcpbinding.md) .</span><span class="sxs-lookup"><span data-stu-id="faf31-135">Defines all binding capabilities of the [\<netPeerTcpBinding>](netpeertcpbinding.md).</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="faf31-136">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="faf31-136">Remarks</span></span>  

 <span data-ttu-id="faf31-137">Sicherheit kann entweder nachrichten- oder transportspezifisch sein.</span><span class="sxs-lookup"><span data-stu-id="faf31-137">Security can be either message- or transport-specific.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="faf31-138">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="faf31-138">See also</span></span>

- <xref:System.ServiceModel.Configuration.PeerSecurityElement>
- <xref:System.ServiceModel.NetPeerTcpBinding.Security%2A>
- <xref:System.ServiceModel.Configuration.NetPeerTcpBindingElement.Security%2A>
- <xref:System.ServiceModel.PeerSecuritySettings>
- [<span data-ttu-id="faf31-139">Sichern von Diensten und Clients</span><span class="sxs-lookup"><span data-stu-id="faf31-139">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="faf31-140">Wählen eines Typs von Anmeldeinformationen</span><span class="sxs-lookup"><span data-stu-id="faf31-140">Selecting a Credential Type</span></span>](../../../wcf/feature-details/selecting-a-credential-type.md)
- [<span data-ttu-id="faf31-141">Bindungen</span><span class="sxs-lookup"><span data-stu-id="faf31-141">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="faf31-142">Konfigurieren der vom System bereitgestellten Bindungen</span><span class="sxs-lookup"><span data-stu-id="faf31-142">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="faf31-143">Verwenden von Bindungen, um Dienste und Clients zu konfigurieren</span><span class="sxs-lookup"><span data-stu-id="faf31-143">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [\<binding>](bindings.md)
