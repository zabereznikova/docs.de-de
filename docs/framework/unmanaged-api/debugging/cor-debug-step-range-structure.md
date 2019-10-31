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
ms.openlocfilehash: 206e4fb232f4786a76525d24aa379b25d6d2f71d
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73099343"
---
# <a name="cor_debug_step_range-structure"></a><span data-ttu-id="c45ae-102">COR_DEBUG_STEP_RANGE-Struktur</span><span class="sxs-lookup"><span data-stu-id="c45ae-102">COR_DEBUG_STEP_RANGE Structure</span></span>
<span data-ttu-id="c45ae-103">Enthält die Offsetinformationen für einen Codebereich.</span><span class="sxs-lookup"><span data-stu-id="c45ae-103">Contains the offset information for a range of code.</span></span>  
  
 <span data-ttu-id="c45ae-104">Diese Struktur wird von der [ICorDebugStepper:: StepRange](icordebugstepper-steprange-method.md) -Methode verwendet.</span><span class="sxs-lookup"><span data-stu-id="c45ae-104">This structure is used by the [ICorDebugStepper::StepRange](icordebugstepper-steprange-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c45ae-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="c45ae-105">Syntax</span></span>  
  
```cpp  
typedef struct {  
    ULONG32 startOffset;  
    ULONG32 endOffset;  
} COR_DEBUG_STEP_RANGE;  
```  
  
## <a name="members"></a><span data-ttu-id="c45ae-106">Member</span><span class="sxs-lookup"><span data-stu-id="c45ae-106">Members</span></span>  
  
|<span data-ttu-id="c45ae-107">Member</span><span class="sxs-lookup"><span data-stu-id="c45ae-107">Member</span></span>|<span data-ttu-id="c45ae-108">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="c45ae-108">Description</span></span>|  
|------------|-----------------|  
|`startOffset`|<span data-ttu-id="c45ae-109">Der Offset vom Anfang des Bereichs.</span><span class="sxs-lookup"><span data-stu-id="c45ae-109">The offset of the beginning of the range.</span></span>|  
|`endOffset`|<span data-ttu-id="c45ae-110">Der Offset des Endes des Bereichs.</span><span class="sxs-lookup"><span data-stu-id="c45ae-110">The offset of the end of the range.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="c45ae-111">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="c45ae-111">Requirements</span></span>  
 <span data-ttu-id="c45ae-112">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c45ae-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c45ae-113">**Header:** Cordebug. idl</span><span class="sxs-lookup"><span data-stu-id="c45ae-113">**Header:** CorDebug.idl</span></span>  
  
 <span data-ttu-id="c45ae-114">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c45ae-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c45ae-115">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c45ae-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c45ae-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c45ae-116">See also</span></span>

- [<span data-ttu-id="c45ae-117">StepRange-Methode</span><span class="sxs-lookup"><span data-stu-id="c45ae-117">StepRange Method</span></span>](icordebugstepper-steprange-method.md)
- [<span data-ttu-id="c45ae-118">Debuggen von Strukturen</span><span class="sxs-lookup"><span data-stu-id="c45ae-118">Debugging Structures</span></span>](debugging-structures.md)
- [<span data-ttu-id="c45ae-119">Debuggen</span><span class="sxs-lookup"><span data-stu-id="c45ae-119">Debugging</span></span>](index.md)
