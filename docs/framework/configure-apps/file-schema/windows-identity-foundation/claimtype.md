---
title: <claimType>
ms.date: 03/30/2017
ms.assetid: d17b5831-9a2c-45c4-b0d1-68f48e72e861
author: BrucePerlerMS
ms.openlocfilehash: 6bc185572528d4229ee53f1421eaa5bf27b053e6
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61667222"
---
# <a name="claimtype"></a><span data-ttu-id="505aa-101">\<claimType></span><span class="sxs-lookup"><span data-stu-id="505aa-101">\<claimType></span></span>
<span data-ttu-id="505aa-102">Gibt einen einzelnen erforderliche oder optionale Anspruch eingehender Sicherheitstoken an.</span><span class="sxs-lookup"><span data-stu-id="505aa-102">Specifies a single optional or required claim for incoming security tokens.</span></span>  
  
 <span data-ttu-id="505aa-103">\<system.identityModel></span><span class="sxs-lookup"><span data-stu-id="505aa-103">\<system.identityModel></span></span>  
<span data-ttu-id="505aa-104">\<identityConfiguration></span><span class="sxs-lookup"><span data-stu-id="505aa-104">\<identityConfiguration></span></span>  
<span data-ttu-id="505aa-105">\<claimTypeRequired></span><span class="sxs-lookup"><span data-stu-id="505aa-105">\<claimTypeRequired></span></span>  
<span data-ttu-id="505aa-106">\<claimType></span><span class="sxs-lookup"><span data-stu-id="505aa-106">\<claimType></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="505aa-107">Syntax</span><span class="sxs-lookup"><span data-stu-id="505aa-107">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="505aa-108">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="505aa-108">Attributes and Elements</span></span>  
 <span data-ttu-id="505aa-109">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="505aa-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="505aa-110">Attribute</span><span class="sxs-lookup"><span data-stu-id="505aa-110">Attributes</span></span>  
  
|<span data-ttu-id="505aa-111">Attribut</span><span class="sxs-lookup"><span data-stu-id="505aa-111">Attribute</span></span>|<span data-ttu-id="505aa-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="505aa-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="505aa-113">Typ</span><span class="sxs-lookup"><span data-stu-id="505aa-113">type</span></span>|<span data-ttu-id="505aa-114">Der Anspruchstyp.</span><span class="sxs-lookup"><span data-stu-id="505aa-114">The claim type.</span></span> <span data-ttu-id="505aa-115">In der Regel ein URI.</span><span class="sxs-lookup"><span data-stu-id="505aa-115">Typically a URI.</span></span> <span data-ttu-id="505aa-116">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="505aa-116">Required.</span></span>|  
|<span data-ttu-id="505aa-117">Optional</span><span class="sxs-lookup"><span data-stu-id="505aa-117">optional</span></span>|<span data-ttu-id="505aa-118">Ein boolescher Wert, der angibt, ob der Typ des Anspruchs optional ist.</span><span class="sxs-lookup"><span data-stu-id="505aa-118">A boolean value that specifies whether the claim type is optional.</span></span> <span data-ttu-id="505aa-119">Dies ist optional.</span><span class="sxs-lookup"><span data-stu-id="505aa-119">Optional.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="505aa-120">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="505aa-120">Child Elements</span></span>  
 <span data-ttu-id="505aa-121">Keiner</span><span class="sxs-lookup"><span data-stu-id="505aa-121">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="505aa-122">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="505aa-122">Parent Elements</span></span>  
  
|<span data-ttu-id="505aa-123">Element</span><span class="sxs-lookup"><span data-stu-id="505aa-123">Element</span></span>|<span data-ttu-id="505aa-124">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="505aa-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="505aa-125">\<claimTypeRequired></span><span class="sxs-lookup"><span data-stu-id="505aa-125">\<claimTypeRequired></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/claimtyperequired.md)|<span data-ttu-id="505aa-126">Gibt den Satz von erforderlichen Ansprüchen für eingehende Sicherheitstoken.</span><span class="sxs-lookup"><span data-stu-id="505aa-126">Specifies the set of required claims for incoming security tokens.</span></span>|
