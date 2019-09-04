---
title: <nameClaimType>
ms.date: 03/30/2017
ms.assetid: 17514d95-f0f5-4789-8e28-346640dc227c
author: BrucePerlerMS
ms.openlocfilehash: 4bf8ad2f70499edfc72dd9fcd9a5d8a0aafbbc66
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/04/2019
ms.locfileid: "70251940"
---
# <a name="nameclaimtype"></a><span data-ttu-id="4c0e2-101">\<nameClaimType></span><span class="sxs-lookup"><span data-stu-id="4c0e2-101">\<nameClaimType></span></span>
<span data-ttu-id="4c0e2-102">Legt den Anspruchstyp fest, der <xref:System.Security.Principal.IIdentity.Name%2A> die Eigenschaft angibt.</span><span class="sxs-lookup"><span data-stu-id="4c0e2-102">Sets the claim type that specifies the <xref:System.Security.Principal.IIdentity.Name%2A> property.</span></span> <span data-ttu-id="4c0e2-103">Der Anspruchstyp wird verwendet, um <xref:System.Security.Claims.Claim> in der Auflistung von <xref:System.Security.Claims.ClaimsIdentity> -Objekten zu suchen, die <xref:System.IdentityModel.Tokens.SecurityTokenHandler.ValidateToken%2A> von der-Methode dieses tokenhandlers zurückgegeben werden.</span><span class="sxs-lookup"><span data-stu-id="4c0e2-103">The claim type is used to search for a <xref:System.Security.Claims.Claim> in the collection of <xref:System.Security.Claims.ClaimsIdentity> objects returned by the <xref:System.IdentityModel.Tokens.SecurityTokenHandler.ValidateToken%2A> method of this token handler.</span></span> <span data-ttu-id="4c0e2-104">Der Wert des übereinstimmenden Anspruchs wird dann als Name <xref:System.Security.Principal.IIdentity> der von diesem Tokenhandler generierten festgelegt.</span><span class="sxs-lookup"><span data-stu-id="4c0e2-104">The value of the matching claim is then set as the name of the <xref:System.Security.Principal.IIdentity> generated from this token handler.</span></span>  
  
<span data-ttu-id="4c0e2-105">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="4c0e2-105">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="4c0e2-106">&nbsp;&nbsp;[ **\<System. IdentityModel->** ](system-identitymodel.md)</span><span class="sxs-lookup"><span data-stu-id="4c0e2-106">&nbsp;&nbsp;[**\<system.identityModel>**](system-identitymodel.md)</span></span>\
<span data-ttu-id="4c0e2-107">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<identityconfiguration->** ](identityconfiguration.md)</span><span class="sxs-lookup"><span data-stu-id="4c0e2-107">&nbsp;&nbsp;&nbsp;&nbsp;[**\<identityConfiguration>**](identityconfiguration.md)</span></span>\
<span data-ttu-id="4c0e2-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<securitytokenhandlers >** ](securitytokenhandlers.md)</span><span class="sxs-lookup"><span data-stu-id="4c0e2-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<securityTokenHandlers>**](securitytokenhandlers.md)</span></span>\
<span data-ttu-id="4c0e2-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> Hinzufügen**](add.md)</span><span class="sxs-lookup"><span data-stu-id="4c0e2-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<add>**](add.md)</span></span>\
<span data-ttu-id="4c0e2-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<samlsecuritytokenrequirements->** ](samlsecuritytokenrequirement.md)</span><span class="sxs-lookup"><span data-stu-id="4c0e2-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<samlSecurityTokenRequirement>**](samlsecuritytokenrequirement.md)</span></span>\
<span data-ttu-id="4c0e2-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<nameclaimtype->**</span><span class="sxs-lookup"><span data-stu-id="4c0e2-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<nameClaimType>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4c0e2-112">Syntax</span><span class="sxs-lookup"><span data-stu-id="4c0e2-112">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="4c0e2-113">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="4c0e2-113">Attributes and Elements</span></span>  
 <span data-ttu-id="4c0e2-114">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="4c0e2-114">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="4c0e2-115">Attribute</span><span class="sxs-lookup"><span data-stu-id="4c0e2-115">Attributes</span></span>  
  
|<span data-ttu-id="4c0e2-116">Attribut</span><span class="sxs-lookup"><span data-stu-id="4c0e2-116">Attribute</span></span>|<span data-ttu-id="4c0e2-117">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="4c0e2-117">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="4c0e2-118">Wert</span><span class="sxs-lookup"><span data-stu-id="4c0e2-118">value</span></span>|<span data-ttu-id="4c0e2-119">Eine Zeichenfolge, die den URI angibt, der den Anspruchstyp des Anspruchs darstellt, der <xref:System.Security.Principal.IIdentity.Name%2A> für die Eigenschaft verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="4c0e2-119">A string that specifies the URI that represents the claim type of the claim to use for the <xref:System.Security.Principal.IIdentity.Name%2A> property.</span></span> <span data-ttu-id="4c0e2-120">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="4c0e2-120">Required.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="4c0e2-121">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="4c0e2-121">Child Elements</span></span>  
 <span data-ttu-id="4c0e2-122">None</span><span class="sxs-lookup"><span data-stu-id="4c0e2-122">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="4c0e2-123">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="4c0e2-123">Parent Elements</span></span>  
  
|<span data-ttu-id="4c0e2-124">Element</span><span class="sxs-lookup"><span data-stu-id="4c0e2-124">Element</span></span>|<span data-ttu-id="4c0e2-125">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="4c0e2-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="4c0e2-126">\<samlSecurityTokenRequirement></span><span class="sxs-lookup"><span data-stu-id="4c0e2-126">\<samlSecurityTokenRequirement></span></span>](samlsecuritytokenrequirement.md)|<span data-ttu-id="4c0e2-127">Stellt die Konfiguration für <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler> die-Klasse <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> , die-Klasse oder eine abgeleitete Klasse einer dieser Klassen bereit.</span><span class="sxs-lookup"><span data-stu-id="4c0e2-127">Provides configuration for the <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler> class, the <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> class, or a derived class of either of these classes.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4c0e2-128">Hinweise</span><span class="sxs-lookup"><span data-stu-id="4c0e2-128">Remarks</span></span>  
 <span data-ttu-id="4c0e2-129">Das `<nameClaimType>` -Element legt <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement.NameClaimType%2A> die-Eigenschaft <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement> fest, wenn ein-Objekt aus der Konfiguration initialisiert wird.</span><span class="sxs-lookup"><span data-stu-id="4c0e2-129">The `<nameClaimType>` element sets the <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement.NameClaimType%2A> property when a <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement> object is initialized from configuration.</span></span>  
  
## <a name="example"></a><span data-ttu-id="4c0e2-130">Beispiel</span><span class="sxs-lookup"><span data-stu-id="4c0e2-130">Example</span></span>  
  
```xml  
<add type="System.IdentityModel.Tokens.SamlSecurityTokenHandler, System.IdentityModel">  
    <samlSecurityTokenRequirement>  
        <nameClaimType value="http://schemas.xmlsoap.org/ws/2005/05/identity/claims/name" />  
    </samlSecurityTokenRequirement>  
</add>  
```  
  
## <a name="see-also"></a><span data-ttu-id="4c0e2-131">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="4c0e2-131">See also</span></span>

- <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement.NameClaimType%2A>
