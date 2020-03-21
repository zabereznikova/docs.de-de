---
title: ICorDebugDataTarget2::EnumerateThreadIDs-Methode
ms.date: 03/30/2017
ms.assetid: af02460f-2a45-496e-bc4e-a1ac4f80fe11
ms.openlocfilehash: 120a970aac33b1ab06ae47335a959d2791f893ed
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79178982"
---
# <a name="icordebugdatatarget2enumeratethreadids-method"></a><span data-ttu-id="8e280-102">ICorDebugDataTarget2::EnumerateThreadIDs-Methode</span><span class="sxs-lookup"><span data-stu-id="8e280-102">ICorDebugDataTarget2::EnumerateThreadIDs Method</span></span>
<span data-ttu-id="8e280-103">Gibt eine Liste der aktiven Thread-IDs aus.</span><span class="sxs-lookup"><span data-stu-id="8e280-103">Returns a list of active thread IDs.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8e280-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="8e280-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumerateThreadIDs(  
    [in] ULONG32 cThreadIds,
    [out] ULONG32 *pcThreadIds,
    [out, size_is(cThreadIds), length_is(*pcThreadIds)] ULONG32 pThreadIds[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8e280-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="8e280-105">Parameters</span></span>  
 <span data-ttu-id="8e280-106">cThreadIDs</span><span class="sxs-lookup"><span data-stu-id="8e280-106">cThreadIDs</span></span>  
 <span data-ttu-id="8e280-107">[in] Die maximale Anzahl der Threads, deren IDs zurückgegeben werden können.</span><span class="sxs-lookup"><span data-stu-id="8e280-107">[in] The maximum number of threads whose IDs can be returned.</span></span>  
  
 <span data-ttu-id="8e280-108">pcThreadIds</span><span class="sxs-lookup"><span data-stu-id="8e280-108">pcThreadIds</span></span>  
 <span data-ttu-id="8e280-109">[out] Ein Zeiger auf ein `ULONG32`, welcher die tatsächliche Anzahl der Thread-IDs angibt, die auf das `pThreadIds`-Array geschrieben wurden.</span><span class="sxs-lookup"><span data-stu-id="8e280-109">[out] A pointer to a `ULONG32` that indicates the actual number of thread IDs written to the `pThreadIds` array.</span></span>  
  
 <span data-ttu-id="8e280-110">pThreadIDs</span><span class="sxs-lookup"><span data-stu-id="8e280-110">pThreadIDs</span></span>  
 <span data-ttu-id="8e280-111">Ein Array an Thread-IDs.</span><span class="sxs-lookup"><span data-stu-id="8e280-111">An array of thread identifiers.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8e280-112">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="8e280-112">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="8e280-113">Diese Methode ist nur mit .NET Native verfügbar.</span><span class="sxs-lookup"><span data-stu-id="8e280-113">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8e280-114">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="8e280-114">Requirements</span></span>  
 <span data-ttu-id="8e280-115">**Plattformen:** Siehe [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md). **Kopfzeile:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="8e280-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="8e280-116">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="8e280-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="8e280-117">**.NET Framework-Versionen:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8e280-117">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8e280-118">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="8e280-118">See also</span></span>

- [<span data-ttu-id="8e280-119">ICorDebugDataTarget2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="8e280-119">ICorDebugDataTarget2 Interface</span></span>](icordebugdatatarget2-interface.md)
- [<span data-ttu-id="8e280-120">Debugschnittstellen</span><span class="sxs-lookup"><span data-stu-id="8e280-120">Debugging Interfaces</span></span>](debugging-interfaces.md)
