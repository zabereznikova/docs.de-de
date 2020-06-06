---
title: <roleClaimType>
ms.date: 03/30/2017
ms.assetid: 69a49deb-6369-41ba-806b-ae8d21fac64b
author: BrucePerlerMS
ms.openlocfilehash: 0f651377346b1f14a4226128cd5cf7059543adca
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/06/2020
ms.locfileid: "70251913"
---
# \<roleClaimType>
<span data-ttu-id="62cd8-101">Gibt den Anspruchstyp an, der die Rollen Typen Ansprüche in der Auflistung von-Objekten definiert, die <xref:System.Security.Claims.ClaimsIdentity> von der- <xref:System.IdentityModel.Tokens.SecurityTokenHandler.ValidateToken%2A> Methode des tokenhandlers zurückgegeben werden.</span><span class="sxs-lookup"><span data-stu-id="62cd8-101">Specifies the claim type that defines the role type claims in the collection of <xref:System.Security.Claims.ClaimsIdentity> objects returned by the <xref:System.IdentityModel.Tokens.SecurityTokenHandler.ValidateToken%2A> method of the token handler.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.identityModel>**](system-identitymodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<identityConfiguration>**](identityconfiguration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<securityTokenHandlers>**](securitytokenhandlers.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<add>**](add.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<samlSecurityTokenRequirement>**](samlsecuritytokenrequirement.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<roleClaimType>**  
  
## <a name="syntax"></a><span data-ttu-id="62cd8-102">Syntax</span><span class="sxs-lookup"><span data-stu-id="62cd8-102">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="62cd8-103">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="62cd8-103">Attributes and Elements</span></span>  
 <span data-ttu-id="62cd8-104">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="62cd8-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="62cd8-105">Attribute</span><span class="sxs-lookup"><span data-stu-id="62cd8-105">Attributes</span></span>  
  
|<span data-ttu-id="62cd8-106">attribute</span><span class="sxs-lookup"><span data-stu-id="62cd8-106">Attribute</span></span>|<span data-ttu-id="62cd8-107">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="62cd8-107">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="62cd8-108">value</span><span class="sxs-lookup"><span data-stu-id="62cd8-108">value</span></span>|<span data-ttu-id="62cd8-109">Eine Zeichenfolge, die den URI angibt, der den Anspruchstyp des Anspruchs darstellt, der für den Rollen Anspruchstyp verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="62cd8-109">A string that specifies the URI that represents the claim type of the claim to use for the role claim type.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="62cd8-110">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="62cd8-110">Child Elements</span></span>  
 <span data-ttu-id="62cd8-111">Keine</span><span class="sxs-lookup"><span data-stu-id="62cd8-111">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="62cd8-112">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="62cd8-112">Parent Elements</span></span>  
  
|<span data-ttu-id="62cd8-113">Element</span><span class="sxs-lookup"><span data-stu-id="62cd8-113">Element</span></span>|<span data-ttu-id="62cd8-114">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="62cd8-114">Description</span></span>|  
|-------------|-----------------|  
|[\<samlSecurityTokenRequirement>](samlsecuritytokenrequirement.md)|<span data-ttu-id="62cd8-115">Stellt die Konfiguration für die- <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler> Klasse, die- <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> Klasse oder eine abgeleitete Klasse einer dieser Klassen bereit.</span><span class="sxs-lookup"><span data-stu-id="62cd8-115">Provides configuration for the <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler> class, the <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> class, or a derived class of either of these classes.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="62cd8-116">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="62cd8-116">Remarks</span></span>  
 <span data-ttu-id="62cd8-117">Das- `<roleClaimType>` Element legt die-Eigenschaft fest, <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement.RoleClaimType%2A> Wenn ein- <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement> Objekt aus der Konfiguration initialisiert wird.</span><span class="sxs-lookup"><span data-stu-id="62cd8-117">The `<roleClaimType>` element sets the <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement.RoleClaimType%2A> property when a <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement> object is initialized from configuration.</span></span>  
  
## <a name="example"></a><span data-ttu-id="62cd8-118">Beispiel</span><span class="sxs-lookup"><span data-stu-id="62cd8-118">Example</span></span>  
  
```xml  
<add type="System.IdentityModel.Tokens.SamlSecurityTokenHandler, System.IdentityModel">  
    <samlSecurityTokenRequirement>  
        <roleClaimType value="schemas.microsoft.com/ws/2006/04/identity/claims/role" />  
    </samlSecurityTokenRequirement>  
</add>  
```  
  
## <a name="see-also"></a><span data-ttu-id="62cd8-119">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="62cd8-119">See also</span></span>

- <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement.RoleClaimType%2A>
