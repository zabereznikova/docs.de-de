---
title: <message>Element von<ws2007FederationHttpBinding>
ms.date: 03/30/2017
ms.assetid: 52cd941d-e230-4c82-8b29-333a7d20eca8
ms.openlocfilehash: b1128bda6068a1fe3d8f5bb5ac29cc349f023b5b
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/06/2019
ms.locfileid: "70397847"
---
# <a name="message-element-of-ws2007federationhttpbinding"></a><span data-ttu-id="fa4f6-102">\<Message > Element von \<WS2007FederationHttpBinding ></span><span class="sxs-lookup"><span data-stu-id="fa4f6-102">\<message> element of \<ws2007FederationHttpBinding></span></span>
<span data-ttu-id="fa4f6-103">Definiert die Einstellungen für die Sicherheit auf Nachrichten Ebene für das [ \<WS2007FederationHttpBinding->](ws2007federationhttpbinding.md) Element.</span><span class="sxs-lookup"><span data-stu-id="fa4f6-103">Defines settings for the message-level security for the [\<ws2007FederationHttpBinding>](ws2007federationhttpbinding.md) element.</span></span>  
  
<span data-ttu-id="fa4f6-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="fa4f6-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="fa4f6-105">&nbsp;&nbsp;[ **\<System. Service Model->** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="fa4f6-105">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="fa4f6-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Bindungen >** ](bindings.md)</span><span class="sxs-lookup"><span data-stu-id="fa4f6-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)</span></span>\
<span data-ttu-id="fa4f6-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<WS2007FederationHttpBinding >** ](ws2007federationhttpbinding.md)</span><span class="sxs-lookup"><span data-stu-id="fa4f6-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<ws2007FederationHttpBinding>**](ws2007federationhttpbinding.md)</span></span>\
<span data-ttu-id="fa4f6-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<Bindungs >** </span><span class="sxs-lookup"><span data-stu-id="fa4f6-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**</span></span>\
<span data-ttu-id="fa4f6-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Sicherheits >** ](security-element-of-ws2007federationhttpbinding.md)</span><span class="sxs-lookup"><span data-stu-id="fa4f6-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<security>**](security-element-of-ws2007federationhttpbinding.md)</span></span>\
<span data-ttu-id="fa4f6-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<Message >**</span><span class="sxs-lookup"><span data-stu-id="fa4f6-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<message>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fa4f6-111">Syntax</span><span class="sxs-lookup"><span data-stu-id="fa4f6-111">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="fa4f6-112">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="fa4f6-112">Attributes and Elements</span></span>  
 <span data-ttu-id="fa4f6-113">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="fa4f6-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="fa4f6-114">Attribute</span><span class="sxs-lookup"><span data-stu-id="fa4f6-114">Attributes</span></span>  
  
|<span data-ttu-id="fa4f6-115">Attribut</span><span class="sxs-lookup"><span data-stu-id="fa4f6-115">Attribute</span></span>|<span data-ttu-id="fa4f6-116">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="fa4f6-116">Description</span></span>|  
|---------------|-----------------|  
|`algorithmSuite`|<span data-ttu-id="fa4f6-117">Optional.</span><span class="sxs-lookup"><span data-stu-id="fa4f6-117">Optional.</span></span> <span data-ttu-id="fa4f6-118">Legt die Nachrichtenverschlüsselung, Signatur und Key Wrap-Algorithmen fest.</span><span class="sxs-lookup"><span data-stu-id="fa4f6-118">Sets the message encryption, signature, and key-wrap algorithms.</span></span> <span data-ttu-id="fa4f6-119">Die Algorithmen und die Schlüsselgröße werden durch die <xref:System.ServiceModel.Security.SecurityAlgorithmSuite>-Klasse ermittelt.</span><span class="sxs-lookup"><span data-stu-id="fa4f6-119">The algorithms and the key sizes are determined by the <xref:System.ServiceModel.Security.SecurityAlgorithmSuite> class.</span></span> <span data-ttu-id="fa4f6-120">Diese Algorithmen entsprechen den in der Security Policy Language (WS-SecurityPolicy)-Spezifikation angegebenen Algorithmen.</span><span class="sxs-lookup"><span data-stu-id="fa4f6-120">These algorithms map to those specified in the Security Policy Language (WS-SecurityPolicy) specification.</span></span><br /><br /> <span data-ttu-id="fa4f6-121">In der folgenden Tabelle sind die möglichen Werte aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="fa4f6-121">See the following table for possible values.</span></span> <span data-ttu-id="fa4f6-122">Der Standardwert ist Basic256.</span><span class="sxs-lookup"><span data-stu-id="fa4f6-122">The default value is Basic256.</span></span>|  
|`issuedKeyType`|<span data-ttu-id="fa4f6-123">Gibt den Typ des auszustellenden Schlüssels an.</span><span class="sxs-lookup"><span data-stu-id="fa4f6-123">Specifies the type of key to be issued.</span></span> <span data-ttu-id="fa4f6-124">Folgende Werte sind gültig:</span><span class="sxs-lookup"><span data-stu-id="fa4f6-124">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="fa4f6-125">-SymmetricKey</span><span class="sxs-lookup"><span data-stu-id="fa4f6-125">-   SymmetricKey</span></span><br /><span data-ttu-id="fa4f6-126">-PublicKey</span><span class="sxs-lookup"><span data-stu-id="fa4f6-126">-   PublicKey</span></span><br /><span data-ttu-id="fa4f6-127">-Bearerkey</span><span class="sxs-lookup"><span data-stu-id="fa4f6-127">-   BearerKey</span></span><br /><br /> <span data-ttu-id="fa4f6-128">Der Standardwert ist SymmetricKey.</span><span class="sxs-lookup"><span data-stu-id="fa4f6-128">The default is SymmetricKey.</span></span> <span data-ttu-id="fa4f6-129">Dieses Attribut ist vom Typ <xref:System.IdentityModel.Tokens.SecurityKeyType>.</span><span class="sxs-lookup"><span data-stu-id="fa4f6-129">This attribute is of type <xref:System.IdentityModel.Tokens.SecurityKeyType>.</span></span>|  
|`issuedTokenType`|<span data-ttu-id="fa4f6-130">Ein URI, der den Typ des auszustellenden Tokens angibt.</span><span class="sxs-lookup"><span data-stu-id="fa4f6-130">A URI that specifies the type of token to be issued.</span></span> <span data-ttu-id="fa4f6-131">Die Standardeinstellung ist `null`.</span><span class="sxs-lookup"><span data-stu-id="fa4f6-131">The default is `null`.</span></span>|  
|`negotiateServiceCredential`|<span data-ttu-id="fa4f6-132">Ein Wert, der angibt, ob die Dienstanmeldeinformationen als Teil der Aushandlung ausgetauscht werden sollen oder ob sie out-of-band zur Verfügung stehen.</span><span class="sxs-lookup"><span data-stu-id="fa4f6-132">A value that specifies whether the service credential should be exchanged as part of negotiation or is available out of band.</span></span> <span data-ttu-id="fa4f6-133">Der Standardwert ist `true`, was bedeutet, dass die Dienstanmeldeinformationen ausgehandelt werden.</span><span class="sxs-lookup"><span data-stu-id="fa4f6-133">The default is `true`, which means that the service credential is negotiated.</span></span>|  
  
## <a name="algorithmsuite-attribute"></a><span data-ttu-id="fa4f6-134">algorithmSuite-Attribut</span><span class="sxs-lookup"><span data-stu-id="fa4f6-134">algorithmSuite Attribute</span></span>  
  
|<span data-ttu-id="fa4f6-135">Wert</span><span class="sxs-lookup"><span data-stu-id="fa4f6-135">Value</span></span>|<span data-ttu-id="fa4f6-136">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="fa4f6-136">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="fa4f6-137">Basic128</span><span class="sxs-lookup"><span data-stu-id="fa4f6-137">Basic128</span></span>|<span data-ttu-id="fa4f6-138">Verwendet Aes128-Verschlüsselung, Sha1 für den Nachrichtenhash und Rsa-oaep-mgf1p für Key Wrap.</span><span class="sxs-lookup"><span data-stu-id="fa4f6-138">Use Aes128 encryption, Sha1 for message digest, and Rsa-oaep-mgf1p for key wrap.</span></span>|  
|<span data-ttu-id="fa4f6-139">Basic192</span><span class="sxs-lookup"><span data-stu-id="fa4f6-139">Basic192</span></span>|<span data-ttu-id="fa4f6-140">Verwendet Aes192-Verschlüsselung, Sha1 für den Nachrichtenhash und Rsa-oaep-mgf1p für Key Wrap.</span><span class="sxs-lookup"><span data-stu-id="fa4f6-140">Use Aes192 encryption, Sha1 for message digest, Rsa-oaep-mgf1p for key wrap.</span></span>|  
|<span data-ttu-id="fa4f6-141">Basic256</span><span class="sxs-lookup"><span data-stu-id="fa4f6-141">Basic256</span></span>|<span data-ttu-id="fa4f6-142">Verwendet Aes256-Verschlüsselung, Sha1 für den Nachrichtenhash und Rsa-oaep-mgf1p für Key Wrap.</span><span class="sxs-lookup"><span data-stu-id="fa4f6-142">Use Aes256 encryption, Sha1 for message digest, Rsa-oaep-mgf1p for key wrap.</span></span>|  
|<span data-ttu-id="fa4f6-143">Basic256Rsa15</span><span class="sxs-lookup"><span data-stu-id="fa4f6-143">Basic256Rsa15</span></span>|<span data-ttu-id="fa4f6-144">Verwendet Aes256-Nachrichtenverschlüsselung, Sha1 für den Nachrichtenhash und Rsa15 für Key Wrap.</span><span class="sxs-lookup"><span data-stu-id="fa4f6-144">Use Aes256 for message encryption, Sha1 for message digest and Rsa15 for key wrap.</span></span>|  
|<span data-ttu-id="fa4f6-145">Basic192Rsa15</span><span class="sxs-lookup"><span data-stu-id="fa4f6-145">Basic192Rsa15</span></span>|<span data-ttu-id="fa4f6-146">Verwendet Aes192 für die Nachrichtenverschlüsselung, Sha1 für den Nachrichtenhash und Rsa15 für Key Wrap.</span><span class="sxs-lookup"><span data-stu-id="fa4f6-146">Use Aes192 for message encryption, Sha1 for message digest and Rsa15 for key wrap.</span></span>|  
|<span data-ttu-id="fa4f6-147">TripleDes</span><span class="sxs-lookup"><span data-stu-id="fa4f6-147">TripleDes</span></span>|<span data-ttu-id="fa4f6-148">Verwendet TripleDes-Verschlüsselung, Sha1 für den Nachrichtenhash und Rsa-oaep-mgf1p für Key Wrap.</span><span class="sxs-lookup"><span data-stu-id="fa4f6-148">Use TripleDes encryption, Sha1 for message digest, Rsa-oaep-mgf1p for key wrap.</span></span>|  
|<span data-ttu-id="fa4f6-149">Basic128Rsa15</span><span class="sxs-lookup"><span data-stu-id="fa4f6-149">Basic128Rsa15</span></span>|<span data-ttu-id="fa4f6-150">Verwendet Aes128 für die Nachrichtenverschlüsselung, Sha1 für den Nachrichtenhash und Rsa15 für Key Wrap.</span><span class="sxs-lookup"><span data-stu-id="fa4f6-150">Use Aes128 for message encryption, Sha1 for message digest and Rsa15 for key wrap.</span></span>|  
|<span data-ttu-id="fa4f6-151">TripleDesRsa15</span><span class="sxs-lookup"><span data-stu-id="fa4f6-151">TripleDesRsa15</span></span>|<span data-ttu-id="fa4f6-152">Verwendet TripleDes-Verschlüsselung, Sha1 für den Nachrichtenhash und Rsa15 für Key Wrap.</span><span class="sxs-lookup"><span data-stu-id="fa4f6-152">Use TripleDes encryption, Sha1 for message digest and Rsa15 for key wrap.</span></span>|  
|<span data-ttu-id="fa4f6-153">Basic128Sha256</span><span class="sxs-lookup"><span data-stu-id="fa4f6-153">Basic128Sha256</span></span>|<span data-ttu-id="fa4f6-154">Verwendet Aes256-Nachrichtenverschlüsselung, Sha256 für den Nachrichtenhash und Rsa-oaep-mgf1p für Key Wrap.</span><span class="sxs-lookup"><span data-stu-id="fa4f6-154">Use Aes256 for message encryption, Sha256 for message digest and Rsa-oaep-mgf1p for key wrap.</span></span>|  
|<span data-ttu-id="fa4f6-155">Basic192Sha256</span><span class="sxs-lookup"><span data-stu-id="fa4f6-155">Basic192Sha256</span></span>|<span data-ttu-id="fa4f6-156">Verwendet Aes192 für die Nachrichtenverschlüsselung, Sha256 für den Nachrichtenhash und Rsa-oaep-mgf1p für Key Wrap.</span><span class="sxs-lookup"><span data-stu-id="fa4f6-156">Use Aes192 for message encryption, Sha256 for message digest and Rsa-oaep-mgf1p for key wrap.</span></span>|  
|<span data-ttu-id="fa4f6-157">Basic256Sha256</span><span class="sxs-lookup"><span data-stu-id="fa4f6-157">Basic256Sha256</span></span>|<span data-ttu-id="fa4f6-158">Verwendet Aes256-Nachrichtenverschlüsselung, Sha256 für den Nachrichtenhash und Rsa-oaep-mgf1p für Key Wrap.</span><span class="sxs-lookup"><span data-stu-id="fa4f6-158">Use Aes256 for message encryption, Sha256 for message digest and Rsa-oaep-mgf1p for key wrap.</span></span>|  
|<span data-ttu-id="fa4f6-159">TripleDesSha256</span><span class="sxs-lookup"><span data-stu-id="fa4f6-159">TripleDesSha256</span></span>|<span data-ttu-id="fa4f6-160">Verwendet TripleDes für die Nachrichtenverschlüsselung, Sha256 für den Nachrichtenhash und Rsa-oaep-mgf1p für Key Wrap.</span><span class="sxs-lookup"><span data-stu-id="fa4f6-160">Use TripleDes for message encryption, Sha256 for message digest and Rsa-oaep-mgf1p for key wrap.</span></span>|  
|<span data-ttu-id="fa4f6-161">Basic128Sha256Rsa15</span><span class="sxs-lookup"><span data-stu-id="fa4f6-161">Basic128Sha256Rsa15</span></span>|<span data-ttu-id="fa4f6-162">Verwendet Aes128 für die Nachrichtenverschlüsselung, Sha256 für den Nachrichtenhash und Rsa15 für Key Wrap.</span><span class="sxs-lookup"><span data-stu-id="fa4f6-162">Use Aes128 for message encryption, Sha256 for message digest and Rsa15 for key wrap.</span></span>|  
|<span data-ttu-id="fa4f6-163">Basic192Sha256Rsa15</span><span class="sxs-lookup"><span data-stu-id="fa4f6-163">Basic192Sha256Rsa15</span></span>|<span data-ttu-id="fa4f6-164">Verwendet Aes192 für die Nachrichtenverschlüsselung, Sha256 für den Nachrichtenhash und Rsa15 für Key Wrap.</span><span class="sxs-lookup"><span data-stu-id="fa4f6-164">Use Aes192 for message encryption, Sha256 for message digest and Rsa15 for key wrap.</span></span>|  
|<span data-ttu-id="fa4f6-165">Basic256Sha256Rsa15</span><span class="sxs-lookup"><span data-stu-id="fa4f6-165">Basic256Sha256Rsa15</span></span>|<span data-ttu-id="fa4f6-166">Verwendet Aes256 für die Nachrichtenverschlüsselung, Sha256 für den Nachrichtenhash und Rsa15 für Key Wrap.</span><span class="sxs-lookup"><span data-stu-id="fa4f6-166">Use Aes256 for message encryption, Sha256 for message digest and Rsa15 for key wrap.</span></span>|  
|<span data-ttu-id="fa4f6-167">TripleDesSha256Rsa15</span><span class="sxs-lookup"><span data-stu-id="fa4f6-167">TripleDesSha256Rsa15</span></span>|<span data-ttu-id="fa4f6-168">Verwendet TripleDes für die Nachrichtenverschlüsselung, Sha256 für den Nachrichtenhash und Rsa15 für Key Wrap.</span><span class="sxs-lookup"><span data-stu-id="fa4f6-168">Use TripleDes for message encryption, Sha256 for message digest and Rsa15 for key wrap.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="fa4f6-169">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="fa4f6-169">Child Elements</span></span>  
  
|<span data-ttu-id="fa4f6-170">Element</span><span class="sxs-lookup"><span data-stu-id="fa4f6-170">Element</span></span>|<span data-ttu-id="fa4f6-171">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="fa4f6-171">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="fa4f6-172">\<claimTypeRequirements></span><span class="sxs-lookup"><span data-stu-id="fa4f6-172">\<claimTypeRequirements></span></span>](claimtyperequirements-element.md)|<span data-ttu-id="fa4f6-173">Gibt eine Auflistung von Anspruchstypen für diese Bindung an.</span><span class="sxs-lookup"><span data-stu-id="fa4f6-173">Specifies a collection of claim types for this binding.</span></span> <span data-ttu-id="fa4f6-174">Jedes Element ist vom Typ <xref:System.ServiceModel.Configuration.ClaimTypeElement>.</span><span class="sxs-lookup"><span data-stu-id="fa4f6-174">Each element is of type <xref:System.ServiceModel.Configuration.ClaimTypeElement>.</span></span>|  
|[<span data-ttu-id="fa4f6-175">\<issuer></span><span class="sxs-lookup"><span data-stu-id="fa4f6-175">\<issuer></span></span>](issuer.md)|<span data-ttu-id="fa4f6-176">Gibt einen Endpunkt an, der ein Sicherheitstoken ausstellt.</span><span class="sxs-lookup"><span data-stu-id="fa4f6-176">Specifies an endpoint that issues a security token.</span></span> <span data-ttu-id="fa4f6-177">Dieses Element ist vom Typ <xref:System.ServiceModel.Configuration.IssuedTokenParametersEndpointAddressElement>.</span><span class="sxs-lookup"><span data-stu-id="fa4f6-177">This element is of type <xref:System.ServiceModel.Configuration.IssuedTokenParametersEndpointAddressElement>.</span></span>|  
|[<span data-ttu-id="fa4f6-178">\<issuerMetadata></span><span class="sxs-lookup"><span data-stu-id="fa4f6-178">\<issuerMetadata></span></span>](issuermetadata.md)|<span data-ttu-id="fa4f6-179">Gibt die Endpunktadresse des Ausstellers an.</span><span class="sxs-lookup"><span data-stu-id="fa4f6-179">Specifies the endpoint address of the issuer.</span></span>|  
|[<span data-ttu-id="fa4f6-180">\<tokenRequestParameters></span><span class="sxs-lookup"><span data-stu-id="fa4f6-180">\<tokenRequestParameters></span></span>](tokenrequestparameters.md)|<span data-ttu-id="fa4f6-181">Eine Auflistung von Tokenanforderungsparametern.</span><span class="sxs-lookup"><span data-stu-id="fa4f6-181">A collection of token request parameters.</span></span> <span data-ttu-id="fa4f6-182">Jeder Parameter ist ein XML-Element.</span><span class="sxs-lookup"><span data-stu-id="fa4f6-182">Each parameter is an XML element.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="fa4f6-183">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="fa4f6-183">Parent Elements</span></span>  
  
|<span data-ttu-id="fa4f6-184">Element</span><span class="sxs-lookup"><span data-stu-id="fa4f6-184">Element</span></span>|<span data-ttu-id="fa4f6-185">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="fa4f6-185">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="fa4f6-186">\<security></span><span class="sxs-lookup"><span data-stu-id="fa4f6-186">\<security></span></span>](security-element-of-ws2007federationhttpbinding.md)|<span data-ttu-id="fa4f6-187">Definiert die Sicherheitseinstellungen für eine Bindung.</span><span class="sxs-lookup"><span data-stu-id="fa4f6-187">Defines the security settings for a binding.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="fa4f6-188">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="fa4f6-188">See also</span></span>

- <xref:System.ServiceModel.FederatedMessageSecurityOverHttp>
- <xref:System.ServiceModel.Configuration.WSFederationHttpSecurityElement.Message%2A>
- <xref:System.ServiceModel.WSFederationHttpSecurity.Message%2A>
- <xref:System.ServiceModel.Configuration.FederatedMessageSecurityOverHttpElement>
- [<span data-ttu-id="fa4f6-189">Sichern von Diensten und Clients</span><span class="sxs-lookup"><span data-stu-id="fa4f6-189">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="fa4f6-190">Bindungen</span><span class="sxs-lookup"><span data-stu-id="fa4f6-190">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="fa4f6-191">Konfigurieren der vom System bereitgestellten Bindungen</span><span class="sxs-lookup"><span data-stu-id="fa4f6-191">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="fa4f6-192">Verwenden von Bindungen, um Dienste und Clients zu konfigurieren</span><span class="sxs-lookup"><span data-stu-id="fa4f6-192">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [<span data-ttu-id="fa4f6-193">\<binding></span><span class="sxs-lookup"><span data-stu-id="fa4f6-193">\<binding></span></span>](../../../misc/binding.md)
