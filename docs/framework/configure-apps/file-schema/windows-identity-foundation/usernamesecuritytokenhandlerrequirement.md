---
title: <userNameSecurityTokenHandlerRequirement>
ms.date: 03/30/2017
ms.assetid: 6ec3bac1-b014-49ae-843c-c54518cb709a
author: BrucePerlerMS
ms.openlocfilehash: 5863c01e97e7f5fb6fe07c43174c0d6cb7a0a25d
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/06/2020
ms.locfileid: "70251747"
---
# \<userNameSecurityTokenHandlerRequirement>
<span data-ttu-id="b399a-101">Stellt die Konfiguration für die- <xref:System.IdentityModel.Services.Tokens.MembershipUserNameSecurityTokenHandler> Klasse oder abgeleitete Klassen bereit.</span><span class="sxs-lookup"><span data-stu-id="b399a-101">Provides configuration for the <xref:System.IdentityModel.Services.Tokens.MembershipUserNameSecurityTokenHandler> class or derived classes.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.identityModel>**](system-identitymodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<identityConfiguration>**](identityconfiguration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<securityTokenHandlers>**](securitytokenhandlers.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<add>**](add.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<userNameSecurityTokenHandlerRequirement>**  
  
## <a name="syntax"></a><span data-ttu-id="b399a-102">Syntax</span><span class="sxs-lookup"><span data-stu-id="b399a-102">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="b399a-103">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="b399a-103">Attributes and Elements</span></span>  
 <span data-ttu-id="b399a-104">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="b399a-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="b399a-105">Attribute</span><span class="sxs-lookup"><span data-stu-id="b399a-105">Attributes</span></span>  
  
|<span data-ttu-id="b399a-106">attribute</span><span class="sxs-lookup"><span data-stu-id="b399a-106">Attribute</span></span>|<span data-ttu-id="b399a-107">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="b399a-107">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="b399a-108">mitgliedshipprovidername</span><span class="sxs-lookup"><span data-stu-id="b399a-108">membershipProviderName</span></span>|<span data-ttu-id="b399a-109">Gibt die <xref:System.Web.Security.MembershipProvider> an, die vom Sicherheitstokenhandler verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="b399a-109">Specifies the <xref:System.Web.Security.MembershipProvider> that should be used by the security token handler.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="b399a-110">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="b399a-110">Child Elements</span></span>  
 <span data-ttu-id="b399a-111">Keine</span><span class="sxs-lookup"><span data-stu-id="b399a-111">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="b399a-112">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="b399a-112">Parent Elements</span></span>  
  
|<span data-ttu-id="b399a-113">Element</span><span class="sxs-lookup"><span data-stu-id="b399a-113">Element</span></span>|<span data-ttu-id="b399a-114">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="b399a-114">Description</span></span>|  
|-------------|-----------------|  
|[\<add>](add.md)|<span data-ttu-id="b399a-115">Fügt der tokenhandlerauflistung den angegebenen Sicherheitstokenhandler hinzu.</span><span class="sxs-lookup"><span data-stu-id="b399a-115">Adds the specified security token handler to the token handler collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b399a-116">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="b399a-116">Remarks</span></span>  
 <span data-ttu-id="b399a-117">Das- `<userNameSecurityTokenHandlerRequirement>` Element legt die-Eigenschaft fest, <xref:System.IdentityModel.Services.Tokens.MembershipUserNameSecurityTokenHandler.MembershipProvider%2A> Wenn ein- <xref:System.IdentityModel.Services.Tokens.MembershipUserNameSecurityTokenHandler> Objekt aus der Konfiguration initialisiert wird.</span><span class="sxs-lookup"><span data-stu-id="b399a-117">The `<userNameSecurityTokenHandlerRequirement>` element sets the <xref:System.IdentityModel.Services.Tokens.MembershipUserNameSecurityTokenHandler.MembershipProvider%2A> property when a <xref:System.IdentityModel.Services.Tokens.MembershipUserNameSecurityTokenHandler> object is initialized from configuration.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b399a-118">Beispiel</span><span class="sxs-lookup"><span data-stu-id="b399a-118">Example</span></span>  
  
```xml  
<add type="System.IdentityModel.Services.Tokens.MembershipUserNameSecurityTokenHandler, System.IdentityModel.Services">  
    <userNameSecurityTokenHandlerRequirement membershipProviderName="AspNetSqlProvider/>  
</add>  
```
