---
title: <add> des <claimTypeRequirements>-Elements
ms.date: 03/30/2017
ms.assetid: 3234cd45-1478-468e-8b19-5c50815c4786
ms.openlocfilehash: 47eb9f95fd024b7df24a16781b3d89fe6deb0b8c
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59222184"
---
# <a name="add-of-claimtyperequirements-element"></a><span data-ttu-id="278fd-102">\<add> of \<claimTypeRequirements> element</span><span class="sxs-lookup"><span data-stu-id="278fd-102">\<add> of \<claimTypeRequirements> element</span></span>
<span data-ttu-id="278fd-103">Gibt die Typen der erforderlichen und optionalen Ansprüche an, die in verbundenen Anmeldeinformationen vorhanden sein sollen.</span><span class="sxs-lookup"><span data-stu-id="278fd-103">Specifies the types of required and optional claims expected to appear in the federated credential.</span></span> <span data-ttu-id="278fd-104">Zum Beispiel geben die Dienste die Anforderungen für eingehende Anmeldeinformationen an, die einen bestimmten Satz von Anspruchstypen verarbeiten müssen.</span><span class="sxs-lookup"><span data-stu-id="278fd-104">For example, services state the requirements on incoming credentials, which must possess a certain set of claim types.</span></span>  
  
 <span data-ttu-id="278fd-105">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="278fd-105">\<system.ServiceModel></span></span>  
<span data-ttu-id="278fd-106">\<bindings></span><span class="sxs-lookup"><span data-stu-id="278fd-106">\<bindings></span></span>  
<span data-ttu-id="278fd-107">\<wsFederatedBinding></span><span class="sxs-lookup"><span data-stu-id="278fd-107">\<wsFederatedBinding></span></span>  
<span data-ttu-id="278fd-108">\<binding></span><span class="sxs-lookup"><span data-stu-id="278fd-108">\<binding></span></span>  
<span data-ttu-id="278fd-109">\<security></span><span class="sxs-lookup"><span data-stu-id="278fd-109">\<security></span></span>  
<span data-ttu-id="278fd-110">\<message></span><span class="sxs-lookup"><span data-stu-id="278fd-110">\<message></span></span>  
<span data-ttu-id="278fd-111">\<claimTypeRequirements></span><span class="sxs-lookup"><span data-stu-id="278fd-111">\<claimTypeRequirements></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="278fd-112">Syntax</span><span class="sxs-lookup"><span data-stu-id="278fd-112">Syntax</span></span>  
  
```xml  
<claimTypeRequirements>
  <add claimType="URI"
       isOptional="Boolean" />
</claimTypeRequirements>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="278fd-113">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="278fd-113">Attributes and Elements</span></span>  
 <span data-ttu-id="278fd-114">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="278fd-114">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="278fd-115">Attribute</span><span class="sxs-lookup"><span data-stu-id="278fd-115">Attributes</span></span>  
  
|<span data-ttu-id="278fd-116">Attribut</span><span class="sxs-lookup"><span data-stu-id="278fd-116">Attribute</span></span>|<span data-ttu-id="278fd-117">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="278fd-117">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="278fd-118">claimType</span><span class="sxs-lookup"><span data-stu-id="278fd-118">claimType</span></span>|<span data-ttu-id="278fd-119">Ein URI, der den Typ eines Anspruchs definiert.</span><span class="sxs-lookup"><span data-stu-id="278fd-119">A URI that defines the type of a claim.</span></span> <span data-ttu-id="278fd-120">Wenn ein Benutzer zum Beispiel ein Produkt auf einer Website erwerben möchte, muss er eine gültige Kreditkarte mit einem ausreichend hohen Kreditrahmen vorlegen.</span><span class="sxs-lookup"><span data-stu-id="278fd-120">For example, to purchase a product from a Web site, the user must present a valid credit card with sufficient credit limit.</span></span> <span data-ttu-id="278fd-121">Der Anspruchstyp wäre der Kreditkarten-URI.</span><span class="sxs-lookup"><span data-stu-id="278fd-121">The claim type would be the credit card URI.</span></span>|  
|<span data-ttu-id="278fd-122">isOptional</span><span class="sxs-lookup"><span data-stu-id="278fd-122">isOptional</span></span>|<span data-ttu-id="278fd-123">Ein boolescher Wert, der angibt, ob der Anspruch optional ist.</span><span class="sxs-lookup"><span data-stu-id="278fd-123">A Boolean value that specifies if this is for an optional claim.</span></span> <span data-ttu-id="278fd-124">Legen Sie dieses Attribut auf `false` fest, wenn dies ein erforderlicher Anspruch ist.</span><span class="sxs-lookup"><span data-stu-id="278fd-124">Set this attribute to `false` if this is a required claim.</span></span><br /><br /> <span data-ttu-id="278fd-125">Sie können dieses Attribut verwenden, wenn der Dienst um Informationen bittet, aber es nicht erfordert.</span><span class="sxs-lookup"><span data-stu-id="278fd-125">You can use this attribute when the service asks for some information but does not require it.</span></span> <span data-ttu-id="278fd-126">Wenn der Benutzer z.&amp;#160;B. seinen Vornamen, Nachnamen und seine Adresse eingeben muss, die Eingabe der Telefonnummer jedoch optional ist.</span><span class="sxs-lookup"><span data-stu-id="278fd-126">For example, if you require the user to enter his/her first name, last name and address, but decide that phone number is optional.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="278fd-127">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="278fd-127">Child Elements</span></span>  
 <span data-ttu-id="278fd-128">Keine</span><span class="sxs-lookup"><span data-stu-id="278fd-128">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="278fd-129">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="278fd-129">Parent Elements</span></span>  
  
|<span data-ttu-id="278fd-130">Element</span><span class="sxs-lookup"><span data-stu-id="278fd-130">Element</span></span>|<span data-ttu-id="278fd-131">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="278fd-131">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="278fd-132">\<claimTypeRequirements></span><span class="sxs-lookup"><span data-stu-id="278fd-132">\<claimTypeRequirements></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/claimtyperequirements-for-message.md)|<span data-ttu-id="278fd-133">Gibt eine Auflistung von erforderlichen Anspruchstypen an.</span><span class="sxs-lookup"><span data-stu-id="278fd-133">Specifies a collection of required claim types.</span></span> <span data-ttu-id="278fd-134">Jedes Element ist vom Typ <xref:System.ServiceModel.Configuration.ClaimTypeElement>.</span><span class="sxs-lookup"><span data-stu-id="278fd-134">Each element is of type <xref:System.ServiceModel.Configuration.ClaimTypeElement>.</span></span><br /><br /> <span data-ttu-id="278fd-135">In einem verbundenen Szenario legen Dienste die Anforderungen für eingehende Anmeldeinformationen fest.</span><span class="sxs-lookup"><span data-stu-id="278fd-135">In a federated scenario, services state the requirements on incoming credentials.</span></span> <span data-ttu-id="278fd-136">Zum Beispiel müssen die eingehenden Anmeldeinformationen einen bestimmten Satz an Anspruchstypen aufweisen.</span><span class="sxs-lookup"><span data-stu-id="278fd-136">For example, the incoming credentials must possess a certain set of claim types.</span></span> <span data-ttu-id="278fd-137">Jedes Element in dieser Auflistung gibt die Typen der erforderlichen und optionalen Ansprüche an, die in verbundenen Anmeldeinformationen vorhanden sein sollen.</span><span class="sxs-lookup"><span data-stu-id="278fd-137">Each element in this collection specifies the types of required and optional claims expected to appear in a federated credential.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="278fd-138">Hinweise</span><span class="sxs-lookup"><span data-stu-id="278fd-138">Remarks</span></span>  
 <span data-ttu-id="278fd-139">In einem verbundenen Szenario legen Dienste die Anforderungen für eingehende Anmeldeinformationen fest.</span><span class="sxs-lookup"><span data-stu-id="278fd-139">In a federated scenario, services state the requirements on incoming credentials.</span></span> <span data-ttu-id="278fd-140">Zum Beispiel müssen die eingehenden Anmeldeinformationen einen bestimmten Satz an Anspruchstypen aufweisen.</span><span class="sxs-lookup"><span data-stu-id="278fd-140">For example, the incoming credentials must possess a certain set of claim types.</span></span> <span data-ttu-id="278fd-141">Diese Anforderung wird sich in einer Sicherheitsrichtlinie auswirken.</span><span class="sxs-lookup"><span data-stu-id="278fd-141">This requirement is manifested in a security policy.</span></span> <span data-ttu-id="278fd-142">Wenn ein Client Anmeldeinformationen von einem Verbunddienst anfordert (z.&amp;#160;B. CardSpace), legt er die Anforderungen in einer Tokenanforderung (RequestSecurityToken) ab, sodass der Verbunddienst die Anmeldeinformationen ausgeben kann, die die Anforderungen entsprechend erfüllen.</span><span class="sxs-lookup"><span data-stu-id="278fd-142">When a client requests credentials from a federated service (for example, CardSpace), it puts the requirements into a token request (RequestSecurityToken) so that the federated service can issue the credentials that satisfy the requirements accordingly.</span></span>  
  
## <a name="example"></a><span data-ttu-id="278fd-143">Beispiel</span><span class="sxs-lookup"><span data-stu-id="278fd-143">Example</span></span>  
 <span data-ttu-id="278fd-144">Die folgende Konfiguration fügt einer Sicherheitsbindung zwei Anspruchstypanforderungen hinzu.</span><span class="sxs-lookup"><span data-stu-id="278fd-144">The following configuration adds two claim type requirements to a security binding.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="278fd-145">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="278fd-145">See also</span></span>

- <xref:System.ServiceModel.FederatedMessageSecurityOverHttp.ClaimTypeRequirements%2A>
- <xref:System.ServiceModel.Security.Tokens.ClaimTypeRequirement>
- <xref:System.ServiceModel.Configuration.FederatedMessageSecurityOverHttpElement.ClaimTypeRequirements%2A>
- <xref:System.ServiceModel.Configuration.ClaimTypeElementCollection>
- <xref:System.ServiceModel.Configuration.ClaimTypeElement>
