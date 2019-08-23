---
title: <add> von <claimTypeRequirements>
ms.date: 03/30/2017
ms.assetid: c68e83c9-39e8-4264-b1ce-b6a9eb5b98aa
ms.openlocfilehash: 7e7f0eac41e69e959aa6c4f8f3cfb488d4ea2917
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69926800"
---
# <a name="add-of-claimtyperequirements"></a><span data-ttu-id="1675a-102">\<Fügen Sie > \<von claimtyperequirequirements hinzu ></span><span class="sxs-lookup"><span data-stu-id="1675a-102">\<add> of \<claimTypeRequirements></span></span>
<span data-ttu-id="1675a-103">Gibt die Typen der erforderlichen und optionalen Ansprüche an, die in verbundenen Anmeldeinformationen vorhanden sein sollen.</span><span class="sxs-lookup"><span data-stu-id="1675a-103">Specifies the types of required and optional claims expected to appear in the federated credential.</span></span> <span data-ttu-id="1675a-104">Zum Beispiel geben die Dienste die Anforderungen für eingehende Anmeldeinformationen an, die einen bestimmten Satz von Anspruchstypen verarbeiten müssen.</span><span class="sxs-lookup"><span data-stu-id="1675a-104">For example, services state the requirements on incoming credentials, which must possess a certain set of claim types.</span></span>  
  
 <span data-ttu-id="1675a-105">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="1675a-105">\<system.serviceModel></span></span>  
<span data-ttu-id="1675a-106">\<bindings></span><span class="sxs-lookup"><span data-stu-id="1675a-106">\<bindings></span></span>  
<span data-ttu-id="1675a-107">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="1675a-107">\<customBinding></span></span>  
<span data-ttu-id="1675a-108">\<binding></span><span class="sxs-lookup"><span data-stu-id="1675a-108">\<binding></span></span>  
<span data-ttu-id="1675a-109">\<security></span><span class="sxs-lookup"><span data-stu-id="1675a-109">\<security></span></span>  
<span data-ttu-id="1675a-110">\<issuedTokenParameters></span><span class="sxs-lookup"><span data-stu-id="1675a-110">\<issuedTokenParameters></span></span>  
<span data-ttu-id="1675a-111">\<claimTypeRequirements></span><span class="sxs-lookup"><span data-stu-id="1675a-111">\<claimTypeRequirements></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1675a-112">Syntax</span><span class="sxs-lookup"><span data-stu-id="1675a-112">Syntax</span></span>  
  
```xml  
<claimTypeRequirements>
  <add claimType="URI"
       isOptional="Boolean" />
</claimTypeRequirements>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="1675a-113">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="1675a-113">Attributes and Elements</span></span>  
 <span data-ttu-id="1675a-114">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="1675a-114">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="1675a-115">Attribute</span><span class="sxs-lookup"><span data-stu-id="1675a-115">Attributes</span></span>  
  
|<span data-ttu-id="1675a-116">Attribut</span><span class="sxs-lookup"><span data-stu-id="1675a-116">Attribute</span></span>|<span data-ttu-id="1675a-117">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="1675a-117">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="1675a-118">claimType</span><span class="sxs-lookup"><span data-stu-id="1675a-118">claimType</span></span>|<span data-ttu-id="1675a-119">Ein URI, der den Typ eines Anspruchs definiert.</span><span class="sxs-lookup"><span data-stu-id="1675a-119">A URI that defines the type of a claim.</span></span> <span data-ttu-id="1675a-120">Wenn ein Benutzer zum Beispiel ein Produkt auf einer Website erwerben möchte, muss er eine gültige Kreditkarte mit einem ausreichend hohen Kreditrahmen vorlegen.</span><span class="sxs-lookup"><span data-stu-id="1675a-120">For example, to purchase a product from a Web site, the user must present a valid credit card with sufficient credit limit.</span></span> <span data-ttu-id="1675a-121">Der Anspruchstyp wäre der Kreditkarten-URI.</span><span class="sxs-lookup"><span data-stu-id="1675a-121">The claim type would be the credit card URI.</span></span>|  
|<span data-ttu-id="1675a-122">isOptional</span><span class="sxs-lookup"><span data-stu-id="1675a-122">isOptional</span></span>|<span data-ttu-id="1675a-123">Ein boolescher Wert, der angibt, ob der Anspruch optional ist.</span><span class="sxs-lookup"><span data-stu-id="1675a-123">A Boolean value that specifies if this is for an optional claim.</span></span> <span data-ttu-id="1675a-124">Legen Sie dieses Attribut auf `false` fest, wenn dies ein erforderlicher Anspruch ist.</span><span class="sxs-lookup"><span data-stu-id="1675a-124">Set this attribute to `false` if this is a required claim.</span></span><br /><br /> <span data-ttu-id="1675a-125">Sie können dieses Attribut verwenden, wenn der Dienst um Informationen bittet, aber es nicht erfordert.</span><span class="sxs-lookup"><span data-stu-id="1675a-125">You can use this attribute when the service asks for some information but does not require it.</span></span> <span data-ttu-id="1675a-126">Wenn der Benutzer z.&#160;B. seinen Vornamen, Nachnamen und seine Adresse eingeben muss, die Eingabe der Telefonnummer jedoch optional ist.</span><span class="sxs-lookup"><span data-stu-id="1675a-126">For example, if you require the user to enter his/her first name, last name and address, but decide that phone number is optional.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="1675a-127">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="1675a-127">Child Elements</span></span>  
 <span data-ttu-id="1675a-128">Keine</span><span class="sxs-lookup"><span data-stu-id="1675a-128">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="1675a-129">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="1675a-129">Parent Elements</span></span>  
  
|<span data-ttu-id="1675a-130">Element</span><span class="sxs-lookup"><span data-stu-id="1675a-130">Element</span></span>|<span data-ttu-id="1675a-131">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="1675a-131">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="1675a-132">\<claimTypeRequirements></span><span class="sxs-lookup"><span data-stu-id="1675a-132">\<claimTypeRequirements></span></span>](claimtyperequirements-element.md)|<span data-ttu-id="1675a-133">Gibt eine Auflistung von erforderlichen Anspruchstypen an.</span><span class="sxs-lookup"><span data-stu-id="1675a-133">Specifies a collection of required claim types.</span></span><br /><br /> <span data-ttu-id="1675a-134">In einem verbundenen Szenario legen Dienste die Anforderungen für eingehende Anmeldeinformationen fest.</span><span class="sxs-lookup"><span data-stu-id="1675a-134">In a federated scenario, services state the requirements on incoming credentials.</span></span> <span data-ttu-id="1675a-135">Zum Beispiel müssen die eingehenden Anmeldeinformationen einen bestimmten Satz an Anspruchstypen aufweisen.</span><span class="sxs-lookup"><span data-stu-id="1675a-135">For example, the incoming credentials must possess a certain set of claim types.</span></span> <span data-ttu-id="1675a-136">Jedes Element in dieser Auflistung gibt die Typen der erforderlichen und optionalen Ansprüche an, die in verbundenen Anmeldeinformationen vorhanden sein sollen.</span><span class="sxs-lookup"><span data-stu-id="1675a-136">Each element in this collection specifies the types of required and optional claims expected to appear in a federated credential.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="1675a-137">Hinweise</span><span class="sxs-lookup"><span data-stu-id="1675a-137">Remarks</span></span>  
 <span data-ttu-id="1675a-138">In einem verbundenen Szenario legen Dienste die Anforderungen für eingehende Anmeldeinformationen fest.</span><span class="sxs-lookup"><span data-stu-id="1675a-138">In a federated scenario, services state the requirements on incoming credentials.</span></span> <span data-ttu-id="1675a-139">Zum Beispiel müssen die eingehenden Anmeldeinformationen einen bestimmten Satz an Anspruchstypen aufweisen.</span><span class="sxs-lookup"><span data-stu-id="1675a-139">For example, the incoming credentials must possess a certain set of claim types.</span></span> <span data-ttu-id="1675a-140">Diese Anforderung wird sich in einer Sicherheitsrichtlinie auswirken.</span><span class="sxs-lookup"><span data-stu-id="1675a-140">This requirement is manifested in a security policy.</span></span> <span data-ttu-id="1675a-141">Wenn ein Client Anmeldeinformationen von einem Verbunddienst anfordert (z.&#160;B. CardSpace), legt er die Anforderungen in einer Tokenanforderung (RequestSecurityToken) ab, sodass der Verbunddienst die Anmeldeinformationen ausgeben kann, die die Anforderungen entsprechend erfüllen.</span><span class="sxs-lookup"><span data-stu-id="1675a-141">When a client requests credentials from a federated service (for example, CardSpace), it puts the requirements into a token request (RequestSecurityToken) so that the federated service can issue the credentials that satisfy the requirements accordingly.</span></span>  
  
## <a name="example"></a><span data-ttu-id="1675a-142">Beispiel</span><span class="sxs-lookup"><span data-stu-id="1675a-142">Example</span></span>  
 <span data-ttu-id="1675a-143">Die folgende Konfiguration fügt einer Sicherheitsbindung zwei Anspruchstypanforderungen hinzu.</span><span class="sxs-lookup"><span data-stu-id="1675a-143">The following configuration adds two claim type requirements to a security binding.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="1675a-144">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="1675a-144">See also</span></span>

- <xref:System.ServiceModel.Security.Tokens.ClaimTypeRequirement>
- <xref:System.ServiceModel.Security.Tokens.IssuedSecurityTokenParameters.ClaimTypeRequirements%2A>
- <xref:System.ServiceModel.Configuration.IssuedTokenParametersElement.ClaimTypeRequirements%2A>
- <xref:System.ServiceModel.Configuration.ClaimTypeElementCollection>
- <xref:System.ServiceModel.Configuration.ClaimTypeElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [<span data-ttu-id="1675a-145">\<claimTypeRequirements></span><span class="sxs-lookup"><span data-stu-id="1675a-145">\<claimTypeRequirements></span></span>](claimtyperequirements-element.md)
- [<span data-ttu-id="1675a-146">Bindungen</span><span class="sxs-lookup"><span data-stu-id="1675a-146">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="1675a-147">Erweitern von Bindungen</span><span class="sxs-lookup"><span data-stu-id="1675a-147">Extending Bindings</span></span>](../../../wcf/extending/extending-bindings.md)
- [<span data-ttu-id="1675a-148">Benutzerdefinierte Bindungen</span><span class="sxs-lookup"><span data-stu-id="1675a-148">Custom Bindings</span></span>](../../../wcf/extending/custom-bindings.md)
- [<span data-ttu-id="1675a-149">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="1675a-149">\<customBinding></span></span>](custombinding.md)
- [<span data-ttu-id="1675a-150">Vorgehensweise: Erstellen einer benutzerdefinierten Bindung mit dem SecurityBindingElement</span><span class="sxs-lookup"><span data-stu-id="1675a-150">How to: Create a Custom Binding Using the SecurityBindingElement</span></span>](../../../wcf/feature-details/how-to-create-a-custom-binding-using-the-securitybindingelement.md)
- [<span data-ttu-id="1675a-151">Sicherheit mit benutzerdefinierten Bindungen</span><span class="sxs-lookup"><span data-stu-id="1675a-151">Custom Binding Security</span></span>](../../../wcf/samples/custom-binding-security.md)
