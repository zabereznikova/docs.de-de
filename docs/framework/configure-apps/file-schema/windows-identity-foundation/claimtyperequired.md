---
title: '&lt;claimTypeRequired&gt;'
ms.date: 03/30/2017
ms.assetid: c469d71f-6c77-4a24-97aa-53efa126ceef
author: BrucePerlerMS
manager: mbaldwin
ms.openlocfilehash: 6fb600aac46b3ee5cb54fa904d35ac7b7ed90719
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
---
# <a name="ltclaimtyperequiredgt"></a><span data-ttu-id="0f349-102">&lt;claimTypeRequired&gt;</span><span class="sxs-lookup"><span data-stu-id="0f349-102">&lt;claimTypeRequired&gt;</span></span>
<span data-ttu-id="0f349-103">Gibt den Satz von erforderlichen Ansprüchen für eingehende Sicherheitstoken.</span><span class="sxs-lookup"><span data-stu-id="0f349-103">Specifies the set of required claims for incoming security tokens.</span></span>  
  
 <span data-ttu-id="0f349-104">\<system.identityModel></span><span class="sxs-lookup"><span data-stu-id="0f349-104">\<system.identityModel></span></span>  
<span data-ttu-id="0f349-105">\<identityConfiguration></span><span class="sxs-lookup"><span data-stu-id="0f349-105">\<identityConfiguration></span></span>  
<span data-ttu-id="0f349-106">\<ClaimTypeRequired ></span><span class="sxs-lookup"><span data-stu-id="0f349-106">\<claimTypeRequired></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0f349-107">Syntax</span><span class="sxs-lookup"><span data-stu-id="0f349-107">Syntax</span></span>  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <claimTypeRequired>  
    </claimTypeRequired>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="0f349-108">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="0f349-108">Attributes and Elements</span></span>  
 <span data-ttu-id="0f349-109">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="0f349-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="0f349-110">Attribute</span><span class="sxs-lookup"><span data-stu-id="0f349-110">Attributes</span></span>  
 <span data-ttu-id="0f349-111">Keiner</span><span class="sxs-lookup"><span data-stu-id="0f349-111">None</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="0f349-112">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="0f349-112">Child Elements</span></span>  
  
|<span data-ttu-id="0f349-113">Element</span><span class="sxs-lookup"><span data-stu-id="0f349-113">Element</span></span>|<span data-ttu-id="0f349-114">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="0f349-114">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="0f349-115">\<ClaimType ></span><span class="sxs-lookup"><span data-stu-id="0f349-115">\<claimType></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/claimtype.md)|<span data-ttu-id="0f349-116">Gibt einen einzelnen Anspruch aus erforderliche oder optionale für eingehende Sicherheitstoken an.</span><span class="sxs-lookup"><span data-stu-id="0f349-116">Specifies a single optional or required claim for incoming security tokens.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="0f349-117">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="0f349-117">Parent Elements</span></span>  
  
|<span data-ttu-id="0f349-118">Element</span><span class="sxs-lookup"><span data-stu-id="0f349-118">Element</span></span>|<span data-ttu-id="0f349-119">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="0f349-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="0f349-120">\<IdentityConfiguration ></span><span class="sxs-lookup"><span data-stu-id="0f349-120">\<identityConfiguration></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md)|<span data-ttu-id="0f349-121">Gibt an, Service Level identitätseinstellungen.</span><span class="sxs-lookup"><span data-stu-id="0f349-121">Specifies service-level identity settings.</span></span>|
