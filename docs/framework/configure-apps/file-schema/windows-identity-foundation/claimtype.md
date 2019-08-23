---
title: <claimType>
ms.date: 03/30/2017
ms.assetid: d17b5831-9a2c-45c4-b0d1-68f48e72e861
author: BrucePerlerMS
ms.openlocfilehash: 4253aec961b812b6893ee201861d2ab38048032a
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69942883"
---
# <a name="claimtype"></a><span data-ttu-id="5f802-101">\<claimType></span><span class="sxs-lookup"><span data-stu-id="5f802-101">\<claimType></span></span>
<span data-ttu-id="5f802-102">Gibt einen einzelnen optionalen oder erforderlichen Anspruch für eingehende Sicherheits Token an.</span><span class="sxs-lookup"><span data-stu-id="5f802-102">Specifies a single optional or required claim for incoming security tokens.</span></span>  
  
 <span data-ttu-id="5f802-103">\<system.identityModel></span><span class="sxs-lookup"><span data-stu-id="5f802-103">\<system.identityModel></span></span>  
<span data-ttu-id="5f802-104">\<identityConfiguration></span><span class="sxs-lookup"><span data-stu-id="5f802-104">\<identityConfiguration></span></span>  
<span data-ttu-id="5f802-105">\<claimTypeRequired></span><span class="sxs-lookup"><span data-stu-id="5f802-105">\<claimTypeRequired></span></span>  
<span data-ttu-id="5f802-106">\<claimType></span><span class="sxs-lookup"><span data-stu-id="5f802-106">\<claimType></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5f802-107">Syntax</span><span class="sxs-lookup"><span data-stu-id="5f802-107">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="5f802-108">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="5f802-108">Attributes and Elements</span></span>  
 <span data-ttu-id="5f802-109">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="5f802-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="5f802-110">Attribute</span><span class="sxs-lookup"><span data-stu-id="5f802-110">Attributes</span></span>  
  
|<span data-ttu-id="5f802-111">Attribut</span><span class="sxs-lookup"><span data-stu-id="5f802-111">Attribute</span></span>|<span data-ttu-id="5f802-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="5f802-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="5f802-113">Typ</span><span class="sxs-lookup"><span data-stu-id="5f802-113">type</span></span>|<span data-ttu-id="5f802-114">Der Anspruchstyp.</span><span class="sxs-lookup"><span data-stu-id="5f802-114">The claim type.</span></span> <span data-ttu-id="5f802-115">In der Regel ein URI.</span><span class="sxs-lookup"><span data-stu-id="5f802-115">Typically a URI.</span></span> <span data-ttu-id="5f802-116">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="5f802-116">Required.</span></span>|  
|<span data-ttu-id="5f802-117">Optional</span><span class="sxs-lookup"><span data-stu-id="5f802-117">optional</span></span>|<span data-ttu-id="5f802-118">Ein boolescher Wert, der angibt, ob der Anspruchstyp optional ist.</span><span class="sxs-lookup"><span data-stu-id="5f802-118">A boolean value that specifies whether the claim type is optional.</span></span> <span data-ttu-id="5f802-119">Optional.</span><span class="sxs-lookup"><span data-stu-id="5f802-119">Optional.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="5f802-120">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="5f802-120">Child Elements</span></span>  
 <span data-ttu-id="5f802-121">None</span><span class="sxs-lookup"><span data-stu-id="5f802-121">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="5f802-122">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="5f802-122">Parent Elements</span></span>  
  
|<span data-ttu-id="5f802-123">Element</span><span class="sxs-lookup"><span data-stu-id="5f802-123">Element</span></span>|<span data-ttu-id="5f802-124">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="5f802-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="5f802-125">\<claimTypeRequired></span><span class="sxs-lookup"><span data-stu-id="5f802-125">\<claimTypeRequired></span></span>](claimtyperequired.md)|<span data-ttu-id="5f802-126">Gibt den Satz erforderlicher Ansprüche für eingehende Sicherheits Token an.</span><span class="sxs-lookup"><span data-stu-id="5f802-126">Specifies the set of required claims for incoming security tokens.</span></span>|
