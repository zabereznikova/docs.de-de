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
ms.openlocfilehash: c1707a09f14fbab6150c2ecbcd188d7bf88064fa
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61989663"
---
# <a name="cordebuggenerationtypes-enumeration"></a><span data-ttu-id="ab663-102">CorDebugGenerationTypes-Enumeration</span><span class="sxs-lookup"><span data-stu-id="ab663-102">CorDebugGenerationTypes Enumeration</span></span>
<span data-ttu-id="ab663-103">Gibt die Generierung eines Arbeitsspeicherbereichs auf dem verwalteten Heap an.</span><span class="sxs-lookup"><span data-stu-id="ab663-103">Specifies the generation of a region of memory on the managed heap.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ab663-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="ab663-104">Syntax</span></span>  
  
```  
typedef enum CorDebugGenerationTypes {  
    CorDebug_Gen0 = 0,  
    CorDebug_Gen1 = 1,  
    CorDebug_Gen2 = 2,  
    CorDebug_LOH  = 3,  
} CorDebugRegionTypes;  
```  
  
## <a name="members"></a><span data-ttu-id="ab663-105">Member</span><span class="sxs-lookup"><span data-stu-id="ab663-105">Members</span></span>  
  
|<span data-ttu-id="ab663-106">Membername</span><span class="sxs-lookup"><span data-stu-id="ab663-106">Member name</span></span>|<span data-ttu-id="ab663-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="ab663-107">Description</span></span>|  
|-----------------|-----------------|  
|`CorDebug_Gen0`|<span data-ttu-id="ab663-108">Generation 0.</span><span class="sxs-lookup"><span data-stu-id="ab663-108">Generation 0.</span></span>|  
|`CorDebug_Gen1`|<span data-ttu-id="ab663-109">Generation 1.</span><span class="sxs-lookup"><span data-stu-id="ab663-109">Generation 1.</span></span>|  
|`CorDebug_Gen2`|<span data-ttu-id="ab663-110">Generation 2.</span><span class="sxs-lookup"><span data-stu-id="ab663-110">Generation 2.</span></span>|  
|`CorDebug_LOH`|<span data-ttu-id="ab663-111">Der große Objektheap.</span><span class="sxs-lookup"><span data-stu-id="ab663-111">The large object heap.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ab663-112">Hinweise</span><span class="sxs-lookup"><span data-stu-id="ab663-112">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ab663-113">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="ab663-113">Requirements</span></span>  
 <span data-ttu-id="ab663-114">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ab663-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ab663-115">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="ab663-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="ab663-116">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ab663-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ab663-117">**.NET Framework-Versionen:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ab663-117">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ab663-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ab663-118">See also</span></span>

- [<span data-ttu-id="ab663-119">Debuggen von Enumerationen</span><span class="sxs-lookup"><span data-stu-id="ab663-119">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
