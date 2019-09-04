---
title: <claimType>
ms.date: 03/30/2017
ms.assetid: d17b5831-9a2c-45c4-b0d1-68f48e72e861
author: BrucePerlerMS
ms.openlocfilehash: a46e9129bd27319abb4d7519444568af622170fc
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/04/2019
ms.locfileid: "70252072"
---
# <a name="claimtype"></a><span data-ttu-id="c8f99-101">\<claimType></span><span class="sxs-lookup"><span data-stu-id="c8f99-101">\<claimType></span></span>
<span data-ttu-id="c8f99-102">Gibt einen einzelnen optionalen oder erforderlichen Anspruch für eingehende Sicherheits Token an.</span><span class="sxs-lookup"><span data-stu-id="c8f99-102">Specifies a single optional or required claim for incoming security tokens.</span></span>  
  
<span data-ttu-id="c8f99-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="c8f99-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="c8f99-104">&nbsp;&nbsp;[ **\<System. IdentityModel->** ](system-identitymodel.md)</span><span class="sxs-lookup"><span data-stu-id="c8f99-104">&nbsp;&nbsp;[**\<system.identityModel>**](system-identitymodel.md)</span></span>\
<span data-ttu-id="c8f99-105">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<identityconfiguration->** ](identityconfiguration.md)</span><span class="sxs-lookup"><span data-stu-id="c8f99-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<identityConfiguration>**](identityconfiguration.md)</span></span>\
<span data-ttu-id="c8f99-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<claimtyperequired->** ](claimtyperequired.md)</span><span class="sxs-lookup"><span data-stu-id="c8f99-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<claimTypeRequired>**](claimtyperequired.md)</span></span>\  
<span data-ttu-id="c8f99-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<ClaimType->**</span><span class="sxs-lookup"><span data-stu-id="c8f99-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<claimType>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c8f99-108">Syntax</span><span class="sxs-lookup"><span data-stu-id="c8f99-108">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="c8f99-109">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="c8f99-109">Attributes and Elements</span></span>  
 <span data-ttu-id="c8f99-110">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="c8f99-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="c8f99-111">Attribute</span><span class="sxs-lookup"><span data-stu-id="c8f99-111">Attributes</span></span>  
  
|<span data-ttu-id="c8f99-112">Attribut</span><span class="sxs-lookup"><span data-stu-id="c8f99-112">Attribute</span></span>|<span data-ttu-id="c8f99-113">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="c8f99-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="c8f99-114">Typ</span><span class="sxs-lookup"><span data-stu-id="c8f99-114">type</span></span>|<span data-ttu-id="c8f99-115">Der Anspruchstyp.</span><span class="sxs-lookup"><span data-stu-id="c8f99-115">The claim type.</span></span> <span data-ttu-id="c8f99-116">In der Regel ein URI.</span><span class="sxs-lookup"><span data-stu-id="c8f99-116">Typically a URI.</span></span> <span data-ttu-id="c8f99-117">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="c8f99-117">Required.</span></span>|  
|<span data-ttu-id="c8f99-118">Optional</span><span class="sxs-lookup"><span data-stu-id="c8f99-118">optional</span></span>|<span data-ttu-id="c8f99-119">Ein boolescher Wert, der angibt, ob der Anspruchstyp optional ist.</span><span class="sxs-lookup"><span data-stu-id="c8f99-119">A boolean value that specifies whether the claim type is optional.</span></span> <span data-ttu-id="c8f99-120">Optional.</span><span class="sxs-lookup"><span data-stu-id="c8f99-120">Optional.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="c8f99-121">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="c8f99-121">Child Elements</span></span>  
 <span data-ttu-id="c8f99-122">None</span><span class="sxs-lookup"><span data-stu-id="c8f99-122">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="c8f99-123">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="c8f99-123">Parent Elements</span></span>  
  
|<span data-ttu-id="c8f99-124">Element</span><span class="sxs-lookup"><span data-stu-id="c8f99-124">Element</span></span>|<span data-ttu-id="c8f99-125">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="c8f99-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="c8f99-126">\<claimTypeRequired></span><span class="sxs-lookup"><span data-stu-id="c8f99-126">\<claimTypeRequired></span></span>](claimtyperequired.md)|<span data-ttu-id="c8f99-127">Gibt den Satz erforderlicher Ansprüche für eingehende Sicherheits Token an.</span><span class="sxs-lookup"><span data-stu-id="c8f99-127">Specifies the set of required claims for incoming security tokens.</span></span>|
