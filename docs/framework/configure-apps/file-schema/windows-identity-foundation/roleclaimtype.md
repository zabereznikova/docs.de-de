---
title: '&lt;roleClaimType&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 69a49deb-6369-41ba-806b-ae8d21fac64b
caps.latest.revision: "4"
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.openlocfilehash: 8a5de30d60478b6601781ac34fd481a6167462e0
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="ltroleclaimtypegt"></a><span data-ttu-id="2cdea-102">&lt;roleClaimType&gt;</span><span class="sxs-lookup"><span data-stu-id="2cdea-102">&lt;roleClaimType&gt;</span></span>
<span data-ttu-id="2cdea-103">Gibt an, der Typ des Anspruchs, der den Typ Rollenansprüche in der Auflistung von definiert <xref:System.Security.Claims.ClaimsIdentity> zurückgegebenen Objekte die <xref:System.IdentityModel.Tokens.SecurityTokenHandler.ValidateToken%2A> Methode von der Tokenhandler.</span><span class="sxs-lookup"><span data-stu-id="2cdea-103">Specifies the claim type that defines the role type claims in the collection of <xref:System.Security.Claims.ClaimsIdentity> objects returned by the <xref:System.IdentityModel.Tokens.SecurityTokenHandler.ValidateToken%2A> method of the token handler.</span></span>  
  
 <span data-ttu-id="2cdea-104">\<system.identityModel ></span><span class="sxs-lookup"><span data-stu-id="2cdea-104">\<system.identityModel></span></span>  
<span data-ttu-id="2cdea-105">\<IdentityConfiguration ></span><span class="sxs-lookup"><span data-stu-id="2cdea-105">\<identityConfiguration></span></span>  
<span data-ttu-id="2cdea-106">\<SecurityTokenHandlers ></span><span class="sxs-lookup"><span data-stu-id="2cdea-106">\<securityTokenHandlers></span></span>  
<span data-ttu-id="2cdea-107">\<add></span><span class="sxs-lookup"><span data-stu-id="2cdea-107">\<add></span></span>  
<span data-ttu-id="2cdea-108">\<SamlSecurityTokenRequirement ></span><span class="sxs-lookup"><span data-stu-id="2cdea-108">\<samlSecurityTokenRequirement></span></span>  
<span data-ttu-id="2cdea-109">\<RoleClaimType ></span><span class="sxs-lookup"><span data-stu-id="2cdea-109">\<roleClaimType></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2cdea-110">Syntax</span><span class="sxs-lookup"><span data-stu-id="2cdea-110">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="2cdea-111">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="2cdea-111">Attributes and Elements</span></span>  
 <span data-ttu-id="2cdea-112">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="2cdea-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="2cdea-113">Attribute</span><span class="sxs-lookup"><span data-stu-id="2cdea-113">Attributes</span></span>  
  
|<span data-ttu-id="2cdea-114">Attribut</span><span class="sxs-lookup"><span data-stu-id="2cdea-114">Attribute</span></span>|<span data-ttu-id="2cdea-115">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="2cdea-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="2cdea-116">Wert</span><span class="sxs-lookup"><span data-stu-id="2cdea-116">value</span></span>|<span data-ttu-id="2cdea-117">Eine Zeichenfolge, die den URI an, der den Anspruchstyp des Anspruchs, verwenden Sie für den Anspruchstyp "Rolle" darstellt.</span><span class="sxs-lookup"><span data-stu-id="2cdea-117">A string that specifies the URI that represents the claim type of the claim to use for the role claim type.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="2cdea-118">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="2cdea-118">Child Elements</span></span>  
 <span data-ttu-id="2cdea-119">Keine</span><span class="sxs-lookup"><span data-stu-id="2cdea-119">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="2cdea-120">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="2cdea-120">Parent Elements</span></span>  
  
|<span data-ttu-id="2cdea-121">Element</span><span class="sxs-lookup"><span data-stu-id="2cdea-121">Element</span></span>|<span data-ttu-id="2cdea-122">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="2cdea-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="2cdea-123">\<SamlSecurityTokenRequirement ></span><span class="sxs-lookup"><span data-stu-id="2cdea-123">\<samlSecurityTokenRequirement></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/samlsecuritytokenrequirement.md)|<span data-ttu-id="2cdea-124">Ermöglicht die Konfiguration für die <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler> -Klasse, die <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> Klasse oder eine abgeleitete Klasse von einer dieser Klassen.</span><span class="sxs-lookup"><span data-stu-id="2cdea-124">Provides configuration for the <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler> class, the <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> class, or a derived class of either of these classes.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2cdea-125">Hinweise</span><span class="sxs-lookup"><span data-stu-id="2cdea-125">Remarks</span></span>  
 <span data-ttu-id="2cdea-126">Die `<roleClaimType>` Element legt die <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement.RoleClaimType%2A> Eigenschaft bei einer <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement> -Objekt aus der Konfiguration initialisiert wird.</span><span class="sxs-lookup"><span data-stu-id="2cdea-126">The `<roleClaimType>` element sets the <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement.RoleClaimType%2A> property when a <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement> object is initialized from configuration.</span></span>  
  
## <a name="example"></a><span data-ttu-id="2cdea-127">Beispiel</span><span class="sxs-lookup"><span data-stu-id="2cdea-127">Example</span></span>  
  
```xml  
<add type="System.IdentityModel.Tokens.SamlSecurityTokenHandler, System.IdentityModel">  
    <samlSecurityTokenRequirement>  
        <roleClaimType value="schemas.microsoft.com/ws/2006/04/identity/claims/role" />  
    </samlSecurityTokenRequirement>  
</add>  
```  
  
## <a name="see-also"></a><span data-ttu-id="2cdea-128">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="2cdea-128">See Also</span></span>  
 <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement.RoleClaimType%2A>
