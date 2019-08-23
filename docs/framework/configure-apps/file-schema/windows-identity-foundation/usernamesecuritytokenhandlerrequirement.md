---
title: <userNameSecurityTokenHandlerRequirement>
ms.date: 03/30/2017
ms.assetid: 6ec3bac1-b014-49ae-843c-c54518cb709a
author: BrucePerlerMS
ms.openlocfilehash: fed8964e03b80e365fdc5eafd45b4fc372a6e352
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69944255"
---
# <a name="usernamesecuritytokenhandlerrequirement"></a><span data-ttu-id="7c893-101">\<userNameSecurityTokenHandlerRequirement></span><span class="sxs-lookup"><span data-stu-id="7c893-101">\<userNameSecurityTokenHandlerRequirement></span></span>
<span data-ttu-id="7c893-102">Stellt die Konfiguration für <xref:System.IdentityModel.Services.Tokens.MembershipUserNameSecurityTokenHandler> die-Klasse oder abgeleitete Klassen bereit.</span><span class="sxs-lookup"><span data-stu-id="7c893-102">Provides configuration for the <xref:System.IdentityModel.Services.Tokens.MembershipUserNameSecurityTokenHandler> class or derived classes.</span></span>  
  
 <span data-ttu-id="7c893-103">\<system.identityModel></span><span class="sxs-lookup"><span data-stu-id="7c893-103">\<system.identityModel></span></span>  
<span data-ttu-id="7c893-104">\<identityConfiguration></span><span class="sxs-lookup"><span data-stu-id="7c893-104">\<identityConfiguration></span></span>  
<span data-ttu-id="7c893-105">\<securityTokenHandlers></span><span class="sxs-lookup"><span data-stu-id="7c893-105">\<securityTokenHandlers></span></span>  
<span data-ttu-id="7c893-106">\<add></span><span class="sxs-lookup"><span data-stu-id="7c893-106">\<add></span></span>  
<span data-ttu-id="7c893-107">\<userNameSecurityTokenHandlerRequirement></span><span class="sxs-lookup"><span data-stu-id="7c893-107">\<userNameSecurityTokenHandlerRequirement></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7c893-108">Syntax</span><span class="sxs-lookup"><span data-stu-id="7c893-108">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="7c893-109">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="7c893-109">Attributes and Elements</span></span>  
 <span data-ttu-id="7c893-110">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="7c893-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="7c893-111">Attribute</span><span class="sxs-lookup"><span data-stu-id="7c893-111">Attributes</span></span>  
  
|<span data-ttu-id="7c893-112">Attribut</span><span class="sxs-lookup"><span data-stu-id="7c893-112">Attribute</span></span>|<span data-ttu-id="7c893-113">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="7c893-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="7c893-114">mitgliedshipprovidername</span><span class="sxs-lookup"><span data-stu-id="7c893-114">membershipProviderName</span></span>|<span data-ttu-id="7c893-115">Gibt die <xref:System.Web.Security.MembershipProvider> an, die vom Sicherheitstokenhandler verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="7c893-115">Specifies the <xref:System.Web.Security.MembershipProvider> that should be used by the security token handler.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="7c893-116">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="7c893-116">Child Elements</span></span>  
 <span data-ttu-id="7c893-117">None</span><span class="sxs-lookup"><span data-stu-id="7c893-117">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="7c893-118">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="7c893-118">Parent Elements</span></span>  
  
|<span data-ttu-id="7c893-119">Element</span><span class="sxs-lookup"><span data-stu-id="7c893-119">Element</span></span>|<span data-ttu-id="7c893-120">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="7c893-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="7c893-121">\<add></span><span class="sxs-lookup"><span data-stu-id="7c893-121">\<add></span></span>](add.md)|<span data-ttu-id="7c893-122">Fügt der tokenhandlerauflistung den angegebenen Sicherheitstokenhandler hinzu.</span><span class="sxs-lookup"><span data-stu-id="7c893-122">Adds the specified security token handler to the token handler collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="7c893-123">Hinweise</span><span class="sxs-lookup"><span data-stu-id="7c893-123">Remarks</span></span>  
 <span data-ttu-id="7c893-124">Das `<userNameSecurityTokenHandlerRequirement>` -Element legt <xref:System.IdentityModel.Services.Tokens.MembershipUserNameSecurityTokenHandler.MembershipProvider%2A> die-Eigenschaft <xref:System.IdentityModel.Services.Tokens.MembershipUserNameSecurityTokenHandler> fest, wenn ein-Objekt aus der Konfiguration initialisiert wird.</span><span class="sxs-lookup"><span data-stu-id="7c893-124">The `<userNameSecurityTokenHandlerRequirement>` element sets the <xref:System.IdentityModel.Services.Tokens.MembershipUserNameSecurityTokenHandler.MembershipProvider%2A> property when a <xref:System.IdentityModel.Services.Tokens.MembershipUserNameSecurityTokenHandler> object is initialized from configuration.</span></span>  
  
## <a name="example"></a><span data-ttu-id="7c893-125">Beispiel</span><span class="sxs-lookup"><span data-stu-id="7c893-125">Example</span></span>  
  
```xml  
<add type="System.IdentityModel.Services.Tokens.MembershipUserNameSecurityTokenHandler, System.IdentityModel.Services">  
    <userNameSecurityTokenHandlerRequirement membershipProviderName="AspNetSqlProvider/>  
</add>  
```
