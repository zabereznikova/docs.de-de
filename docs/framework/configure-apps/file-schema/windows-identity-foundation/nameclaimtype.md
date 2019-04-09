---
title: <nameClaimType>
ms.date: 03/30/2017
ms.assetid: 17514d95-f0f5-4789-8e28-346640dc227c
author: BrucePerlerMS
ms.openlocfilehash: 5202e162a7eb5fc4e36d6a6c0a2c18af48872a69
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59130324"
---
# <a name="nameclaimtype"></a><span data-ttu-id="e4ddd-101">\<nameClaimType></span><span class="sxs-lookup"><span data-stu-id="e4ddd-101">\<nameClaimType></span></span>
<span data-ttu-id="e4ddd-102">Legt den Typ des Anspruchs, der angibt, die <xref:System.Security.Principal.IIdentity.Name%2A> Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="e4ddd-102">Sets the claim type that specifies the <xref:System.Security.Principal.IIdentity.Name%2A> property.</span></span> <span data-ttu-id="e4ddd-103">Der Anspruchstyp wird verwendet, um für die Suche eine <xref:System.Security.Claims.Claim> in der Auflistung der <xref:System.Security.Claims.ClaimsIdentity> zurückgegebenen Objekte die <xref:System.IdentityModel.Tokens.SecurityTokenHandler.ValidateToken%2A> -Methode der diesem Tokenhandler.</span><span class="sxs-lookup"><span data-stu-id="e4ddd-103">The claim type is used to search for a <xref:System.Security.Claims.Claim> in the collection of <xref:System.Security.Claims.ClaimsIdentity> objects returned by the <xref:System.IdentityModel.Tokens.SecurityTokenHandler.ValidateToken%2A> method of this token handler.</span></span> <span data-ttu-id="e4ddd-104">Der Wert, der den übereinstimmenden Anspruch wird als Name des festgelegt die <xref:System.Security.Principal.IIdentity> aus dieser Handler token generiert.</span><span class="sxs-lookup"><span data-stu-id="e4ddd-104">The value of the matching claim is then set as the name of the <xref:System.Security.Principal.IIdentity> generated from this token handler.</span></span>  
  
 <span data-ttu-id="e4ddd-105">\<system.identityModel></span><span class="sxs-lookup"><span data-stu-id="e4ddd-105">\<system.identityModel></span></span>  
<span data-ttu-id="e4ddd-106">\<identityConfiguration></span><span class="sxs-lookup"><span data-stu-id="e4ddd-106">\<identityConfiguration></span></span>  
<span data-ttu-id="e4ddd-107">\<securityTokenHandlers></span><span class="sxs-lookup"><span data-stu-id="e4ddd-107">\<securityTokenHandlers></span></span>  
<span data-ttu-id="e4ddd-108">\<add></span><span class="sxs-lookup"><span data-stu-id="e4ddd-108">\<add></span></span>  
<span data-ttu-id="e4ddd-109">\<samlSecurityTokenRequirement></span><span class="sxs-lookup"><span data-stu-id="e4ddd-109">\<samlSecurityTokenRequirement></span></span>  
<span data-ttu-id="e4ddd-110">\<nameClaimType></span><span class="sxs-lookup"><span data-stu-id="e4ddd-110">\<nameClaimType></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e4ddd-111">Syntax</span><span class="sxs-lookup"><span data-stu-id="e4ddd-111">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="e4ddd-112">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="e4ddd-112">Attributes and Elements</span></span>  
 <span data-ttu-id="e4ddd-113">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="e4ddd-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="e4ddd-114">Attribute</span><span class="sxs-lookup"><span data-stu-id="e4ddd-114">Attributes</span></span>  
  
|<span data-ttu-id="e4ddd-115">Attribut</span><span class="sxs-lookup"><span data-stu-id="e4ddd-115">Attribute</span></span>|<span data-ttu-id="e4ddd-116">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="e4ddd-116">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="e4ddd-117">Wert</span><span class="sxs-lookup"><span data-stu-id="e4ddd-117">value</span></span>|<span data-ttu-id="e4ddd-118">Eine Zeichenfolge, die den URI an, der den Anspruchstyp des Anspruchs für die Verwendung der <xref:System.Security.Principal.IIdentity.Name%2A> Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="e4ddd-118">A string that specifies the URI that represents the claim type of the claim to use for the <xref:System.Security.Principal.IIdentity.Name%2A> property.</span></span> <span data-ttu-id="e4ddd-119">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="e4ddd-119">Required.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="e4ddd-120">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="e4ddd-120">Child Elements</span></span>  
 <span data-ttu-id="e4ddd-121">Keiner</span><span class="sxs-lookup"><span data-stu-id="e4ddd-121">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="e4ddd-122">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="e4ddd-122">Parent Elements</span></span>  
  
|<span data-ttu-id="e4ddd-123">Element</span><span class="sxs-lookup"><span data-stu-id="e4ddd-123">Element</span></span>|<span data-ttu-id="e4ddd-124">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="e4ddd-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="e4ddd-125">\<samlSecurityTokenRequirement></span><span class="sxs-lookup"><span data-stu-id="e4ddd-125">\<samlSecurityTokenRequirement></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/samlsecuritytokenrequirement.md)|<span data-ttu-id="e4ddd-126">Ermöglicht die Konfiguration für die <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler> -Klasse, die <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> Klasse oder eine abgeleitete Klasse von einer dieser Klassen.</span><span class="sxs-lookup"><span data-stu-id="e4ddd-126">Provides configuration for the <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler> class, the <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> class, or a derived class of either of these classes.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e4ddd-127">Hinweise</span><span class="sxs-lookup"><span data-stu-id="e4ddd-127">Remarks</span></span>  
 <span data-ttu-id="e4ddd-128">Die `<nameClaimType>` Elementgruppen die <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement.NameClaimType%2A> Eigenschaft bei einer <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement> -Objekt aus der Konfiguration initialisiert wird.</span><span class="sxs-lookup"><span data-stu-id="e4ddd-128">The `<nameClaimType>` element sets the <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement.NameClaimType%2A> property when a <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement> object is initialized from configuration.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e4ddd-129">Beispiel</span><span class="sxs-lookup"><span data-stu-id="e4ddd-129">Example</span></span>  
  
```xml  
<add type="System.IdentityModel.Tokens.SamlSecurityTokenHandler, System.IdentityModel">  
    <samlSecurityTokenRequirement>  
        <nameClaimType value="http://schemas.xmlsoap.org/ws/2005/05/identity/claims/name" />  
    </samlSecurityTokenRequirement>  
</add>  
```  
  
## <a name="see-also"></a><span data-ttu-id="e4ddd-130">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e4ddd-130">See also</span></span>

- <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement.NameClaimType%2A>
