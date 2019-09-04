---
title: <userNameSecurityTokenHandlerRequirement>
ms.date: 03/30/2017
ms.assetid: 6ec3bac1-b014-49ae-843c-c54518cb709a
author: BrucePerlerMS
ms.openlocfilehash: 5863c01e97e7f5fb6fe07c43174c0d6cb7a0a25d
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/04/2019
ms.locfileid: "70251747"
---
# <a name="usernamesecuritytokenhandlerrequirement"></a><span data-ttu-id="cc40b-101">\<userNameSecurityTokenHandlerRequirement></span><span class="sxs-lookup"><span data-stu-id="cc40b-101">\<userNameSecurityTokenHandlerRequirement></span></span>
<span data-ttu-id="cc40b-102">Stellt die Konfiguration für <xref:System.IdentityModel.Services.Tokens.MembershipUserNameSecurityTokenHandler> die-Klasse oder abgeleitete Klassen bereit.</span><span class="sxs-lookup"><span data-stu-id="cc40b-102">Provides configuration for the <xref:System.IdentityModel.Services.Tokens.MembershipUserNameSecurityTokenHandler> class or derived classes.</span></span>  
  
<span data-ttu-id="cc40b-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="cc40b-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="cc40b-104">&nbsp;&nbsp;[ **\<System. IdentityModel->** ](system-identitymodel.md)</span><span class="sxs-lookup"><span data-stu-id="cc40b-104">&nbsp;&nbsp;[**\<system.identityModel>**](system-identitymodel.md)</span></span>\
<span data-ttu-id="cc40b-105">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<identityconfiguration->** ](identityconfiguration.md)</span><span class="sxs-lookup"><span data-stu-id="cc40b-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<identityConfiguration>**](identityconfiguration.md)</span></span>\
<span data-ttu-id="cc40b-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<securitytokenhandlers >** ](securitytokenhandlers.md)</span><span class="sxs-lookup"><span data-stu-id="cc40b-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<securityTokenHandlers>**](securitytokenhandlers.md)</span></span>\
<span data-ttu-id="cc40b-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> Hinzufügen**](add.md)</span><span class="sxs-lookup"><span data-stu-id="cc40b-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<add>**](add.md)</span></span>\
<span data-ttu-id="cc40b-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<usernamesecuritytokenhandlerrequirements->**</span><span class="sxs-lookup"><span data-stu-id="cc40b-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<userNameSecurityTokenHandlerRequirement>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cc40b-109">Syntax</span><span class="sxs-lookup"><span data-stu-id="cc40b-109">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="cc40b-110">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="cc40b-110">Attributes and Elements</span></span>  
 <span data-ttu-id="cc40b-111">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="cc40b-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="cc40b-112">Attribute</span><span class="sxs-lookup"><span data-stu-id="cc40b-112">Attributes</span></span>  
  
|<span data-ttu-id="cc40b-113">Attribut</span><span class="sxs-lookup"><span data-stu-id="cc40b-113">Attribute</span></span>|<span data-ttu-id="cc40b-114">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="cc40b-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="cc40b-115">mitgliedshipprovidername</span><span class="sxs-lookup"><span data-stu-id="cc40b-115">membershipProviderName</span></span>|<span data-ttu-id="cc40b-116">Gibt die <xref:System.Web.Security.MembershipProvider> an, die vom Sicherheitstokenhandler verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="cc40b-116">Specifies the <xref:System.Web.Security.MembershipProvider> that should be used by the security token handler.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="cc40b-117">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="cc40b-117">Child Elements</span></span>  
 <span data-ttu-id="cc40b-118">None</span><span class="sxs-lookup"><span data-stu-id="cc40b-118">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="cc40b-119">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="cc40b-119">Parent Elements</span></span>  
  
|<span data-ttu-id="cc40b-120">Element</span><span class="sxs-lookup"><span data-stu-id="cc40b-120">Element</span></span>|<span data-ttu-id="cc40b-121">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="cc40b-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="cc40b-122">\<add></span><span class="sxs-lookup"><span data-stu-id="cc40b-122">\<add></span></span>](add.md)|<span data-ttu-id="cc40b-123">Fügt der tokenhandlerauflistung den angegebenen Sicherheitstokenhandler hinzu.</span><span class="sxs-lookup"><span data-stu-id="cc40b-123">Adds the specified security token handler to the token handler collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="cc40b-124">Hinweise</span><span class="sxs-lookup"><span data-stu-id="cc40b-124">Remarks</span></span>  
 <span data-ttu-id="cc40b-125">Das `<userNameSecurityTokenHandlerRequirement>` -Element legt <xref:System.IdentityModel.Services.Tokens.MembershipUserNameSecurityTokenHandler.MembershipProvider%2A> die-Eigenschaft <xref:System.IdentityModel.Services.Tokens.MembershipUserNameSecurityTokenHandler> fest, wenn ein-Objekt aus der Konfiguration initialisiert wird.</span><span class="sxs-lookup"><span data-stu-id="cc40b-125">The `<userNameSecurityTokenHandlerRequirement>` element sets the <xref:System.IdentityModel.Services.Tokens.MembershipUserNameSecurityTokenHandler.MembershipProvider%2A> property when a <xref:System.IdentityModel.Services.Tokens.MembershipUserNameSecurityTokenHandler> object is initialized from configuration.</span></span>  
  
## <a name="example"></a><span data-ttu-id="cc40b-126">Beispiel</span><span class="sxs-lookup"><span data-stu-id="cc40b-126">Example</span></span>  
  
```xml  
<add type="System.IdentityModel.Services.Tokens.MembershipUserNameSecurityTokenHandler, System.IdentityModel.Services">  
    <userNameSecurityTokenHandlerRequirement membershipProviderName="AspNetSqlProvider/>  
</add>  
```
