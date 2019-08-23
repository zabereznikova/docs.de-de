---
title: <transport> von <netPeerTcpBinding>
ms.date: 03/30/2017
ms.assetid: c44d86d2-1160-44d7-9c7a-297b12eccc7f
ms.openlocfilehash: 837d01540fa63579877ab4085bd8034c78f2fbe0
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69915566"
---
# <a name="transport-of-netpeertcpbinding"></a><span data-ttu-id="b4375-102">\<Transport > von \<netpeer ertcpbinding ></span><span class="sxs-lookup"><span data-stu-id="b4375-102">\<transport> of \<netPeerTcpBinding></span></span>
<span data-ttu-id="b4375-103">Gibt Einstellungen für die Sicherheit auf Transport Ebene an, wenn die [ \<NetPeerTcpBinding->](netpeertcpbinding.md)verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="b4375-103">Specifies settings for transport level security when using the [\<netPeerTcpBinding>](netpeertcpbinding.md).</span></span>  
  
 <span data-ttu-id="b4375-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="b4375-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="b4375-105">\<bindings></span><span class="sxs-lookup"><span data-stu-id="b4375-105">\<bindings></span></span>  
<span data-ttu-id="b4375-106">\<netPeerTcpBinding></span><span class="sxs-lookup"><span data-stu-id="b4375-106">\<netPeerTcpBinding></span></span>  
<span data-ttu-id="b4375-107">\<binding></span><span class="sxs-lookup"><span data-stu-id="b4375-107">\<binding></span></span>  
<span data-ttu-id="b4375-108">\<security></span><span class="sxs-lookup"><span data-stu-id="b4375-108">\<security></span></span>  
<span data-ttu-id="b4375-109">\<transport></span><span class="sxs-lookup"><span data-stu-id="b4375-109">\<transport></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b4375-110">Syntax</span><span class="sxs-lookup"><span data-stu-id="b4375-110">Syntax</span></span>  
  
```xml  
<netPeerTcpBinding>
  <binding>
    <security>
      <transport credentialType="Certificate/Password" />
    </security>
  </binding>
</netPeerTcpBinding>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="b4375-111">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="b4375-111">Attributes and Elements</span></span>  
 <span data-ttu-id="b4375-112">In den folgenden Abschnitten werden Attribute, untergeordnete Elemente sowie übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="b4375-112">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="b4375-113">Attribute</span><span class="sxs-lookup"><span data-stu-id="b4375-113">Attributes</span></span>  
  
|<span data-ttu-id="b4375-114">Attribut</span><span class="sxs-lookup"><span data-stu-id="b4375-114">Attribute</span></span>|<span data-ttu-id="b4375-115">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="b4375-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="b4375-116">credentialType</span><span class="sxs-lookup"><span data-stu-id="b4375-116">credentialType</span></span>|<span data-ttu-id="b4375-117">Optional.</span><span class="sxs-lookup"><span data-stu-id="b4375-117">Optional.</span></span> <span data-ttu-id="b4375-118">Gibt den Typ von Anmeldeinformationen an, die zum Überprüfen von über den Peertransport gesendeten Nachrichten verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="b4375-118">Specifies the type of credentials used to verify messages sent with the peer transport.</span></span> <span data-ttu-id="b4375-119">Dieses Attribut ist vom Typ <xref:System.ServiceModel.PeerTransportCredentialType>.</span><span class="sxs-lookup"><span data-stu-id="b4375-119">This attribute is of type <xref:System.ServiceModel.PeerTransportCredentialType>.</span></span>|  
  
## <a name="credentialtype-attribute"></a><span data-ttu-id="b4375-120">credentialType-Attribut</span><span class="sxs-lookup"><span data-stu-id="b4375-120">credentialType Attribute</span></span>  
  
|<span data-ttu-id="b4375-121">Wert</span><span class="sxs-lookup"><span data-stu-id="b4375-121">Value</span></span>|<span data-ttu-id="b4375-122">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="b4375-122">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="b4375-123">Zertifikat</span><span class="sxs-lookup"><span data-stu-id="b4375-123">Certificate</span></span>|<span data-ttu-id="b4375-124">Zur Authentifizierung des Peerkanaltransports ist ein X509-Zertifikat erforderlich.</span><span class="sxs-lookup"><span data-stu-id="b4375-124">Authentication of the peer channel transport requires an X509 certificate.</span></span>|  
|<span data-ttu-id="b4375-125">Kennwort</span><span class="sxs-lookup"><span data-stu-id="b4375-125">Password</span></span>|<span data-ttu-id="b4375-126">Zur Authentifizierung des Peerkanaltransports ist ein korrektes Kennwort erforderlich.</span><span class="sxs-lookup"><span data-stu-id="b4375-126">Authentication of the peer channel transport requires a correct password.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="b4375-127">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="b4375-127">Child Elements</span></span>  
 <span data-ttu-id="b4375-128">None</span><span class="sxs-lookup"><span data-stu-id="b4375-128">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="b4375-129">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="b4375-129">Parent Elements</span></span>  
  
|<span data-ttu-id="b4375-130">Element</span><span class="sxs-lookup"><span data-stu-id="b4375-130">Element</span></span>|<span data-ttu-id="b4375-131">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="b4375-131">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="b4375-132">\<security></span><span class="sxs-lookup"><span data-stu-id="b4375-132">\<security></span></span>](security-of-netpeerbinding.md)|<span data-ttu-id="b4375-133">Definiert die Sicherheitseinstellungen für die [ \<netpeer ertcpbinding->](netpeertcpbinding.md).</span><span class="sxs-lookup"><span data-stu-id="b4375-133">Defines the security settings for the [\<netPeerTcpBinding>](netpeertcpbinding.md).</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="b4375-134">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b4375-134">See also</span></span>

- <xref:System.ServiceModel.Configuration.PeerTransportSecurityElement>
- <xref:System.ServiceModel.PeerSecuritySettings.Transport%2A>
- <xref:System.ServiceModel.Configuration.PeerSecurityElement.Transport%2A>
- <xref:System.ServiceModel.PeerTransportSecuritySettings>
- [<span data-ttu-id="b4375-135">Sichern von Diensten und Clients</span><span class="sxs-lookup"><span data-stu-id="b4375-135">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="b4375-136">Bindungen</span><span class="sxs-lookup"><span data-stu-id="b4375-136">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="b4375-137">Konfigurieren der vom System bereitgestellten Bindungen</span><span class="sxs-lookup"><span data-stu-id="b4375-137">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="b4375-138">Verwenden von Bindungen, um Dienste und Clients zu konfigurieren</span><span class="sxs-lookup"><span data-stu-id="b4375-138">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [<span data-ttu-id="b4375-139">\<binding></span><span class="sxs-lookup"><span data-stu-id="b4375-139">\<binding></span></span>](../../../misc/binding.md)
