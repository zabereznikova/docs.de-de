---
title: CorParamAttr-Enumeration
ms.date: 03/30/2017
api_name:
- CorParamAttr
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorParamAttr
helpviewer_keywords:
- CorParamAttr enumeration [.NET Framework metadata]
ms.assetid: a7ff90ad-dad8-48e8-917d-4aa9a118cbc8
topic_type:
- apiref
ms.openlocfilehash: 6f5d022a96fa021cb28dbbb67d0b53e08f77498c
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95729283"
---
# <a name="corparamattr-enumeration"></a><span data-ttu-id="e58bc-102">CorParamAttr-Enumeration</span><span class="sxs-lookup"><span data-stu-id="e58bc-102">CorParamAttr Enumeration</span></span>

<span data-ttu-id="e58bc-103">Enthält Werte, die die Metadaten eines Methodenparameters beschreiben.</span><span class="sxs-lookup"><span data-stu-id="e58bc-103">Contains values that describe the metadata of a method parameter.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e58bc-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="e58bc-104">Syntax</span></span>  
  
```cpp  
typedef enum CorParamAttr {  
  
    pdIn                        =   0x0001,  
    pdOut                       =   0x0002,  
    pdOptional                  =   0x0010,  
  
    pdReservedMask              =   0xf000,  
    pdHasDefault                =   0x1000,  
    pdHasFieldMarshal           =   0x2000,  
  
    pdUnused                    =   0xcfe0  
  
} CorParamAttr;  
```  
  
## <a name="members"></a><span data-ttu-id="e58bc-105">Member</span><span class="sxs-lookup"><span data-stu-id="e58bc-105">Members</span></span>  
  
|<span data-ttu-id="e58bc-106">Member</span><span class="sxs-lookup"><span data-stu-id="e58bc-106">Member</span></span>|<span data-ttu-id="e58bc-107">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="e58bc-107">Description</span></span>|  
|------------|-----------------|  
|`pdIn`|<span data-ttu-id="e58bc-108">Gibt an, dass der-Parameter an den-Methodenaufrufe übergeben wird.</span><span class="sxs-lookup"><span data-stu-id="e58bc-108">Specifies that the parameter is passed into the method call.</span></span>|  
|`pdOut`|<span data-ttu-id="e58bc-109">Gibt an, dass der Parameter von der Rückgabe der Methode übergeben wird.</span><span class="sxs-lookup"><span data-stu-id="e58bc-109">Specifies that the parameter is passed from the method return.</span></span>|  
|`pdOptional`|<span data-ttu-id="e58bc-110">Gibt an, dass der Parameter optional ist.</span><span class="sxs-lookup"><span data-stu-id="e58bc-110">Specifies that the parameter is optional.</span></span>|  
|`pdReservedMask`|<span data-ttu-id="e58bc-111">Reserviert für die interne Verwendung durch den Common Language Runtime.</span><span class="sxs-lookup"><span data-stu-id="e58bc-111">Reserved for internal use by the common language runtime.</span></span>|  
|`pdHasDefault`|<span data-ttu-id="e58bc-112">Gibt an, dass der Parameter einen Standardwert besitzt.</span><span class="sxs-lookup"><span data-stu-id="e58bc-112">Specifies that the parameter has a default value.</span></span>|  
|`pdHasFieldMarshal`|<span data-ttu-id="e58bc-113">Gibt an, dass der Parameter über Marshallinginformationen verfügt.</span><span class="sxs-lookup"><span data-stu-id="e58bc-113">Specifies that the parameter has marshaling information.</span></span>|  
|`pdUnused`|<span data-ttu-id="e58bc-114">Nicht verwendet.</span><span class="sxs-lookup"><span data-stu-id="e58bc-114">Unused.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="e58bc-115">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="e58bc-115">Requirements</span></span>  

 <span data-ttu-id="e58bc-116">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e58bc-116">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e58bc-117">**Header:** Corhdr. h</span><span class="sxs-lookup"><span data-stu-id="e58bc-117">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="e58bc-118">**.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e58bc-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e58bc-119">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="e58bc-119">See also</span></span>

- [<span data-ttu-id="e58bc-120">Metadatenenumerationen</span><span class="sxs-lookup"><span data-stu-id="e58bc-120">Metadata Enumerations</span></span>](metadata-enumerations.md)
