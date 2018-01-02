---
title: '&lt;nameClaimType&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 17514d95-f0f5-4789-8e28-346640dc227c
caps.latest.revision: "4"
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.workload: dotnet
ms.openlocfilehash: 2c53886458b4c6e2867e1f9fddd4ab50b199c660
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="ltnameclaimtypegt"></a><span data-ttu-id="7610f-102">&lt;nameClaimType&gt;</span><span class="sxs-lookup"><span data-stu-id="7610f-102">&lt;nameClaimType&gt;</span></span>
<span data-ttu-id="7610f-103">Legt den Typ des Anspruchs, der angibt, die <xref:System.Security.Principal.IIdentity.Name%2A> Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="7610f-103">Sets the claim type that specifies the <xref:System.Security.Principal.IIdentity.Name%2A> property.</span></span> <span data-ttu-id="7610f-104">Der Typ des Anspruchs zur Suche nach einer <xref:System.Security.Claims.Claim> in der Auflistung der <xref:System.Security.Claims.ClaimsIdentity> zurückgegebenen Objekte die <xref:System.IdentityModel.Tokens.SecurityTokenHandler.ValidateToken%2A> Methode diese Tokenhandler.</span><span class="sxs-lookup"><span data-stu-id="7610f-104">The claim type is used to search for a <xref:System.Security.Claims.Claim> in the collection of <xref:System.Security.Claims.ClaimsIdentity> objects returned by the <xref:System.IdentityModel.Tokens.SecurityTokenHandler.ValidateToken%2A> method of this token handler.</span></span> <span data-ttu-id="7610f-105">Der Wert, der den übereinstimmenden Anspruch wird festgelegt, als den Namen des der <xref:System.Security.Principal.IIdentity> aus diesen token Handler generiert.</span><span class="sxs-lookup"><span data-stu-id="7610f-105">The value of the matching claim is then set as the name of the <xref:System.Security.Principal.IIdentity> generated from this token handler.</span></span>  
  
 <span data-ttu-id="7610f-106">\<system.identityModel ></span><span class="sxs-lookup"><span data-stu-id="7610f-106">\<system.identityModel></span></span>  
<span data-ttu-id="7610f-107">\<IdentityConfiguration ></span><span class="sxs-lookup"><span data-stu-id="7610f-107">\<identityConfiguration></span></span>  
<span data-ttu-id="7610f-108">\<SecurityTokenHandlers ></span><span class="sxs-lookup"><span data-stu-id="7610f-108">\<securityTokenHandlers></span></span>  
<span data-ttu-id="7610f-109">\<add></span><span class="sxs-lookup"><span data-stu-id="7610f-109">\<add></span></span>  
<span data-ttu-id="7610f-110">\<SamlSecurityTokenRequirement ></span><span class="sxs-lookup"><span data-stu-id="7610f-110">\<samlSecurityTokenRequirement></span></span>  
<span data-ttu-id="7610f-111">\<NameClaimType ></span><span class="sxs-lookup"><span data-stu-id="7610f-111">\<nameClaimType></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7610f-112">Syntax</span><span class="sxs-lookup"><span data-stu-id="7610f-112">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="7610f-113">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="7610f-113">Attributes and Elements</span></span>  
 <span data-ttu-id="7610f-114">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="7610f-114">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="7610f-115">Attribute</span><span class="sxs-lookup"><span data-stu-id="7610f-115">Attributes</span></span>  
  
|<span data-ttu-id="7610f-116">Attribut</span><span class="sxs-lookup"><span data-stu-id="7610f-116">Attribute</span></span>|<span data-ttu-id="7610f-117">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="7610f-117">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="7610f-118">Wert</span><span class="sxs-lookup"><span data-stu-id="7610f-118">value</span></span>|<span data-ttu-id="7610f-119">Eine Zeichenfolge, die den URI an, der den Anspruchstyp des Anspruchs, verwenden Sie für die <xref:System.Security.Principal.IIdentity.Name%2A> Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="7610f-119">A string that specifies the URI that represents the claim type of the claim to use for the <xref:System.Security.Principal.IIdentity.Name%2A> property.</span></span> <span data-ttu-id="7610f-120">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="7610f-120">Required.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="7610f-121">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="7610f-121">Child Elements</span></span>  
 <span data-ttu-id="7610f-122">Keiner</span><span class="sxs-lookup"><span data-stu-id="7610f-122">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="7610f-123">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="7610f-123">Parent Elements</span></span>  
  
|<span data-ttu-id="7610f-124">Element</span><span class="sxs-lookup"><span data-stu-id="7610f-124">Element</span></span>|<span data-ttu-id="7610f-125">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="7610f-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="7610f-126">\<SamlSecurityTokenRequirement ></span><span class="sxs-lookup"><span data-stu-id="7610f-126">\<samlSecurityTokenRequirement></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/samlsecuritytokenrequirement.md)|<span data-ttu-id="7610f-127">Ermöglicht die Konfiguration für die <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler> -Klasse, die <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> Klasse oder eine abgeleitete Klasse von einer dieser Klassen.</span><span class="sxs-lookup"><span data-stu-id="7610f-127">Provides configuration for the <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler> class, the <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> class, or a derived class of either of these classes.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="7610f-128">Hinweise</span><span class="sxs-lookup"><span data-stu-id="7610f-128">Remarks</span></span>  
 <span data-ttu-id="7610f-129">Die `<nameClaimType>` Element legt die <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement.NameClaimType%2A> Eigenschaft bei einer <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement> -Objekt aus der Konfiguration initialisiert wird.</span><span class="sxs-lookup"><span data-stu-id="7610f-129">The `<nameClaimType>` element sets the <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement.NameClaimType%2A> property when a <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement> object is initialized from configuration.</span></span>  
  
## <a name="example"></a><span data-ttu-id="7610f-130">Beispiel</span><span class="sxs-lookup"><span data-stu-id="7610f-130">Example</span></span>  
  
```xml  
<add type="System.IdentityModel.Tokens.SamlSecurityTokenHandler, System.IdentityModel">  
    <samlSecurityTokenRequirement>  
        <nameClaimType value="http://schemas.xmlsoap.org/ws/2005/05/identity/claims/name" />  
    </samlSecurityTokenRequirement>  
</add>  
```  
  
## <a name="see-also"></a><span data-ttu-id="7610f-131">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="7610f-131">See Also</span></span>  
 <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement.NameClaimType%2A>
