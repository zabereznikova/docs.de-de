---
title: <clear>
ms.date: 03/30/2017
ms.assetid: 54dcd1d1-038f-4fc8-a3a4-56ba7a1ca0fd
author: BrucePerlerMS
ms.openlocfilehash: e96349c72fc4a952e3dc7efeea5f69ebaa1fd0ad
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/04/2019
ms.locfileid: "70252043"
---
# <a name="clear"></a><span data-ttu-id="edead-101">\<clear></span><span class="sxs-lookup"><span data-stu-id="edead-101">\<clear></span></span>
<span data-ttu-id="edead-102">Löscht alle Sicherheitstokenhandler aus der aktuellen Auflistung von tokenhandlern.</span><span class="sxs-lookup"><span data-stu-id="edead-102">Clears all security token handlers from the current token handler collection.</span></span>  
  
<span data-ttu-id="edead-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="edead-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="edead-104">&nbsp;&nbsp;[ **\<System. IdentityModel->** ](system-identitymodel.md)</span><span class="sxs-lookup"><span data-stu-id="edead-104">&nbsp;&nbsp;[**\<system.identityModel>**](system-identitymodel.md)</span></span>\
<span data-ttu-id="edead-105">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<identityconfiguration->** ](identityconfiguration.md)</span><span class="sxs-lookup"><span data-stu-id="edead-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<identityConfiguration>**](identityconfiguration.md)</span></span>\
<span data-ttu-id="edead-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<securitytokenhandlers >** ](securitytokenhandlers.md)</span><span class="sxs-lookup"><span data-stu-id="edead-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<securityTokenHandlers>**](securitytokenhandlers.md)</span></span>\
<span data-ttu-id="edead-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<Löschen >**</span><span class="sxs-lookup"><span data-stu-id="edead-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<clear>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="edead-108">Syntax</span><span class="sxs-lookup"><span data-stu-id="edead-108">Syntax</span></span>  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <securityTokenHandlers>  
      <clear>  
      </clear>  
    </securityTokenHandlers>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="edead-109">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="edead-109">Attributes and Elements</span></span>  
 <span data-ttu-id="edead-110">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="edead-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="edead-111">Attribute</span><span class="sxs-lookup"><span data-stu-id="edead-111">Attributes</span></span>  
 <span data-ttu-id="edead-112">None</span><span class="sxs-lookup"><span data-stu-id="edead-112">None</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="edead-113">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="edead-113">Child Elements</span></span>  
 <span data-ttu-id="edead-114">None</span><span class="sxs-lookup"><span data-stu-id="edead-114">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="edead-115">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="edead-115">Parent Elements</span></span>  
  
|<span data-ttu-id="edead-116">Element</span><span class="sxs-lookup"><span data-stu-id="edead-116">Element</span></span>|<span data-ttu-id="edead-117">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="edead-117">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="edead-118">\<securityTokenHandlers></span><span class="sxs-lookup"><span data-stu-id="edead-118">\<securityTokenHandlers></span></span>](securitytokenhandlers.md)|<span data-ttu-id="edead-119">Gibt eine Auflistung von Sicherheitstokenhandlern an, die beim Endpunkt registriert sind.</span><span class="sxs-lookup"><span data-stu-id="edead-119">Specifies a collection of security token handlers that are registered with the endpoint.</span></span>|
