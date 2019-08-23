---
title: <security>Element von<ws2007FederationHttpBinding>
ms.date: 03/30/2017
ms.assetid: 826219b4-3a16-45fc-832d-0cd7cbbd3b84
ms.openlocfilehash: 61b56ca1fae5c328cda0bbebef4026f0784095a3
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69936821"
---
# <a name="security-element-of-ws2007federationhttpbinding"></a><span data-ttu-id="3124b-102">\<Security > Element von \<WS2007FederationHttpBinding ></span><span class="sxs-lookup"><span data-stu-id="3124b-102">\<security> element of \<ws2007FederationHttpBinding></span></span>
<span data-ttu-id="3124b-103">Definiert die Sicherheitseinstellungen des [ \<WS2007FederationHttpBinding->](ws2007federationhttpbinding.md) Elements.</span><span class="sxs-lookup"><span data-stu-id="3124b-103">Defines the security settings of the [\<ws2007FederationHttpBinding>](ws2007federationhttpbinding.md) element.</span></span>  
  
 <span data-ttu-id="3124b-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="3124b-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="3124b-105">\<bindings></span><span class="sxs-lookup"><span data-stu-id="3124b-105">\<bindings></span></span>  
<span data-ttu-id="3124b-106">\<ws2007FederationHttpBinding></span><span class="sxs-lookup"><span data-stu-id="3124b-106">\<ws2007FederationHttpBinding></span></span>  
<span data-ttu-id="3124b-107">\<binding></span><span class="sxs-lookup"><span data-stu-id="3124b-107">\<binding></span></span>  
<span data-ttu-id="3124b-108">\<security></span><span class="sxs-lookup"><span data-stu-id="3124b-108">\<security></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3124b-109">Syntax</span><span class="sxs-lookup"><span data-stu-id="3124b-109">Syntax</span></span>  
  
```xml  
<ws2007FederationBinding>
  <binding>
    <security mode="None/Message/TransportWithMessageCredential">
      <message negotiateServiceCredential="Boolean"
               algorithmSuite="Basic128/Basic192/Basic256/Basic128Rsa15/  Basic256Rsa15/TripleDes/TripleDesRsa15/Basic128Sha256/Basic192Sha256/TripleDesSha256/Basic128Sha256Rsa15/Basic192Sha256Rsa15/Basic256Sha256Rsa15/TripleDesSha256Rsa15"
               defaultProtectionLevel="none/sign/EncryptAndSign"
               issuedTokenType="string"
               issuedKeyType="SymmetricKey/PublicKey">
      </message>
    </security>
  </binding>
</ws2007FederationBinding>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="3124b-110">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="3124b-110">Attributes and Elements</span></span>  
 <span data-ttu-id="3124b-111">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="3124b-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="3124b-112">Attribute</span><span class="sxs-lookup"><span data-stu-id="3124b-112">Attributes</span></span>  
  
|<span data-ttu-id="3124b-113">Attribut</span><span class="sxs-lookup"><span data-stu-id="3124b-113">Attribute</span></span>|<span data-ttu-id="3124b-114">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="3124b-114">Description</span></span>|  
|---------------|-----------------|  
|`mode`|<span data-ttu-id="3124b-115">Optional.</span><span class="sxs-lookup"><span data-stu-id="3124b-115">Optional.</span></span> <span data-ttu-id="3124b-116">Gibt den angewendeten Sicherheitstyp an.</span><span class="sxs-lookup"><span data-stu-id="3124b-116">Specifies the type of security that is applied.</span></span> <span data-ttu-id="3124b-117">Der Standardwert ist `Message`.</span><span class="sxs-lookup"><span data-stu-id="3124b-117">The default value is `Message`.</span></span> <span data-ttu-id="3124b-118">Dieses Attribut ist vom Typ <xref:System.ServiceModel.WSFederationHttpSecurityMode>.</span><span class="sxs-lookup"><span data-stu-id="3124b-118">This attribute is of type <xref:System.ServiceModel.WSFederationHttpSecurityMode>.</span></span>|  
  
## <a name="mode-attribute"></a><span data-ttu-id="3124b-119">mode-Attribut</span><span class="sxs-lookup"><span data-stu-id="3124b-119">mode Attribute</span></span>  
  
|<span data-ttu-id="3124b-120">Wert</span><span class="sxs-lookup"><span data-stu-id="3124b-120">Value</span></span>|<span data-ttu-id="3124b-121">Description</span><span class="sxs-lookup"><span data-stu-id="3124b-121">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="3124b-122">None</span><span class="sxs-lookup"><span data-stu-id="3124b-122">None</span></span>|<span data-ttu-id="3124b-123">Die SOAP-Nachricht ist während der Übertragung nicht sicher.</span><span class="sxs-lookup"><span data-stu-id="3124b-123">The SOAP message is not secure during transfer.</span></span>|  
|<span data-ttu-id="3124b-124">Meldung</span><span class="sxs-lookup"><span data-stu-id="3124b-124">Message</span></span>|<span data-ttu-id="3124b-125">Integrität, Vertraulichkeit, Serverauthentifizierung und Clientauthentifizierung werden mittels SOAP-Nachrichtensicherheit bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="3124b-125">Integrity, confidentiality, server authentication and client authentication are provided using SOAP message security.</span></span> <span data-ttu-id="3124b-126">Standardmäßig wird der Text verschlüsselt und signiert.</span><span class="sxs-lookup"><span data-stu-id="3124b-126">By default, the body is encrypted and signed.</span></span> <span data-ttu-id="3124b-127">Der Dienst muss mit einem Zertifikat konfiguriert werden.</span><span class="sxs-lookup"><span data-stu-id="3124b-127">The service must be configured with a certificate.</span></span> <span data-ttu-id="3124b-128">Die Clientauthentifizierung basiert auf dem Token, das von einem Sicherheitstokendienst für den Client ausgestellt wird.</span><span class="sxs-lookup"><span data-stu-id="3124b-128">Client authentication is based on the token issued to the client by a security token service.</span></span>|  
|<span data-ttu-id="3124b-129">TransportWithMessageCredential</span><span class="sxs-lookup"><span data-stu-id="3124b-129">TransportWithMessageCredential</span></span>|<span data-ttu-id="3124b-130">Integrität, Vertraulichkeit und Serverauthentifizierung werden über HTTPS bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="3124b-130">Integrity, confidentiality and server authentication are provided by HTTPS.</span></span> <span data-ttu-id="3124b-131">Der Dienst muss mit einem Zertifikat konfiguriert werden.</span><span class="sxs-lookup"><span data-stu-id="3124b-131">The service must be configured with a certificate.</span></span> <span data-ttu-id="3124b-132">Die Clientauthentifizierung wird mittels SOAP-Nachrichtensicherheit bereitgestellt und basiert auf dem Token, das von einem Sicherheitstokendienst für den Client ausgestellt wird.</span><span class="sxs-lookup"><span data-stu-id="3124b-132">Client authentication is provided by means of SOAP message security and is based on the token issued to the client by a security token service.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="3124b-133">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="3124b-133">Child Elements</span></span>  
  
|<span data-ttu-id="3124b-134">Element</span><span class="sxs-lookup"><span data-stu-id="3124b-134">Element</span></span>|<span data-ttu-id="3124b-135">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="3124b-135">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="3124b-136">\<message></span><span class="sxs-lookup"><span data-stu-id="3124b-136">\<message></span></span>](message-of-ws2007httpbinding.md)|<span data-ttu-id="3124b-137">Definiert die Einstellungen für die Sicherheit auf Nachrichtenebene.</span><span class="sxs-lookup"><span data-stu-id="3124b-137">Defines the settings for the message-level security.</span></span> <span data-ttu-id="3124b-138">Dieses Element ist vom Typ <xref:System.ServiceModel.Configuration.FederatedMessageSecurityOverHttpElement>.</span><span class="sxs-lookup"><span data-stu-id="3124b-138">This element is of type <xref:System.ServiceModel.Configuration.FederatedMessageSecurityOverHttpElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="3124b-139">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="3124b-139">Parent Elements</span></span>  
  
|<span data-ttu-id="3124b-140">Element</span><span class="sxs-lookup"><span data-stu-id="3124b-140">Element</span></span>|<span data-ttu-id="3124b-141">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="3124b-141">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="3124b-142">\<binding></span><span class="sxs-lookup"><span data-stu-id="3124b-142">\<binding></span></span>](../../../misc/binding.md)|<span data-ttu-id="3124b-143">Definiert alle Bindungsfunktionen der [ \<WSDualHttpBinding->](wsdualhttpbinding.md).</span><span class="sxs-lookup"><span data-stu-id="3124b-143">Defines all binding capabilities of the [\<wsDualHttpBinding>](wsdualhttpbinding.md).</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="3124b-144">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="3124b-144">See also</span></span>

- <xref:System.ServiceModel.WSFederationHttpSecurity>
- <xref:System.ServiceModel.WSFederationHttpBinding.Security%2A>
- <xref:System.ServiceModel.Configuration.WSFederationHttpBindingElement.Security%2A>
- <xref:System.ServiceModel.Configuration.WSFederationHttpSecurityElement>
- [<span data-ttu-id="3124b-145">Vorgehensweise: Erstellen einer WSFederationHttpBinding</span><span class="sxs-lookup"><span data-stu-id="3124b-145">How to: Create a WSFederationHttpBinding</span></span>](../../../wcf/feature-details/how-to-create-a-wsfederationhttpbinding.md)
- [<span data-ttu-id="3124b-146">Sichern von Diensten und Clients</span><span class="sxs-lookup"><span data-stu-id="3124b-146">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="3124b-147">Ausählen eines Anmeldeinformationentyps</span><span class="sxs-lookup"><span data-stu-id="3124b-147">Selecting a Credential Type</span></span>](../../../wcf/feature-details/selecting-a-credential-type.md)
- [<span data-ttu-id="3124b-148">Bindungen</span><span class="sxs-lookup"><span data-stu-id="3124b-148">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="3124b-149">Konfigurieren der vom System bereitgestellten Bindungen</span><span class="sxs-lookup"><span data-stu-id="3124b-149">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="3124b-150">Verwenden von Bindungen, um Dienste und Clients zu konfigurieren</span><span class="sxs-lookup"><span data-stu-id="3124b-150">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [<span data-ttu-id="3124b-151">\<binding></span><span class="sxs-lookup"><span data-stu-id="3124b-151">\<binding></span></span>](../../../misc/binding.md)
