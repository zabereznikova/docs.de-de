---
title: <security> von <wsFederationHttpBinding>
ms.date: 03/30/2017
ms.assetid: a8e5e854-b8dc-4921-843d-34b6a4a6a8ba
ms.openlocfilehash: ea029444cee331a235c7a2fc140b4321d7530063
ms.sourcegitcommit: 22be09204266253d45ece46f51cc6f080f2b3fd6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/07/2019
ms.locfileid: "73736332"
---
# <a name="security-of-wsfederationhttpbinding"></a><span data-ttu-id="3a403-102">\<Sicherheits > von \<WSFederationHttpBinding ></span><span class="sxs-lookup"><span data-stu-id="3a403-102">\<security> of \<wsFederationHttpBinding></span></span>
<span data-ttu-id="3a403-103">Definiert die Sicherheitseinstellungen des [\<WSFederationHttpBinding->](wsfederationhttpbinding.md).</span><span class="sxs-lookup"><span data-stu-id="3a403-103">Defines the security settings of the [\<wsFederationHttpBinding>](wsfederationhttpbinding.md).</span></span>  
  
<span data-ttu-id="3a403-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="3a403-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="3a403-105">&nbsp; &nbsp;[ **\<system. Service Model->** ](system-servicemodel.md) </span><span class="sxs-lookup"><span data-stu-id="3a403-105">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="3a403-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Bindungen >** ](bindings.md)</span><span class="sxs-lookup"><span data-stu-id="3a403-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)</span></span>\
<span data-ttu-id="3a403-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<WSFederationHttpBinding >** ](wsfederationhttpbinding.md)</span><span class="sxs-lookup"><span data-stu-id="3a403-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<wsFederationHttpBinding>**](wsfederationhttpbinding.md)</span></span>\
<span data-ttu-id="3a403-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<**Bindungs >** </span><span class="sxs-lookup"><span data-stu-id="3a403-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**</span></span>\
<span data-ttu-id="3a403-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<Sicherheit >**</span><span class="sxs-lookup"><span data-stu-id="3a403-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<security>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3a403-110">Syntax</span><span class="sxs-lookup"><span data-stu-id="3a403-110">Syntax</span></span>  
  
```xml  
<wsFederationBinding>
  <binding>
    <security mode="None/Message/TransportWithMessageCredential">
      <message algorithmSuite="Basic128/Basic192/Basic256/Basic128Rsa15/Basic256Rsa15/TripleDes/TripleDesRsa15/Basic128Sha256/Basic192Sha256/TripleDesSha256/Basic128Sha256Rsa15/Basic192Sha256Rsa15/Basic256Sha256Rsa15/TripleDesSha256Rsa15"
               issuedTokenType="string"
               issuedKeyType="SymmetricKey/PublicKey"
               negotiateServiceCredential="Boolean">
        <claimTypeRequirements>
          <add claimType="URI"
               isOptional="Boolean" />
        </claimTypeRequirements>
        <issuer address="Uri" >
          <headers>
            <add name="String"
                 namespace="String" />
          </headers>
          <identity>
            <certificate encodedValue="String" />
            <certificateReference findValue="String"
                                  isChainIncluded="Boolean"
                                  storeName="AddressBook/AuthRoot/CertificateAuthority/Disallowed/My/Root/TrustedPeople/TrustedPublisher"
                                  storeLocation="LocalMachine/CurrentUser"
                                  X509FindType="System.Security.Cryptography.X509certificates.X509findtype" />
            <dns value="String" />
            <rsa value="String" />
            <servicePrincipalName value="String" />
            <usePrincipalName value="String" />
          </identity>
        </issuer>
        <issuerMetadata address="String">
          <headers>
            <add name="String"
                 namespace="String" />
          </headers>
          <identity>
            <certificate encodedValue="String" />
            <certificateReference findValue="String"
                                  isChainIncluded="Boolean"
                                  storeName="AddressBook/AuthRoot/CertificateAuthority/Disallowed/My/Root/TrustedPeople/TrustedPublisher"
                                  storeLocation="LocalMachine/CurrentUser"
                                  X509FindType="System.Security.Cryptography.X509certificates.X509findtype" />
            <dns value="String" />
            <rsa value="String" />
            <servicePrincipalName value="String" />
            <usePrincipalName value="String" />
          </identity>
        </issuerMetadata>
        <tokenRequestParameters>
          <xmlElement>
          </xmlElement>
        </tokenRequestParameters>
      </message>
    </security>
  </binding>
</wsFederationBinding>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="3a403-111">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="3a403-111">Attributes and Elements</span></span>  
 <span data-ttu-id="3a403-112">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="3a403-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="3a403-113">Attribute</span><span class="sxs-lookup"><span data-stu-id="3a403-113">Attributes</span></span>  
  
|<span data-ttu-id="3a403-114">Attribut</span><span class="sxs-lookup"><span data-stu-id="3a403-114">Attribute</span></span>|<span data-ttu-id="3a403-115">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="3a403-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="3a403-116">Modus</span><span class="sxs-lookup"><span data-stu-id="3a403-116">Mode</span></span>|<span data-ttu-id="3a403-117">Dies ist optional.</span><span class="sxs-lookup"><span data-stu-id="3a403-117">Optional.</span></span> <span data-ttu-id="3a403-118">Gibt den angewendeten Sicherheitstyp an.</span><span class="sxs-lookup"><span data-stu-id="3a403-118">Specifies the type of security that is applied.</span></span> <span data-ttu-id="3a403-119">Der Standardwert ist `Message`sein.</span><span class="sxs-lookup"><span data-stu-id="3a403-119">The default value is `Message`.</span></span> <span data-ttu-id="3a403-120">Dieses Attribut ist vom Typ <xref:System.ServiceModel.WSFederationHttpSecurityMode>.</span><span class="sxs-lookup"><span data-stu-id="3a403-120">This attribute is of type <xref:System.ServiceModel.WSFederationHttpSecurityMode>.</span></span>|  
  
## <a name="mode-attribute"></a><span data-ttu-id="3a403-121">Mode-Attribut</span><span class="sxs-lookup"><span data-stu-id="3a403-121">Mode Attribute</span></span>  
  
|<span data-ttu-id="3a403-122">Wert</span><span class="sxs-lookup"><span data-stu-id="3a403-122">Value</span></span>|<span data-ttu-id="3a403-123">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="3a403-123">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="3a403-124">Keiner</span><span class="sxs-lookup"><span data-stu-id="3a403-124">None</span></span>|<span data-ttu-id="3a403-125">Die SOAP-Nachricht ist während der Übertragung nicht sicher.</span><span class="sxs-lookup"><span data-stu-id="3a403-125">The SOAP message is not secure during transfer.</span></span>|  
|<span data-ttu-id="3a403-126">Nachricht</span><span class="sxs-lookup"><span data-stu-id="3a403-126">Message</span></span>|<span data-ttu-id="3a403-127">Integrität, Vertraulichkeit, Serverauthentifizierung und Clientauthentifizierung werden mittels SOAP-Nachrichtensicherheit bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="3a403-127">Integrity, confidentiality, server authentication and client authentication are provided using SOAP message security.</span></span> <span data-ttu-id="3a403-128">Standardmäßig wird der Text verschlüsselt und signiert.</span><span class="sxs-lookup"><span data-stu-id="3a403-128">By default, the body is encrypted and signed.</span></span> <span data-ttu-id="3a403-129">Der Dienst muss mit einem Zertifikat konfiguriert werden.</span><span class="sxs-lookup"><span data-stu-id="3a403-129">The service needs to be configured with a certificate.</span></span> <span data-ttu-id="3a403-130">Die Clientauthentifizierung basiert auf dem Token, das von einem Sicherheitstokendienst für den Client ausgestellt wird.</span><span class="sxs-lookup"><span data-stu-id="3a403-130">Client authentication is based on the token issued to the client by a security token service</span></span>|  
|<span data-ttu-id="3a403-131">TransportWithMessageCredential</span><span class="sxs-lookup"><span data-stu-id="3a403-131">TransportWithMessageCredential</span></span>|<span data-ttu-id="3a403-132">Integrität, Vertraulichkeit und Serverauthentifizierung werden über HTTPS bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="3a403-132">Integrity, confidentiality and server authentication are provided by HTTPS.</span></span> <span data-ttu-id="3a403-133">Der Dienst muss mit einem Zertifikat konfiguriert werden.</span><span class="sxs-lookup"><span data-stu-id="3a403-133">The service needs to be configured with a certificate.</span></span> <span data-ttu-id="3a403-134">Die Clientauthentifizierung wird mittels SOAP-Nachrichtensicherheit bereitgestellt und basiert auf dem Token, das von einem Sicherheitstokendienst für den Client ausgestellt wird.</span><span class="sxs-lookup"><span data-stu-id="3a403-134">Client authentication is provided by means of SOAP message security and is based on the token issued to the client by a security token service.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="3a403-135">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="3a403-135">Child Elements</span></span>  
  
|<span data-ttu-id="3a403-136">Element</span><span class="sxs-lookup"><span data-stu-id="3a403-136">Element</span></span>|<span data-ttu-id="3a403-137">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="3a403-137">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="3a403-138">\<message ></span><span class="sxs-lookup"><span data-stu-id="3a403-138">\<message></span></span>](message-element-of-wsfederationhttpbinding.md)|<span data-ttu-id="3a403-139">Definiert die Einstellungen für die Sicherheit auf Nachrichtenebene.</span><span class="sxs-lookup"><span data-stu-id="3a403-139">Defines the settings for the message-level security.</span></span> <span data-ttu-id="3a403-140">Dieses Element ist vom Typ <xref:System.ServiceModel.Configuration.FederatedMessageSecurityOverHttpElement>.</span><span class="sxs-lookup"><span data-stu-id="3a403-140">This element is of type <xref:System.ServiceModel.Configuration.FederatedMessageSecurityOverHttpElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="3a403-141">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="3a403-141">Parent Elements</span></span>  
  
|<span data-ttu-id="3a403-142">Element</span><span class="sxs-lookup"><span data-stu-id="3a403-142">Element</span></span>|<span data-ttu-id="3a403-143">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="3a403-143">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="3a403-144">\<binding ></span><span class="sxs-lookup"><span data-stu-id="3a403-144">\<binding></span></span>](bindings.md)|<span data-ttu-id="3a403-145">Definiert alle Bindungsfunktionen des [\<WSDualHttpBinding->](wsdualhttpbinding.md).</span><span class="sxs-lookup"><span data-stu-id="3a403-145">Defines all binding capabilities of the [\<wsDualHttpBinding>](wsdualhttpbinding.md).</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="3a403-146">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="3a403-146">See also</span></span>

- <xref:System.ServiceModel.WSFederationHttpSecurity>
- <xref:System.ServiceModel.WSFederationHttpBinding.Security%2A>
- <xref:System.ServiceModel.Configuration.WSFederationHttpBindingElement.Security%2A>
- <xref:System.ServiceModel.Configuration.WSFederationHttpSecurityElement>
- [<span data-ttu-id="3a403-147">Vorgehensweise: Erstellen einer WSFederationHttpBinding</span><span class="sxs-lookup"><span data-stu-id="3a403-147">How to: Create a WSFederationHttpBinding</span></span>](../../../wcf/feature-details/how-to-create-a-wsfederationhttpbinding.md)
- [<span data-ttu-id="3a403-148">Sichern von Diensten und Clients</span><span class="sxs-lookup"><span data-stu-id="3a403-148">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="3a403-149">Ausählen eines Anmeldeinformationentyps</span><span class="sxs-lookup"><span data-stu-id="3a403-149">Selecting a Credential Type</span></span>](../../../wcf/feature-details/selecting-a-credential-type.md)
- [<span data-ttu-id="3a403-150">Bindungen</span><span class="sxs-lookup"><span data-stu-id="3a403-150">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="3a403-151">Konfigurieren der vom System bereitgestellten Bindungen</span><span class="sxs-lookup"><span data-stu-id="3a403-151">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="3a403-152">Verwenden von Bindungen, um Dienste und Clients zu konfigurieren</span><span class="sxs-lookup"><span data-stu-id="3a403-152">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [<span data-ttu-id="3a403-153">\<binding ></span><span class="sxs-lookup"><span data-stu-id="3a403-153">\<binding></span></span>](bindings.md)
