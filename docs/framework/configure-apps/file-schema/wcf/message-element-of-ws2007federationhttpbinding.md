---
title: <message>Element von<ws2007FederationHttpBinding>
ms.date: 03/30/2017
ms.assetid: 52cd941d-e230-4c82-8b29-333a7d20eca8
ms.openlocfilehash: dde763687dbc62d6fb342a21a4c614208f28d7e8
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/06/2020
ms.locfileid: "73739000"
---
# <a name="message-element-of-ws2007federationhttpbinding"></a><span data-ttu-id="7429f-102">\<message>Element von\<ws2007FederationHttpBinding></span><span class="sxs-lookup"><span data-stu-id="7429f-102">\<message> element of \<ws2007FederationHttpBinding></span></span>
<span data-ttu-id="7429f-103">Definiert Einstellungen für die Sicherheit auf Nachrichten Ebene für das- [\<ws2007FederationHttpBinding>](ws2007federationhttpbinding.md) Element.</span><span class="sxs-lookup"><span data-stu-id="7429f-103">Defines settings for the message-level security for the [\<ws2007FederationHttpBinding>](ws2007federationhttpbinding.md) element.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<ws2007FederationHttpBinding>**](ws2007federationhttpbinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<security>**](security-element-of-ws2007federationhttpbinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<message>**  
  
## <a name="syntax"></a><span data-ttu-id="7429f-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="7429f-104">Syntax</span></span>  
  
```xml  
<ws2007FederationBinding>
  <binding>
    <security>
      <message algorithmSuite="Basic128/Basic192/Basic256/Basic128Rsa15/Basic256Rsa15/TripleDes/TripleDesRsa15/Basic128Sha256/Basic192Sha256/TripleDesSha256/Basic128Sha256Rsa15/Basic192Sha256Rsa15/Basic256Sha256Rsa15/TripleDesSha256Rsa15"
               issuedTokenType="string"
               issuedKeyType="SymmetricKey/PublicKey"
               negotiateServiceCredential="Boolean">
        <claimTypeRequirements>
          <add claimType="URI"
               isOptional="Boolean" />
        </claimTypeRequirements>
        <issuer address="Uri">
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
                                  x509FindType="System.Security.Cryptography.X509certificates.X509findtype" />
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
</ws2007FederationBinding>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="7429f-105">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="7429f-105">Attributes and Elements</span></span>  
 <span data-ttu-id="7429f-106">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="7429f-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="7429f-107">Attribute</span><span class="sxs-lookup"><span data-stu-id="7429f-107">Attributes</span></span>  
  
|<span data-ttu-id="7429f-108">attribute</span><span class="sxs-lookup"><span data-stu-id="7429f-108">Attribute</span></span>|<span data-ttu-id="7429f-109">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="7429f-109">Description</span></span>|  
|---------------|-----------------|  
|`algorithmSuite`|<span data-ttu-id="7429f-110">Optional.</span><span class="sxs-lookup"><span data-stu-id="7429f-110">Optional.</span></span> <span data-ttu-id="7429f-111">Legt die Nachrichtenverschlüsselung, Signatur und Key Wrap-Algorithmen fest.</span><span class="sxs-lookup"><span data-stu-id="7429f-111">Sets the message encryption, signature, and key-wrap algorithms.</span></span> <span data-ttu-id="7429f-112">Die Algorithmen und die Schlüsselgröße werden durch die <xref:System.ServiceModel.Security.SecurityAlgorithmSuite>-Klasse ermittelt.</span><span class="sxs-lookup"><span data-stu-id="7429f-112">The algorithms and the key sizes are determined by the <xref:System.ServiceModel.Security.SecurityAlgorithmSuite> class.</span></span> <span data-ttu-id="7429f-113">Diese Algorithmen sind den Algorithmen in der Spezifikation der Sicherheitsrichtliniensprache (WS-SecurityPolicy) zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="7429f-113">These algorithms map to those specified in the Security Policy Language (WS-SecurityPolicy) specification.</span></span><br /><br /> <span data-ttu-id="7429f-114">In der folgenden Tabelle sind die möglichen Werte aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="7429f-114">See the following table for possible values.</span></span> <span data-ttu-id="7429f-115">Der Standardwert ist Basic256.</span><span class="sxs-lookup"><span data-stu-id="7429f-115">The default value is Basic256.</span></span>|  
|`issuedKeyType`|<span data-ttu-id="7429f-116">Gibt den Typ des auszustellenden Schlüssels an.</span><span class="sxs-lookup"><span data-stu-id="7429f-116">Specifies the type of key to be issued.</span></span> <span data-ttu-id="7429f-117">Gültige Werte sind:</span><span class="sxs-lookup"><span data-stu-id="7429f-117">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="7429f-118">-SymmetricKey</span><span class="sxs-lookup"><span data-stu-id="7429f-118">-   SymmetricKey</span></span><br /><span data-ttu-id="7429f-119">-PublicKey</span><span class="sxs-lookup"><span data-stu-id="7429f-119">-   PublicKey</span></span><br /><span data-ttu-id="7429f-120">-Bearerkey</span><span class="sxs-lookup"><span data-stu-id="7429f-120">-   BearerKey</span></span><br /><br /> <span data-ttu-id="7429f-121">Der Standardwert ist SymmetricKey.</span><span class="sxs-lookup"><span data-stu-id="7429f-121">The default is SymmetricKey.</span></span> <span data-ttu-id="7429f-122">Dieses Attribut ist vom Typ <xref:System.IdentityModel.Tokens.SecurityKeyType>.</span><span class="sxs-lookup"><span data-stu-id="7429f-122">This attribute is of type <xref:System.IdentityModel.Tokens.SecurityKeyType>.</span></span>|  
|`issuedTokenType`|<span data-ttu-id="7429f-123">Ein URI, der den Typ des auszustellenden Tokens angibt.</span><span class="sxs-lookup"><span data-stu-id="7429f-123">A URI that specifies the type of token to be issued.</span></span> <span data-ttu-id="7429f-124">Der Standardwert lautet `null`.</span><span class="sxs-lookup"><span data-stu-id="7429f-124">The default is `null`.</span></span>|  
|`negotiateServiceCredential`|<span data-ttu-id="7429f-125">Ein Wert, der angibt, ob die Dienstanmeldeinformationen als Teil der Aushandlung ausgetauscht werden sollen oder ob sie out-of-band zur Verfügung stehen.</span><span class="sxs-lookup"><span data-stu-id="7429f-125">A value that specifies whether the service credential should be exchanged as part of negotiation or is available out of band.</span></span> <span data-ttu-id="7429f-126">Der Standardwert ist `true`, was bedeutet, dass die Dienstanmeldeinformationen ausgehandelt werden.</span><span class="sxs-lookup"><span data-stu-id="7429f-126">The default is `true`, which means that the service credential is negotiated.</span></span>|  
  
## <a name="algorithmsuite-attribute"></a><span data-ttu-id="7429f-127">algorithmSuite-Attribut</span><span class="sxs-lookup"><span data-stu-id="7429f-127">algorithmSuite Attribute</span></span>  
  
|<span data-ttu-id="7429f-128">Wert</span><span class="sxs-lookup"><span data-stu-id="7429f-128">Value</span></span>|<span data-ttu-id="7429f-129">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="7429f-129">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="7429f-130">Basic128</span><span class="sxs-lookup"><span data-stu-id="7429f-130">Basic128</span></span>|<span data-ttu-id="7429f-131">Verwendet Aes128-Verschlüsselung, Sha1 für den Nachrichtenhash und Rsa-oaep-mgf1p für Key Wrap.</span><span class="sxs-lookup"><span data-stu-id="7429f-131">Use Aes128 encryption, Sha1 for message digest, and Rsa-oaep-mgf1p for key wrap.</span></span>|  
|<span data-ttu-id="7429f-132">Basic192</span><span class="sxs-lookup"><span data-stu-id="7429f-132">Basic192</span></span>|<span data-ttu-id="7429f-133">Verwendet Aes192-Verschlüsselung, Sha1 für den Nachrichtenhash und Rsa-oaep-mgf1p für Key Wrap.</span><span class="sxs-lookup"><span data-stu-id="7429f-133">Use Aes192 encryption, Sha1 for message digest, Rsa-oaep-mgf1p for key wrap.</span></span>|  
|<span data-ttu-id="7429f-134">Basic256</span><span class="sxs-lookup"><span data-stu-id="7429f-134">Basic256</span></span>|<span data-ttu-id="7429f-135">Verwendet Aes256-Verschlüsselung, Sha1 für den Nachrichtenhash und Rsa-oaep-mgf1p für Key Wrap.</span><span class="sxs-lookup"><span data-stu-id="7429f-135">Use Aes256 encryption, Sha1 for message digest, Rsa-oaep-mgf1p for key wrap.</span></span>|  
|<span data-ttu-id="7429f-136">Basic256Rsa15</span><span class="sxs-lookup"><span data-stu-id="7429f-136">Basic256Rsa15</span></span>|<span data-ttu-id="7429f-137">Verwendet Aes256-Nachrichtenverschlüsselung, Sha1 für den Nachrichtenhash und Rsa15 für Key Wrap.</span><span class="sxs-lookup"><span data-stu-id="7429f-137">Use Aes256 for message encryption, Sha1 for message digest and Rsa15 for key wrap.</span></span>|  
|<span data-ttu-id="7429f-138">Basic192Rsa15</span><span class="sxs-lookup"><span data-stu-id="7429f-138">Basic192Rsa15</span></span>|<span data-ttu-id="7429f-139">Verwendet Aes192 für die Nachrichtenverschlüsselung, Sha1 für den Nachrichtenhash und Rsa15 für Key Wrap.</span><span class="sxs-lookup"><span data-stu-id="7429f-139">Use Aes192 for message encryption, Sha1 for message digest and Rsa15 for key wrap.</span></span>|  
|<span data-ttu-id="7429f-140">TripleDes</span><span class="sxs-lookup"><span data-stu-id="7429f-140">TripleDes</span></span>|<span data-ttu-id="7429f-141">Verwendet TripleDes-Verschlüsselung, Sha1 für den Nachrichtenhash und Rsa-oaep-mgf1p für Key Wrap.</span><span class="sxs-lookup"><span data-stu-id="7429f-141">Use TripleDes encryption, Sha1 for message digest, Rsa-oaep-mgf1p for key wrap.</span></span>|  
|<span data-ttu-id="7429f-142">Basic128Rsa15</span><span class="sxs-lookup"><span data-stu-id="7429f-142">Basic128Rsa15</span></span>|<span data-ttu-id="7429f-143">Verwendet Aes128 für die Nachrichtenverschlüsselung, Sha1 für den Nachrichtenhash und Rsa15 für Key Wrap.</span><span class="sxs-lookup"><span data-stu-id="7429f-143">Use Aes128 for message encryption, Sha1 for message digest and Rsa15 for key wrap.</span></span>|  
|<span data-ttu-id="7429f-144">TripleDesRsa15</span><span class="sxs-lookup"><span data-stu-id="7429f-144">TripleDesRsa15</span></span>|<span data-ttu-id="7429f-145">Verwendet TripleDes-Verschlüsselung, Sha1 für den Nachrichtenhash und Rsa15 für Key Wrap.</span><span class="sxs-lookup"><span data-stu-id="7429f-145">Use TripleDes encryption, Sha1 for message digest and Rsa15 for key wrap.</span></span>|  
|<span data-ttu-id="7429f-146">Basic128Sha256</span><span class="sxs-lookup"><span data-stu-id="7429f-146">Basic128Sha256</span></span>|<span data-ttu-id="7429f-147">Verwendet Aes256-Nachrichtenverschlüsselung, Sha256 für den Nachrichtenhash und Rsa-oaep-mgf1p für Key Wrap.</span><span class="sxs-lookup"><span data-stu-id="7429f-147">Use Aes256 for message encryption, Sha256 for message digest and Rsa-oaep-mgf1p for key wrap.</span></span>|  
|<span data-ttu-id="7429f-148">Basic192Sha256</span><span class="sxs-lookup"><span data-stu-id="7429f-148">Basic192Sha256</span></span>|<span data-ttu-id="7429f-149">Verwendet Aes192 für die Nachrichtenverschlüsselung, Sha256 für den Nachrichtenhash und Rsa-oaep-mgf1p für Key Wrap.</span><span class="sxs-lookup"><span data-stu-id="7429f-149">Use Aes192 for message encryption, Sha256 for message digest and Rsa-oaep-mgf1p for key wrap.</span></span>|  
|<span data-ttu-id="7429f-150">Basic256Sha256</span><span class="sxs-lookup"><span data-stu-id="7429f-150">Basic256Sha256</span></span>|<span data-ttu-id="7429f-151">Verwendet Aes256-Nachrichtenverschlüsselung, Sha256 für den Nachrichtenhash und Rsa-oaep-mgf1p für Key Wrap.</span><span class="sxs-lookup"><span data-stu-id="7429f-151">Use Aes256 for message encryption, Sha256 for message digest and Rsa-oaep-mgf1p for key wrap.</span></span>|  
|<span data-ttu-id="7429f-152">TripleDesSha256</span><span class="sxs-lookup"><span data-stu-id="7429f-152">TripleDesSha256</span></span>|<span data-ttu-id="7429f-153">Verwendet TripleDes für die Nachrichtenverschlüsselung, Sha256 für den Nachrichtenhash und Rsa-oaep-mgf1p für Key Wrap.</span><span class="sxs-lookup"><span data-stu-id="7429f-153">Use TripleDes for message encryption, Sha256 for message digest and Rsa-oaep-mgf1p for key wrap.</span></span>|  
|<span data-ttu-id="7429f-154">Basic128Sha256Rsa15</span><span class="sxs-lookup"><span data-stu-id="7429f-154">Basic128Sha256Rsa15</span></span>|<span data-ttu-id="7429f-155">Verwendet Aes128 für die Nachrichtenverschlüsselung, Sha256 für den Nachrichtenhash und Rsa15 für Key Wrap.</span><span class="sxs-lookup"><span data-stu-id="7429f-155">Use Aes128 for message encryption, Sha256 for message digest and Rsa15 for key wrap.</span></span>|  
|<span data-ttu-id="7429f-156">Basic192Sha256Rsa15</span><span class="sxs-lookup"><span data-stu-id="7429f-156">Basic192Sha256Rsa15</span></span>|<span data-ttu-id="7429f-157">Verwendet Aes192 für die Nachrichtenverschlüsselung, Sha256 für den Nachrichtenhash und Rsa15 für Key Wrap.</span><span class="sxs-lookup"><span data-stu-id="7429f-157">Use Aes192 for message encryption, Sha256 for message digest and Rsa15 for key wrap.</span></span>|  
|<span data-ttu-id="7429f-158">Basic256Sha256Rsa15</span><span class="sxs-lookup"><span data-stu-id="7429f-158">Basic256Sha256Rsa15</span></span>|<span data-ttu-id="7429f-159">Verwendet Aes256 für die Nachrichtenverschlüsselung, Sha256 für den Nachrichtenhash und Rsa15 für Key Wrap.</span><span class="sxs-lookup"><span data-stu-id="7429f-159">Use Aes256 for message encryption, Sha256 for message digest and Rsa15 for key wrap.</span></span>|  
|<span data-ttu-id="7429f-160">TripleDesSha256Rsa15</span><span class="sxs-lookup"><span data-stu-id="7429f-160">TripleDesSha256Rsa15</span></span>|<span data-ttu-id="7429f-161">Verwendet TripleDes für die Nachrichtenverschlüsselung, Sha256 für den Nachrichtenhash und Rsa15 für Key Wrap.</span><span class="sxs-lookup"><span data-stu-id="7429f-161">Use TripleDes for message encryption, Sha256 for message digest and Rsa15 for key wrap.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="7429f-162">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="7429f-162">Child Elements</span></span>  
  
|<span data-ttu-id="7429f-163">Element</span><span class="sxs-lookup"><span data-stu-id="7429f-163">Element</span></span>|<span data-ttu-id="7429f-164">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="7429f-164">Description</span></span>|  
|-------------|-----------------|  
|[\<claimTypeRequirements>](claimtyperequirements-element.md)|<span data-ttu-id="7429f-165">Gibt eine Auflistung von Anspruchstypen für diese Bindung an.</span><span class="sxs-lookup"><span data-stu-id="7429f-165">Specifies a collection of claim types for this binding.</span></span> <span data-ttu-id="7429f-166">Jedes Element ist vom Typ <xref:System.ServiceModel.Configuration.ClaimTypeElement>.</span><span class="sxs-lookup"><span data-stu-id="7429f-166">Each element is of type <xref:System.ServiceModel.Configuration.ClaimTypeElement>.</span></span>|  
|[\<issuer>](issuer.md)|<span data-ttu-id="7429f-167">Gibt einen Endpunkt an, der ein Sicherheitstoken ausstellt.</span><span class="sxs-lookup"><span data-stu-id="7429f-167">Specifies an endpoint that issues a security token.</span></span> <span data-ttu-id="7429f-168">Dieses Element ist vom Typ <xref:System.ServiceModel.Configuration.IssuedTokenParametersEndpointAddressElement>.</span><span class="sxs-lookup"><span data-stu-id="7429f-168">This element is of type <xref:System.ServiceModel.Configuration.IssuedTokenParametersEndpointAddressElement>.</span></span>|  
|[\<issuerMetadata>](issuermetadata.md)|<span data-ttu-id="7429f-169">Gibt die Endpunktadresse des Ausstellers an.</span><span class="sxs-lookup"><span data-stu-id="7429f-169">Specifies the endpoint address of the issuer.</span></span>|  
|[\<tokenRequestParameters>](tokenrequestparameters.md)|<span data-ttu-id="7429f-170">Eine Auflistung von Tokenanforderungsparametern.</span><span class="sxs-lookup"><span data-stu-id="7429f-170">A collection of token request parameters.</span></span> <span data-ttu-id="7429f-171">Jeder Parameter ist ein XML-Element.</span><span class="sxs-lookup"><span data-stu-id="7429f-171">Each parameter is an XML element.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="7429f-172">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="7429f-172">Parent Elements</span></span>  
  
|<span data-ttu-id="7429f-173">Element</span><span class="sxs-lookup"><span data-stu-id="7429f-173">Element</span></span>|<span data-ttu-id="7429f-174">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="7429f-174">Description</span></span>|  
|-------------|-----------------|  
|[\<security>](security-element-of-ws2007federationhttpbinding.md)|<span data-ttu-id="7429f-175">Definiert die Sicherheitseinstellungen für eine Bindung.</span><span class="sxs-lookup"><span data-stu-id="7429f-175">Defines the security settings for a binding.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="7429f-176">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="7429f-176">See also</span></span>

- <xref:System.ServiceModel.FederatedMessageSecurityOverHttp>
- <xref:System.ServiceModel.Configuration.WSFederationHttpSecurityElement.Message%2A>
- <xref:System.ServiceModel.WSFederationHttpSecurity.Message%2A>
- <xref:System.ServiceModel.Configuration.FederatedMessageSecurityOverHttpElement>
- [<span data-ttu-id="7429f-177">Sichern von Diensten und Clients</span><span class="sxs-lookup"><span data-stu-id="7429f-177">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="7429f-178">Bindungen</span><span class="sxs-lookup"><span data-stu-id="7429f-178">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="7429f-179">Konfigurieren der vom System bereitgestellten Bindungen</span><span class="sxs-lookup"><span data-stu-id="7429f-179">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="7429f-180">Verwenden von Bindungen, um Dienste und Clients zu konfigurieren</span><span class="sxs-lookup"><span data-stu-id="7429f-180">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [\<binding>](bindings.md)
