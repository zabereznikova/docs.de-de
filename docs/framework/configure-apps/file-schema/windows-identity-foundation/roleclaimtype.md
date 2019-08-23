---
title: <roleClaimType>
ms.date: 03/30/2017
ms.assetid: 69a49deb-6369-41ba-806b-ae8d21fac64b
author: BrucePerlerMS
ms.openlocfilehash: 0ce2e06ee895d09de193bac1fe7038e71794dda4
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69942538"
---
# <a name="roleclaimtype"></a><span data-ttu-id="3acee-101">\<roleClaimType></span><span class="sxs-lookup"><span data-stu-id="3acee-101">\<roleClaimType></span></span>
<span data-ttu-id="3acee-102">Gibt den Anspruchstyp an, der die Rollen Typen Ansprüche in der Auflistung <xref:System.Security.Claims.ClaimsIdentity> von-Objekten definiert <xref:System.IdentityModel.Tokens.SecurityTokenHandler.ValidateToken%2A> , die von der-Methode des tokenhandlers zurückgegeben werden.</span><span class="sxs-lookup"><span data-stu-id="3acee-102">Specifies the claim type that defines the role type claims in the collection of <xref:System.Security.Claims.ClaimsIdentity> objects returned by the <xref:System.IdentityModel.Tokens.SecurityTokenHandler.ValidateToken%2A> method of the token handler.</span></span>  
  
 <span data-ttu-id="3acee-103">\<system.identityModel></span><span class="sxs-lookup"><span data-stu-id="3acee-103">\<system.identityModel></span></span>  
<span data-ttu-id="3acee-104">\<identityConfiguration></span><span class="sxs-lookup"><span data-stu-id="3acee-104">\<identityConfiguration></span></span>  
<span data-ttu-id="3acee-105">\<securityTokenHandlers></span><span class="sxs-lookup"><span data-stu-id="3acee-105">\<securityTokenHandlers></span></span>  
<span data-ttu-id="3acee-106">\<add></span><span class="sxs-lookup"><span data-stu-id="3acee-106">\<add></span></span>  
<span data-ttu-id="3acee-107">\<samlSecurityTokenRequirement></span><span class="sxs-lookup"><span data-stu-id="3acee-107">\<samlSecurityTokenRequirement></span></span>  
<span data-ttu-id="3acee-108">\<roleClaimType></span><span class="sxs-lookup"><span data-stu-id="3acee-108">\<roleClaimType></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3acee-109">Syntax</span><span class="sxs-lookup"><span data-stu-id="3acee-109">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="3acee-110">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="3acee-110">Attributes and Elements</span></span>  
 <span data-ttu-id="3acee-111">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="3acee-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="3acee-112">Attribute</span><span class="sxs-lookup"><span data-stu-id="3acee-112">Attributes</span></span>  
  
|<span data-ttu-id="3acee-113">Attribut</span><span class="sxs-lookup"><span data-stu-id="3acee-113">Attribute</span></span>|<span data-ttu-id="3acee-114">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="3acee-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="3acee-115">Wert</span><span class="sxs-lookup"><span data-stu-id="3acee-115">value</span></span>|<span data-ttu-id="3acee-116">Eine Zeichenfolge, die den URI angibt, der den Anspruchstyp des Anspruchs darstellt, der für den Rollen Anspruchstyp verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="3acee-116">A string that specifies the URI that represents the claim type of the claim to use for the role claim type.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="3acee-117">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="3acee-117">Child Elements</span></span>  
 <span data-ttu-id="3acee-118">None</span><span class="sxs-lookup"><span data-stu-id="3acee-118">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="3acee-119">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="3acee-119">Parent Elements</span></span>  
  
|<span data-ttu-id="3acee-120">Element</span><span class="sxs-lookup"><span data-stu-id="3acee-120">Element</span></span>|<span data-ttu-id="3acee-121">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="3acee-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="3acee-122">\<samlSecurityTokenRequirement></span><span class="sxs-lookup"><span data-stu-id="3acee-122">\<samlSecurityTokenRequirement></span></span>](samlsecuritytokenrequirement.md)|<span data-ttu-id="3acee-123">Stellt die Konfiguration für <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler> die-Klasse <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> , die-Klasse oder eine abgeleitete Klasse einer dieser Klassen bereit.</span><span class="sxs-lookup"><span data-stu-id="3acee-123">Provides configuration for the <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler> class, the <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> class, or a derived class of either of these classes.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3acee-124">Hinweise</span><span class="sxs-lookup"><span data-stu-id="3acee-124">Remarks</span></span>  
 <span data-ttu-id="3acee-125">Das `<roleClaimType>` -Element legt <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement.RoleClaimType%2A> die-Eigenschaft <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement> fest, wenn ein-Objekt aus der Konfiguration initialisiert wird.</span><span class="sxs-lookup"><span data-stu-id="3acee-125">The `<roleClaimType>` element sets the <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement.RoleClaimType%2A> property when a <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement> object is initialized from configuration.</span></span>  
  
## <a name="example"></a><span data-ttu-id="3acee-126">Beispiel</span><span class="sxs-lookup"><span data-stu-id="3acee-126">Example</span></span>  
  
```xml  
<add type="System.IdentityModel.Tokens.SamlSecurityTokenHandler, System.IdentityModel">  
    <samlSecurityTokenRequirement>  
        <roleClaimType value="schemas.microsoft.com/ws/2006/04/identity/claims/role" />  
    </samlSecurityTokenRequirement>  
</add>  
```  
  
## <a name="see-also"></a><span data-ttu-id="3acee-127">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="3acee-127">See also</span></span>

- <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement.RoleClaimType%2A>
