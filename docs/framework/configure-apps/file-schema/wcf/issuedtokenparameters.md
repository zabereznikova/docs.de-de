---
title: '&lt;issuedTokenParameters&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 120b3f37-7331-4816-b712-d6aab39655a4
caps.latest.revision: "10"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: ef68585054d61de8c25b7e3effd1d72063d4589c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="ltissuedtokenparametersgt"></a><span data-ttu-id="6a708-102">&lt;issuedTokenParameters&gt;</span><span class="sxs-lookup"><span data-stu-id="6a708-102">&lt;issuedTokenParameters&gt;</span></span>
<span data-ttu-id="6a708-103">Gibt die Parameter für einen Sicherheitstoken an, der in einem verbundenen Sicherheitsszenario ausgegeben wird.</span><span class="sxs-lookup"><span data-stu-id="6a708-103">Specifies the parameters for a security token issued in a Federated security scenario.</span></span>  
  
 <span data-ttu-id="6a708-104">\<system.serviceModel ></span><span class="sxs-lookup"><span data-stu-id="6a708-104">\<system.serviceModel></span></span>  
<span data-ttu-id="6a708-105">\<Bindungen ></span><span class="sxs-lookup"><span data-stu-id="6a708-105">\<bindings></span></span>  
<span data-ttu-id="6a708-106">\<CustomBinding ></span><span class="sxs-lookup"><span data-stu-id="6a708-106">\<customBinding></span></span>  
<span data-ttu-id="6a708-107">\<Binden von ></span><span class="sxs-lookup"><span data-stu-id="6a708-107">\<binding></span></span>  
<span data-ttu-id="6a708-108">\<Sicherheit ></span><span class="sxs-lookup"><span data-stu-id="6a708-108">\<security></span></span>  
<span data-ttu-id="6a708-109">\<IssuedTokenParameters ></span><span class="sxs-lookup"><span data-stu-id="6a708-109">\<issuedTokenParameters></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6a708-110">Syntax</span><span class="sxs-lookup"><span data-stu-id="6a708-110">Syntax</span></span>  
  
```xml  
<issuedTokenParameters   
      DefaultMessageSecurityVersion="System.ServiceModel.MessageSecurityVersion"  
      inclusionMode="AlwaysToInitiator/AlwaysToRecipient/Never/Once"  
      keySize="Integer"  
   keyType="AsymmetricKey/BearerKey/SymmetricKey"  
      tokenType="String" >  
   <additionalRequestParameters />  
      <claimTypeRequirements>  
            <add claimType="URI"  
           isOptional="Boolean" />  
      </claimTypeRequirements>  
      <issuer address="String"   
                      binding=" " />  
      <issuerMetadata address="String" />   
</issuedTokenParameters>  
```  
  
## <a name="type"></a><span data-ttu-id="6a708-111">Typ</span><span class="sxs-lookup"><span data-stu-id="6a708-111">Type</span></span>  
 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="6a708-112">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="6a708-112">Attributes and Elements</span></span>  
 <span data-ttu-id="6a708-113">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="6a708-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="6a708-114">Attribute</span><span class="sxs-lookup"><span data-stu-id="6a708-114">Attributes</span></span>  
  
|<span data-ttu-id="6a708-115">Attribut</span><span class="sxs-lookup"><span data-stu-id="6a708-115">Attribute</span></span>|<span data-ttu-id="6a708-116">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="6a708-116">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="6a708-117">defaultMessageSecurityVersion</span><span class="sxs-lookup"><span data-stu-id="6a708-117">defaultMessageSecurityVersion</span></span>|<span data-ttu-id="6a708-118">Gibt die Versionen der Sicherheitsspezifikationen (WS-Security, WS-Trust, WS-Secure Conversation und WS-Security Policy) an, die von der Bindung unterstützt werden müssen.</span><span class="sxs-lookup"><span data-stu-id="6a708-118">Specifies the versions of the security specifications, (WS-Security, WS-Trust, WS-Secure Conversation and WS-Security Policy) that must be supported by the binding.</span></span> <span data-ttu-id="6a708-119">Dieser Wert ist vom Typ <xref:System.ServiceModel.MessageSecurityVersion>.</span><span class="sxs-lookup"><span data-stu-id="6a708-119">This value is of type <xref:System.ServiceModel.MessageSecurityVersion>.</span></span>|  
|<span data-ttu-id="6a708-120">inclusionMode</span><span class="sxs-lookup"><span data-stu-id="6a708-120">inclusionMode</span></span>|<span data-ttu-id="6a708-121">Gibt die Tokeneinschlussanforderungen an.</span><span class="sxs-lookup"><span data-stu-id="6a708-121">Specifies the token inclusion requirements.</span></span> <span data-ttu-id="6a708-122">Dieses Attribut ist vom Typ <xref:System.ServiceModel.Security.Tokens.SecurityTokenInclusionMode>.</span><span class="sxs-lookup"><span data-stu-id="6a708-122">This attribute is of type <xref:System.ServiceModel.Security.Tokens.SecurityTokenInclusionMode>.</span></span>|  
|<span data-ttu-id="6a708-123">keySize</span><span class="sxs-lookup"><span data-stu-id="6a708-123">keySize</span></span>|<span data-ttu-id="6a708-124">Eine ganze Zahl, die die Größe des Tokenschlüssels angibt.</span><span class="sxs-lookup"><span data-stu-id="6a708-124">An integer that specifies the token key size.</span></span> <span data-ttu-id="6a708-125">Der Standardwert ist 256.</span><span class="sxs-lookup"><span data-stu-id="6a708-125">The default value is 256.</span></span>|  
|<span data-ttu-id="6a708-126">keyType</span><span class="sxs-lookup"><span data-stu-id="6a708-126">keyType</span></span>|<span data-ttu-id="6a708-127">Ein gültiger Wert von <xref:System.IdentityModel.Tokens.SecurityKeyType>, der den Schlüsseltyp angibt.</span><span class="sxs-lookup"><span data-stu-id="6a708-127">A valid value of <xref:System.IdentityModel.Tokens.SecurityKeyType> that specifies the key type.</span></span> <span data-ttu-id="6a708-128">Die Standardeinstellung ist `SymmetricKey`.</span><span class="sxs-lookup"><span data-stu-id="6a708-128">The default is `SymmetricKey`.</span></span>|  
|<span data-ttu-id="6a708-129">tokenType</span><span class="sxs-lookup"><span data-stu-id="6a708-129">tokenType</span></span>|<span data-ttu-id="6a708-130">Eine Zeichenfolge, die den Tokentyp angibt.</span><span class="sxs-lookup"><span data-stu-id="6a708-130">A string that specifies the token type.</span></span> <span data-ttu-id="6a708-131">Der Standardwert lautet "http://docs.oasis-open.org/wss/oasis-wss-saml-token-profile-1.1#SAML".</span><span class="sxs-lookup"><span data-stu-id="6a708-131">The default is "http://docs.oasis-open.org/wss/oasis-wss-saml-token-profile-1.1#SAML".</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="6a708-132">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="6a708-132">Child Elements</span></span>  
  
|<span data-ttu-id="6a708-133">Element</span><span class="sxs-lookup"><span data-stu-id="6a708-133">Element</span></span>|<span data-ttu-id="6a708-134">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="6a708-134">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="6a708-135">\<AdditionalRequestParameters ></span><span class="sxs-lookup"><span data-stu-id="6a708-135">\<additionalRequestParameters></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/additionalrequestparameters-element.md)|<span data-ttu-id="6a708-136">Eine Auflistung von Konfigurationselementen, die zusätzliche Anforderungsparameter angeben.</span><span class="sxs-lookup"><span data-stu-id="6a708-136">A collection of configuration elements that specify additional request parameters.</span></span>|  
|[<span data-ttu-id="6a708-137">\<ClaimTypeRequirements ></span><span class="sxs-lookup"><span data-stu-id="6a708-137">\<claimTypeRequirements></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/claimtyperequirements-element.md)|<span data-ttu-id="6a708-138">Gibt eine Auflistung von erforderlichen Anspruchstypen an.</span><span class="sxs-lookup"><span data-stu-id="6a708-138">Specifies a collection of required claim types.</span></span><br /><br /> <span data-ttu-id="6a708-139">In einem verbundenen Szenario legen Dienste die Anforderungen für eingehende Anmeldeinformationen fest.</span><span class="sxs-lookup"><span data-stu-id="6a708-139">In a federated scenario, services state the requirements on incoming credentials.</span></span> <span data-ttu-id="6a708-140">Zum Beispiel müssen die eingehenden Anmeldeinformationen einen bestimmten Satz an Anspruchstypen aufweisen.</span><span class="sxs-lookup"><span data-stu-id="6a708-140">For example, the incoming credentials must possess a certain set of claim types.</span></span> <span data-ttu-id="6a708-141">Jedes Element in dieser Auflistung gibt die Typen der erforderlichen und optionalen Ansprüche an, die in verbundenen Anmeldeinformationen vorhanden sein sollen.</span><span class="sxs-lookup"><span data-stu-id="6a708-141">Each element in this collection specifies the types of required and optional claims expected to appear in a federated credential.</span></span>|  
|[<span data-ttu-id="6a708-142">\<Aussteller ></span><span class="sxs-lookup"><span data-stu-id="6a708-142">\<issuer></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/issuer-of-issuedtokenparameters.md)|<span data-ttu-id="6a708-143">Ein Konfigurationselement, das den Endpunkt angibt, der das aktuelle Token ausgibt.</span><span class="sxs-lookup"><span data-stu-id="6a708-143">A configuration element that specifies the endpoint that issues the current token.</span></span>|  
|[<span data-ttu-id="6a708-144">\<IssuerMetadata ></span><span class="sxs-lookup"><span data-stu-id="6a708-144">\<issuerMetadata></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/issuermetadata-of-issuedtokenparameters.md)|<span data-ttu-id="6a708-145">Ein Konfigurationselement, das die Endpunktadresse der Metadaten des Tokenausstellers angibt.</span><span class="sxs-lookup"><span data-stu-id="6a708-145">A configuration element that specifies the endpoint address of the token issuer's metadata.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="6a708-146">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="6a708-146">Parent Elements</span></span>  
  
|<span data-ttu-id="6a708-147">Element</span><span class="sxs-lookup"><span data-stu-id="6a708-147">Element</span></span>|<span data-ttu-id="6a708-148">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="6a708-148">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="6a708-149">\<SecureConversationBootstrap ></span><span class="sxs-lookup"><span data-stu-id="6a708-149">\<secureConversationBootstrap></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/secureconversationbootstrap.md)|<span data-ttu-id="6a708-150">Gibt die Standardwerte an, die zum Initiieren eines sicheren Konversationsdiensts verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="6a708-150">Specifies the default values used for initiating a secure conversation service.</span></span>|  
|[<span data-ttu-id="6a708-151">\<Sicherheit ></span><span class="sxs-lookup"><span data-stu-id="6a708-151">\<security></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md)|<span data-ttu-id="6a708-152">Gibt die Sicherheitsoptionen für eine benutzerdefinierte Bindung an.</span><span class="sxs-lookup"><span data-stu-id="6a708-152">Specifies the security options for a custom binding.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="6a708-153">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="6a708-153">See Also</span></span>  
 <xref:System.ServiceModel.Security.Tokens.IssuedSecurityTokenParameters>  
 <xref:System.ServiceModel.Configuration.IssuedTokenParametersElement>  
 <xref:System.ServiceModel.Configuration.SecurityElementBase.IssuedTokenParameters%2A>  
 <xref:System.ServiceModel.Channels.CustomBinding>  
 [<span data-ttu-id="6a708-154">Bindungen</span><span class="sxs-lookup"><span data-stu-id="6a708-154">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)  
 [<span data-ttu-id="6a708-155">Erweitern von Bindungen</span><span class="sxs-lookup"><span data-stu-id="6a708-155">Extending Bindings</span></span>](../../../../../docs/framework/wcf/extending/extending-bindings.md)  
 [<span data-ttu-id="6a708-156">Benutzerdefinierte Bindungen</span><span class="sxs-lookup"><span data-stu-id="6a708-156">Custom Bindings</span></span>](../../../../../docs/framework/wcf/extending/custom-bindings.md)  
 [<span data-ttu-id="6a708-157">\<CustomBinding ></span><span class="sxs-lookup"><span data-stu-id="6a708-157">\<customBinding></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)  
 [<span data-ttu-id="6a708-158">Vorgehensweise: Erstellen einer benutzerdefinierten Bindung mit dem SecurityBindingElement</span><span class="sxs-lookup"><span data-stu-id="6a708-158">How to: Create a Custom Binding Using the SecurityBindingElement</span></span>](../../../../../docs/framework/wcf/feature-details/how-to-create-a-custom-binding-using-the-securitybindingelement.md)  
 [<span data-ttu-id="6a708-159">Sicherheit mit benutzerdefinierten Bindungen</span><span class="sxs-lookup"><span data-stu-id="6a708-159">Custom Binding Security</span></span>](../../../../../docs/framework/wcf/samples/custom-binding-security.md)  
 [<span data-ttu-id="6a708-160">Dienstidentität und Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="6a708-160">Service Identity and Authentication</span></span>](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md)  
 [<span data-ttu-id="6a708-161">Verbund und ausgestellte Token</span><span class="sxs-lookup"><span data-stu-id="6a708-161">Federation and Issued Tokens</span></span>](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)  
 [<span data-ttu-id="6a708-162">Sicherheitsfunktionen mit benutzerdefinierten Bindungen</span><span class="sxs-lookup"><span data-stu-id="6a708-162">Security Capabilities with Custom Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/security-capabilities-with-custom-bindings.md)  
 [<span data-ttu-id="6a708-163">Verbund und ausgestellte Token</span><span class="sxs-lookup"><span data-stu-id="6a708-163">Federation and Issued Tokens</span></span>](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)
