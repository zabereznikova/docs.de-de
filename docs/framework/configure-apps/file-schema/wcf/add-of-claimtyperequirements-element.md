---
title: '&lt;add&gt; des &lt;claimTypeRequirements&gt;-Elements'
ms.date: 03/30/2017
ms.assetid: 3234cd45-1478-468e-8b19-5c50815c4786
ms.openlocfilehash: 7f86073d0ecce353c63f31fd28c4bfeffb2411ed
ms.sourcegitcommit: 4ac80713f6faa220e5a119d5165308a58f7ccdc8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/09/2019
ms.locfileid: "54145548"
---
# <a name="ltaddgt-of-ltclaimtyperequirementsgt-element"></a><span data-ttu-id="92a2c-102">&lt;add&gt; des &lt;claimTypeRequirements&gt;-Elements</span><span class="sxs-lookup"><span data-stu-id="92a2c-102">&lt;add&gt; of &lt;claimTypeRequirements&gt; element</span></span>
<span data-ttu-id="92a2c-103">Gibt die Typen der erforderlichen und optionalen Ansprüche an, die in verbundenen Anmeldeinformationen vorhanden sein sollen.</span><span class="sxs-lookup"><span data-stu-id="92a2c-103">Specifies the types of required and optional claims expected to appear in the federated credential.</span></span> <span data-ttu-id="92a2c-104">Zum Beispiel geben die Dienste die Anforderungen für eingehende Anmeldeinformationen an, die einen bestimmten Satz von Anspruchstypen verarbeiten müssen.</span><span class="sxs-lookup"><span data-stu-id="92a2c-104">For example, services state the requirements on incoming credentials, which must possess a certain set of claim types.</span></span>  
  
 <span data-ttu-id="92a2c-105">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="92a2c-105">\<system.ServiceModel></span></span>  
<span data-ttu-id="92a2c-106">\<bindings></span><span class="sxs-lookup"><span data-stu-id="92a2c-106">\<bindings></span></span>  
<span data-ttu-id="92a2c-107">\<wsFederatedBinding></span><span class="sxs-lookup"><span data-stu-id="92a2c-107">\<wsFederatedBinding></span></span>  
<span data-ttu-id="92a2c-108">\<binding></span><span class="sxs-lookup"><span data-stu-id="92a2c-108">\<binding></span></span>  
<span data-ttu-id="92a2c-109">\<Sicherheit ></span><span class="sxs-lookup"><span data-stu-id="92a2c-109">\<security></span></span>  
<span data-ttu-id="92a2c-110">\<Meldung ></span><span class="sxs-lookup"><span data-stu-id="92a2c-110">\<message></span></span>  
<span data-ttu-id="92a2c-111">\<ClaimTypeRequirements ></span><span class="sxs-lookup"><span data-stu-id="92a2c-111">\<claimTypeRequirements></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="92a2c-112">Syntax</span><span class="sxs-lookup"><span data-stu-id="92a2c-112">Syntax</span></span>  
  
```xml  
<claimTypeRequirements>
  <add claimType="URI"
       isOptional="Boolean" />
</claimTypeRequirements>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="92a2c-113">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="92a2c-113">Attributes and Elements</span></span>  
 <span data-ttu-id="92a2c-114">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="92a2c-114">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="92a2c-115">Attribute</span><span class="sxs-lookup"><span data-stu-id="92a2c-115">Attributes</span></span>  
  
|<span data-ttu-id="92a2c-116">Attribut</span><span class="sxs-lookup"><span data-stu-id="92a2c-116">Attribute</span></span>|<span data-ttu-id="92a2c-117">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="92a2c-117">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="92a2c-118">claimType</span><span class="sxs-lookup"><span data-stu-id="92a2c-118">claimType</span></span>|<span data-ttu-id="92a2c-119">Ein URI, der den Typ eines Anspruchs definiert.</span><span class="sxs-lookup"><span data-stu-id="92a2c-119">A URI that defines the type of a claim.</span></span> <span data-ttu-id="92a2c-120">Wenn ein Benutzer zum Beispiel ein Produkt auf einer Website erwerben möchte, muss er eine gültige Kreditkarte mit einem ausreichend hohen Kreditrahmen vorlegen.</span><span class="sxs-lookup"><span data-stu-id="92a2c-120">For example, to purchase a product from a Web site, the user must present a valid credit card with sufficient credit limit.</span></span> <span data-ttu-id="92a2c-121">Der Anspruchstyp wäre der Kreditkarten-URI.</span><span class="sxs-lookup"><span data-stu-id="92a2c-121">The claim type would be the credit card URI.</span></span>|  
|<span data-ttu-id="92a2c-122">isOptional</span><span class="sxs-lookup"><span data-stu-id="92a2c-122">isOptional</span></span>|<span data-ttu-id="92a2c-123">Ein boolescher Wert, der angibt, ob der Anspruch optional ist.</span><span class="sxs-lookup"><span data-stu-id="92a2c-123">A Boolean value that specifies if this is for an optional claim.</span></span> <span data-ttu-id="92a2c-124">Legen Sie dieses Attribut auf `false` fest, wenn dies ein erforderlicher Anspruch ist.</span><span class="sxs-lookup"><span data-stu-id="92a2c-124">Set this attribute to `false` if this is a required claim.</span></span><br /><br /> <span data-ttu-id="92a2c-125">Sie können dieses Attribut verwenden, wenn der Dienst um Informationen bittet, aber es nicht erfordert.</span><span class="sxs-lookup"><span data-stu-id="92a2c-125">You can use this attribute when the service asks for some information but does not require it.</span></span> <span data-ttu-id="92a2c-126">Wenn der Benutzer z.&#160;B. seinen Vornamen, Nachnamen und seine Adresse eingeben muss, die Eingabe der Telefonnummer jedoch optional ist.</span><span class="sxs-lookup"><span data-stu-id="92a2c-126">For example, if you require the user to enter his/her first name, last name and address, but decide that phone number is optional.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="92a2c-127">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="92a2c-127">Child Elements</span></span>  
 <span data-ttu-id="92a2c-128">Keine</span><span class="sxs-lookup"><span data-stu-id="92a2c-128">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="92a2c-129">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="92a2c-129">Parent Elements</span></span>  
  
|<span data-ttu-id="92a2c-130">Element</span><span class="sxs-lookup"><span data-stu-id="92a2c-130">Element</span></span>|<span data-ttu-id="92a2c-131">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="92a2c-131">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="92a2c-132">\<claimTypeRequirements></span><span class="sxs-lookup"><span data-stu-id="92a2c-132">\<claimTypeRequirements></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/claimtyperequirements-for-message.md)|<span data-ttu-id="92a2c-133">Gibt eine Auflistung von erforderlichen Anspruchstypen an.</span><span class="sxs-lookup"><span data-stu-id="92a2c-133">Specifies a collection of required claim types.</span></span> <span data-ttu-id="92a2c-134">Jedes Element ist vom Typ <xref:System.ServiceModel.Configuration.ClaimTypeElement>.</span><span class="sxs-lookup"><span data-stu-id="92a2c-134">Each element is of type <xref:System.ServiceModel.Configuration.ClaimTypeElement>.</span></span><br /><br /> <span data-ttu-id="92a2c-135">In einem verbundenen Szenario legen Dienste die Anforderungen für eingehende Anmeldeinformationen fest.</span><span class="sxs-lookup"><span data-stu-id="92a2c-135">In a federated scenario, services state the requirements on incoming credentials.</span></span> <span data-ttu-id="92a2c-136">Zum Beispiel müssen die eingehenden Anmeldeinformationen einen bestimmten Satz an Anspruchstypen aufweisen.</span><span class="sxs-lookup"><span data-stu-id="92a2c-136">For example, the incoming credentials must possess a certain set of claim types.</span></span> <span data-ttu-id="92a2c-137">Jedes Element in dieser Auflistung gibt die Typen der erforderlichen und optionalen Ansprüche an, die in verbundenen Anmeldeinformationen vorhanden sein sollen.</span><span class="sxs-lookup"><span data-stu-id="92a2c-137">Each element in this collection specifies the types of required and optional claims expected to appear in a federated credential.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="92a2c-138">Hinweise</span><span class="sxs-lookup"><span data-stu-id="92a2c-138">Remarks</span></span>  
 <span data-ttu-id="92a2c-139">In einem verbundenen Szenario legen Dienste die Anforderungen für eingehende Anmeldeinformationen fest.</span><span class="sxs-lookup"><span data-stu-id="92a2c-139">In a federated scenario, services state the requirements on incoming credentials.</span></span> <span data-ttu-id="92a2c-140">Zum Beispiel müssen die eingehenden Anmeldeinformationen einen bestimmten Satz an Anspruchstypen aufweisen.</span><span class="sxs-lookup"><span data-stu-id="92a2c-140">For example, the incoming credentials must possess a certain set of claim types.</span></span> <span data-ttu-id="92a2c-141">Diese Anforderung wird sich in einer Sicherheitsrichtlinie auswirken.</span><span class="sxs-lookup"><span data-stu-id="92a2c-141">This requirement is manifested in a security policy.</span></span> <span data-ttu-id="92a2c-142">Wenn ein Client Anmeldeinformationen von einem Verbunddienst anfordert (z.&#160;B. CardSpace), legt er die Anforderungen in einer Tokenanforderung (RequestSecurityToken) ab, sodass der Verbunddienst die Anmeldeinformationen ausgeben kann, die die Anforderungen entsprechend erfüllen.</span><span class="sxs-lookup"><span data-stu-id="92a2c-142">When a client requests credentials from a federated service (for example, CardSpace), it puts the requirements into a token request (RequestSecurityToken) so that the federated service can issue the credentials that satisfy the requirements accordingly.</span></span>  
  
## <a name="example"></a><span data-ttu-id="92a2c-143">Beispiel</span><span class="sxs-lookup"><span data-stu-id="92a2c-143">Example</span></span>  
 <span data-ttu-id="92a2c-144">Die folgende Konfiguration fügt einer Sicherheitsbindung zwei Anspruchstypanforderungen hinzu.</span><span class="sxs-lookup"><span data-stu-id="92a2c-144">The following configuration adds two claim type requirements to a security binding.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="92a2c-145">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="92a2c-145">See Also</span></span>  
 <xref:System.ServiceModel.FederatedMessageSecurityOverHttp.ClaimTypeRequirements%2A>  
 <xref:System.ServiceModel.Security.Tokens.ClaimTypeRequirement>  
 <xref:System.ServiceModel.Configuration.FederatedMessageSecurityOverHttpElement.ClaimTypeRequirements%2A>  
 <xref:System.ServiceModel.Configuration.ClaimTypeElementCollection>  
 <xref:System.ServiceModel.Configuration.ClaimTypeElement>
