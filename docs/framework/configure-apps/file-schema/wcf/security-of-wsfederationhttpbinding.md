---
title: <security> von <wsFederationHttpBinding>
ms.date: 03/30/2017
ms.assetid: a8e5e854-b8dc-4921-843d-34b6a4a6a8ba
ms.openlocfilehash: 650483099c7d70450cfc56a9a28efac076d64675
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91162234"
---
# <a name="security-of-wsfederationhttpbinding"></a><span data-ttu-id="e67c4-102">\<security> von \<wsFederationHttpBinding></span><span class="sxs-lookup"><span data-stu-id="e67c4-102">\<security> of \<wsFederationHttpBinding></span></span>

<span data-ttu-id="e67c4-103">Definiert die Sicherheitseinstellungen des [\<wsFederationHttpBinding>](wsfederationhttpbinding.md) .</span><span class="sxs-lookup"><span data-stu-id="e67c4-103">Defines the security settings of the [\<wsFederationHttpBinding>](wsfederationhttpbinding.md).</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<wsFederationHttpBinding>**](wsfederationhttpbinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<security>**  
  
## <a name="syntax"></a><span data-ttu-id="e67c4-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="e67c4-104">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="e67c4-105">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="e67c4-105">Attributes and Elements</span></span>  

 <span data-ttu-id="e67c4-106">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="e67c4-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="e67c4-107">Attribute</span><span class="sxs-lookup"><span data-stu-id="e67c4-107">Attributes</span></span>  
  
|<span data-ttu-id="e67c4-108">attribute</span><span class="sxs-lookup"><span data-stu-id="e67c4-108">Attribute</span></span>|<span data-ttu-id="e67c4-109">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="e67c4-109">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="e67c4-110">Mode</span><span class="sxs-lookup"><span data-stu-id="e67c4-110">Mode</span></span>|<span data-ttu-id="e67c4-111">Dies ist optional.</span><span class="sxs-lookup"><span data-stu-id="e67c4-111">Optional.</span></span> <span data-ttu-id="e67c4-112">Gibt den angewendeten Sicherheitstyp an.</span><span class="sxs-lookup"><span data-stu-id="e67c4-112">Specifies the type of security that is applied.</span></span> <span data-ttu-id="e67c4-113">Standardwert: `Message`.</span><span class="sxs-lookup"><span data-stu-id="e67c4-113">The default value is `Message`.</span></span> <span data-ttu-id="e67c4-114">Dieses Attribut ist vom Typ <xref:System.ServiceModel.WSFederationHttpSecurityMode>.</span><span class="sxs-lookup"><span data-stu-id="e67c4-114">This attribute is of type <xref:System.ServiceModel.WSFederationHttpSecurityMode>.</span></span>|  
  
## <a name="mode-attribute"></a><span data-ttu-id="e67c4-115">Mode-Attribut</span><span class="sxs-lookup"><span data-stu-id="e67c4-115">Mode Attribute</span></span>  
  
|<span data-ttu-id="e67c4-116">Wert</span><span class="sxs-lookup"><span data-stu-id="e67c4-116">Value</span></span>|<span data-ttu-id="e67c4-117">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="e67c4-117">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="e67c4-118">Keine</span><span class="sxs-lookup"><span data-stu-id="e67c4-118">None</span></span>|<span data-ttu-id="e67c4-119">Die SOAP-Nachricht ist während der Übertragung nicht sicher.</span><span class="sxs-lookup"><span data-stu-id="e67c4-119">The SOAP message is not secure during transfer.</span></span>|  
|<span data-ttu-id="e67c4-120">`Message`</span><span class="sxs-lookup"><span data-stu-id="e67c4-120">Message</span></span>|<span data-ttu-id="e67c4-121">Integrität, Vertraulichkeit, Serverauthentifizierung und Clientauthentifizierung werden mittels SOAP-Nachrichtensicherheit bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="e67c4-121">Integrity, confidentiality, server authentication and client authentication are provided using SOAP message security.</span></span> <span data-ttu-id="e67c4-122">Standardmäßig wird der Text verschlüsselt und signiert.</span><span class="sxs-lookup"><span data-stu-id="e67c4-122">By default, the body is encrypted and signed.</span></span> <span data-ttu-id="e67c4-123">Der Dienst muss mit einem Zertifikat konfiguriert werden.</span><span class="sxs-lookup"><span data-stu-id="e67c4-123">The service needs to be configured with a certificate.</span></span> <span data-ttu-id="e67c4-124">Die Clientauthentifizierung basiert auf dem Token, das von einem Sicherheitstokendienst für den Client ausgestellt wird.</span><span class="sxs-lookup"><span data-stu-id="e67c4-124">Client authentication is based on the token issued to the client by a security token service</span></span>|  
|<span data-ttu-id="e67c4-125">TransportWithMessageCredential</span><span class="sxs-lookup"><span data-stu-id="e67c4-125">TransportWithMessageCredential</span></span>|<span data-ttu-id="e67c4-126">Integrität, Vertraulichkeit und Serverauthentifizierung werden über HTTPS bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="e67c4-126">Integrity, confidentiality and server authentication are provided by HTTPS.</span></span> <span data-ttu-id="e67c4-127">Der Dienst muss mit einem Zertifikat konfiguriert werden.</span><span class="sxs-lookup"><span data-stu-id="e67c4-127">The service needs to be configured with a certificate.</span></span> <span data-ttu-id="e67c4-128">Die Clientauthentifizierung wird mittels SOAP-Nachrichtensicherheit bereitgestellt und basiert auf dem Token, das von einem Sicherheitstokendienst für den Client ausgestellt wird.</span><span class="sxs-lookup"><span data-stu-id="e67c4-128">Client authentication is provided by means of SOAP message security and is based on the token issued to the client by a security token service.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="e67c4-129">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="e67c4-129">Child Elements</span></span>  
  
|<span data-ttu-id="e67c4-130">Element</span><span class="sxs-lookup"><span data-stu-id="e67c4-130">Element</span></span>|<span data-ttu-id="e67c4-131">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="e67c4-131">Description</span></span>|  
|-------------|-----------------|  
|[\<message>](message-element-of-wsfederationhttpbinding.md)|<span data-ttu-id="e67c4-132">Definiert die Einstellungen für die Sicherheit auf Nachrichtenebene.</span><span class="sxs-lookup"><span data-stu-id="e67c4-132">Defines the settings for the message-level security.</span></span> <span data-ttu-id="e67c4-133">Dieses Element ist vom Typ <xref:System.ServiceModel.Configuration.FederatedMessageSecurityOverHttpElement>.</span><span class="sxs-lookup"><span data-stu-id="e67c4-133">This element is of type <xref:System.ServiceModel.Configuration.FederatedMessageSecurityOverHttpElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="e67c4-134">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="e67c4-134">Parent Elements</span></span>  
  
|<span data-ttu-id="e67c4-135">Element</span><span class="sxs-lookup"><span data-stu-id="e67c4-135">Element</span></span>|<span data-ttu-id="e67c4-136">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="e67c4-136">Description</span></span>|  
|-------------|-----------------|  
|[\<binding>](bindings.md)|<span data-ttu-id="e67c4-137">Definiert alle Bindungsfunktionen von [\<wsDualHttpBinding>](wsdualhttpbinding.md) .</span><span class="sxs-lookup"><span data-stu-id="e67c4-137">Defines all binding capabilities of the [\<wsDualHttpBinding>](wsdualhttpbinding.md).</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="e67c4-138">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="e67c4-138">See also</span></span>

- <xref:System.ServiceModel.WSFederationHttpSecurity>
- <xref:System.ServiceModel.WSFederationHttpBinding.Security%2A>
- <xref:System.ServiceModel.Configuration.WSFederationHttpBindingElement.Security%2A>
- <xref:System.ServiceModel.Configuration.WSFederationHttpSecurityElement>
- [<span data-ttu-id="e67c4-139">Vorgehensweise: Erstellen einer WSFederationHttpBinding</span><span class="sxs-lookup"><span data-stu-id="e67c4-139">How to: Create a WSFederationHttpBinding</span></span>](../../../wcf/feature-details/how-to-create-a-wsfederationhttpbinding.md)
- [<span data-ttu-id="e67c4-140">Sichern von Diensten und Clients</span><span class="sxs-lookup"><span data-stu-id="e67c4-140">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="e67c4-141">Wählen eines Typs von Anmeldeinformationen</span><span class="sxs-lookup"><span data-stu-id="e67c4-141">Selecting a Credential Type</span></span>](../../../wcf/feature-details/selecting-a-credential-type.md)
- [<span data-ttu-id="e67c4-142">Bindungen</span><span class="sxs-lookup"><span data-stu-id="e67c4-142">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="e67c4-143">Konfigurieren der vom System bereitgestellten Bindungen</span><span class="sxs-lookup"><span data-stu-id="e67c4-143">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="e67c4-144">Verwenden von Bindungen, um Dienste und Clients zu konfigurieren</span><span class="sxs-lookup"><span data-stu-id="e67c4-144">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [\<binding>](bindings.md)
