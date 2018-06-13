---
title: COR_ACTIVE_FUNCTION-Struktur
ms.date: 03/30/2017
api_name:
- COR_ACTIVE_FUNCTION
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- COR_ACTIVE_FUNCTION
helpviewer_keywords:
- COR_ACTIVE_FUNCTION structure [.NET Framework debugging]
ms.assetid: ed86185f-2152-459c-961f-10c06d62e83f
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 86ab3d3a0f460f1ecdf86147b14df205aaf49635
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33404197"
---
# <a name="coractivefunction-structure"></a><span data-ttu-id="d9e31-102">COR_ACTIVE_FUNCTION-Struktur</span><span class="sxs-lookup"><span data-stu-id="d9e31-102">COR_ACTIVE_FUNCTION Structure</span></span>
<span data-ttu-id="d9e31-103">Enthält Informationen zu den Funktionen, die aktuell in den Rahmen eines Threads aktiv sind.</span><span class="sxs-lookup"><span data-stu-id="d9e31-103">Contains information about the functions that are currently active in a thread's frames.</span></span> <span data-ttu-id="d9e31-104">Diese Struktur wird verwendet, durch die [ICorDebugThread2:: GetActiveFunctions](../../../../docs/framework/unmanaged-api/debugging/icordebugthread2-getactivefunctions-method.md) Methode.</span><span class="sxs-lookup"><span data-stu-id="d9e31-104">This structure is used by the [ICorDebugThread2::GetActiveFunctions](../../../../docs/framework/unmanaged-api/debugging/icordebugthread2-getactivefunctions-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d9e31-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="d9e31-105">Syntax</span></span>  
  
```  
typedef struct  _COR_ACTIVE_FUNCTION {  
    ICorDebugAppDomain   *pAppDomain;  
    ICorDebugModule      *pModule;  
    ICorDebugFunction2   *pFunction;  
    ULONG32              ilOffset;  
    ULONG32              flags;  
} COR_ACTIVE_FUNCTION;  
```  
  
## <a name="members"></a><span data-ttu-id="d9e31-106">Member</span><span class="sxs-lookup"><span data-stu-id="d9e31-106">Members</span></span>  
  
|<span data-ttu-id="d9e31-107">Member</span><span class="sxs-lookup"><span data-stu-id="d9e31-107">Member</span></span>|<span data-ttu-id="d9e31-108">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="d9e31-108">Description</span></span>|  
|------------|-----------------|  
|`pAppDomain`|<span data-ttu-id="d9e31-109">Zeiger auf den Besitzer von der `ilOffset` Feld.</span><span class="sxs-lookup"><span data-stu-id="d9e31-109">Pointer to the application domain owner of the `ilOffset` field.</span></span>|  
|`pModule`|<span data-ttu-id="d9e31-110">Zeiger zum Inhaber des Moduls der `ilOffset` Feld.</span><span class="sxs-lookup"><span data-stu-id="d9e31-110">Pointer to the module owner of the `ilOffset` field.</span></span>|  
|`pFunction`|<span data-ttu-id="d9e31-111">Zeiger zum Inhaber der Funktion der `ilOffset` Feld.</span><span class="sxs-lookup"><span data-stu-id="d9e31-111">Pointer to the function owner of the `ilOffset` field.</span></span>|  
|`ilOffset`|<span data-ttu-id="d9e31-112">Der Microsoft intermediate Language (MSIL)-Offset des Frames.</span><span class="sxs-lookup"><span data-stu-id="d9e31-112">The Microsoft intermediate language (MSIL) offset of the frame.</span></span>|  
|`flags`|<span data-ttu-id="d9e31-113">Für zukünftige Erweiterungen reserviert.</span><span class="sxs-lookup"><span data-stu-id="d9e31-113">Reserved for future extensibility.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="d9e31-114">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="d9e31-114">Requirements</span></span>  
 <span data-ttu-id="d9e31-115">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d9e31-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d9e31-116">**Header:** CorDebug.idl</span><span class="sxs-lookup"><span data-stu-id="d9e31-116">**Header:** CorDebug.idl</span></span>  
  
 <span data-ttu-id="d9e31-117">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d9e31-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d9e31-118">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d9e31-118">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d9e31-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d9e31-119">See Also</span></span>  
 [<span data-ttu-id="d9e31-120">Debuggen von Strukturen</span><span class="sxs-lookup"><span data-stu-id="d9e31-120">Debugging Structures</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-structures.md)  
 [<span data-ttu-id="d9e31-121">Debuggen</span><span class="sxs-lookup"><span data-stu-id="d9e31-121">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
