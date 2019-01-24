---
title: '&lt;nameClaimType&gt;'
ms.date: 03/30/2017
ms.assetid: 17514d95-f0f5-4789-8e28-346640dc227c
author: BrucePerlerMS
ms.openlocfilehash: 502fc5dd14d7bc3d979153607e1eeeb9354031bb
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54737428"
---
# <a name="ltnameclaimtypegt"></a><span data-ttu-id="e1625-102">&lt;nameClaimType&gt;</span><span class="sxs-lookup"><span data-stu-id="e1625-102">&lt;nameClaimType&gt;</span></span>
<span data-ttu-id="e1625-103">Legt den Typ des Anspruchs, der angibt, die <xref:System.Security.Principal.IIdentity.Name%2A> Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="e1625-103">Sets the claim type that specifies the <xref:System.Security.Principal.IIdentity.Name%2A> property.</span></span> <span data-ttu-id="e1625-104">Der Anspruchstyp wird verwendet, um für die Suche eine <xref:System.Security.Claims.Claim> in der Auflistung der <xref:System.Security.Claims.ClaimsIdentity> zurückgegebenen Objekte die <xref:System.IdentityModel.Tokens.SecurityTokenHandler.ValidateToken%2A> -Methode der diesem Tokenhandler.</span><span class="sxs-lookup"><span data-stu-id="e1625-104">The claim type is used to search for a <xref:System.Security.Claims.Claim> in the collection of <xref:System.Security.Claims.ClaimsIdentity> objects returned by the <xref:System.IdentityModel.Tokens.SecurityTokenHandler.ValidateToken%2A> method of this token handler.</span></span> <span data-ttu-id="e1625-105">Der Wert, der den übereinstimmenden Anspruch wird als Name des festgelegt die <xref:System.Security.Principal.IIdentity> aus dieser Handler token generiert.</span><span class="sxs-lookup"><span data-stu-id="e1625-105">The value of the matching claim is then set as the name of the <xref:System.Security.Principal.IIdentity> generated from this token handler.</span></span>  
  
 <span data-ttu-id="e1625-106">\<system.identityModel></span><span class="sxs-lookup"><span data-stu-id="e1625-106">\<system.identityModel></span></span>  
<span data-ttu-id="e1625-107">\<identityConfiguration></span><span class="sxs-lookup"><span data-stu-id="e1625-107">\<identityConfiguration></span></span>  
<span data-ttu-id="e1625-108">\<securityTokenHandlers></span><span class="sxs-lookup"><span data-stu-id="e1625-108">\<securityTokenHandlers></span></span>  
<span data-ttu-id="e1625-109">\<add></span><span class="sxs-lookup"><span data-stu-id="e1625-109">\<add></span></span>  
<span data-ttu-id="e1625-110">\<samlSecurityTokenRequirement></span><span class="sxs-lookup"><span data-stu-id="e1625-110">\<samlSecurityTokenRequirement></span></span>  
<span data-ttu-id="e1625-111">\<nameClaimType></span><span class="sxs-lookup"><span data-stu-id="e1625-111">\<nameClaimType></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e1625-112">Syntax</span><span class="sxs-lookup"><span data-stu-id="e1625-112">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="e1625-113">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="e1625-113">Attributes and Elements</span></span>  
 <span data-ttu-id="e1625-114">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="e1625-114">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="e1625-115">Attribute</span><span class="sxs-lookup"><span data-stu-id="e1625-115">Attributes</span></span>  
  
|<span data-ttu-id="e1625-116">Attribut</span><span class="sxs-lookup"><span data-stu-id="e1625-116">Attribute</span></span>|<span data-ttu-id="e1625-117">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="e1625-117">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="e1625-118">Wert</span><span class="sxs-lookup"><span data-stu-id="e1625-118">value</span></span>|<span data-ttu-id="e1625-119">Eine Zeichenfolge, die den URI an, der den Anspruchstyp des Anspruchs für die Verwendung der <xref:System.Security.Principal.IIdentity.Name%2A> Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="e1625-119">A string that specifies the URI that represents the claim type of the claim to use for the <xref:System.Security.Principal.IIdentity.Name%2A> property.</span></span> <span data-ttu-id="e1625-120">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="e1625-120">Required.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="e1625-121">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="e1625-121">Child Elements</span></span>  
 <span data-ttu-id="e1625-122">Keine</span><span class="sxs-lookup"><span data-stu-id="e1625-122">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="e1625-123">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="e1625-123">Parent Elements</span></span>  
  
|<span data-ttu-id="e1625-124">Element</span><span class="sxs-lookup"><span data-stu-id="e1625-124">Element</span></span>|<span data-ttu-id="e1625-125">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="e1625-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="e1625-126">\<samlSecurityTokenRequirement></span><span class="sxs-lookup"><span data-stu-id="e1625-126">\<samlSecurityTokenRequirement></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/samlsecuritytokenrequirement.md)|<span data-ttu-id="e1625-127">Ermöglicht die Konfiguration für die <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler> -Klasse, die <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> Klasse oder eine abgeleitete Klasse von einer dieser Klassen.</span><span class="sxs-lookup"><span data-stu-id="e1625-127">Provides configuration for the <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler> class, the <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> class, or a derived class of either of these classes.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e1625-128">Hinweise</span><span class="sxs-lookup"><span data-stu-id="e1625-128">Remarks</span></span>  
 <span data-ttu-id="e1625-129">Die `<nameClaimType>` Elementgruppen die <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement.NameClaimType%2A> Eigenschaft bei einer <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement> -Objekt aus der Konfiguration initialisiert wird.</span><span class="sxs-lookup"><span data-stu-id="e1625-129">The `<nameClaimType>` element sets the <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement.NameClaimType%2A> property when a <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement> object is initialized from configuration.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e1625-130">Beispiel</span><span class="sxs-lookup"><span data-stu-id="e1625-130">Example</span></span>  
  
```xml  
<add type="System.IdentityModel.Tokens.SamlSecurityTokenHandler, System.IdentityModel">  
    <samlSecurityTokenRequirement>  
        <nameClaimType value="http://schemas.xmlsoap.org/ws/2005/05/identity/claims/name" />  
    </samlSecurityTokenRequirement>  
</add>  
```  
  
## <a name="see-also"></a><span data-ttu-id="e1625-131">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e1625-131">See also</span></span>
- <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement.NameClaimType%2A>
