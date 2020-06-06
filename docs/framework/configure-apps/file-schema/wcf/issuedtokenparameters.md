---
title: <issuedTokenParameters>
ms.date: 03/30/2017
ms.assetid: 120b3f37-7331-4816-b712-d6aab39655a4
ms.openlocfilehash: 8432463ff62e4b5e54a491b574cc6a5285efe220
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/06/2020
ms.locfileid: "70397959"
---
# \<issuedTokenParameters>
<span data-ttu-id="792b1-101">Gibt die Parameter für einen Sicherheitstoken an, der in einem verbundenen Sicherheitsszenario ausgegeben wird.</span><span class="sxs-lookup"><span data-stu-id="792b1-101">Specifies the parameters for a security token issued in a Federated security scenario.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<customBinding>**](custombinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<security>**](security-of-custombinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<issuedTokenParameters>**  
  
## <a name="syntax"></a><span data-ttu-id="792b1-102">Syntax</span><span class="sxs-lookup"><span data-stu-id="792b1-102">Syntax</span></span>  
  
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
  
## <a name="type"></a><span data-ttu-id="792b1-103">type</span><span class="sxs-lookup"><span data-stu-id="792b1-103">Type</span></span>  
 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="792b1-104">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="792b1-104">Attributes and Elements</span></span>  
 <span data-ttu-id="792b1-105">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="792b1-105">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="792b1-106">Attribute</span><span class="sxs-lookup"><span data-stu-id="792b1-106">Attributes</span></span>  
  
|<span data-ttu-id="792b1-107">attribute</span><span class="sxs-lookup"><span data-stu-id="792b1-107">Attribute</span></span>|<span data-ttu-id="792b1-108">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="792b1-108">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="792b1-109">defaultMessageSecurityVersion</span><span class="sxs-lookup"><span data-stu-id="792b1-109">defaultMessageSecurityVersion</span></span>|<span data-ttu-id="792b1-110">Gibt die Versionen der Sicherheitsspezifikationen (WS-Security, WS-Trust, WS-Secure Conversation und WS-Security Policy) an, die von der Bindung unterstützt werden müssen.</span><span class="sxs-lookup"><span data-stu-id="792b1-110">Specifies the versions of the security specifications, (WS-Security, WS-Trust, WS-Secure Conversation and WS-Security Policy) that must be supported by the binding.</span></span> <span data-ttu-id="792b1-111">Dieser Wert ist vom Typ <xref:System.ServiceModel.MessageSecurityVersion>.</span><span class="sxs-lookup"><span data-stu-id="792b1-111">This value is of type <xref:System.ServiceModel.MessageSecurityVersion>.</span></span>|  
|<span data-ttu-id="792b1-112">inclusionMode</span><span class="sxs-lookup"><span data-stu-id="792b1-112">inclusionMode</span></span>|<span data-ttu-id="792b1-113">Gibt die Tokeneinschlussanforderungen an.</span><span class="sxs-lookup"><span data-stu-id="792b1-113">Specifies the token inclusion requirements.</span></span> <span data-ttu-id="792b1-114">Dieses Attribut ist vom Typ <xref:System.ServiceModel.Security.Tokens.SecurityTokenInclusionMode>.</span><span class="sxs-lookup"><span data-stu-id="792b1-114">This attribute is of type <xref:System.ServiceModel.Security.Tokens.SecurityTokenInclusionMode>.</span></span>|  
|<span data-ttu-id="792b1-115">keySize</span><span class="sxs-lookup"><span data-stu-id="792b1-115">keySize</span></span>|<span data-ttu-id="792b1-116">Eine ganze Zahl, die die Größe des Tokenschlüssels angibt.</span><span class="sxs-lookup"><span data-stu-id="792b1-116">An integer that specifies the token key size.</span></span> <span data-ttu-id="792b1-117">Der Standardwert ist 256.</span><span class="sxs-lookup"><span data-stu-id="792b1-117">The default value is 256.</span></span>|  
|<span data-ttu-id="792b1-118">keyType</span><span class="sxs-lookup"><span data-stu-id="792b1-118">keyType</span></span>|<span data-ttu-id="792b1-119">Ein gültiger Wert von <xref:System.IdentityModel.Tokens.SecurityKeyType>, der den Schlüsseltyp angibt.</span><span class="sxs-lookup"><span data-stu-id="792b1-119">A valid value of <xref:System.IdentityModel.Tokens.SecurityKeyType> that specifies the key type.</span></span> <span data-ttu-id="792b1-120">Der Standardwert lautet `SymmetricKey`.</span><span class="sxs-lookup"><span data-stu-id="792b1-120">The default is `SymmetricKey`.</span></span>|  
|<span data-ttu-id="792b1-121">tokenType</span><span class="sxs-lookup"><span data-stu-id="792b1-121">tokenType</span></span>|<span data-ttu-id="792b1-122">Eine Zeichenfolge, die den Tokentyp angibt.</span><span class="sxs-lookup"><span data-stu-id="792b1-122">A string that specifies the token type.</span></span> <span data-ttu-id="792b1-123">Der Standardwert ist "http://docs.oasis-open.org/wss/oasis-wss-saml-token-profile-1.1#SAML".</span><span class="sxs-lookup"><span data-stu-id="792b1-123">The default is "http://docs.oasis-open.org/wss/oasis-wss-saml-token-profile-1.1#SAML".</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="792b1-124">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="792b1-124">Child Elements</span></span>  
  
|<span data-ttu-id="792b1-125">Element</span><span class="sxs-lookup"><span data-stu-id="792b1-125">Element</span></span>|<span data-ttu-id="792b1-126">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="792b1-126">Description</span></span>|  
|-------------|-----------------|  
|[\<additionalRequestParameters>](additionalrequestparameters-element.md)|<span data-ttu-id="792b1-127">Eine Auflistung von Konfigurationselementen, die zusätzliche Anforderungsparameter angeben.</span><span class="sxs-lookup"><span data-stu-id="792b1-127">A collection of configuration elements that specify additional request parameters.</span></span>|  
|[\<claimTypeRequirements>](claimtyperequirements-element.md)|<span data-ttu-id="792b1-128">Gibt eine Auflistung von erforderlichen Anspruchstypen an.</span><span class="sxs-lookup"><span data-stu-id="792b1-128">Specifies a collection of required claim types.</span></span><br /><br /> <span data-ttu-id="792b1-129">In einem verbundenen Szenario legen Dienste die Anforderungen für eingehende Anmeldeinformationen fest.</span><span class="sxs-lookup"><span data-stu-id="792b1-129">In a federated scenario, services state the requirements on incoming credentials.</span></span> <span data-ttu-id="792b1-130">Zum Beispiel müssen die eingehenden Anmeldeinformationen einen bestimmten Satz an Anspruchstypen aufweisen.</span><span class="sxs-lookup"><span data-stu-id="792b1-130">For example, the incoming credentials must possess a certain set of claim types.</span></span> <span data-ttu-id="792b1-131">Jedes Element in dieser Auflistung gibt die Typen der erforderlichen und optionalen Ansprüche an, die in verbundenen Anmeldeinformationen vorhanden sein sollen.</span><span class="sxs-lookup"><span data-stu-id="792b1-131">Each element in this collection specifies the types of required and optional claims expected to appear in a federated credential.</span></span>|  
|[\<issuer>](issuer-of-issuedtokenparameters.md)|<span data-ttu-id="792b1-132">Ein Konfigurationselement, das den Endpunkt angibt, der das aktuelle Token ausgibt.</span><span class="sxs-lookup"><span data-stu-id="792b1-132">A configuration element that specifies the endpoint that issues the current token.</span></span>|  
|[\<issuerMetadata>](issuermetadata-of-issuedtokenparameters.md)|<span data-ttu-id="792b1-133">Ein Konfigurationselement, das die Endpunktadresse der Metadaten des Tokenausstellers angibt.</span><span class="sxs-lookup"><span data-stu-id="792b1-133">A configuration element that specifies the endpoint address of the token issuer's metadata.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="792b1-134">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="792b1-134">Parent Elements</span></span>  
  
|<span data-ttu-id="792b1-135">Element</span><span class="sxs-lookup"><span data-stu-id="792b1-135">Element</span></span>|<span data-ttu-id="792b1-136">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="792b1-136">Description</span></span>|  
|-------------|-----------------|  
|[\<secureConversationBootstrap>](secureconversationbootstrap.md)|<span data-ttu-id="792b1-137">Gibt die Standardwerte an, die zum Initiieren eines sicheren Konversationsdiensts verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="792b1-137">Specifies the default values used for initiating a secure conversation service.</span></span>|  
|[\<security>](security-of-custombinding.md)|<span data-ttu-id="792b1-138">Gibt die Sicherheitsoptionen für eine benutzerdefinierte Bindung an.</span><span class="sxs-lookup"><span data-stu-id="792b1-138">Specifies the security options for a custom binding.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="792b1-139">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="792b1-139">See also</span></span>

- <xref:System.ServiceModel.Security.Tokens.IssuedSecurityTokenParameters>
- <xref:System.ServiceModel.Configuration.IssuedTokenParametersElement>
- <xref:System.ServiceModel.Configuration.SecurityElementBase.IssuedTokenParameters%2A>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [<span data-ttu-id="792b1-140">Bindungen</span><span class="sxs-lookup"><span data-stu-id="792b1-140">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="792b1-141">Erweitern von Bindungen</span><span class="sxs-lookup"><span data-stu-id="792b1-141">Extending Bindings</span></span>](../../../wcf/extending/extending-bindings.md)
- [<span data-ttu-id="792b1-142">Benutzerdefinierte Bindungen</span><span class="sxs-lookup"><span data-stu-id="792b1-142">Custom Bindings</span></span>](../../../wcf/extending/custom-bindings.md)
- [\<customBinding>](custombinding.md)
- [<span data-ttu-id="792b1-143">Vorgehensweise: Erstellen einer benutzerdefinierten Bindung mit dem SecurityBindingElement</span><span class="sxs-lookup"><span data-stu-id="792b1-143">How to: Create a Custom Binding Using the SecurityBindingElement</span></span>](../../../wcf/feature-details/how-to-create-a-custom-binding-using-the-securitybindingelement.md)
- [<span data-ttu-id="792b1-144">Sicherheit mit benutzerdefinierten Bindungen</span><span class="sxs-lookup"><span data-stu-id="792b1-144">Custom Binding Security</span></span>](../../../wcf/samples/custom-binding-security.md)
- [<span data-ttu-id="792b1-145">Dienstidentität und Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="792b1-145">Service Identity and Authentication</span></span>](../../../wcf/feature-details/service-identity-and-authentication.md)
- [<span data-ttu-id="792b1-146">Verbund und ausgestellte Token</span><span class="sxs-lookup"><span data-stu-id="792b1-146">Federation and Issued Tokens</span></span>](../../../wcf/feature-details/federation-and-issued-tokens.md)
- [<span data-ttu-id="792b1-147">Sicherheitsfunktionen mit benutzerdefinierten Bindungen</span><span class="sxs-lookup"><span data-stu-id="792b1-147">Security Capabilities with Custom Bindings</span></span>](../../../wcf/feature-details/security-capabilities-with-custom-bindings.md)
- [<span data-ttu-id="792b1-148">Verbund und ausgestellte Token</span><span class="sxs-lookup"><span data-stu-id="792b1-148">Federation and Issued Tokens</span></span>](../../../wcf/feature-details/federation-and-issued-tokens.md)
