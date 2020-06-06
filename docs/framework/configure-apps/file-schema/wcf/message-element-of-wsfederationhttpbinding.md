---
title: <message>Element von<wsFederationHttpBinding>
ms.date: 03/30/2017
ms.assetid: 9d710389-d9d8-4454-9bf2-da4ccda31cec
ms.openlocfilehash: 8e0903dd1313e68e2de65730e129079199ebe2f2
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/06/2020
ms.locfileid: "73738980"
---
# <a name="message-element-of-wsfederationhttpbinding"></a><span data-ttu-id="5ee83-102">\<message>Element von\<wsFederationHttpBinding></span><span class="sxs-lookup"><span data-stu-id="5ee83-102">\<message> element of \<wsFederationHttpBinding></span></span>
<span data-ttu-id="5ee83-103">Definiert die Einstellungen für die Sicherheit auf Nachrichten Ebene für den [\<wsFederationHttpBinding>](wsfederationhttpbinding.md) .</span><span class="sxs-lookup"><span data-stu-id="5ee83-103">Defines the settings for the message-level security for the [\<wsFederationHttpBinding>](wsfederationhttpbinding.md).</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<wsFederationHttpBinding>**](wsfederationhttpbinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<security>**](security-of-wsfederationhttpbinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<message>**  
  
## <a name="syntax"></a><span data-ttu-id="5ee83-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="5ee83-104">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="5ee83-105">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="5ee83-105">Attributes and Elements</span></span>  
 <span data-ttu-id="5ee83-106">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="5ee83-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="5ee83-107">Attribute</span><span class="sxs-lookup"><span data-stu-id="5ee83-107">Attributes</span></span>  
  
|<span data-ttu-id="5ee83-108">attribute</span><span class="sxs-lookup"><span data-stu-id="5ee83-108">Attribute</span></span>|<span data-ttu-id="5ee83-109">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="5ee83-109">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="5ee83-110">algorithmSuite</span><span class="sxs-lookup"><span data-stu-id="5ee83-110">algorithmSuite</span></span>|<span data-ttu-id="5ee83-111">Legt die Nachrichtenverschlüsselungs- und Key Wrap-Algorithmen fest.</span><span class="sxs-lookup"><span data-stu-id="5ee83-111">Sets the message encryption and key-wrap algorithms.</span></span> <span data-ttu-id="5ee83-112">In der Tabelle "algorithmSuite-Attribut" sind die für dieses Attribut gültigen Werte zusammengestellt.</span><span class="sxs-lookup"><span data-stu-id="5ee83-112">See the "algorithmSuite attribute" table for valid values of this attribute.</span></span> <span data-ttu-id="5ee83-113">Der Standardwert ist `Basic256`.</span><span class="sxs-lookup"><span data-stu-id="5ee83-113">The default value is `Basic256`.</span></span><br /><br /> <span data-ttu-id="5ee83-114">Dieses Attribut ist vom Typ <xref:System.ServiceModel.Security.SecurityAlgorithmSuite>.</span><span class="sxs-lookup"><span data-stu-id="5ee83-114">This attribute is of type <xref:System.ServiceModel.Security.SecurityAlgorithmSuite>.</span></span> <span data-ttu-id="5ee83-115">Diese Algorithmen sind den Algorithmen in der Spezifikation der Sicherheitsrichtliniensprache (WS-SecurityPolicy) zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="5ee83-115">These algorithms map to those specified in the Security Policy Language (WS-SecurityPolicy) specification.</span></span>|  
|<span data-ttu-id="5ee83-116">issuedKeyType</span><span class="sxs-lookup"><span data-stu-id="5ee83-116">issuedKeyType</span></span>|<span data-ttu-id="5ee83-117">Gibt den Typ des auszustellenden Schlüssels an.</span><span class="sxs-lookup"><span data-stu-id="5ee83-117">Specifies the type of key to be issued.</span></span> <span data-ttu-id="5ee83-118">Gültige Werte sind:</span><span class="sxs-lookup"><span data-stu-id="5ee83-118">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="5ee83-119">-SymmetricKey</span><span class="sxs-lookup"><span data-stu-id="5ee83-119">-   SymmetricKey</span></span><br /><span data-ttu-id="5ee83-120">-PublicKey</span><span class="sxs-lookup"><span data-stu-id="5ee83-120">-   PublicKey</span></span><br /><br /> <span data-ttu-id="5ee83-121">Der Standardwert lautet `SymmetricKey`.</span><span class="sxs-lookup"><span data-stu-id="5ee83-121">The default is `SymmetricKey`.</span></span> <span data-ttu-id="5ee83-122">Dieses Attribut ist vom Typ <xref:System.IdentityModel.Tokens.SecurityKeyType>.</span><span class="sxs-lookup"><span data-stu-id="5ee83-122">This attribute is of type <xref:System.IdentityModel.Tokens.SecurityKeyType>.</span></span>|  
|<span data-ttu-id="5ee83-123">issuedTokenType</span><span class="sxs-lookup"><span data-stu-id="5ee83-123">issuedTokenType</span></span>|<span data-ttu-id="5ee83-124">Eine Zeichenfolge mit einem URI, die den Typ des auszustellenden Tokens angibt.</span><span class="sxs-lookup"><span data-stu-id="5ee83-124">A string that contains a URI that specifies the type of token to be issued.</span></span> <span data-ttu-id="5ee83-125">Der Standardwert lautet `null`.</span><span class="sxs-lookup"><span data-stu-id="5ee83-125">The default is `null`.</span></span>|  
|<span data-ttu-id="5ee83-126">negotiateServiceCredential</span><span class="sxs-lookup"><span data-stu-id="5ee83-126">negotiateServiceCredential</span></span>|<span data-ttu-id="5ee83-127">Ein boolescher Wert, der angibt, ob die Dienstanmeldeinformationen als Teil der Aushandlung ausgetauscht werden sollen oder ob sie out-of-band zur Verfügung stehen.</span><span class="sxs-lookup"><span data-stu-id="5ee83-127">A Boolean value that specifies whether the service credential should be exchanged as part of negotiation or is available out of band.</span></span> <span data-ttu-id="5ee83-128">Der Standardwert ist `true`, was bedeutet, dass die Dienstanmeldeinformationen ausgehandelt werden.</span><span class="sxs-lookup"><span data-stu-id="5ee83-128">The default is `true`, which means that the service credential is negotiated.</span></span>|  
  
## <a name="algorithmsuite-attribute"></a><span data-ttu-id="5ee83-129">algorithmSuite-Attribut</span><span class="sxs-lookup"><span data-stu-id="5ee83-129">algorithmSuite Attribute</span></span>  
  
|<span data-ttu-id="5ee83-130">Wert</span><span class="sxs-lookup"><span data-stu-id="5ee83-130">Value</span></span>|<span data-ttu-id="5ee83-131">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="5ee83-131">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="5ee83-132">Basic128</span><span class="sxs-lookup"><span data-stu-id="5ee83-132">Basic128</span></span>|<span data-ttu-id="5ee83-133">Verwendet Basic128-Verschlüsselung, Sha1 für den Nachrichtenhash und Rsa-oaep-mgf1p für Key Wrap.</span><span class="sxs-lookup"><span data-stu-id="5ee83-133">Use Basic128 encryption, Sha1 for message digest, and Rsa-oaep-mgf1p for key wrap.</span></span>|  
|<span data-ttu-id="5ee83-134">Basic192</span><span class="sxs-lookup"><span data-stu-id="5ee83-134">Basic192</span></span>|<span data-ttu-id="5ee83-135">Verwendet Basic192-Verschlüsselung, Sha1 für den Nachrichtenhash und Rsa-oaep-mgf1p für Key Wrap.</span><span class="sxs-lookup"><span data-stu-id="5ee83-135">Use Basic192 encryption, Sha1 for message digest, Rsa-oaep-mgf1p for key wrap.</span></span>|  
|<span data-ttu-id="5ee83-136">Basic256</span><span class="sxs-lookup"><span data-stu-id="5ee83-136">Basic256</span></span>|<span data-ttu-id="5ee83-137">Verwendet Basic256-Verschlüsselung, Sha1 für den Nachrichtenhash und Rsa-oaep-mgf1p für Key Wrap.</span><span class="sxs-lookup"><span data-stu-id="5ee83-137">Use Basic256 encryption, Sha1 for message digest, Rsa-oaep-mgf1p for key wrap.</span></span>|  
|<span data-ttu-id="5ee83-138">Basic256Rsa15</span><span class="sxs-lookup"><span data-stu-id="5ee83-138">Basic256Rsa15</span></span>|<span data-ttu-id="5ee83-139">Verwendet Basic256 für die Nachrichtenverschlüsselung, Sha1 für den Nachrichtenhash und Rsa15 für Key Wrap.</span><span class="sxs-lookup"><span data-stu-id="5ee83-139">Use Basic256 for message encryption, Sha1 for message digest and Rsa15 for key wrap.</span></span>|  
|<span data-ttu-id="5ee83-140">Basic192Rsa15</span><span class="sxs-lookup"><span data-stu-id="5ee83-140">Basic192Rsa15</span></span>|<span data-ttu-id="5ee83-141">Verwendet Basic192 für die Nachrichtenverschlüsselung, Sha1 für den Nachrichtenhash und Rsa15 für Key Wrap.</span><span class="sxs-lookup"><span data-stu-id="5ee83-141">Use Basic192 for message encryption, Sha1 for message digest and Rsa15 for key wrap.</span></span>|  
|<span data-ttu-id="5ee83-142">TripleDes</span><span class="sxs-lookup"><span data-stu-id="5ee83-142">TripleDes</span></span>|<span data-ttu-id="5ee83-143">Verwendet TripleDes-Verschlüsselung, Sha1 für den Nachrichtenhash und Rsa-oaep-mgf1p für Key Wrap.</span><span class="sxs-lookup"><span data-stu-id="5ee83-143">Use TripleDes encryption, Sha1 for message digest, Rsa-oaep-mgf1p for key wrap.</span></span>|  
|<span data-ttu-id="5ee83-144">Basic128Rsa15</span><span class="sxs-lookup"><span data-stu-id="5ee83-144">Basic128Rsa15</span></span>|<span data-ttu-id="5ee83-145">Verwendet Basic128 für die Nachrichtenverschlüsselung, Sha1 für den Nachrichtenhash und Rsa15 für Key Wrap.</span><span class="sxs-lookup"><span data-stu-id="5ee83-145">Use Basic128 for message encryption, Sha1 for message digest and Rsa15 for key wrap.</span></span>|  
|<span data-ttu-id="5ee83-146">TripleDesRsa15</span><span class="sxs-lookup"><span data-stu-id="5ee83-146">TripleDesRsa15</span></span>|<span data-ttu-id="5ee83-147">Verwendet TripleDes-Verschlüsselung, Sha1 für den Nachrichtenhash und Rsa15 für Key Wrap.</span><span class="sxs-lookup"><span data-stu-id="5ee83-147">Use TripleDes encryption, Sha1 for message digest and Rsa15 for key wrap.</span></span>|  
|<span data-ttu-id="5ee83-148">Basic128Sha256</span><span class="sxs-lookup"><span data-stu-id="5ee83-148">Basic128Sha256</span></span>|<span data-ttu-id="5ee83-149">Verwendet Basic128 für die Nachrichtenverschlüsselung, Sha256 für den Nachrichtenhash und Rsa-oaep-mgf1p für Key Wrap.</span><span class="sxs-lookup"><span data-stu-id="5ee83-149">Use Basic128 for message encryption, Sha256 for message digest and Rsa-oaep-mgf1p for key wrap.</span></span>|  
|<span data-ttu-id="5ee83-150">Basic192Sha256</span><span class="sxs-lookup"><span data-stu-id="5ee83-150">Basic192Sha256</span></span>|<span data-ttu-id="5ee83-151">Verwendet Basic192 für die Nachrichtenverschlüsselung, Sha256 für den Nachrichtenhash und Rsa-oaep-mgf1p für Key Wrap.</span><span class="sxs-lookup"><span data-stu-id="5ee83-151">Use Basic192 for message encryption, Sha256 for message digest and Rsa-oaep-mgf1p for key wrap.</span></span>|  
|<span data-ttu-id="5ee83-152">Basic256Sha256</span><span class="sxs-lookup"><span data-stu-id="5ee83-152">Basic256Sha256</span></span>|<span data-ttu-id="5ee83-153">Verwendet Basic256 für die Nachrichtenverschlüsselung, Sha256 für den Nachrichtenhash und Rsa-oaep-mgf1p für Key Wrap.</span><span class="sxs-lookup"><span data-stu-id="5ee83-153">Use Basic256 for message encryption, Sha256 for message digest and Rsa-oaep-mgf1p for key wrap.</span></span>|  
|<span data-ttu-id="5ee83-154">TripleDesSha256</span><span class="sxs-lookup"><span data-stu-id="5ee83-154">TripleDesSha256</span></span>|<span data-ttu-id="5ee83-155">Verwendet TripleDes für die Nachrichtenverschlüsselung, Sha256 für den Nachrichtenhash und Rsa-oaep-mgf1p für Key Wrap.</span><span class="sxs-lookup"><span data-stu-id="5ee83-155">Use TripleDes for message encryption, Sha256 for message digest and Rsa-oaep-mgf1p for key wrap.</span></span>|  
|<span data-ttu-id="5ee83-156">Basic128Sha256Rsa15</span><span class="sxs-lookup"><span data-stu-id="5ee83-156">Basic128Sha256Rsa15</span></span>|<span data-ttu-id="5ee83-157">Verwendet Basic128 für die Nachrichtenverschlüsselung, Sha256 für den Nachrichtenhash und Rsa15 für Key Wrap.</span><span class="sxs-lookup"><span data-stu-id="5ee83-157">Use Basic128 for message encryption, Sha256 for message digest and Rsa15 for key wrap.</span></span>|  
|<span data-ttu-id="5ee83-158">Basic192Sha256Rsa15</span><span class="sxs-lookup"><span data-stu-id="5ee83-158">Basic192Sha256Rsa15</span></span>|<span data-ttu-id="5ee83-159">Verwendet Aes192 für die Nachrichtenverschlüsselung, Sha256 für den Nachrichtenhash und Rsa15 für Key Wrap.</span><span class="sxs-lookup"><span data-stu-id="5ee83-159">Use Aes192 for message encryption, Sha256 for message digest and Rsa15 for key wrap.</span></span>|  
|<span data-ttu-id="5ee83-160">Basic256Sha256Rsa15</span><span class="sxs-lookup"><span data-stu-id="5ee83-160">Basic256Sha256Rsa15</span></span>|<span data-ttu-id="5ee83-161">Verwendet Basic256 für die Nachrichtenverschlüsselung, Sha256 für den Nachrichtenhash und Rsa15 für Key Wrap.</span><span class="sxs-lookup"><span data-stu-id="5ee83-161">Use Basic256 for message encryption, Sha256 for message digest and Rsa15 for key wrap.</span></span>|  
|<span data-ttu-id="5ee83-162">TripleDesSha256Rsa15</span><span class="sxs-lookup"><span data-stu-id="5ee83-162">TripleDesSha256Rsa15</span></span>|<span data-ttu-id="5ee83-163">Verwendet TripleDes für die Nachrichtenverschlüsselung, Sha256 für den Nachrichtenhash und Rsa15 für Key Wrap.</span><span class="sxs-lookup"><span data-stu-id="5ee83-163">Use TripleDes for message encryption, Sha256 for message digest and Rsa15 for key wrap.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="5ee83-164">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="5ee83-164">Child Elements</span></span>  
  
|<span data-ttu-id="5ee83-165">Element</span><span class="sxs-lookup"><span data-stu-id="5ee83-165">Element</span></span>|<span data-ttu-id="5ee83-166">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="5ee83-166">Description</span></span>|  
|-------------|-----------------|  
|[\<claimTypeRequirements>](claimtyperequirements-element.md)|<span data-ttu-id="5ee83-167">Gibt eine Auflistung von Anspruchstypen für diese Bindung an.</span><span class="sxs-lookup"><span data-stu-id="5ee83-167">Specifies a collection of claim types for this binding.</span></span> <span data-ttu-id="5ee83-168">Jedes Element ist vom Typ <xref:System.ServiceModel.Configuration.ClaimTypeElement>.</span><span class="sxs-lookup"><span data-stu-id="5ee83-168">Each element is of type <xref:System.ServiceModel.Configuration.ClaimTypeElement>.</span></span>|  
|<span data-ttu-id="5ee83-169">Issuer (Aussteller)</span><span class="sxs-lookup"><span data-stu-id="5ee83-169">issuer</span></span>|<span data-ttu-id="5ee83-170">Gibt einen Endpunkt an, der ein Sicherheitstoken ausstellt.</span><span class="sxs-lookup"><span data-stu-id="5ee83-170">Specifies an endpoint that issues a security token.</span></span> <span data-ttu-id="5ee83-171">Dieses Element ist vom Typ <xref:System.ServiceModel.Configuration.IssuedTokenParametersEndpointAddressElement>.</span><span class="sxs-lookup"><span data-stu-id="5ee83-171">This element is of type <xref:System.ServiceModel.Configuration.IssuedTokenParametersEndpointAddressElement>.</span></span>|  
|<span data-ttu-id="5ee83-172">issuerMetadata</span><span class="sxs-lookup"><span data-stu-id="5ee83-172">issuerMetadata</span></span>|<span data-ttu-id="5ee83-173">Gibt die Endpunktadresse des Ausstellers an.</span><span class="sxs-lookup"><span data-stu-id="5ee83-173">Specifies the endpoint address of the issuer.</span></span>|  
|[\<tokenRequestParameters>](tokenrequestparameters.md)|<span data-ttu-id="5ee83-174">Eine Auflistung von Tokenanforderungsparametern.</span><span class="sxs-lookup"><span data-stu-id="5ee83-174">A collection of token request parameters.</span></span> <span data-ttu-id="5ee83-175">Jeder Parameter ist ein XML-Element.</span><span class="sxs-lookup"><span data-stu-id="5ee83-175">Each parameter is an XML element.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="5ee83-176">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="5ee83-176">Parent Elements</span></span>  
  
|<span data-ttu-id="5ee83-177">Element</span><span class="sxs-lookup"><span data-stu-id="5ee83-177">Element</span></span>|<span data-ttu-id="5ee83-178">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="5ee83-178">Description</span></span>|  
|-------------|-----------------|  
|[\<security>](security-of-wsfederationhttpbinding.md)|<span data-ttu-id="5ee83-179">Definiert die Sicherheitseinstellungen für eine Bindung.</span><span class="sxs-lookup"><span data-stu-id="5ee83-179">Defines the security settings for a binding.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="5ee83-180">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="5ee83-180">See also</span></span>

- <xref:System.ServiceModel.FederatedMessageSecurityOverHttp>
- <xref:System.ServiceModel.Configuration.WSFederationHttpSecurityElement.Message%2A>
- <xref:System.ServiceModel.WSFederationHttpSecurity.Message%2A>
- <xref:System.ServiceModel.Configuration.FederatedMessageSecurityOverHttpElement>
- [<span data-ttu-id="5ee83-181">Sichern von Diensten und Clients</span><span class="sxs-lookup"><span data-stu-id="5ee83-181">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="5ee83-182">Bindungen</span><span class="sxs-lookup"><span data-stu-id="5ee83-182">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="5ee83-183">Konfigurieren der vom System bereitgestellten Bindungen</span><span class="sxs-lookup"><span data-stu-id="5ee83-183">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="5ee83-184">Verwenden von Bindungen, um Dienste und Clients zu konfigurieren</span><span class="sxs-lookup"><span data-stu-id="5ee83-184">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [\<binding>](bindings.md)
