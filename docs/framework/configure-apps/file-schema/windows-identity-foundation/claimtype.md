---
title: '&lt;ClaimType&gt;'
ms.date: 03/30/2017
ms.assetid: d17b5831-9a2c-45c4-b0d1-68f48e72e861
author: BrucePerlerMS
manager: mbaldwin
ms.openlocfilehash: 94f8586a9ca63b8c1f1128cdda4a74ccfe0f5416
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
ms.locfileid: "32767426"
---
# <a name="ltclaimtypegt"></a><span data-ttu-id="9185d-102">&lt;ClaimType&gt;</span><span class="sxs-lookup"><span data-stu-id="9185d-102">&lt;claimType&gt;</span></span>
<span data-ttu-id="9185d-103">Gibt einen einzelnen Anspruch aus erforderliche oder optionale für eingehende Sicherheitstoken an.</span><span class="sxs-lookup"><span data-stu-id="9185d-103">Specifies a single optional or required claim for incoming security tokens.</span></span>  
  
 <span data-ttu-id="9185d-104">\<system.identityModel></span><span class="sxs-lookup"><span data-stu-id="9185d-104">\<system.identityModel></span></span>  
<span data-ttu-id="9185d-105">\<identityConfiguration></span><span class="sxs-lookup"><span data-stu-id="9185d-105">\<identityConfiguration></span></span>  
<span data-ttu-id="9185d-106">\<ClaimTypeRequired ></span><span class="sxs-lookup"><span data-stu-id="9185d-106">\<claimTypeRequired></span></span>  
<span data-ttu-id="9185d-107">\<ClaimType ></span><span class="sxs-lookup"><span data-stu-id="9185d-107">\<claimType></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9185d-108">Syntax</span><span class="sxs-lookup"><span data-stu-id="9185d-108">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="9185d-109">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="9185d-109">Attributes and Elements</span></span>  
 <span data-ttu-id="9185d-110">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="9185d-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="9185d-111">Attribute</span><span class="sxs-lookup"><span data-stu-id="9185d-111">Attributes</span></span>  
  
|<span data-ttu-id="9185d-112">Attribut</span><span class="sxs-lookup"><span data-stu-id="9185d-112">Attribute</span></span>|<span data-ttu-id="9185d-113">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="9185d-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="9185d-114">Typ</span><span class="sxs-lookup"><span data-stu-id="9185d-114">type</span></span>|<span data-ttu-id="9185d-115">Der Anspruchstyp.</span><span class="sxs-lookup"><span data-stu-id="9185d-115">The claim type.</span></span> <span data-ttu-id="9185d-116">In der Regel ein URI.</span><span class="sxs-lookup"><span data-stu-id="9185d-116">Typically a URI.</span></span> <span data-ttu-id="9185d-117">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="9185d-117">Required.</span></span>|  
|<span data-ttu-id="9185d-118">Optional</span><span class="sxs-lookup"><span data-stu-id="9185d-118">optional</span></span>|<span data-ttu-id="9185d-119">Ein boolescher Wert, der angibt, ob der Typ des Anspruchs optional ist.</span><span class="sxs-lookup"><span data-stu-id="9185d-119">A boolean value that specifies whether the claim type is optional.</span></span> <span data-ttu-id="9185d-120">Dies ist optional.</span><span class="sxs-lookup"><span data-stu-id="9185d-120">Optional.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="9185d-121">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="9185d-121">Child Elements</span></span>  
 <span data-ttu-id="9185d-122">Keiner</span><span class="sxs-lookup"><span data-stu-id="9185d-122">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="9185d-123">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="9185d-123">Parent Elements</span></span>  
  
|<span data-ttu-id="9185d-124">Element</span><span class="sxs-lookup"><span data-stu-id="9185d-124">Element</span></span>|<span data-ttu-id="9185d-125">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="9185d-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="9185d-126">\<ClaimTypeRequired ></span><span class="sxs-lookup"><span data-stu-id="9185d-126">\<claimTypeRequired></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/claimtyperequired.md)|<span data-ttu-id="9185d-127">Gibt den Satz von erforderlichen Ansprüchen für eingehende Sicherheitstoken.</span><span class="sxs-lookup"><span data-stu-id="9185d-127">Specifies the set of required claims for incoming security tokens.</span></span>|
