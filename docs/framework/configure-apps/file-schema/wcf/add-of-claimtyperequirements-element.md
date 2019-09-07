---
title: <add> des <claimTypeRequirements>-Elements
ms.date: 03/30/2017
ms.assetid: 3234cd45-1478-468e-8b19-5c50815c4786
ms.openlocfilehash: 9c56cccd7a6f72a701e4b8652afecc2361e6218a
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/06/2019
ms.locfileid: "70400685"
---
# <a name="add-of-claimtyperequirements-element"></a><span data-ttu-id="74d8b-102">\<> von \<claimtyperequiation> Element hinzufügen</span><span class="sxs-lookup"><span data-stu-id="74d8b-102">\<add> of \<claimTypeRequirements> element</span></span>
<span data-ttu-id="74d8b-103">Gibt die Typen der erforderlichen und optionalen Ansprüche an, die in verbundenen Anmeldeinformationen vorhanden sein sollen.</span><span class="sxs-lookup"><span data-stu-id="74d8b-103">Specifies the types of required and optional claims expected to appear in the federated credential.</span></span> <span data-ttu-id="74d8b-104">Zum Beispiel geben die Dienste die Anforderungen für eingehende Anmeldeinformationen an, die einen bestimmten Satz von Anspruchstypen verarbeiten müssen.</span><span class="sxs-lookup"><span data-stu-id="74d8b-104">For example, services state the requirements on incoming credentials, which must possess a certain set of claim types.</span></span>  
  
<span data-ttu-id="74d8b-105">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="74d8b-105">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="74d8b-106">&nbsp;&nbsp;[ **\<System. Service Model->** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="74d8b-106">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="74d8b-107">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Bindungen >** ](bindings.md)</span><span class="sxs-lookup"><span data-stu-id="74d8b-107">&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)</span></span>\
<span data-ttu-id="74d8b-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<WSFederationHttpBinding->** ](wsfederationhttpbinding.md)</span><span class="sxs-lookup"><span data-stu-id="74d8b-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<wsFederationHttpBinding>**](wsfederationhttpbinding.md)</span></span>\
<span data-ttu-id="74d8b-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<Bindungs >** </span><span class="sxs-lookup"><span data-stu-id="74d8b-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**</span></span>\
<span data-ttu-id="74d8b-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Sicherheits >** ](security-of-custombinding.md)</span><span class="sxs-lookup"><span data-stu-id="74d8b-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<security>**](security-of-custombinding.md)</span></span>\
<span data-ttu-id="74d8b-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Message >** ](message-element-of-wsfederationhttpbinding.md)</span><span class="sxs-lookup"><span data-stu-id="74d8b-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<message>**](message-element-of-wsfederationhttpbinding.md)</span></span>\
<span data-ttu-id="74d8b-112">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<claimtyperequirequirements->** ](claimtyperequirements-for-message.md)</span><span class="sxs-lookup"><span data-stu-id="74d8b-112">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<claimTypeRequirements>**](claimtyperequirements-for-message.md)</span></span>\
<span data-ttu-id="74d8b-113">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<> Hinzufügen**</span><span class="sxs-lookup"><span data-stu-id="74d8b-113">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**</span></span>
  
## <a name="syntax"></a><span data-ttu-id="74d8b-114">Syntax</span><span class="sxs-lookup"><span data-stu-id="74d8b-114">Syntax</span></span>  
  
```xml  
<claimTypeRequirements>
  <add claimType="URI"
       isOptional="Boolean" />
</claimTypeRequirements>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="74d8b-115">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="74d8b-115">Attributes and Elements</span></span>  
 <span data-ttu-id="74d8b-116">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="74d8b-116">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="74d8b-117">Attribute</span><span class="sxs-lookup"><span data-stu-id="74d8b-117">Attributes</span></span>  
  
|<span data-ttu-id="74d8b-118">Attribut</span><span class="sxs-lookup"><span data-stu-id="74d8b-118">Attribute</span></span>|<span data-ttu-id="74d8b-119">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="74d8b-119">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="74d8b-120">claimType</span><span class="sxs-lookup"><span data-stu-id="74d8b-120">claimType</span></span>|<span data-ttu-id="74d8b-121">Ein URI, der den Typ eines Anspruchs definiert.</span><span class="sxs-lookup"><span data-stu-id="74d8b-121">A URI that defines the type of a claim.</span></span> <span data-ttu-id="74d8b-122">Wenn ein Benutzer zum Beispiel ein Produkt auf einer Website erwerben möchte, muss er eine gültige Kreditkarte mit einem ausreichend hohen Kreditrahmen vorlegen.</span><span class="sxs-lookup"><span data-stu-id="74d8b-122">For example, to purchase a product from a Web site, the user must present a valid credit card with sufficient credit limit.</span></span> <span data-ttu-id="74d8b-123">Der Anspruchstyp wäre der Kreditkarten-URI.</span><span class="sxs-lookup"><span data-stu-id="74d8b-123">The claim type would be the credit card URI.</span></span>|  
|<span data-ttu-id="74d8b-124">isOptional</span><span class="sxs-lookup"><span data-stu-id="74d8b-124">isOptional</span></span>|<span data-ttu-id="74d8b-125">Ein boolescher Wert, der angibt, ob der Anspruch optional ist.</span><span class="sxs-lookup"><span data-stu-id="74d8b-125">A Boolean value that specifies if this is for an optional claim.</span></span> <span data-ttu-id="74d8b-126">Legen Sie dieses Attribut auf `false` fest, wenn dies ein erforderlicher Anspruch ist.</span><span class="sxs-lookup"><span data-stu-id="74d8b-126">Set this attribute to `false` if this is a required claim.</span></span><br /><br /> <span data-ttu-id="74d8b-127">Sie können dieses Attribut verwenden, wenn der Dienst um Informationen bittet, aber es nicht erfordert.</span><span class="sxs-lookup"><span data-stu-id="74d8b-127">You can use this attribute when the service asks for some information but does not require it.</span></span> <span data-ttu-id="74d8b-128">Wenn der Benutzer z.&#160;B. seinen Vornamen, Nachnamen und seine Adresse eingeben muss, die Eingabe der Telefonnummer jedoch optional ist.</span><span class="sxs-lookup"><span data-stu-id="74d8b-128">For example, if you require the user to enter his/her first name, last name and address, but decide that phone number is optional.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="74d8b-129">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="74d8b-129">Child Elements</span></span>  
 <span data-ttu-id="74d8b-130">Keine</span><span class="sxs-lookup"><span data-stu-id="74d8b-130">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="74d8b-131">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="74d8b-131">Parent Elements</span></span>  
  
|<span data-ttu-id="74d8b-132">Element</span><span class="sxs-lookup"><span data-stu-id="74d8b-132">Element</span></span>|<span data-ttu-id="74d8b-133">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="74d8b-133">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="74d8b-134">\<claimTypeRequirements></span><span class="sxs-lookup"><span data-stu-id="74d8b-134">\<claimTypeRequirements></span></span>](claimtyperequirements-for-message.md)|<span data-ttu-id="74d8b-135">Gibt eine Auflistung von erforderlichen Anspruchstypen an.</span><span class="sxs-lookup"><span data-stu-id="74d8b-135">Specifies a collection of required claim types.</span></span> <span data-ttu-id="74d8b-136">Jedes Element ist vom Typ <xref:System.ServiceModel.Configuration.ClaimTypeElement>.</span><span class="sxs-lookup"><span data-stu-id="74d8b-136">Each element is of type <xref:System.ServiceModel.Configuration.ClaimTypeElement>.</span></span><br /><br /> <span data-ttu-id="74d8b-137">In einem verbundenen Szenario legen Dienste die Anforderungen für eingehende Anmeldeinformationen fest.</span><span class="sxs-lookup"><span data-stu-id="74d8b-137">In a federated scenario, services state the requirements on incoming credentials.</span></span> <span data-ttu-id="74d8b-138">Zum Beispiel müssen die eingehenden Anmeldeinformationen einen bestimmten Satz an Anspruchstypen aufweisen.</span><span class="sxs-lookup"><span data-stu-id="74d8b-138">For example, the incoming credentials must possess a certain set of claim types.</span></span> <span data-ttu-id="74d8b-139">Jedes Element in dieser Auflistung gibt die Typen der erforderlichen und optionalen Ansprüche an, die in verbundenen Anmeldeinformationen vorhanden sein sollen.</span><span class="sxs-lookup"><span data-stu-id="74d8b-139">Each element in this collection specifies the types of required and optional claims expected to appear in a federated credential.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="74d8b-140">Hinweise</span><span class="sxs-lookup"><span data-stu-id="74d8b-140">Remarks</span></span>  
 <span data-ttu-id="74d8b-141">In einem verbundenen Szenario legen Dienste die Anforderungen für eingehende Anmeldeinformationen fest.</span><span class="sxs-lookup"><span data-stu-id="74d8b-141">In a federated scenario, services state the requirements on incoming credentials.</span></span> <span data-ttu-id="74d8b-142">Zum Beispiel müssen die eingehenden Anmeldeinformationen einen bestimmten Satz an Anspruchstypen aufweisen.</span><span class="sxs-lookup"><span data-stu-id="74d8b-142">For example, the incoming credentials must possess a certain set of claim types.</span></span> <span data-ttu-id="74d8b-143">Diese Anforderung wird sich in einer Sicherheitsrichtlinie auswirken.</span><span class="sxs-lookup"><span data-stu-id="74d8b-143">This requirement is manifested in a security policy.</span></span> <span data-ttu-id="74d8b-144">Wenn ein Client Anmeldeinformationen von einem Verbunddienst anfordert (z.&#160;B. CardSpace), legt er die Anforderungen in einer Tokenanforderung (RequestSecurityToken) ab, sodass der Verbunddienst die Anmeldeinformationen ausgeben kann, die die Anforderungen entsprechend erfüllen.</span><span class="sxs-lookup"><span data-stu-id="74d8b-144">When a client requests credentials from a federated service (for example, CardSpace), it puts the requirements into a token request (RequestSecurityToken) so that the federated service can issue the credentials that satisfy the requirements accordingly.</span></span>  
  
## <a name="example"></a><span data-ttu-id="74d8b-145">Beispiel</span><span class="sxs-lookup"><span data-stu-id="74d8b-145">Example</span></span>  
 <span data-ttu-id="74d8b-146">Die folgende Konfiguration fügt einer Sicherheitsbindung zwei Anspruchstypanforderungen hinzu.</span><span class="sxs-lookup"><span data-stu-id="74d8b-146">The following configuration adds two claim type requirements to a security binding.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="74d8b-147">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="74d8b-147">See also</span></span>

- <xref:System.ServiceModel.FederatedMessageSecurityOverHttp.ClaimTypeRequirements%2A>
- <xref:System.ServiceModel.Security.Tokens.ClaimTypeRequirement>
- <xref:System.ServiceModel.Configuration.FederatedMessageSecurityOverHttpElement.ClaimTypeRequirements%2A>
- <xref:System.ServiceModel.Configuration.ClaimTypeElementCollection>
- <xref:System.ServiceModel.Configuration.ClaimTypeElement>
