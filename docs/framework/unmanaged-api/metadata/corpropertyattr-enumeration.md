---
title: CorPropertyAttr-Enumeration
ms.date: 03/30/2017
api_name:
- CorPropertyAttr
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorPropertyAttr
helpviewer_keywords:
- CorPropertyAttr enumeration [.NET Framework metadata]
ms.assetid: 58ac8202-854d-4efd-acfb-d2da8b446e12
topic_type:
- apiref
ms.openlocfilehash: d76de80f87a8e5a63eac9f6a413f2efb0e394b0a
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95706124"
---
# <a name="corpropertyattr-enumeration"></a><span data-ttu-id="15c5b-102">CorPropertyAttr-Enumeration</span><span class="sxs-lookup"><span data-stu-id="15c5b-102">CorPropertyAttr Enumeration</span></span>

<span data-ttu-id="15c5b-103">Enthält Werte, in denen die Metadaten einer Eigenschaft beschrieben werden.</span><span class="sxs-lookup"><span data-stu-id="15c5b-103">Contains values that describe the metadata of a property.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="15c5b-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="15c5b-104">Syntax</span></span>  
  
```cpp  
typedef enum CorPropertyAttr {  
  
    prSpecialName           =   0x0200,
    prReservedMask          =   0xf400,  
    prRTSpecialName         =   0x0400,  
    prHasDefault            =   0x1000,  
    prUnused                =   0xe9ff  
  
} CorPropertyAttr;  
```  
  
## <a name="members"></a><span data-ttu-id="15c5b-105">Member</span><span class="sxs-lookup"><span data-stu-id="15c5b-105">Members</span></span>  
  
|<span data-ttu-id="15c5b-106">Member</span><span class="sxs-lookup"><span data-stu-id="15c5b-106">Member</span></span>|<span data-ttu-id="15c5b-107">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="15c5b-107">Description</span></span>|  
|------------|-----------------|  
|`prSpecialName`|<span data-ttu-id="15c5b-108">Gibt an, dass die Eigenschaft speziell ist, und dass Ihr Name beschreibt, wie.</span><span class="sxs-lookup"><span data-stu-id="15c5b-108">Specifies that the property is special, and that its name describes how.</span></span>|  
|`prReservedMask`|<span data-ttu-id="15c5b-109">Reserviert für die interne Verwendung durch den Common Language Runtime.</span><span class="sxs-lookup"><span data-stu-id="15c5b-109">Reserved for internal use by the common language runtime.</span></span>|  
|`prRTSpecialName`|<span data-ttu-id="15c5b-110">Gibt an, dass die Common Language Runtime Metadaten-internen APIs die Codierung des Eigenschafts namens überprüfen sollen.</span><span class="sxs-lookup"><span data-stu-id="15c5b-110">Specifies that the common language runtime metadata internal APIs should check the encoding of the property name.</span></span>|  
|`prHasDefault`|<span data-ttu-id="15c5b-111">Gibt an, dass die Eigenschaft einen Standardwert besitzt.</span><span class="sxs-lookup"><span data-stu-id="15c5b-111">Specifies that the property has a default value.</span></span>|  
|`prUnused`|<span data-ttu-id="15c5b-112">Nicht verwendet.</span><span class="sxs-lookup"><span data-stu-id="15c5b-112">Unused.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="15c5b-113">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="15c5b-113">Requirements</span></span>  

 <span data-ttu-id="15c5b-114">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="15c5b-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="15c5b-115">**Header:** Corhdr. h</span><span class="sxs-lookup"><span data-stu-id="15c5b-115">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="15c5b-116">**.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="15c5b-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="15c5b-117">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="15c5b-117">See also</span></span>

- [<span data-ttu-id="15c5b-118">Metadatenenumerationen</span><span class="sxs-lookup"><span data-stu-id="15c5b-118">Metadata Enumerations</span></span>](metadata-enumerations.md)
