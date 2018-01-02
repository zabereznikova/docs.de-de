---
title: '&lt;userNameSecurityTokenHandlerRequirement&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 6ec3bac1-b014-49ae-843c-c54518cb709a
caps.latest.revision: "4"
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.workload: dotnet
ms.openlocfilehash: 31e0c2cf10b8bc93ade0d417763075c4419ac19f
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="ltusernamesecuritytokenhandlerrequirementgt"></a><span data-ttu-id="3622a-102">&lt;userNameSecurityTokenHandlerRequirement&gt;</span><span class="sxs-lookup"><span data-stu-id="3622a-102">&lt;userNameSecurityTokenHandlerRequirement&gt;</span></span>
<span data-ttu-id="3622a-103">Ermöglicht die Konfiguration für die <xref:System.IdentityModel.Services.Tokens.MembershipUserNameSecurityTokenHandler> abgeleiteten Klassen.</span><span class="sxs-lookup"><span data-stu-id="3622a-103">Provides configuration for the <xref:System.IdentityModel.Services.Tokens.MembershipUserNameSecurityTokenHandler> class or derived classes.</span></span>  
  
 <span data-ttu-id="3622a-104">\<system.identityModel ></span><span class="sxs-lookup"><span data-stu-id="3622a-104">\<system.identityModel></span></span>  
<span data-ttu-id="3622a-105">\<IdentityConfiguration ></span><span class="sxs-lookup"><span data-stu-id="3622a-105">\<identityConfiguration></span></span>  
<span data-ttu-id="3622a-106">\<SecurityTokenHandlers ></span><span class="sxs-lookup"><span data-stu-id="3622a-106">\<securityTokenHandlers></span></span>  
<span data-ttu-id="3622a-107">\<add></span><span class="sxs-lookup"><span data-stu-id="3622a-107">\<add></span></span>  
<span data-ttu-id="3622a-108">\<UserNameSecurityTokenHandlerRequirement ></span><span class="sxs-lookup"><span data-stu-id="3622a-108">\<userNameSecurityTokenHandlerRequirement></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3622a-109">Syntax</span><span class="sxs-lookup"><span data-stu-id="3622a-109">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="3622a-110">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="3622a-110">Attributes and Elements</span></span>  
 <span data-ttu-id="3622a-111">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="3622a-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="3622a-112">Attribute</span><span class="sxs-lookup"><span data-stu-id="3622a-112">Attributes</span></span>  
  
|<span data-ttu-id="3622a-113">Attribut</span><span class="sxs-lookup"><span data-stu-id="3622a-113">Attribute</span></span>|<span data-ttu-id="3622a-114">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="3622a-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="3622a-115">membershipProviderName</span><span class="sxs-lookup"><span data-stu-id="3622a-115">membershipProviderName</span></span>|<span data-ttu-id="3622a-116">Gibt an, die <xref:System.Web.Security.MembershipProvider> vom Security token Handler verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="3622a-116">Specifies the <xref:System.Web.Security.MembershipProvider> that should be used by the security token handler.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="3622a-117">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="3622a-117">Child Elements</span></span>  
 <span data-ttu-id="3622a-118">Keiner</span><span class="sxs-lookup"><span data-stu-id="3622a-118">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="3622a-119">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="3622a-119">Parent Elements</span></span>  
  
|<span data-ttu-id="3622a-120">Element</span><span class="sxs-lookup"><span data-stu-id="3622a-120">Element</span></span>|<span data-ttu-id="3622a-121">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="3622a-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="3622a-122">\<add></span><span class="sxs-lookup"><span data-stu-id="3622a-122">\<add></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/add.md)|<span data-ttu-id="3622a-123">Fügt den angegebenen Sicherheits-Tokenhandler der Tokenhandler Auflistung hinzu.</span><span class="sxs-lookup"><span data-stu-id="3622a-123">Adds the specified security token handler to the token handler collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3622a-124">Hinweise</span><span class="sxs-lookup"><span data-stu-id="3622a-124">Remarks</span></span>  
 <span data-ttu-id="3622a-125">Die `<userNameSecurityTokenHandlerRequirement>` Element legt die <xref:System.IdentityModel.Services.Tokens.MembershipUserNameSecurityTokenHandler.MembershipProvider%2A> Eigenschaft bei einer <xref:System.IdentityModel.Services.Tokens.MembershipUserNameSecurityTokenHandler> -Objekt aus der Konfiguration initialisiert wird.</span><span class="sxs-lookup"><span data-stu-id="3622a-125">The `<userNameSecurityTokenHandlerRequirement>` element sets the <xref:System.IdentityModel.Services.Tokens.MembershipUserNameSecurityTokenHandler.MembershipProvider%2A> property when a <xref:System.IdentityModel.Services.Tokens.MembershipUserNameSecurityTokenHandler> object is initialized from configuration.</span></span>  
  
## <a name="example"></a><span data-ttu-id="3622a-126">Beispiel</span><span class="sxs-lookup"><span data-stu-id="3622a-126">Example</span></span>  
  
```xml  
<add type="System.IdentityModel.Services.Tokens.MembershipUserNameSecurityTokenHandler, System.IdentityModel.Services">  
    <userNameSecurityTokenHandlerRequirement membershipProviderName="AspNetSqlProvider/>  
</add>  
```
