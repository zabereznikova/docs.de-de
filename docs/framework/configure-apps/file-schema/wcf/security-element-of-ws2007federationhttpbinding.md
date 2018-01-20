---
title: '&lt;security&gt;-Element von &lt;ws2007FederationHttpBinding&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 826219b4-3a16-45fc-832d-0cd7cbbd3b84
caps.latest.revision: "10"
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.workload: dotnet
ms.openlocfilehash: 0358b8cd0ddc91baf4028fa8a3f06d032c3f117b
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/19/2018
---
# <a name="ltsecuritygt-element-of-ltws2007federationhttpbindinggt"></a><span data-ttu-id="9ffb7-102">&lt;security&gt;-Element von &lt;ws2007FederationHttpBinding&gt;</span><span class="sxs-lookup"><span data-stu-id="9ffb7-102">&lt;security&gt; element of &lt;ws2007FederationHttpBinding&gt;</span></span>
<span data-ttu-id="9ffb7-103">Definiert die Sicherheitseinstellungen für die [ \<ws2007FederationHttpBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/ws2007federationhttpbinding.md) Element.</span><span class="sxs-lookup"><span data-stu-id="9ffb7-103">Defines the security settings of the [\<ws2007FederationHttpBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/ws2007federationhttpbinding.md) element.</span></span>  
  
 <span data-ttu-id="9ffb7-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="9ffb7-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="9ffb7-105">\<bindings></span><span class="sxs-lookup"><span data-stu-id="9ffb7-105">\<bindings></span></span>  
<span data-ttu-id="9ffb7-106">\<ws2007FederationHttpBinding></span><span class="sxs-lookup"><span data-stu-id="9ffb7-106">\<ws2007FederationHttpBinding></span></span>  
<span data-ttu-id="9ffb7-107">\<binding></span><span class="sxs-lookup"><span data-stu-id="9ffb7-107">\<binding></span></span>  
<span data-ttu-id="9ffb7-108">\<security></span><span class="sxs-lookup"><span data-stu-id="9ffb7-108">\<security></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9ffb7-109">Syntax</span><span class="sxs-lookup"><span data-stu-id="9ffb7-109">Syntax</span></span>  
  
```xml  
<ws2007FederationBinding>  
    <binding >  
        <security mode="None/Message/TransportWithMessageCredential">  
           <message negotiateServiceCredential="Boolean"  
                algorithmSuite="Basic128/Basic192/Basic256/Basic128Rsa15/ Basic256Rsa15/TripleDes/TripleDesRsa15/Basic128Sha256/Basic192Sha256/TripleDesSha256/Basic128Sha256Rsa15/Basic192Sha256Rsa15/Basic256Sha256Rsa15/TripleDesSha256Rsa15"  
                defaultProtectionLevel="none/sign/EncryptAndSign"   
                issuedTokenType="string"   
                issuedKeyType="SymmetricKey/PublicKey"  
           </message>  
        </security>  
    </binding>  
</ws2007FederationBinding>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="9ffb7-110">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="9ffb7-110">Attributes and Elements</span></span>  
 <span data-ttu-id="9ffb7-111">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="9ffb7-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="9ffb7-112">Attribute</span><span class="sxs-lookup"><span data-stu-id="9ffb7-112">Attributes</span></span>  
  
|<span data-ttu-id="9ffb7-113">Attribut</span><span class="sxs-lookup"><span data-stu-id="9ffb7-113">Attribute</span></span>|<span data-ttu-id="9ffb7-114">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="9ffb7-114">Description</span></span>|  
|---------------|-----------------|  
|`mode`|<span data-ttu-id="9ffb7-115">Dies ist optional.</span><span class="sxs-lookup"><span data-stu-id="9ffb7-115">Optional.</span></span> <span data-ttu-id="9ffb7-116">Gibt den angewendeten Sicherheitstyp an.</span><span class="sxs-lookup"><span data-stu-id="9ffb7-116">Specifies the type of security that is applied.</span></span> <span data-ttu-id="9ffb7-117">Der Standardwert ist `Message`.</span><span class="sxs-lookup"><span data-stu-id="9ffb7-117">The default value is `Message`.</span></span> <span data-ttu-id="9ffb7-118">Dieses Attribut ist vom Typ <xref:System.ServiceModel.WSFederationHttpSecurityMode>.</span><span class="sxs-lookup"><span data-stu-id="9ffb7-118">This attribute is of type <xref:System.ServiceModel.WSFederationHttpSecurityMode>.</span></span>|  
  
## <a name="mode-attribute"></a><span data-ttu-id="9ffb7-119">mode-Attribut</span><span class="sxs-lookup"><span data-stu-id="9ffb7-119">mode Attribute</span></span>  
  
|<span data-ttu-id="9ffb7-120">Wert</span><span class="sxs-lookup"><span data-stu-id="9ffb7-120">Value</span></span>|<span data-ttu-id="9ffb7-121">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="9ffb7-121">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="9ffb7-122">Keine</span><span class="sxs-lookup"><span data-stu-id="9ffb7-122">None</span></span>|<span data-ttu-id="9ffb7-123">Die SOAP-Nachricht ist während der Übertragung nicht sicher.</span><span class="sxs-lookup"><span data-stu-id="9ffb7-123">The SOAP message is not secure during transfer.</span></span>|  
|<span data-ttu-id="9ffb7-124">Meldung</span><span class="sxs-lookup"><span data-stu-id="9ffb7-124">Message</span></span>|<span data-ttu-id="9ffb7-125">Integrität, Vertraulichkeit, Serverauthentifizierung und Clientauthentifizierung werden mittels SOAP-Nachrichtensicherheit bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="9ffb7-125">Integrity, confidentiality, server authentication and client authentication are provided using SOAP message security.</span></span> <span data-ttu-id="9ffb7-126">Standardmäßig wird der Text verschlüsselt und signiert.</span><span class="sxs-lookup"><span data-stu-id="9ffb7-126">By default, the body is encrypted and signed.</span></span> <span data-ttu-id="9ffb7-127">Der Dienst muss mit einem Zertifikat konfiguriert werden.</span><span class="sxs-lookup"><span data-stu-id="9ffb7-127">The service must be configured with a certificate.</span></span> <span data-ttu-id="9ffb7-128">Die Clientauthentifizierung basiert auf dem Token, das von einem Sicherheitstokendienst für den Client ausgestellt wird.</span><span class="sxs-lookup"><span data-stu-id="9ffb7-128">Client authentication is based on the token issued to the client by a security token service.</span></span>|  
|<span data-ttu-id="9ffb7-129">TransportWithMessageCredential</span><span class="sxs-lookup"><span data-stu-id="9ffb7-129">TransportWithMessageCredential</span></span>|<span data-ttu-id="9ffb7-130">Integrität, Vertraulichkeit und Serverauthentifizierung werden über HTTPS bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="9ffb7-130">Integrity, confidentiality and server authentication are provided by HTTPS.</span></span> <span data-ttu-id="9ffb7-131">Der Dienst muss mit einem Zertifikat konfiguriert werden.</span><span class="sxs-lookup"><span data-stu-id="9ffb7-131">The service must be configured with a certificate.</span></span> <span data-ttu-id="9ffb7-132">Die Clientauthentifizierung wird mittels SOAP-Nachrichtensicherheit bereitgestellt und basiert auf dem Token, das von einem Sicherheitstokendienst für den Client ausgestellt wird.</span><span class="sxs-lookup"><span data-stu-id="9ffb7-132">Client authentication is provided by means of SOAP message security and is based on the token issued to the client by a security token service.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="9ffb7-133">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="9ffb7-133">Child Elements</span></span>  
  
|<span data-ttu-id="9ffb7-134">Element</span><span class="sxs-lookup"><span data-stu-id="9ffb7-134">Element</span></span>|<span data-ttu-id="9ffb7-135">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="9ffb7-135">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="9ffb7-136">\<message></span><span class="sxs-lookup"><span data-stu-id="9ffb7-136">\<message></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/message-of-ws2007httpbinding.md)|<span data-ttu-id="9ffb7-137">Definiert die Einstellungen für die Sicherheit auf Nachrichtenebene.</span><span class="sxs-lookup"><span data-stu-id="9ffb7-137">Defines the settings for the message-level security.</span></span> <span data-ttu-id="9ffb7-138">Dieses Element ist vom Typ <xref:System.ServiceModel.Configuration.FederatedMessageSecurityOverHttpElement>.</span><span class="sxs-lookup"><span data-stu-id="9ffb7-138">This element is of type <xref:System.ServiceModel.Configuration.FederatedMessageSecurityOverHttpElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="9ffb7-139">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="9ffb7-139">Parent Elements</span></span>  
  
|<span data-ttu-id="9ffb7-140">Element</span><span class="sxs-lookup"><span data-stu-id="9ffb7-140">Element</span></span>|<span data-ttu-id="9ffb7-141">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="9ffb7-141">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="9ffb7-142">\<binding></span><span class="sxs-lookup"><span data-stu-id="9ffb7-142">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)|<span data-ttu-id="9ffb7-143">Definiert alle bindungsmöglichkeiten der [ \<WsDualHttpBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/wsdualhttpbinding.md).</span><span class="sxs-lookup"><span data-stu-id="9ffb7-143">Defines all binding capabilities of the [\<wsDualHttpBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/wsdualhttpbinding.md).</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="9ffb7-144">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="9ffb7-144">See Also</span></span>  
 <xref:System.ServiceModel.WSFederationHttpSecurity>  
 <xref:System.ServiceModel.WSFederationHttpBinding.Security%2A>  
 <xref:System.ServiceModel.Configuration.WSFederationHttpBindingElement.Security%2A>  
 <xref:System.ServiceModel.Configuration.WSFederationHttpSecurityElement>  
 [<span data-ttu-id="9ffb7-145">Vorgehensweise: Erstellen einer WSFederationHttpBinding</span><span class="sxs-lookup"><span data-stu-id="9ffb7-145">How to: Create a WSFederationHttpBinding</span></span>](../../../../../docs/framework/wcf/feature-details/how-to-create-a-wsfederationhttpbinding.md)  
 [<span data-ttu-id="9ffb7-146">Sichern von Diensten und Clients</span><span class="sxs-lookup"><span data-stu-id="9ffb7-146">Securing Services and Clients</span></span>](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)  
 [<span data-ttu-id="9ffb7-147">Ausählen eines Anmeldeinformationentyps</span><span class="sxs-lookup"><span data-stu-id="9ffb7-147">Selecting a Credential Type</span></span>](../../../../../docs/framework/wcf/feature-details/selecting-a-credential-type.md)  
 [<span data-ttu-id="9ffb7-148">Bindungen</span><span class="sxs-lookup"><span data-stu-id="9ffb7-148">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)  
 [<span data-ttu-id="9ffb7-149">Konfigurieren der vom System bereitgestellten Bindungen</span><span class="sxs-lookup"><span data-stu-id="9ffb7-149">Configuring System-Provided Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)  
 [<span data-ttu-id="9ffb7-150">Verwenden von Bindungen, um Windows Communication Foundation-Dienste und Clients konfigurieren</span><span class="sxs-lookup"><span data-stu-id="9ffb7-150">Using Bindings to Configure Windows Communication Foundation Services and Clients</span></span>](http://msdn.microsoft.com/library/bd8b277b-932f-472f-a42a-b02bb5257dfb)  
 [<span data-ttu-id="9ffb7-151">\<binding></span><span class="sxs-lookup"><span data-stu-id="9ffb7-151">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)
