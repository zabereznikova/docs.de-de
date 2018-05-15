---
title: '&lt;userNameSecurityTokenHandlerRequirement&gt;'
ms.date: 03/30/2017
ms.assetid: 6ec3bac1-b014-49ae-843c-c54518cb709a
author: BrucePerlerMS
manager: mbaldwin
ms.openlocfilehash: 5d725cc0d16457f2bdfb404baf4758e3431ce6b7
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
---
# <a name="ltusernamesecuritytokenhandlerrequirementgt"></a><span data-ttu-id="fb28b-102">&lt;userNameSecurityTokenHandlerRequirement&gt;</span><span class="sxs-lookup"><span data-stu-id="fb28b-102">&lt;userNameSecurityTokenHandlerRequirement&gt;</span></span>
<span data-ttu-id="fb28b-103">Ermöglicht die Konfiguration für die <xref:System.IdentityModel.Services.Tokens.MembershipUserNameSecurityTokenHandler> abgeleiteten Klassen.</span><span class="sxs-lookup"><span data-stu-id="fb28b-103">Provides configuration for the <xref:System.IdentityModel.Services.Tokens.MembershipUserNameSecurityTokenHandler> class or derived classes.</span></span>  
  
 <span data-ttu-id="fb28b-104">\<system.identityModel></span><span class="sxs-lookup"><span data-stu-id="fb28b-104">\<system.identityModel></span></span>  
<span data-ttu-id="fb28b-105">\<identityConfiguration></span><span class="sxs-lookup"><span data-stu-id="fb28b-105">\<identityConfiguration></span></span>  
<span data-ttu-id="fb28b-106">\<SecurityTokenHandlers ></span><span class="sxs-lookup"><span data-stu-id="fb28b-106">\<securityTokenHandlers></span></span>  
<span data-ttu-id="fb28b-107">\<add></span><span class="sxs-lookup"><span data-stu-id="fb28b-107">\<add></span></span>  
<span data-ttu-id="fb28b-108">\<UserNameSecurityTokenHandlerRequirement ></span><span class="sxs-lookup"><span data-stu-id="fb28b-108">\<userNameSecurityTokenHandlerRequirement></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fb28b-109">Syntax</span><span class="sxs-lookup"><span data-stu-id="fb28b-109">Syntax</span></span>  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <securityTokenHandlers>  
      <add type="System.IdentityModel.Services.Tokens.MembershipUserNameSecurityTokenHandler, System.IdentityModel.Services">  
        <userNameSecurityTokenHandlerRequirement membershipProviderName=xs:string >  
        </userNameSecurityTokenHandlerRequirement>  
      </add>  
    </securityTokenHandlers>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="fb28b-110">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="fb28b-110">Attributes and Elements</span></span>  
 <span data-ttu-id="fb28b-111">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="fb28b-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="fb28b-112">Attribute</span><span class="sxs-lookup"><span data-stu-id="fb28b-112">Attributes</span></span>  
  
|<span data-ttu-id="fb28b-113">Attribut</span><span class="sxs-lookup"><span data-stu-id="fb28b-113">Attribute</span></span>|<span data-ttu-id="fb28b-114">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="fb28b-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="fb28b-115">membershipProviderName</span><span class="sxs-lookup"><span data-stu-id="fb28b-115">membershipProviderName</span></span>|<span data-ttu-id="fb28b-116">Gibt an, die <xref:System.Web.Security.MembershipProvider> vom Security token Handler verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="fb28b-116">Specifies the <xref:System.Web.Security.MembershipProvider> that should be used by the security token handler.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="fb28b-117">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="fb28b-117">Child Elements</span></span>  
 <span data-ttu-id="fb28b-118">Keiner</span><span class="sxs-lookup"><span data-stu-id="fb28b-118">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="fb28b-119">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="fb28b-119">Parent Elements</span></span>  
  
|<span data-ttu-id="fb28b-120">Element</span><span class="sxs-lookup"><span data-stu-id="fb28b-120">Element</span></span>|<span data-ttu-id="fb28b-121">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="fb28b-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="fb28b-122">\<add></span><span class="sxs-lookup"><span data-stu-id="fb28b-122">\<add></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/add.md)|<span data-ttu-id="fb28b-123">Fügt den angegebenen Sicherheits-Tokenhandler der Tokenhandler Auflistung hinzu.</span><span class="sxs-lookup"><span data-stu-id="fb28b-123">Adds the specified security token handler to the token handler collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="fb28b-124">Hinweise</span><span class="sxs-lookup"><span data-stu-id="fb28b-124">Remarks</span></span>  
 <span data-ttu-id="fb28b-125">Die `<userNameSecurityTokenHandlerRequirement>` Element legt die <xref:System.IdentityModel.Services.Tokens.MembershipUserNameSecurityTokenHandler.MembershipProvider%2A> Eigenschaft bei einer <xref:System.IdentityModel.Services.Tokens.MembershipUserNameSecurityTokenHandler> -Objekt aus der Konfiguration initialisiert wird.</span><span class="sxs-lookup"><span data-stu-id="fb28b-125">The `<userNameSecurityTokenHandlerRequirement>` element sets the <xref:System.IdentityModel.Services.Tokens.MembershipUserNameSecurityTokenHandler.MembershipProvider%2A> property when a <xref:System.IdentityModel.Services.Tokens.MembershipUserNameSecurityTokenHandler> object is initialized from configuration.</span></span>  
  
## <a name="example"></a><span data-ttu-id="fb28b-126">Beispiel</span><span class="sxs-lookup"><span data-stu-id="fb28b-126">Example</span></span>  
  
```xml  
<add type="System.IdentityModel.Services.Tokens.MembershipUserNameSecurityTokenHandler, System.IdentityModel.Services">  
    <userNameSecurityTokenHandlerRequirement membershipProviderName="AspNetSqlProvider/>  
</add>  
```
