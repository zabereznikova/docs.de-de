---
title: <add> von <claimTypeRequirements>
ms.date: 03/30/2017
ms.assetid: c68e83c9-39e8-4264-b1ce-b6a9eb5b98aa
ms.openlocfilehash: 6ba935f7f6dae0e4d9e6581f53a50c684efcbed3
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79153086"
---
# <a name="add-of-claimtyperequirements"></a><span data-ttu-id="00f60-102">\<Hinzufügen> \<von claimTypeRequirements></span><span class="sxs-lookup"><span data-stu-id="00f60-102">\<add> of \<claimTypeRequirements></span></span>
<span data-ttu-id="00f60-103">Gibt die Typen der erforderlichen und optionalen Ansprüche an, die in verbundenen Anmeldeinformationen vorhanden sein sollen.</span><span class="sxs-lookup"><span data-stu-id="00f60-103">Specifies the types of required and optional claims expected to appear in the federated credential.</span></span> <span data-ttu-id="00f60-104">Zum Beispiel geben die Dienste die Anforderungen für eingehende Anmeldeinformationen an, die einen bestimmten Satz von Anspruchstypen verarbeiten müssen.</span><span class="sxs-lookup"><span data-stu-id="00f60-104">For example, services state the requirements on incoming credentials, which must possess a certain set of claim types.</span></span>  
  
<span data-ttu-id="00f60-105">[**\<Konfiguration>**](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="00f60-105">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="00f60-106">&nbsp;&nbsp;[**\<system.serviceModell>**](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="00f60-106">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="00f60-107">&nbsp;&nbsp;&nbsp;&nbsp;[**\<Bindungen>**](bindings.md)</span><span class="sxs-lookup"><span data-stu-id="00f60-107">&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)</span></span>\
<span data-ttu-id="00f60-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<customBinding>**](custombinding.md)</span><span class="sxs-lookup"><span data-stu-id="00f60-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<customBinding>**](custombinding.md)</span></span>\
<span data-ttu-id="00f60-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<verbindliche>**</span><span class="sxs-lookup"><span data-stu-id="00f60-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**</span></span>\
<span data-ttu-id="00f60-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<Sicherheits->**](security-of-custombinding.md)</span><span class="sxs-lookup"><span data-stu-id="00f60-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<security>**](security-of-custombinding.md)</span></span>\
<span data-ttu-id="00f60-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<issuedTokenParameters>**](issuedtokenparameters.md)</span><span class="sxs-lookup"><span data-stu-id="00f60-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<issuedTokenParameters>**](issuedtokenparameters.md)</span></span>\
<span data-ttu-id="00f60-112">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<claimTypeRequirements>**](claimtyperequirements-element.md)</span><span class="sxs-lookup"><span data-stu-id="00f60-112">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<claimTypeRequirements>**](claimtyperequirements-element.md)</span></span>\
<span data-ttu-id="00f60-113">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<hinzufügen>**</span><span class="sxs-lookup"><span data-stu-id="00f60-113">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="00f60-114">Syntax</span><span class="sxs-lookup"><span data-stu-id="00f60-114">Syntax</span></span>  
  
```xml  
<claimTypeRequirements>
  <add claimType="URI"
       isOptional="Boolean" />
</claimTypeRequirements>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="00f60-115">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="00f60-115">Attributes and Elements</span></span>  
 <span data-ttu-id="00f60-116">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="00f60-116">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="00f60-117">Attributes</span><span class="sxs-lookup"><span data-stu-id="00f60-117">Attributes</span></span>  
  
|<span data-ttu-id="00f60-118">attribute</span><span class="sxs-lookup"><span data-stu-id="00f60-118">Attribute</span></span>|<span data-ttu-id="00f60-119">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="00f60-119">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="00f60-120">claimType</span><span class="sxs-lookup"><span data-stu-id="00f60-120">claimType</span></span>|<span data-ttu-id="00f60-121">Ein URI, der den Typ eines Anspruchs definiert.</span><span class="sxs-lookup"><span data-stu-id="00f60-121">A URI that defines the type of a claim.</span></span> <span data-ttu-id="00f60-122">Wenn ein Benutzer zum Beispiel ein Produkt auf einer Website erwerben möchte, muss er eine gültige Kreditkarte mit einem ausreichend hohen Kreditrahmen vorlegen.</span><span class="sxs-lookup"><span data-stu-id="00f60-122">For example, to purchase a product from a Web site, the user must present a valid credit card with sufficient credit limit.</span></span> <span data-ttu-id="00f60-123">Der Anspruchstyp wäre der Kreditkarten-URI.</span><span class="sxs-lookup"><span data-stu-id="00f60-123">The claim type would be the credit card URI.</span></span>|  
|<span data-ttu-id="00f60-124">isOptional</span><span class="sxs-lookup"><span data-stu-id="00f60-124">isOptional</span></span>|<span data-ttu-id="00f60-125">Ein boolescher Wert, der angibt, ob der Anspruch optional ist.</span><span class="sxs-lookup"><span data-stu-id="00f60-125">A Boolean value that specifies if this is for an optional claim.</span></span> <span data-ttu-id="00f60-126">Legen Sie dieses Attribut auf `false` fest, wenn dies ein erforderlicher Anspruch ist.</span><span class="sxs-lookup"><span data-stu-id="00f60-126">Set this attribute to `false` if this is a required claim.</span></span><br /><br /> <span data-ttu-id="00f60-127">Sie können dieses Attribut verwenden, wenn der Dienst um Informationen bittet, aber es nicht erfordert.</span><span class="sxs-lookup"><span data-stu-id="00f60-127">You can use this attribute when the service asks for some information but does not require it.</span></span> <span data-ttu-id="00f60-128">Wenn Sie z. B. verlangen, dass der Benutzer seinen Vornamen, Nachnamen und seine Adresse eingibt, diese Telefonnummer jedoch optional ist.</span><span class="sxs-lookup"><span data-stu-id="00f60-128">For example, if you require the user to enter their first name, last name, and address, but decide that phone number is optional.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="00f60-129">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="00f60-129">Child Elements</span></span>  
 <span data-ttu-id="00f60-130">Keine.</span><span class="sxs-lookup"><span data-stu-id="00f60-130">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="00f60-131">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="00f60-131">Parent Elements</span></span>  
  
|<span data-ttu-id="00f60-132">Element</span><span class="sxs-lookup"><span data-stu-id="00f60-132">Element</span></span>|<span data-ttu-id="00f60-133">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="00f60-133">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="00f60-134">\<claimTypeRequirements></span><span class="sxs-lookup"><span data-stu-id="00f60-134">\<claimTypeRequirements></span></span>](claimtyperequirements-element.md)|<span data-ttu-id="00f60-135">Gibt eine Auflistung von erforderlichen Anspruchstypen an.</span><span class="sxs-lookup"><span data-stu-id="00f60-135">Specifies a collection of required claim types.</span></span><br /><br /> <span data-ttu-id="00f60-136">In einem verbundenen Szenario legen Dienste die Anforderungen für eingehende Anmeldeinformationen fest.</span><span class="sxs-lookup"><span data-stu-id="00f60-136">In a federated scenario, services state the requirements on incoming credentials.</span></span> <span data-ttu-id="00f60-137">Zum Beispiel müssen die eingehenden Anmeldeinformationen einen bestimmten Satz an Anspruchstypen aufweisen.</span><span class="sxs-lookup"><span data-stu-id="00f60-137">For example, the incoming credentials must possess a certain set of claim types.</span></span> <span data-ttu-id="00f60-138">Jedes Element in dieser Auflistung gibt die Typen der erforderlichen und optionalen Ansprüche an, die in verbundenen Anmeldeinformationen vorhanden sein sollen.</span><span class="sxs-lookup"><span data-stu-id="00f60-138">Each element in this collection specifies the types of required and optional claims expected to appear in a federated credential.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="00f60-139">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="00f60-139">Remarks</span></span>  
 <span data-ttu-id="00f60-140">In einem verbundenen Szenario legen Dienste die Anforderungen für eingehende Anmeldeinformationen fest.</span><span class="sxs-lookup"><span data-stu-id="00f60-140">In a federated scenario, services state the requirements on incoming credentials.</span></span> <span data-ttu-id="00f60-141">Zum Beispiel müssen die eingehenden Anmeldeinformationen einen bestimmten Satz an Anspruchstypen aufweisen.</span><span class="sxs-lookup"><span data-stu-id="00f60-141">For example, the incoming credentials must possess a certain set of claim types.</span></span> <span data-ttu-id="00f60-142">Diese Anforderung wird sich in einer Sicherheitsrichtlinie auswirken.</span><span class="sxs-lookup"><span data-stu-id="00f60-142">This requirement is manifested in a security policy.</span></span> <span data-ttu-id="00f60-143">Wenn ein Client Anmeldeinformationen von einem Verbunddienst anfordert (z.&#160;B. CardSpace), legt er die Anforderungen in einer Tokenanforderung (RequestSecurityToken) ab, sodass der Verbunddienst die Anmeldeinformationen ausgeben kann, die die Anforderungen entsprechend erfüllen.</span><span class="sxs-lookup"><span data-stu-id="00f60-143">When a client requests credentials from a federated service (for example, CardSpace), it puts the requirements into a token request (RequestSecurityToken) so that the federated service can issue the credentials that satisfy the requirements accordingly.</span></span>  
  
## <a name="example"></a><span data-ttu-id="00f60-144">Beispiel</span><span class="sxs-lookup"><span data-stu-id="00f60-144">Example</span></span>  
 <span data-ttu-id="00f60-145">Die folgende Konfiguration fügt einer Sicherheitsbindung zwei Anspruchstypanforderungen hinzu.</span><span class="sxs-lookup"><span data-stu-id="00f60-145">The following configuration adds two claim type requirements to a security binding.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="00f60-146">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="00f60-146">See also</span></span>

- <xref:System.ServiceModel.Security.Tokens.ClaimTypeRequirement>
- <xref:System.ServiceModel.Security.Tokens.IssuedSecurityTokenParameters.ClaimTypeRequirements%2A>
- <xref:System.ServiceModel.Configuration.IssuedTokenParametersElement.ClaimTypeRequirements%2A>
- <xref:System.ServiceModel.Configuration.ClaimTypeElementCollection>
- <xref:System.ServiceModel.Configuration.ClaimTypeElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [<span data-ttu-id="00f60-147">\<claimTypeRequirements></span><span class="sxs-lookup"><span data-stu-id="00f60-147">\<claimTypeRequirements></span></span>](claimtyperequirements-element.md)
- [<span data-ttu-id="00f60-148">Bindungen</span><span class="sxs-lookup"><span data-stu-id="00f60-148">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="00f60-149">Erweitern von Bindungen</span><span class="sxs-lookup"><span data-stu-id="00f60-149">Extending Bindings</span></span>](../../../wcf/extending/extending-bindings.md)
- [<span data-ttu-id="00f60-150">Benutzerdefinierte Bindungen</span><span class="sxs-lookup"><span data-stu-id="00f60-150">Custom Bindings</span></span>](../../../wcf/extending/custom-bindings.md)
- [<span data-ttu-id="00f60-151">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="00f60-151">\<customBinding></span></span>](custombinding.md)
- [<span data-ttu-id="00f60-152">Vorgehensweise: Erstellen einer benutzerdefinierten Bindung mit dem SecurityBindingElement</span><span class="sxs-lookup"><span data-stu-id="00f60-152">How to: Create a Custom Binding Using the SecurityBindingElement</span></span>](../../../wcf/feature-details/how-to-create-a-custom-binding-using-the-securitybindingelement.md)
- [<span data-ttu-id="00f60-153">Sicherheit mit benutzerdefinierten Bindungen</span><span class="sxs-lookup"><span data-stu-id="00f60-153">Custom Binding Security</span></span>](../../../wcf/samples/custom-binding-security.md)
