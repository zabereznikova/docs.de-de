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
ms.openlocfilehash: f16a5d1bad80a5aad8573508aab5fbf98c8c2a03
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67736836"
---
# <a name="icordebugprocess2setunmanagedbreakpoint-method"></a><span data-ttu-id="82afc-102">ICorDebugProcess2::SetUnmanagedBreakpoint-Method</span><span class="sxs-lookup"><span data-stu-id="82afc-102">ICorDebugProcess2::SetUnmanagedBreakpoint Method</span></span>
<span data-ttu-id="82afc-103">Legt einen nicht verwaltete Haltepunkt am Offset angegebene systemeigene Image fest.</span><span class="sxs-lookup"><span data-stu-id="82afc-103">Sets an unmanaged breakpoint at the specified native image offset.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="82afc-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="82afc-104">Syntax</span></span>  
  
```cpp  
HRESULT SetUnmanagedBreakpoint (  
    [in]  CORDB_ADDRESS    address,  
    [in]  ULONG32          bufsize,  
    [out, size_is(bufsize), length_is(*bufLen)]   
        BYTE               buffer[],  
    [out] ULONG32          *bufLen  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="82afc-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="82afc-105">Parameters</span></span>  
 `address`  
 <span data-ttu-id="82afc-106">[in] Ein `CORDB_ADDRESS` Objekt, das den Offset des systemeigenen Images angibt.</span><span class="sxs-lookup"><span data-stu-id="82afc-106">[in] A `CORDB_ADDRESS` object that specifies the native image offset.</span></span>  
  
 `bufsize`  
 <span data-ttu-id="82afc-107">[in] Die Größe in Bytes, der die `buffer` Array.</span><span class="sxs-lookup"><span data-stu-id="82afc-107">[in] The size, in bytes, of the `buffer` array.</span></span>  
  
 `buffer`  
 <span data-ttu-id="82afc-108">[out] Ein Array, das den Opcode enthält, der durch den Haltepunkt ersetzt wird.</span><span class="sxs-lookup"><span data-stu-id="82afc-108">[out] An array that contains the opcode that is replaced by the breakpoint.</span></span>  
  
 `bufLen`  
 <span data-ttu-id="82afc-109">[out] Ein Zeiger auf die Anzahl der Bytes, die zurückgegeben werden, der `buffer` Array.</span><span class="sxs-lookup"><span data-stu-id="82afc-109">[out] A pointer to the number of bytes returned in the `buffer` array.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="82afc-110">Hinweise</span><span class="sxs-lookup"><span data-stu-id="82afc-110">Remarks</span></span>  
 <span data-ttu-id="82afc-111">Wenn der Offset des systemeigenen Images in der common Language Runtime (CLR) ist, wird der Breakpoint ignoriert.</span><span class="sxs-lookup"><span data-stu-id="82afc-111">If the native image offset is within the common language runtime (CLR), the breakpoint will be ignored.</span></span> <span data-ttu-id="82afc-112">Dadurch wird die CLR, um zu vermeiden, einen Out-of-Band-Haltepunkt, verteilen, wenn der Haltepunkt, durch den Debugger gesetzt ist.</span><span class="sxs-lookup"><span data-stu-id="82afc-112">This allows the CLR to avoid dispatching an out-of-band breakpoint, when the breakpoint is set by the debugger.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="82afc-113">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="82afc-113">Requirements</span></span>  
 <span data-ttu-id="82afc-114">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="82afc-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="82afc-115">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="82afc-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="82afc-116">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="82afc-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="82afc-117">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="82afc-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
