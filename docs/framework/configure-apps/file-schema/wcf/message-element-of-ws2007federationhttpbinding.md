---
title: '&lt;message&gt;-Element von &lt;ws2007FederationHttpBinding&gt;'
ms.date: 03/30/2017
ms.assetid: 52cd941d-e230-4c82-8b29-333a7d20eca8
ms.openlocfilehash: 280d92978dba44d3347699959fb2cab3b98faca1
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54493806"
---
# <a name="ltmessagegt-element-of-ltws2007federationhttpbindinggt"></a><span data-ttu-id="e59f3-102">&lt;message&gt;-Element von &lt;ws2007FederationHttpBinding&gt;</span><span class="sxs-lookup"><span data-stu-id="e59f3-102">&lt;message&gt; element of &lt;ws2007FederationHttpBinding&gt;</span></span>
<span data-ttu-id="e59f3-103">Definiert die Einstellungen für die Sicherheit auf Nachrichtenebene für die [ \<ws2007FederationHttpBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/ws2007federationhttpbinding.md) Element.</span><span class="sxs-lookup"><span data-stu-id="e59f3-103">Defines settings for the message-level security for the [\<ws2007FederationHttpBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/ws2007federationhttpbinding.md) element.</span></span>  
  
 <span data-ttu-id="e59f3-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="e59f3-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="e59f3-105">\<bindings></span><span class="sxs-lookup"><span data-stu-id="e59f3-105">\<bindings></span></span>  
<span data-ttu-id="e59f3-106">\<ws2007FederationHttpBinding></span><span class="sxs-lookup"><span data-stu-id="e59f3-106">\<ws2007FederationHttpBinding></span></span>  
<span data-ttu-id="e59f3-107">\<binding></span><span class="sxs-lookup"><span data-stu-id="e59f3-107">\<binding></span></span>  
<span data-ttu-id="e59f3-108">\<security></span><span class="sxs-lookup"><span data-stu-id="e59f3-108">\<security></span></span>  
<span data-ttu-id="e59f3-109">\<message></span><span class="sxs-lookup"><span data-stu-id="e59f3-109">\<message></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e59f3-110">Syntax</span><span class="sxs-lookup"><span data-stu-id="e59f3-110">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="e59f3-111">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="e59f3-111">Attributes and Elements</span></span>  
 <span data-ttu-id="e59f3-112">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="e59f3-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="e59f3-113">Attribute</span><span class="sxs-lookup"><span data-stu-id="e59f3-113">Attributes</span></span>  
  
|<span data-ttu-id="e59f3-114">Attribut</span><span class="sxs-lookup"><span data-stu-id="e59f3-114">Attribute</span></span>|<span data-ttu-id="e59f3-115">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="e59f3-115">Description</span></span>|  
|---------------|-----------------|  
|`algorithmSuite`|<span data-ttu-id="e59f3-116">Dies ist optional.</span><span class="sxs-lookup"><span data-stu-id="e59f3-116">Optional.</span></span> <span data-ttu-id="e59f3-117">Legt die Nachrichtenverschlüsselung, Signatur und Key Wrap-Algorithmen fest.</span><span class="sxs-lookup"><span data-stu-id="e59f3-117">Sets the message encryption, signature, and key-wrap algorithms.</span></span> <span data-ttu-id="e59f3-118">Die Algorithmen und die Schlüsselgröße werden durch die <xref:System.ServiceModel.Security.SecurityAlgorithmSuite>-Klasse ermittelt.</span><span class="sxs-lookup"><span data-stu-id="e59f3-118">The algorithms and the key sizes are determined by the <xref:System.ServiceModel.Security.SecurityAlgorithmSuite> class.</span></span> <span data-ttu-id="e59f3-119">Diese Algorithmen entsprechen den in der Security Policy Language (WS-SecurityPolicy)-Spezifikation angegebenen Algorithmen.</span><span class="sxs-lookup"><span data-stu-id="e59f3-119">These algorithms map to those specified in the Security Policy Language (WS-SecurityPolicy) specification.</span></span><br /><br /> <span data-ttu-id="e59f3-120">In der folgenden Tabelle sind die möglichen Werte aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="e59f3-120">See the following table for possible values.</span></span> <span data-ttu-id="e59f3-121">Der Standardwert ist Basic256.</span><span class="sxs-lookup"><span data-stu-id="e59f3-121">The default value is Basic256.</span></span>|  
|`issuedKeyType`|<span data-ttu-id="e59f3-122">Gibt den Typ des auszustellenden Schlüssels an.</span><span class="sxs-lookup"><span data-stu-id="e59f3-122">Specifies the type of key to be issued.</span></span> <span data-ttu-id="e59f3-123">Folgende Werte sind gültig:</span><span class="sxs-lookup"><span data-stu-id="e59f3-123">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="e59f3-124">-"SymmetricKey"</span><span class="sxs-lookup"><span data-stu-id="e59f3-124">-   SymmetricKey</span></span><br /><span data-ttu-id="e59f3-125">: Öffentlicher Schlüssel</span><span class="sxs-lookup"><span data-stu-id="e59f3-125">-   PublicKey</span></span><br /><span data-ttu-id="e59f3-126">-BearerKey</span><span class="sxs-lookup"><span data-stu-id="e59f3-126">-   BearerKey</span></span><br /><br /> <span data-ttu-id="e59f3-127">Der Standardwert ist SymmetricKey.</span><span class="sxs-lookup"><span data-stu-id="e59f3-127">The default is SymmetricKey.</span></span> <span data-ttu-id="e59f3-128">Dieses Attribut ist vom Typ <xref:System.IdentityModel.Tokens.SecurityKeyType>.</span><span class="sxs-lookup"><span data-stu-id="e59f3-128">This attribute is of type <xref:System.IdentityModel.Tokens.SecurityKeyType>.</span></span>|  
|`issuedTokenType`|<span data-ttu-id="e59f3-129">Ein URI, der den Typ des auszustellenden Tokens angibt.</span><span class="sxs-lookup"><span data-stu-id="e59f3-129">A URI that specifies the type of token to be issued.</span></span> <span data-ttu-id="e59f3-130">Die Standardeinstellung ist `null`.</span><span class="sxs-lookup"><span data-stu-id="e59f3-130">The default is `null`.</span></span>|  
|`negotiateServiceCredential`|<span data-ttu-id="e59f3-131">Ein Wert, der angibt, ob die Dienstanmeldeinformationen als Teil der Aushandlung ausgetauscht werden sollen oder ob sie out-of-band zur Verfügung stehen.</span><span class="sxs-lookup"><span data-stu-id="e59f3-131">A value that specifies whether the service credential should be exchanged as part of negotiation or is available out of band.</span></span> <span data-ttu-id="e59f3-132">Der Standardwert ist `true`, was bedeutet, dass die Dienstanmeldeinformationen ausgehandelt werden.</span><span class="sxs-lookup"><span data-stu-id="e59f3-132">The default is `true`, which means that the service credential is negotiated.</span></span>|  
  
## <a name="algorithmsuite-attribute"></a><span data-ttu-id="e59f3-133">algorithmSuite-Attribut</span><span class="sxs-lookup"><span data-stu-id="e59f3-133">algorithmSuite Attribute</span></span>  
  
|<span data-ttu-id="e59f3-134">Wert</span><span class="sxs-lookup"><span data-stu-id="e59f3-134">Value</span></span>|<span data-ttu-id="e59f3-135">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="e59f3-135">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="e59f3-136">Basic128</span><span class="sxs-lookup"><span data-stu-id="e59f3-136">Basic128</span></span>|<span data-ttu-id="e59f3-137">Verwendet Aes128-Verschlüsselung, Sha1 für den Nachrichtenhash und Rsa-oaep-mgf1p für Key Wrap.</span><span class="sxs-lookup"><span data-stu-id="e59f3-137">Use Aes128 encryption, Sha1 for message digest, and Rsa-oaep-mgf1p for key wrap.</span></span>|  
|<span data-ttu-id="e59f3-138">Basic192</span><span class="sxs-lookup"><span data-stu-id="e59f3-138">Basic192</span></span>|<span data-ttu-id="e59f3-139">Verwendet Aes192-Verschlüsselung, Sha1 für den Nachrichtenhash und Rsa-oaep-mgf1p für Key Wrap.</span><span class="sxs-lookup"><span data-stu-id="e59f3-139">Use Aes192 encryption, Sha1 for message digest, Rsa-oaep-mgf1p for key wrap.</span></span>|  
|<span data-ttu-id="e59f3-140">Basic256</span><span class="sxs-lookup"><span data-stu-id="e59f3-140">Basic256</span></span>|<span data-ttu-id="e59f3-141">Verwendet Aes256-Verschlüsselung, Sha1 für den Nachrichtenhash und Rsa-oaep-mgf1p für Key Wrap.</span><span class="sxs-lookup"><span data-stu-id="e59f3-141">Use Aes256 encryption, Sha1 for message digest, Rsa-oaep-mgf1p for key wrap.</span></span>|  
|<span data-ttu-id="e59f3-142">Basic256Rsa15</span><span class="sxs-lookup"><span data-stu-id="e59f3-142">Basic256Rsa15</span></span>|<span data-ttu-id="e59f3-143">Verwendet Aes256-Nachrichtenverschlüsselung, Sha1 für den Nachrichtenhash und Rsa15 für Key Wrap.</span><span class="sxs-lookup"><span data-stu-id="e59f3-143">Use Aes256 for message encryption, Sha1 for message digest and Rsa15 for key wrap.</span></span>|  
|<span data-ttu-id="e59f3-144">Basic192Rsa15</span><span class="sxs-lookup"><span data-stu-id="e59f3-144">Basic192Rsa15</span></span>|<span data-ttu-id="e59f3-145">Verwendet Aes192 für die Nachrichtenverschlüsselung, Sha1 für den Nachrichtenhash und Rsa15 für Key Wrap.</span><span class="sxs-lookup"><span data-stu-id="e59f3-145">Use Aes192 for message encryption, Sha1 for message digest and Rsa15 for key wrap.</span></span>|  
|<span data-ttu-id="e59f3-146">TripleDes</span><span class="sxs-lookup"><span data-stu-id="e59f3-146">TripleDes</span></span>|<span data-ttu-id="e59f3-147">Verwendet TripleDes-Verschlüsselung, Sha1 für den Nachrichtenhash und Rsa-oaep-mgf1p für Key Wrap.</span><span class="sxs-lookup"><span data-stu-id="e59f3-147">Use TripleDes encryption, Sha1 for message digest, Rsa-oaep-mgf1p for key wrap.</span></span>|  
|<span data-ttu-id="e59f3-148">Basic128Rsa15</span><span class="sxs-lookup"><span data-stu-id="e59f3-148">Basic128Rsa15</span></span>|<span data-ttu-id="e59f3-149">Verwendet Aes128 für die Nachrichtenverschlüsselung, Sha1 für den Nachrichtenhash und Rsa15 für Key Wrap.</span><span class="sxs-lookup"><span data-stu-id="e59f3-149">Use Aes128 for message encryption, Sha1 for message digest and Rsa15 for key wrap.</span></span>|  
|<span data-ttu-id="e59f3-150">TripleDesRsa15</span><span class="sxs-lookup"><span data-stu-id="e59f3-150">TripleDesRsa15</span></span>|<span data-ttu-id="e59f3-151">Verwendet TripleDes-Verschlüsselung, Sha1 für den Nachrichtenhash und Rsa15 für Key Wrap.</span><span class="sxs-lookup"><span data-stu-id="e59f3-151">Use TripleDes encryption, Sha1 for message digest and Rsa15 for key wrap.</span></span>|  
|<span data-ttu-id="e59f3-152">Basic128Sha256</span><span class="sxs-lookup"><span data-stu-id="e59f3-152">Basic128Sha256</span></span>|<span data-ttu-id="e59f3-153">Verwendet Aes256-Nachrichtenverschlüsselung, Sha256 für den Nachrichtenhash und Rsa-oaep-mgf1p für Key Wrap.</span><span class="sxs-lookup"><span data-stu-id="e59f3-153">Use Aes256 for message encryption, Sha256 for message digest and Rsa-oaep-mgf1p for key wrap.</span></span>|  
|<span data-ttu-id="e59f3-154">Basic192Sha256</span><span class="sxs-lookup"><span data-stu-id="e59f3-154">Basic192Sha256</span></span>|<span data-ttu-id="e59f3-155">Verwendet Aes192 für die Nachrichtenverschlüsselung, Sha256 für den Nachrichtenhash und Rsa-oaep-mgf1p für Key Wrap.</span><span class="sxs-lookup"><span data-stu-id="e59f3-155">Use Aes192 for message encryption, Sha256 for message digest and Rsa-oaep-mgf1p for key wrap.</span></span>|  
|<span data-ttu-id="e59f3-156">Basic256Sha256</span><span class="sxs-lookup"><span data-stu-id="e59f3-156">Basic256Sha256</span></span>|<span data-ttu-id="e59f3-157">Verwendet Aes256-Nachrichtenverschlüsselung, Sha256 für den Nachrichtenhash und Rsa-oaep-mgf1p für Key Wrap.</span><span class="sxs-lookup"><span data-stu-id="e59f3-157">Use Aes256 for message encryption, Sha256 for message digest and Rsa-oaep-mgf1p for key wrap.</span></span>|  
|<span data-ttu-id="e59f3-158">TripleDesSha256</span><span class="sxs-lookup"><span data-stu-id="e59f3-158">TripleDesSha256</span></span>|<span data-ttu-id="e59f3-159">Verwendet TripleDes für die Nachrichtenverschlüsselung, Sha256 für den Nachrichtenhash und Rsa-oaep-mgf1p für Key Wrap.</span><span class="sxs-lookup"><span data-stu-id="e59f3-159">Use TripleDes for message encryption, Sha256 for message digest and Rsa-oaep-mgf1p for key wrap.</span></span>|  
|<span data-ttu-id="e59f3-160">Basic128Sha256Rsa15</span><span class="sxs-lookup"><span data-stu-id="e59f3-160">Basic128Sha256Rsa15</span></span>|<span data-ttu-id="e59f3-161">Verwendet Aes128 für die Nachrichtenverschlüsselung, Sha256 für den Nachrichtenhash und Rsa15 für Key Wrap.</span><span class="sxs-lookup"><span data-stu-id="e59f3-161">Use Aes128 for message encryption, Sha256 for message digest and Rsa15 for key wrap.</span></span>|  
|<span data-ttu-id="e59f3-162">Basic192Sha256Rsa15</span><span class="sxs-lookup"><span data-stu-id="e59f3-162">Basic192Sha256Rsa15</span></span>|<span data-ttu-id="e59f3-163">Verwendet Aes192 für die Nachrichtenverschlüsselung, Sha256 für den Nachrichtenhash und Rsa15 für Key Wrap.</span><span class="sxs-lookup"><span data-stu-id="e59f3-163">Use Aes192 for message encryption, Sha256 for message digest and Rsa15 for key wrap.</span></span>|  
|<span data-ttu-id="e59f3-164">Basic256Sha256Rsa15</span><span class="sxs-lookup"><span data-stu-id="e59f3-164">Basic256Sha256Rsa15</span></span>|<span data-ttu-id="e59f3-165">Verwendet Aes256 für die Nachrichtenverschlüsselung, Sha256 für den Nachrichtenhash und Rsa15 für Key Wrap.</span><span class="sxs-lookup"><span data-stu-id="e59f3-165">Use Aes256 for message encryption, Sha256 for message digest and Rsa15 for key wrap.</span></span>|  
|<span data-ttu-id="e59f3-166">TripleDesSha256Rsa15</span><span class="sxs-lookup"><span data-stu-id="e59f3-166">TripleDesSha256Rsa15</span></span>|<span data-ttu-id="e59f3-167">Verwendet TripleDes für die Nachrichtenverschlüsselung, Sha256 für den Nachrichtenhash und Rsa15 für Key Wrap.</span><span class="sxs-lookup"><span data-stu-id="e59f3-167">Use TripleDes for message encryption, Sha256 for message digest and Rsa15 for key wrap.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="e59f3-168">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="e59f3-168">Child Elements</span></span>  
  
|<span data-ttu-id="e59f3-169">Element</span><span class="sxs-lookup"><span data-stu-id="e59f3-169">Element</span></span>|<span data-ttu-id="e59f3-170">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="e59f3-170">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="e59f3-171">\<claimTypeRequirements></span><span class="sxs-lookup"><span data-stu-id="e59f3-171">\<claimTypeRequirements></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/claimtyperequirements-element.md)|<span data-ttu-id="e59f3-172">Gibt eine Auflistung von Anspruchstypen für diese Bindung an.</span><span class="sxs-lookup"><span data-stu-id="e59f3-172">Specifies a collection of claim types for this binding.</span></span> <span data-ttu-id="e59f3-173">Jedes Element ist vom Typ <xref:System.ServiceModel.Configuration.ClaimTypeElement>.</span><span class="sxs-lookup"><span data-stu-id="e59f3-173">Each element is of type <xref:System.ServiceModel.Configuration.ClaimTypeElement>.</span></span>|  
|[<span data-ttu-id="e59f3-174">\<issuer></span><span class="sxs-lookup"><span data-stu-id="e59f3-174">\<issuer></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/issuer.md)|<span data-ttu-id="e59f3-175">Gibt einen Endpunkt an, der ein Sicherheitstoken ausstellt.</span><span class="sxs-lookup"><span data-stu-id="e59f3-175">Specifies an endpoint that issues a security token.</span></span> <span data-ttu-id="e59f3-176">Dieses Element ist vom Typ <xref:System.ServiceModel.Configuration.IssuedTokenParametersEndpointAddressElement>.</span><span class="sxs-lookup"><span data-stu-id="e59f3-176">This element is of type <xref:System.ServiceModel.Configuration.IssuedTokenParametersEndpointAddressElement>.</span></span>|  
|[<span data-ttu-id="e59f3-177">\<issuerMetadata></span><span class="sxs-lookup"><span data-stu-id="e59f3-177">\<issuerMetadata></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/issuermetadata.md)|<span data-ttu-id="e59f3-178">Gibt die Endpunktadresse des Ausstellers an.</span><span class="sxs-lookup"><span data-stu-id="e59f3-178">Specifies the endpoint address of the issuer.</span></span>|  
|[<span data-ttu-id="e59f3-179">\<tokenRequestParameters></span><span class="sxs-lookup"><span data-stu-id="e59f3-179">\<tokenRequestParameters></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/tokenrequestparameters.md)|<span data-ttu-id="e59f3-180">Eine Auflistung von Tokenanforderungsparametern.</span><span class="sxs-lookup"><span data-stu-id="e59f3-180">A collection of token request parameters.</span></span> <span data-ttu-id="e59f3-181">Jeder Parameter ist ein XML-Element.</span><span class="sxs-lookup"><span data-stu-id="e59f3-181">Each parameter is an XML element.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="e59f3-182">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="e59f3-182">Parent Elements</span></span>  
  
|<span data-ttu-id="e59f3-183">Element</span><span class="sxs-lookup"><span data-stu-id="e59f3-183">Element</span></span>|<span data-ttu-id="e59f3-184">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="e59f3-184">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="e59f3-185">\<security></span><span class="sxs-lookup"><span data-stu-id="e59f3-185">\<security></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/security-element-of-ws2007federationhttpbinding.md)|<span data-ttu-id="e59f3-186">Definiert die Sicherheitseinstellungen für eine Bindung.</span><span class="sxs-lookup"><span data-stu-id="e59f3-186">Defines the security settings for a binding.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="e59f3-187">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e59f3-187">See also</span></span>
- <xref:System.ServiceModel.FederatedMessageSecurityOverHttp>
- <xref:System.ServiceModel.Configuration.WSFederationHttpSecurityElement.Message%2A>
- <xref:System.ServiceModel.WSFederationHttpSecurity.Message%2A>
 `System.ServiceModel.Configuration.FederatedMessageSecurityElement` 
- [<span data-ttu-id="e59f3-188">Sichern von Diensten und Clients</span><span class="sxs-lookup"><span data-stu-id="e59f3-188">Securing Services and Clients</span></span>](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="e59f3-189">Bindungen</span><span class="sxs-lookup"><span data-stu-id="e59f3-189">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)
- [<span data-ttu-id="e59f3-190">Konfigurieren der vom System bereitgestellten Bindungen</span><span class="sxs-lookup"><span data-stu-id="e59f3-190">Configuring System-Provided Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="e59f3-191">Verwenden von Bindungen, um Dienste und Clients zu konfigurieren</span><span class="sxs-lookup"><span data-stu-id="e59f3-191">Using Bindings to Configure Services and Clients</span></span>](../../../../../docs/framework/wcf/using-bindings-to-configure-services-and-clients.md)
- [<span data-ttu-id="e59f3-192">\<binding></span><span class="sxs-lookup"><span data-stu-id="e59f3-192">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)
