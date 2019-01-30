---
title: <userNameSecurityTokenHandlerRequirement>
ms.date: 03/30/2017
ms.assetid: 6ec3bac1-b014-49ae-843c-c54518cb709a
author: BrucePerlerMS
ms.openlocfilehash: 18769794da8528f085c567264827db5aa6b214f1
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/30/2019
ms.locfileid: "55271888"
---
# <a name="usernamesecuritytokenhandlerrequirement"></a><span data-ttu-id="d9a0f-101">\<userNameSecurityTokenHandlerRequirement></span><span class="sxs-lookup"><span data-stu-id="d9a0f-101">\<userNameSecurityTokenHandlerRequirement></span></span>
<span data-ttu-id="d9a0f-102">Ermöglicht die Konfiguration für die <xref:System.IdentityModel.Services.Tokens.MembershipUserNameSecurityTokenHandler> Klasse oder abgeleitete Klassen.</span><span class="sxs-lookup"><span data-stu-id="d9a0f-102">Provides configuration for the <xref:System.IdentityModel.Services.Tokens.MembershipUserNameSecurityTokenHandler> class or derived classes.</span></span>  
  
 <span data-ttu-id="d9a0f-103">\<system.identityModel></span><span class="sxs-lookup"><span data-stu-id="d9a0f-103">\<system.identityModel></span></span>  
<span data-ttu-id="d9a0f-104">\<identityConfiguration></span><span class="sxs-lookup"><span data-stu-id="d9a0f-104">\<identityConfiguration></span></span>  
<span data-ttu-id="d9a0f-105">\<securityTokenHandlers></span><span class="sxs-lookup"><span data-stu-id="d9a0f-105">\<securityTokenHandlers></span></span>  
<span data-ttu-id="d9a0f-106">\<add></span><span class="sxs-lookup"><span data-stu-id="d9a0f-106">\<add></span></span>  
<span data-ttu-id="d9a0f-107">\<userNameSecurityTokenHandlerRequirement></span><span class="sxs-lookup"><span data-stu-id="d9a0f-107">\<userNameSecurityTokenHandlerRequirement></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d9a0f-108">Syntax</span><span class="sxs-lookup"><span data-stu-id="d9a0f-108">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="d9a0f-109">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="d9a0f-109">Attributes and Elements</span></span>  
 <span data-ttu-id="d9a0f-110">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="d9a0f-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="d9a0f-111">Attribute</span><span class="sxs-lookup"><span data-stu-id="d9a0f-111">Attributes</span></span>  
  
|<span data-ttu-id="d9a0f-112">Attribut</span><span class="sxs-lookup"><span data-stu-id="d9a0f-112">Attribute</span></span>|<span data-ttu-id="d9a0f-113">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="d9a0f-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="d9a0f-114">membershipProviderName</span><span class="sxs-lookup"><span data-stu-id="d9a0f-114">membershipProviderName</span></span>|<span data-ttu-id="d9a0f-115">Gibt an, die <xref:System.Web.Security.MembershipProvider> , die verwendet werden soll, indem Sie den Sicherheitstokenhandler.</span><span class="sxs-lookup"><span data-stu-id="d9a0f-115">Specifies the <xref:System.Web.Security.MembershipProvider> that should be used by the security token handler.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="d9a0f-116">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="d9a0f-116">Child Elements</span></span>  
 <span data-ttu-id="d9a0f-117">Keine</span><span class="sxs-lookup"><span data-stu-id="d9a0f-117">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="d9a0f-118">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="d9a0f-118">Parent Elements</span></span>  
  
|<span data-ttu-id="d9a0f-119">Element</span><span class="sxs-lookup"><span data-stu-id="d9a0f-119">Element</span></span>|<span data-ttu-id="d9a0f-120">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="d9a0f-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="d9a0f-121">\<add></span><span class="sxs-lookup"><span data-stu-id="d9a0f-121">\<add></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/add.md)|<span data-ttu-id="d9a0f-122">Der Tokenhandler-Auflistung hinzugefügt den angegebenen Sicherheitstokenhandler.</span><span class="sxs-lookup"><span data-stu-id="d9a0f-122">Adds the specified security token handler to the token handler collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d9a0f-123">Hinweise</span><span class="sxs-lookup"><span data-stu-id="d9a0f-123">Remarks</span></span>  
 <span data-ttu-id="d9a0f-124">Die `<userNameSecurityTokenHandlerRequirement>` Elementgruppen die <xref:System.IdentityModel.Services.Tokens.MembershipUserNameSecurityTokenHandler.MembershipProvider%2A> Eigenschaft bei einer <xref:System.IdentityModel.Services.Tokens.MembershipUserNameSecurityTokenHandler> -Objekt aus der Konfiguration initialisiert wird.</span><span class="sxs-lookup"><span data-stu-id="d9a0f-124">The `<userNameSecurityTokenHandlerRequirement>` element sets the <xref:System.IdentityModel.Services.Tokens.MembershipUserNameSecurityTokenHandler.MembershipProvider%2A> property when a <xref:System.IdentityModel.Services.Tokens.MembershipUserNameSecurityTokenHandler> object is initialized from configuration.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d9a0f-125">Beispiel</span><span class="sxs-lookup"><span data-stu-id="d9a0f-125">Example</span></span>  
  
```xml  
<add type="System.IdentityModel.Services.Tokens.MembershipUserNameSecurityTokenHandler, System.IdentityModel.Services">  
    <userNameSecurityTokenHandlerRequirement membershipProviderName="AspNetSqlProvider/>  
</add>  
```
