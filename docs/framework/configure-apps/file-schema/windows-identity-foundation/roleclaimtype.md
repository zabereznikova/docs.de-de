---
title: '&lt;RoleClaimType&gt;'
ms.date: 03/30/2017
ms.assetid: 69a49deb-6369-41ba-806b-ae8d21fac64b
author: BrucePerlerMS
ms.openlocfilehash: 565bf30d334c62c8132c60f411e89f7b260c54f1
ms.sourcegitcommit: 213292dfbb0c37d83f62709959ff55c50af5560d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/25/2018
ms.locfileid: "47084344"
---
# <a name="ltroleclaimtypegt"></a><span data-ttu-id="9c4c3-102">&lt;RoleClaimType&gt;</span><span class="sxs-lookup"><span data-stu-id="9c4c3-102">&lt;roleClaimType&gt;</span></span>
<span data-ttu-id="9c4c3-103">Gibt an, den Anspruchstyp, der die Rollenansprüche für den Typ in der Auflistung definiert <xref:System.Security.Claims.ClaimsIdentity> zurückgegebenen Objekte die <xref:System.IdentityModel.Tokens.SecurityTokenHandler.ValidateToken%2A> Methode der Tokenhandler.</span><span class="sxs-lookup"><span data-stu-id="9c4c3-103">Specifies the claim type that defines the role type claims in the collection of <xref:System.Security.Claims.ClaimsIdentity> objects returned by the <xref:System.IdentityModel.Tokens.SecurityTokenHandler.ValidateToken%2A> method of the token handler.</span></span>  
  
 <span data-ttu-id="9c4c3-104">\<system.identityModel></span><span class="sxs-lookup"><span data-stu-id="9c4c3-104">\<system.identityModel></span></span>  
<span data-ttu-id="9c4c3-105">\<identityConfiguration></span><span class="sxs-lookup"><span data-stu-id="9c4c3-105">\<identityConfiguration></span></span>  
<span data-ttu-id="9c4c3-106">\<SecurityTokenHandlers ></span><span class="sxs-lookup"><span data-stu-id="9c4c3-106">\<securityTokenHandlers></span></span>  
<span data-ttu-id="9c4c3-107">\<add></span><span class="sxs-lookup"><span data-stu-id="9c4c3-107">\<add></span></span>  
<span data-ttu-id="9c4c3-108">\<SamlSecurityTokenRequirement ></span><span class="sxs-lookup"><span data-stu-id="9c4c3-108">\<samlSecurityTokenRequirement></span></span>  
<span data-ttu-id="9c4c3-109">\<RoleClaimType ></span><span class="sxs-lookup"><span data-stu-id="9c4c3-109">\<roleClaimType></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9c4c3-110">Syntax</span><span class="sxs-lookup"><span data-stu-id="9c4c3-110">Syntax</span></span>  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <securityTokenHandlers>  
      <add>  
        <samlSecurityTokenRequirement>  
          <roleClaimType value=xs:string>  
          </roleClaimType>  
        </samlSecurityTokenRequirement>  
      </add>  
    </securityTokenHandlers>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="9c4c3-111">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="9c4c3-111">Attributes and Elements</span></span>  
 <span data-ttu-id="9c4c3-112">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="9c4c3-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="9c4c3-113">Attribute</span><span class="sxs-lookup"><span data-stu-id="9c4c3-113">Attributes</span></span>  
  
|<span data-ttu-id="9c4c3-114">Attribut</span><span class="sxs-lookup"><span data-stu-id="9c4c3-114">Attribute</span></span>|<span data-ttu-id="9c4c3-115">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="9c4c3-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="9c4c3-116">Wert</span><span class="sxs-lookup"><span data-stu-id="9c4c3-116">value</span></span>|<span data-ttu-id="9c4c3-117">Eine Zeichenfolge, die den URI an, der den Anspruchstyp des Anspruchs, verwenden Sie für den Anspruchstyp "Rolle" darstellt.</span><span class="sxs-lookup"><span data-stu-id="9c4c3-117">A string that specifies the URI that represents the claim type of the claim to use for the role claim type.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="9c4c3-118">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="9c4c3-118">Child Elements</span></span>  
 <span data-ttu-id="9c4c3-119">Keiner</span><span class="sxs-lookup"><span data-stu-id="9c4c3-119">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="9c4c3-120">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="9c4c3-120">Parent Elements</span></span>  
  
|<span data-ttu-id="9c4c3-121">Element</span><span class="sxs-lookup"><span data-stu-id="9c4c3-121">Element</span></span>|<span data-ttu-id="9c4c3-122">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="9c4c3-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="9c4c3-123">\<samlSecurityTokenRequirement></span><span class="sxs-lookup"><span data-stu-id="9c4c3-123">\<samlSecurityTokenRequirement></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/samlsecuritytokenrequirement.md)|<span data-ttu-id="9c4c3-124">Ermöglicht die Konfiguration für die <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler> -Klasse, die <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> Klasse oder eine abgeleitete Klasse von einer dieser Klassen.</span><span class="sxs-lookup"><span data-stu-id="9c4c3-124">Provides configuration for the <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler> class, the <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> class, or a derived class of either of these classes.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="9c4c3-125">Hinweise</span><span class="sxs-lookup"><span data-stu-id="9c4c3-125">Remarks</span></span>  
 <span data-ttu-id="9c4c3-126">Die `<roleClaimType>` Elementgruppen die <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement.RoleClaimType%2A> Eigenschaft bei einer <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement> -Objekt aus der Konfiguration initialisiert wird.</span><span class="sxs-lookup"><span data-stu-id="9c4c3-126">The `<roleClaimType>` element sets the <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement.RoleClaimType%2A> property when a <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement> object is initialized from configuration.</span></span>  
  
## <a name="example"></a><span data-ttu-id="9c4c3-127">Beispiel</span><span class="sxs-lookup"><span data-stu-id="9c4c3-127">Example</span></span>  
  
```xml  
<add type="System.IdentityModel.Tokens.SamlSecurityTokenHandler, System.IdentityModel">  
    <samlSecurityTokenRequirement>  
        <roleClaimType value="schemas.microsoft.com/ws/2006/04/identity/claims/role" />  
    </samlSecurityTokenRequirement>  
</add>  
```  
  
## <a name="see-also"></a><span data-ttu-id="9c4c3-128">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="9c4c3-128">See Also</span></span>  
 <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement.RoleClaimType%2A>
