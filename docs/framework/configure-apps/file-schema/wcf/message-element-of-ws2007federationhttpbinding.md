---
title: '&lt;message&gt;-Element von &lt;ws2007FederationHttpBinding&gt;'
ms.date: 03/30/2017
ms.assetid: 52cd941d-e230-4c82-8b29-333a7d20eca8
ms.openlocfilehash: 3f0dbc3128af812c7fd09eed5acd90ab43ec8351
ms.sourcegitcommit: 3ab9254890a52a50762995fa6d7d77a00348db7e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/20/2018
ms.locfileid: "46471589"
---
# <a name="ltmessagegt-element-of-ltws2007federationhttpbindinggt"></a><span data-ttu-id="a9936-102">&lt;message&gt;-Element von &lt;ws2007FederationHttpBinding&gt;</span><span class="sxs-lookup"><span data-stu-id="a9936-102">&lt;message&gt; element of &lt;ws2007FederationHttpBinding&gt;</span></span>
<span data-ttu-id="a9936-103">Definiert die Einstellungen für die Sicherheit auf Nachrichtenebene für die [ \<ws2007FederationHttpBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/ws2007federationhttpbinding.md) Element.</span><span class="sxs-lookup"><span data-stu-id="a9936-103">Defines settings for the message-level security for the [\<ws2007FederationHttpBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/ws2007federationhttpbinding.md) element.</span></span>  
  
 <span data-ttu-id="a9936-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="a9936-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="a9936-105">\<bindings></span><span class="sxs-lookup"><span data-stu-id="a9936-105">\<bindings></span></span>  
<span data-ttu-id="a9936-106">\<ws2007FederationHttpBinding></span><span class="sxs-lookup"><span data-stu-id="a9936-106">\<ws2007FederationHttpBinding></span></span>  
<span data-ttu-id="a9936-107">\<binding></span><span class="sxs-lookup"><span data-stu-id="a9936-107">\<binding></span></span>  
<span data-ttu-id="a9936-108">\<Sicherheit ></span><span class="sxs-lookup"><span data-stu-id="a9936-108">\<security></span></span>  
<span data-ttu-id="a9936-109">\<Meldung ></span><span class="sxs-lookup"><span data-stu-id="a9936-109">\<message></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a9936-110">Syntax</span><span class="sxs-lookup"><span data-stu-id="a9936-110">Syntax</span></span>  
  
```xml  
<ws2007FederationBinding>  
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
</ws2007FederationBinding>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="a9936-111">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="a9936-111">Attributes and Elements</span></span>  
 <span data-ttu-id="a9936-112">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="a9936-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="a9936-113">Attribute</span><span class="sxs-lookup"><span data-stu-id="a9936-113">Attributes</span></span>  
  
|<span data-ttu-id="a9936-114">Attribut</span><span class="sxs-lookup"><span data-stu-id="a9936-114">Attribute</span></span>|<span data-ttu-id="a9936-115">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="a9936-115">Description</span></span>|  
|---------------|-----------------|  
|`algorithmSuite`|<span data-ttu-id="a9936-116">Dies ist optional.</span><span class="sxs-lookup"><span data-stu-id="a9936-116">Optional.</span></span> <span data-ttu-id="a9936-117">Legt die Nachrichtenverschlüsselung, Signatur und Key Wrap-Algorithmen fest.</span><span class="sxs-lookup"><span data-stu-id="a9936-117">Sets the message encryption, signature, and key-wrap algorithms.</span></span> <span data-ttu-id="a9936-118">Die Algorithmen und die Schlüsselgröße werden durch die <xref:System.ServiceModel.Security.SecurityAlgorithmSuite>-Klasse ermittelt.</span><span class="sxs-lookup"><span data-stu-id="a9936-118">The algorithms and the key sizes are determined by the <xref:System.ServiceModel.Security.SecurityAlgorithmSuite> class.</span></span> <span data-ttu-id="a9936-119">Diese Algorithmen entsprechen den in der Security Policy Language (WS-SecurityPolicy)-Spezifikation angegebenen Algorithmen.</span><span class="sxs-lookup"><span data-stu-id="a9936-119">These algorithms map to those specified in the Security Policy Language (WS-SecurityPolicy) specification.</span></span><br /><br /> <span data-ttu-id="a9936-120">In der folgenden Tabelle sind die möglichen Werte aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="a9936-120">See the following table for possible values.</span></span> <span data-ttu-id="a9936-121">Der Standardwert ist Basic256.</span><span class="sxs-lookup"><span data-stu-id="a9936-121">The default value is Basic256.</span></span>|  
|`issuedKeyType`|<span data-ttu-id="a9936-122">Gibt den Typ des auszustellenden Schlüssels an.</span><span class="sxs-lookup"><span data-stu-id="a9936-122">Specifies the type of key to be issued.</span></span> <span data-ttu-id="a9936-123">Folgende Werte sind gültig:</span><span class="sxs-lookup"><span data-stu-id="a9936-123">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="a9936-124">-"SymmetricKey"</span><span class="sxs-lookup"><span data-stu-id="a9936-124">-   SymmetricKey</span></span><br /><span data-ttu-id="a9936-125">: Öffentlicher Schlüssel</span><span class="sxs-lookup"><span data-stu-id="a9936-125">-   PublicKey</span></span><br /><span data-ttu-id="a9936-126">-BearerKey</span><span class="sxs-lookup"><span data-stu-id="a9936-126">-   BearerKey</span></span><br /><br /> <span data-ttu-id="a9936-127">Der Standardwert ist SymmetricKey.</span><span class="sxs-lookup"><span data-stu-id="a9936-127">The default is SymmetricKey.</span></span> <span data-ttu-id="a9936-128">Dieses Attribut ist vom Typ <xref:System.IdentityModel.Tokens.SecurityKeyType>.</span><span class="sxs-lookup"><span data-stu-id="a9936-128">This attribute is of type <xref:System.IdentityModel.Tokens.SecurityKeyType>.</span></span>|  
|`issuedTokenType`|<span data-ttu-id="a9936-129">Ein URI, der den Typ des auszustellenden Tokens angibt.</span><span class="sxs-lookup"><span data-stu-id="a9936-129">A URI that specifies the type of token to be issued.</span></span> <span data-ttu-id="a9936-130">Die Standardeinstellung ist `null`.</span><span class="sxs-lookup"><span data-stu-id="a9936-130">The default is `null`.</span></span>|  
|`negotiateServiceCredential`|<span data-ttu-id="a9936-131">Ein Wert, der angibt, ob die Dienstanmeldeinformationen als Teil der Aushandlung ausgetauscht werden sollen oder ob sie out-of-band zur Verfügung stehen.</span><span class="sxs-lookup"><span data-stu-id="a9936-131">A value that specifies whether the service credential should be exchanged as part of negotiation or is available out of band.</span></span> <span data-ttu-id="a9936-132">Der Standardwert ist `true`, was bedeutet, dass die Dienstanmeldeinformationen ausgehandelt werden.</span><span class="sxs-lookup"><span data-stu-id="a9936-132">The default is `true`, which means that the service credential is negotiated.</span></span>|  
  
## <a name="algorithmsuite-attribute"></a><span data-ttu-id="a9936-133">algorithmSuite-Attribut</span><span class="sxs-lookup"><span data-stu-id="a9936-133">algorithmSuite Attribute</span></span>  
  
|<span data-ttu-id="a9936-134">Wert</span><span class="sxs-lookup"><span data-stu-id="a9936-134">Value</span></span>|<span data-ttu-id="a9936-135">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="a9936-135">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="a9936-136">Basic128</span><span class="sxs-lookup"><span data-stu-id="a9936-136">Basic128</span></span>|<span data-ttu-id="a9936-137">Verwendet Aes128-Verschlüsselung, Sha1 für den Nachrichtenhash und Rsa-oaep-mgf1p für Key Wrap.</span><span class="sxs-lookup"><span data-stu-id="a9936-137">Use Aes128 encryption, Sha1 for message digest, and Rsa-oaep-mgf1p for key wrap.</span></span>|  
|<span data-ttu-id="a9936-138">Basic192</span><span class="sxs-lookup"><span data-stu-id="a9936-138">Basic192</span></span>|<span data-ttu-id="a9936-139">Verwendet Aes192-Verschlüsselung, Sha1 für den Nachrichtenhash und Rsa-oaep-mgf1p für Key Wrap.</span><span class="sxs-lookup"><span data-stu-id="a9936-139">Use Aes192 encryption, Sha1 for message digest, Rsa-oaep-mgf1p for key wrap.</span></span>|  
|<span data-ttu-id="a9936-140">Basic256</span><span class="sxs-lookup"><span data-stu-id="a9936-140">Basic256</span></span>|<span data-ttu-id="a9936-141">Verwendet Aes256-Verschlüsselung, Sha1 für den Nachrichtenhash und Rsa-oaep-mgf1p für Key Wrap.</span><span class="sxs-lookup"><span data-stu-id="a9936-141">Use Aes256 encryption, Sha1 for message digest, Rsa-oaep-mgf1p for key wrap.</span></span>|  
|<span data-ttu-id="a9936-142">Basic256Rsa15</span><span class="sxs-lookup"><span data-stu-id="a9936-142">Basic256Rsa15</span></span>|<span data-ttu-id="a9936-143">Verwendet Aes256-Nachrichtenverschlüsselung, Sha1 für den Nachrichtenhash und Rsa15 für Key Wrap.</span><span class="sxs-lookup"><span data-stu-id="a9936-143">Use Aes256 for message encryption, Sha1 for message digest and Rsa15 for key wrap.</span></span>|  
|<span data-ttu-id="a9936-144">Basic192Rsa15</span><span class="sxs-lookup"><span data-stu-id="a9936-144">Basic192Rsa15</span></span>|<span data-ttu-id="a9936-145">Verwendet Aes192 für die Nachrichtenverschlüsselung, Sha1 für den Nachrichtenhash und Rsa15 für Key Wrap.</span><span class="sxs-lookup"><span data-stu-id="a9936-145">Use Aes192 for message encryption, Sha1 for message digest and Rsa15 for key wrap.</span></span>|  
|<span data-ttu-id="a9936-146">TripleDes</span><span class="sxs-lookup"><span data-stu-id="a9936-146">TripleDes</span></span>|<span data-ttu-id="a9936-147">Verwendet TripleDes-Verschlüsselung, Sha1 für den Nachrichtenhash und Rsa-oaep-mgf1p für Key Wrap.</span><span class="sxs-lookup"><span data-stu-id="a9936-147">Use TripleDes encryption, Sha1 for message digest, Rsa-oaep-mgf1p for key wrap.</span></span>|  
|<span data-ttu-id="a9936-148">Basic128Rsa15</span><span class="sxs-lookup"><span data-stu-id="a9936-148">Basic128Rsa15</span></span>|<span data-ttu-id="a9936-149">Verwendet Aes128 für die Nachrichtenverschlüsselung, Sha1 für den Nachrichtenhash und Rsa15 für Key Wrap.</span><span class="sxs-lookup"><span data-stu-id="a9936-149">Use Aes128 for message encryption, Sha1 for message digest and Rsa15 for key wrap.</span></span>|  
|<span data-ttu-id="a9936-150">TripleDesRsa15</span><span class="sxs-lookup"><span data-stu-id="a9936-150">TripleDesRsa15</span></span>|<span data-ttu-id="a9936-151">Verwendet TripleDes-Verschlüsselung, Sha1 für den Nachrichtenhash und Rsa15 für Key Wrap.</span><span class="sxs-lookup"><span data-stu-id="a9936-151">Use TripleDes encryption, Sha1 for message digest and Rsa15 for key wrap.</span></span>|  
|<span data-ttu-id="a9936-152">Basic128Sha256</span><span class="sxs-lookup"><span data-stu-id="a9936-152">Basic128Sha256</span></span>|<span data-ttu-id="a9936-153">Verwendet Aes256-Nachrichtenverschlüsselung, Sha256 für den Nachrichtenhash und Rsa-oaep-mgf1p für Key Wrap.</span><span class="sxs-lookup"><span data-stu-id="a9936-153">Use Aes256 for message encryption, Sha256 for message digest and Rsa-oaep-mgf1p for key wrap.</span></span>|  
|<span data-ttu-id="a9936-154">Basic192Sha256</span><span class="sxs-lookup"><span data-stu-id="a9936-154">Basic192Sha256</span></span>|<span data-ttu-id="a9936-155">Verwendet Aes192 für die Nachrichtenverschlüsselung, Sha256 für den Nachrichtenhash und Rsa-oaep-mgf1p für Key Wrap.</span><span class="sxs-lookup"><span data-stu-id="a9936-155">Use Aes192 for message encryption, Sha256 for message digest and Rsa-oaep-mgf1p for key wrap.</span></span>|  
|<span data-ttu-id="a9936-156">Basic256Sha256</span><span class="sxs-lookup"><span data-stu-id="a9936-156">Basic256Sha256</span></span>|<span data-ttu-id="a9936-157">Verwendet Aes256-Nachrichtenverschlüsselung, Sha256 für den Nachrichtenhash und Rsa-oaep-mgf1p für Key Wrap.</span><span class="sxs-lookup"><span data-stu-id="a9936-157">Use Aes256 for message encryption, Sha256 for message digest and Rsa-oaep-mgf1p for key wrap.</span></span>|  
|<span data-ttu-id="a9936-158">TripleDesSha256</span><span class="sxs-lookup"><span data-stu-id="a9936-158">TripleDesSha256</span></span>|<span data-ttu-id="a9936-159">Verwendet TripleDes für die Nachrichtenverschlüsselung, Sha256 für den Nachrichtenhash und Rsa-oaep-mgf1p für Key Wrap.</span><span class="sxs-lookup"><span data-stu-id="a9936-159">Use TripleDes for message encryption, Sha256 for message digest and Rsa-oaep-mgf1p for key wrap.</span></span>|  
|<span data-ttu-id="a9936-160">Basic128Sha256Rsa15</span><span class="sxs-lookup"><span data-stu-id="a9936-160">Basic128Sha256Rsa15</span></span>|<span data-ttu-id="a9936-161">Verwendet Aes128 für die Nachrichtenverschlüsselung, Sha256 für den Nachrichtenhash und Rsa15 für Key Wrap.</span><span class="sxs-lookup"><span data-stu-id="a9936-161">Use Aes128 for message encryption, Sha256 for message digest and Rsa15 for key wrap.</span></span>|  
|<span data-ttu-id="a9936-162">Basic192Sha256Rsa15</span><span class="sxs-lookup"><span data-stu-id="a9936-162">Basic192Sha256Rsa15</span></span>|<span data-ttu-id="a9936-163">Verwendet Aes192 für die Nachrichtenverschlüsselung, Sha256 für den Nachrichtenhash und Rsa15 für Key Wrap.</span><span class="sxs-lookup"><span data-stu-id="a9936-163">Use Aes192 for message encryption, Sha256 for message digest and Rsa15 for key wrap.</span></span>|  
|<span data-ttu-id="a9936-164">Basic256Sha256Rsa15</span><span class="sxs-lookup"><span data-stu-id="a9936-164">Basic256Sha256Rsa15</span></span>|<span data-ttu-id="a9936-165">Verwendet Aes256 für die Nachrichtenverschlüsselung, Sha256 für den Nachrichtenhash und Rsa15 für Key Wrap.</span><span class="sxs-lookup"><span data-stu-id="a9936-165">Use Aes256 for message encryption, Sha256 for message digest and Rsa15 for key wrap.</span></span>|  
|<span data-ttu-id="a9936-166">TripleDesSha256Rsa15</span><span class="sxs-lookup"><span data-stu-id="a9936-166">TripleDesSha256Rsa15</span></span>|<span data-ttu-id="a9936-167">Verwendet TripleDes für die Nachrichtenverschlüsselung, Sha256 für den Nachrichtenhash und Rsa15 für Key Wrap.</span><span class="sxs-lookup"><span data-stu-id="a9936-167">Use TripleDes for message encryption, Sha256 for message digest and Rsa15 for key wrap.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="a9936-168">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="a9936-168">Child Elements</span></span>  
  
|<span data-ttu-id="a9936-169">Element</span><span class="sxs-lookup"><span data-stu-id="a9936-169">Element</span></span>|<span data-ttu-id="a9936-170">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="a9936-170">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="a9936-171">\<claimTypeRequirements></span><span class="sxs-lookup"><span data-stu-id="a9936-171">\<claimTypeRequirements></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/claimtyperequirements-element.md)|<span data-ttu-id="a9936-172">Gibt eine Auflistung von Anspruchstypen für diese Bindung an.</span><span class="sxs-lookup"><span data-stu-id="a9936-172">Specifies a collection of claim types for this binding.</span></span> <span data-ttu-id="a9936-173">Jedes Element ist vom Typ <xref:System.ServiceModel.Configuration.ClaimTypeElement>.</span><span class="sxs-lookup"><span data-stu-id="a9936-173">Each element is of type <xref:System.ServiceModel.Configuration.ClaimTypeElement>.</span></span>|  
|[<span data-ttu-id="a9936-174">\<issuer></span><span class="sxs-lookup"><span data-stu-id="a9936-174">\<issuer></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/issuer.md)|<span data-ttu-id="a9936-175">Gibt einen Endpunkt an, der ein Sicherheitstoken ausstellt.</span><span class="sxs-lookup"><span data-stu-id="a9936-175">Specifies an endpoint that issues a security token.</span></span> <span data-ttu-id="a9936-176">Dieses Element ist vom Typ <xref:System.ServiceModel.Configuration.IssuedTokenParametersEndpointAddressElement>.</span><span class="sxs-lookup"><span data-stu-id="a9936-176">This element is of type <xref:System.ServiceModel.Configuration.IssuedTokenParametersEndpointAddressElement>.</span></span>|  
|[<span data-ttu-id="a9936-177">\<issuerMetadata></span><span class="sxs-lookup"><span data-stu-id="a9936-177">\<issuerMetadata></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/issuermetadata.md)|<span data-ttu-id="a9936-178">Gibt die Endpunktadresse des Ausstellers an.</span><span class="sxs-lookup"><span data-stu-id="a9936-178">Specifies the endpoint address of the issuer.</span></span>|  
|[<span data-ttu-id="a9936-179">\<tokenRequestParameters></span><span class="sxs-lookup"><span data-stu-id="a9936-179">\<tokenRequestParameters></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/tokenrequestparameters.md)|<span data-ttu-id="a9936-180">Eine Auflistung von Tokenanforderungsparametern.</span><span class="sxs-lookup"><span data-stu-id="a9936-180">A collection of token request parameters.</span></span> <span data-ttu-id="a9936-181">Jeder Parameter ist ein XML-Element.</span><span class="sxs-lookup"><span data-stu-id="a9936-181">Each parameter is an XML element.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="a9936-182">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="a9936-182">Parent Elements</span></span>  
  
|<span data-ttu-id="a9936-183">Element</span><span class="sxs-lookup"><span data-stu-id="a9936-183">Element</span></span>|<span data-ttu-id="a9936-184">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="a9936-184">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="a9936-185">\<security></span><span class="sxs-lookup"><span data-stu-id="a9936-185">\<security></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/security-element-of-ws2007federationhttpbinding.md)|<span data-ttu-id="a9936-186">Definiert die Sicherheitseinstellungen für eine Bindung.</span><span class="sxs-lookup"><span data-stu-id="a9936-186">Defines the security settings for a binding.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="a9936-187">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a9936-187">See Also</span></span>  
 <xref:System.ServiceModel.FederatedMessageSecurityOverHttp>  
 <xref:System.ServiceModel.Configuration.WSFederationHttpSecurityElement.Message%2A>  
 <xref:System.ServiceModel.WSFederationHttpSecurity.Message%2A>  
 <span data-ttu-id="a9936-188">`System.ServiceModel.Configuration.FederatedMessageSecurityElement` [Sichern von Diensten und Clients](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)</span><span class="sxs-lookup"><span data-stu-id="a9936-188">`System.ServiceModel.Configuration.FederatedMessageSecurityElement` [Securing Services and Clients](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)</span></span>  
 [<span data-ttu-id="a9936-189">Bindungen</span><span class="sxs-lookup"><span data-stu-id="a9936-189">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)  
 [<span data-ttu-id="a9936-190">Konfigurieren der vom System bereitgestellten Bindungen</span><span class="sxs-lookup"><span data-stu-id="a9936-190">Configuring System-Provided Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)  
 [<span data-ttu-id="a9936-191">Verwenden von Bindungen, um Windows Communication Foundation-Dienste und Clients konfigurieren</span><span class="sxs-lookup"><span data-stu-id="a9936-191">Using Bindings to Configure Windows Communication Foundation Services and Clients</span></span>](https://msdn.microsoft.com/library/bd8b277b-932f-472f-a42a-b02bb5257dfb)  
 [<span data-ttu-id="a9936-192">\<binding></span><span class="sxs-lookup"><span data-stu-id="a9936-192">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)
