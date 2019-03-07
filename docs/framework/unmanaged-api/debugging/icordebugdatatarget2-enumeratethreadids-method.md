---
title: ICorDebugDataTarget2::EnumerateThreadIDs-Methode
ms.date: 03/30/2017
ms.assetid: af02460f-2a45-496e-bc4e-a1ac4f80fe11
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 1136b01aba5f2143c6d26388568df0b60a5db123
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/06/2019
ms.locfileid: "57492178"
---
# <a name="icordebugdatatarget2enumeratethreadids-method"></a><span data-ttu-id="445f7-102">ICorDebugDataTarget2::EnumerateThreadIDs-Methode</span><span class="sxs-lookup"><span data-stu-id="445f7-102">ICorDebugDataTarget2::EnumerateThreadIDs Method</span></span>
<span data-ttu-id="445f7-103">Gibt eine Liste der aktiven Thread-IDs aus.</span><span class="sxs-lookup"><span data-stu-id="445f7-103">Returns a list of active thread IDs.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="445f7-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="445f7-104">Syntax</span></span>  
  
```  
HRESULT EnumerateThreadIDs(  
    [in] ULONG32 cThreadIds,   
    [out] ULONG32 *pcThreadIds,   
    [out, size_is(cThreadIds), length_is(*pcThreadIds)] ULONG32 pThreadIds[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="445f7-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="445f7-105">Parameters</span></span>  
 <span data-ttu-id="445f7-106">cThreadIDs</span><span class="sxs-lookup"><span data-stu-id="445f7-106">cThreadIDs</span></span>  
 <span data-ttu-id="445f7-107">[in] Die maximale Anzahl der Threads, deren IDs zurückgegeben werden können.</span><span class="sxs-lookup"><span data-stu-id="445f7-107">[in] The maximum number of threads whose IDs can be returned.</span></span>  
  
 <span data-ttu-id="445f7-108">pcThreadIds</span><span class="sxs-lookup"><span data-stu-id="445f7-108">pcThreadIds</span></span>  
 <span data-ttu-id="445f7-109">[out] Ein Zeiger auf ein `ULONG32`, welcher die tatsächliche Anzahl der Thread-IDs angibt, die auf das `pThreadIds`-Array geschrieben wurden.</span><span class="sxs-lookup"><span data-stu-id="445f7-109">[out] A pointer to a `ULONG32` that indicates the actual number of thread IDs written to the `pThreadIds` array.</span></span>  
  
 <span data-ttu-id="445f7-110">pThreadIDs</span><span class="sxs-lookup"><span data-stu-id="445f7-110">pThreadIDs</span></span>  
 <span data-ttu-id="445f7-111">Ein Array an Thread-IDs.</span><span class="sxs-lookup"><span data-stu-id="445f7-111">An array of thread identifiers.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="445f7-112">Hinweise</span><span class="sxs-lookup"><span data-stu-id="445f7-112">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="445f7-113">Diese Methode ist nur mit .NET Native verfügbar.</span><span class="sxs-lookup"><span data-stu-id="445f7-113">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="445f7-114">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="445f7-114">Requirements</span></span>  
 <span data-ttu-id="445f7-115">**Plattformen:** Finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md). **Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="445f7-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="445f7-116">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="445f7-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="445f7-117">**.NET Framework-Versionen:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="445f7-117">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="445f7-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="445f7-118">See also</span></span>
- [<span data-ttu-id="445f7-119">ICorDebugDataTarget2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="445f7-119">ICorDebugDataTarget2 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget2-interface.md)
- [<span data-ttu-id="445f7-120">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="445f7-120">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
