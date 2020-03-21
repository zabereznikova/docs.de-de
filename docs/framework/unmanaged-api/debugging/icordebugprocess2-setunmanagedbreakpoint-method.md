---
title: ICorDebugProcess2::SetUnmanagedBreakpoint-Method
ms.date: 03/30/2017
api_name:
- ICorDebugProcess2.SetUnmanagedBreakpoint
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess2::SetUnmanagedBreakpoint
helpviewer_keywords:
- ICorDebugProcess2::SetUnmanagedBreakpoint method [.NET Framework debugging]
- SetUnmanagedBreakpoint method [.NET Framework debugging]
ms.assetid: 93829d15-d942-4e2d-b7a4-dfc9d7fb96be
topic_type:
- apiref
ms.openlocfilehash: fb8b8f3e29c141e91587a4d0cdc81cdabccdbc9e
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79178646"
---
# <a name="icordebugprocess2setunmanagedbreakpoint-method"></a><span data-ttu-id="49f7e-102">ICorDebugProcess2::SetUnmanagedBreakpoint-Method</span><span class="sxs-lookup"><span data-stu-id="49f7e-102">ICorDebugProcess2::SetUnmanagedBreakpoint Method</span></span>
<span data-ttu-id="49f7e-103">Legt einen nicht verwalteten Haltepunkt am angegebenen systemeigenen Bildversatz fest.</span><span class="sxs-lookup"><span data-stu-id="49f7e-103">Sets an unmanaged breakpoint at the specified native image offset.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="49f7e-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="49f7e-104">Syntax</span></span>  
  
```cpp  
HRESULT SetUnmanagedBreakpoint (  
    [in]  CORDB_ADDRESS    address,  
    [in]  ULONG32          bufsize,  
    [out, size_is(bufsize), length_is(*bufLen)]
        BYTE               buffer[],  
    [out] ULONG32          *bufLen  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="49f7e-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="49f7e-105">Parameters</span></span>  
 `address`  
 <span data-ttu-id="49f7e-106">[in] Ein `CORDB_ADDRESS` Objekt, das den systemeigenen Bildversatz angibt.</span><span class="sxs-lookup"><span data-stu-id="49f7e-106">[in] A `CORDB_ADDRESS` object that specifies the native image offset.</span></span>  
  
 `bufsize`  
 <span data-ttu-id="49f7e-107">[in] Die Größe des `buffer` Arrays in Bytes.</span><span class="sxs-lookup"><span data-stu-id="49f7e-107">[in] The size, in bytes, of the `buffer` array.</span></span>  
  
 `buffer`  
 <span data-ttu-id="49f7e-108">[out] Ein Array, das den Opcode enthält, der durch den Haltepunkt ersetzt wird.</span><span class="sxs-lookup"><span data-stu-id="49f7e-108">[out] An array that contains the opcode that is replaced by the breakpoint.</span></span>  
  
 `bufLen`  
 <span data-ttu-id="49f7e-109">[out] Ein Zeiger auf die Anzahl der `buffer` im Array zurückgegebenen Bytes.</span><span class="sxs-lookup"><span data-stu-id="49f7e-109">[out] A pointer to the number of bytes returned in the `buffer` array.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="49f7e-110">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="49f7e-110">Remarks</span></span>  
 <span data-ttu-id="49f7e-111">Wenn sich der native Bildversatz innerhalb der Common Language Runtime (CLR) befindet, wird der Haltepunkt ignoriert.</span><span class="sxs-lookup"><span data-stu-id="49f7e-111">If the native image offset is within the common language runtime (CLR), the breakpoint will be ignored.</span></span> <span data-ttu-id="49f7e-112">Dadurch kann die CLR das Aussenden eines Out-of-Band-Haltepunkts vermeiden, wenn der Haltepunkt vom Debugger festgelegt wird.</span><span class="sxs-lookup"><span data-stu-id="49f7e-112">This allows the CLR to avoid dispatching an out-of-band breakpoint, when the breakpoint is set by the debugger.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="49f7e-113">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="49f7e-113">Requirements</span></span>  
 <span data-ttu-id="49f7e-114">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="49f7e-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="49f7e-115">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="49f7e-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="49f7e-116">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="49f7e-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="49f7e-117">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="49f7e-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
