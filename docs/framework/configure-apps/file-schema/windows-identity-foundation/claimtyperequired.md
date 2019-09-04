---
title: <claimTypeRequired>
ms.date: 03/30/2017
ms.assetid: c469d71f-6c77-4a24-97aa-53efa126ceef
author: BrucePerlerMS
ms.openlocfilehash: 1c40c5e4b4a24a3c1bbd6e096f12b7b044331c88
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/04/2019
ms.locfileid: "70252049"
---
# <a name="claimtyperequired"></a><span data-ttu-id="b6d66-101">\<claimTypeRequired></span><span class="sxs-lookup"><span data-stu-id="b6d66-101">\<claimTypeRequired></span></span>
<span data-ttu-id="b6d66-102">Gibt den Satz erforderlicher Ansprüche für eingehende Sicherheits Token an.</span><span class="sxs-lookup"><span data-stu-id="b6d66-102">Specifies the set of required claims for incoming security tokens.</span></span>  
  
<span data-ttu-id="b6d66-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="b6d66-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="b6d66-104">&nbsp;&nbsp;[ **\<System. IdentityModel->** ](system-identitymodel.md)</span><span class="sxs-lookup"><span data-stu-id="b6d66-104">&nbsp;&nbsp;[**\<system.identityModel>**](system-identitymodel.md)</span></span>\
<span data-ttu-id="b6d66-105">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<identityconfiguration->** ](identityconfiguration.md)</span><span class="sxs-lookup"><span data-stu-id="b6d66-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<identityConfiguration>**](identityconfiguration.md)</span></span>\
<span data-ttu-id="b6d66-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<claimtyperequired->**</span><span class="sxs-lookup"><span data-stu-id="b6d66-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<claimTypeRequired>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b6d66-107">Syntax</span><span class="sxs-lookup"><span data-stu-id="b6d66-107">Syntax</span></span>  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <claimTypeRequired>  
    </claimTypeRequired>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="b6d66-108">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="b6d66-108">Attributes and Elements</span></span>  
 <span data-ttu-id="b6d66-109">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="b6d66-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="b6d66-110">Attribute</span><span class="sxs-lookup"><span data-stu-id="b6d66-110">Attributes</span></span>  
 <span data-ttu-id="b6d66-111">None</span><span class="sxs-lookup"><span data-stu-id="b6d66-111">None</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="b6d66-112">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="b6d66-112">Child Elements</span></span>  
  
|<span data-ttu-id="b6d66-113">Element</span><span class="sxs-lookup"><span data-stu-id="b6d66-113">Element</span></span>|<span data-ttu-id="b6d66-114">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="b6d66-114">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="b6d66-115">\<claimType></span><span class="sxs-lookup"><span data-stu-id="b6d66-115">\<claimType></span></span>](claimtype.md)|<span data-ttu-id="b6d66-116">Gibt einen einzelnen optionalen oder erforderlichen Anspruch für eingehende Sicherheits Token an.</span><span class="sxs-lookup"><span data-stu-id="b6d66-116">Specifies a single optional or required claim for incoming security tokens.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="b6d66-117">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="b6d66-117">Parent Elements</span></span>  
  
|<span data-ttu-id="b6d66-118">Element</span><span class="sxs-lookup"><span data-stu-id="b6d66-118">Element</span></span>|<span data-ttu-id="b6d66-119">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="b6d66-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="b6d66-120">\<identityConfiguration></span><span class="sxs-lookup"><span data-stu-id="b6d66-120">\<identityConfiguration></span></span>](identityconfiguration.md)|<span data-ttu-id="b6d66-121">Gibt Identitäts Einstellungen auf Dienst Ebene an.</span><span class="sxs-lookup"><span data-stu-id="b6d66-121">Specifies service-level identity settings.</span></span>|
