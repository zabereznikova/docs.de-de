---
title: <nameClaimType>
ms.date: 03/30/2017
ms.assetid: 17514d95-f0f5-4789-8e28-346640dc227c
author: BrucePerlerMS
ms.openlocfilehash: 47366c5bb2bd9228268fce3ae6e1fb5ad457dab1
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69942620"
---
# <a name="nameclaimtype"></a><span data-ttu-id="30b75-101">\<nameClaimType></span><span class="sxs-lookup"><span data-stu-id="30b75-101">\<nameClaimType></span></span>
<span data-ttu-id="30b75-102">Legt den Anspruchstyp fest, der <xref:System.Security.Principal.IIdentity.Name%2A> die Eigenschaft angibt.</span><span class="sxs-lookup"><span data-stu-id="30b75-102">Sets the claim type that specifies the <xref:System.Security.Principal.IIdentity.Name%2A> property.</span></span> <span data-ttu-id="30b75-103">Der Anspruchstyp wird verwendet, um <xref:System.Security.Claims.Claim> in der Auflistung von <xref:System.Security.Claims.ClaimsIdentity> -Objekten zu suchen, die <xref:System.IdentityModel.Tokens.SecurityTokenHandler.ValidateToken%2A> von der-Methode dieses tokenhandlers zurückgegeben werden.</span><span class="sxs-lookup"><span data-stu-id="30b75-103">The claim type is used to search for a <xref:System.Security.Claims.Claim> in the collection of <xref:System.Security.Claims.ClaimsIdentity> objects returned by the <xref:System.IdentityModel.Tokens.SecurityTokenHandler.ValidateToken%2A> method of this token handler.</span></span> <span data-ttu-id="30b75-104">Der Wert des übereinstimmenden Anspruchs wird dann als Name <xref:System.Security.Principal.IIdentity> der von diesem Tokenhandler generierten festgelegt.</span><span class="sxs-lookup"><span data-stu-id="30b75-104">The value of the matching claim is then set as the name of the <xref:System.Security.Principal.IIdentity> generated from this token handler.</span></span>  
  
 <span data-ttu-id="30b75-105">\<system.identityModel></span><span class="sxs-lookup"><span data-stu-id="30b75-105">\<system.identityModel></span></span>  
<span data-ttu-id="30b75-106">\<identityConfiguration></span><span class="sxs-lookup"><span data-stu-id="30b75-106">\<identityConfiguration></span></span>  
<span data-ttu-id="30b75-107">\<securityTokenHandlers></span><span class="sxs-lookup"><span data-stu-id="30b75-107">\<securityTokenHandlers></span></span>  
<span data-ttu-id="30b75-108">\<add></span><span class="sxs-lookup"><span data-stu-id="30b75-108">\<add></span></span>  
<span data-ttu-id="30b75-109">\<samlSecurityTokenRequirement></span><span class="sxs-lookup"><span data-stu-id="30b75-109">\<samlSecurityTokenRequirement></span></span>  
<span data-ttu-id="30b75-110">\<nameClaimType></span><span class="sxs-lookup"><span data-stu-id="30b75-110">\<nameClaimType></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="30b75-111">Syntax</span><span class="sxs-lookup"><span data-stu-id="30b75-111">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="30b75-112">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="30b75-112">Attributes and Elements</span></span>  
 <span data-ttu-id="30b75-113">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="30b75-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="30b75-114">Attribute</span><span class="sxs-lookup"><span data-stu-id="30b75-114">Attributes</span></span>  
  
|<span data-ttu-id="30b75-115">Attribut</span><span class="sxs-lookup"><span data-stu-id="30b75-115">Attribute</span></span>|<span data-ttu-id="30b75-116">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="30b75-116">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="30b75-117">Wert</span><span class="sxs-lookup"><span data-stu-id="30b75-117">value</span></span>|<span data-ttu-id="30b75-118">Eine Zeichenfolge, die den URI angibt, der den Anspruchstyp des Anspruchs darstellt, der <xref:System.Security.Principal.IIdentity.Name%2A> für die Eigenschaft verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="30b75-118">A string that specifies the URI that represents the claim type of the claim to use for the <xref:System.Security.Principal.IIdentity.Name%2A> property.</span></span> <span data-ttu-id="30b75-119">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="30b75-119">Required.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="30b75-120">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="30b75-120">Child Elements</span></span>  
 <span data-ttu-id="30b75-121">None</span><span class="sxs-lookup"><span data-stu-id="30b75-121">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="30b75-122">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="30b75-122">Parent Elements</span></span>  
  
|<span data-ttu-id="30b75-123">Element</span><span class="sxs-lookup"><span data-stu-id="30b75-123">Element</span></span>|<span data-ttu-id="30b75-124">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="30b75-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="30b75-125">\<samlSecurityTokenRequirement></span><span class="sxs-lookup"><span data-stu-id="30b75-125">\<samlSecurityTokenRequirement></span></span>](samlsecuritytokenrequirement.md)|<span data-ttu-id="30b75-126">Stellt die Konfiguration für <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler> die-Klasse <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> , die-Klasse oder eine abgeleitete Klasse einer dieser Klassen bereit.</span><span class="sxs-lookup"><span data-stu-id="30b75-126">Provides configuration for the <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler> class, the <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> class, or a derived class of either of these classes.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="30b75-127">Hinweise</span><span class="sxs-lookup"><span data-stu-id="30b75-127">Remarks</span></span>  
 <span data-ttu-id="30b75-128">Das `<nameClaimType>` -Element legt <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement.NameClaimType%2A> die-Eigenschaft <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement> fest, wenn ein-Objekt aus der Konfiguration initialisiert wird.</span><span class="sxs-lookup"><span data-stu-id="30b75-128">The `<nameClaimType>` element sets the <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement.NameClaimType%2A> property when a <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement> object is initialized from configuration.</span></span>  
  
## <a name="example"></a><span data-ttu-id="30b75-129">Beispiel</span><span class="sxs-lookup"><span data-stu-id="30b75-129">Example</span></span>  
  
```xml  
<add type="System.IdentityModel.Tokens.SamlSecurityTokenHandler, System.IdentityModel">  
    <samlSecurityTokenRequirement>  
        <nameClaimType value="http://schemas.xmlsoap.org/ws/2005/05/identity/claims/name" />  
    </samlSecurityTokenRequirement>  
</add>  
```  
  
## <a name="see-also"></a><span data-ttu-id="30b75-130">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="30b75-130">See also</span></span>

- <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement.NameClaimType%2A>
