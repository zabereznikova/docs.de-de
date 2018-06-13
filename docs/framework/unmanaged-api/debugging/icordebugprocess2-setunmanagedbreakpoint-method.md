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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: d4326c6d8a3ee780cf63652badc8c527f55a075c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33420816"
---
# <a name="icordebugprocess2setunmanagedbreakpoint-method"></a><span data-ttu-id="c7423-102">ICorDebugProcess2::SetUnmanagedBreakpoint-Method</span><span class="sxs-lookup"><span data-stu-id="c7423-102">ICorDebugProcess2::SetUnmanagedBreakpoint Method</span></span>
<span data-ttu-id="c7423-103">Legt einen Haltepunkt auf nicht verwalteten Offset angegebene systemeigene Image fest.</span><span class="sxs-lookup"><span data-stu-id="c7423-103">Sets an unmanaged breakpoint at the specified native image offset.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c7423-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="c7423-104">Syntax</span></span>  
  
```  
HRESULT SetUnmanagedBreakpoint (  
    [in]  CORDB_ADDRESS    address,  
    [in]  ULONG32          bufsize,  
    [out, size_is(bufsize), length_is(*bufLen)]   
        BYTE               buffer[],  
    [out] ULONG32          *bufLen  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="c7423-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="c7423-105">Parameters</span></span>  
 `address`  
 <span data-ttu-id="c7423-106">[in] Ein `CORDB_ADDRESS` Objekt, das die systemeigene Images Offset angibt.</span><span class="sxs-lookup"><span data-stu-id="c7423-106">[in] A `CORDB_ADDRESS` object that specifies the native image offset.</span></span>  
  
 `bufsize`  
 <span data-ttu-id="c7423-107">[in] Die Größe in Bytes, der die `buffer` Array.</span><span class="sxs-lookup"><span data-stu-id="c7423-107">[in] The size, in bytes, of the `buffer` array.</span></span>  
  
 `buffer`  
 <span data-ttu-id="c7423-108">[out] Ein Array, das den Opcode enthält, der durch den Haltepunkt ersetzt wird.</span><span class="sxs-lookup"><span data-stu-id="c7423-108">[out] An array that contains the opcode that is replaced by the breakpoint.</span></span>  
  
 `bufLen`  
 <span data-ttu-id="c7423-109">[out] Ein Zeiger auf die Anzahl der Bytes, die zurückgegeben werden, der `buffer` Array.</span><span class="sxs-lookup"><span data-stu-id="c7423-109">[out] A pointer to the number of bytes returned in the `buffer` array.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c7423-110">Hinweise</span><span class="sxs-lookup"><span data-stu-id="c7423-110">Remarks</span></span>  
 <span data-ttu-id="c7423-111">Wenn der systemeigene Images-Offset innerhalb der common Language Runtime (CLR) ist, wird der Breakpoint ignoriert werden.</span><span class="sxs-lookup"><span data-stu-id="c7423-111">If the native image offset is within the common language runtime (CLR), the breakpoint will be ignored.</span></span> <span data-ttu-id="c7423-112">Dadurch wird der von der CLR zu vermeiden, einen Haltepunkt auf Out-of-Band-verteilen, wenn der Haltepunkt vom Debugger festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="c7423-112">This allows the CLR to avoid dispatching an out-of-band breakpoint, when the breakpoint is set by the debugger.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c7423-113">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="c7423-113">Requirements</span></span>  
 <span data-ttu-id="c7423-114">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c7423-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c7423-115">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="c7423-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="c7423-116">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c7423-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c7423-117">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c7423-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
