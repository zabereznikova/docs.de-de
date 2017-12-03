---
title: '&lt;transport&gt; von &lt;netPeerTcpBinding&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c44d86d2-1160-44d7-9c7a-297b12eccc7f
caps.latest.revision: "16"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 181e6a9458754934d6b3b27a31c2cf2dd3455f52
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/02/2017
---
# <a name="lttransportgt-of-ltnetpeertcpbindinggt"></a><span data-ttu-id="5c116-102">&lt;transport&gt; von &lt;netPeerTcpBinding&gt;</span><span class="sxs-lookup"><span data-stu-id="5c116-102">&lt;transport&gt; of &lt;netPeerTcpBinding&gt;</span></span>
<span data-ttu-id="5c116-103">Gibt die Einstellungen für Sicherheit auf Transportebene bei Verwendung der [ \<NetPeerTcpBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/netpeertcpbinding.md).</span><span class="sxs-lookup"><span data-stu-id="5c116-103">Specifies settings for transport level security when using the [\<netPeerTcpBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/netpeertcpbinding.md).</span></span>  
  
 <span data-ttu-id="5c116-104">\<System. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="5c116-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="5c116-105">\<Bindungen ></span><span class="sxs-lookup"><span data-stu-id="5c116-105">\<bindings></span></span>  
<span data-ttu-id="5c116-106">\<NetPeerTcpBinding ></span><span class="sxs-lookup"><span data-stu-id="5c116-106">\<netPeerTcpBinding></span></span>  
<span data-ttu-id="5c116-107">\<Binden von ></span><span class="sxs-lookup"><span data-stu-id="5c116-107">\<binding></span></span>  
<span data-ttu-id="5c116-108">\<Sicherheit ></span><span class="sxs-lookup"><span data-stu-id="5c116-108">\<security></span></span>  
<span data-ttu-id="5c116-109">\<Transport ></span><span class="sxs-lookup"><span data-stu-id="5c116-109">\<transport></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5c116-110">Syntax</span><span class="sxs-lookup"><span data-stu-id="5c116-110">Syntax</span></span>  
  
```xml  
<netPeerTcpBinding>  
    <binding>  
        <security>  
            <transport credentialType="Certificate/Password" />  
        </security>         
    </binding>  
</netPeerTcpBinding>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="5c116-111">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="5c116-111">Attributes and Elements</span></span>  
 <span data-ttu-id="5c116-112">In den folgenden Abschnitten werden Attribute, untergeordnete Elemente sowie übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="5c116-112">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="5c116-113">Attribute</span><span class="sxs-lookup"><span data-stu-id="5c116-113">Attributes</span></span>  
  
|<span data-ttu-id="5c116-114">Attribut</span><span class="sxs-lookup"><span data-stu-id="5c116-114">Attribute</span></span>|<span data-ttu-id="5c116-115">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="5c116-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="5c116-116">credentialType</span><span class="sxs-lookup"><span data-stu-id="5c116-116">credentialType</span></span>|<span data-ttu-id="5c116-117">Dies ist optional.</span><span class="sxs-lookup"><span data-stu-id="5c116-117">Optional.</span></span> <span data-ttu-id="5c116-118">Gibt den Typ von Anmeldeinformationen an, die zum Überprüfen von über den Peertransport gesendeten Nachrichten verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="5c116-118">Specifies the type of credentials used to verify messages sent with the peer transport.</span></span> <span data-ttu-id="5c116-119">Dieses Attribut ist vom Typ <xref:System.ServiceModel.PeerTransportCredentialType>.</span><span class="sxs-lookup"><span data-stu-id="5c116-119">This attribute is of type <xref:System.ServiceModel.PeerTransportCredentialType>.</span></span>|  
  
## <a name="credentialtype-attribute"></a><span data-ttu-id="5c116-120">credentialType-Attribut</span><span class="sxs-lookup"><span data-stu-id="5c116-120">credentialType Attribute</span></span>  
  
|<span data-ttu-id="5c116-121">Wert</span><span class="sxs-lookup"><span data-stu-id="5c116-121">Value</span></span>|<span data-ttu-id="5c116-122">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="5c116-122">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="5c116-123">Zertifikat</span><span class="sxs-lookup"><span data-stu-id="5c116-123">Certificate</span></span>|<span data-ttu-id="5c116-124">Zur Authentifizierung des Peerkanaltransports ist ein X509-Zertifikat erforderlich.</span><span class="sxs-lookup"><span data-stu-id="5c116-124">Authentication of the peer channel transport requires an X509 certificate.</span></span>|  
|<span data-ttu-id="5c116-125">Kennwort</span><span class="sxs-lookup"><span data-stu-id="5c116-125">Password</span></span>|<span data-ttu-id="5c116-126">Zur Authentifizierung des Peerkanaltransports ist ein korrektes Kennwort erforderlich.</span><span class="sxs-lookup"><span data-stu-id="5c116-126">Authentication of the peer channel transport requires a correct password.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="5c116-127">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="5c116-127">Child Elements</span></span>  
 <span data-ttu-id="5c116-128">Keine</span><span class="sxs-lookup"><span data-stu-id="5c116-128">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="5c116-129">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="5c116-129">Parent Elements</span></span>  
  
|<span data-ttu-id="5c116-130">Element</span><span class="sxs-lookup"><span data-stu-id="5c116-130">Element</span></span>|<span data-ttu-id="5c116-131">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="5c116-131">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="5c116-132">\<Sicherheit ></span><span class="sxs-lookup"><span data-stu-id="5c116-132">\<security></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/security-of-netpeerbinding.md)|<span data-ttu-id="5c116-133">Definiert die Sicherheitseinstellungen für die [ \<NetPeerTcpBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/netpeertcpbinding.md).</span><span class="sxs-lookup"><span data-stu-id="5c116-133">Defines the security settings for the [\<netPeerTcpBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/netpeertcpbinding.md).</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="5c116-134">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="5c116-134">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.PeerTransportSecurityElement>  
 <xref:System.ServiceModel.PeerSecuritySettings.Transport%2A>  
 <xref:System.ServiceModel.Configuration.PeerSecurityElement.Transport%2A>  
 <xref:System.ServiceModel.PeerTransportSecuritySettings>  
 [<span data-ttu-id="5c116-135">Sichern von Diensten und Clients</span><span class="sxs-lookup"><span data-stu-id="5c116-135">Securing Services and Clients</span></span>](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)  
 [<span data-ttu-id="5c116-136">Bindungen</span><span class="sxs-lookup"><span data-stu-id="5c116-136">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)  
 [<span data-ttu-id="5c116-137">Konfigurieren der vom System bereitgestellte Bindungen</span><span class="sxs-lookup"><span data-stu-id="5c116-137">Configuring System-Provided Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)  
 [<span data-ttu-id="5c116-138">Verwenden von Bindungen, um Windows Communication Foundation-Dienste und Clients konfigurieren</span><span class="sxs-lookup"><span data-stu-id="5c116-138">Using Bindings to Configure Windows Communication Foundation Services and Clients</span></span>](http://msdn.microsoft.com/en-us/bd8b277b-932f-472f-a42a-b02bb5257dfb)  
 [<span data-ttu-id="5c116-139">\<Binden von ></span><span class="sxs-lookup"><span data-stu-id="5c116-139">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)
