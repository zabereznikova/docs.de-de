---
title: '&lt;message&gt;-Element von &lt;wsFederationHttpBinding&gt;'
ms.date: 03/30/2017
ms.assetid: 9d710389-d9d8-4454-9bf2-da4ccda31cec
ms.openlocfilehash: 9614d973319e962655fd5e9c76f8703dab85c009
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54740826"
---
# <a name="ltmessagegt-element-of-ltwsfederationhttpbindinggt"></a><span data-ttu-id="ef23d-102">&lt;message&gt;-Element von &lt;wsFederationHttpBinding&gt;</span><span class="sxs-lookup"><span data-stu-id="ef23d-102">&lt;message&gt; element of &lt;wsFederationHttpBinding&gt;</span></span>
<span data-ttu-id="ef23d-103">Definiert die Einstellungen für die Sicherheit auf Nachrichtenebene für die [ \<WsFederationHttpBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/wsfederationhttpbinding.md).</span><span class="sxs-lookup"><span data-stu-id="ef23d-103">Defines the settings for the message-level security for the [\<wsFederationHttpBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/wsfederationhttpbinding.md).</span></span>  
  
 <span data-ttu-id="ef23d-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="ef23d-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="ef23d-105">\<bindings></span><span class="sxs-lookup"><span data-stu-id="ef23d-105">\<bindings></span></span>  
<span data-ttu-id="ef23d-106">\<wsFederatedBinding></span><span class="sxs-lookup"><span data-stu-id="ef23d-106">\<wsFederatedBinding></span></span>  
<span data-ttu-id="ef23d-107">\<binding></span><span class="sxs-lookup"><span data-stu-id="ef23d-107">\<binding></span></span>  
<span data-ttu-id="ef23d-108">\<security></span><span class="sxs-lookup"><span data-stu-id="ef23d-108">\<security></span></span>  
<span data-ttu-id="ef23d-109">\<message></span><span class="sxs-lookup"><span data-stu-id="ef23d-109">\<message></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ef23d-110">Syntax</span><span class="sxs-lookup"><span data-stu-id="ef23d-110">Syntax</span></span>  
  
```xml  
<wsFederationBinding>
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
</wsFederationBinding>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="ef23d-111">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="ef23d-111">Attributes and Elements</span></span>  
 <span data-ttu-id="ef23d-112">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="ef23d-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="ef23d-113">Attribute</span><span class="sxs-lookup"><span data-stu-id="ef23d-113">Attributes</span></span>  
  
|<span data-ttu-id="ef23d-114">Attribut</span><span class="sxs-lookup"><span data-stu-id="ef23d-114">Attribute</span></span>|<span data-ttu-id="ef23d-115">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="ef23d-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="ef23d-116">algorithmSuite</span><span class="sxs-lookup"><span data-stu-id="ef23d-116">algorithmSuite</span></span>|<span data-ttu-id="ef23d-117">Legt die Nachrichtenverschlüsselungs- und Key Wrap-Algorithmen fest.</span><span class="sxs-lookup"><span data-stu-id="ef23d-117">Sets the message encryption and key-wrap algorithms.</span></span> <span data-ttu-id="ef23d-118">In der Tabelle "algorithmSuite-Attribut" sind die für dieses Attribut gültigen Werte zusammengestellt.</span><span class="sxs-lookup"><span data-stu-id="ef23d-118">See the "algorithmSuite attribute" table for valid values of this attribute.</span></span> <span data-ttu-id="ef23d-119">Der Standardwert ist `Basic256`.</span><span class="sxs-lookup"><span data-stu-id="ef23d-119">The default value is `Basic256`.</span></span><br /><br /> <span data-ttu-id="ef23d-120">Dieses Attribut ist vom Typ <xref:System.ServiceModel.Security.SecurityAlgorithmSuite>.</span><span class="sxs-lookup"><span data-stu-id="ef23d-120">This attribute is of type <xref:System.ServiceModel.Security.SecurityAlgorithmSuite>.</span></span> <span data-ttu-id="ef23d-121">Diese Algorithmen entsprechen den in der Security Policy Language (WS-SecurityPolicy)-Spezifikation angegebenen Algorithmen.</span><span class="sxs-lookup"><span data-stu-id="ef23d-121">These algorithms map to those specified in the Security Policy Language (WS-SecurityPolicy) specification.</span></span>|  
|<span data-ttu-id="ef23d-122">issuedKeyType</span><span class="sxs-lookup"><span data-stu-id="ef23d-122">issuedKeyType</span></span>|<span data-ttu-id="ef23d-123">Gibt den Typ des auszustellenden Schlüssels an.</span><span class="sxs-lookup"><span data-stu-id="ef23d-123">Specifies the type of key to be issued.</span></span> <span data-ttu-id="ef23d-124">Folgende Werte sind gültig:</span><span class="sxs-lookup"><span data-stu-id="ef23d-124">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="ef23d-125">-"SymmetricKey"</span><span class="sxs-lookup"><span data-stu-id="ef23d-125">-   SymmetricKey</span></span><br /><span data-ttu-id="ef23d-126">: Öffentlicher Schlüssel</span><span class="sxs-lookup"><span data-stu-id="ef23d-126">-   PublicKey</span></span><br /><br /> <span data-ttu-id="ef23d-127">Die Standardeinstellung ist `SymmetricKey`.</span><span class="sxs-lookup"><span data-stu-id="ef23d-127">The default is `SymmetricKey`.</span></span> <span data-ttu-id="ef23d-128">Dieses Attribut ist vom Typ <xref:System.IdentityModel.Tokens.SecurityKeyType>.</span><span class="sxs-lookup"><span data-stu-id="ef23d-128">This attribute is of type <xref:System.IdentityModel.Tokens.SecurityKeyType>.</span></span>|  
|<span data-ttu-id="ef23d-129">issuedTokenType</span><span class="sxs-lookup"><span data-stu-id="ef23d-129">issuedTokenType</span></span>|<span data-ttu-id="ef23d-130">Eine Zeichenfolge mit einem URI, die den Typ des auszustellenden Tokens angibt.</span><span class="sxs-lookup"><span data-stu-id="ef23d-130">A string that contains a URI that specifies the type of token to be issued.</span></span> <span data-ttu-id="ef23d-131">Die Standardeinstellung ist `null`.</span><span class="sxs-lookup"><span data-stu-id="ef23d-131">The default is `null`.</span></span>|  
|<span data-ttu-id="ef23d-132">negotiateServiceCredential</span><span class="sxs-lookup"><span data-stu-id="ef23d-132">negotiateServiceCredential</span></span>|<span data-ttu-id="ef23d-133">Ein boolescher Wert, der angibt, ob die Dienstanmeldeinformationen als Teil der Aushandlung ausgetauscht werden sollen oder ob sie out-of-band zur Verfügung stehen.</span><span class="sxs-lookup"><span data-stu-id="ef23d-133">A Boolean value that specifies whether the service credential should be exchanged as part of negotiation or is available out of band.</span></span> <span data-ttu-id="ef23d-134">Der Standardwert ist `true`, was bedeutet, dass die Dienstanmeldeinformationen ausgehandelt werden.</span><span class="sxs-lookup"><span data-stu-id="ef23d-134">The default is `true`, which means that the service credential is negotiated.</span></span>|  
  
## <a name="algorithmsuite-attribute"></a><span data-ttu-id="ef23d-135">algorithmSuite-Attribut</span><span class="sxs-lookup"><span data-stu-id="ef23d-135">algorithmSuite Attribute</span></span>  
  
|<span data-ttu-id="ef23d-136">Wert</span><span class="sxs-lookup"><span data-stu-id="ef23d-136">Value</span></span>|<span data-ttu-id="ef23d-137">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="ef23d-137">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="ef23d-138">Basic128</span><span class="sxs-lookup"><span data-stu-id="ef23d-138">Basic128</span></span>|<span data-ttu-id="ef23d-139">Verwendet Basic128-Verschlüsselung, Sha1 für den Nachrichtenhash und Rsa-oaep-mgf1p für Key Wrap.</span><span class="sxs-lookup"><span data-stu-id="ef23d-139">Use Basic128 encryption, Sha1 for message digest, and Rsa-oaep-mgf1p for key wrap.</span></span>|  
|<span data-ttu-id="ef23d-140">Basic192</span><span class="sxs-lookup"><span data-stu-id="ef23d-140">Basic192</span></span>|<span data-ttu-id="ef23d-141">Verwendet Basic192-Verschlüsselung, Sha1 für den Nachrichtenhash und Rsa-oaep-mgf1p für Key Wrap.</span><span class="sxs-lookup"><span data-stu-id="ef23d-141">Use Basic192 encryption, Sha1 for message digest, Rsa-oaep-mgf1p for key wrap.</span></span>|  
|<span data-ttu-id="ef23d-142">Basic256</span><span class="sxs-lookup"><span data-stu-id="ef23d-142">Basic256</span></span>|<span data-ttu-id="ef23d-143">Verwendet Basic256-Verschlüsselung, Sha1 für den Nachrichtenhash und Rsa-oaep-mgf1p für Key Wrap.</span><span class="sxs-lookup"><span data-stu-id="ef23d-143">Use Basic256 encryption, Sha1 for message digest, Rsa-oaep-mgf1p for key wrap.</span></span>|  
|<span data-ttu-id="ef23d-144">Basic256Rsa15</span><span class="sxs-lookup"><span data-stu-id="ef23d-144">Basic256Rsa15</span></span>|<span data-ttu-id="ef23d-145">Verwendet Basic256 für die Nachrichtenverschlüsselung, Sha1 für den Nachrichtenhash und Rsa15 für Key Wrap.</span><span class="sxs-lookup"><span data-stu-id="ef23d-145">Use Basic256 for message encryption, Sha1 for message digest and Rsa15 for key wrap.</span></span>|  
|<span data-ttu-id="ef23d-146">Basic192Rsa15</span><span class="sxs-lookup"><span data-stu-id="ef23d-146">Basic192Rsa15</span></span>|<span data-ttu-id="ef23d-147">Verwendet Basic192 für die Nachrichtenverschlüsselung, Sha1 für den Nachrichtenhash und Rsa15 für Key Wrap.</span><span class="sxs-lookup"><span data-stu-id="ef23d-147">Use Basic192 for message encryption, Sha1 for message digest and Rsa15 for key wrap.</span></span>|  
|<span data-ttu-id="ef23d-148">TripleDes</span><span class="sxs-lookup"><span data-stu-id="ef23d-148">TripleDes</span></span>|<span data-ttu-id="ef23d-149">Verwendet TripleDes-Verschlüsselung, Sha1 für den Nachrichtenhash und Rsa-oaep-mgf1p für Key Wrap.</span><span class="sxs-lookup"><span data-stu-id="ef23d-149">Use TripleDes encryption, Sha1 for message digest, Rsa-oaep-mgf1p for key wrap.</span></span>|  
|<span data-ttu-id="ef23d-150">Basic128Rsa15</span><span class="sxs-lookup"><span data-stu-id="ef23d-150">Basic128Rsa15</span></span>|<span data-ttu-id="ef23d-151">Verwendet Basic128 für die Nachrichtenverschlüsselung, Sha1 für den Nachrichtenhash und Rsa15 für Key Wrap.</span><span class="sxs-lookup"><span data-stu-id="ef23d-151">Use Basic128 for message encryption, Sha1 for message digest and Rsa15 for key wrap.</span></span>|  
|<span data-ttu-id="ef23d-152">TripleDesRsa15</span><span class="sxs-lookup"><span data-stu-id="ef23d-152">TripleDesRsa15</span></span>|<span data-ttu-id="ef23d-153">Verwendet TripleDes-Verschlüsselung, Sha1 für den Nachrichtenhash und Rsa15 für Key Wrap.</span><span class="sxs-lookup"><span data-stu-id="ef23d-153">Use TripleDes encryption, Sha1 for message digest and Rsa15 for key wrap.</span></span>|  
|<span data-ttu-id="ef23d-154">Basic128Sha256</span><span class="sxs-lookup"><span data-stu-id="ef23d-154">Basic128Sha256</span></span>|<span data-ttu-id="ef23d-155">Verwendet Basic128 für die Nachrichtenverschlüsselung, Sha256 für den Nachrichtenhash und Rsa-oaep-mgf1p für Key Wrap.</span><span class="sxs-lookup"><span data-stu-id="ef23d-155">Use Basic128 for message encryption, Sha256 for message digest and Rsa-oaep-mgf1p for key wrap.</span></span>|  
|<span data-ttu-id="ef23d-156">Basic192Sha256</span><span class="sxs-lookup"><span data-stu-id="ef23d-156">Basic192Sha256</span></span>|<span data-ttu-id="ef23d-157">Verwendet Basic192 für die Nachrichtenverschlüsselung, Sha256 für den Nachrichtenhash und Rsa-oaep-mgf1p für Key Wrap.</span><span class="sxs-lookup"><span data-stu-id="ef23d-157">Use Basic192 for message encryption, Sha256 for message digest and Rsa-oaep-mgf1p for key wrap.</span></span>|  
|<span data-ttu-id="ef23d-158">Basic256Sha256</span><span class="sxs-lookup"><span data-stu-id="ef23d-158">Basic256Sha256</span></span>|<span data-ttu-id="ef23d-159">Verwendet Basic256 für die Nachrichtenverschlüsselung, Sha256 für den Nachrichtenhash und Rsa-oaep-mgf1p für Key Wrap.</span><span class="sxs-lookup"><span data-stu-id="ef23d-159">Use Basic256 for message encryption, Sha256 for message digest and Rsa-oaep-mgf1p for key wrap.</span></span>|  
|<span data-ttu-id="ef23d-160">TripleDesSha256</span><span class="sxs-lookup"><span data-stu-id="ef23d-160">TripleDesSha256</span></span>|<span data-ttu-id="ef23d-161">Verwendet TripleDes für die Nachrichtenverschlüsselung, Sha256 für den Nachrichtenhash und Rsa-oaep-mgf1p für Key Wrap.</span><span class="sxs-lookup"><span data-stu-id="ef23d-161">Use TripleDes for message encryption, Sha256 for message digest and Rsa-oaep-mgf1p for key wrap.</span></span>|  
|<span data-ttu-id="ef23d-162">Basic128Sha256Rsa15</span><span class="sxs-lookup"><span data-stu-id="ef23d-162">Basic128Sha256Rsa15</span></span>|<span data-ttu-id="ef23d-163">Verwendet Basic128 für die Nachrichtenverschlüsselung, Sha256 für den Nachrichtenhash und Rsa15 für Key Wrap.</span><span class="sxs-lookup"><span data-stu-id="ef23d-163">Use Basic128 for message encryption, Sha256 for message digest and Rsa15 for key wrap.</span></span>|  
|<span data-ttu-id="ef23d-164">Basic192Sha256Rsa15</span><span class="sxs-lookup"><span data-stu-id="ef23d-164">Basic192Sha256Rsa15</span></span>|<span data-ttu-id="ef23d-165">Verwendet Aes192 für die Nachrichtenverschlüsselung, Sha256 für den Nachrichtenhash und Rsa15 für Key Wrap.</span><span class="sxs-lookup"><span data-stu-id="ef23d-165">Use Aes192 for message encryption, Sha256 for message digest and Rsa15 for key wrap.</span></span>|  
|<span data-ttu-id="ef23d-166">Basic256Sha256Rsa15</span><span class="sxs-lookup"><span data-stu-id="ef23d-166">Basic256Sha256Rsa15</span></span>|<span data-ttu-id="ef23d-167">Verwendet Basic256 für die Nachrichtenverschlüsselung, Sha256 für den Nachrichtenhash und Rsa15 für Key Wrap.</span><span class="sxs-lookup"><span data-stu-id="ef23d-167">Use Basic256 for message encryption, Sha256 for message digest and Rsa15 for key wrap.</span></span>|  
|<span data-ttu-id="ef23d-168">TripleDesSha256Rsa15</span><span class="sxs-lookup"><span data-stu-id="ef23d-168">TripleDesSha256Rsa15</span></span>|<span data-ttu-id="ef23d-169">Verwendet TripleDes für die Nachrichtenverschlüsselung, Sha256 für den Nachrichtenhash und Rsa15 für Key Wrap.</span><span class="sxs-lookup"><span data-stu-id="ef23d-169">Use TripleDes for message encryption, Sha256 for message digest and Rsa15 for key wrap.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="ef23d-170">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="ef23d-170">Child Elements</span></span>  
  
|<span data-ttu-id="ef23d-171">Element</span><span class="sxs-lookup"><span data-stu-id="ef23d-171">Element</span></span>|<span data-ttu-id="ef23d-172">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="ef23d-172">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="ef23d-173">\<claimTypeRequirements></span><span class="sxs-lookup"><span data-stu-id="ef23d-173">\<claimTypeRequirements></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/claimtyperequirements-element.md)|<span data-ttu-id="ef23d-174">Gibt eine Auflistung von Anspruchstypen für diese Bindung an.</span><span class="sxs-lookup"><span data-stu-id="ef23d-174">Specifies a collection of claim types for this binding.</span></span> <span data-ttu-id="ef23d-175">Jedes Element ist vom Typ <xref:System.ServiceModel.Configuration.ClaimTypeElement>.</span><span class="sxs-lookup"><span data-stu-id="ef23d-175">Each element is of type <xref:System.ServiceModel.Configuration.ClaimTypeElement>.</span></span>|  
|<span data-ttu-id="ef23d-176">issuer</span><span class="sxs-lookup"><span data-stu-id="ef23d-176">issuer</span></span>|<span data-ttu-id="ef23d-177">Gibt einen Endpunkt an, der ein Sicherheitstoken ausstellt.</span><span class="sxs-lookup"><span data-stu-id="ef23d-177">Specifies an endpoint that issues a security token.</span></span> <span data-ttu-id="ef23d-178">Dieses Element ist vom Typ <xref:System.ServiceModel.Configuration.IssuedTokenParametersEndpointAddressElement>.</span><span class="sxs-lookup"><span data-stu-id="ef23d-178">This element is of type <xref:System.ServiceModel.Configuration.IssuedTokenParametersEndpointAddressElement>.</span></span>|  
|<span data-ttu-id="ef23d-179">issuerMetadata</span><span class="sxs-lookup"><span data-stu-id="ef23d-179">issuerMetadata</span></span>|<span data-ttu-id="ef23d-180">Gibt die Endpunktadresse des Ausstellers an.</span><span class="sxs-lookup"><span data-stu-id="ef23d-180">Specifies the endpoint address of the issuer.</span></span>|  
|[<span data-ttu-id="ef23d-181">\<tokenRequestParameters></span><span class="sxs-lookup"><span data-stu-id="ef23d-181">\<tokenRequestParameters></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/tokenrequestparameters.md)|<span data-ttu-id="ef23d-182">Eine Auflistung von Tokenanforderungsparametern.</span><span class="sxs-lookup"><span data-stu-id="ef23d-182">A collection of token request parameters.</span></span> <span data-ttu-id="ef23d-183">Jeder Parameter ist ein XML-Element.</span><span class="sxs-lookup"><span data-stu-id="ef23d-183">Each parameter is an XML element.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="ef23d-184">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="ef23d-184">Parent Elements</span></span>  
  
|<span data-ttu-id="ef23d-185">Element</span><span class="sxs-lookup"><span data-stu-id="ef23d-185">Element</span></span>|<span data-ttu-id="ef23d-186">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="ef23d-186">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="ef23d-187">\<security></span><span class="sxs-lookup"><span data-stu-id="ef23d-187">\<security></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/security-of-wsfederationhttpbinding.md)|<span data-ttu-id="ef23d-188">Definiert die Sicherheitseinstellungen für eine Bindung.</span><span class="sxs-lookup"><span data-stu-id="ef23d-188">Defines the security settings for a binding.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="ef23d-189">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ef23d-189">See also</span></span>
- <xref:System.ServiceModel.FederatedMessageSecurityOverHttp>
- <xref:System.ServiceModel.Configuration.WSFederationHttpSecurityElement.Message%2A>
- <xref:System.ServiceModel.WSFederationHttpSecurity.Message%2A>
 `System.ServiceModel.Configuration.FederatedMessageSecurityElement`
- [<span data-ttu-id="ef23d-190">Sichern von Diensten und Clients</span><span class="sxs-lookup"><span data-stu-id="ef23d-190">Securing Services and Clients</span></span>](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="ef23d-191">Bindungen</span><span class="sxs-lookup"><span data-stu-id="ef23d-191">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)
- [<span data-ttu-id="ef23d-192">Konfigurieren der vom System bereitgestellten Bindungen</span><span class="sxs-lookup"><span data-stu-id="ef23d-192">Configuring System-Provided Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="ef23d-193">Verwenden von Bindungen, um Dienste und Clients zu konfigurieren</span><span class="sxs-lookup"><span data-stu-id="ef23d-193">Using Bindings to Configure Services and Clients</span></span>](../../../../../docs/framework/wcf/using-bindings-to-configure-services-and-clients.md)
- [<span data-ttu-id="ef23d-194">\<binding></span><span class="sxs-lookup"><span data-stu-id="ef23d-194">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)
