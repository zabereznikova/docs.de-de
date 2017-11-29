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
ms.openlocfilehash: 89d42cba78eb9758d8b3491fd1bd3b25ef168f9c
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="ltclaimtyperequiredgt"></a><span data-ttu-id="2f6fe-102">&lt;claimTypeRequired&gt;</span><span class="sxs-lookup"><span data-stu-id="2f6fe-102">&lt;claimTypeRequired&gt;</span></span>
<span data-ttu-id="2f6fe-103">Gibt den Satz von erforderlichen Ansprüchen für eingehende Sicherheitstoken.</span><span class="sxs-lookup"><span data-stu-id="2f6fe-103">Specifies the set of required claims for incoming security tokens.</span></span>  
  
 <span data-ttu-id="2f6fe-104">\<system.identityModel ></span><span class="sxs-lookup"><span data-stu-id="2f6fe-104">\<system.identityModel></span></span>  
<span data-ttu-id="2f6fe-105">\<IdentityConfiguration ></span><span class="sxs-lookup"><span data-stu-id="2f6fe-105">\<identityConfiguration></span></span>  
<span data-ttu-id="2f6fe-106">\<ClaimTypeRequired ></span><span class="sxs-lookup"><span data-stu-id="2f6fe-106">\<claimTypeRequired></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2f6fe-107">Syntax</span><span class="sxs-lookup"><span data-stu-id="2f6fe-107">Syntax</span></span>  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <claimTypeRequired>  
    </claimTypeRequired>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="2f6fe-108">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="2f6fe-108">Attributes and Elements</span></span>  
 <span data-ttu-id="2f6fe-109">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="2f6fe-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="2f6fe-110">Attribute</span><span class="sxs-lookup"><span data-stu-id="2f6fe-110">Attributes</span></span>  
 <span data-ttu-id="2f6fe-111">Keine</span><span class="sxs-lookup"><span data-stu-id="2f6fe-111">None</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="2f6fe-112">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="2f6fe-112">Child Elements</span></span>  
  
|<span data-ttu-id="2f6fe-113">Element</span><span class="sxs-lookup"><span data-stu-id="2f6fe-113">Element</span></span>|<span data-ttu-id="2f6fe-114">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="2f6fe-114">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="2f6fe-115">\<ClaimType ></span><span class="sxs-lookup"><span data-stu-id="2f6fe-115">\<claimType></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/claimtype.md)|<span data-ttu-id="2f6fe-116">Gibt einen einzelnen Anspruch aus erforderliche oder optionale für eingehende Sicherheitstoken an.</span><span class="sxs-lookup"><span data-stu-id="2f6fe-116">Specifies a single optional or required claim for incoming security tokens.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="2f6fe-117">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="2f6fe-117">Parent Elements</span></span>  
  
|<span data-ttu-id="2f6fe-118">Element</span><span class="sxs-lookup"><span data-stu-id="2f6fe-118">Element</span></span>|<span data-ttu-id="2f6fe-119">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="2f6fe-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="2f6fe-120">\<IdentityConfiguration ></span><span class="sxs-lookup"><span data-stu-id="2f6fe-120">\<identityConfiguration></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md)|<span data-ttu-id="2f6fe-121">Gibt an, Service Level identitätseinstellungen.</span><span class="sxs-lookup"><span data-stu-id="2f6fe-121">Specifies service-level identity settings.</span></span>|
