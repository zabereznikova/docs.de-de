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
ms.openlocfilehash: c0400da0cd29d642a1be42be7e2b22213ae54b94
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59121770"
---
# <a name="coractivefunction-structure"></a><span data-ttu-id="fb42c-102">COR_ACTIVE_FUNCTION-Struktur</span><span class="sxs-lookup"><span data-stu-id="fb42c-102">COR_ACTIVE_FUNCTION Structure</span></span>
<span data-ttu-id="fb42c-103">Enthält Informationen zu den Funktionen, die aktuell in den Rahmen eines Threads aktiv sind.</span><span class="sxs-lookup"><span data-stu-id="fb42c-103">Contains information about the functions that are currently active in a thread's frames.</span></span> <span data-ttu-id="fb42c-104">Diese Struktur wird verwendet, durch die [ICorDebugThread2:: GetActiveFunctions](../../../../docs/framework/unmanaged-api/debugging/icordebugthread2-getactivefunctions-method.md) Methode.</span><span class="sxs-lookup"><span data-stu-id="fb42c-104">This structure is used by the [ICorDebugThread2::GetActiveFunctions](../../../../docs/framework/unmanaged-api/debugging/icordebugthread2-getactivefunctions-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fb42c-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="fb42c-105">Syntax</span></span>  
  
```  
typedef struct  _COR_ACTIVE_FUNCTION {  
    ICorDebugAppDomain   *pAppDomain;  
    ICorDebugModule      *pModule;  
    ICorDebugFunction2   *pFunction;  
    ULONG32              ilOffset;  
    ULONG32              flags;  
} COR_ACTIVE_FUNCTION;  
```  
  
## <a name="members"></a><span data-ttu-id="fb42c-106">Member</span><span class="sxs-lookup"><span data-stu-id="fb42c-106">Members</span></span>  
  
|<span data-ttu-id="fb42c-107">Member</span><span class="sxs-lookup"><span data-stu-id="fb42c-107">Member</span></span>|<span data-ttu-id="fb42c-108">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="fb42c-108">Description</span></span>|  
|------------|-----------------|  
|`pAppDomain`|<span data-ttu-id="fb42c-109">Zeiger auf den Besitzer des der `ilOffset` Feld.</span><span class="sxs-lookup"><span data-stu-id="fb42c-109">Pointer to the application domain owner of the `ilOffset` field.</span></span>|  
|`pModule`|<span data-ttu-id="fb42c-110">Zeiger auf die modulbesitzer, der die `ilOffset` Feld.</span><span class="sxs-lookup"><span data-stu-id="fb42c-110">Pointer to the module owner of the `ilOffset` field.</span></span>|  
|`pFunction`|<span data-ttu-id="fb42c-111">Zeiger zum Inhaber der Funktion der `ilOffset` Feld.</span><span class="sxs-lookup"><span data-stu-id="fb42c-111">Pointer to the function owner of the `ilOffset` field.</span></span>|  
|`ilOffset`|<span data-ttu-id="fb42c-112">Der Microsoft intermediate Language (MSIL)-Offset des Frames.</span><span class="sxs-lookup"><span data-stu-id="fb42c-112">The Microsoft intermediate language (MSIL) offset of the frame.</span></span>|  
|`flags`|<span data-ttu-id="fb42c-113">Reserviert für zukünftige Erweiterbarkeit.</span><span class="sxs-lookup"><span data-stu-id="fb42c-113">Reserved for future extensibility.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="fb42c-114">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="fb42c-114">Requirements</span></span>  
 <span data-ttu-id="fb42c-115">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="fb42c-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fb42c-116">**Header:** CorDebug.idl</span><span class="sxs-lookup"><span data-stu-id="fb42c-116">**Header:** CorDebug.idl</span></span>  
  
 <span data-ttu-id="fb42c-117">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="fb42c-117">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="fb42c-118">.NET Framework-Versionen:</span><span class="sxs-lookup"><span data-stu-id="fb42c-118">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="fb42c-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="fb42c-119">See also</span></span>

- [<span data-ttu-id="fb42c-120">Debuggen von Strukturen</span><span class="sxs-lookup"><span data-stu-id="fb42c-120">Debugging Structures</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-structures.md)
- [<span data-ttu-id="fb42c-121">Debuggen</span><span class="sxs-lookup"><span data-stu-id="fb42c-121">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
