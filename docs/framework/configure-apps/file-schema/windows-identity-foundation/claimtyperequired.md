---
title: <claimTypeRequired>
ms.date: 03/30/2017
ms.assetid: c469d71f-6c77-4a24-97aa-53efa126ceef
author: BrucePerlerMS
ms.openlocfilehash: 1c40c5e4b4a24a3c1bbd6e096f12b7b044331c88
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/06/2020
ms.locfileid: "70252049"
---
# \<claimTypeRequired>
<span data-ttu-id="bbb0a-101">Gibt den Satz erforderlicher Ansprüche für eingehende Sicherheits Token an.</span><span class="sxs-lookup"><span data-stu-id="bbb0a-101">Specifies the set of required claims for incoming security tokens.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.identityModel>**](system-identitymodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<identityConfiguration>**](identityconfiguration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<claimTypeRequired>**  
  
## <a name="syntax"></a><span data-ttu-id="bbb0a-102">Syntax</span><span class="sxs-lookup"><span data-stu-id="bbb0a-102">Syntax</span></span>  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <claimTypeRequired>  
    </claimTypeRequired>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="bbb0a-103">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="bbb0a-103">Attributes and Elements</span></span>  
 <span data-ttu-id="bbb0a-104">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="bbb0a-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="bbb0a-105">Attribute</span><span class="sxs-lookup"><span data-stu-id="bbb0a-105">Attributes</span></span>  
 <span data-ttu-id="bbb0a-106">Keine</span><span class="sxs-lookup"><span data-stu-id="bbb0a-106">None</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="bbb0a-107">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="bbb0a-107">Child Elements</span></span>  
  
|<span data-ttu-id="bbb0a-108">Element</span><span class="sxs-lookup"><span data-stu-id="bbb0a-108">Element</span></span>|<span data-ttu-id="bbb0a-109">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="bbb0a-109">Description</span></span>|  
|-------------|-----------------|  
|[\<claimType>](claimtype.md)|<span data-ttu-id="bbb0a-110">Gibt einen einzelnen optionalen oder erforderlichen Anspruch für eingehende Sicherheits Token an.</span><span class="sxs-lookup"><span data-stu-id="bbb0a-110">Specifies a single optional or required claim for incoming security tokens.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="bbb0a-111">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="bbb0a-111">Parent Elements</span></span>  
  
|<span data-ttu-id="bbb0a-112">Element</span><span class="sxs-lookup"><span data-stu-id="bbb0a-112">Element</span></span>|<span data-ttu-id="bbb0a-113">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="bbb0a-113">Description</span></span>|  
|-------------|-----------------|  
|[\<identityConfiguration>](identityconfiguration.md)|<span data-ttu-id="bbb0a-114">Gibt Identitäts Einstellungen auf Dienst Ebene an.</span><span class="sxs-lookup"><span data-stu-id="bbb0a-114">Specifies service-level identity settings.</span></span>|
