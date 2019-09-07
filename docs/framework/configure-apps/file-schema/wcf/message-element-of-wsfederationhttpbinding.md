---
title: <message>Element von<wsFederationHttpBinding>
ms.date: 03/30/2017
ms.assetid: 9d710389-d9d8-4454-9bf2-da4ccda31cec
ms.openlocfilehash: e26e1f94fb38e0654fd0bc9f06c6096a488bccfe
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/06/2019
ms.locfileid: "70400284"
---
# <a name="message-element-of-wsfederationhttpbinding"></a><span data-ttu-id="a90e3-102">\<Message >-Element \<von WSFederationHttpBinding ></span><span class="sxs-lookup"><span data-stu-id="a90e3-102">\<message> element of \<wsFederationHttpBinding></span></span>
<span data-ttu-id="a90e3-103">Definiert die Einstellungen für die Sicherheit auf Nachrichten Ebene für die [ \<WSFederationHttpBinding->](wsfederationhttpbinding.md).</span><span class="sxs-lookup"><span data-stu-id="a90e3-103">Defines the settings for the message-level security for the [\<wsFederationHttpBinding>](wsfederationhttpbinding.md).</span></span>  
  
<span data-ttu-id="a90e3-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="a90e3-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="a90e3-105">&nbsp;&nbsp;[ **\<System. Service Model->** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="a90e3-105">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="a90e3-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Bindungen >** ](bindings.md)</span><span class="sxs-lookup"><span data-stu-id="a90e3-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)</span></span>\
<span data-ttu-id="a90e3-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<WSFederationHttpBinding->** ](wsfederationhttpbinding.md)</span><span class="sxs-lookup"><span data-stu-id="a90e3-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<wsFederationHttpBinding>**](wsfederationhttpbinding.md)</span></span>\
<span data-ttu-id="a90e3-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<Bindungs >** </span><span class="sxs-lookup"><span data-stu-id="a90e3-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**</span></span>\
<span data-ttu-id="a90e3-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Sicherheits >** ](security-of-wsfederationhttpbinding.md)</span><span class="sxs-lookup"><span data-stu-id="a90e3-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<security>**](security-of-wsfederationhttpbinding.md)</span></span>\
<span data-ttu-id="a90e3-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<Message >**</span><span class="sxs-lookup"><span data-stu-id="a90e3-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<message>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a90e3-111">Syntax</span><span class="sxs-lookup"><span data-stu-id="a90e3-111">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="a90e3-112">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="a90e3-112">Attributes and Elements</span></span>  
 <span data-ttu-id="a90e3-113">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="a90e3-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="a90e3-114">Attribute</span><span class="sxs-lookup"><span data-stu-id="a90e3-114">Attributes</span></span>  
  
|<span data-ttu-id="a90e3-115">Attribut</span><span class="sxs-lookup"><span data-stu-id="a90e3-115">Attribute</span></span>|<span data-ttu-id="a90e3-116">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="a90e3-116">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="a90e3-117">algorithmSuite</span><span class="sxs-lookup"><span data-stu-id="a90e3-117">algorithmSuite</span></span>|<span data-ttu-id="a90e3-118">Legt die Nachrichtenverschlüsselungs- und Key Wrap-Algorithmen fest.</span><span class="sxs-lookup"><span data-stu-id="a90e3-118">Sets the message encryption and key-wrap algorithms.</span></span> <span data-ttu-id="a90e3-119">In der Tabelle "algorithmSuite-Attribut" sind die für dieses Attribut gültigen Werte zusammengestellt.</span><span class="sxs-lookup"><span data-stu-id="a90e3-119">See the "algorithmSuite attribute" table for valid values of this attribute.</span></span> <span data-ttu-id="a90e3-120">Der Standardwert ist `Basic256`.</span><span class="sxs-lookup"><span data-stu-id="a90e3-120">The default value is `Basic256`.</span></span><br /><br /> <span data-ttu-id="a90e3-121">Dieses Attribut ist vom Typ <xref:System.ServiceModel.Security.SecurityAlgorithmSuite>.</span><span class="sxs-lookup"><span data-stu-id="a90e3-121">This attribute is of type <xref:System.ServiceModel.Security.SecurityAlgorithmSuite>.</span></span> <span data-ttu-id="a90e3-122">Diese Algorithmen entsprechen den in der Security Policy Language (WS-SecurityPolicy)-Spezifikation angegebenen Algorithmen.</span><span class="sxs-lookup"><span data-stu-id="a90e3-122">These algorithms map to those specified in the Security Policy Language (WS-SecurityPolicy) specification.</span></span>|  
|<span data-ttu-id="a90e3-123">issuedKeyType</span><span class="sxs-lookup"><span data-stu-id="a90e3-123">issuedKeyType</span></span>|<span data-ttu-id="a90e3-124">Gibt den Typ des auszustellenden Schlüssels an.</span><span class="sxs-lookup"><span data-stu-id="a90e3-124">Specifies the type of key to be issued.</span></span> <span data-ttu-id="a90e3-125">Folgende Werte sind gültig:</span><span class="sxs-lookup"><span data-stu-id="a90e3-125">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="a90e3-126">-SymmetricKey</span><span class="sxs-lookup"><span data-stu-id="a90e3-126">-   SymmetricKey</span></span><br /><span data-ttu-id="a90e3-127">-PublicKey</span><span class="sxs-lookup"><span data-stu-id="a90e3-127">-   PublicKey</span></span><br /><br /> <span data-ttu-id="a90e3-128">Die Standardeinstellung ist `SymmetricKey`.</span><span class="sxs-lookup"><span data-stu-id="a90e3-128">The default is `SymmetricKey`.</span></span> <span data-ttu-id="a90e3-129">Dieses Attribut ist vom Typ <xref:System.IdentityModel.Tokens.SecurityKeyType>.</span><span class="sxs-lookup"><span data-stu-id="a90e3-129">This attribute is of type <xref:System.IdentityModel.Tokens.SecurityKeyType>.</span></span>|  
|<span data-ttu-id="a90e3-130">issuedTokenType</span><span class="sxs-lookup"><span data-stu-id="a90e3-130">issuedTokenType</span></span>|<span data-ttu-id="a90e3-131">Eine Zeichenfolge mit einem URI, die den Typ des auszustellenden Tokens angibt.</span><span class="sxs-lookup"><span data-stu-id="a90e3-131">A string that contains a URI that specifies the type of token to be issued.</span></span> <span data-ttu-id="a90e3-132">Die Standardeinstellung ist `null`.</span><span class="sxs-lookup"><span data-stu-id="a90e3-132">The default is `null`.</span></span>|  
|<span data-ttu-id="a90e3-133">negotiateServiceCredential</span><span class="sxs-lookup"><span data-stu-id="a90e3-133">negotiateServiceCredential</span></span>|<span data-ttu-id="a90e3-134">Ein boolescher Wert, der angibt, ob die Dienstanmeldeinformationen als Teil der Aushandlung ausgetauscht werden sollen oder ob sie out-of-band zur Verfügung stehen.</span><span class="sxs-lookup"><span data-stu-id="a90e3-134">A Boolean value that specifies whether the service credential should be exchanged as part of negotiation or is available out of band.</span></span> <span data-ttu-id="a90e3-135">Der Standardwert ist `true`, was bedeutet, dass die Dienstanmeldeinformationen ausgehandelt werden.</span><span class="sxs-lookup"><span data-stu-id="a90e3-135">The default is `true`, which means that the service credential is negotiated.</span></span>|  
  
## <a name="algorithmsuite-attribute"></a><span data-ttu-id="a90e3-136">algorithmSuite-Attribut</span><span class="sxs-lookup"><span data-stu-id="a90e3-136">algorithmSuite Attribute</span></span>  
  
|<span data-ttu-id="a90e3-137">Wert</span><span class="sxs-lookup"><span data-stu-id="a90e3-137">Value</span></span>|<span data-ttu-id="a90e3-138">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="a90e3-138">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="a90e3-139">Basic128</span><span class="sxs-lookup"><span data-stu-id="a90e3-139">Basic128</span></span>|<span data-ttu-id="a90e3-140">Verwendet Basic128-Verschlüsselung, Sha1 für den Nachrichtenhash und Rsa-oaep-mgf1p für Key Wrap.</span><span class="sxs-lookup"><span data-stu-id="a90e3-140">Use Basic128 encryption, Sha1 for message digest, and Rsa-oaep-mgf1p for key wrap.</span></span>|  
|<span data-ttu-id="a90e3-141">Basic192</span><span class="sxs-lookup"><span data-stu-id="a90e3-141">Basic192</span></span>|<span data-ttu-id="a90e3-142">Verwendet Basic192-Verschlüsselung, Sha1 für den Nachrichtenhash und Rsa-oaep-mgf1p für Key Wrap.</span><span class="sxs-lookup"><span data-stu-id="a90e3-142">Use Basic192 encryption, Sha1 for message digest, Rsa-oaep-mgf1p for key wrap.</span></span>|  
|<span data-ttu-id="a90e3-143">Basic256</span><span class="sxs-lookup"><span data-stu-id="a90e3-143">Basic256</span></span>|<span data-ttu-id="a90e3-144">Verwendet Basic256-Verschlüsselung, Sha1 für den Nachrichtenhash und Rsa-oaep-mgf1p für Key Wrap.</span><span class="sxs-lookup"><span data-stu-id="a90e3-144">Use Basic256 encryption, Sha1 for message digest, Rsa-oaep-mgf1p for key wrap.</span></span>|  
|<span data-ttu-id="a90e3-145">Basic256Rsa15</span><span class="sxs-lookup"><span data-stu-id="a90e3-145">Basic256Rsa15</span></span>|<span data-ttu-id="a90e3-146">Verwendet Basic256 für die Nachrichtenverschlüsselung, Sha1 für den Nachrichtenhash und Rsa15 für Key Wrap.</span><span class="sxs-lookup"><span data-stu-id="a90e3-146">Use Basic256 for message encryption, Sha1 for message digest and Rsa15 for key wrap.</span></span>|  
|<span data-ttu-id="a90e3-147">Basic192Rsa15</span><span class="sxs-lookup"><span data-stu-id="a90e3-147">Basic192Rsa15</span></span>|<span data-ttu-id="a90e3-148">Verwendet Basic192 für die Nachrichtenverschlüsselung, Sha1 für den Nachrichtenhash und Rsa15 für Key Wrap.</span><span class="sxs-lookup"><span data-stu-id="a90e3-148">Use Basic192 for message encryption, Sha1 for message digest and Rsa15 for key wrap.</span></span>|  
|<span data-ttu-id="a90e3-149">TripleDes</span><span class="sxs-lookup"><span data-stu-id="a90e3-149">TripleDes</span></span>|<span data-ttu-id="a90e3-150">Verwendet TripleDes-Verschlüsselung, Sha1 für den Nachrichtenhash und Rsa-oaep-mgf1p für Key Wrap.</span><span class="sxs-lookup"><span data-stu-id="a90e3-150">Use TripleDes encryption, Sha1 for message digest, Rsa-oaep-mgf1p for key wrap.</span></span>|  
|<span data-ttu-id="a90e3-151">Basic128Rsa15</span><span class="sxs-lookup"><span data-stu-id="a90e3-151">Basic128Rsa15</span></span>|<span data-ttu-id="a90e3-152">Verwendet Basic128 für die Nachrichtenverschlüsselung, Sha1 für den Nachrichtenhash und Rsa15 für Key Wrap.</span><span class="sxs-lookup"><span data-stu-id="a90e3-152">Use Basic128 for message encryption, Sha1 for message digest and Rsa15 for key wrap.</span></span>|  
|<span data-ttu-id="a90e3-153">TripleDesRsa15</span><span class="sxs-lookup"><span data-stu-id="a90e3-153">TripleDesRsa15</span></span>|<span data-ttu-id="a90e3-154">Verwendet TripleDes-Verschlüsselung, Sha1 für den Nachrichtenhash und Rsa15 für Key Wrap.</span><span class="sxs-lookup"><span data-stu-id="a90e3-154">Use TripleDes encryption, Sha1 for message digest and Rsa15 for key wrap.</span></span>|  
|<span data-ttu-id="a90e3-155">Basic128Sha256</span><span class="sxs-lookup"><span data-stu-id="a90e3-155">Basic128Sha256</span></span>|<span data-ttu-id="a90e3-156">Verwendet Basic128 für die Nachrichtenverschlüsselung, Sha256 für den Nachrichtenhash und Rsa-oaep-mgf1p für Key Wrap.</span><span class="sxs-lookup"><span data-stu-id="a90e3-156">Use Basic128 for message encryption, Sha256 for message digest and Rsa-oaep-mgf1p for key wrap.</span></span>|  
|<span data-ttu-id="a90e3-157">Basic192Sha256</span><span class="sxs-lookup"><span data-stu-id="a90e3-157">Basic192Sha256</span></span>|<span data-ttu-id="a90e3-158">Verwendet Basic192 für die Nachrichtenverschlüsselung, Sha256 für den Nachrichtenhash und Rsa-oaep-mgf1p für Key Wrap.</span><span class="sxs-lookup"><span data-stu-id="a90e3-158">Use Basic192 for message encryption, Sha256 for message digest and Rsa-oaep-mgf1p for key wrap.</span></span>|  
|<span data-ttu-id="a90e3-159">Basic256Sha256</span><span class="sxs-lookup"><span data-stu-id="a90e3-159">Basic256Sha256</span></span>|<span data-ttu-id="a90e3-160">Verwendet Basic256 für die Nachrichtenverschlüsselung, Sha256 für den Nachrichtenhash und Rsa-oaep-mgf1p für Key Wrap.</span><span class="sxs-lookup"><span data-stu-id="a90e3-160">Use Basic256 for message encryption, Sha256 for message digest and Rsa-oaep-mgf1p for key wrap.</span></span>|  
|<span data-ttu-id="a90e3-161">TripleDesSha256</span><span class="sxs-lookup"><span data-stu-id="a90e3-161">TripleDesSha256</span></span>|<span data-ttu-id="a90e3-162">Verwendet TripleDes für die Nachrichtenverschlüsselung, Sha256 für den Nachrichtenhash und Rsa-oaep-mgf1p für Key Wrap.</span><span class="sxs-lookup"><span data-stu-id="a90e3-162">Use TripleDes for message encryption, Sha256 for message digest and Rsa-oaep-mgf1p for key wrap.</span></span>|  
|<span data-ttu-id="a90e3-163">Basic128Sha256Rsa15</span><span class="sxs-lookup"><span data-stu-id="a90e3-163">Basic128Sha256Rsa15</span></span>|<span data-ttu-id="a90e3-164">Verwendet Basic128 für die Nachrichtenverschlüsselung, Sha256 für den Nachrichtenhash und Rsa15 für Key Wrap.</span><span class="sxs-lookup"><span data-stu-id="a90e3-164">Use Basic128 for message encryption, Sha256 for message digest and Rsa15 for key wrap.</span></span>|  
|<span data-ttu-id="a90e3-165">Basic192Sha256Rsa15</span><span class="sxs-lookup"><span data-stu-id="a90e3-165">Basic192Sha256Rsa15</span></span>|<span data-ttu-id="a90e3-166">Verwendet Aes192 für die Nachrichtenverschlüsselung, Sha256 für den Nachrichtenhash und Rsa15 für Key Wrap.</span><span class="sxs-lookup"><span data-stu-id="a90e3-166">Use Aes192 for message encryption, Sha256 for message digest and Rsa15 for key wrap.</span></span>|  
|<span data-ttu-id="a90e3-167">Basic256Sha256Rsa15</span><span class="sxs-lookup"><span data-stu-id="a90e3-167">Basic256Sha256Rsa15</span></span>|<span data-ttu-id="a90e3-168">Verwendet Basic256 für die Nachrichtenverschlüsselung, Sha256 für den Nachrichtenhash und Rsa15 für Key Wrap.</span><span class="sxs-lookup"><span data-stu-id="a90e3-168">Use Basic256 for message encryption, Sha256 for message digest and Rsa15 for key wrap.</span></span>|  
|<span data-ttu-id="a90e3-169">TripleDesSha256Rsa15</span><span class="sxs-lookup"><span data-stu-id="a90e3-169">TripleDesSha256Rsa15</span></span>|<span data-ttu-id="a90e3-170">Verwendet TripleDes für die Nachrichtenverschlüsselung, Sha256 für den Nachrichtenhash und Rsa15 für Key Wrap.</span><span class="sxs-lookup"><span data-stu-id="a90e3-170">Use TripleDes for message encryption, Sha256 for message digest and Rsa15 for key wrap.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="a90e3-171">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="a90e3-171">Child Elements</span></span>  
  
|<span data-ttu-id="a90e3-172">Element</span><span class="sxs-lookup"><span data-stu-id="a90e3-172">Element</span></span>|<span data-ttu-id="a90e3-173">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="a90e3-173">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="a90e3-174">\<claimTypeRequirements></span><span class="sxs-lookup"><span data-stu-id="a90e3-174">\<claimTypeRequirements></span></span>](claimtyperequirements-element.md)|<span data-ttu-id="a90e3-175">Gibt eine Auflistung von Anspruchstypen für diese Bindung an.</span><span class="sxs-lookup"><span data-stu-id="a90e3-175">Specifies a collection of claim types for this binding.</span></span> <span data-ttu-id="a90e3-176">Jedes Element ist vom Typ <xref:System.ServiceModel.Configuration.ClaimTypeElement>.</span><span class="sxs-lookup"><span data-stu-id="a90e3-176">Each element is of type <xref:System.ServiceModel.Configuration.ClaimTypeElement>.</span></span>|  
|<span data-ttu-id="a90e3-177">issuer</span><span class="sxs-lookup"><span data-stu-id="a90e3-177">issuer</span></span>|<span data-ttu-id="a90e3-178">Gibt einen Endpunkt an, der ein Sicherheitstoken ausstellt.</span><span class="sxs-lookup"><span data-stu-id="a90e3-178">Specifies an endpoint that issues a security token.</span></span> <span data-ttu-id="a90e3-179">Dieses Element ist vom Typ <xref:System.ServiceModel.Configuration.IssuedTokenParametersEndpointAddressElement>.</span><span class="sxs-lookup"><span data-stu-id="a90e3-179">This element is of type <xref:System.ServiceModel.Configuration.IssuedTokenParametersEndpointAddressElement>.</span></span>|  
|<span data-ttu-id="a90e3-180">issuerMetadata</span><span class="sxs-lookup"><span data-stu-id="a90e3-180">issuerMetadata</span></span>|<span data-ttu-id="a90e3-181">Gibt die Endpunktadresse des Ausstellers an.</span><span class="sxs-lookup"><span data-stu-id="a90e3-181">Specifies the endpoint address of the issuer.</span></span>|  
|[<span data-ttu-id="a90e3-182">\<tokenRequestParameters></span><span class="sxs-lookup"><span data-stu-id="a90e3-182">\<tokenRequestParameters></span></span>](tokenrequestparameters.md)|<span data-ttu-id="a90e3-183">Eine Auflistung von Tokenanforderungsparametern.</span><span class="sxs-lookup"><span data-stu-id="a90e3-183">A collection of token request parameters.</span></span> <span data-ttu-id="a90e3-184">Jeder Parameter ist ein XML-Element.</span><span class="sxs-lookup"><span data-stu-id="a90e3-184">Each parameter is an XML element.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="a90e3-185">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="a90e3-185">Parent Elements</span></span>  
  
|<span data-ttu-id="a90e3-186">Element</span><span class="sxs-lookup"><span data-stu-id="a90e3-186">Element</span></span>|<span data-ttu-id="a90e3-187">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="a90e3-187">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="a90e3-188">\<security></span><span class="sxs-lookup"><span data-stu-id="a90e3-188">\<security></span></span>](security-of-wsfederationhttpbinding.md)|<span data-ttu-id="a90e3-189">Definiert die Sicherheitseinstellungen für eine Bindung.</span><span class="sxs-lookup"><span data-stu-id="a90e3-189">Defines the security settings for a binding.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="a90e3-190">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a90e3-190">See also</span></span>

- <xref:System.ServiceModel.FederatedMessageSecurityOverHttp>
- <xref:System.ServiceModel.Configuration.WSFederationHttpSecurityElement.Message%2A>
- <xref:System.ServiceModel.WSFederationHttpSecurity.Message%2A>
- <xref:System.ServiceModel.Configuration.FederatedMessageSecurityOverHttpElement>
- [<span data-ttu-id="a90e3-191">Sichern von Diensten und Clients</span><span class="sxs-lookup"><span data-stu-id="a90e3-191">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="a90e3-192">Bindungen</span><span class="sxs-lookup"><span data-stu-id="a90e3-192">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="a90e3-193">Konfigurieren der vom System bereitgestellten Bindungen</span><span class="sxs-lookup"><span data-stu-id="a90e3-193">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="a90e3-194">Verwenden von Bindungen, um Dienste und Clients zu konfigurieren</span><span class="sxs-lookup"><span data-stu-id="a90e3-194">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [<span data-ttu-id="a90e3-195">\<binding></span><span class="sxs-lookup"><span data-stu-id="a90e3-195">\<binding></span></span>](../../../misc/binding.md)
