---
title: <userNameSecurityTokenHandlerRequirement>
ms.date: 03/30/2017
ms.assetid: 6ec3bac1-b014-49ae-843c-c54518cb709a
author: BrucePerlerMS
ms.openlocfilehash: 18769794da8528f085c567264827db5aa6b214f1
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61790454"
---
# <a name="usernamesecuritytokenhandlerrequirement"></a><span data-ttu-id="942be-101">\<userNameSecurityTokenHandlerRequirement></span><span class="sxs-lookup"><span data-stu-id="942be-101">\<userNameSecurityTokenHandlerRequirement></span></span>
<span data-ttu-id="942be-102">Ermöglicht die Konfiguration für die <xref:System.IdentityModel.Services.Tokens.MembershipUserNameSecurityTokenHandler> Klasse oder abgeleitete Klassen.</span><span class="sxs-lookup"><span data-stu-id="942be-102">Provides configuration for the <xref:System.IdentityModel.Services.Tokens.MembershipUserNameSecurityTokenHandler> class or derived classes.</span></span>  
  
 <span data-ttu-id="942be-103">\<system.identityModel></span><span class="sxs-lookup"><span data-stu-id="942be-103">\<system.identityModel></span></span>  
<span data-ttu-id="942be-104">\<identityConfiguration></span><span class="sxs-lookup"><span data-stu-id="942be-104">\<identityConfiguration></span></span>  
<span data-ttu-id="942be-105">\<securityTokenHandlers></span><span class="sxs-lookup"><span data-stu-id="942be-105">\<securityTokenHandlers></span></span>  
<span data-ttu-id="942be-106">\<add></span><span class="sxs-lookup"><span data-stu-id="942be-106">\<add></span></span>  
<span data-ttu-id="942be-107">\<userNameSecurityTokenHandlerRequirement></span><span class="sxs-lookup"><span data-stu-id="942be-107">\<userNameSecurityTokenHandlerRequirement></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="942be-108">Syntax</span><span class="sxs-lookup"><span data-stu-id="942be-108">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="942be-109">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="942be-109">Attributes and Elements</span></span>  
 <span data-ttu-id="942be-110">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="942be-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="942be-111">Attribute</span><span class="sxs-lookup"><span data-stu-id="942be-111">Attributes</span></span>  
  
|<span data-ttu-id="942be-112">Attribut</span><span class="sxs-lookup"><span data-stu-id="942be-112">Attribute</span></span>|<span data-ttu-id="942be-113">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="942be-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="942be-114">membershipProviderName</span><span class="sxs-lookup"><span data-stu-id="942be-114">membershipProviderName</span></span>|<span data-ttu-id="942be-115">Gibt an, die <xref:System.Web.Security.MembershipProvider> , die verwendet werden soll, indem Sie den Sicherheitstokenhandler.</span><span class="sxs-lookup"><span data-stu-id="942be-115">Specifies the <xref:System.Web.Security.MembershipProvider> that should be used by the security token handler.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="942be-116">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="942be-116">Child Elements</span></span>  
 <span data-ttu-id="942be-117">Keiner</span><span class="sxs-lookup"><span data-stu-id="942be-117">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="942be-118">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="942be-118">Parent Elements</span></span>  
  
|<span data-ttu-id="942be-119">Element</span><span class="sxs-lookup"><span data-stu-id="942be-119">Element</span></span>|<span data-ttu-id="942be-120">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="942be-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="942be-121">\<add></span><span class="sxs-lookup"><span data-stu-id="942be-121">\<add></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/add.md)|<span data-ttu-id="942be-122">Der Tokenhandler-Auflistung hinzugefügt den angegebenen Sicherheitstokenhandler.</span><span class="sxs-lookup"><span data-stu-id="942be-122">Adds the specified security token handler to the token handler collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="942be-123">Hinweise</span><span class="sxs-lookup"><span data-stu-id="942be-123">Remarks</span></span>  
 <span data-ttu-id="942be-124">Die `<userNameSecurityTokenHandlerRequirement>` Elementgruppen die <xref:System.IdentityModel.Services.Tokens.MembershipUserNameSecurityTokenHandler.MembershipProvider%2A> Eigenschaft bei einer <xref:System.IdentityModel.Services.Tokens.MembershipUserNameSecurityTokenHandler> -Objekt aus der Konfiguration initialisiert wird.</span><span class="sxs-lookup"><span data-stu-id="942be-124">The `<userNameSecurityTokenHandlerRequirement>` element sets the <xref:System.IdentityModel.Services.Tokens.MembershipUserNameSecurityTokenHandler.MembershipProvider%2A> property when a <xref:System.IdentityModel.Services.Tokens.MembershipUserNameSecurityTokenHandler> object is initialized from configuration.</span></span>  
  
## <a name="example"></a><span data-ttu-id="942be-125">Beispiel</span><span class="sxs-lookup"><span data-stu-id="942be-125">Example</span></span>  
  
```xml  
<add type="System.IdentityModel.Services.Tokens.MembershipUserNameSecurityTokenHandler, System.IdentityModel.Services">  
    <userNameSecurityTokenHandlerRequirement membershipProviderName="AspNetSqlProvider/>  
</add>  
```
