---
title: '&lt;"ClaimType"&gt;'
ms.date: 03/30/2017
ms.assetid: d17b5831-9a2c-45c4-b0d1-68f48e72e861
author: BrucePerlerMS
ms.openlocfilehash: 805377565b6e835fd9ffba915a003bc56529a3b6
ms.sourcegitcommit: 213292dfbb0c37d83f62709959ff55c50af5560d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/25/2018
ms.locfileid: "47084214"
---
# <a name="ltclaimtypegt"></a><span data-ttu-id="21f9e-102">&lt;"ClaimType"&gt;</span><span class="sxs-lookup"><span data-stu-id="21f9e-102">&lt;claimType&gt;</span></span>
<span data-ttu-id="21f9e-103">Gibt einen einzelnen erforderliche oder optionale Anspruch eingehender Sicherheitstoken an.</span><span class="sxs-lookup"><span data-stu-id="21f9e-103">Specifies a single optional or required claim for incoming security tokens.</span></span>  
  
 <span data-ttu-id="21f9e-104">\<system.identityModel></span><span class="sxs-lookup"><span data-stu-id="21f9e-104">\<system.identityModel></span></span>  
<span data-ttu-id="21f9e-105">\<identityConfiguration></span><span class="sxs-lookup"><span data-stu-id="21f9e-105">\<identityConfiguration></span></span>  
<span data-ttu-id="21f9e-106">\<ClaimTypeRequired ></span><span class="sxs-lookup"><span data-stu-id="21f9e-106">\<claimTypeRequired></span></span>  
<span data-ttu-id="21f9e-107">\<"ClaimType" ></span><span class="sxs-lookup"><span data-stu-id="21f9e-107">\<claimType></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="21f9e-108">Syntax</span><span class="sxs-lookup"><span data-stu-id="21f9e-108">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="21f9e-109">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="21f9e-109">Attributes and Elements</span></span>  
 <span data-ttu-id="21f9e-110">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="21f9e-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="21f9e-111">Attribute</span><span class="sxs-lookup"><span data-stu-id="21f9e-111">Attributes</span></span>  
  
|<span data-ttu-id="21f9e-112">Attribut</span><span class="sxs-lookup"><span data-stu-id="21f9e-112">Attribute</span></span>|<span data-ttu-id="21f9e-113">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="21f9e-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="21f9e-114">Typ</span><span class="sxs-lookup"><span data-stu-id="21f9e-114">type</span></span>|<span data-ttu-id="21f9e-115">Der Anspruchstyp.</span><span class="sxs-lookup"><span data-stu-id="21f9e-115">The claim type.</span></span> <span data-ttu-id="21f9e-116">In der Regel ein URI.</span><span class="sxs-lookup"><span data-stu-id="21f9e-116">Typically a URI.</span></span> <span data-ttu-id="21f9e-117">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="21f9e-117">Required.</span></span>|  
|<span data-ttu-id="21f9e-118">Optional</span><span class="sxs-lookup"><span data-stu-id="21f9e-118">optional</span></span>|<span data-ttu-id="21f9e-119">Ein boolescher Wert, der angibt, ob der Typ des Anspruchs optional ist.</span><span class="sxs-lookup"><span data-stu-id="21f9e-119">A boolean value that specifies whether the claim type is optional.</span></span> <span data-ttu-id="21f9e-120">Dies ist optional.</span><span class="sxs-lookup"><span data-stu-id="21f9e-120">Optional.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="21f9e-121">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="21f9e-121">Child Elements</span></span>  
 <span data-ttu-id="21f9e-122">Keiner</span><span class="sxs-lookup"><span data-stu-id="21f9e-122">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="21f9e-123">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="21f9e-123">Parent Elements</span></span>  
  
|<span data-ttu-id="21f9e-124">Element</span><span class="sxs-lookup"><span data-stu-id="21f9e-124">Element</span></span>|<span data-ttu-id="21f9e-125">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="21f9e-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="21f9e-126">\<ClaimTypeRequired ></span><span class="sxs-lookup"><span data-stu-id="21f9e-126">\<claimTypeRequired></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/claimtyperequired.md)|<span data-ttu-id="21f9e-127">Gibt den Satz von erforderlichen Ansprüchen für eingehende Sicherheitstoken.</span><span class="sxs-lookup"><span data-stu-id="21f9e-127">Specifies the set of required claims for incoming security tokens.</span></span>|
