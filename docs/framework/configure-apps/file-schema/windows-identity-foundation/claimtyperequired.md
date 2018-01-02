---
title: '&lt;claimTypeRequired&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c469d71f-6c77-4a24-97aa-53efa126ceef
caps.latest.revision: "5"
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.workload: dotnet
ms.openlocfilehash: 491277e39b29d7c3e0a0d69ec8745b2c6718a91e
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="ltclaimtyperequiredgt"></a><span data-ttu-id="24f3c-102">&lt;claimTypeRequired&gt;</span><span class="sxs-lookup"><span data-stu-id="24f3c-102">&lt;claimTypeRequired&gt;</span></span>
<span data-ttu-id="24f3c-103">Gibt den Satz von erforderlichen Ansprüchen für eingehende Sicherheitstoken.</span><span class="sxs-lookup"><span data-stu-id="24f3c-103">Specifies the set of required claims for incoming security tokens.</span></span>  
  
 <span data-ttu-id="24f3c-104">\<system.identityModel ></span><span class="sxs-lookup"><span data-stu-id="24f3c-104">\<system.identityModel></span></span>  
<span data-ttu-id="24f3c-105">\<IdentityConfiguration ></span><span class="sxs-lookup"><span data-stu-id="24f3c-105">\<identityConfiguration></span></span>  
<span data-ttu-id="24f3c-106">\<ClaimTypeRequired ></span><span class="sxs-lookup"><span data-stu-id="24f3c-106">\<claimTypeRequired></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="24f3c-107">Syntax</span><span class="sxs-lookup"><span data-stu-id="24f3c-107">Syntax</span></span>  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <claimTypeRequired>  
    </claimTypeRequired>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="24f3c-108">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="24f3c-108">Attributes and Elements</span></span>  
 <span data-ttu-id="24f3c-109">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="24f3c-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="24f3c-110">Attribute</span><span class="sxs-lookup"><span data-stu-id="24f3c-110">Attributes</span></span>  
 <span data-ttu-id="24f3c-111">Keiner</span><span class="sxs-lookup"><span data-stu-id="24f3c-111">None</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="24f3c-112">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="24f3c-112">Child Elements</span></span>  
  
|<span data-ttu-id="24f3c-113">Element</span><span class="sxs-lookup"><span data-stu-id="24f3c-113">Element</span></span>|<span data-ttu-id="24f3c-114">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="24f3c-114">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="24f3c-115">\<ClaimType ></span><span class="sxs-lookup"><span data-stu-id="24f3c-115">\<claimType></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/claimtype.md)|<span data-ttu-id="24f3c-116">Gibt einen einzelnen Anspruch aus erforderliche oder optionale für eingehende Sicherheitstoken an.</span><span class="sxs-lookup"><span data-stu-id="24f3c-116">Specifies a single optional or required claim for incoming security tokens.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="24f3c-117">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="24f3c-117">Parent Elements</span></span>  
  
|<span data-ttu-id="24f3c-118">Element</span><span class="sxs-lookup"><span data-stu-id="24f3c-118">Element</span></span>|<span data-ttu-id="24f3c-119">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="24f3c-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="24f3c-120">\<IdentityConfiguration ></span><span class="sxs-lookup"><span data-stu-id="24f3c-120">\<identityConfiguration></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md)|<span data-ttu-id="24f3c-121">Gibt an, Service Level identitätseinstellungen.</span><span class="sxs-lookup"><span data-stu-id="24f3c-121">Specifies service-level identity settings.</span></span>|
