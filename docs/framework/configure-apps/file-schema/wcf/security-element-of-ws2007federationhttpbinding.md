---
title: <security> Element von <ws2007FederationHttpBinding>
ms.date: 03/30/2017
ms.assetid: 826219b4-3a16-45fc-832d-0cd7cbbd3b84
ms.openlocfilehash: b85c54c6507313522286e0c66504cfd0c8afb2b0
ms.sourcegitcommit: 22be09204266253d45ece46f51cc6f080f2b3fd6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/07/2019
ms.locfileid: "73738721"
---
# <a name="security-element-of-ws2007federationhttpbinding"></a><span data-ttu-id="e548a-102">\<Sicherheits > Element von \<WS2007FederationHttpBinding ></span><span class="sxs-lookup"><span data-stu-id="e548a-102">\<security> element of \<ws2007FederationHttpBinding></span></span>
<span data-ttu-id="e548a-103">Definiert die Sicherheitseinstellungen des [\<WS2007FederationHttpBinding->](ws2007federationhttpbinding.md) Elements.</span><span class="sxs-lookup"><span data-stu-id="e548a-103">Defines the security settings of the [\<ws2007FederationHttpBinding>](ws2007federationhttpbinding.md) element.</span></span>  
  
<span data-ttu-id="e548a-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="e548a-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="e548a-105">&nbsp; &nbsp;[ **\<system. Service Model->** ](system-servicemodel.md) </span><span class="sxs-lookup"><span data-stu-id="e548a-105">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="e548a-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Bindungen >** ](bindings.md)</span><span class="sxs-lookup"><span data-stu-id="e548a-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)</span></span>\
<span data-ttu-id="e548a-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<WS2007FederationHttpBinding >** ](ws2007federationhttpbinding.md)</span><span class="sxs-lookup"><span data-stu-id="e548a-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<ws2007FederationHttpBinding>**](ws2007federationhttpbinding.md)</span></span>\
<span data-ttu-id="e548a-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<**Bindungs >** </span><span class="sxs-lookup"><span data-stu-id="e548a-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**</span></span>\
<span data-ttu-id="e548a-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<Sicherheit >**</span><span class="sxs-lookup"><span data-stu-id="e548a-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<security>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e548a-110">Syntax</span><span class="sxs-lookup"><span data-stu-id="e548a-110">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="e548a-111">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="e548a-111">Attributes and Elements</span></span>  
 <span data-ttu-id="e548a-112">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="e548a-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="e548a-113">Attribute</span><span class="sxs-lookup"><span data-stu-id="e548a-113">Attributes</span></span>  
  
|<span data-ttu-id="e548a-114">Attribut</span><span class="sxs-lookup"><span data-stu-id="e548a-114">Attribute</span></span>|<span data-ttu-id="e548a-115">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="e548a-115">Description</span></span>|  
|---------------|-----------------|  
|`mode`|<span data-ttu-id="e548a-116">Dies ist optional.</span><span class="sxs-lookup"><span data-stu-id="e548a-116">Optional.</span></span> <span data-ttu-id="e548a-117">Gibt den angewendeten Sicherheitstyp an.</span><span class="sxs-lookup"><span data-stu-id="e548a-117">Specifies the type of security that is applied.</span></span> <span data-ttu-id="e548a-118">Der Standardwert ist `Message`sein.</span><span class="sxs-lookup"><span data-stu-id="e548a-118">The default value is `Message`.</span></span> <span data-ttu-id="e548a-119">Dieses Attribut ist vom Typ <xref:System.ServiceModel.WSFederationHttpSecurityMode>.</span><span class="sxs-lookup"><span data-stu-id="e548a-119">This attribute is of type <xref:System.ServiceModel.WSFederationHttpSecurityMode>.</span></span>|  
  
## <a name="mode-attribute"></a><span data-ttu-id="e548a-120">mode-Attribut</span><span class="sxs-lookup"><span data-stu-id="e548a-120">mode Attribute</span></span>  
  
|<span data-ttu-id="e548a-121">Wert</span><span class="sxs-lookup"><span data-stu-id="e548a-121">Value</span></span>|<span data-ttu-id="e548a-122">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="e548a-122">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="e548a-123">Keiner</span><span class="sxs-lookup"><span data-stu-id="e548a-123">None</span></span>|<span data-ttu-id="e548a-124">Die SOAP-Nachricht ist während der Übertragung nicht sicher.</span><span class="sxs-lookup"><span data-stu-id="e548a-124">The SOAP message is not secure during transfer.</span></span>|  
|<span data-ttu-id="e548a-125">Nachricht</span><span class="sxs-lookup"><span data-stu-id="e548a-125">Message</span></span>|<span data-ttu-id="e548a-126">Integrität, Vertraulichkeit, Serverauthentifizierung und Clientauthentifizierung werden mittels SOAP-Nachrichtensicherheit bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="e548a-126">Integrity, confidentiality, server authentication and client authentication are provided using SOAP message security.</span></span> <span data-ttu-id="e548a-127">Standardmäßig wird der Text verschlüsselt und signiert.</span><span class="sxs-lookup"><span data-stu-id="e548a-127">By default, the body is encrypted and signed.</span></span> <span data-ttu-id="e548a-128">Der Dienst muss mit einem Zertifikat konfiguriert werden.</span><span class="sxs-lookup"><span data-stu-id="e548a-128">The service must be configured with a certificate.</span></span> <span data-ttu-id="e548a-129">Die Clientauthentifizierung basiert auf dem Token, das von einem Sicherheitstokendienst für den Client ausgestellt wird.</span><span class="sxs-lookup"><span data-stu-id="e548a-129">Client authentication is based on the token issued to the client by a security token service.</span></span>|  
|<span data-ttu-id="e548a-130">TransportWithMessageCredential</span><span class="sxs-lookup"><span data-stu-id="e548a-130">TransportWithMessageCredential</span></span>|<span data-ttu-id="e548a-131">Integrität, Vertraulichkeit und Serverauthentifizierung werden über HTTPS bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="e548a-131">Integrity, confidentiality and server authentication are provided by HTTPS.</span></span> <span data-ttu-id="e548a-132">Der Dienst muss mit einem Zertifikat konfiguriert werden.</span><span class="sxs-lookup"><span data-stu-id="e548a-132">The service must be configured with a certificate.</span></span> <span data-ttu-id="e548a-133">Die Clientauthentifizierung wird mittels SOAP-Nachrichtensicherheit bereitgestellt und basiert auf dem Token, das von einem Sicherheitstokendienst für den Client ausgestellt wird.</span><span class="sxs-lookup"><span data-stu-id="e548a-133">Client authentication is provided by means of SOAP message security and is based on the token issued to the client by a security token service.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="e548a-134">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="e548a-134">Child Elements</span></span>  
  
|<span data-ttu-id="e548a-135">Element</span><span class="sxs-lookup"><span data-stu-id="e548a-135">Element</span></span>|<span data-ttu-id="e548a-136">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="e548a-136">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="e548a-137">\<message ></span><span class="sxs-lookup"><span data-stu-id="e548a-137">\<message></span></span>](message-of-ws2007httpbinding.md)|<span data-ttu-id="e548a-138">Definiert die Einstellungen für die Sicherheit auf Nachrichtenebene.</span><span class="sxs-lookup"><span data-stu-id="e548a-138">Defines the settings for the message-level security.</span></span> <span data-ttu-id="e548a-139">Dieses Element ist vom Typ <xref:System.ServiceModel.Configuration.FederatedMessageSecurityOverHttpElement>.</span><span class="sxs-lookup"><span data-stu-id="e548a-139">This element is of type <xref:System.ServiceModel.Configuration.FederatedMessageSecurityOverHttpElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="e548a-140">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="e548a-140">Parent Elements</span></span>  
  
|<span data-ttu-id="e548a-141">Element</span><span class="sxs-lookup"><span data-stu-id="e548a-141">Element</span></span>|<span data-ttu-id="e548a-142">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="e548a-142">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="e548a-143">\<binding ></span><span class="sxs-lookup"><span data-stu-id="e548a-143">\<binding></span></span>](bindings.md)|<span data-ttu-id="e548a-144">Definiert alle Bindungsfunktionen des [\<WSDualHttpBinding->](wsdualhttpbinding.md).</span><span class="sxs-lookup"><span data-stu-id="e548a-144">Defines all binding capabilities of the [\<wsDualHttpBinding>](wsdualhttpbinding.md).</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="e548a-145">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e548a-145">See also</span></span>

- <xref:System.ServiceModel.WSFederationHttpSecurity>
- <xref:System.ServiceModel.WSFederationHttpBinding.Security%2A>
- <xref:System.ServiceModel.Configuration.WSFederationHttpBindingElement.Security%2A>
- <xref:System.ServiceModel.Configuration.WSFederationHttpSecurityElement>
- [<span data-ttu-id="e548a-146">Vorgehensweise: Erstellen einer WSFederationHttpBinding</span><span class="sxs-lookup"><span data-stu-id="e548a-146">How to: Create a WSFederationHttpBinding</span></span>](../../../wcf/feature-details/how-to-create-a-wsfederationhttpbinding.md)
- [<span data-ttu-id="e548a-147">Sichern von Diensten und Clients</span><span class="sxs-lookup"><span data-stu-id="e548a-147">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="e548a-148">Ausählen eines Anmeldeinformationentyps</span><span class="sxs-lookup"><span data-stu-id="e548a-148">Selecting a Credential Type</span></span>](../../../wcf/feature-details/selecting-a-credential-type.md)
- [<span data-ttu-id="e548a-149">Bindungen</span><span class="sxs-lookup"><span data-stu-id="e548a-149">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="e548a-150">Konfigurieren der vom System bereitgestellten Bindungen</span><span class="sxs-lookup"><span data-stu-id="e548a-150">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="e548a-151">Verwenden von Bindungen, um Dienste und Clients zu konfigurieren</span><span class="sxs-lookup"><span data-stu-id="e548a-151">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [<span data-ttu-id="e548a-152">\<binding ></span><span class="sxs-lookup"><span data-stu-id="e548a-152">\<binding></span></span>](bindings.md)
