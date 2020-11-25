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
ms.openlocfilehash: c50ba530d78296ebb956329b2f34b4f1e5cae94c
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95727418"
---
# <a name="cor_active_function-structure"></a><span data-ttu-id="be1d5-102">COR_ACTIVE_FUNCTION-Struktur</span><span class="sxs-lookup"><span data-stu-id="be1d5-102">COR_ACTIVE_FUNCTION Structure</span></span>

<span data-ttu-id="be1d5-103">Enthält Informationen zu den Funktionen, die aktuell in den Rahmen eines Threads aktiv sind.</span><span class="sxs-lookup"><span data-stu-id="be1d5-103">Contains information about the functions that are currently active in a thread's frames.</span></span> <span data-ttu-id="be1d5-104">Diese Struktur wird von der [ICorDebugThread2:: GetActiveFunctions](icordebugthread2-getactivefunctions-method.md) -Methode verwendet.</span><span class="sxs-lookup"><span data-stu-id="be1d5-104">This structure is used by the [ICorDebugThread2::GetActiveFunctions](icordebugthread2-getactivefunctions-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="be1d5-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="be1d5-105">Syntax</span></span>  
  
```cpp  
typedef struct  _COR_ACTIVE_FUNCTION {  
    ICorDebugAppDomain   *pAppDomain;  
    ICorDebugModule      *pModule;  
    ICorDebugFunction2   *pFunction;  
    ULONG32              ilOffset;  
    ULONG32              flags;  
} COR_ACTIVE_FUNCTION;  
```  
  
## <a name="members"></a><span data-ttu-id="be1d5-106">Member</span><span class="sxs-lookup"><span data-stu-id="be1d5-106">Members</span></span>  
  
|<span data-ttu-id="be1d5-107">Member</span><span class="sxs-lookup"><span data-stu-id="be1d5-107">Member</span></span>|<span data-ttu-id="be1d5-108">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="be1d5-108">Description</span></span>|  
|------------|-----------------|  
|`pAppDomain`|<span data-ttu-id="be1d5-109">Zeiger auf den Anwendungs Domänen Besitzer des `ilOffset` Felds.</span><span class="sxs-lookup"><span data-stu-id="be1d5-109">Pointer to the application domain owner of the `ilOffset` field.</span></span>|  
|`pModule`|<span data-ttu-id="be1d5-110">Zeiger auf den Modul Besitzer des `ilOffset` Felds.</span><span class="sxs-lookup"><span data-stu-id="be1d5-110">Pointer to the module owner of the `ilOffset` field.</span></span>|  
|`pFunction`|<span data-ttu-id="be1d5-111">Zeiger auf den Funktions Besitzer des `ilOffset` Felds.</span><span class="sxs-lookup"><span data-stu-id="be1d5-111">Pointer to the function owner of the `ilOffset` field.</span></span>|  
|`ilOffset`|<span data-ttu-id="be1d5-112">Der MSIL-Offset (Microsoft Intermediate Language) des Frames.</span><span class="sxs-lookup"><span data-stu-id="be1d5-112">The Microsoft intermediate language (MSIL) offset of the frame.</span></span>|  
|`flags`|<span data-ttu-id="be1d5-113">Reserviert für zukünftige Erweiterbarkeit.</span><span class="sxs-lookup"><span data-stu-id="be1d5-113">Reserved for future extensibility.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="be1d5-114">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="be1d5-114">Requirements</span></span>  

 <span data-ttu-id="be1d5-115">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="be1d5-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="be1d5-116">**Header:** Cordebug. idl</span><span class="sxs-lookup"><span data-stu-id="be1d5-116">**Header:** CorDebug.idl</span></span>  
  
 <span data-ttu-id="be1d5-117">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="be1d5-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="be1d5-118">**.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="be1d5-118">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="be1d5-119">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="be1d5-119">See also</span></span>

- [<span data-ttu-id="be1d5-120">Debuggen von Strukturen</span><span class="sxs-lookup"><span data-stu-id="be1d5-120">Debugging Structures</span></span>](debugging-structures.md)
- [<span data-ttu-id="be1d5-121">Debuggen</span><span class="sxs-lookup"><span data-stu-id="be1d5-121">Debugging</span></span>](index.md)
