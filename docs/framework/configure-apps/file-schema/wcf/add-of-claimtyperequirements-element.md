---
title: <add> des <claimTypeRequirements>-Elements
ms.date: 03/30/2017
ms.assetid: 3234cd45-1478-468e-8b19-5c50815c4786
ms.openlocfilehash: f6948052c62684faa734b592f5bdfc2e7827a07a
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/06/2020
ms.locfileid: "79153099"
---
# <a name="add-of-claimtyperequirements-element"></a><span data-ttu-id="1a73d-102">\<add> des \<claimTypeRequirements>-Elements</span><span class="sxs-lookup"><span data-stu-id="1a73d-102">\<add> of \<claimTypeRequirements> element</span></span>
<span data-ttu-id="1a73d-103">Gibt die Typen der erforderlichen und optionalen Ansprüche an, die in verbundenen Anmeldeinformationen vorhanden sein sollen.</span><span class="sxs-lookup"><span data-stu-id="1a73d-103">Specifies the types of required and optional claims expected to appear in the federated credential.</span></span> <span data-ttu-id="1a73d-104">Zum Beispiel geben die Dienste die Anforderungen für eingehende Anmeldeinformationen an, die einen bestimmten Satz von Anspruchstypen verarbeiten müssen.</span><span class="sxs-lookup"><span data-stu-id="1a73d-104">For example, services state the requirements on incoming credentials, which must possess a certain set of claim types.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<wsFederationHttpBinding>**](wsfederationhttpbinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<security>**](security-of-custombinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<message>**](message-element-of-wsfederationhttpbinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<claimTypeRequirements>**](claimtyperequirements-for-message.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**
  
## <a name="syntax"></a><span data-ttu-id="1a73d-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="1a73d-105">Syntax</span></span>  
  
```xml  
<claimTypeRequirements>
  <add claimType="URI"
       isOptional="Boolean" />
</claimTypeRequirements>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="1a73d-106">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="1a73d-106">Attributes and Elements</span></span>  
 <span data-ttu-id="1a73d-107">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="1a73d-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="1a73d-108">Attribute</span><span class="sxs-lookup"><span data-stu-id="1a73d-108">Attributes</span></span>  
  
|<span data-ttu-id="1a73d-109">attribute</span><span class="sxs-lookup"><span data-stu-id="1a73d-109">Attribute</span></span>|<span data-ttu-id="1a73d-110">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="1a73d-110">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="1a73d-111">claimType</span><span class="sxs-lookup"><span data-stu-id="1a73d-111">claimType</span></span>|<span data-ttu-id="1a73d-112">Ein URI, der den Typ eines Anspruchs definiert.</span><span class="sxs-lookup"><span data-stu-id="1a73d-112">A URI that defines the type of a claim.</span></span> <span data-ttu-id="1a73d-113">Wenn ein Benutzer zum Beispiel ein Produkt auf einer Website erwerben möchte, muss er eine gültige Kreditkarte mit einem ausreichend hohen Kreditrahmen vorlegen.</span><span class="sxs-lookup"><span data-stu-id="1a73d-113">For example, to purchase a product from a Web site, the user must present a valid credit card with sufficient credit limit.</span></span> <span data-ttu-id="1a73d-114">Der Anspruchstyp wäre der Kreditkarten-URI.</span><span class="sxs-lookup"><span data-stu-id="1a73d-114">The claim type would be the credit card URI.</span></span>|  
|<span data-ttu-id="1a73d-115">isOptional</span><span class="sxs-lookup"><span data-stu-id="1a73d-115">isOptional</span></span>|<span data-ttu-id="1a73d-116">Ein boolescher Wert, der angibt, ob der Anspruch optional ist.</span><span class="sxs-lookup"><span data-stu-id="1a73d-116">A Boolean value that specifies if this is for an optional claim.</span></span> <span data-ttu-id="1a73d-117">Legen Sie dieses Attribut auf `false` fest, wenn dies ein erforderlicher Anspruch ist.</span><span class="sxs-lookup"><span data-stu-id="1a73d-117">Set this attribute to `false` if this is a required claim.</span></span><br /><br /> <span data-ttu-id="1a73d-118">Sie können dieses Attribut verwenden, wenn der Dienst um Informationen bittet, aber es nicht erfordert.</span><span class="sxs-lookup"><span data-stu-id="1a73d-118">You can use this attribute when the service asks for some information but does not require it.</span></span> <span data-ttu-id="1a73d-119">Wenn Sie z. b. den Vornamen, den Nachnamen und die Adresse des Benutzers eingeben müssen, aber entscheiden, dass die Telefonnummer optional ist.</span><span class="sxs-lookup"><span data-stu-id="1a73d-119">For example, if you require the user to enter their first name, last name, and address, but decide that phone number is optional.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="1a73d-120">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="1a73d-120">Child Elements</span></span>  
 <span data-ttu-id="1a73d-121">Keine</span><span class="sxs-lookup"><span data-stu-id="1a73d-121">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="1a73d-122">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="1a73d-122">Parent Elements</span></span>  
  
|<span data-ttu-id="1a73d-123">Element</span><span class="sxs-lookup"><span data-stu-id="1a73d-123">Element</span></span>|<span data-ttu-id="1a73d-124">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="1a73d-124">Description</span></span>|  
|-------------|-----------------|  
|[\<claimTypeRequirements>](claimtyperequirements-for-message.md)|<span data-ttu-id="1a73d-125">Gibt eine Auflistung von erforderlichen Anspruchstypen an.</span><span class="sxs-lookup"><span data-stu-id="1a73d-125">Specifies a collection of required claim types.</span></span> <span data-ttu-id="1a73d-126">Jedes Element ist vom Typ <xref:System.ServiceModel.Configuration.ClaimTypeElement>.</span><span class="sxs-lookup"><span data-stu-id="1a73d-126">Each element is of type <xref:System.ServiceModel.Configuration.ClaimTypeElement>.</span></span><br /><br /> <span data-ttu-id="1a73d-127">In einem verbundenen Szenario legen Dienste die Anforderungen für eingehende Anmeldeinformationen fest.</span><span class="sxs-lookup"><span data-stu-id="1a73d-127">In a federated scenario, services state the requirements on incoming credentials.</span></span> <span data-ttu-id="1a73d-128">Zum Beispiel müssen die eingehenden Anmeldeinformationen einen bestimmten Satz an Anspruchstypen aufweisen.</span><span class="sxs-lookup"><span data-stu-id="1a73d-128">For example, the incoming credentials must possess a certain set of claim types.</span></span> <span data-ttu-id="1a73d-129">Jedes Element in dieser Auflistung gibt die Typen der erforderlichen und optionalen Ansprüche an, die in verbundenen Anmeldeinformationen vorhanden sein sollen.</span><span class="sxs-lookup"><span data-stu-id="1a73d-129">Each element in this collection specifies the types of required and optional claims expected to appear in a federated credential.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="1a73d-130">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="1a73d-130">Remarks</span></span>  
 <span data-ttu-id="1a73d-131">In einem verbundenen Szenario legen Dienste die Anforderungen für eingehende Anmeldeinformationen fest.</span><span class="sxs-lookup"><span data-stu-id="1a73d-131">In a federated scenario, services state the requirements on incoming credentials.</span></span> <span data-ttu-id="1a73d-132">Zum Beispiel müssen die eingehenden Anmeldeinformationen einen bestimmten Satz an Anspruchstypen aufweisen.</span><span class="sxs-lookup"><span data-stu-id="1a73d-132">For example, the incoming credentials must possess a certain set of claim types.</span></span> <span data-ttu-id="1a73d-133">Diese Anforderung wird sich in einer Sicherheitsrichtlinie auswirken.</span><span class="sxs-lookup"><span data-stu-id="1a73d-133">This requirement is manifested in a security policy.</span></span> <span data-ttu-id="1a73d-134">Wenn ein Client Anmeldeinformationen von einem Verbunddienst anfordert (z.&#160;B. CardSpace), legt er die Anforderungen in einer Tokenanforderung (RequestSecurityToken) ab, sodass der Verbunddienst die Anmeldeinformationen ausgeben kann, die die Anforderungen entsprechend erfüllen.</span><span class="sxs-lookup"><span data-stu-id="1a73d-134">When a client requests credentials from a federated service (for example, CardSpace), it puts the requirements into a token request (RequestSecurityToken) so that the federated service can issue the credentials that satisfy the requirements accordingly.</span></span>  
  
## <a name="example"></a><span data-ttu-id="1a73d-135">Beispiel</span><span class="sxs-lookup"><span data-stu-id="1a73d-135">Example</span></span>  
 <span data-ttu-id="1a73d-136">Die folgende Konfiguration fügt einer Sicherheitsbindung zwei Anspruchstypanforderungen hinzu.</span><span class="sxs-lookup"><span data-stu-id="1a73d-136">The following configuration adds two claim type requirements to a security binding.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="1a73d-137">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="1a73d-137">See also</span></span>

- <xref:System.ServiceModel.FederatedMessageSecurityOverHttp.ClaimTypeRequirements%2A>
- <xref:System.ServiceModel.Security.Tokens.ClaimTypeRequirement>
- <xref:System.ServiceModel.Configuration.FederatedMessageSecurityOverHttpElement.ClaimTypeRequirements%2A>
- <xref:System.ServiceModel.Configuration.ClaimTypeElementCollection>
- <xref:System.ServiceModel.Configuration.ClaimTypeElement>
