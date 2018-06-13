---
title: CorDebugGenerationTypes-Enumeration
ms.date: 03/30/2017
api_name:
- CorDebugGenerationTypes
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- CorDebugGenerationTypes
helpviewer_keywords:
- CorDebugGenerationTypes enumeration [.NET Framework debugging]
ms.assetid: 9f25b64f-eedd-4ae5-8b0e-cfdfb9b6c5d8
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 563c1fccd0b1fd254d721f631b0c8312b3b09bbd
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33402430"
---
# <a name="cordebuggenerationtypes-enumeration"></a><span data-ttu-id="99e7c-102">CorDebugGenerationTypes-Enumeration</span><span class="sxs-lookup"><span data-stu-id="99e7c-102">CorDebugGenerationTypes Enumeration</span></span>
<span data-ttu-id="99e7c-103">Gibt die Generierung eines Arbeitsspeicherbereichs auf dem verwalteten Heap an.</span><span class="sxs-lookup"><span data-stu-id="99e7c-103">Specifies the generation of a region of memory on the managed heap.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="99e7c-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="99e7c-104">Syntax</span></span>  
  
```  
typedef enum CorDebugGenerationTypes {  
    CorDebug_Gen0 = 0,  
    CorDebug_Gen1 = 1,  
    CorDebug_Gen2 = 2,  
    CorDebug_LOH  = 3,  
} CorDebugRegionTypes;  
```  
  
## <a name="members"></a><span data-ttu-id="99e7c-105">Member</span><span class="sxs-lookup"><span data-stu-id="99e7c-105">Members</span></span>  
  
|<span data-ttu-id="99e7c-106">Membername</span><span class="sxs-lookup"><span data-stu-id="99e7c-106">Member name</span></span>|<span data-ttu-id="99e7c-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="99e7c-107">Description</span></span>|  
|-----------------|-----------------|  
|`CorDebug_Gen0`|<span data-ttu-id="99e7c-108">Generation 0.</span><span class="sxs-lookup"><span data-stu-id="99e7c-108">Generation 0.</span></span>|  
|`CorDebug_Gen1`|<span data-ttu-id="99e7c-109">Generation 1.</span><span class="sxs-lookup"><span data-stu-id="99e7c-109">Generation 1.</span></span>|  
|`CorDebug_Gen2`|<span data-ttu-id="99e7c-110">Generation 2.</span><span class="sxs-lookup"><span data-stu-id="99e7c-110">Generation 2.</span></span>|  
|`CorDebug_LOH`|<span data-ttu-id="99e7c-111">Der große Objektheap.</span><span class="sxs-lookup"><span data-stu-id="99e7c-111">The large object heap.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="99e7c-112">Hinweise</span><span class="sxs-lookup"><span data-stu-id="99e7c-112">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="99e7c-113">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="99e7c-113">Requirements</span></span>  
 <span data-ttu-id="99e7c-114">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="99e7c-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="99e7c-115">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="99e7c-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="99e7c-116">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="99e7c-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="99e7c-117">**.NET Framework-Versionen:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="99e7c-117">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="99e7c-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="99e7c-118">See Also</span></span>  
 [<span data-ttu-id="99e7c-119">Debuggen von Enumerationen</span><span class="sxs-lookup"><span data-stu-id="99e7c-119">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
