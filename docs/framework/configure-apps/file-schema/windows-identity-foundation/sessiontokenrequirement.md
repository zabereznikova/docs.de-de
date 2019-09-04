---
title: <sessionTokenRequirement>
ms.date: 03/30/2017
ms.assetid: 496a1735-cbb7-49d5-a6aa-dd5550462073
author: BrucePerlerMS
ms.openlocfilehash: 968c48df9e92a1dfbfb6e248b06cf4f97cece8b4
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/04/2019
ms.locfileid: "70251817"
---
# <a name="sessiontokenrequirement"></a><span data-ttu-id="143ca-101">\<sessionTokenRequirement></span><span class="sxs-lookup"><span data-stu-id="143ca-101">\<sessionTokenRequirement></span></span>
<span data-ttu-id="143ca-102">Stellt die Konfiguration für <xref:System.IdentityModel.Tokens.SessionSecurityTokenHandler> die-Klasse oder abgeleitete Klassen bereit.</span><span class="sxs-lookup"><span data-stu-id="143ca-102">Provides configuration for the <xref:System.IdentityModel.Tokens.SessionSecurityTokenHandler> class or derived classes.</span></span>  
  
<span data-ttu-id="143ca-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="143ca-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="143ca-104">&nbsp;&nbsp;[ **\<System. IdentityModel->** ](system-identitymodel.md)</span><span class="sxs-lookup"><span data-stu-id="143ca-104">&nbsp;&nbsp;[**\<system.identityModel>**](system-identitymodel.md)</span></span>\
<span data-ttu-id="143ca-105">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<identityconfiguration->** ](identityconfiguration.md)</span><span class="sxs-lookup"><span data-stu-id="143ca-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<identityConfiguration>**](identityconfiguration.md)</span></span>\
<span data-ttu-id="143ca-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<securitytokenhandlers >** ](securitytokenhandlers.md)</span><span class="sxs-lookup"><span data-stu-id="143ca-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<securityTokenHandlers>**](securitytokenhandlers.md)</span></span>\
<span data-ttu-id="143ca-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> Hinzufügen**](add.md)</span><span class="sxs-lookup"><span data-stu-id="143ca-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<add>**](add.md)</span></span>\
<span data-ttu-id="143ca-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<sessiontokenrequirements->**</span><span class="sxs-lookup"><span data-stu-id="143ca-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<sessionTokenRequirement>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="143ca-109">Syntax</span><span class="sxs-lookup"><span data-stu-id="143ca-109">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="143ca-110">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="143ca-110">Attributes and Elements</span></span>  
 <span data-ttu-id="143ca-111">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="143ca-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="143ca-112">Attribute</span><span class="sxs-lookup"><span data-stu-id="143ca-112">Attributes</span></span>  
  
|<span data-ttu-id="143ca-113">Attribut</span><span class="sxs-lookup"><span data-stu-id="143ca-113">Attribute</span></span>|<span data-ttu-id="143ca-114">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="143ca-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="143ca-115">Lebensdauer</span><span class="sxs-lookup"><span data-stu-id="143ca-115">lifetime</span></span>|<span data-ttu-id="143ca-116">Gibt die Lebensdauer von Sitzungs Token an.</span><span class="sxs-lookup"><span data-stu-id="143ca-116">Specifies the lifetime of session tokens.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="143ca-117">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="143ca-117">Child Elements</span></span>  
 <span data-ttu-id="143ca-118">None</span><span class="sxs-lookup"><span data-stu-id="143ca-118">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="143ca-119">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="143ca-119">Parent Elements</span></span>  
  
|<span data-ttu-id="143ca-120">Element</span><span class="sxs-lookup"><span data-stu-id="143ca-120">Element</span></span>|<span data-ttu-id="143ca-121">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="143ca-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="143ca-122">\<add></span><span class="sxs-lookup"><span data-stu-id="143ca-122">\<add></span></span>](add.md)|<span data-ttu-id="143ca-123">Fügt der tokenhandlerauflistung den angegebenen Sicherheitstokenhandler hinzu.</span><span class="sxs-lookup"><span data-stu-id="143ca-123">Adds the specified security token handler to the token handler collection.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="143ca-124">Beispiel</span><span class="sxs-lookup"><span data-stu-id="143ca-124">Example</span></span>  
  
```xml  
<add type="System.IdentityModel.Tokens.SessionSecurityTokenHandler, System.IdentityModel">           
    <sessionTokenRequirement lifetime="10:00" />  
</add>  
```
