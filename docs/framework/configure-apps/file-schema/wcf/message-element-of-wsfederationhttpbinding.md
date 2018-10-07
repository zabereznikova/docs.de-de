---
title: '&lt;message&gt;-Element von &lt;wsFederationHttpBinding&gt;'
ms.date: 03/30/2017
ms.assetid: 9d710389-d9d8-4454-9bf2-da4ccda31cec
ms.openlocfilehash: d959d43d9f7d232dea2972b81f1ad2697c8d494a
ms.sourcegitcommit: 586dbdcaef9767642436b1e4efbe88fb15473d6f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/06/2018
ms.locfileid: "48840318"
---
# <a name="ltmessagegt-element-of-ltwsfederationhttpbindinggt"></a><span data-ttu-id="0f72a-102">&lt;message&gt;-Element von &lt;wsFederationHttpBinding&gt;</span><span class="sxs-lookup"><span data-stu-id="0f72a-102">&lt;message&gt; element of &lt;wsFederationHttpBinding&gt;</span></span>
<span data-ttu-id="0f72a-103">Definiert die Einstellungen für die Sicherheit auf Nachrichtenebene für die [ \<WsFederationHttpBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/wsfederationhttpbinding.md).</span><span class="sxs-lookup"><span data-stu-id="0f72a-103">Defines the settings for the message-level security for the [\<wsFederationHttpBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/wsfederationhttpbinding.md).</span></span>  
  
 <span data-ttu-id="0f72a-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="0f72a-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="0f72a-105">\<bindings></span><span class="sxs-lookup"><span data-stu-id="0f72a-105">\<bindings></span></span>  
<span data-ttu-id="0f72a-106">\<wsFederatedBinding></span><span class="sxs-lookup"><span data-stu-id="0f72a-106">\<wsFederatedBinding></span></span>  
<span data-ttu-id="0f72a-107">\<binding></span><span class="sxs-lookup"><span data-stu-id="0f72a-107">\<binding></span></span>  
<span data-ttu-id="0f72a-108">\<Sicherheit ></span><span class="sxs-lookup"><span data-stu-id="0f72a-108">\<security></span></span>  
<span data-ttu-id="0f72a-109">\<Meldung ></span><span class="sxs-lookup"><span data-stu-id="0f72a-109">\<message></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0f72a-110">Syntax</span><span class="sxs-lookup"><span data-stu-id="0f72a-110">Syntax</span></span>  
  
```xml  
<wsFederationBinding>  
     <binding >  
         <security>  
         <message   
            algorithmSuite="Basic128/Basic192/Basic256/Basic128Rsa15/Basic256Rsa15/TripleDes/TripleDesRsa15/Basic128Sha256/Basic192Sha256/TripleDesSha256/Basic128Sha256Rsa15/Basic192Sha256Rsa15/Basic256Sha256Rsa15/TripleDesSha256Rsa15"  
            issuedTokenType="string"   
            issuedKeyType="SymmetricKey/PublicKey"  
            negotiateServiceCredential="Boolean" >  
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
                              <certificate encodedValue="String"/>  
                                <certificateReference findValue="String"   
                                 isChainIncluded="Boolean"  
                            storeName="AddressBook/AuthRoot/CertificateAuthority/Disallowed/My/Root/TrustedPeople/TrustedPublisher"  
                                  storeLocation="LocalMachine/CurrentUser"  
                     x509FindType=System.Security.Cryptography.X509certificates.X509findtype/>  
                                   <dns value="String"/>  
                                <rsa value="String"/>  
                                <servicePrincipalName value="String"/>  
                                <usePrincipalName value="String"/>  
                              </identity>  
                        </issuer>  
                        <issuerMetadata address=String" >  
               <headers>  
                  <add name="String"  
                       namespace="String" />  
               </headers>  
               <identity>  
                  <certificate encodedValue="String"/>  
                  <certificateReference findValue="String"   
                     isChainIncluded="Boolean"  
                     storeName="AddressBook/AuthRoot/CertificateAuthority/Disallowed/My/Root/TrustedPeople/TrustedPublisher"  
                     storeLocation="LocalMachine/CurrentUser"  
                     X509FindType=System.Security.Cryptography.X509certificates.X509findtype/>  
                  <dns value="String"/>  
                  <rsa value="String"/>  
                  <servicePrincipalName value="String"/>  
                  <usePrincipalName value="String"/>  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="0f72a-111">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="0f72a-111">Attributes and Elements</span></span>  
 <span data-ttu-id="0f72a-112">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="0f72a-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="0f72a-113">Attribute</span><span class="sxs-lookup"><span data-stu-id="0f72a-113">Attributes</span></span>  
  
|<span data-ttu-id="0f72a-114">Attribut</span><span class="sxs-lookup"><span data-stu-id="0f72a-114">Attribute</span></span>|<span data-ttu-id="0f72a-115">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="0f72a-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="0f72a-116">algorithmSuite</span><span class="sxs-lookup"><span data-stu-id="0f72a-116">algorithmSuite</span></span>|<span data-ttu-id="0f72a-117">Legt die Nachrichtenverschlüsselungs- und Key Wrap-Algorithmen fest.</span><span class="sxs-lookup"><span data-stu-id="0f72a-117">Sets the message encryption and key-wrap algorithms.</span></span> <span data-ttu-id="0f72a-118">In der Tabelle "algorithmSuite-Attribut" sind die für dieses Attribut gültigen Werte zusammengestellt.</span><span class="sxs-lookup"><span data-stu-id="0f72a-118">See the "algorithmSuite attribute" table for valid values of this attribute.</span></span> <span data-ttu-id="0f72a-119">Der Standardwert ist `Basic256`.</span><span class="sxs-lookup"><span data-stu-id="0f72a-119">The default value is `Basic256`.</span></span><br /><br /> <span data-ttu-id="0f72a-120">Dieses Attribut ist vom Typ <xref:System.ServiceModel.Security.SecurityAlgorithmSuite>.</span><span class="sxs-lookup"><span data-stu-id="0f72a-120">This attribute is of type <xref:System.ServiceModel.Security.SecurityAlgorithmSuite>.</span></span> <span data-ttu-id="0f72a-121">Diese Algorithmen entsprechen den in der Security Policy Language (WS-SecurityPolicy)-Spezifikation angegebenen Algorithmen.</span><span class="sxs-lookup"><span data-stu-id="0f72a-121">These algorithms map to those specified in the Security Policy Language (WS-SecurityPolicy) specification.</span></span>|  
|<span data-ttu-id="0f72a-122">issuedKeyType</span><span class="sxs-lookup"><span data-stu-id="0f72a-122">issuedKeyType</span></span>|<span data-ttu-id="0f72a-123">Gibt den Typ des auszustellenden Schlüssels an.</span><span class="sxs-lookup"><span data-stu-id="0f72a-123">Specifies the type of key to be issued.</span></span> <span data-ttu-id="0f72a-124">Folgende Werte sind gültig:</span><span class="sxs-lookup"><span data-stu-id="0f72a-124">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="0f72a-125">-"SymmetricKey"</span><span class="sxs-lookup"><span data-stu-id="0f72a-125">-   SymmetricKey</span></span><br /><span data-ttu-id="0f72a-126">: Öffentlicher Schlüssel</span><span class="sxs-lookup"><span data-stu-id="0f72a-126">-   PublicKey</span></span><br /><br /> <span data-ttu-id="0f72a-127">Die Standardeinstellung ist `SymmetricKey`.</span><span class="sxs-lookup"><span data-stu-id="0f72a-127">The default is `SymmetricKey`.</span></span> <span data-ttu-id="0f72a-128">Dieses Attribut ist vom Typ <xref:System.IdentityModel.Tokens.SecurityKeyType>.</span><span class="sxs-lookup"><span data-stu-id="0f72a-128">This attribute is of type <xref:System.IdentityModel.Tokens.SecurityKeyType>.</span></span>|  
|<span data-ttu-id="0f72a-129">issuedTokenType</span><span class="sxs-lookup"><span data-stu-id="0f72a-129">issuedTokenType</span></span>|<span data-ttu-id="0f72a-130">Eine Zeichenfolge mit einem URI, die den Typ des auszustellenden Tokens angibt.</span><span class="sxs-lookup"><span data-stu-id="0f72a-130">A string that contains a URI that specifies the type of token to be issued.</span></span> <span data-ttu-id="0f72a-131">Die Standardeinstellung ist `null`.</span><span class="sxs-lookup"><span data-stu-id="0f72a-131">The default is `null`.</span></span>|  
|<span data-ttu-id="0f72a-132">negotiateServiceCredential</span><span class="sxs-lookup"><span data-stu-id="0f72a-132">negotiateServiceCredential</span></span>|<span data-ttu-id="0f72a-133">Ein boolescher Wert, der angibt, ob die Dienstanmeldeinformationen als Teil der Aushandlung ausgetauscht werden sollen oder ob sie out-of-band zur Verfügung stehen.</span><span class="sxs-lookup"><span data-stu-id="0f72a-133">A Boolean value that specifies whether the service credential should be exchanged as part of negotiation or is available out of band.</span></span> <span data-ttu-id="0f72a-134">Der Standardwert ist `true`, was bedeutet, dass die Dienstanmeldeinformationen ausgehandelt werden.</span><span class="sxs-lookup"><span data-stu-id="0f72a-134">The default is `true`, which means that the service credential is negotiated.</span></span>|  
  
## <a name="algorithmsuite-attribute"></a><span data-ttu-id="0f72a-135">algorithmSuite-Attribut</span><span class="sxs-lookup"><span data-stu-id="0f72a-135">algorithmSuite Attribute</span></span>  
  
|<span data-ttu-id="0f72a-136">Wert</span><span class="sxs-lookup"><span data-stu-id="0f72a-136">Value</span></span>|<span data-ttu-id="0f72a-137">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="0f72a-137">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="0f72a-138">Basic128</span><span class="sxs-lookup"><span data-stu-id="0f72a-138">Basic128</span></span>|<span data-ttu-id="0f72a-139">Verwendet Basic128-Verschlüsselung, Sha1 für den Nachrichtenhash und Rsa-oaep-mgf1p für Key Wrap.</span><span class="sxs-lookup"><span data-stu-id="0f72a-139">Use Basic128 encryption, Sha1 for message digest, and Rsa-oaep-mgf1p for key wrap.</span></span>|  
|<span data-ttu-id="0f72a-140">Basic192</span><span class="sxs-lookup"><span data-stu-id="0f72a-140">Basic192</span></span>|<span data-ttu-id="0f72a-141">Verwendet Basic192-Verschlüsselung, Sha1 für den Nachrichtenhash und Rsa-oaep-mgf1p für Key Wrap.</span><span class="sxs-lookup"><span data-stu-id="0f72a-141">Use Basic192 encryption, Sha1 for message digest, Rsa-oaep-mgf1p for key wrap.</span></span>|  
|<span data-ttu-id="0f72a-142">Basic256</span><span class="sxs-lookup"><span data-stu-id="0f72a-142">Basic256</span></span>|<span data-ttu-id="0f72a-143">Verwendet Basic256-Verschlüsselung, Sha1 für den Nachrichtenhash und Rsa-oaep-mgf1p für Key Wrap.</span><span class="sxs-lookup"><span data-stu-id="0f72a-143">Use Basic256 encryption, Sha1 for message digest, Rsa-oaep-mgf1p for key wrap.</span></span>|  
|<span data-ttu-id="0f72a-144">Basic256Rsa15</span><span class="sxs-lookup"><span data-stu-id="0f72a-144">Basic256Rsa15</span></span>|<span data-ttu-id="0f72a-145">Verwendet Basic256 für die Nachrichtenverschlüsselung, Sha1 für den Nachrichtenhash und Rsa15 für Key Wrap.</span><span class="sxs-lookup"><span data-stu-id="0f72a-145">Use Basic256 for message encryption, Sha1 for message digest and Rsa15 for key wrap.</span></span>|  
|<span data-ttu-id="0f72a-146">Basic192Rsa15</span><span class="sxs-lookup"><span data-stu-id="0f72a-146">Basic192Rsa15</span></span>|<span data-ttu-id="0f72a-147">Verwendet Basic192 für die Nachrichtenverschlüsselung, Sha1 für den Nachrichtenhash und Rsa15 für Key Wrap.</span><span class="sxs-lookup"><span data-stu-id="0f72a-147">Use Basic192 for message encryption, Sha1 for message digest and Rsa15 for key wrap.</span></span>|  
|<span data-ttu-id="0f72a-148">TripleDes</span><span class="sxs-lookup"><span data-stu-id="0f72a-148">TripleDes</span></span>|<span data-ttu-id="0f72a-149">Verwendet TripleDes-Verschlüsselung, Sha1 für den Nachrichtenhash und Rsa-oaep-mgf1p für Key Wrap.</span><span class="sxs-lookup"><span data-stu-id="0f72a-149">Use TripleDes encryption, Sha1 for message digest, Rsa-oaep-mgf1p for key wrap.</span></span>|  
|<span data-ttu-id="0f72a-150">Basic128Rsa15</span><span class="sxs-lookup"><span data-stu-id="0f72a-150">Basic128Rsa15</span></span>|<span data-ttu-id="0f72a-151">Verwendet Basic128 für die Nachrichtenverschlüsselung, Sha1 für den Nachrichtenhash und Rsa15 für Key Wrap.</span><span class="sxs-lookup"><span data-stu-id="0f72a-151">Use Basic128 for message encryption, Sha1 for message digest and Rsa15 for key wrap.</span></span>|  
|<span data-ttu-id="0f72a-152">TripleDesRsa15</span><span class="sxs-lookup"><span data-stu-id="0f72a-152">TripleDesRsa15</span></span>|<span data-ttu-id="0f72a-153">Verwendet TripleDes-Verschlüsselung, Sha1 für den Nachrichtenhash und Rsa15 für Key Wrap.</span><span class="sxs-lookup"><span data-stu-id="0f72a-153">Use TripleDes encryption, Sha1 for message digest and Rsa15 for key wrap.</span></span>|  
|<span data-ttu-id="0f72a-154">Basic128Sha256</span><span class="sxs-lookup"><span data-stu-id="0f72a-154">Basic128Sha256</span></span>|<span data-ttu-id="0f72a-155">Verwendet Basic128 für die Nachrichtenverschlüsselung, Sha256 für den Nachrichtenhash und Rsa-oaep-mgf1p für Key Wrap.</span><span class="sxs-lookup"><span data-stu-id="0f72a-155">Use Basic128 for message encryption, Sha256 for message digest and Rsa-oaep-mgf1p for key wrap.</span></span>|  
|<span data-ttu-id="0f72a-156">Basic192Sha256</span><span class="sxs-lookup"><span data-stu-id="0f72a-156">Basic192Sha256</span></span>|<span data-ttu-id="0f72a-157">Verwendet Basic192 für die Nachrichtenverschlüsselung, Sha256 für den Nachrichtenhash und Rsa-oaep-mgf1p für Key Wrap.</span><span class="sxs-lookup"><span data-stu-id="0f72a-157">Use Basic192 for message encryption, Sha256 for message digest and Rsa-oaep-mgf1p for key wrap.</span></span>|  
|<span data-ttu-id="0f72a-158">Basic256Sha256</span><span class="sxs-lookup"><span data-stu-id="0f72a-158">Basic256Sha256</span></span>|<span data-ttu-id="0f72a-159">Verwendet Basic256 für die Nachrichtenverschlüsselung, Sha256 für den Nachrichtenhash und Rsa-oaep-mgf1p für Key Wrap.</span><span class="sxs-lookup"><span data-stu-id="0f72a-159">Use Basic256 for message encryption, Sha256 for message digest and Rsa-oaep-mgf1p for key wrap.</span></span>|  
|<span data-ttu-id="0f72a-160">TripleDesSha256</span><span class="sxs-lookup"><span data-stu-id="0f72a-160">TripleDesSha256</span></span>|<span data-ttu-id="0f72a-161">Verwendet TripleDes für die Nachrichtenverschlüsselung, Sha256 für den Nachrichtenhash und Rsa-oaep-mgf1p für Key Wrap.</span><span class="sxs-lookup"><span data-stu-id="0f72a-161">Use TripleDes for message encryption, Sha256 for message digest and Rsa-oaep-mgf1p for key wrap.</span></span>|  
|<span data-ttu-id="0f72a-162">Basic128Sha256Rsa15</span><span class="sxs-lookup"><span data-stu-id="0f72a-162">Basic128Sha256Rsa15</span></span>|<span data-ttu-id="0f72a-163">Verwendet Basic128 für die Nachrichtenverschlüsselung, Sha256 für den Nachrichtenhash und Rsa15 für Key Wrap.</span><span class="sxs-lookup"><span data-stu-id="0f72a-163">Use Basic128 for message encryption, Sha256 for message digest and Rsa15 for key wrap.</span></span>|  
|<span data-ttu-id="0f72a-164">Basic192Sha256Rsa15</span><span class="sxs-lookup"><span data-stu-id="0f72a-164">Basic192Sha256Rsa15</span></span>|<span data-ttu-id="0f72a-165">Verwendet Aes192 für die Nachrichtenverschlüsselung, Sha256 für den Nachrichtenhash und Rsa15 für Key Wrap.</span><span class="sxs-lookup"><span data-stu-id="0f72a-165">Use Aes192 for message encryption, Sha256 for message digest and Rsa15 for key wrap.</span></span>|  
|<span data-ttu-id="0f72a-166">Basic256Sha256Rsa15</span><span class="sxs-lookup"><span data-stu-id="0f72a-166">Basic256Sha256Rsa15</span></span>|<span data-ttu-id="0f72a-167">Verwendet Basic256 für die Nachrichtenverschlüsselung, Sha256 für den Nachrichtenhash und Rsa15 für Key Wrap.</span><span class="sxs-lookup"><span data-stu-id="0f72a-167">Use Basic256 for message encryption, Sha256 for message digest and Rsa15 for key wrap.</span></span>|  
|<span data-ttu-id="0f72a-168">TripleDesSha256Rsa15</span><span class="sxs-lookup"><span data-stu-id="0f72a-168">TripleDesSha256Rsa15</span></span>|<span data-ttu-id="0f72a-169">Verwendet TripleDes für die Nachrichtenverschlüsselung, Sha256 für den Nachrichtenhash und Rsa15 für Key Wrap.</span><span class="sxs-lookup"><span data-stu-id="0f72a-169">Use TripleDes for message encryption, Sha256 for message digest and Rsa15 for key wrap.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="0f72a-170">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="0f72a-170">Child Elements</span></span>  
  
|<span data-ttu-id="0f72a-171">Element</span><span class="sxs-lookup"><span data-stu-id="0f72a-171">Element</span></span>|<span data-ttu-id="0f72a-172">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="0f72a-172">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="0f72a-173">\<claimTypeRequirements></span><span class="sxs-lookup"><span data-stu-id="0f72a-173">\<claimTypeRequirements></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/claimtyperequirements-element.md)|<span data-ttu-id="0f72a-174">Gibt eine Auflistung von Anspruchstypen für diese Bindung an.</span><span class="sxs-lookup"><span data-stu-id="0f72a-174">Specifies a collection of claim types for this binding.</span></span> <span data-ttu-id="0f72a-175">Jedes Element ist vom Typ <xref:System.ServiceModel.Configuration.ClaimTypeElement>.</span><span class="sxs-lookup"><span data-stu-id="0f72a-175">Each element is of type <xref:System.ServiceModel.Configuration.ClaimTypeElement>.</span></span>|  
|<span data-ttu-id="0f72a-176">issuer</span><span class="sxs-lookup"><span data-stu-id="0f72a-176">issuer</span></span>|<span data-ttu-id="0f72a-177">Gibt einen Endpunkt an, der ein Sicherheitstoken ausstellt.</span><span class="sxs-lookup"><span data-stu-id="0f72a-177">Specifies an endpoint that issues a security token.</span></span> <span data-ttu-id="0f72a-178">Dieses Element ist vom Typ <xref:System.ServiceModel.Configuration.IssuedTokenParametersEndpointAddressElement>.</span><span class="sxs-lookup"><span data-stu-id="0f72a-178">This element is of type <xref:System.ServiceModel.Configuration.IssuedTokenParametersEndpointAddressElement>.</span></span>|  
|<span data-ttu-id="0f72a-179">issuerMetadata</span><span class="sxs-lookup"><span data-stu-id="0f72a-179">issuerMetadata</span></span>|<span data-ttu-id="0f72a-180">Gibt die Endpunktadresse des Ausstellers an.</span><span class="sxs-lookup"><span data-stu-id="0f72a-180">Specifies the endpoint address of the issuer.</span></span>|  
|[<span data-ttu-id="0f72a-181">\<tokenRequestParameters></span><span class="sxs-lookup"><span data-stu-id="0f72a-181">\<tokenRequestParameters></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/tokenrequestparameters.md)|<span data-ttu-id="0f72a-182">Eine Auflistung von Tokenanforderungsparametern.</span><span class="sxs-lookup"><span data-stu-id="0f72a-182">A collection of token request parameters.</span></span> <span data-ttu-id="0f72a-183">Jeder Parameter ist ein XML-Element.</span><span class="sxs-lookup"><span data-stu-id="0f72a-183">Each parameter is an XML element.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="0f72a-184">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="0f72a-184">Parent Elements</span></span>  
  
|<span data-ttu-id="0f72a-185">Element</span><span class="sxs-lookup"><span data-stu-id="0f72a-185">Element</span></span>|<span data-ttu-id="0f72a-186">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="0f72a-186">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="0f72a-187">\<security></span><span class="sxs-lookup"><span data-stu-id="0f72a-187">\<security></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/security-of-wsfederationhttpbinding.md)|<span data-ttu-id="0f72a-188">Definiert die Sicherheitseinstellungen für eine Bindung.</span><span class="sxs-lookup"><span data-stu-id="0f72a-188">Defines the security settings for a binding.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="0f72a-189">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="0f72a-189">See Also</span></span>  
 <xref:System.ServiceModel.FederatedMessageSecurityOverHttp>  
 <xref:System.ServiceModel.Configuration.WSFederationHttpSecurityElement.Message%2A>  
 <xref:System.ServiceModel.WSFederationHttpSecurity.Message%2A>  
 <span data-ttu-id="0f72a-190">`System.ServiceModel.Configuration.FederatedMessageSecurityElement` [Sichern von Diensten und Clients](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)</span><span class="sxs-lookup"><span data-stu-id="0f72a-190">`System.ServiceModel.Configuration.FederatedMessageSecurityElement` [Securing Services and Clients](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)</span></span>  
 [<span data-ttu-id="0f72a-191">Bindungen</span><span class="sxs-lookup"><span data-stu-id="0f72a-191">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)  
 [<span data-ttu-id="0f72a-192">Konfigurieren der vom System bereitgestellten Bindungen</span><span class="sxs-lookup"><span data-stu-id="0f72a-192">Configuring System-Provided Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)  
 [<span data-ttu-id="0f72a-193">Verwenden von Bindungen, um Dienste und Clients zu konfigurieren</span><span class="sxs-lookup"><span data-stu-id="0f72a-193">Using Bindings to Configure Services and Clients</span></span>](../../../../../docs/framework/wcf/using-bindings-to-configure-services-and-clients.md)  
 [<span data-ttu-id="0f72a-194">\<binding></span><span class="sxs-lookup"><span data-stu-id="0f72a-194">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)
