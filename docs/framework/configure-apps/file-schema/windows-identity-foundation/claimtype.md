---
title: <claimType>
ms.date: 03/30/2017
ms.assetid: d17b5831-9a2c-45c4-b0d1-68f48e72e861
author: BrucePerlerMS
ms.openlocfilehash: a46e9129bd27319abb4d7519444568af622170fc
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/06/2020
ms.locfileid: "70252072"
---
# \<claimType>
<span data-ttu-id="6890c-101">Gibt einen einzelnen optionalen oder erforderlichen Anspruch für eingehende Sicherheits Token an.</span><span class="sxs-lookup"><span data-stu-id="6890c-101">Specifies a single optional or required claim for incoming security tokens.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.identityModel>**](system-identitymodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<identityConfiguration>**](identityconfiguration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<claimTypeRequired>**](claimtyperequired.md)\  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<claimType>**  
  
## <a name="syntax"></a><span data-ttu-id="6890c-102">Syntax</span><span class="sxs-lookup"><span data-stu-id="6890c-102">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="6890c-103">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="6890c-103">Attributes and Elements</span></span>  
 <span data-ttu-id="6890c-104">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="6890c-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="6890c-105">Attribute</span><span class="sxs-lookup"><span data-stu-id="6890c-105">Attributes</span></span>  
  
|<span data-ttu-id="6890c-106">attribute</span><span class="sxs-lookup"><span data-stu-id="6890c-106">Attribute</span></span>|<span data-ttu-id="6890c-107">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="6890c-107">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="6890c-108">type</span><span class="sxs-lookup"><span data-stu-id="6890c-108">type</span></span>|<span data-ttu-id="6890c-109">Der Anspruchstyp.</span><span class="sxs-lookup"><span data-stu-id="6890c-109">The claim type.</span></span> <span data-ttu-id="6890c-110">In der Regel ein URI.</span><span class="sxs-lookup"><span data-stu-id="6890c-110">Typically a URI.</span></span> <span data-ttu-id="6890c-111">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="6890c-111">Required.</span></span>|  
|<span data-ttu-id="6890c-112">optional</span><span class="sxs-lookup"><span data-stu-id="6890c-112">optional</span></span>|<span data-ttu-id="6890c-113">Ein boolescher Wert, der angibt, ob der Anspruchstyp optional ist.</span><span class="sxs-lookup"><span data-stu-id="6890c-113">A boolean value that specifies whether the claim type is optional.</span></span> <span data-ttu-id="6890c-114">(Optional)</span><span class="sxs-lookup"><span data-stu-id="6890c-114">Optional.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="6890c-115">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="6890c-115">Child Elements</span></span>  
 <span data-ttu-id="6890c-116">Keine</span><span class="sxs-lookup"><span data-stu-id="6890c-116">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="6890c-117">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="6890c-117">Parent Elements</span></span>  
  
|<span data-ttu-id="6890c-118">Element</span><span class="sxs-lookup"><span data-stu-id="6890c-118">Element</span></span>|<span data-ttu-id="6890c-119">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="6890c-119">Description</span></span>|  
|-------------|-----------------|  
|[\<claimTypeRequired>](claimtyperequired.md)|<span data-ttu-id="6890c-120">Gibt den Satz erforderlicher Ansprüche für eingehende Sicherheits Token an.</span><span class="sxs-lookup"><span data-stu-id="6890c-120">Specifies the set of required claims for incoming security tokens.</span></span>|
