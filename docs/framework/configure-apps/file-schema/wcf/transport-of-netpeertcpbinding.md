---
title: <transport> von <netPeerTcpBinding>
ms.date: 03/30/2017
ms.assetid: c44d86d2-1160-44d7-9c7a-297b12eccc7f
ms.openlocfilehash: 49b31a889d192d190125214e89ba09305114eb7f
ms.sourcegitcommit: 22be09204266253d45ece46f51cc6f080f2b3fd6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/07/2019
ms.locfileid: "73735973"
---
# <a name="transport-of-netpeertcpbinding"></a><span data-ttu-id="a86dd-102">\<Transport > von \<netpeer ertcpbinding ></span><span class="sxs-lookup"><span data-stu-id="a86dd-102">\<transport> of \<netPeerTcpBinding></span></span>
<span data-ttu-id="a86dd-103">Gibt Einstellungen für die Sicherheit auf Transport Ebene an, wenn die [\<NetPeerTcpBinding->](netpeertcpbinding.md)verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="a86dd-103">Specifies settings for transport level security when using the [\<netPeerTcpBinding>](netpeertcpbinding.md).</span></span>  
  
<span data-ttu-id="a86dd-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="a86dd-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="a86dd-105">&nbsp; &nbsp;[ **\<system. Service Model->** ](system-servicemodel.md) </span><span class="sxs-lookup"><span data-stu-id="a86dd-105">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="a86dd-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Bindungen >** ](bindings.md)</span><span class="sxs-lookup"><span data-stu-id="a86dd-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)</span></span>\
<span data-ttu-id="a86dd-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<netpeer ertcpbinding >** ](netpeertcpbinding.md)</span><span class="sxs-lookup"><span data-stu-id="a86dd-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<netPeerTcpBinding>**](netpeertcpbinding.md)</span></span>\
<span data-ttu-id="a86dd-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<**Bindungs >** </span><span class="sxs-lookup"><span data-stu-id="a86dd-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**</span></span>\
<span data-ttu-id="a86dd-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Sicherheit >** ](security-of-netpeerbinding.md)</span><span class="sxs-lookup"><span data-stu-id="a86dd-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<security>**](security-of-netpeerbinding.md)</span></span>\
<span data-ttu-id="a86dd-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<**Transport >**</span><span class="sxs-lookup"><span data-stu-id="a86dd-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<transport>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a86dd-111">Syntax</span><span class="sxs-lookup"><span data-stu-id="a86dd-111">Syntax</span></span>  
  
```xml  
<netPeerTcpBinding>
  <binding>
    <security>
      <transport credentialType="Certificate/Password" />
    </security>
  </binding>
</netPeerTcpBinding>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="a86dd-112">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="a86dd-112">Attributes and Elements</span></span>  
 <span data-ttu-id="a86dd-113">In den folgenden Abschnitten werden Attribute, untergeordnete Elemente sowie übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="a86dd-113">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="a86dd-114">Attribute</span><span class="sxs-lookup"><span data-stu-id="a86dd-114">Attributes</span></span>  
  
|<span data-ttu-id="a86dd-115">Attribut</span><span class="sxs-lookup"><span data-stu-id="a86dd-115">Attribute</span></span>|<span data-ttu-id="a86dd-116">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="a86dd-116">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="a86dd-117">credentialType</span><span class="sxs-lookup"><span data-stu-id="a86dd-117">credentialType</span></span>|<span data-ttu-id="a86dd-118">Dies ist optional.</span><span class="sxs-lookup"><span data-stu-id="a86dd-118">Optional.</span></span> <span data-ttu-id="a86dd-119">Gibt den Typ von Anmeldeinformationen an, die zum Überprüfen von über den Peertransport gesendeten Nachrichten verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="a86dd-119">Specifies the type of credentials used to verify messages sent with the peer transport.</span></span> <span data-ttu-id="a86dd-120">Dieses Attribut ist vom Typ <xref:System.ServiceModel.PeerTransportCredentialType>.</span><span class="sxs-lookup"><span data-stu-id="a86dd-120">This attribute is of type <xref:System.ServiceModel.PeerTransportCredentialType>.</span></span>|  
  
## <a name="credentialtype-attribute"></a><span data-ttu-id="a86dd-121">credentialType-Attribut</span><span class="sxs-lookup"><span data-stu-id="a86dd-121">credentialType Attribute</span></span>  
  
|<span data-ttu-id="a86dd-122">Wert</span><span class="sxs-lookup"><span data-stu-id="a86dd-122">Value</span></span>|<span data-ttu-id="a86dd-123">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="a86dd-123">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="a86dd-124">Zertifikat</span><span class="sxs-lookup"><span data-stu-id="a86dd-124">Certificate</span></span>|<span data-ttu-id="a86dd-125">Zur Authentifizierung des Peerkanaltransports ist ein X509-Zertifikat erforderlich.</span><span class="sxs-lookup"><span data-stu-id="a86dd-125">Authentication of the peer channel transport requires an X509 certificate.</span></span>|  
|<span data-ttu-id="a86dd-126">Kennwort</span><span class="sxs-lookup"><span data-stu-id="a86dd-126">Password</span></span>|<span data-ttu-id="a86dd-127">Zur Authentifizierung des Peerkanaltransports ist ein korrektes Kennwort erforderlich.</span><span class="sxs-lookup"><span data-stu-id="a86dd-127">Authentication of the peer channel transport requires a correct password.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="a86dd-128">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="a86dd-128">Child Elements</span></span>  
 <span data-ttu-id="a86dd-129">Keiner</span><span class="sxs-lookup"><span data-stu-id="a86dd-129">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="a86dd-130">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="a86dd-130">Parent Elements</span></span>  
  
|<span data-ttu-id="a86dd-131">Element</span><span class="sxs-lookup"><span data-stu-id="a86dd-131">Element</span></span>|<span data-ttu-id="a86dd-132">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="a86dd-132">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="a86dd-133">\<Security ></span><span class="sxs-lookup"><span data-stu-id="a86dd-133">\<security></span></span>](security-of-netpeerbinding.md)|<span data-ttu-id="a86dd-134">Definiert die Sicherheitseinstellungen für das [\<netpeer ertcpbinding->](netpeertcpbinding.md).</span><span class="sxs-lookup"><span data-stu-id="a86dd-134">Defines the security settings for the [\<netPeerTcpBinding>](netpeertcpbinding.md).</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="a86dd-135">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a86dd-135">See also</span></span>

- <xref:System.ServiceModel.Configuration.PeerTransportSecurityElement>
- <xref:System.ServiceModel.PeerSecuritySettings.Transport%2A>
- <xref:System.ServiceModel.Configuration.PeerSecurityElement.Transport%2A>
- <xref:System.ServiceModel.PeerTransportSecuritySettings>
- [<span data-ttu-id="a86dd-136">Sichern von Diensten und Clients</span><span class="sxs-lookup"><span data-stu-id="a86dd-136">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="a86dd-137">Bindungen</span><span class="sxs-lookup"><span data-stu-id="a86dd-137">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="a86dd-138">Konfigurieren der vom System bereitgestellten Bindungen</span><span class="sxs-lookup"><span data-stu-id="a86dd-138">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="a86dd-139">Verwenden von Bindungen, um Dienste und Clients zu konfigurieren</span><span class="sxs-lookup"><span data-stu-id="a86dd-139">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [<span data-ttu-id="a86dd-140">\<binding ></span><span class="sxs-lookup"><span data-stu-id="a86dd-140">\<binding></span></span>](bindings.md)
