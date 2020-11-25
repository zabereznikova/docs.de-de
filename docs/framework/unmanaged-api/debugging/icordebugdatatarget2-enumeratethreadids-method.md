---
title: ICorDebugDataTarget2::EnumerateThreadIDs-Methode
ms.date: 03/30/2017
ms.assetid: af02460f-2a45-496e-bc4e-a1ac4f80fe11
ms.openlocfilehash: 31a839076b34901ae1a8f3b43021f64f77629fc0
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95713846"
---
# <a name="icordebugdatatarget2enumeratethreadids-method"></a><span data-ttu-id="f98ca-102">ICorDebugDataTarget2::EnumerateThreadIDs-Methode</span><span class="sxs-lookup"><span data-stu-id="f98ca-102">ICorDebugDataTarget2::EnumerateThreadIDs Method</span></span>

<span data-ttu-id="f98ca-103">Gibt eine Liste der aktiven Thread-IDs aus.</span><span class="sxs-lookup"><span data-stu-id="f98ca-103">Returns a list of active thread IDs.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f98ca-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="f98ca-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumerateThreadIDs(  
    [in] ULONG32 cThreadIds,
    [out] ULONG32 *pcThreadIds,
    [out, size_is(cThreadIds), length_is(*pcThreadIds)] ULONG32 pThreadIds[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f98ca-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="f98ca-105">Parameters</span></span>  

 <span data-ttu-id="f98ca-106">cThreadIDs</span><span class="sxs-lookup"><span data-stu-id="f98ca-106">cThreadIDs</span></span>  
 <span data-ttu-id="f98ca-107">[in] Die maximale Anzahl der Threads, deren IDs zurückgegeben werden können.</span><span class="sxs-lookup"><span data-stu-id="f98ca-107">[in] The maximum number of threads whose IDs can be returned.</span></span>  
  
 <span data-ttu-id="f98ca-108">pcThreadIds</span><span class="sxs-lookup"><span data-stu-id="f98ca-108">pcThreadIds</span></span>  
 <span data-ttu-id="f98ca-109">[out] Ein Zeiger auf ein `ULONG32`, welcher die tatsächliche Anzahl der Thread-IDs angibt, die auf das `pThreadIds`-Array geschrieben wurden.</span><span class="sxs-lookup"><span data-stu-id="f98ca-109">[out] A pointer to a `ULONG32` that indicates the actual number of thread IDs written to the `pThreadIds` array.</span></span>  
  
 <span data-ttu-id="f98ca-110">pThreadIDs</span><span class="sxs-lookup"><span data-stu-id="f98ca-110">pThreadIDs</span></span>  
 <span data-ttu-id="f98ca-111">Ein Array an Thread-IDs.</span><span class="sxs-lookup"><span data-stu-id="f98ca-111">An array of thread identifiers.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f98ca-112">Hinweise</span><span class="sxs-lookup"><span data-stu-id="f98ca-112">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="f98ca-113">Diese Methode ist nur mit .NET Native verfügbar.</span><span class="sxs-lookup"><span data-stu-id="f98ca-113">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f98ca-114">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="f98ca-114">Requirements</span></span>  

 <span data-ttu-id="f98ca-115">**Plattformen:** Siehe [System Anforderungen](../../get-started/system-requirements.md). **Header:** Cordebug. idl, Cordebug. h</span><span class="sxs-lookup"><span data-stu-id="f98ca-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="f98ca-116">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f98ca-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f98ca-117">**.NET Framework Versionen:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f98ca-117">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f98ca-118">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="f98ca-118">See also</span></span>

- [<span data-ttu-id="f98ca-119">ICorDebugDataTarget2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="f98ca-119">ICorDebugDataTarget2 Interface</span></span>](icordebugdatatarget2-interface.md)
- [<span data-ttu-id="f98ca-120">Debugschnittstellen</span><span class="sxs-lookup"><span data-stu-id="f98ca-120">Debugging Interfaces</span></span>](debugging-interfaces.md)
