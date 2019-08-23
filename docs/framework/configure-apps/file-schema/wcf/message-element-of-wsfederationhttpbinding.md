---
title: <message>Element von<wsFederationHttpBinding>
ms.date: 03/30/2017
ms.assetid: 9d710389-d9d8-4454-9bf2-da4ccda31cec
ms.openlocfilehash: 4730d7e573eefdfcd5704621d0a7ccaa15f76d3a
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69931576"
---
# <a name="message-element-of-wsfederationhttpbinding"></a><span data-ttu-id="41b16-102">\<Message >-Element \<von WSFederationHttpBinding ></span><span class="sxs-lookup"><span data-stu-id="41b16-102">\<message> element of \<wsFederationHttpBinding></span></span>
<span data-ttu-id="41b16-103">Definiert die Einstellungen für die Sicherheit auf Nachrichten Ebene für die [ \<WSFederationHttpBinding->](wsfederationhttpbinding.md).</span><span class="sxs-lookup"><span data-stu-id="41b16-103">Defines the settings for the message-level security for the [\<wsFederationHttpBinding>](wsfederationhttpbinding.md).</span></span>  
  
 <span data-ttu-id="41b16-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="41b16-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="41b16-105">\<bindings></span><span class="sxs-lookup"><span data-stu-id="41b16-105">\<bindings></span></span>  
<span data-ttu-id="41b16-106">\<wsFederatedBinding></span><span class="sxs-lookup"><span data-stu-id="41b16-106">\<wsFederatedBinding></span></span>  
<span data-ttu-id="41b16-107">\<binding></span><span class="sxs-lookup"><span data-stu-id="41b16-107">\<binding></span></span>  
<span data-ttu-id="41b16-108">\<security></span><span class="sxs-lookup"><span data-stu-id="41b16-108">\<security></span></span>  
<span data-ttu-id="41b16-109">\<Message ></span><span class="sxs-lookup"><span data-stu-id="41b16-109">\<message></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="41b16-110">Syntax</span><span class="sxs-lookup"><span data-stu-id="41b16-110">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="41b16-111">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="41b16-111">Attributes and Elements</span></span>  
 <span data-ttu-id="41b16-112">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="41b16-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="41b16-113">Attribute</span><span class="sxs-lookup"><span data-stu-id="41b16-113">Attributes</span></span>  
  
|<span data-ttu-id="41b16-114">Attribut</span><span class="sxs-lookup"><span data-stu-id="41b16-114">Attribute</span></span>|<span data-ttu-id="41b16-115">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="41b16-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="41b16-116">algorithmSuite</span><span class="sxs-lookup"><span data-stu-id="41b16-116">algorithmSuite</span></span>|<span data-ttu-id="41b16-117">Legt die Nachrichtenverschlüsselungs- und Key Wrap-Algorithmen fest.</span><span class="sxs-lookup"><span data-stu-id="41b16-117">Sets the message encryption and key-wrap algorithms.</span></span> <span data-ttu-id="41b16-118">In der Tabelle "algorithmSuite-Attribut" sind die für dieses Attribut gültigen Werte zusammengestellt.</span><span class="sxs-lookup"><span data-stu-id="41b16-118">See the "algorithmSuite attribute" table for valid values of this attribute.</span></span> <span data-ttu-id="41b16-119">Der Standardwert ist `Basic256`.</span><span class="sxs-lookup"><span data-stu-id="41b16-119">The default value is `Basic256`.</span></span><br /><br /> <span data-ttu-id="41b16-120">Dieses Attribut ist vom Typ <xref:System.ServiceModel.Security.SecurityAlgorithmSuite>.</span><span class="sxs-lookup"><span data-stu-id="41b16-120">This attribute is of type <xref:System.ServiceModel.Security.SecurityAlgorithmSuite>.</span></span> <span data-ttu-id="41b16-121">Diese Algorithmen entsprechen den in der Security Policy Language (WS-SecurityPolicy)-Spezifikation angegebenen Algorithmen.</span><span class="sxs-lookup"><span data-stu-id="41b16-121">These algorithms map to those specified in the Security Policy Language (WS-SecurityPolicy) specification.</span></span>|  
|<span data-ttu-id="41b16-122">issuedKeyType</span><span class="sxs-lookup"><span data-stu-id="41b16-122">issuedKeyType</span></span>|<span data-ttu-id="41b16-123">Gibt den Typ des auszustellenden Schlüssels an.</span><span class="sxs-lookup"><span data-stu-id="41b16-123">Specifies the type of key to be issued.</span></span> <span data-ttu-id="41b16-124">Folgende Werte sind gültig:</span><span class="sxs-lookup"><span data-stu-id="41b16-124">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="41b16-125">-SymmetricKey</span><span class="sxs-lookup"><span data-stu-id="41b16-125">-   SymmetricKey</span></span><br /><span data-ttu-id="41b16-126">-PublicKey</span><span class="sxs-lookup"><span data-stu-id="41b16-126">-   PublicKey</span></span><br /><br /> <span data-ttu-id="41b16-127">Die Standardeinstellung ist `SymmetricKey`.</span><span class="sxs-lookup"><span data-stu-id="41b16-127">The default is `SymmetricKey`.</span></span> <span data-ttu-id="41b16-128">Dieses Attribut ist vom Typ <xref:System.IdentityModel.Tokens.SecurityKeyType>.</span><span class="sxs-lookup"><span data-stu-id="41b16-128">This attribute is of type <xref:System.IdentityModel.Tokens.SecurityKeyType>.</span></span>|  
|<span data-ttu-id="41b16-129">issuedTokenType</span><span class="sxs-lookup"><span data-stu-id="41b16-129">issuedTokenType</span></span>|<span data-ttu-id="41b16-130">Eine Zeichenfolge mit einem URI, die den Typ des auszustellenden Tokens angibt.</span><span class="sxs-lookup"><span data-stu-id="41b16-130">A string that contains a URI that specifies the type of token to be issued.</span></span> <span data-ttu-id="41b16-131">Die Standardeinstellung ist `null`.</span><span class="sxs-lookup"><span data-stu-id="41b16-131">The default is `null`.</span></span>|  
|<span data-ttu-id="41b16-132">negotiateServiceCredential</span><span class="sxs-lookup"><span data-stu-id="41b16-132">negotiateServiceCredential</span></span>|<span data-ttu-id="41b16-133">Ein boolescher Wert, der angibt, ob die Dienstanmeldeinformationen als Teil der Aushandlung ausgetauscht werden sollen oder ob sie out-of-band zur Verfügung stehen.</span><span class="sxs-lookup"><span data-stu-id="41b16-133">A Boolean value that specifies whether the service credential should be exchanged as part of negotiation or is available out of band.</span></span> <span data-ttu-id="41b16-134">Der Standardwert ist `true`, was bedeutet, dass die Dienstanmeldeinformationen ausgehandelt werden.</span><span class="sxs-lookup"><span data-stu-id="41b16-134">The default is `true`, which means that the service credential is negotiated.</span></span>|  
  
## <a name="algorithmsuite-attribute"></a><span data-ttu-id="41b16-135">algorithmSuite-Attribut</span><span class="sxs-lookup"><span data-stu-id="41b16-135">algorithmSuite Attribute</span></span>  
  
|<span data-ttu-id="41b16-136">Wert</span><span class="sxs-lookup"><span data-stu-id="41b16-136">Value</span></span>|<span data-ttu-id="41b16-137">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="41b16-137">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="41b16-138">Basic128</span><span class="sxs-lookup"><span data-stu-id="41b16-138">Basic128</span></span>|<span data-ttu-id="41b16-139">Verwendet Basic128-Verschlüsselung, Sha1 für den Nachrichtenhash und Rsa-oaep-mgf1p für Key Wrap.</span><span class="sxs-lookup"><span data-stu-id="41b16-139">Use Basic128 encryption, Sha1 for message digest, and Rsa-oaep-mgf1p for key wrap.</span></span>|  
|<span data-ttu-id="41b16-140">Basic192</span><span class="sxs-lookup"><span data-stu-id="41b16-140">Basic192</span></span>|<span data-ttu-id="41b16-141">Verwendet Basic192-Verschlüsselung, Sha1 für den Nachrichtenhash und Rsa-oaep-mgf1p für Key Wrap.</span><span class="sxs-lookup"><span data-stu-id="41b16-141">Use Basic192 encryption, Sha1 for message digest, Rsa-oaep-mgf1p for key wrap.</span></span>|  
|<span data-ttu-id="41b16-142">Basic256</span><span class="sxs-lookup"><span data-stu-id="41b16-142">Basic256</span></span>|<span data-ttu-id="41b16-143">Verwendet Basic256-Verschlüsselung, Sha1 für den Nachrichtenhash und Rsa-oaep-mgf1p für Key Wrap.</span><span class="sxs-lookup"><span data-stu-id="41b16-143">Use Basic256 encryption, Sha1 for message digest, Rsa-oaep-mgf1p for key wrap.</span></span>|  
|<span data-ttu-id="41b16-144">Basic256Rsa15</span><span class="sxs-lookup"><span data-stu-id="41b16-144">Basic256Rsa15</span></span>|<span data-ttu-id="41b16-145">Verwendet Basic256 für die Nachrichtenverschlüsselung, Sha1 für den Nachrichtenhash und Rsa15 für Key Wrap.</span><span class="sxs-lookup"><span data-stu-id="41b16-145">Use Basic256 for message encryption, Sha1 for message digest and Rsa15 for key wrap.</span></span>|  
|<span data-ttu-id="41b16-146">Basic192Rsa15</span><span class="sxs-lookup"><span data-stu-id="41b16-146">Basic192Rsa15</span></span>|<span data-ttu-id="41b16-147">Verwendet Basic192 für die Nachrichtenverschlüsselung, Sha1 für den Nachrichtenhash und Rsa15 für Key Wrap.</span><span class="sxs-lookup"><span data-stu-id="41b16-147">Use Basic192 for message encryption, Sha1 for message digest and Rsa15 for key wrap.</span></span>|  
|<span data-ttu-id="41b16-148">TripleDes</span><span class="sxs-lookup"><span data-stu-id="41b16-148">TripleDes</span></span>|<span data-ttu-id="41b16-149">Verwendet TripleDes-Verschlüsselung, Sha1 für den Nachrichtenhash und Rsa-oaep-mgf1p für Key Wrap.</span><span class="sxs-lookup"><span data-stu-id="41b16-149">Use TripleDes encryption, Sha1 for message digest, Rsa-oaep-mgf1p for key wrap.</span></span>|  
|<span data-ttu-id="41b16-150">Basic128Rsa15</span><span class="sxs-lookup"><span data-stu-id="41b16-150">Basic128Rsa15</span></span>|<span data-ttu-id="41b16-151">Verwendet Basic128 für die Nachrichtenverschlüsselung, Sha1 für den Nachrichtenhash und Rsa15 für Key Wrap.</span><span class="sxs-lookup"><span data-stu-id="41b16-151">Use Basic128 for message encryption, Sha1 for message digest and Rsa15 for key wrap.</span></span>|  
|<span data-ttu-id="41b16-152">TripleDesRsa15</span><span class="sxs-lookup"><span data-stu-id="41b16-152">TripleDesRsa15</span></span>|<span data-ttu-id="41b16-153">Verwendet TripleDes-Verschlüsselung, Sha1 für den Nachrichtenhash und Rsa15 für Key Wrap.</span><span class="sxs-lookup"><span data-stu-id="41b16-153">Use TripleDes encryption, Sha1 for message digest and Rsa15 for key wrap.</span></span>|  
|<span data-ttu-id="41b16-154">Basic128Sha256</span><span class="sxs-lookup"><span data-stu-id="41b16-154">Basic128Sha256</span></span>|<span data-ttu-id="41b16-155">Verwendet Basic128 für die Nachrichtenverschlüsselung, Sha256 für den Nachrichtenhash und Rsa-oaep-mgf1p für Key Wrap.</span><span class="sxs-lookup"><span data-stu-id="41b16-155">Use Basic128 for message encryption, Sha256 for message digest and Rsa-oaep-mgf1p for key wrap.</span></span>|  
|<span data-ttu-id="41b16-156">Basic192Sha256</span><span class="sxs-lookup"><span data-stu-id="41b16-156">Basic192Sha256</span></span>|<span data-ttu-id="41b16-157">Verwendet Basic192 für die Nachrichtenverschlüsselung, Sha256 für den Nachrichtenhash und Rsa-oaep-mgf1p für Key Wrap.</span><span class="sxs-lookup"><span data-stu-id="41b16-157">Use Basic192 for message encryption, Sha256 for message digest and Rsa-oaep-mgf1p for key wrap.</span></span>|  
|<span data-ttu-id="41b16-158">Basic256Sha256</span><span class="sxs-lookup"><span data-stu-id="41b16-158">Basic256Sha256</span></span>|<span data-ttu-id="41b16-159">Verwendet Basic256 für die Nachrichtenverschlüsselung, Sha256 für den Nachrichtenhash und Rsa-oaep-mgf1p für Key Wrap.</span><span class="sxs-lookup"><span data-stu-id="41b16-159">Use Basic256 for message encryption, Sha256 for message digest and Rsa-oaep-mgf1p for key wrap.</span></span>|  
|<span data-ttu-id="41b16-160">TripleDesSha256</span><span class="sxs-lookup"><span data-stu-id="41b16-160">TripleDesSha256</span></span>|<span data-ttu-id="41b16-161">Verwendet TripleDes für die Nachrichtenverschlüsselung, Sha256 für den Nachrichtenhash und Rsa-oaep-mgf1p für Key Wrap.</span><span class="sxs-lookup"><span data-stu-id="41b16-161">Use TripleDes for message encryption, Sha256 for message digest and Rsa-oaep-mgf1p for key wrap.</span></span>|  
|<span data-ttu-id="41b16-162">Basic128Sha256Rsa15</span><span class="sxs-lookup"><span data-stu-id="41b16-162">Basic128Sha256Rsa15</span></span>|<span data-ttu-id="41b16-163">Verwendet Basic128 für die Nachrichtenverschlüsselung, Sha256 für den Nachrichtenhash und Rsa15 für Key Wrap.</span><span class="sxs-lookup"><span data-stu-id="41b16-163">Use Basic128 for message encryption, Sha256 for message digest and Rsa15 for key wrap.</span></span>|  
|<span data-ttu-id="41b16-164">Basic192Sha256Rsa15</span><span class="sxs-lookup"><span data-stu-id="41b16-164">Basic192Sha256Rsa15</span></span>|<span data-ttu-id="41b16-165">Verwendet Aes192 für die Nachrichtenverschlüsselung, Sha256 für den Nachrichtenhash und Rsa15 für Key Wrap.</span><span class="sxs-lookup"><span data-stu-id="41b16-165">Use Aes192 for message encryption, Sha256 for message digest and Rsa15 for key wrap.</span></span>|  
|<span data-ttu-id="41b16-166">Basic256Sha256Rsa15</span><span class="sxs-lookup"><span data-stu-id="41b16-166">Basic256Sha256Rsa15</span></span>|<span data-ttu-id="41b16-167">Verwendet Basic256 für die Nachrichtenverschlüsselung, Sha256 für den Nachrichtenhash und Rsa15 für Key Wrap.</span><span class="sxs-lookup"><span data-stu-id="41b16-167">Use Basic256 for message encryption, Sha256 for message digest and Rsa15 for key wrap.</span></span>|  
|<span data-ttu-id="41b16-168">TripleDesSha256Rsa15</span><span class="sxs-lookup"><span data-stu-id="41b16-168">TripleDesSha256Rsa15</span></span>|<span data-ttu-id="41b16-169">Verwendet TripleDes für die Nachrichtenverschlüsselung, Sha256 für den Nachrichtenhash und Rsa15 für Key Wrap.</span><span class="sxs-lookup"><span data-stu-id="41b16-169">Use TripleDes for message encryption, Sha256 for message digest and Rsa15 for key wrap.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="41b16-170">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="41b16-170">Child Elements</span></span>  
  
|<span data-ttu-id="41b16-171">Element</span><span class="sxs-lookup"><span data-stu-id="41b16-171">Element</span></span>|<span data-ttu-id="41b16-172">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="41b16-172">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="41b16-173">\<claimTypeRequirements></span><span class="sxs-lookup"><span data-stu-id="41b16-173">\<claimTypeRequirements></span></span>](claimtyperequirements-element.md)|<span data-ttu-id="41b16-174">Gibt eine Auflistung von Anspruchstypen für diese Bindung an.</span><span class="sxs-lookup"><span data-stu-id="41b16-174">Specifies a collection of claim types for this binding.</span></span> <span data-ttu-id="41b16-175">Jedes Element ist vom Typ <xref:System.ServiceModel.Configuration.ClaimTypeElement>.</span><span class="sxs-lookup"><span data-stu-id="41b16-175">Each element is of type <xref:System.ServiceModel.Configuration.ClaimTypeElement>.</span></span>|  
|<span data-ttu-id="41b16-176">issuer</span><span class="sxs-lookup"><span data-stu-id="41b16-176">issuer</span></span>|<span data-ttu-id="41b16-177">Gibt einen Endpunkt an, der ein Sicherheitstoken ausstellt.</span><span class="sxs-lookup"><span data-stu-id="41b16-177">Specifies an endpoint that issues a security token.</span></span> <span data-ttu-id="41b16-178">Dieses Element ist vom Typ <xref:System.ServiceModel.Configuration.IssuedTokenParametersEndpointAddressElement>.</span><span class="sxs-lookup"><span data-stu-id="41b16-178">This element is of type <xref:System.ServiceModel.Configuration.IssuedTokenParametersEndpointAddressElement>.</span></span>|  
|<span data-ttu-id="41b16-179">issuerMetadata</span><span class="sxs-lookup"><span data-stu-id="41b16-179">issuerMetadata</span></span>|<span data-ttu-id="41b16-180">Gibt die Endpunktadresse des Ausstellers an.</span><span class="sxs-lookup"><span data-stu-id="41b16-180">Specifies the endpoint address of the issuer.</span></span>|  
|[<span data-ttu-id="41b16-181">\<tokenRequestParameters></span><span class="sxs-lookup"><span data-stu-id="41b16-181">\<tokenRequestParameters></span></span>](tokenrequestparameters.md)|<span data-ttu-id="41b16-182">Eine Auflistung von Tokenanforderungsparametern.</span><span class="sxs-lookup"><span data-stu-id="41b16-182">A collection of token request parameters.</span></span> <span data-ttu-id="41b16-183">Jeder Parameter ist ein XML-Element.</span><span class="sxs-lookup"><span data-stu-id="41b16-183">Each parameter is an XML element.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="41b16-184">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="41b16-184">Parent Elements</span></span>  
  
|<span data-ttu-id="41b16-185">Element</span><span class="sxs-lookup"><span data-stu-id="41b16-185">Element</span></span>|<span data-ttu-id="41b16-186">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="41b16-186">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="41b16-187">\<security></span><span class="sxs-lookup"><span data-stu-id="41b16-187">\<security></span></span>](security-of-wsfederationhttpbinding.md)|<span data-ttu-id="41b16-188">Definiert die Sicherheitseinstellungen für eine Bindung.</span><span class="sxs-lookup"><span data-stu-id="41b16-188">Defines the security settings for a binding.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="41b16-189">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="41b16-189">See also</span></span>

- <xref:System.ServiceModel.FederatedMessageSecurityOverHttp>
- <xref:System.ServiceModel.Configuration.WSFederationHttpSecurityElement.Message%2A>
- <xref:System.ServiceModel.WSFederationHttpSecurity.Message%2A>
- <xref:System.ServiceModel.Configuration.FederatedMessageSecurityOverHttpElement>
- [<span data-ttu-id="41b16-190">Sichern von Diensten und Clients</span><span class="sxs-lookup"><span data-stu-id="41b16-190">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="41b16-191">Bindungen</span><span class="sxs-lookup"><span data-stu-id="41b16-191">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="41b16-192">Konfigurieren der vom System bereitgestellten Bindungen</span><span class="sxs-lookup"><span data-stu-id="41b16-192">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="41b16-193">Verwenden von Bindungen, um Dienste und Clients zu konfigurieren</span><span class="sxs-lookup"><span data-stu-id="41b16-193">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [<span data-ttu-id="41b16-194">\<binding></span><span class="sxs-lookup"><span data-stu-id="41b16-194">\<binding></span></span>](../../../misc/binding.md)
