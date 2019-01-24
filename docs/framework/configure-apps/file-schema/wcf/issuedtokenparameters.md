---
title: '&lt;issuedTokenParameters&gt;'
ms.date: 03/30/2017
ms.assetid: 120b3f37-7331-4816-b712-d6aab39655a4
ms.openlocfilehash: d3770764e75b3bfd1345ac6a44761861595309d1
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54627459"
---
# <a name="ltissuedtokenparametersgt"></a><span data-ttu-id="a164b-102">&lt;issuedTokenParameters&gt;</span><span class="sxs-lookup"><span data-stu-id="a164b-102">&lt;issuedTokenParameters&gt;</span></span>
<span data-ttu-id="a164b-103">Gibt die Parameter für einen Sicherheitstoken an, der in einem verbundenen Sicherheitsszenario ausgegeben wird.</span><span class="sxs-lookup"><span data-stu-id="a164b-103">Specifies the parameters for a security token issued in a Federated security scenario.</span></span>  
  
 <span data-ttu-id="a164b-104">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="a164b-104">\<system.serviceModel></span></span>  
<span data-ttu-id="a164b-105">\<bindings></span><span class="sxs-lookup"><span data-stu-id="a164b-105">\<bindings></span></span>  
<span data-ttu-id="a164b-106">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="a164b-106">\<customBinding></span></span>  
<span data-ttu-id="a164b-107">\<binding></span><span class="sxs-lookup"><span data-stu-id="a164b-107">\<binding></span></span>  
<span data-ttu-id="a164b-108">\<security></span><span class="sxs-lookup"><span data-stu-id="a164b-108">\<security></span></span>  
<span data-ttu-id="a164b-109">\<issuedTokenParameters></span><span class="sxs-lookup"><span data-stu-id="a164b-109">\<issuedTokenParameters></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a164b-110">Syntax</span><span class="sxs-lookup"><span data-stu-id="a164b-110">Syntax</span></span>  
  
```xml  
<issuedTokenParameters defaultMessageSecurityVersion="System.ServiceModel.MessageSecurityVersion"
                       inclusionMode="AlwaysToInitiator/AlwaysToRecipient/Never/Once"
                       keySize="Integer"
                       keyType="AsymmetricKey/BearerKey/SymmetricKey"
                       tokenType="String">
  <additionalRequestParameters />
  <claimTypeRequirements>
    <add claimType="URI"
         isOptional="Boolean" />
  </claimTypeRequirements>
  <issuer address="String"
          binding="" />
  <issuerMetadata address="String" />
</issuedTokenParameters>
```  
  
## <a name="type"></a><span data-ttu-id="a164b-111">Typ</span><span class="sxs-lookup"><span data-stu-id="a164b-111">Type</span></span>  
 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="a164b-112">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="a164b-112">Attributes and Elements</span></span>  
 <span data-ttu-id="a164b-113">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="a164b-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="a164b-114">Attribute</span><span class="sxs-lookup"><span data-stu-id="a164b-114">Attributes</span></span>  
  
|<span data-ttu-id="a164b-115">Attribut</span><span class="sxs-lookup"><span data-stu-id="a164b-115">Attribute</span></span>|<span data-ttu-id="a164b-116">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="a164b-116">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="a164b-117">defaultMessageSecurityVersion</span><span class="sxs-lookup"><span data-stu-id="a164b-117">defaultMessageSecurityVersion</span></span>|<span data-ttu-id="a164b-118">Gibt die Versionen der Sicherheitsspezifikationen (WS-Security, WS-Trust, WS-Secure Conversation und WS-Security Policy) an, die von der Bindung unterstützt werden müssen.</span><span class="sxs-lookup"><span data-stu-id="a164b-118">Specifies the versions of the security specifications, (WS-Security, WS-Trust, WS-Secure Conversation and WS-Security Policy) that must be supported by the binding.</span></span> <span data-ttu-id="a164b-119">Dieser Wert ist vom Typ <xref:System.ServiceModel.MessageSecurityVersion>.</span><span class="sxs-lookup"><span data-stu-id="a164b-119">This value is of type <xref:System.ServiceModel.MessageSecurityVersion>.</span></span>|  
|<span data-ttu-id="a164b-120">inclusionMode</span><span class="sxs-lookup"><span data-stu-id="a164b-120">inclusionMode</span></span>|<span data-ttu-id="a164b-121">Gibt die Tokeneinschlussanforderungen an.</span><span class="sxs-lookup"><span data-stu-id="a164b-121">Specifies the token inclusion requirements.</span></span> <span data-ttu-id="a164b-122">Dieses Attribut ist vom Typ <xref:System.ServiceModel.Security.Tokens.SecurityTokenInclusionMode>.</span><span class="sxs-lookup"><span data-stu-id="a164b-122">This attribute is of type <xref:System.ServiceModel.Security.Tokens.SecurityTokenInclusionMode>.</span></span>|  
|<span data-ttu-id="a164b-123">keySize</span><span class="sxs-lookup"><span data-stu-id="a164b-123">keySize</span></span>|<span data-ttu-id="a164b-124">Eine ganze Zahl, die die Größe des Tokenschlüssels angibt.</span><span class="sxs-lookup"><span data-stu-id="a164b-124">An integer that specifies the token key size.</span></span> <span data-ttu-id="a164b-125">Der Standardwert ist 256.</span><span class="sxs-lookup"><span data-stu-id="a164b-125">The default value is 256.</span></span>|  
|<span data-ttu-id="a164b-126">keyType</span><span class="sxs-lookup"><span data-stu-id="a164b-126">keyType</span></span>|<span data-ttu-id="a164b-127">Ein gültiger Wert von <xref:System.IdentityModel.Tokens.SecurityKeyType>, der den Schlüsseltyp angibt.</span><span class="sxs-lookup"><span data-stu-id="a164b-127">A valid value of <xref:System.IdentityModel.Tokens.SecurityKeyType> that specifies the key type.</span></span> <span data-ttu-id="a164b-128">Die Standardeinstellung ist `SymmetricKey`.</span><span class="sxs-lookup"><span data-stu-id="a164b-128">The default is `SymmetricKey`.</span></span>|  
|<span data-ttu-id="a164b-129">tokenType</span><span class="sxs-lookup"><span data-stu-id="a164b-129">tokenType</span></span>|<span data-ttu-id="a164b-130">Eine Zeichenfolge, die den Tokentyp angibt.</span><span class="sxs-lookup"><span data-stu-id="a164b-130">A string that specifies the token type.</span></span> <span data-ttu-id="a164b-131">Der Standardwert ist "http://docs.oasis-open.org/wss/oasis-wss-saml-token-profile-1.1#SAML".</span><span class="sxs-lookup"><span data-stu-id="a164b-131">The default is "http://docs.oasis-open.org/wss/oasis-wss-saml-token-profile-1.1#SAML".</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="a164b-132">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="a164b-132">Child Elements</span></span>  
  
|<span data-ttu-id="a164b-133">Element</span><span class="sxs-lookup"><span data-stu-id="a164b-133">Element</span></span>|<span data-ttu-id="a164b-134">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="a164b-134">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="a164b-135">\<additionalRequestParameters></span><span class="sxs-lookup"><span data-stu-id="a164b-135">\<additionalRequestParameters></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/additionalrequestparameters-element.md)|<span data-ttu-id="a164b-136">Eine Auflistung von Konfigurationselementen, die zusätzliche Anforderungsparameter angeben.</span><span class="sxs-lookup"><span data-stu-id="a164b-136">A collection of configuration elements that specify additional request parameters.</span></span>|  
|[<span data-ttu-id="a164b-137">\<claimTypeRequirements></span><span class="sxs-lookup"><span data-stu-id="a164b-137">\<claimTypeRequirements></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/claimtyperequirements-element.md)|<span data-ttu-id="a164b-138">Gibt eine Auflistung von erforderlichen Anspruchstypen an.</span><span class="sxs-lookup"><span data-stu-id="a164b-138">Specifies a collection of required claim types.</span></span><br /><br /> <span data-ttu-id="a164b-139">In einem verbundenen Szenario legen Dienste die Anforderungen für eingehende Anmeldeinformationen fest.</span><span class="sxs-lookup"><span data-stu-id="a164b-139">In a federated scenario, services state the requirements on incoming credentials.</span></span> <span data-ttu-id="a164b-140">Zum Beispiel müssen die eingehenden Anmeldeinformationen einen bestimmten Satz an Anspruchstypen aufweisen.</span><span class="sxs-lookup"><span data-stu-id="a164b-140">For example, the incoming credentials must possess a certain set of claim types.</span></span> <span data-ttu-id="a164b-141">Jedes Element in dieser Auflistung gibt die Typen der erforderlichen und optionalen Ansprüche an, die in verbundenen Anmeldeinformationen vorhanden sein sollen.</span><span class="sxs-lookup"><span data-stu-id="a164b-141">Each element in this collection specifies the types of required and optional claims expected to appear in a federated credential.</span></span>|  
|[<span data-ttu-id="a164b-142">\<issuer></span><span class="sxs-lookup"><span data-stu-id="a164b-142">\<issuer></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/issuer-of-issuedtokenparameters.md)|<span data-ttu-id="a164b-143">Ein Konfigurationselement, das den Endpunkt angibt, der das aktuelle Token ausgibt.</span><span class="sxs-lookup"><span data-stu-id="a164b-143">A configuration element that specifies the endpoint that issues the current token.</span></span>|  
|[<span data-ttu-id="a164b-144">\<issuerMetadata></span><span class="sxs-lookup"><span data-stu-id="a164b-144">\<issuerMetadata></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/issuermetadata-of-issuedtokenparameters.md)|<span data-ttu-id="a164b-145">Ein Konfigurationselement, das die Endpunktadresse der Metadaten des Tokenausstellers angibt.</span><span class="sxs-lookup"><span data-stu-id="a164b-145">A configuration element that specifies the endpoint address of the token issuer's metadata.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="a164b-146">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="a164b-146">Parent Elements</span></span>  
  
|<span data-ttu-id="a164b-147">Element</span><span class="sxs-lookup"><span data-stu-id="a164b-147">Element</span></span>|<span data-ttu-id="a164b-148">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="a164b-148">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="a164b-149">\<secureConversationBootstrap></span><span class="sxs-lookup"><span data-stu-id="a164b-149">\<secureConversationBootstrap></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/secureconversationbootstrap.md)|<span data-ttu-id="a164b-150">Gibt die Standardwerte an, die zum Initiieren eines sicheren Konversationsdiensts verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="a164b-150">Specifies the default values used for initiating a secure conversation service.</span></span>|  
|[<span data-ttu-id="a164b-151">\<security></span><span class="sxs-lookup"><span data-stu-id="a164b-151">\<security></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md)|<span data-ttu-id="a164b-152">Gibt die Sicherheitsoptionen für eine benutzerdefinierte Bindung an.</span><span class="sxs-lookup"><span data-stu-id="a164b-152">Specifies the security options for a custom binding.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="a164b-153">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a164b-153">See also</span></span>
- <xref:System.ServiceModel.Security.Tokens.IssuedSecurityTokenParameters>
- <xref:System.ServiceModel.Configuration.IssuedTokenParametersElement>
- <xref:System.ServiceModel.Configuration.SecurityElementBase.IssuedTokenParameters%2A>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [<span data-ttu-id="a164b-154">Bindungen</span><span class="sxs-lookup"><span data-stu-id="a164b-154">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)
- [<span data-ttu-id="a164b-155">Erweitern von Bindungen</span><span class="sxs-lookup"><span data-stu-id="a164b-155">Extending Bindings</span></span>](../../../../../docs/framework/wcf/extending/extending-bindings.md)
- [<span data-ttu-id="a164b-156">Benutzerdefinierte Bindungen</span><span class="sxs-lookup"><span data-stu-id="a164b-156">Custom Bindings</span></span>](../../../../../docs/framework/wcf/extending/custom-bindings.md)
- [<span data-ttu-id="a164b-157">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="a164b-157">\<customBinding></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)
- [<span data-ttu-id="a164b-158">Vorgehensweise: Erstellen einer benutzerdefinierten Bindung mit dem SecurityBindingElement</span><span class="sxs-lookup"><span data-stu-id="a164b-158">How to: Create a Custom Binding Using the SecurityBindingElement</span></span>](../../../../../docs/framework/wcf/feature-details/how-to-create-a-custom-binding-using-the-securitybindingelement.md)
- [<span data-ttu-id="a164b-159">Sicherheit mit benutzerdefinierten Bindungen</span><span class="sxs-lookup"><span data-stu-id="a164b-159">Custom Binding Security</span></span>](../../../../../docs/framework/wcf/samples/custom-binding-security.md)
- [<span data-ttu-id="a164b-160">Dienstidentität und Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="a164b-160">Service Identity and Authentication</span></span>](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md)
- [<span data-ttu-id="a164b-161">Verbund und ausgestellte Token</span><span class="sxs-lookup"><span data-stu-id="a164b-161">Federation and Issued Tokens</span></span>](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)
- [<span data-ttu-id="a164b-162">Sicherheitsfunktionen mit benutzerdefinierten Bindungen</span><span class="sxs-lookup"><span data-stu-id="a164b-162">Security Capabilities with Custom Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/security-capabilities-with-custom-bindings.md)
- [<span data-ttu-id="a164b-163">Verbund und ausgestellte Token</span><span class="sxs-lookup"><span data-stu-id="a164b-163">Federation and Issued Tokens</span></span>](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)
