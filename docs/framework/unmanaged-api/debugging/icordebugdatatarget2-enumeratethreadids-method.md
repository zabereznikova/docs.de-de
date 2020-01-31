---
title: ICorDebugDataTarget2::EnumerateThreadIDs-Methode
ms.date: 03/30/2017
ms.assetid: af02460f-2a45-496e-bc4e-a1ac4f80fe11
ms.openlocfilehash: 74d4905f2b386f8e0345e4300dd2c8c6d0c882ea
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/28/2020
ms.locfileid: "76783640"
---
# <a name="icordebugdatatarget2enumeratethreadids-method"></a><span data-ttu-id="0fb53-102">ICorDebugDataTarget2::EnumerateThreadIDs-Methode</span><span class="sxs-lookup"><span data-stu-id="0fb53-102">ICorDebugDataTarget2::EnumerateThreadIDs Method</span></span>
<span data-ttu-id="0fb53-103">Gibt eine Liste der aktiven Thread-IDs aus.</span><span class="sxs-lookup"><span data-stu-id="0fb53-103">Returns a list of active thread IDs.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0fb53-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="0fb53-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumerateThreadIDs(  
    [in] ULONG32 cThreadIds,   
    [out] ULONG32 *pcThreadIds,   
    [out, size_is(cThreadIds), length_is(*pcThreadIds)] ULONG32 pThreadIds[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0fb53-105">Parameters</span><span class="sxs-lookup"><span data-stu-id="0fb53-105">Parameters</span></span>  
 <span data-ttu-id="0fb53-106">cThreadIDs</span><span class="sxs-lookup"><span data-stu-id="0fb53-106">cThreadIDs</span></span>  
 <span data-ttu-id="0fb53-107">[in] Die maximale Anzahl der Threads, deren IDs zurückgegeben werden können.</span><span class="sxs-lookup"><span data-stu-id="0fb53-107">[in] The maximum number of threads whose IDs can be returned.</span></span>  
  
 <span data-ttu-id="0fb53-108">pcThreadIds</span><span class="sxs-lookup"><span data-stu-id="0fb53-108">pcThreadIds</span></span>  
 <span data-ttu-id="0fb53-109">[out] Ein Zeiger auf ein `ULONG32`, welcher die tatsächliche Anzahl der Thread-IDs angibt, die auf das `pThreadIds`-Array geschrieben wurden.</span><span class="sxs-lookup"><span data-stu-id="0fb53-109">[out] A pointer to a `ULONG32` that indicates the actual number of thread IDs written to the `pThreadIds` array.</span></span>  
  
 <span data-ttu-id="0fb53-110">pThreadIDs</span><span class="sxs-lookup"><span data-stu-id="0fb53-110">pThreadIDs</span></span>  
 <span data-ttu-id="0fb53-111">Ein Array an Thread-IDs.</span><span class="sxs-lookup"><span data-stu-id="0fb53-111">An array of thread identifiers.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="0fb53-112">Hinweise</span><span class="sxs-lookup"><span data-stu-id="0fb53-112">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="0fb53-113">Diese Methode ist nur mit .NET Native verfügbar.</span><span class="sxs-lookup"><span data-stu-id="0fb53-113">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0fb53-114">-Anforderungen</span><span class="sxs-lookup"><span data-stu-id="0fb53-114">Requirements</span></span>  
 <span data-ttu-id="0fb53-115">**Plattformen:** Siehe [System Anforderungen](../../../../docs/framework/get-started/system-requirements.md). **Header:** Cordebug. idl, Cordebug. h</span><span class="sxs-lookup"><span data-stu-id="0fb53-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="0fb53-116">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="0fb53-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="0fb53-117">**.NET Framework Versionen:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0fb53-117">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0fb53-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="0fb53-118">See also</span></span>

- [<span data-ttu-id="0fb53-119">ICorDebugDataTarget2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="0fb53-119">ICorDebugDataTarget2 Interface</span></span>](icordebugdatatarget2-interface.md)
- [<span data-ttu-id="0fb53-120">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="0fb53-120">Debugging Interfaces</span></span>](debugging-interfaces.md)
