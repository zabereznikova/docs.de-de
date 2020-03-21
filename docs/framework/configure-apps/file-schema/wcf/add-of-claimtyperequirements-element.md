---
title: <add> des <claimTypeRequirements>-Elements
ms.date: 03/30/2017
ms.assetid: 3234cd45-1478-468e-8b19-5c50815c4786
ms.openlocfilehash: f6948052c62684faa734b592f5bdfc2e7827a07a
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79153099"
---
# <a name="add-of-claimtyperequirements-element"></a><span data-ttu-id="8f81d-102">\<Hinzufügen> \<von claimTypeRequirements>-Element</span><span class="sxs-lookup"><span data-stu-id="8f81d-102">\<add> of \<claimTypeRequirements> element</span></span>
<span data-ttu-id="8f81d-103">Gibt die Typen der erforderlichen und optionalen Ansprüche an, die in verbundenen Anmeldeinformationen vorhanden sein sollen.</span><span class="sxs-lookup"><span data-stu-id="8f81d-103">Specifies the types of required and optional claims expected to appear in the federated credential.</span></span> <span data-ttu-id="8f81d-104">Zum Beispiel geben die Dienste die Anforderungen für eingehende Anmeldeinformationen an, die einen bestimmten Satz von Anspruchstypen verarbeiten müssen.</span><span class="sxs-lookup"><span data-stu-id="8f81d-104">For example, services state the requirements on incoming credentials, which must possess a certain set of claim types.</span></span>  
  
<span data-ttu-id="8f81d-105">[**\<Konfiguration>**](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="8f81d-105">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="8f81d-106">&nbsp;&nbsp;[**\<system.serviceModell>**](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="8f81d-106">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="8f81d-107">&nbsp;&nbsp;&nbsp;&nbsp;[**\<Bindungen>**](bindings.md)</span><span class="sxs-lookup"><span data-stu-id="8f81d-107">&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)</span></span>\
<span data-ttu-id="8f81d-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<wsFederationHttpBinding>**](wsfederationhttpbinding.md)</span><span class="sxs-lookup"><span data-stu-id="8f81d-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<wsFederationHttpBinding>**](wsfederationhttpbinding.md)</span></span>\
<span data-ttu-id="8f81d-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<verbindliche>**</span><span class="sxs-lookup"><span data-stu-id="8f81d-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**</span></span>\
<span data-ttu-id="8f81d-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<Sicherheits->**](security-of-custombinding.md)</span><span class="sxs-lookup"><span data-stu-id="8f81d-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<security>**](security-of-custombinding.md)</span></span>\
<span data-ttu-id="8f81d-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<Nachricht>**](message-element-of-wsfederationhttpbinding.md)</span><span class="sxs-lookup"><span data-stu-id="8f81d-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<message>**](message-element-of-wsfederationhttpbinding.md)</span></span>\
<span data-ttu-id="8f81d-112">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<claimTypeRequirements>**](claimtyperequirements-for-message.md)</span><span class="sxs-lookup"><span data-stu-id="8f81d-112">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<claimTypeRequirements>**](claimtyperequirements-for-message.md)</span></span>\
<span data-ttu-id="8f81d-113">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<hinzufügen>**</span><span class="sxs-lookup"><span data-stu-id="8f81d-113">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**</span></span>
  
## <a name="syntax"></a><span data-ttu-id="8f81d-114">Syntax</span><span class="sxs-lookup"><span data-stu-id="8f81d-114">Syntax</span></span>  
  
```xml  
<claimTypeRequirements>
  <add claimType="URI"
       isOptional="Boolean" />
</claimTypeRequirements>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="8f81d-115">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="8f81d-115">Attributes and Elements</span></span>  
 <span data-ttu-id="8f81d-116">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="8f81d-116">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="8f81d-117">Attributes</span><span class="sxs-lookup"><span data-stu-id="8f81d-117">Attributes</span></span>  
  
|<span data-ttu-id="8f81d-118">attribute</span><span class="sxs-lookup"><span data-stu-id="8f81d-118">Attribute</span></span>|<span data-ttu-id="8f81d-119">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="8f81d-119">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="8f81d-120">claimType</span><span class="sxs-lookup"><span data-stu-id="8f81d-120">claimType</span></span>|<span data-ttu-id="8f81d-121">Ein URI, der den Typ eines Anspruchs definiert.</span><span class="sxs-lookup"><span data-stu-id="8f81d-121">A URI that defines the type of a claim.</span></span> <span data-ttu-id="8f81d-122">Wenn ein Benutzer zum Beispiel ein Produkt auf einer Website erwerben möchte, muss er eine gültige Kreditkarte mit einem ausreichend hohen Kreditrahmen vorlegen.</span><span class="sxs-lookup"><span data-stu-id="8f81d-122">For example, to purchase a product from a Web site, the user must present a valid credit card with sufficient credit limit.</span></span> <span data-ttu-id="8f81d-123">Der Anspruchstyp wäre der Kreditkarten-URI.</span><span class="sxs-lookup"><span data-stu-id="8f81d-123">The claim type would be the credit card URI.</span></span>|  
|<span data-ttu-id="8f81d-124">isOptional</span><span class="sxs-lookup"><span data-stu-id="8f81d-124">isOptional</span></span>|<span data-ttu-id="8f81d-125">Ein boolescher Wert, der angibt, ob der Anspruch optional ist.</span><span class="sxs-lookup"><span data-stu-id="8f81d-125">A Boolean value that specifies if this is for an optional claim.</span></span> <span data-ttu-id="8f81d-126">Legen Sie dieses Attribut auf `false` fest, wenn dies ein erforderlicher Anspruch ist.</span><span class="sxs-lookup"><span data-stu-id="8f81d-126">Set this attribute to `false` if this is a required claim.</span></span><br /><br /> <span data-ttu-id="8f81d-127">Sie können dieses Attribut verwenden, wenn der Dienst um Informationen bittet, aber es nicht erfordert.</span><span class="sxs-lookup"><span data-stu-id="8f81d-127">You can use this attribute when the service asks for some information but does not require it.</span></span> <span data-ttu-id="8f81d-128">Wenn Sie z. B. verlangen, dass der Benutzer seinen Vornamen, Nachnamen und seine Adresse eingibt, diese Telefonnummer jedoch optional ist.</span><span class="sxs-lookup"><span data-stu-id="8f81d-128">For example, if you require the user to enter their first name, last name, and address, but decide that phone number is optional.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="8f81d-129">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="8f81d-129">Child Elements</span></span>  
 <span data-ttu-id="8f81d-130">Keine.</span><span class="sxs-lookup"><span data-stu-id="8f81d-130">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="8f81d-131">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="8f81d-131">Parent Elements</span></span>  
  
|<span data-ttu-id="8f81d-132">Element</span><span class="sxs-lookup"><span data-stu-id="8f81d-132">Element</span></span>|<span data-ttu-id="8f81d-133">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="8f81d-133">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="8f81d-134">\<claimTypeRequirements></span><span class="sxs-lookup"><span data-stu-id="8f81d-134">\<claimTypeRequirements></span></span>](claimtyperequirements-for-message.md)|<span data-ttu-id="8f81d-135">Gibt eine Auflistung von erforderlichen Anspruchstypen an.</span><span class="sxs-lookup"><span data-stu-id="8f81d-135">Specifies a collection of required claim types.</span></span> <span data-ttu-id="8f81d-136">Jedes Element ist vom Typ <xref:System.ServiceModel.Configuration.ClaimTypeElement>.</span><span class="sxs-lookup"><span data-stu-id="8f81d-136">Each element is of type <xref:System.ServiceModel.Configuration.ClaimTypeElement>.</span></span><br /><br /> <span data-ttu-id="8f81d-137">In einem verbundenen Szenario legen Dienste die Anforderungen für eingehende Anmeldeinformationen fest.</span><span class="sxs-lookup"><span data-stu-id="8f81d-137">In a federated scenario, services state the requirements on incoming credentials.</span></span> <span data-ttu-id="8f81d-138">Zum Beispiel müssen die eingehenden Anmeldeinformationen einen bestimmten Satz an Anspruchstypen aufweisen.</span><span class="sxs-lookup"><span data-stu-id="8f81d-138">For example, the incoming credentials must possess a certain set of claim types.</span></span> <span data-ttu-id="8f81d-139">Jedes Element in dieser Auflistung gibt die Typen der erforderlichen und optionalen Ansprüche an, die in verbundenen Anmeldeinformationen vorhanden sein sollen.</span><span class="sxs-lookup"><span data-stu-id="8f81d-139">Each element in this collection specifies the types of required and optional claims expected to appear in a federated credential.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="8f81d-140">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="8f81d-140">Remarks</span></span>  
 <span data-ttu-id="8f81d-141">In einem verbundenen Szenario legen Dienste die Anforderungen für eingehende Anmeldeinformationen fest.</span><span class="sxs-lookup"><span data-stu-id="8f81d-141">In a federated scenario, services state the requirements on incoming credentials.</span></span> <span data-ttu-id="8f81d-142">Zum Beispiel müssen die eingehenden Anmeldeinformationen einen bestimmten Satz an Anspruchstypen aufweisen.</span><span class="sxs-lookup"><span data-stu-id="8f81d-142">For example, the incoming credentials must possess a certain set of claim types.</span></span> <span data-ttu-id="8f81d-143">Diese Anforderung wird sich in einer Sicherheitsrichtlinie auswirken.</span><span class="sxs-lookup"><span data-stu-id="8f81d-143">This requirement is manifested in a security policy.</span></span> <span data-ttu-id="8f81d-144">Wenn ein Client Anmeldeinformationen von einem Verbunddienst anfordert (z.&#160;B. CardSpace), legt er die Anforderungen in einer Tokenanforderung (RequestSecurityToken) ab, sodass der Verbunddienst die Anmeldeinformationen ausgeben kann, die die Anforderungen entsprechend erfüllen.</span><span class="sxs-lookup"><span data-stu-id="8f81d-144">When a client requests credentials from a federated service (for example, CardSpace), it puts the requirements into a token request (RequestSecurityToken) so that the federated service can issue the credentials that satisfy the requirements accordingly.</span></span>  
  
## <a name="example"></a><span data-ttu-id="8f81d-145">Beispiel</span><span class="sxs-lookup"><span data-stu-id="8f81d-145">Example</span></span>  
 <span data-ttu-id="8f81d-146">Die folgende Konfiguration fügt einer Sicherheitsbindung zwei Anspruchstypanforderungen hinzu.</span><span class="sxs-lookup"><span data-stu-id="8f81d-146">The following configuration adds two claim type requirements to a security binding.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="8f81d-147">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="8f81d-147">See also</span></span>

- <xref:System.ServiceModel.FederatedMessageSecurityOverHttp.ClaimTypeRequirements%2A>
- <xref:System.ServiceModel.Security.Tokens.ClaimTypeRequirement>
- <xref:System.ServiceModel.Configuration.FederatedMessageSecurityOverHttpElement.ClaimTypeRequirements%2A>
- <xref:System.ServiceModel.Configuration.ClaimTypeElementCollection>
- <xref:System.ServiceModel.Configuration.ClaimTypeElement>
