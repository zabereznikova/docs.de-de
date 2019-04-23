---
title: <message> Element <wsFederationHttpBinding>
ms.date: 03/30/2017
ms.assetid: 9d710389-d9d8-4454-9bf2-da4ccda31cec
ms.openlocfilehash: 79739dd715d7982555e5577c921cb65156af5923
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59223813"
---
# <a name="message-element-of-wsfederationhttpbinding"></a><span data-ttu-id="cac51-102">\<Message >-Element der \<WsFederationHttpBinding ></span><span class="sxs-lookup"><span data-stu-id="cac51-102">\<message> element of \<wsFederationHttpBinding></span></span>
<span data-ttu-id="cac51-103">Definiert die Einstellungen für die Sicherheit auf Nachrichtenebene für die [ \<WsFederationHttpBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/wsfederationhttpbinding.md).</span><span class="sxs-lookup"><span data-stu-id="cac51-103">Defines the settings for the message-level security for the [\<wsFederationHttpBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/wsfederationhttpbinding.md).</span></span>  
  
 <span data-ttu-id="cac51-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="cac51-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="cac51-105">\<bindings></span><span class="sxs-lookup"><span data-stu-id="cac51-105">\<bindings></span></span>  
<span data-ttu-id="cac51-106">\<wsFederatedBinding></span><span class="sxs-lookup"><span data-stu-id="cac51-106">\<wsFederatedBinding></span></span>  
<span data-ttu-id="cac51-107">\<binding></span><span class="sxs-lookup"><span data-stu-id="cac51-107">\<binding></span></span>  
<span data-ttu-id="cac51-108">\<security></span><span class="sxs-lookup"><span data-stu-id="cac51-108">\<security></span></span>  
<span data-ttu-id="cac51-109">\<message></span><span class="sxs-lookup"><span data-stu-id="cac51-109">\<message></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cac51-110">Syntax</span><span class="sxs-lookup"><span data-stu-id="cac51-110">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="cac51-111">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="cac51-111">Attributes and Elements</span></span>  
 <span data-ttu-id="cac51-112">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="cac51-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="cac51-113">Attribute</span><span class="sxs-lookup"><span data-stu-id="cac51-113">Attributes</span></span>  
  
|<span data-ttu-id="cac51-114">Attribut</span><span class="sxs-lookup"><span data-stu-id="cac51-114">Attribute</span></span>|<span data-ttu-id="cac51-115">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="cac51-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="cac51-116">algorithmSuite</span><span class="sxs-lookup"><span data-stu-id="cac51-116">algorithmSuite</span></span>|<span data-ttu-id="cac51-117">Legt die Nachrichtenverschlüsselungs- und Key Wrap-Algorithmen fest.</span><span class="sxs-lookup"><span data-stu-id="cac51-117">Sets the message encryption and key-wrap algorithms.</span></span> <span data-ttu-id="cac51-118">In der Tabelle "algorithmSuite-Attribut" sind die für dieses Attribut gültigen Werte zusammengestellt.</span><span class="sxs-lookup"><span data-stu-id="cac51-118">See the "algorithmSuite attribute" table for valid values of this attribute.</span></span> <span data-ttu-id="cac51-119">Der Standardwert ist `Basic256`.</span><span class="sxs-lookup"><span data-stu-id="cac51-119">The default value is `Basic256`.</span></span><br /><br /> <span data-ttu-id="cac51-120">Dieses Attribut ist vom Typ <xref:System.ServiceModel.Security.SecurityAlgorithmSuite>.</span><span class="sxs-lookup"><span data-stu-id="cac51-120">This attribute is of type <xref:System.ServiceModel.Security.SecurityAlgorithmSuite>.</span></span> <span data-ttu-id="cac51-121">Diese Algorithmen entsprechen den in der Security Policy Language (WS-SecurityPolicy)-Spezifikation angegebenen Algorithmen.</span><span class="sxs-lookup"><span data-stu-id="cac51-121">These algorithms map to those specified in the Security Policy Language (WS-SecurityPolicy) specification.</span></span>|  
|<span data-ttu-id="cac51-122">issuedKeyType</span><span class="sxs-lookup"><span data-stu-id="cac51-122">issuedKeyType</span></span>|<span data-ttu-id="cac51-123">Gibt den Typ des auszustellenden Schlüssels an.</span><span class="sxs-lookup"><span data-stu-id="cac51-123">Specifies the type of key to be issued.</span></span> <span data-ttu-id="cac51-124">Folgende Werte sind gültig:</span><span class="sxs-lookup"><span data-stu-id="cac51-124">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="cac51-125">-"SymmetricKey"</span><span class="sxs-lookup"><span data-stu-id="cac51-125">-   SymmetricKey</span></span><br /><span data-ttu-id="cac51-126">: Öffentlicher Schlüssel</span><span class="sxs-lookup"><span data-stu-id="cac51-126">-   PublicKey</span></span><br /><br /> <span data-ttu-id="cac51-127">Die Standardeinstellung ist `SymmetricKey`.</span><span class="sxs-lookup"><span data-stu-id="cac51-127">The default is `SymmetricKey`.</span></span> <span data-ttu-id="cac51-128">Dieses Attribut ist vom Typ <xref:System.IdentityModel.Tokens.SecurityKeyType>.</span><span class="sxs-lookup"><span data-stu-id="cac51-128">This attribute is of type <xref:System.IdentityModel.Tokens.SecurityKeyType>.</span></span>|  
|<span data-ttu-id="cac51-129">issuedTokenType</span><span class="sxs-lookup"><span data-stu-id="cac51-129">issuedTokenType</span></span>|<span data-ttu-id="cac51-130">Eine Zeichenfolge mit einem URI, die den Typ des auszustellenden Tokens angibt.</span><span class="sxs-lookup"><span data-stu-id="cac51-130">A string that contains a URI that specifies the type of token to be issued.</span></span> <span data-ttu-id="cac51-131">Die Standardeinstellung ist `null`.</span><span class="sxs-lookup"><span data-stu-id="cac51-131">The default is `null`.</span></span>|  
|<span data-ttu-id="cac51-132">negotiateServiceCredential</span><span class="sxs-lookup"><span data-stu-id="cac51-132">negotiateServiceCredential</span></span>|<span data-ttu-id="cac51-133">Ein boolescher Wert, der angibt, ob die Dienstanmeldeinformationen als Teil der Aushandlung ausgetauscht werden sollen oder ob sie out-of-band zur Verfügung stehen.</span><span class="sxs-lookup"><span data-stu-id="cac51-133">A Boolean value that specifies whether the service credential should be exchanged as part of negotiation or is available out of band.</span></span> <span data-ttu-id="cac51-134">Der Standardwert ist `true`, was bedeutet, dass die Dienstanmeldeinformationen ausgehandelt werden.</span><span class="sxs-lookup"><span data-stu-id="cac51-134">The default is `true`, which means that the service credential is negotiated.</span></span>|  
  
## <a name="algorithmsuite-attribute"></a><span data-ttu-id="cac51-135">algorithmSuite-Attribut</span><span class="sxs-lookup"><span data-stu-id="cac51-135">algorithmSuite Attribute</span></span>  
  
|<span data-ttu-id="cac51-136">Wert</span><span class="sxs-lookup"><span data-stu-id="cac51-136">Value</span></span>|<span data-ttu-id="cac51-137">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="cac51-137">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="cac51-138">Basic128</span><span class="sxs-lookup"><span data-stu-id="cac51-138">Basic128</span></span>|<span data-ttu-id="cac51-139">Verwendet Basic128-Verschlüsselung, Sha1 für den Nachrichtenhash und Rsa-oaep-mgf1p für Key Wrap.</span><span class="sxs-lookup"><span data-stu-id="cac51-139">Use Basic128 encryption, Sha1 for message digest, and Rsa-oaep-mgf1p for key wrap.</span></span>|  
|<span data-ttu-id="cac51-140">Basic192</span><span class="sxs-lookup"><span data-stu-id="cac51-140">Basic192</span></span>|<span data-ttu-id="cac51-141">Verwendet Basic192-Verschlüsselung, Sha1 für den Nachrichtenhash und Rsa-oaep-mgf1p für Key Wrap.</span><span class="sxs-lookup"><span data-stu-id="cac51-141">Use Basic192 encryption, Sha1 for message digest, Rsa-oaep-mgf1p for key wrap.</span></span>|  
|<span data-ttu-id="cac51-142">Basic256</span><span class="sxs-lookup"><span data-stu-id="cac51-142">Basic256</span></span>|<span data-ttu-id="cac51-143">Verwendet Basic256-Verschlüsselung, Sha1 für den Nachrichtenhash und Rsa-oaep-mgf1p für Key Wrap.</span><span class="sxs-lookup"><span data-stu-id="cac51-143">Use Basic256 encryption, Sha1 for message digest, Rsa-oaep-mgf1p for key wrap.</span></span>|  
|<span data-ttu-id="cac51-144">Basic256Rsa15</span><span class="sxs-lookup"><span data-stu-id="cac51-144">Basic256Rsa15</span></span>|<span data-ttu-id="cac51-145">Verwendet Basic256 für die Nachrichtenverschlüsselung, Sha1 für den Nachrichtenhash und Rsa15 für Key Wrap.</span><span class="sxs-lookup"><span data-stu-id="cac51-145">Use Basic256 for message encryption, Sha1 for message digest and Rsa15 for key wrap.</span></span>|  
|<span data-ttu-id="cac51-146">Basic192Rsa15</span><span class="sxs-lookup"><span data-stu-id="cac51-146">Basic192Rsa15</span></span>|<span data-ttu-id="cac51-147">Verwendet Basic192 für die Nachrichtenverschlüsselung, Sha1 für den Nachrichtenhash und Rsa15 für Key Wrap.</span><span class="sxs-lookup"><span data-stu-id="cac51-147">Use Basic192 for message encryption, Sha1 for message digest and Rsa15 for key wrap.</span></span>|  
|<span data-ttu-id="cac51-148">TripleDes</span><span class="sxs-lookup"><span data-stu-id="cac51-148">TripleDes</span></span>|<span data-ttu-id="cac51-149">Verwendet TripleDes-Verschlüsselung, Sha1 für den Nachrichtenhash und Rsa-oaep-mgf1p für Key Wrap.</span><span class="sxs-lookup"><span data-stu-id="cac51-149">Use TripleDes encryption, Sha1 for message digest, Rsa-oaep-mgf1p for key wrap.</span></span>|  
|<span data-ttu-id="cac51-150">Basic128Rsa15</span><span class="sxs-lookup"><span data-stu-id="cac51-150">Basic128Rsa15</span></span>|<span data-ttu-id="cac51-151">Verwendet Basic128 für die Nachrichtenverschlüsselung, Sha1 für den Nachrichtenhash und Rsa15 für Key Wrap.</span><span class="sxs-lookup"><span data-stu-id="cac51-151">Use Basic128 for message encryption, Sha1 for message digest and Rsa15 for key wrap.</span></span>|  
|<span data-ttu-id="cac51-152">TripleDesRsa15</span><span class="sxs-lookup"><span data-stu-id="cac51-152">TripleDesRsa15</span></span>|<span data-ttu-id="cac51-153">Verwendet TripleDes-Verschlüsselung, Sha1 für den Nachrichtenhash und Rsa15 für Key Wrap.</span><span class="sxs-lookup"><span data-stu-id="cac51-153">Use TripleDes encryption, Sha1 for message digest and Rsa15 for key wrap.</span></span>|  
|<span data-ttu-id="cac51-154">Basic128Sha256</span><span class="sxs-lookup"><span data-stu-id="cac51-154">Basic128Sha256</span></span>|<span data-ttu-id="cac51-155">Verwendet Basic128 für die Nachrichtenverschlüsselung, Sha256 für den Nachrichtenhash und Rsa-oaep-mgf1p für Key Wrap.</span><span class="sxs-lookup"><span data-stu-id="cac51-155">Use Basic128 for message encryption, Sha256 for message digest and Rsa-oaep-mgf1p for key wrap.</span></span>|  
|<span data-ttu-id="cac51-156">Basic192Sha256</span><span class="sxs-lookup"><span data-stu-id="cac51-156">Basic192Sha256</span></span>|<span data-ttu-id="cac51-157">Verwendet Basic192 für die Nachrichtenverschlüsselung, Sha256 für den Nachrichtenhash und Rsa-oaep-mgf1p für Key Wrap.</span><span class="sxs-lookup"><span data-stu-id="cac51-157">Use Basic192 for message encryption, Sha256 for message digest and Rsa-oaep-mgf1p for key wrap.</span></span>|  
|<span data-ttu-id="cac51-158">Basic256Sha256</span><span class="sxs-lookup"><span data-stu-id="cac51-158">Basic256Sha256</span></span>|<span data-ttu-id="cac51-159">Verwendet Basic256 für die Nachrichtenverschlüsselung, Sha256 für den Nachrichtenhash und Rsa-oaep-mgf1p für Key Wrap.</span><span class="sxs-lookup"><span data-stu-id="cac51-159">Use Basic256 for message encryption, Sha256 for message digest and Rsa-oaep-mgf1p for key wrap.</span></span>|  
|<span data-ttu-id="cac51-160">TripleDesSha256</span><span class="sxs-lookup"><span data-stu-id="cac51-160">TripleDesSha256</span></span>|<span data-ttu-id="cac51-161">Verwendet TripleDes für die Nachrichtenverschlüsselung, Sha256 für den Nachrichtenhash und Rsa-oaep-mgf1p für Key Wrap.</span><span class="sxs-lookup"><span data-stu-id="cac51-161">Use TripleDes for message encryption, Sha256 for message digest and Rsa-oaep-mgf1p for key wrap.</span></span>|  
|<span data-ttu-id="cac51-162">Basic128Sha256Rsa15</span><span class="sxs-lookup"><span data-stu-id="cac51-162">Basic128Sha256Rsa15</span></span>|<span data-ttu-id="cac51-163">Verwendet Basic128 für die Nachrichtenverschlüsselung, Sha256 für den Nachrichtenhash und Rsa15 für Key Wrap.</span><span class="sxs-lookup"><span data-stu-id="cac51-163">Use Basic128 for message encryption, Sha256 for message digest and Rsa15 for key wrap.</span></span>|  
|<span data-ttu-id="cac51-164">Basic192Sha256Rsa15</span><span class="sxs-lookup"><span data-stu-id="cac51-164">Basic192Sha256Rsa15</span></span>|<span data-ttu-id="cac51-165">Verwendet Aes192 für die Nachrichtenverschlüsselung, Sha256 für den Nachrichtenhash und Rsa15 für Key Wrap.</span><span class="sxs-lookup"><span data-stu-id="cac51-165">Use Aes192 for message encryption, Sha256 for message digest and Rsa15 for key wrap.</span></span>|  
|<span data-ttu-id="cac51-166">Basic256Sha256Rsa15</span><span class="sxs-lookup"><span data-stu-id="cac51-166">Basic256Sha256Rsa15</span></span>|<span data-ttu-id="cac51-167">Verwendet Basic256 für die Nachrichtenverschlüsselung, Sha256 für den Nachrichtenhash und Rsa15 für Key Wrap.</span><span class="sxs-lookup"><span data-stu-id="cac51-167">Use Basic256 for message encryption, Sha256 for message digest and Rsa15 for key wrap.</span></span>|  
|<span data-ttu-id="cac51-168">TripleDesSha256Rsa15</span><span class="sxs-lookup"><span data-stu-id="cac51-168">TripleDesSha256Rsa15</span></span>|<span data-ttu-id="cac51-169">Verwendet TripleDes für die Nachrichtenverschlüsselung, Sha256 für den Nachrichtenhash und Rsa15 für Key Wrap.</span><span class="sxs-lookup"><span data-stu-id="cac51-169">Use TripleDes for message encryption, Sha256 for message digest and Rsa15 for key wrap.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="cac51-170">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="cac51-170">Child Elements</span></span>  
  
|<span data-ttu-id="cac51-171">Element</span><span class="sxs-lookup"><span data-stu-id="cac51-171">Element</span></span>|<span data-ttu-id="cac51-172">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="cac51-172">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="cac51-173">\<claimTypeRequirements></span><span class="sxs-lookup"><span data-stu-id="cac51-173">\<claimTypeRequirements></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/claimtyperequirements-element.md)|<span data-ttu-id="cac51-174">Gibt eine Auflistung von Anspruchstypen für diese Bindung an.</span><span class="sxs-lookup"><span data-stu-id="cac51-174">Specifies a collection of claim types for this binding.</span></span> <span data-ttu-id="cac51-175">Jedes Element ist vom Typ <xref:System.ServiceModel.Configuration.ClaimTypeElement>.</span><span class="sxs-lookup"><span data-stu-id="cac51-175">Each element is of type <xref:System.ServiceModel.Configuration.ClaimTypeElement>.</span></span>|  
|<span data-ttu-id="cac51-176">issuer</span><span class="sxs-lookup"><span data-stu-id="cac51-176">issuer</span></span>|<span data-ttu-id="cac51-177">Gibt einen Endpunkt an, der ein Sicherheitstoken ausstellt.</span><span class="sxs-lookup"><span data-stu-id="cac51-177">Specifies an endpoint that issues a security token.</span></span> <span data-ttu-id="cac51-178">Dieses Element ist vom Typ <xref:System.ServiceModel.Configuration.IssuedTokenParametersEndpointAddressElement>.</span><span class="sxs-lookup"><span data-stu-id="cac51-178">This element is of type <xref:System.ServiceModel.Configuration.IssuedTokenParametersEndpointAddressElement>.</span></span>|  
|<span data-ttu-id="cac51-179">issuerMetadata</span><span class="sxs-lookup"><span data-stu-id="cac51-179">issuerMetadata</span></span>|<span data-ttu-id="cac51-180">Gibt die Endpunktadresse des Ausstellers an.</span><span class="sxs-lookup"><span data-stu-id="cac51-180">Specifies the endpoint address of the issuer.</span></span>|  
|[<span data-ttu-id="cac51-181">\<tokenRequestParameters></span><span class="sxs-lookup"><span data-stu-id="cac51-181">\<tokenRequestParameters></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/tokenrequestparameters.md)|<span data-ttu-id="cac51-182">Eine Auflistung von Tokenanforderungsparametern.</span><span class="sxs-lookup"><span data-stu-id="cac51-182">A collection of token request parameters.</span></span> <span data-ttu-id="cac51-183">Jeder Parameter ist ein XML-Element.</span><span class="sxs-lookup"><span data-stu-id="cac51-183">Each parameter is an XML element.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="cac51-184">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="cac51-184">Parent Elements</span></span>  
  
|<span data-ttu-id="cac51-185">Element</span><span class="sxs-lookup"><span data-stu-id="cac51-185">Element</span></span>|<span data-ttu-id="cac51-186">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="cac51-186">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="cac51-187">\<security></span><span class="sxs-lookup"><span data-stu-id="cac51-187">\<security></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/security-of-wsfederationhttpbinding.md)|<span data-ttu-id="cac51-188">Definiert die Sicherheitseinstellungen für eine Bindung.</span><span class="sxs-lookup"><span data-stu-id="cac51-188">Defines the security settings for a binding.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="cac51-189">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="cac51-189">See also</span></span>

- <xref:System.ServiceModel.FederatedMessageSecurityOverHttp>
- <xref:System.ServiceModel.Configuration.WSFederationHttpSecurityElement.Message%2A>
- <xref:System.ServiceModel.WSFederationHttpSecurity.Message%2A>
- <xref:System.ServiceModel.Configuration.FederatedMessageSecurityOverHttpElement>
- [<span data-ttu-id="cac51-190">Sichern von Diensten und Clients</span><span class="sxs-lookup"><span data-stu-id="cac51-190">Securing Services and Clients</span></span>](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="cac51-191">Bindungen</span><span class="sxs-lookup"><span data-stu-id="cac51-191">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)
- [<span data-ttu-id="cac51-192">Konfigurieren der vom System bereitgestellten Bindungen</span><span class="sxs-lookup"><span data-stu-id="cac51-192">Configuring System-Provided Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="cac51-193">Verwenden von Bindungen, um Dienste und Clients zu konfigurieren</span><span class="sxs-lookup"><span data-stu-id="cac51-193">Using Bindings to Configure Services and Clients</span></span>](../../../../../docs/framework/wcf/using-bindings-to-configure-services-and-clients.md)
- [<span data-ttu-id="cac51-194">\<binding></span><span class="sxs-lookup"><span data-stu-id="cac51-194">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)
