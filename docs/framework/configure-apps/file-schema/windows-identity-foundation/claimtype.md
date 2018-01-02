---
title: '&lt;claimType&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: d17b5831-9a2c-45c4-b0d1-68f48e72e861
caps.latest.revision: "4"
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.workload: dotnet
ms.openlocfilehash: ae572ff3a8a2335a4259bdce2af5f6922fb0596f
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="ltclaimtypegt"></a><span data-ttu-id="103b7-102">&lt;claimType&gt;</span><span class="sxs-lookup"><span data-stu-id="103b7-102">&lt;claimType&gt;</span></span>
<span data-ttu-id="103b7-103">Gibt einen einzelnen Anspruch aus erforderliche oder optionale für eingehende Sicherheitstoken an.</span><span class="sxs-lookup"><span data-stu-id="103b7-103">Specifies a single optional or required claim for incoming security tokens.</span></span>  
  
 <span data-ttu-id="103b7-104">\<system.identityModel ></span><span class="sxs-lookup"><span data-stu-id="103b7-104">\<system.identityModel></span></span>  
<span data-ttu-id="103b7-105">\<IdentityConfiguration ></span><span class="sxs-lookup"><span data-stu-id="103b7-105">\<identityConfiguration></span></span>  
<span data-ttu-id="103b7-106">\<ClaimTypeRequired ></span><span class="sxs-lookup"><span data-stu-id="103b7-106">\<claimTypeRequired></span></span>  
<span data-ttu-id="103b7-107">\<ClaimType ></span><span class="sxs-lookup"><span data-stu-id="103b7-107">\<claimType></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="103b7-108">Syntax</span><span class="sxs-lookup"><span data-stu-id="103b7-108">Syntax</span></span>  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <claimTypeRequired>  
      <claimType type=URI optional=xs:boolean >  
      </claimType>  
    </claimTypeRequired>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="103b7-109">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="103b7-109">Attributes and Elements</span></span>  
 <span data-ttu-id="103b7-110">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="103b7-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="103b7-111">Attribute</span><span class="sxs-lookup"><span data-stu-id="103b7-111">Attributes</span></span>  
  
|<span data-ttu-id="103b7-112">Attribut</span><span class="sxs-lookup"><span data-stu-id="103b7-112">Attribute</span></span>|<span data-ttu-id="103b7-113">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="103b7-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="103b7-114">Typ</span><span class="sxs-lookup"><span data-stu-id="103b7-114">type</span></span>|<span data-ttu-id="103b7-115">Der Anspruchstyp.</span><span class="sxs-lookup"><span data-stu-id="103b7-115">The claim type.</span></span> <span data-ttu-id="103b7-116">In der Regel ein URI.</span><span class="sxs-lookup"><span data-stu-id="103b7-116">Typically a URI.</span></span> <span data-ttu-id="103b7-117">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="103b7-117">Required.</span></span>|  
|<span data-ttu-id="103b7-118">Optional</span><span class="sxs-lookup"><span data-stu-id="103b7-118">optional</span></span>|<span data-ttu-id="103b7-119">Ein boolescher Wert, der angibt, ob der Typ des Anspruchs optional ist.</span><span class="sxs-lookup"><span data-stu-id="103b7-119">A boolean value that specifies whether the claim type is optional.</span></span> <span data-ttu-id="103b7-120">Dies ist optional.</span><span class="sxs-lookup"><span data-stu-id="103b7-120">Optional.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="103b7-121">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="103b7-121">Child Elements</span></span>  
 <span data-ttu-id="103b7-122">Keiner</span><span class="sxs-lookup"><span data-stu-id="103b7-122">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="103b7-123">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="103b7-123">Parent Elements</span></span>  
  
|<span data-ttu-id="103b7-124">Element</span><span class="sxs-lookup"><span data-stu-id="103b7-124">Element</span></span>|<span data-ttu-id="103b7-125">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="103b7-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="103b7-126">\<ClaimTypeRequired ></span><span class="sxs-lookup"><span data-stu-id="103b7-126">\<claimTypeRequired></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/claimtyperequired.md)|<span data-ttu-id="103b7-127">Gibt den Satz von erforderlichen Ansprüchen für eingehende Sicherheitstoken.</span><span class="sxs-lookup"><span data-stu-id="103b7-127">Specifies the set of required claims for incoming security tokens.</span></span>|
