---
title: <add> von <claimTypeRequirements>
ms.date: 03/30/2017
ms.assetid: c68e83c9-39e8-4264-b1ce-b6a9eb5b98aa
ms.openlocfilehash: 00699a6fa5d0de7ac554db6ef8d0bbe511a85c0a
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91149217"
---
# <a name="add-of-claimtyperequirements"></a><span data-ttu-id="894b5-102">\<add> von \<claimTypeRequirements></span><span class="sxs-lookup"><span data-stu-id="894b5-102">\<add> of \<claimTypeRequirements></span></span>

<span data-ttu-id="894b5-103">Gibt die Typen der erforderlichen und optionalen Ansprüche an, die in verbundenen Anmeldeinformationen vorhanden sein sollen.</span><span class="sxs-lookup"><span data-stu-id="894b5-103">Specifies the types of required and optional claims expected to appear in the federated credential.</span></span> <span data-ttu-id="894b5-104">Zum Beispiel geben die Dienste die Anforderungen für eingehende Anmeldeinformationen an, die einen bestimmten Satz von Anspruchstypen verarbeiten müssen.</span><span class="sxs-lookup"><span data-stu-id="894b5-104">For example, services state the requirements on incoming credentials, which must possess a certain set of claim types.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<customBinding>**](custombinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<security>**](security-of-custombinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<issuedTokenParameters>**](issuedtokenparameters.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<claimTypeRequirements>**](claimtyperequirements-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**  
  
## <a name="syntax"></a><span data-ttu-id="894b5-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="894b5-105">Syntax</span></span>  
  
```xml  
<claimTypeRequirements>
  <add claimType="URI"
       isOptional="Boolean" />
</claimTypeRequirements>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="894b5-106">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="894b5-106">Attributes and Elements</span></span>  

 <span data-ttu-id="894b5-107">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="894b5-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="894b5-108">Attribute</span><span class="sxs-lookup"><span data-stu-id="894b5-108">Attributes</span></span>  
  
|<span data-ttu-id="894b5-109">attribute</span><span class="sxs-lookup"><span data-stu-id="894b5-109">Attribute</span></span>|<span data-ttu-id="894b5-110">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="894b5-110">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="894b5-111">claimType</span><span class="sxs-lookup"><span data-stu-id="894b5-111">claimType</span></span>|<span data-ttu-id="894b5-112">Ein URI, der den Typ eines Anspruchs definiert.</span><span class="sxs-lookup"><span data-stu-id="894b5-112">A URI that defines the type of a claim.</span></span> <span data-ttu-id="894b5-113">Wenn ein Benutzer zum Beispiel ein Produkt auf einer Website erwerben möchte, muss er eine gültige Kreditkarte mit einem ausreichend hohen Kreditrahmen vorlegen.</span><span class="sxs-lookup"><span data-stu-id="894b5-113">For example, to purchase a product from a Web site, the user must present a valid credit card with sufficient credit limit.</span></span> <span data-ttu-id="894b5-114">Der Anspruchstyp wäre der Kreditkarten-URI.</span><span class="sxs-lookup"><span data-stu-id="894b5-114">The claim type would be the credit card URI.</span></span>|  
|<span data-ttu-id="894b5-115">isOptional</span><span class="sxs-lookup"><span data-stu-id="894b5-115">isOptional</span></span>|<span data-ttu-id="894b5-116">Ein boolescher Wert, der angibt, ob der Anspruch optional ist.</span><span class="sxs-lookup"><span data-stu-id="894b5-116">A Boolean value that specifies if this is for an optional claim.</span></span> <span data-ttu-id="894b5-117">Legen Sie dieses Attribut auf `false` fest, wenn dies ein erforderlicher Anspruch ist.</span><span class="sxs-lookup"><span data-stu-id="894b5-117">Set this attribute to `false` if this is a required claim.</span></span><br /><br /> <span data-ttu-id="894b5-118">Sie können dieses Attribut verwenden, wenn der Dienst um Informationen bittet, aber es nicht erfordert.</span><span class="sxs-lookup"><span data-stu-id="894b5-118">You can use this attribute when the service asks for some information but does not require it.</span></span> <span data-ttu-id="894b5-119">Wenn Sie z. b. den Vornamen, den Nachnamen und die Adresse des Benutzers eingeben müssen, aber entscheiden, dass die Telefonnummer optional ist.</span><span class="sxs-lookup"><span data-stu-id="894b5-119">For example, if you require the user to enter their first name, last name, and address, but decide that phone number is optional.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="894b5-120">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="894b5-120">Child Elements</span></span>  

 <span data-ttu-id="894b5-121">Keine</span><span class="sxs-lookup"><span data-stu-id="894b5-121">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="894b5-122">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="894b5-122">Parent Elements</span></span>  
  
|<span data-ttu-id="894b5-123">Element</span><span class="sxs-lookup"><span data-stu-id="894b5-123">Element</span></span>|<span data-ttu-id="894b5-124">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="894b5-124">Description</span></span>|  
|-------------|-----------------|  
|[\<claimTypeRequirements>](claimtyperequirements-element.md)|<span data-ttu-id="894b5-125">Gibt eine Auflistung von erforderlichen Anspruchstypen an.</span><span class="sxs-lookup"><span data-stu-id="894b5-125">Specifies a collection of required claim types.</span></span><br /><br /> <span data-ttu-id="894b5-126">In einem verbundenen Szenario legen Dienste die Anforderungen für eingehende Anmeldeinformationen fest.</span><span class="sxs-lookup"><span data-stu-id="894b5-126">In a federated scenario, services state the requirements on incoming credentials.</span></span> <span data-ttu-id="894b5-127">Zum Beispiel müssen die eingehenden Anmeldeinformationen einen bestimmten Satz an Anspruchstypen aufweisen.</span><span class="sxs-lookup"><span data-stu-id="894b5-127">For example, the incoming credentials must possess a certain set of claim types.</span></span> <span data-ttu-id="894b5-128">Jedes Element in dieser Auflistung gibt die Typen der erforderlichen und optionalen Ansprüche an, die in verbundenen Anmeldeinformationen vorhanden sein sollen.</span><span class="sxs-lookup"><span data-stu-id="894b5-128">Each element in this collection specifies the types of required and optional claims expected to appear in a federated credential.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="894b5-129">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="894b5-129">Remarks</span></span>  

 <span data-ttu-id="894b5-130">In einem verbundenen Szenario legen Dienste die Anforderungen für eingehende Anmeldeinformationen fest.</span><span class="sxs-lookup"><span data-stu-id="894b5-130">In a federated scenario, services state the requirements on incoming credentials.</span></span> <span data-ttu-id="894b5-131">Zum Beispiel müssen die eingehenden Anmeldeinformationen einen bestimmten Satz an Anspruchstypen aufweisen.</span><span class="sxs-lookup"><span data-stu-id="894b5-131">For example, the incoming credentials must possess a certain set of claim types.</span></span> <span data-ttu-id="894b5-132">Diese Anforderung wird sich in einer Sicherheitsrichtlinie auswirken.</span><span class="sxs-lookup"><span data-stu-id="894b5-132">This requirement is manifested in a security policy.</span></span> <span data-ttu-id="894b5-133">Wenn ein Client Anmeldeinformationen von einem Verbunddienst anfordert (z.&#160;B. CardSpace), legt er die Anforderungen in einer Tokenanforderung (RequestSecurityToken) ab, sodass der Verbunddienst die Anmeldeinformationen ausgeben kann, die die Anforderungen entsprechend erfüllen.</span><span class="sxs-lookup"><span data-stu-id="894b5-133">When a client requests credentials from a federated service (for example, CardSpace), it puts the requirements into a token request (RequestSecurityToken) so that the federated service can issue the credentials that satisfy the requirements accordingly.</span></span>  
  
## <a name="example"></a><span data-ttu-id="894b5-134">Beispiel</span><span class="sxs-lookup"><span data-stu-id="894b5-134">Example</span></span>  

 <span data-ttu-id="894b5-135">Die folgende Konfiguration fügt einer Sicherheitsbindung zwei Anspruchstypanforderungen hinzu.</span><span class="sxs-lookup"><span data-stu-id="894b5-135">The following configuration adds two claim type requirements to a security binding.</span></span>  
  
```xml  
<bindings>
  <wsFederationHttpBinding>
    <binding name="myFederatedBinding">
      <security mode="Message">
        <message issuedTokenType="urn:oasis:names:tc:SAML:1.0:assertion">
          <claimTypeRequirements>
            <add claimType="http://schemas.microsoft.com/ws/2005/05/identity/claims/EmailAddress" />
            <add claimType="http://schemas.microsoft.com/ws/2005/05/identity/claims/UserName"
                 optional="true" />
          </claimTypeRequirements>
        </message>
      </security>
    </binding>
  </wsFederationHttpBinding>
</bindings>
```  
  
## <a name="see-also"></a><span data-ttu-id="894b5-136">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="894b5-136">See also</span></span>

- <xref:System.ServiceModel.Security.Tokens.ClaimTypeRequirement>
- <xref:System.ServiceModel.Security.Tokens.IssuedSecurityTokenParameters.ClaimTypeRequirements%2A>
- <xref:System.ServiceModel.Configuration.IssuedTokenParametersElement.ClaimTypeRequirements%2A>
- <xref:System.ServiceModel.Configuration.ClaimTypeElementCollection>
- <xref:System.ServiceModel.Configuration.ClaimTypeElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [\<claimTypeRequirements>](claimtyperequirements-element.md)
- [<span data-ttu-id="894b5-137">Bindungen</span><span class="sxs-lookup"><span data-stu-id="894b5-137">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="894b5-138">Erweitern von Bindungen</span><span class="sxs-lookup"><span data-stu-id="894b5-138">Extending Bindings</span></span>](../../../wcf/extending/extending-bindings.md)
- [<span data-ttu-id="894b5-139">Benutzerdefinierte Bindungen</span><span class="sxs-lookup"><span data-stu-id="894b5-139">Custom Bindings</span></span>](../../../wcf/extending/custom-bindings.md)
- [\<customBinding>](custombinding.md)
- [<span data-ttu-id="894b5-140">Vorgehensweise: Erstellen einer benutzerdefinierten Bindung mit dem SecurityBindingElement</span><span class="sxs-lookup"><span data-stu-id="894b5-140">How to: Create a Custom Binding Using the SecurityBindingElement</span></span>](../../../wcf/feature-details/how-to-create-a-custom-binding-using-the-securitybindingelement.md)
- [<span data-ttu-id="894b5-141">Sicherheit mit benutzerdefinierten Bindungen</span><span class="sxs-lookup"><span data-stu-id="894b5-141">Custom Binding Security</span></span>](../../../wcf/samples/custom-binding-security.md)
