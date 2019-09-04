---
title: <roleClaimType>
ms.date: 03/30/2017
ms.assetid: 69a49deb-6369-41ba-806b-ae8d21fac64b
author: BrucePerlerMS
ms.openlocfilehash: 0f651377346b1f14a4226128cd5cf7059543adca
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/04/2019
ms.locfileid: "70251913"
---
# <a name="roleclaimtype"></a><span data-ttu-id="648fa-101">\<roleClaimType></span><span class="sxs-lookup"><span data-stu-id="648fa-101">\<roleClaimType></span></span>
<span data-ttu-id="648fa-102">Gibt den Anspruchstyp an, der die Rollen Typen Ansprüche in der Auflistung <xref:System.Security.Claims.ClaimsIdentity> von-Objekten definiert <xref:System.IdentityModel.Tokens.SecurityTokenHandler.ValidateToken%2A> , die von der-Methode des tokenhandlers zurückgegeben werden.</span><span class="sxs-lookup"><span data-stu-id="648fa-102">Specifies the claim type that defines the role type claims in the collection of <xref:System.Security.Claims.ClaimsIdentity> objects returned by the <xref:System.IdentityModel.Tokens.SecurityTokenHandler.ValidateToken%2A> method of the token handler.</span></span>  
  
<span data-ttu-id="648fa-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="648fa-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="648fa-104">&nbsp;&nbsp;[ **\<System. IdentityModel->** ](system-identitymodel.md)</span><span class="sxs-lookup"><span data-stu-id="648fa-104">&nbsp;&nbsp;[**\<system.identityModel>**](system-identitymodel.md)</span></span>\
<span data-ttu-id="648fa-105">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<identityconfiguration->** ](identityconfiguration.md)</span><span class="sxs-lookup"><span data-stu-id="648fa-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<identityConfiguration>**](identityconfiguration.md)</span></span>\
<span data-ttu-id="648fa-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<securitytokenhandlers >** ](securitytokenhandlers.md)</span><span class="sxs-lookup"><span data-stu-id="648fa-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<securityTokenHandlers>**](securitytokenhandlers.md)</span></span>\
<span data-ttu-id="648fa-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> Hinzufügen**](add.md)</span><span class="sxs-lookup"><span data-stu-id="648fa-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<add>**](add.md)</span></span>\
<span data-ttu-id="648fa-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<samlsecuritytokenrequirements->** ](samlsecuritytokenrequirement.md)</span><span class="sxs-lookup"><span data-stu-id="648fa-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<samlSecurityTokenRequirement>**](samlsecuritytokenrequirement.md)</span></span>\
<span data-ttu-id="648fa-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<roleclaimtype->**</span><span class="sxs-lookup"><span data-stu-id="648fa-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<roleClaimType>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="648fa-110">Syntax</span><span class="sxs-lookup"><span data-stu-id="648fa-110">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="648fa-111">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="648fa-111">Attributes and Elements</span></span>  
 <span data-ttu-id="648fa-112">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="648fa-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="648fa-113">Attribute</span><span class="sxs-lookup"><span data-stu-id="648fa-113">Attributes</span></span>  
  
|<span data-ttu-id="648fa-114">Attribut</span><span class="sxs-lookup"><span data-stu-id="648fa-114">Attribute</span></span>|<span data-ttu-id="648fa-115">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="648fa-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="648fa-116">Wert</span><span class="sxs-lookup"><span data-stu-id="648fa-116">value</span></span>|<span data-ttu-id="648fa-117">Eine Zeichenfolge, die den URI angibt, der den Anspruchstyp des Anspruchs darstellt, der für den Rollen Anspruchstyp verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="648fa-117">A string that specifies the URI that represents the claim type of the claim to use for the role claim type.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="648fa-118">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="648fa-118">Child Elements</span></span>  
 <span data-ttu-id="648fa-119">None</span><span class="sxs-lookup"><span data-stu-id="648fa-119">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="648fa-120">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="648fa-120">Parent Elements</span></span>  
  
|<span data-ttu-id="648fa-121">Element</span><span class="sxs-lookup"><span data-stu-id="648fa-121">Element</span></span>|<span data-ttu-id="648fa-122">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="648fa-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="648fa-123">\<samlSecurityTokenRequirement></span><span class="sxs-lookup"><span data-stu-id="648fa-123">\<samlSecurityTokenRequirement></span></span>](samlsecuritytokenrequirement.md)|<span data-ttu-id="648fa-124">Stellt die Konfiguration für <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler> die-Klasse <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> , die-Klasse oder eine abgeleitete Klasse einer dieser Klassen bereit.</span><span class="sxs-lookup"><span data-stu-id="648fa-124">Provides configuration for the <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler> class, the <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> class, or a derived class of either of these classes.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="648fa-125">Hinweise</span><span class="sxs-lookup"><span data-stu-id="648fa-125">Remarks</span></span>  
 <span data-ttu-id="648fa-126">Das `<roleClaimType>` -Element legt <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement.RoleClaimType%2A> die-Eigenschaft <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement> fest, wenn ein-Objekt aus der Konfiguration initialisiert wird.</span><span class="sxs-lookup"><span data-stu-id="648fa-126">The `<roleClaimType>` element sets the <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement.RoleClaimType%2A> property when a <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement> object is initialized from configuration.</span></span>  
  
## <a name="example"></a><span data-ttu-id="648fa-127">Beispiel</span><span class="sxs-lookup"><span data-stu-id="648fa-127">Example</span></span>  
  
```xml  
<add type="System.IdentityModel.Tokens.SamlSecurityTokenHandler, System.IdentityModel">  
    <samlSecurityTokenRequirement>  
        <roleClaimType value="schemas.microsoft.com/ws/2006/04/identity/claims/role" />  
    </samlSecurityTokenRequirement>  
</add>  
```  
  
## <a name="see-also"></a><span data-ttu-id="648fa-128">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="648fa-128">See also</span></span>

- <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement.RoleClaimType%2A>
