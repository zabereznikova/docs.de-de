---
title: '&lt;security&gt;-Element von &lt;ws2007FederationHttpBinding&gt;'
ms.date: 03/30/2017
ms.assetid: 826219b4-3a16-45fc-832d-0cd7cbbd3b84
author: BrucePerlerMS
ms.openlocfilehash: f413a7f978df1a0ef3d731abee93c34824c8a6c6
ms.sourcegitcommit: 586dbdcaef9767642436b1e4efbe88fb15473d6f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/06/2018
ms.locfileid: "48841150"
---
# <a name="ltsecuritygt-element-of-ltws2007federationhttpbindinggt"></a><span data-ttu-id="f18c9-102">&lt;security&gt;-Element von &lt;ws2007FederationHttpBinding&gt;</span><span class="sxs-lookup"><span data-stu-id="f18c9-102">&lt;security&gt; element of &lt;ws2007FederationHttpBinding&gt;</span></span>
<span data-ttu-id="f18c9-103">Definiert die Sicherheitseinstellungen der [ \<ws2007FederationHttpBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/ws2007federationhttpbinding.md) Element.</span><span class="sxs-lookup"><span data-stu-id="f18c9-103">Defines the security settings of the [\<ws2007FederationHttpBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/ws2007federationhttpbinding.md) element.</span></span>  
  
 <span data-ttu-id="f18c9-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="f18c9-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="f18c9-105">\<bindings></span><span class="sxs-lookup"><span data-stu-id="f18c9-105">\<bindings></span></span>  
<span data-ttu-id="f18c9-106">\<ws2007FederationHttpBinding></span><span class="sxs-lookup"><span data-stu-id="f18c9-106">\<ws2007FederationHttpBinding></span></span>  
<span data-ttu-id="f18c9-107">\<binding></span><span class="sxs-lookup"><span data-stu-id="f18c9-107">\<binding></span></span>  
<span data-ttu-id="f18c9-108">\<Sicherheit ></span><span class="sxs-lookup"><span data-stu-id="f18c9-108">\<security></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f18c9-109">Syntax</span><span class="sxs-lookup"><span data-stu-id="f18c9-109">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="f18c9-110">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="f18c9-110">Attributes and Elements</span></span>  
 <span data-ttu-id="f18c9-111">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="f18c9-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="f18c9-112">Attribute</span><span class="sxs-lookup"><span data-stu-id="f18c9-112">Attributes</span></span>  
  
|<span data-ttu-id="f18c9-113">Attribut</span><span class="sxs-lookup"><span data-stu-id="f18c9-113">Attribute</span></span>|<span data-ttu-id="f18c9-114">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="f18c9-114">Description</span></span>|  
|---------------|-----------------|  
|`mode`|<span data-ttu-id="f18c9-115">Dies ist optional.</span><span class="sxs-lookup"><span data-stu-id="f18c9-115">Optional.</span></span> <span data-ttu-id="f18c9-116">Gibt den angewendeten Sicherheitstyp an.</span><span class="sxs-lookup"><span data-stu-id="f18c9-116">Specifies the type of security that is applied.</span></span> <span data-ttu-id="f18c9-117">Der Standardwert ist `Message`.</span><span class="sxs-lookup"><span data-stu-id="f18c9-117">The default value is `Message`.</span></span> <span data-ttu-id="f18c9-118">Dieses Attribut ist vom Typ <xref:System.ServiceModel.WSFederationHttpSecurityMode>.</span><span class="sxs-lookup"><span data-stu-id="f18c9-118">This attribute is of type <xref:System.ServiceModel.WSFederationHttpSecurityMode>.</span></span>|  
  
## <a name="mode-attribute"></a><span data-ttu-id="f18c9-119">mode-Attribut</span><span class="sxs-lookup"><span data-stu-id="f18c9-119">mode Attribute</span></span>  
  
|<span data-ttu-id="f18c9-120">Wert</span><span class="sxs-lookup"><span data-stu-id="f18c9-120">Value</span></span>|<span data-ttu-id="f18c9-121">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="f18c9-121">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="f18c9-122">Keine</span><span class="sxs-lookup"><span data-stu-id="f18c9-122">None</span></span>|<span data-ttu-id="f18c9-123">Die SOAP-Nachricht ist während der Übertragung nicht sicher.</span><span class="sxs-lookup"><span data-stu-id="f18c9-123">The SOAP message is not secure during transfer.</span></span>|  
|<span data-ttu-id="f18c9-124">Meldung</span><span class="sxs-lookup"><span data-stu-id="f18c9-124">Message</span></span>|<span data-ttu-id="f18c9-125">Integrität, Vertraulichkeit, Serverauthentifizierung und Clientauthentifizierung werden mittels SOAP-Nachrichtensicherheit bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="f18c9-125">Integrity, confidentiality, server authentication and client authentication are provided using SOAP message security.</span></span> <span data-ttu-id="f18c9-126">Standardmäßig wird der Text verschlüsselt und signiert.</span><span class="sxs-lookup"><span data-stu-id="f18c9-126">By default, the body is encrypted and signed.</span></span> <span data-ttu-id="f18c9-127">Der Dienst muss mit einem Zertifikat konfiguriert werden.</span><span class="sxs-lookup"><span data-stu-id="f18c9-127">The service must be configured with a certificate.</span></span> <span data-ttu-id="f18c9-128">Die Clientauthentifizierung basiert auf dem Token, das von einem Sicherheitstokendienst für den Client ausgestellt wird.</span><span class="sxs-lookup"><span data-stu-id="f18c9-128">Client authentication is based on the token issued to the client by a security token service.</span></span>|  
|<span data-ttu-id="f18c9-129">TransportWithMessageCredential</span><span class="sxs-lookup"><span data-stu-id="f18c9-129">TransportWithMessageCredential</span></span>|<span data-ttu-id="f18c9-130">Integrität, Vertraulichkeit und Serverauthentifizierung werden über HTTPS bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="f18c9-130">Integrity, confidentiality and server authentication are provided by HTTPS.</span></span> <span data-ttu-id="f18c9-131">Der Dienst muss mit einem Zertifikat konfiguriert werden.</span><span class="sxs-lookup"><span data-stu-id="f18c9-131">The service must be configured with a certificate.</span></span> <span data-ttu-id="f18c9-132">Die Clientauthentifizierung wird mittels SOAP-Nachrichtensicherheit bereitgestellt und basiert auf dem Token, das von einem Sicherheitstokendienst für den Client ausgestellt wird.</span><span class="sxs-lookup"><span data-stu-id="f18c9-132">Client authentication is provided by means of SOAP message security and is based on the token issued to the client by a security token service.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="f18c9-133">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="f18c9-133">Child Elements</span></span>  
  
|<span data-ttu-id="f18c9-134">Element</span><span class="sxs-lookup"><span data-stu-id="f18c9-134">Element</span></span>|<span data-ttu-id="f18c9-135">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="f18c9-135">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="f18c9-136">\<message></span><span class="sxs-lookup"><span data-stu-id="f18c9-136">\<message></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/message-of-ws2007httpbinding.md)|<span data-ttu-id="f18c9-137">Definiert die Einstellungen für die Sicherheit auf Nachrichtenebene.</span><span class="sxs-lookup"><span data-stu-id="f18c9-137">Defines the settings for the message-level security.</span></span> <span data-ttu-id="f18c9-138">Dieses Element ist vom Typ <xref:System.ServiceModel.Configuration.FederatedMessageSecurityOverHttpElement>.</span><span class="sxs-lookup"><span data-stu-id="f18c9-138">This element is of type <xref:System.ServiceModel.Configuration.FederatedMessageSecurityOverHttpElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="f18c9-139">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="f18c9-139">Parent Elements</span></span>  
  
|<span data-ttu-id="f18c9-140">Element</span><span class="sxs-lookup"><span data-stu-id="f18c9-140">Element</span></span>|<span data-ttu-id="f18c9-141">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="f18c9-141">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="f18c9-142">\<binding></span><span class="sxs-lookup"><span data-stu-id="f18c9-142">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)|<span data-ttu-id="f18c9-143">Definiert alle bindungsfähigkeiten von der [ \<WsDualHttpBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/wsdualhttpbinding.md).</span><span class="sxs-lookup"><span data-stu-id="f18c9-143">Defines all binding capabilities of the [\<wsDualHttpBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/wsdualhttpbinding.md).</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="f18c9-144">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f18c9-144">See Also</span></span>  
 <xref:System.ServiceModel.WSFederationHttpSecurity>  
 <xref:System.ServiceModel.WSFederationHttpBinding.Security%2A>  
 <xref:System.ServiceModel.Configuration.WSFederationHttpBindingElement.Security%2A>  
 <xref:System.ServiceModel.Configuration.WSFederationHttpSecurityElement>  
 [<span data-ttu-id="f18c9-145">Vorgehensweise: Erstellen einer WSFederationHttpBinding</span><span class="sxs-lookup"><span data-stu-id="f18c9-145">How to: Create a WSFederationHttpBinding</span></span>](../../../../../docs/framework/wcf/feature-details/how-to-create-a-wsfederationhttpbinding.md)  
 [<span data-ttu-id="f18c9-146">Sichern von Diensten und Clients</span><span class="sxs-lookup"><span data-stu-id="f18c9-146">Securing Services and Clients</span></span>](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)  
 [<span data-ttu-id="f18c9-147">Ausählen eines Anmeldeinformationentyps</span><span class="sxs-lookup"><span data-stu-id="f18c9-147">Selecting a Credential Type</span></span>](../../../../../docs/framework/wcf/feature-details/selecting-a-credential-type.md)  
 [<span data-ttu-id="f18c9-148">Bindungen</span><span class="sxs-lookup"><span data-stu-id="f18c9-148">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)  
 [<span data-ttu-id="f18c9-149">Konfigurieren der vom System bereitgestellten Bindungen</span><span class="sxs-lookup"><span data-stu-id="f18c9-149">Configuring System-Provided Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)  
 [<span data-ttu-id="f18c9-150">Verwenden von Bindungen, um Dienste und Clients zu konfigurieren</span><span class="sxs-lookup"><span data-stu-id="f18c9-150">Using Bindings to Configure Services and Clients</span></span>](../../../../../docs/framework/wcf/using-bindings-to-configure-services-and-clients.md)  
 [<span data-ttu-id="f18c9-151">\<binding></span><span class="sxs-lookup"><span data-stu-id="f18c9-151">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)
