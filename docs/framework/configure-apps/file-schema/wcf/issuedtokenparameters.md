---
title: <issuedTokenParameters>
ms.date: 03/30/2017
ms.assetid: 120b3f37-7331-4816-b712-d6aab39655a4
ms.openlocfilehash: c90024a0629f39d160967ca00434e48f682d8933
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91157316"
---
# \<issuedTokenParameters>

<span data-ttu-id="0b64b-101">Gibt die Parameter für einen Sicherheitstoken an, der in einem verbundenen Sicherheitsszenario ausgegeben wird.</span><span class="sxs-lookup"><span data-stu-id="0b64b-101">Specifies the parameters for a security token issued in a Federated security scenario.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<customBinding>**](custombinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<security>**](security-of-custombinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<issuedTokenParameters>**  
  
## <a name="syntax"></a><span data-ttu-id="0b64b-102">Syntax</span><span class="sxs-lookup"><span data-stu-id="0b64b-102">Syntax</span></span>  
  
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
  
## <a name="type"></a><span data-ttu-id="0b64b-103">Typ</span><span class="sxs-lookup"><span data-stu-id="0b64b-103">Type</span></span>  

 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="0b64b-104">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="0b64b-104">Attributes and Elements</span></span>  

 <span data-ttu-id="0b64b-105">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="0b64b-105">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="0b64b-106">Attribute</span><span class="sxs-lookup"><span data-stu-id="0b64b-106">Attributes</span></span>  
  
|<span data-ttu-id="0b64b-107">attribute</span><span class="sxs-lookup"><span data-stu-id="0b64b-107">Attribute</span></span>|<span data-ttu-id="0b64b-108">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="0b64b-108">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="0b64b-109">defaultMessageSecurityVersion</span><span class="sxs-lookup"><span data-stu-id="0b64b-109">defaultMessageSecurityVersion</span></span>|<span data-ttu-id="0b64b-110">Gibt die Versionen der Sicherheitsspezifikationen (WS-Security, WS-Trust, WS-Secure Conversation und WS-Security Policy) an, die von der Bindung unterstützt werden müssen.</span><span class="sxs-lookup"><span data-stu-id="0b64b-110">Specifies the versions of the security specifications, (WS-Security, WS-Trust, WS-Secure Conversation and WS-Security Policy) that must be supported by the binding.</span></span> <span data-ttu-id="0b64b-111">Dieser Wert ist vom Typ <xref:System.ServiceModel.MessageSecurityVersion>.</span><span class="sxs-lookup"><span data-stu-id="0b64b-111">This value is of type <xref:System.ServiceModel.MessageSecurityVersion>.</span></span>|  
|<span data-ttu-id="0b64b-112">inclusionMode</span><span class="sxs-lookup"><span data-stu-id="0b64b-112">inclusionMode</span></span>|<span data-ttu-id="0b64b-113">Gibt die Tokeneinschlussanforderungen an.</span><span class="sxs-lookup"><span data-stu-id="0b64b-113">Specifies the token inclusion requirements.</span></span> <span data-ttu-id="0b64b-114">Dieses Attribut ist vom Typ <xref:System.ServiceModel.Security.Tokens.SecurityTokenInclusionMode>.</span><span class="sxs-lookup"><span data-stu-id="0b64b-114">This attribute is of type <xref:System.ServiceModel.Security.Tokens.SecurityTokenInclusionMode>.</span></span>|  
|<span data-ttu-id="0b64b-115">keySize</span><span class="sxs-lookup"><span data-stu-id="0b64b-115">keySize</span></span>|<span data-ttu-id="0b64b-116">Eine ganze Zahl, die die Größe des Tokenschlüssels angibt.</span><span class="sxs-lookup"><span data-stu-id="0b64b-116">An integer that specifies the token key size.</span></span> <span data-ttu-id="0b64b-117">Der Standardwert ist 256.</span><span class="sxs-lookup"><span data-stu-id="0b64b-117">The default value is 256.</span></span>|  
|<span data-ttu-id="0b64b-118">keyType</span><span class="sxs-lookup"><span data-stu-id="0b64b-118">keyType</span></span>|<span data-ttu-id="0b64b-119">Ein gültiger Wert von <xref:System.IdentityModel.Tokens.SecurityKeyType>, der den Schlüsseltyp angibt.</span><span class="sxs-lookup"><span data-stu-id="0b64b-119">A valid value of <xref:System.IdentityModel.Tokens.SecurityKeyType> that specifies the key type.</span></span> <span data-ttu-id="0b64b-120">Der Standardwert lautet `SymmetricKey`.</span><span class="sxs-lookup"><span data-stu-id="0b64b-120">The default is `SymmetricKey`.</span></span>|  
|<span data-ttu-id="0b64b-121">tokenType</span><span class="sxs-lookup"><span data-stu-id="0b64b-121">tokenType</span></span>|<span data-ttu-id="0b64b-122">Eine Zeichenfolge, die den Tokentyp angibt.</span><span class="sxs-lookup"><span data-stu-id="0b64b-122">A string that specifies the token type.</span></span> <span data-ttu-id="0b64b-123">Der Standardwert ist "http://docs.oasis-open.org/wss/oasis-wss-saml-token-profile-1.1#SAML".</span><span class="sxs-lookup"><span data-stu-id="0b64b-123">The default is "http://docs.oasis-open.org/wss/oasis-wss-saml-token-profile-1.1#SAML".</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="0b64b-124">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="0b64b-124">Child Elements</span></span>  
  
|<span data-ttu-id="0b64b-125">Element</span><span class="sxs-lookup"><span data-stu-id="0b64b-125">Element</span></span>|<span data-ttu-id="0b64b-126">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="0b64b-126">Description</span></span>|  
|-------------|-----------------|  
|[\<additionalRequestParameters>](additionalrequestparameters-element.md)|<span data-ttu-id="0b64b-127">Eine Auflistung von Konfigurationselementen, die zusätzliche Anforderungsparameter angeben.</span><span class="sxs-lookup"><span data-stu-id="0b64b-127">A collection of configuration elements that specify additional request parameters.</span></span>|  
|[\<claimTypeRequirements>](claimtyperequirements-element.md)|<span data-ttu-id="0b64b-128">Gibt eine Auflistung von erforderlichen Anspruchstypen an.</span><span class="sxs-lookup"><span data-stu-id="0b64b-128">Specifies a collection of required claim types.</span></span><br /><br /> <span data-ttu-id="0b64b-129">In einem verbundenen Szenario legen Dienste die Anforderungen für eingehende Anmeldeinformationen fest.</span><span class="sxs-lookup"><span data-stu-id="0b64b-129">In a federated scenario, services state the requirements on incoming credentials.</span></span> <span data-ttu-id="0b64b-130">Zum Beispiel müssen die eingehenden Anmeldeinformationen einen bestimmten Satz an Anspruchstypen aufweisen.</span><span class="sxs-lookup"><span data-stu-id="0b64b-130">For example, the incoming credentials must possess a certain set of claim types.</span></span> <span data-ttu-id="0b64b-131">Jedes Element in dieser Auflistung gibt die Typen der erforderlichen und optionalen Ansprüche an, die in verbundenen Anmeldeinformationen vorhanden sein sollen.</span><span class="sxs-lookup"><span data-stu-id="0b64b-131">Each element in this collection specifies the types of required and optional claims expected to appear in a federated credential.</span></span>|  
|[\<issuer>](issuer-of-issuedtokenparameters.md)|<span data-ttu-id="0b64b-132">Ein Konfigurationselement, das den Endpunkt angibt, der das aktuelle Token ausgibt.</span><span class="sxs-lookup"><span data-stu-id="0b64b-132">A configuration element that specifies the endpoint that issues the current token.</span></span>|  
|[\<issuerMetadata>](issuermetadata-of-issuedtokenparameters.md)|<span data-ttu-id="0b64b-133">Ein Konfigurationselement, das die Endpunktadresse der Metadaten des Tokenausstellers angibt.</span><span class="sxs-lookup"><span data-stu-id="0b64b-133">A configuration element that specifies the endpoint address of the token issuer's metadata.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="0b64b-134">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="0b64b-134">Parent Elements</span></span>  
  
|<span data-ttu-id="0b64b-135">Element</span><span class="sxs-lookup"><span data-stu-id="0b64b-135">Element</span></span>|<span data-ttu-id="0b64b-136">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="0b64b-136">Description</span></span>|  
|-------------|-----------------|  
|[\<secureConversationBootstrap>](secureconversationbootstrap.md)|<span data-ttu-id="0b64b-137">Gibt die Standardwerte an, die zum Initiieren eines sicheren Konversationsdiensts verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="0b64b-137">Specifies the default values used for initiating a secure conversation service.</span></span>|  
|[\<security>](security-of-custombinding.md)|<span data-ttu-id="0b64b-138">Gibt die Sicherheitsoptionen für eine benutzerdefinierte Bindung an.</span><span class="sxs-lookup"><span data-stu-id="0b64b-138">Specifies the security options for a custom binding.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="0b64b-139">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="0b64b-139">See also</span></span>

- <xref:System.ServiceModel.Security.Tokens.IssuedSecurityTokenParameters>
- <xref:System.ServiceModel.Configuration.IssuedTokenParametersElement>
- <xref:System.ServiceModel.Configuration.SecurityElementBase.IssuedTokenParameters%2A>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [<span data-ttu-id="0b64b-140">Bindungen</span><span class="sxs-lookup"><span data-stu-id="0b64b-140">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="0b64b-141">Erweitern von Bindungen</span><span class="sxs-lookup"><span data-stu-id="0b64b-141">Extending Bindings</span></span>](../../../wcf/extending/extending-bindings.md)
- [<span data-ttu-id="0b64b-142">Benutzerdefinierte Bindungen</span><span class="sxs-lookup"><span data-stu-id="0b64b-142">Custom Bindings</span></span>](../../../wcf/extending/custom-bindings.md)
- [\<customBinding>](custombinding.md)
- [<span data-ttu-id="0b64b-143">Vorgehensweise: Erstellen einer benutzerdefinierten Bindung mit dem SecurityBindingElement</span><span class="sxs-lookup"><span data-stu-id="0b64b-143">How to: Create a Custom Binding Using the SecurityBindingElement</span></span>](../../../wcf/feature-details/how-to-create-a-custom-binding-using-the-securitybindingelement.md)
- [<span data-ttu-id="0b64b-144">Sicherheit mit benutzerdefinierten Bindungen</span><span class="sxs-lookup"><span data-stu-id="0b64b-144">Custom Binding Security</span></span>](../../../wcf/samples/custom-binding-security.md)
- [<span data-ttu-id="0b64b-145">Dienstidentität und Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="0b64b-145">Service Identity and Authentication</span></span>](../../../wcf/feature-details/service-identity-and-authentication.md)
- [<span data-ttu-id="0b64b-146">Verbund und ausgestellte Token</span><span class="sxs-lookup"><span data-stu-id="0b64b-146">Federation and Issued Tokens</span></span>](../../../wcf/feature-details/federation-and-issued-tokens.md)
- [<span data-ttu-id="0b64b-147">Sicherheitsfunktionen mit benutzerdefinierten Bindungen</span><span class="sxs-lookup"><span data-stu-id="0b64b-147">Security Capabilities with Custom Bindings</span></span>](../../../wcf/feature-details/security-capabilities-with-custom-bindings.md)
- [<span data-ttu-id="0b64b-148">Verbund und ausgestellte Token</span><span class="sxs-lookup"><span data-stu-id="0b64b-148">Federation and Issued Tokens</span></span>](../../../wcf/feature-details/federation-and-issued-tokens.md)
