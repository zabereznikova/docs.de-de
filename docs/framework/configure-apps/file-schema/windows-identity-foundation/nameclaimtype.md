---
title: '&lt;nameClaimType&gt;'
ms.date: 03/30/2017
ms.assetid: 17514d95-f0f5-4789-8e28-346640dc227c
author: BrucePerlerMS
ms.openlocfilehash: bd4033b2edea7450b66c25f446669b3ded65e9af
ms.sourcegitcommit: 213292dfbb0c37d83f62709959ff55c50af5560d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/25/2018
ms.locfileid: "47112217"
---
# <a name="ltnameclaimtypegt"></a><span data-ttu-id="73647-102">&lt;nameClaimType&gt;</span><span class="sxs-lookup"><span data-stu-id="73647-102">&lt;nameClaimType&gt;</span></span>
<span data-ttu-id="73647-103">Legt den Typ des Anspruchs, der angibt, die <xref:System.Security.Principal.IIdentity.Name%2A> Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="73647-103">Sets the claim type that specifies the <xref:System.Security.Principal.IIdentity.Name%2A> property.</span></span> <span data-ttu-id="73647-104">Der Anspruchstyp wird verwendet, um für die Suche eine <xref:System.Security.Claims.Claim> in der Auflistung der <xref:System.Security.Claims.ClaimsIdentity> zurückgegebenen Objekte die <xref:System.IdentityModel.Tokens.SecurityTokenHandler.ValidateToken%2A> -Methode der diesem Tokenhandler.</span><span class="sxs-lookup"><span data-stu-id="73647-104">The claim type is used to search for a <xref:System.Security.Claims.Claim> in the collection of <xref:System.Security.Claims.ClaimsIdentity> objects returned by the <xref:System.IdentityModel.Tokens.SecurityTokenHandler.ValidateToken%2A> method of this token handler.</span></span> <span data-ttu-id="73647-105">Der Wert, der den übereinstimmenden Anspruch wird als Name des festgelegt die <xref:System.Security.Principal.IIdentity> aus dieser Handler token generiert.</span><span class="sxs-lookup"><span data-stu-id="73647-105">The value of the matching claim is then set as the name of the <xref:System.Security.Principal.IIdentity> generated from this token handler.</span></span>  
  
 <span data-ttu-id="73647-106">\<system.identityModel></span><span class="sxs-lookup"><span data-stu-id="73647-106">\<system.identityModel></span></span>  
<span data-ttu-id="73647-107">\<identityConfiguration></span><span class="sxs-lookup"><span data-stu-id="73647-107">\<identityConfiguration></span></span>  
<span data-ttu-id="73647-108">\<SecurityTokenHandlers ></span><span class="sxs-lookup"><span data-stu-id="73647-108">\<securityTokenHandlers></span></span>  
<span data-ttu-id="73647-109">\<add></span><span class="sxs-lookup"><span data-stu-id="73647-109">\<add></span></span>  
<span data-ttu-id="73647-110">\<SamlSecurityTokenRequirement ></span><span class="sxs-lookup"><span data-stu-id="73647-110">\<samlSecurityTokenRequirement></span></span>  
<span data-ttu-id="73647-111">\<NameClaimType ></span><span class="sxs-lookup"><span data-stu-id="73647-111">\<nameClaimType></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="73647-112">Syntax</span><span class="sxs-lookup"><span data-stu-id="73647-112">Syntax</span></span>  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <securityTokenHandlers>  
      <add>  
        <samlSecurityTokenRequirement>  
          <nameClaimType value=xs:string>  
          </nameClaimType>  
        </samlSecurityTokenRequirement>  
      </add>  
    </securityTokenHandlers>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="73647-113">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="73647-113">Attributes and Elements</span></span>  
 <span data-ttu-id="73647-114">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="73647-114">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="73647-115">Attribute</span><span class="sxs-lookup"><span data-stu-id="73647-115">Attributes</span></span>  
  
|<span data-ttu-id="73647-116">Attribut</span><span class="sxs-lookup"><span data-stu-id="73647-116">Attribute</span></span>|<span data-ttu-id="73647-117">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="73647-117">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="73647-118">Wert</span><span class="sxs-lookup"><span data-stu-id="73647-118">value</span></span>|<span data-ttu-id="73647-119">Eine Zeichenfolge, die den URI an, der den Anspruchstyp des Anspruchs für die Verwendung der <xref:System.Security.Principal.IIdentity.Name%2A> Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="73647-119">A string that specifies the URI that represents the claim type of the claim to use for the <xref:System.Security.Principal.IIdentity.Name%2A> property.</span></span> <span data-ttu-id="73647-120">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="73647-120">Required.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="73647-121">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="73647-121">Child Elements</span></span>  
 <span data-ttu-id="73647-122">Keiner</span><span class="sxs-lookup"><span data-stu-id="73647-122">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="73647-123">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="73647-123">Parent Elements</span></span>  
  
|<span data-ttu-id="73647-124">Element</span><span class="sxs-lookup"><span data-stu-id="73647-124">Element</span></span>|<span data-ttu-id="73647-125">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="73647-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="73647-126">\<samlSecurityTokenRequirement></span><span class="sxs-lookup"><span data-stu-id="73647-126">\<samlSecurityTokenRequirement></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/samlsecuritytokenrequirement.md)|<span data-ttu-id="73647-127">Ermöglicht die Konfiguration für die <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler> -Klasse, die <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> Klasse oder eine abgeleitete Klasse von einer dieser Klassen.</span><span class="sxs-lookup"><span data-stu-id="73647-127">Provides configuration for the <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler> class, the <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> class, or a derived class of either of these classes.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="73647-128">Hinweise</span><span class="sxs-lookup"><span data-stu-id="73647-128">Remarks</span></span>  
 <span data-ttu-id="73647-129">Die `<nameClaimType>` Elementgruppen die <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement.NameClaimType%2A> Eigenschaft bei einer <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement> -Objekt aus der Konfiguration initialisiert wird.</span><span class="sxs-lookup"><span data-stu-id="73647-129">The `<nameClaimType>` element sets the <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement.NameClaimType%2A> property when a <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement> object is initialized from configuration.</span></span>  
  
## <a name="example"></a><span data-ttu-id="73647-130">Beispiel</span><span class="sxs-lookup"><span data-stu-id="73647-130">Example</span></span>  
  
```xml  
<add type="System.IdentityModel.Tokens.SamlSecurityTokenHandler, System.IdentityModel">  
    <samlSecurityTokenRequirement>  
        <nameClaimType value="http://schemas.xmlsoap.org/ws/2005/05/identity/claims/name" />  
    </samlSecurityTokenRequirement>  
</add>  
```  
  
## <a name="see-also"></a><span data-ttu-id="73647-131">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="73647-131">See Also</span></span>  
 <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement.NameClaimType%2A>
