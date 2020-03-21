---
title: <sessionTokenRequirement>
ms.date: 03/30/2017
ms.assetid: 496a1735-cbb7-49d5-a6aa-dd5550462073
author: BrucePerlerMS
ms.openlocfilehash: ade55a5b26826633faf2e7ef7598a4071d613bbc
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79152540"
---
# <a name="sessiontokenrequirement"></a><span data-ttu-id="055a9-101">\<sessionTokenRequirement></span><span class="sxs-lookup"><span data-stu-id="055a9-101">\<sessionTokenRequirement></span></span>
<span data-ttu-id="055a9-102">Stellt die <xref:System.IdentityModel.Tokens.SessionSecurityTokenHandler> Konfiguration für die Klasse oder abgeleitete Klassen bereit.</span><span class="sxs-lookup"><span data-stu-id="055a9-102">Provides configuration for the <xref:System.IdentityModel.Tokens.SessionSecurityTokenHandler> class or derived classes.</span></span>  
  
<span data-ttu-id="055a9-103">[**\<Konfiguration>**](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="055a9-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="055a9-104">&nbsp;&nbsp;[**\<system.identityModel>**](system-identitymodel.md)</span><span class="sxs-lookup"><span data-stu-id="055a9-104">&nbsp;&nbsp;[**\<system.identityModel>**](system-identitymodel.md)</span></span>\
<span data-ttu-id="055a9-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<identityConfiguration>**](identityconfiguration.md)</span><span class="sxs-lookup"><span data-stu-id="055a9-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<identityConfiguration>**](identityconfiguration.md)</span></span>\
<span data-ttu-id="055a9-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<securityTokenHandlers>**](securitytokenhandlers.md)</span><span class="sxs-lookup"><span data-stu-id="055a9-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<securityTokenHandlers>**](securitytokenhandlers.md)</span></span>\
<span data-ttu-id="055a9-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<hinzufügen>**](add.md)</span><span class="sxs-lookup"><span data-stu-id="055a9-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<add>**](add.md)</span></span>\
<span data-ttu-id="055a9-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<sessionTokenRequirement>**</span><span class="sxs-lookup"><span data-stu-id="055a9-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<sessionTokenRequirement>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="055a9-109">Syntax</span><span class="sxs-lookup"><span data-stu-id="055a9-109">Syntax</span></span>  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <securityTokenHandlers>  
      <add type="System.IdentityModel.Tokens.SessionSecurityTokenHandler, System.IdentityModel">  
        <sessionTokenRequirement lifetime=TimeSpan >  
        </sessionTokenRequirement>  
      </add>  
    </securityTokenHandlers>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="055a9-110">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="055a9-110">Attributes and Elements</span></span>  
 <span data-ttu-id="055a9-111">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="055a9-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="055a9-112">Attributes</span><span class="sxs-lookup"><span data-stu-id="055a9-112">Attributes</span></span>  
  
|<span data-ttu-id="055a9-113">attribute</span><span class="sxs-lookup"><span data-stu-id="055a9-113">Attribute</span></span>|<span data-ttu-id="055a9-114">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="055a9-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="055a9-115">lifetime</span><span class="sxs-lookup"><span data-stu-id="055a9-115">lifetime</span></span>|<span data-ttu-id="055a9-116">Gibt die Lebensdauer von Sitzungstoken an.</span><span class="sxs-lookup"><span data-stu-id="055a9-116">Specifies the lifetime of session tokens.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="055a9-117">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="055a9-117">Child Elements</span></span>  
 <span data-ttu-id="055a9-118">Keine</span><span class="sxs-lookup"><span data-stu-id="055a9-118">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="055a9-119">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="055a9-119">Parent Elements</span></span>  
  
|<span data-ttu-id="055a9-120">Element</span><span class="sxs-lookup"><span data-stu-id="055a9-120">Element</span></span>|<span data-ttu-id="055a9-121">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="055a9-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="055a9-122">\<hinzufügen></span><span class="sxs-lookup"><span data-stu-id="055a9-122">\<add></span></span>](add.md)|<span data-ttu-id="055a9-123">Fügt der Tokenhandlerauflistung den angegebenen Sicherheitstokenhandler hinzu.</span><span class="sxs-lookup"><span data-stu-id="055a9-123">Adds the specified security token handler to the token handler collection.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="055a9-124">Beispiel</span><span class="sxs-lookup"><span data-stu-id="055a9-124">Example</span></span>  
  
```xml  
<add type="System.IdentityModel.Tokens.SessionSecurityTokenHandler, System.IdentityModel">
    <sessionTokenRequirement lifetime="10:00" />  
</add>  
```
