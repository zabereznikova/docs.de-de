---
title: <message> Element von <wsFederationHttpBinding>
ms.date: 03/30/2017
ms.assetid: 9d710389-d9d8-4454-9bf2-da4ccda31cec
ms.openlocfilehash: 8e0903dd1313e68e2de65730e129079199ebe2f2
ms.sourcegitcommit: 22be09204266253d45ece46f51cc6f080f2b3fd6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/07/2019
ms.locfileid: "73738980"
---
# <a name="message-element-of-wsfederationhttpbinding"></a><span data-ttu-id="71ee2-102">\<Message > Element von \<WSFederationHttpBinding ></span><span class="sxs-lookup"><span data-stu-id="71ee2-102">\<message> element of \<wsFederationHttpBinding></span></span>
<span data-ttu-id="71ee2-103">Definiert die Einstellungen für die Sicherheit auf Nachrichten Ebene für die [\<WSFederationHttpBinding->](wsfederationhttpbinding.md).</span><span class="sxs-lookup"><span data-stu-id="71ee2-103">Defines the settings for the message-level security for the [\<wsFederationHttpBinding>](wsfederationhttpbinding.md).</span></span>  
  
<span data-ttu-id="71ee2-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="71ee2-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="71ee2-105">&nbsp; &nbsp;[ **\<system. Service Model->** ](system-servicemodel.md) </span><span class="sxs-lookup"><span data-stu-id="71ee2-105">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="71ee2-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Bindungen >** ](bindings.md)</span><span class="sxs-lookup"><span data-stu-id="71ee2-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)</span></span>\
<span data-ttu-id="71ee2-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<WSFederationHttpBinding >** ](wsfederationhttpbinding.md)</span><span class="sxs-lookup"><span data-stu-id="71ee2-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<wsFederationHttpBinding>**](wsfederationhttpbinding.md)</span></span>\
<span data-ttu-id="71ee2-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<**Bindungs >** </span><span class="sxs-lookup"><span data-stu-id="71ee2-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**</span></span>\
<span data-ttu-id="71ee2-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Sicherheit >** ](security-of-wsfederationhttpbinding.md)</span><span class="sxs-lookup"><span data-stu-id="71ee2-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<security>**](security-of-wsfederationhttpbinding.md)</span></span>\
<span data-ttu-id="71ee2-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<**Meldung** ></span><span class="sxs-lookup"><span data-stu-id="71ee2-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<message>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="71ee2-111">Syntax</span><span class="sxs-lookup"><span data-stu-id="71ee2-111">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="71ee2-112">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="71ee2-112">Attributes and Elements</span></span>  
 <span data-ttu-id="71ee2-113">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="71ee2-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="71ee2-114">Attribute</span><span class="sxs-lookup"><span data-stu-id="71ee2-114">Attributes</span></span>  
  
|<span data-ttu-id="71ee2-115">Attribut</span><span class="sxs-lookup"><span data-stu-id="71ee2-115">Attribute</span></span>|<span data-ttu-id="71ee2-116">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="71ee2-116">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="71ee2-117">algorithmSuite</span><span class="sxs-lookup"><span data-stu-id="71ee2-117">algorithmSuite</span></span>|<span data-ttu-id="71ee2-118">Legt die Nachrichtenverschlüsselungs- und Key Wrap-Algorithmen fest.</span><span class="sxs-lookup"><span data-stu-id="71ee2-118">Sets the message encryption and key-wrap algorithms.</span></span> <span data-ttu-id="71ee2-119">In der Tabelle "algorithmSuite-Attribut" sind die für dieses Attribut gültigen Werte zusammengestellt.</span><span class="sxs-lookup"><span data-stu-id="71ee2-119">See the "algorithmSuite attribute" table for valid values of this attribute.</span></span> <span data-ttu-id="71ee2-120">Der Standardwert ist `Basic256`sein.</span><span class="sxs-lookup"><span data-stu-id="71ee2-120">The default value is `Basic256`.</span></span><br /><br /> <span data-ttu-id="71ee2-121">Dieses Attribut ist vom Typ <xref:System.ServiceModel.Security.SecurityAlgorithmSuite>.</span><span class="sxs-lookup"><span data-stu-id="71ee2-121">This attribute is of type <xref:System.ServiceModel.Security.SecurityAlgorithmSuite>.</span></span> <span data-ttu-id="71ee2-122">Diese Algorithmen entsprechen den in der Security Policy Language (WS-SecurityPolicy)-Spezifikation angegebenen Algorithmen.</span><span class="sxs-lookup"><span data-stu-id="71ee2-122">These algorithms map to those specified in the Security Policy Language (WS-SecurityPolicy) specification.</span></span>|  
|<span data-ttu-id="71ee2-123">issuedKeyType</span><span class="sxs-lookup"><span data-stu-id="71ee2-123">issuedKeyType</span></span>|<span data-ttu-id="71ee2-124">Gibt den Typ des auszustellenden Schlüssels an.</span><span class="sxs-lookup"><span data-stu-id="71ee2-124">Specifies the type of key to be issued.</span></span> <span data-ttu-id="71ee2-125">Folgende Werte sind gültig:</span><span class="sxs-lookup"><span data-stu-id="71ee2-125">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="71ee2-126">-SymmetricKey</span><span class="sxs-lookup"><span data-stu-id="71ee2-126">-   SymmetricKey</span></span><br /><span data-ttu-id="71ee2-127">-PublicKey</span><span class="sxs-lookup"><span data-stu-id="71ee2-127">-   PublicKey</span></span><br /><br /> <span data-ttu-id="71ee2-128">Der Standardwert ist `SymmetricKey`.</span><span class="sxs-lookup"><span data-stu-id="71ee2-128">The default is `SymmetricKey`.</span></span> <span data-ttu-id="71ee2-129">Dieses Attribut ist vom Typ <xref:System.IdentityModel.Tokens.SecurityKeyType>.</span><span class="sxs-lookup"><span data-stu-id="71ee2-129">This attribute is of type <xref:System.IdentityModel.Tokens.SecurityKeyType>.</span></span>|  
|<span data-ttu-id="71ee2-130">issuedTokenType</span><span class="sxs-lookup"><span data-stu-id="71ee2-130">issuedTokenType</span></span>|<span data-ttu-id="71ee2-131">Eine Zeichenfolge mit einem URI, die den Typ des auszustellenden Tokens angibt.</span><span class="sxs-lookup"><span data-stu-id="71ee2-131">A string that contains a URI that specifies the type of token to be issued.</span></span> <span data-ttu-id="71ee2-132">Der Standardwert ist `null`.</span><span class="sxs-lookup"><span data-stu-id="71ee2-132">The default is `null`.</span></span>|  
|<span data-ttu-id="71ee2-133">negotiateServiceCredential</span><span class="sxs-lookup"><span data-stu-id="71ee2-133">negotiateServiceCredential</span></span>|<span data-ttu-id="71ee2-134">Ein boolescher Wert, der angibt, ob die Dienstanmeldeinformationen als Teil der Aushandlung ausgetauscht werden sollen oder ob sie out-of-band zur Verfügung stehen.</span><span class="sxs-lookup"><span data-stu-id="71ee2-134">A Boolean value that specifies whether the service credential should be exchanged as part of negotiation or is available out of band.</span></span> <span data-ttu-id="71ee2-135">Der Standardwert ist `true`, was bedeutet, dass die Dienstanmeldeinformationen ausgehandelt werden.</span><span class="sxs-lookup"><span data-stu-id="71ee2-135">The default is `true`, which means that the service credential is negotiated.</span></span>|  
  
## <a name="algorithmsuite-attribute"></a><span data-ttu-id="71ee2-136">algorithmSuite-Attribut</span><span class="sxs-lookup"><span data-stu-id="71ee2-136">algorithmSuite Attribute</span></span>  
  
|<span data-ttu-id="71ee2-137">Wert</span><span class="sxs-lookup"><span data-stu-id="71ee2-137">Value</span></span>|<span data-ttu-id="71ee2-138">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="71ee2-138">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="71ee2-139">Basic128</span><span class="sxs-lookup"><span data-stu-id="71ee2-139">Basic128</span></span>|<span data-ttu-id="71ee2-140">Verwendet Basic128-Verschlüsselung, Sha1 für den Nachrichtenhash und Rsa-oaep-mgf1p für Key Wrap.</span><span class="sxs-lookup"><span data-stu-id="71ee2-140">Use Basic128 encryption, Sha1 for message digest, and Rsa-oaep-mgf1p for key wrap.</span></span>|  
|<span data-ttu-id="71ee2-141">Basic192</span><span class="sxs-lookup"><span data-stu-id="71ee2-141">Basic192</span></span>|<span data-ttu-id="71ee2-142">Verwendet Basic192-Verschlüsselung, Sha1 für den Nachrichtenhash und Rsa-oaep-mgf1p für Key Wrap.</span><span class="sxs-lookup"><span data-stu-id="71ee2-142">Use Basic192 encryption, Sha1 for message digest, Rsa-oaep-mgf1p for key wrap.</span></span>|  
|<span data-ttu-id="71ee2-143">Basic256</span><span class="sxs-lookup"><span data-stu-id="71ee2-143">Basic256</span></span>|<span data-ttu-id="71ee2-144">Verwendet Basic256-Verschlüsselung, Sha1 für den Nachrichtenhash und Rsa-oaep-mgf1p für Key Wrap.</span><span class="sxs-lookup"><span data-stu-id="71ee2-144">Use Basic256 encryption, Sha1 for message digest, Rsa-oaep-mgf1p for key wrap.</span></span>|  
|<span data-ttu-id="71ee2-145">Basic256Rsa15</span><span class="sxs-lookup"><span data-stu-id="71ee2-145">Basic256Rsa15</span></span>|<span data-ttu-id="71ee2-146">Verwendet Basic256 für die Nachrichtenverschlüsselung, Sha1 für den Nachrichtenhash und Rsa15 für Key Wrap.</span><span class="sxs-lookup"><span data-stu-id="71ee2-146">Use Basic256 for message encryption, Sha1 for message digest and Rsa15 for key wrap.</span></span>|  
|<span data-ttu-id="71ee2-147">Basic192Rsa15</span><span class="sxs-lookup"><span data-stu-id="71ee2-147">Basic192Rsa15</span></span>|<span data-ttu-id="71ee2-148">Verwendet Basic192 für die Nachrichtenverschlüsselung, Sha1 für den Nachrichtenhash und Rsa15 für Key Wrap.</span><span class="sxs-lookup"><span data-stu-id="71ee2-148">Use Basic192 for message encryption, Sha1 for message digest and Rsa15 for key wrap.</span></span>|  
|<span data-ttu-id="71ee2-149">TripleDes</span><span class="sxs-lookup"><span data-stu-id="71ee2-149">TripleDes</span></span>|<span data-ttu-id="71ee2-150">Verwendet TripleDes-Verschlüsselung, Sha1 für den Nachrichtenhash und Rsa-oaep-mgf1p für Key Wrap.</span><span class="sxs-lookup"><span data-stu-id="71ee2-150">Use TripleDes encryption, Sha1 for message digest, Rsa-oaep-mgf1p for key wrap.</span></span>|  
|<span data-ttu-id="71ee2-151">Basic128Rsa15</span><span class="sxs-lookup"><span data-stu-id="71ee2-151">Basic128Rsa15</span></span>|<span data-ttu-id="71ee2-152">Verwendet Basic128 für die Nachrichtenverschlüsselung, Sha1 für den Nachrichtenhash und Rsa15 für Key Wrap.</span><span class="sxs-lookup"><span data-stu-id="71ee2-152">Use Basic128 for message encryption, Sha1 for message digest and Rsa15 for key wrap.</span></span>|  
|<span data-ttu-id="71ee2-153">TripleDesRsa15</span><span class="sxs-lookup"><span data-stu-id="71ee2-153">TripleDesRsa15</span></span>|<span data-ttu-id="71ee2-154">Verwendet TripleDes-Verschlüsselung, Sha1 für den Nachrichtenhash und Rsa15 für Key Wrap.</span><span class="sxs-lookup"><span data-stu-id="71ee2-154">Use TripleDes encryption, Sha1 for message digest and Rsa15 for key wrap.</span></span>|  
|<span data-ttu-id="71ee2-155">Basic128Sha256</span><span class="sxs-lookup"><span data-stu-id="71ee2-155">Basic128Sha256</span></span>|<span data-ttu-id="71ee2-156">Verwendet Basic128 für die Nachrichtenverschlüsselung, Sha256 für den Nachrichtenhash und Rsa-oaep-mgf1p für Key Wrap.</span><span class="sxs-lookup"><span data-stu-id="71ee2-156">Use Basic128 for message encryption, Sha256 for message digest and Rsa-oaep-mgf1p for key wrap.</span></span>|  
|<span data-ttu-id="71ee2-157">Basic192Sha256</span><span class="sxs-lookup"><span data-stu-id="71ee2-157">Basic192Sha256</span></span>|<span data-ttu-id="71ee2-158">Verwendet Basic192 für die Nachrichtenverschlüsselung, Sha256 für den Nachrichtenhash und Rsa-oaep-mgf1p für Key Wrap.</span><span class="sxs-lookup"><span data-stu-id="71ee2-158">Use Basic192 for message encryption, Sha256 for message digest and Rsa-oaep-mgf1p for key wrap.</span></span>|  
|<span data-ttu-id="71ee2-159">Basic256Sha256</span><span class="sxs-lookup"><span data-stu-id="71ee2-159">Basic256Sha256</span></span>|<span data-ttu-id="71ee2-160">Verwendet Basic256 für die Nachrichtenverschlüsselung, Sha256 für den Nachrichtenhash und Rsa-oaep-mgf1p für Key Wrap.</span><span class="sxs-lookup"><span data-stu-id="71ee2-160">Use Basic256 for message encryption, Sha256 for message digest and Rsa-oaep-mgf1p for key wrap.</span></span>|  
|<span data-ttu-id="71ee2-161">TripleDesSha256</span><span class="sxs-lookup"><span data-stu-id="71ee2-161">TripleDesSha256</span></span>|<span data-ttu-id="71ee2-162">Verwendet TripleDes für die Nachrichtenverschlüsselung, Sha256 für den Nachrichtenhash und Rsa-oaep-mgf1p für Key Wrap.</span><span class="sxs-lookup"><span data-stu-id="71ee2-162">Use TripleDes for message encryption, Sha256 for message digest and Rsa-oaep-mgf1p for key wrap.</span></span>|  
|<span data-ttu-id="71ee2-163">Basic128Sha256Rsa15</span><span class="sxs-lookup"><span data-stu-id="71ee2-163">Basic128Sha256Rsa15</span></span>|<span data-ttu-id="71ee2-164">Verwendet Basic128 für die Nachrichtenverschlüsselung, Sha256 für den Nachrichtenhash und Rsa15 für Key Wrap.</span><span class="sxs-lookup"><span data-stu-id="71ee2-164">Use Basic128 for message encryption, Sha256 for message digest and Rsa15 for key wrap.</span></span>|  
|<span data-ttu-id="71ee2-165">Basic192Sha256Rsa15</span><span class="sxs-lookup"><span data-stu-id="71ee2-165">Basic192Sha256Rsa15</span></span>|<span data-ttu-id="71ee2-166">Verwendet Aes192 für die Nachrichtenverschlüsselung, Sha256 für den Nachrichtenhash und Rsa15 für Key Wrap.</span><span class="sxs-lookup"><span data-stu-id="71ee2-166">Use Aes192 for message encryption, Sha256 for message digest and Rsa15 for key wrap.</span></span>|  
|<span data-ttu-id="71ee2-167">Basic256Sha256Rsa15</span><span class="sxs-lookup"><span data-stu-id="71ee2-167">Basic256Sha256Rsa15</span></span>|<span data-ttu-id="71ee2-168">Verwendet Basic256 für die Nachrichtenverschlüsselung, Sha256 für den Nachrichtenhash und Rsa15 für Key Wrap.</span><span class="sxs-lookup"><span data-stu-id="71ee2-168">Use Basic256 for message encryption, Sha256 for message digest and Rsa15 for key wrap.</span></span>|  
|<span data-ttu-id="71ee2-169">TripleDesSha256Rsa15</span><span class="sxs-lookup"><span data-stu-id="71ee2-169">TripleDesSha256Rsa15</span></span>|<span data-ttu-id="71ee2-170">Verwendet TripleDes für die Nachrichtenverschlüsselung, Sha256 für den Nachrichtenhash und Rsa15 für Key Wrap.</span><span class="sxs-lookup"><span data-stu-id="71ee2-170">Use TripleDes for message encryption, Sha256 for message digest and Rsa15 for key wrap.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="71ee2-171">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="71ee2-171">Child Elements</span></span>  
  
|<span data-ttu-id="71ee2-172">Element</span><span class="sxs-lookup"><span data-stu-id="71ee2-172">Element</span></span>|<span data-ttu-id="71ee2-173">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="71ee2-173">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="71ee2-174">\<claimtyperequirequirements ></span><span class="sxs-lookup"><span data-stu-id="71ee2-174">\<claimTypeRequirements></span></span>](claimtyperequirements-element.md)|<span data-ttu-id="71ee2-175">Gibt eine Auflistung von Anspruchstypen für diese Bindung an.</span><span class="sxs-lookup"><span data-stu-id="71ee2-175">Specifies a collection of claim types for this binding.</span></span> <span data-ttu-id="71ee2-176">Jedes Element ist vom Typ <xref:System.ServiceModel.Configuration.ClaimTypeElement>.</span><span class="sxs-lookup"><span data-stu-id="71ee2-176">Each element is of type <xref:System.ServiceModel.Configuration.ClaimTypeElement>.</span></span>|  
|<span data-ttu-id="71ee2-177">issuer</span><span class="sxs-lookup"><span data-stu-id="71ee2-177">issuer</span></span>|<span data-ttu-id="71ee2-178">Gibt einen Endpunkt an, der ein Sicherheitstoken ausstellt.</span><span class="sxs-lookup"><span data-stu-id="71ee2-178">Specifies an endpoint that issues a security token.</span></span> <span data-ttu-id="71ee2-179">Dieses Element ist vom Typ <xref:System.ServiceModel.Configuration.IssuedTokenParametersEndpointAddressElement>.</span><span class="sxs-lookup"><span data-stu-id="71ee2-179">This element is of type <xref:System.ServiceModel.Configuration.IssuedTokenParametersEndpointAddressElement>.</span></span>|  
|<span data-ttu-id="71ee2-180">issuerMetadata</span><span class="sxs-lookup"><span data-stu-id="71ee2-180">issuerMetadata</span></span>|<span data-ttu-id="71ee2-181">Gibt die Endpunktadresse des Ausstellers an.</span><span class="sxs-lookup"><span data-stu-id="71ee2-181">Specifies the endpoint address of the issuer.</span></span>|  
|[<span data-ttu-id="71ee2-182">\<TokenRequestParameters ></span><span class="sxs-lookup"><span data-stu-id="71ee2-182">\<tokenRequestParameters></span></span>](tokenrequestparameters.md)|<span data-ttu-id="71ee2-183">Eine Auflistung von Tokenanforderungsparametern.</span><span class="sxs-lookup"><span data-stu-id="71ee2-183">A collection of token request parameters.</span></span> <span data-ttu-id="71ee2-184">Jeder Parameter ist ein XML-Element.</span><span class="sxs-lookup"><span data-stu-id="71ee2-184">Each parameter is an XML element.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="71ee2-185">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="71ee2-185">Parent Elements</span></span>  
  
|<span data-ttu-id="71ee2-186">Element</span><span class="sxs-lookup"><span data-stu-id="71ee2-186">Element</span></span>|<span data-ttu-id="71ee2-187">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="71ee2-187">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="71ee2-188">\<Security ></span><span class="sxs-lookup"><span data-stu-id="71ee2-188">\<security></span></span>](security-of-wsfederationhttpbinding.md)|<span data-ttu-id="71ee2-189">Definiert die Sicherheitseinstellungen für eine Bindung.</span><span class="sxs-lookup"><span data-stu-id="71ee2-189">Defines the security settings for a binding.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="71ee2-190">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="71ee2-190">See also</span></span>

- <xref:System.ServiceModel.FederatedMessageSecurityOverHttp>
- <xref:System.ServiceModel.Configuration.WSFederationHttpSecurityElement.Message%2A>
- <xref:System.ServiceModel.WSFederationHttpSecurity.Message%2A>
- <xref:System.ServiceModel.Configuration.FederatedMessageSecurityOverHttpElement>
- [<span data-ttu-id="71ee2-191">Sichern von Diensten und Clients</span><span class="sxs-lookup"><span data-stu-id="71ee2-191">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="71ee2-192">Bindungen</span><span class="sxs-lookup"><span data-stu-id="71ee2-192">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="71ee2-193">Konfigurieren der vom System bereitgestellten Bindungen</span><span class="sxs-lookup"><span data-stu-id="71ee2-193">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="71ee2-194">Verwenden von Bindungen, um Dienste und Clients zu konfigurieren</span><span class="sxs-lookup"><span data-stu-id="71ee2-194">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [<span data-ttu-id="71ee2-195">\<binding ></span><span class="sxs-lookup"><span data-stu-id="71ee2-195">\<binding></span></span>](bindings.md)
