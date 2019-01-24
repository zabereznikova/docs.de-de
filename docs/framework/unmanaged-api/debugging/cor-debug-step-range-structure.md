---
title: COR_DEBUG_STEP_RANGE-Struktur
ms.date: 03/30/2017
api_name:
- COR_DEBUG_STEP_RANGE
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- COR_DEBUG_STEP_RANGE
helpviewer_keywords:
- COR_DEBUG_STEP_RANGE structure [.NET Framework debugging]
ms.assetid: 8809d00e-beaa-4dcf-b4e8-e89d0a5406b7
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 45340a26b3351ca03b453fbcdb626de199bd6d19
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54710364"
---
# <a name="cordebugsteprange-structure"></a><span data-ttu-id="16a04-102">COR_DEBUG_STEP_RANGE-Struktur</span><span class="sxs-lookup"><span data-stu-id="16a04-102">COR_DEBUG_STEP_RANGE Structure</span></span>
<span data-ttu-id="16a04-103">Enthält die Offsetinformationen für einen Codebereich.</span><span class="sxs-lookup"><span data-stu-id="16a04-103">Contains the offset information for a range of code.</span></span>  
  
 <span data-ttu-id="16a04-104">Diese Struktur wird verwendet, durch die [ICorDebugStepper:: StepRange](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-steprange-method.md) Methode.</span><span class="sxs-lookup"><span data-stu-id="16a04-104">This structure is used by the [ICorDebugStepper::StepRange](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-steprange-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="16a04-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="16a04-105">Syntax</span></span>  
  
```  
typedef struct {  
    ULONG32 startOffset;  
    ULONG32 endOffset;  
} COR_DEBUG_STEP_RANGE;  
```  
  
## <a name="members"></a><span data-ttu-id="16a04-106">Member</span><span class="sxs-lookup"><span data-stu-id="16a04-106">Members</span></span>  
  
|<span data-ttu-id="16a04-107">Member</span><span class="sxs-lookup"><span data-stu-id="16a04-107">Member</span></span>|<span data-ttu-id="16a04-108">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="16a04-108">Description</span></span>|  
|------------|-----------------|  
|`startOffset`|<span data-ttu-id="16a04-109">Der Offset vom Anfang des Bereichs.</span><span class="sxs-lookup"><span data-stu-id="16a04-109">The offset of the beginning of the range.</span></span>|  
|`endOffset`|<span data-ttu-id="16a04-110">Der Offset des Endes des Bereichs.</span><span class="sxs-lookup"><span data-stu-id="16a04-110">The offset of the end of the range.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="16a04-111">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="16a04-111">Requirements</span></span>  
 <span data-ttu-id="16a04-112">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="16a04-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="16a04-113">**Header:** CorDebug.idl</span><span class="sxs-lookup"><span data-stu-id="16a04-113">**Header:** CorDebug.idl</span></span>  
  
 <span data-ttu-id="16a04-114">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="16a04-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="16a04-115">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="16a04-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="16a04-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="16a04-116">See also</span></span>
- [<span data-ttu-id="16a04-117">StepRange-Methode</span><span class="sxs-lookup"><span data-stu-id="16a04-117">StepRange Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-steprange-method.md)
- [<span data-ttu-id="16a04-118">Debuggen von Strukturen</span><span class="sxs-lookup"><span data-stu-id="16a04-118">Debugging Structures</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-structures.md)
- [<span data-ttu-id="16a04-119">Debuggen</span><span class="sxs-lookup"><span data-stu-id="16a04-119">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
