---
title: <roleClaimType>
ms.date: 03/30/2017
ms.assetid: 69a49deb-6369-41ba-806b-ae8d21fac64b
author: BrucePerlerMS
ms.openlocfilehash: 812d44ef947d27b0f73d9dc2172494e89ee56d72
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/30/2019
ms.locfileid: "55270868"
---
# <a name="roleclaimtype"></a><span data-ttu-id="b5662-101">\<roleClaimType></span><span class="sxs-lookup"><span data-stu-id="b5662-101">\<roleClaimType></span></span>
<span data-ttu-id="b5662-102">Gibt an, den Anspruchstyp, der die Rollenansprüche für den Typ in der Auflistung definiert <xref:System.Security.Claims.ClaimsIdentity> zurückgegebenen Objekte die <xref:System.IdentityModel.Tokens.SecurityTokenHandler.ValidateToken%2A> Methode der Tokenhandler.</span><span class="sxs-lookup"><span data-stu-id="b5662-102">Specifies the claim type that defines the role type claims in the collection of <xref:System.Security.Claims.ClaimsIdentity> objects returned by the <xref:System.IdentityModel.Tokens.SecurityTokenHandler.ValidateToken%2A> method of the token handler.</span></span>  
  
 <span data-ttu-id="b5662-103">\<system.identityModel></span><span class="sxs-lookup"><span data-stu-id="b5662-103">\<system.identityModel></span></span>  
<span data-ttu-id="b5662-104">\<identityConfiguration></span><span class="sxs-lookup"><span data-stu-id="b5662-104">\<identityConfiguration></span></span>  
<span data-ttu-id="b5662-105">\<securityTokenHandlers></span><span class="sxs-lookup"><span data-stu-id="b5662-105">\<securityTokenHandlers></span></span>  
<span data-ttu-id="b5662-106">\<add></span><span class="sxs-lookup"><span data-stu-id="b5662-106">\<add></span></span>  
<span data-ttu-id="b5662-107">\<samlSecurityTokenRequirement></span><span class="sxs-lookup"><span data-stu-id="b5662-107">\<samlSecurityTokenRequirement></span></span>  
<span data-ttu-id="b5662-108">\<roleClaimType></span><span class="sxs-lookup"><span data-stu-id="b5662-108">\<roleClaimType></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b5662-109">Syntax</span><span class="sxs-lookup"><span data-stu-id="b5662-109">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="b5662-110">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="b5662-110">Attributes and Elements</span></span>  
 <span data-ttu-id="b5662-111">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="b5662-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="b5662-112">Attribute</span><span class="sxs-lookup"><span data-stu-id="b5662-112">Attributes</span></span>  
  
|<span data-ttu-id="b5662-113">Attribut</span><span class="sxs-lookup"><span data-stu-id="b5662-113">Attribute</span></span>|<span data-ttu-id="b5662-114">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="b5662-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="b5662-115">Wert</span><span class="sxs-lookup"><span data-stu-id="b5662-115">value</span></span>|<span data-ttu-id="b5662-116">Eine Zeichenfolge, die den URI an, der den Anspruchstyp des Anspruchs, verwenden Sie für den Anspruchstyp "Rolle" darstellt.</span><span class="sxs-lookup"><span data-stu-id="b5662-116">A string that specifies the URI that represents the claim type of the claim to use for the role claim type.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="b5662-117">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="b5662-117">Child Elements</span></span>  
 <span data-ttu-id="b5662-118">Keine</span><span class="sxs-lookup"><span data-stu-id="b5662-118">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="b5662-119">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="b5662-119">Parent Elements</span></span>  
  
|<span data-ttu-id="b5662-120">Element</span><span class="sxs-lookup"><span data-stu-id="b5662-120">Element</span></span>|<span data-ttu-id="b5662-121">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="b5662-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="b5662-122">\<samlSecurityTokenRequirement></span><span class="sxs-lookup"><span data-stu-id="b5662-122">\<samlSecurityTokenRequirement></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/samlsecuritytokenrequirement.md)|<span data-ttu-id="b5662-123">Ermöglicht die Konfiguration für die <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler> -Klasse, die <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> Klasse oder eine abgeleitete Klasse von einer dieser Klassen.</span><span class="sxs-lookup"><span data-stu-id="b5662-123">Provides configuration for the <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler> class, the <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> class, or a derived class of either of these classes.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b5662-124">Hinweise</span><span class="sxs-lookup"><span data-stu-id="b5662-124">Remarks</span></span>  
 <span data-ttu-id="b5662-125">Die `<roleClaimType>` Elementgruppen die <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement.RoleClaimType%2A> Eigenschaft bei einer <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement> -Objekt aus der Konfiguration initialisiert wird.</span><span class="sxs-lookup"><span data-stu-id="b5662-125">The `<roleClaimType>` element sets the <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement.RoleClaimType%2A> property when a <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement> object is initialized from configuration.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b5662-126">Beispiel</span><span class="sxs-lookup"><span data-stu-id="b5662-126">Example</span></span>  
  
```xml  
<add type="System.IdentityModel.Tokens.SamlSecurityTokenHandler, System.IdentityModel">  
    <samlSecurityTokenRequirement>  
        <roleClaimType value="schemas.microsoft.com/ws/2006/04/identity/claims/role" />  
    </samlSecurityTokenRequirement>  
</add>  
```  
  
## <a name="see-also"></a><span data-ttu-id="b5662-127">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b5662-127">See also</span></span>
- <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement.RoleClaimType%2A>
