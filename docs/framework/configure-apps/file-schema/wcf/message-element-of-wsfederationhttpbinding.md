---
title: '&lt;message&gt;-Element von &lt;wsFederationHttpBinding&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 9d710389-d9d8-4454-9bf2-da4ccda31cec
caps.latest.revision: "28"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: fb12cc0162cabd75f176c636b9cd4d00309bb594
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/02/2017
---
# <a name="ltmessagegt-element-of-ltwsfederationhttpbindinggt"></a><span data-ttu-id="505d2-102">&lt;message&gt;-Element von &lt;wsFederationHttpBinding&gt;</span><span class="sxs-lookup"><span data-stu-id="505d2-102">&lt;message&gt; element of &lt;wsFederationHttpBinding&gt;</span></span>
<span data-ttu-id="505d2-103">Definiert die Einstellungen für die Sicherheit auf Nachrichtenebene für die [ \<WsFederationHttpBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/wsfederationhttpbinding.md).</span><span class="sxs-lookup"><span data-stu-id="505d2-103">Defines the settings for the message-level security for the [\<wsFederationHttpBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/wsfederationhttpbinding.md).</span></span>  
  
 <span data-ttu-id="505d2-104">\<System. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="505d2-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="505d2-105">\<Bindungen ></span><span class="sxs-lookup"><span data-stu-id="505d2-105">\<bindings></span></span>  
<span data-ttu-id="505d2-106">\<WsFederatedBinding ></span><span class="sxs-lookup"><span data-stu-id="505d2-106">\<wsFederatedBinding></span></span>  
<span data-ttu-id="505d2-107">\<Binden von ></span><span class="sxs-lookup"><span data-stu-id="505d2-107">\<binding></span></span>  
<span data-ttu-id="505d2-108">\<Sicherheit ></span><span class="sxs-lookup"><span data-stu-id="505d2-108">\<security></span></span>  
<span data-ttu-id="505d2-109">\<Meldung ></span><span class="sxs-lookup"><span data-stu-id="505d2-109">\<message></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="505d2-110">Syntax</span><span class="sxs-lookup"><span data-stu-id="505d2-110">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="505d2-111">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="505d2-111">Attributes and Elements</span></span>  
 <span data-ttu-id="505d2-112">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="505d2-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="505d2-113">Attribute</span><span class="sxs-lookup"><span data-stu-id="505d2-113">Attributes</span></span>  
  
|<span data-ttu-id="505d2-114">Attribut</span><span class="sxs-lookup"><span data-stu-id="505d2-114">Attribute</span></span>|<span data-ttu-id="505d2-115">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="505d2-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="505d2-116">algorithmSuite</span><span class="sxs-lookup"><span data-stu-id="505d2-116">algorithmSuite</span></span>|<span data-ttu-id="505d2-117">Legt die Nachrichtenverschlüsselungs- und Key Wrap-Algorithmen fest.</span><span class="sxs-lookup"><span data-stu-id="505d2-117">Sets the message encryption and key-wrap algorithms.</span></span> <span data-ttu-id="505d2-118">In der Tabelle "algorithmSuite-Attribut" sind die für dieses Attribut gültigen Werte zusammengestellt.</span><span class="sxs-lookup"><span data-stu-id="505d2-118">See the "algorithmSuite attribute" table for valid values of this attribute.</span></span> <span data-ttu-id="505d2-119">Der Standardwert ist `Basic256`.</span><span class="sxs-lookup"><span data-stu-id="505d2-119">The default value is `Basic256`.</span></span><br /><br /> <span data-ttu-id="505d2-120">Dieses Attribut ist vom Typ <xref:System.ServiceModel.Security.SecurityAlgorithmSuite>.</span><span class="sxs-lookup"><span data-stu-id="505d2-120">This attribute is of type <xref:System.ServiceModel.Security.SecurityAlgorithmSuite>.</span></span> <span data-ttu-id="505d2-121">Diese Algorithmen entsprechen den in der Security Policy Language (WS-SecurityPolicy)-Spezifikation angegebenen Algorithmen.</span><span class="sxs-lookup"><span data-stu-id="505d2-121">These algorithms map to those specified in the Security Policy Language (WS-SecurityPolicy) specification.</span></span>|  
|<span data-ttu-id="505d2-122">issuedKeyType</span><span class="sxs-lookup"><span data-stu-id="505d2-122">issuedKeyType</span></span>|<span data-ttu-id="505d2-123">Gibt den Typ des auszustellenden Schlüssels an.</span><span class="sxs-lookup"><span data-stu-id="505d2-123">Specifies the type of key to be issued.</span></span> <span data-ttu-id="505d2-124">Folgende Werte sind gültig:</span><span class="sxs-lookup"><span data-stu-id="505d2-124">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="505d2-125">-SymmetricKey</span><span class="sxs-lookup"><span data-stu-id="505d2-125">-   SymmetricKey</span></span><br /><span data-ttu-id="505d2-126">-PublicKey</span><span class="sxs-lookup"><span data-stu-id="505d2-126">-   PublicKey</span></span><br /><br /> <span data-ttu-id="505d2-127">Die Standardeinstellung ist `SymmetricKey`.</span><span class="sxs-lookup"><span data-stu-id="505d2-127">The default is `SymmetricKey`.</span></span> <span data-ttu-id="505d2-128">Dieses Attribut ist vom Typ <xref:System.IdentityModel.Tokens.SecurityKeyType>.</span><span class="sxs-lookup"><span data-stu-id="505d2-128">This attribute is of type <xref:System.IdentityModel.Tokens.SecurityKeyType>.</span></span>|  
|<span data-ttu-id="505d2-129">issuedTokenType</span><span class="sxs-lookup"><span data-stu-id="505d2-129">issuedTokenType</span></span>|<span data-ttu-id="505d2-130">Eine Zeichenfolge mit einem URI, die den Typ des auszustellenden Tokens angibt.</span><span class="sxs-lookup"><span data-stu-id="505d2-130">A string that contains a URI that specifies the type of token to be issued.</span></span> <span data-ttu-id="505d2-131">Die Standardeinstellung ist `null`.</span><span class="sxs-lookup"><span data-stu-id="505d2-131">The default is `null`.</span></span>|  
|<span data-ttu-id="505d2-132">negotiateServiceCredential</span><span class="sxs-lookup"><span data-stu-id="505d2-132">negotiateServiceCredential</span></span>|<span data-ttu-id="505d2-133">Ein boolescher Wert, der angibt, ob die Dienstanmeldeinformationen als Teil der Aushandlung ausgetauscht werden sollen oder ob sie out-of-band zur Verfügung stehen.</span><span class="sxs-lookup"><span data-stu-id="505d2-133">A Boolean value that specifies whether the service credential should be exchanged as part of negotiation or is available out of band.</span></span> <span data-ttu-id="505d2-134">Der Standardwert ist `true`, was bedeutet, dass die Dienstanmeldeinformationen ausgehandelt werden.</span><span class="sxs-lookup"><span data-stu-id="505d2-134">The default is `true`, which means that the service credential is negotiated.</span></span>|  
  
## <a name="algorithmsuite-attribute"></a><span data-ttu-id="505d2-135">algorithmSuite-Attribut</span><span class="sxs-lookup"><span data-stu-id="505d2-135">algorithmSuite Attribute</span></span>  
  
|<span data-ttu-id="505d2-136">Wert</span><span class="sxs-lookup"><span data-stu-id="505d2-136">Value</span></span>|<span data-ttu-id="505d2-137">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="505d2-137">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="505d2-138">Basic128</span><span class="sxs-lookup"><span data-stu-id="505d2-138">Basic128</span></span>|<span data-ttu-id="505d2-139">Verwendet Basic128-Verschlüsselung, Sha1 für den Nachrichtenhash und Rsa-oaep-mgf1p für Key Wrap.</span><span class="sxs-lookup"><span data-stu-id="505d2-139">Use Basic128 encryption, Sha1 for message digest, and Rsa-oaep-mgf1p for key wrap.</span></span>|  
|<span data-ttu-id="505d2-140">Basic192</span><span class="sxs-lookup"><span data-stu-id="505d2-140">Basic192</span></span>|<span data-ttu-id="505d2-141">Verwendet Basic192-Verschlüsselung, Sha1 für den Nachrichtenhash und Rsa-oaep-mgf1p für Key Wrap.</span><span class="sxs-lookup"><span data-stu-id="505d2-141">Use Basic192 encryption, Sha1 for message digest, Rsa-oaep-mgf1p for key wrap.</span></span>|  
|<span data-ttu-id="505d2-142">Basic256</span><span class="sxs-lookup"><span data-stu-id="505d2-142">Basic256</span></span>|<span data-ttu-id="505d2-143">Verwendet Basic256-Verschlüsselung, Sha1 für den Nachrichtenhash und Rsa-oaep-mgf1p für Key Wrap.</span><span class="sxs-lookup"><span data-stu-id="505d2-143">Use Basic256 encryption, Sha1 for message digest, Rsa-oaep-mgf1p for key wrap.</span></span>|  
|<span data-ttu-id="505d2-144">Basic256Rsa15</span><span class="sxs-lookup"><span data-stu-id="505d2-144">Basic256Rsa15</span></span>|<span data-ttu-id="505d2-145">Verwendet Basic256 für die Nachrichtenverschlüsselung, Sha1 für den Nachrichtenhash und Rsa15 für Key Wrap.</span><span class="sxs-lookup"><span data-stu-id="505d2-145">Use Basic256 for message encryption, Sha1 for message digest and Rsa15 for key wrap.</span></span>|  
|<span data-ttu-id="505d2-146">Basic192Rsa15</span><span class="sxs-lookup"><span data-stu-id="505d2-146">Basic192Rsa15</span></span>|<span data-ttu-id="505d2-147">Verwendet Basic192 für die Nachrichtenverschlüsselung, Sha1 für den Nachrichtenhash und Rsa15 für Key Wrap.</span><span class="sxs-lookup"><span data-stu-id="505d2-147">Use Basic192 for message encryption, Sha1 for message digest and Rsa15 for key wrap.</span></span>|  
|<span data-ttu-id="505d2-148">TripleDes</span><span class="sxs-lookup"><span data-stu-id="505d2-148">TripleDes</span></span>|<span data-ttu-id="505d2-149">Verwendet TripleDes-Verschlüsselung, Sha1 für den Nachrichtenhash und Rsa-oaep-mgf1p für Key Wrap.</span><span class="sxs-lookup"><span data-stu-id="505d2-149">Use TripleDes encryption, Sha1 for message digest, Rsa-oaep-mgf1p for key wrap.</span></span>|  
|<span data-ttu-id="505d2-150">Basic128Rsa15</span><span class="sxs-lookup"><span data-stu-id="505d2-150">Basic128Rsa15</span></span>|<span data-ttu-id="505d2-151">Verwendet Basic128 für die Nachrichtenverschlüsselung, Sha1 für den Nachrichtenhash und Rsa15 für Key Wrap.</span><span class="sxs-lookup"><span data-stu-id="505d2-151">Use Basic128 for message encryption, Sha1 for message digest and Rsa15 for key wrap.</span></span>|  
|<span data-ttu-id="505d2-152">TripleDesRsa15</span><span class="sxs-lookup"><span data-stu-id="505d2-152">TripleDesRsa15</span></span>|<span data-ttu-id="505d2-153">Verwendet TripleDes-Verschlüsselung, Sha1 für den Nachrichtenhash und Rsa15 für Key Wrap.</span><span class="sxs-lookup"><span data-stu-id="505d2-153">Use TripleDes encryption, Sha1 for message digest and Rsa15 for key wrap.</span></span>|  
|<span data-ttu-id="505d2-154">Basic128Sha256</span><span class="sxs-lookup"><span data-stu-id="505d2-154">Basic128Sha256</span></span>|<span data-ttu-id="505d2-155">Verwendet Basic128 für die Nachrichtenverschlüsselung, Sha256 für den Nachrichtenhash und Rsa-oaep-mgf1p für Key Wrap.</span><span class="sxs-lookup"><span data-stu-id="505d2-155">Use Basic128 for message encryption, Sha256 for message digest and Rsa-oaep-mgf1p for key wrap.</span></span>|  
|<span data-ttu-id="505d2-156">Basic192Sha256</span><span class="sxs-lookup"><span data-stu-id="505d2-156">Basic192Sha256</span></span>|<span data-ttu-id="505d2-157">Verwendet Basic192 für die Nachrichtenverschlüsselung, Sha256 für den Nachrichtenhash und Rsa-oaep-mgf1p für Key Wrap.</span><span class="sxs-lookup"><span data-stu-id="505d2-157">Use Basic192 for message encryption, Sha256 for message digest and Rsa-oaep-mgf1p for key wrap.</span></span>|  
|<span data-ttu-id="505d2-158">Basic256Sha256</span><span class="sxs-lookup"><span data-stu-id="505d2-158">Basic256Sha256</span></span>|<span data-ttu-id="505d2-159">Verwendet Basic256 für die Nachrichtenverschlüsselung, Sha256 für den Nachrichtenhash und Rsa-oaep-mgf1p für Key Wrap.</span><span class="sxs-lookup"><span data-stu-id="505d2-159">Use Basic256 for message encryption, Sha256 for message digest and Rsa-oaep-mgf1p for key wrap.</span></span>|  
|<span data-ttu-id="505d2-160">TripleDesSha256</span><span class="sxs-lookup"><span data-stu-id="505d2-160">TripleDesSha256</span></span>|<span data-ttu-id="505d2-161">Verwendet TripleDes für die Nachrichtenverschlüsselung, Sha256 für den Nachrichtenhash und Rsa-oaep-mgf1p für Key Wrap.</span><span class="sxs-lookup"><span data-stu-id="505d2-161">Use TripleDes for message encryption, Sha256 for message digest and Rsa-oaep-mgf1p for key wrap.</span></span>|  
|<span data-ttu-id="505d2-162">Basic128Sha256Rsa15</span><span class="sxs-lookup"><span data-stu-id="505d2-162">Basic128Sha256Rsa15</span></span>|<span data-ttu-id="505d2-163">Verwendet Basic128 für die Nachrichtenverschlüsselung, Sha256 für den Nachrichtenhash und Rsa15 für Key Wrap.</span><span class="sxs-lookup"><span data-stu-id="505d2-163">Use Basic128 for message encryption, Sha256 for message digest and Rsa15 for key wrap.</span></span>|  
|<span data-ttu-id="505d2-164">Basic192Sha256Rsa15</span><span class="sxs-lookup"><span data-stu-id="505d2-164">Basic192Sha256Rsa15</span></span>|<span data-ttu-id="505d2-165">Verwendet Aes192 für die Nachrichtenverschlüsselung, Sha256 für den Nachrichtenhash und Rsa15 für Key Wrap.</span><span class="sxs-lookup"><span data-stu-id="505d2-165">Use Aes192 for message encryption, Sha256 for message digest and Rsa15 for key wrap.</span></span>|  
|<span data-ttu-id="505d2-166">Basic256Sha256Rsa15</span><span class="sxs-lookup"><span data-stu-id="505d2-166">Basic256Sha256Rsa15</span></span>|<span data-ttu-id="505d2-167">Verwendet Basic256 für die Nachrichtenverschlüsselung, Sha256 für den Nachrichtenhash und Rsa15 für Key Wrap.</span><span class="sxs-lookup"><span data-stu-id="505d2-167">Use Basic256 for message encryption, Sha256 for message digest and Rsa15 for key wrap.</span></span>|  
|<span data-ttu-id="505d2-168">TripleDesSha256Rsa15</span><span class="sxs-lookup"><span data-stu-id="505d2-168">TripleDesSha256Rsa15</span></span>|<span data-ttu-id="505d2-169">Verwendet TripleDes für die Nachrichtenverschlüsselung, Sha256 für den Nachrichtenhash und Rsa15 für Key Wrap.</span><span class="sxs-lookup"><span data-stu-id="505d2-169">Use TripleDes for message encryption, Sha256 for message digest and Rsa15 for key wrap.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="505d2-170">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="505d2-170">Child Elements</span></span>  
  
|<span data-ttu-id="505d2-171">Element</span><span class="sxs-lookup"><span data-stu-id="505d2-171">Element</span></span>|<span data-ttu-id="505d2-172">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="505d2-172">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="505d2-173">\<ClaimTypeRequirements ></span><span class="sxs-lookup"><span data-stu-id="505d2-173">\<claimTypeRequirements></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/claimtyperequirements-element.md)|<span data-ttu-id="505d2-174">Gibt eine Auflistung von Anspruchstypen für diese Bindung an.</span><span class="sxs-lookup"><span data-stu-id="505d2-174">Specifies a collection of claim types for this binding.</span></span> <span data-ttu-id="505d2-175">Jedes Element ist vom Typ <xref:System.ServiceModel.Configuration.ClaimTypeElement>.</span><span class="sxs-lookup"><span data-stu-id="505d2-175">Each element is of type <xref:System.ServiceModel.Configuration.ClaimTypeElement>.</span></span>|  
|<span data-ttu-id="505d2-176">issuer</span><span class="sxs-lookup"><span data-stu-id="505d2-176">issuer</span></span>|<span data-ttu-id="505d2-177">Gibt einen Endpunkt an, der ein Sicherheitstoken ausstellt.</span><span class="sxs-lookup"><span data-stu-id="505d2-177">Specifies an endpoint that issues a security token.</span></span> <span data-ttu-id="505d2-178">Dieses Element ist vom Typ <xref:System.ServiceModel.Configuration.IssuedTokenParametersEndpointAddressElement>.</span><span class="sxs-lookup"><span data-stu-id="505d2-178">This element is of type <xref:System.ServiceModel.Configuration.IssuedTokenParametersEndpointAddressElement>.</span></span>|  
|<span data-ttu-id="505d2-179">issuerMetadata</span><span class="sxs-lookup"><span data-stu-id="505d2-179">issuerMetadata</span></span>|<span data-ttu-id="505d2-180">Gibt die Endpunktadresse des Ausstellers an.</span><span class="sxs-lookup"><span data-stu-id="505d2-180">Specifies the endpoint address of the issuer.</span></span>|  
|[<span data-ttu-id="505d2-181">\<TokenRequestParameters ></span><span class="sxs-lookup"><span data-stu-id="505d2-181">\<tokenRequestParameters></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/tokenrequestparameters.md)|<span data-ttu-id="505d2-182">Eine Auflistung von Tokenanforderungsparametern.</span><span class="sxs-lookup"><span data-stu-id="505d2-182">A collection of token request parameters.</span></span> <span data-ttu-id="505d2-183">Jeder Parameter ist ein XML-Element.</span><span class="sxs-lookup"><span data-stu-id="505d2-183">Each parameter is an XML element.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="505d2-184">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="505d2-184">Parent Elements</span></span>  
  
|<span data-ttu-id="505d2-185">Element</span><span class="sxs-lookup"><span data-stu-id="505d2-185">Element</span></span>|<span data-ttu-id="505d2-186">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="505d2-186">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="505d2-187">\<Sicherheit ></span><span class="sxs-lookup"><span data-stu-id="505d2-187">\<security></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/security-of-wsfederationhttpbinding.md)|<span data-ttu-id="505d2-188">Definiert die Sicherheitseinstellungen für eine Bindung.</span><span class="sxs-lookup"><span data-stu-id="505d2-188">Defines the security settings for a binding.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="505d2-189">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="505d2-189">See Also</span></span>  
 <xref:System.ServiceModel.FederatedMessageSecurityOverHttp>  
 <xref:System.ServiceModel.Configuration.WSFederationHttpSecurityElement.Message%2A>  
 <xref:System.ServiceModel.WSFederationHttpSecurity.Message%2A>  
 <span data-ttu-id="505d2-190">`System.ServiceModel.Configuration.FederatedMessageSecurityElement`[Sichern von Diensten und Clients](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)</span><span class="sxs-lookup"><span data-stu-id="505d2-190">`System.ServiceModel.Configuration.FederatedMessageSecurityElement` [Securing Services and Clients](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)</span></span>  
 [<span data-ttu-id="505d2-191">Bindungen</span><span class="sxs-lookup"><span data-stu-id="505d2-191">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)  
 [<span data-ttu-id="505d2-192">Konfigurieren der vom System bereitgestellte Bindungen</span><span class="sxs-lookup"><span data-stu-id="505d2-192">Configuring System-Provided Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)  
 [<span data-ttu-id="505d2-193">Verwenden von Bindungen, um Windows Communication Foundation-Dienste und Clients konfigurieren</span><span class="sxs-lookup"><span data-stu-id="505d2-193">Using Bindings to Configure Windows Communication Foundation Services and Clients</span></span>](http://msdn.microsoft.com/en-us/bd8b277b-932f-472f-a42a-b02bb5257dfb)  
 [<span data-ttu-id="505d2-194">\<Binden von ></span><span class="sxs-lookup"><span data-stu-id="505d2-194">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)
