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
ms.openlocfilehash: c4ee8833578b082f25c427b13d77072d1954197f
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="ltclaimtypegt"></a><span data-ttu-id="29abd-102">&lt;claimType&gt;</span><span class="sxs-lookup"><span data-stu-id="29abd-102">&lt;claimType&gt;</span></span>
<span data-ttu-id="29abd-103">Gibt einen einzelnen Anspruch aus erforderliche oder optionale für eingehende Sicherheitstoken an.</span><span class="sxs-lookup"><span data-stu-id="29abd-103">Specifies a single optional or required claim for incoming security tokens.</span></span>  
  
 <span data-ttu-id="29abd-104">\<system.identityModel ></span><span class="sxs-lookup"><span data-stu-id="29abd-104">\<system.identityModel></span></span>  
<span data-ttu-id="29abd-105">\<IdentityConfiguration ></span><span class="sxs-lookup"><span data-stu-id="29abd-105">\<identityConfiguration></span></span>  
<span data-ttu-id="29abd-106">\<ClaimTypeRequired ></span><span class="sxs-lookup"><span data-stu-id="29abd-106">\<claimTypeRequired></span></span>  
<span data-ttu-id="29abd-107">\<ClaimType ></span><span class="sxs-lookup"><span data-stu-id="29abd-107">\<claimType></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="29abd-108">Syntax</span><span class="sxs-lookup"><span data-stu-id="29abd-108">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="29abd-109">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="29abd-109">Attributes and Elements</span></span>  
 <span data-ttu-id="29abd-110">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="29abd-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="29abd-111">Attribute</span><span class="sxs-lookup"><span data-stu-id="29abd-111">Attributes</span></span>  
  
|<span data-ttu-id="29abd-112">Attribut</span><span class="sxs-lookup"><span data-stu-id="29abd-112">Attribute</span></span>|<span data-ttu-id="29abd-113">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="29abd-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="29abd-114">Typ</span><span class="sxs-lookup"><span data-stu-id="29abd-114">type</span></span>|<span data-ttu-id="29abd-115">Der Anspruchstyp.</span><span class="sxs-lookup"><span data-stu-id="29abd-115">The claim type.</span></span> <span data-ttu-id="29abd-116">In der Regel ein URI.</span><span class="sxs-lookup"><span data-stu-id="29abd-116">Typically a URI.</span></span> <span data-ttu-id="29abd-117">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="29abd-117">Required.</span></span>|  
|<span data-ttu-id="29abd-118">Optional</span><span class="sxs-lookup"><span data-stu-id="29abd-118">optional</span></span>|<span data-ttu-id="29abd-119">Ein boolescher Wert, der angibt, ob der Typ des Anspruchs optional ist.</span><span class="sxs-lookup"><span data-stu-id="29abd-119">A boolean value that specifies whether the claim type is optional.</span></span> <span data-ttu-id="29abd-120">Dies ist optional.</span><span class="sxs-lookup"><span data-stu-id="29abd-120">Optional.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="29abd-121">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="29abd-121">Child Elements</span></span>  
 <span data-ttu-id="29abd-122">Keine</span><span class="sxs-lookup"><span data-stu-id="29abd-122">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="29abd-123">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="29abd-123">Parent Elements</span></span>  
  
|<span data-ttu-id="29abd-124">Element</span><span class="sxs-lookup"><span data-stu-id="29abd-124">Element</span></span>|<span data-ttu-id="29abd-125">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="29abd-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="29abd-126">\<ClaimTypeRequired ></span><span class="sxs-lookup"><span data-stu-id="29abd-126">\<claimTypeRequired></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/claimtyperequired.md)|<span data-ttu-id="29abd-127">Gibt den Satz von erforderlichen Ansprüchen für eingehende Sicherheitstoken.</span><span class="sxs-lookup"><span data-stu-id="29abd-127">Specifies the set of required claims for incoming security tokens.</span></span>|
