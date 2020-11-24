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
ms.openlocfilehash: 1a883878107569145b97d5793f0628efefb13545
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95675242"
---
# <a name="icordebugprocess2setunmanagedbreakpoint-method"></a><span data-ttu-id="c4136-102">ICorDebugProcess2::SetUnmanagedBreakpoint-Method</span><span class="sxs-lookup"><span data-stu-id="c4136-102">ICorDebugProcess2::SetUnmanagedBreakpoint Method</span></span>

<span data-ttu-id="c4136-103">Legt einen nicht verwalteten Haltepunkt am angegebenen systemeigenen Abbild Offset fest.</span><span class="sxs-lookup"><span data-stu-id="c4136-103">Sets an unmanaged breakpoint at the specified native image offset.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c4136-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="c4136-104">Syntax</span></span>  
  
```cpp  
HRESULT SetUnmanagedBreakpoint (  
    [in]  CORDB_ADDRESS    address,  
    [in]  ULONG32          bufsize,  
    [out, size_is(bufsize), length_is(*bufLen)]
        BYTE               buffer[],  
    [out] ULONG32          *bufLen  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c4136-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="c4136-105">Parameters</span></span>  

 `address`  
 <span data-ttu-id="c4136-106">in Ein- `CORDB_ADDRESS` Objekt, das den Offset des systemeigenen Bilds angibt.</span><span class="sxs-lookup"><span data-stu-id="c4136-106">[in] A `CORDB_ADDRESS` object that specifies the native image offset.</span></span>  
  
 `bufsize`  
 <span data-ttu-id="c4136-107">in Die Größe des Arrays in Bytes `buffer` .</span><span class="sxs-lookup"><span data-stu-id="c4136-107">[in] The size, in bytes, of the `buffer` array.</span></span>  
  
 `buffer`  
 <span data-ttu-id="c4136-108">vorgenommen Ein Array, das den Opcode enthält, der durch den Breakpoint ersetzt wird.</span><span class="sxs-lookup"><span data-stu-id="c4136-108">[out] An array that contains the opcode that is replaced by the breakpoint.</span></span>  
  
 `bufLen`  
 <span data-ttu-id="c4136-109">vorgenommen Ein Zeiger auf die Anzahl der im Array zurückgegebenen Bytes `buffer` .</span><span class="sxs-lookup"><span data-stu-id="c4136-109">[out] A pointer to the number of bytes returned in the `buffer` array.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c4136-110">Hinweise</span><span class="sxs-lookup"><span data-stu-id="c4136-110">Remarks</span></span>  

 <span data-ttu-id="c4136-111">Wenn der Offset des systemeigenen Images innerhalb des Common Language Runtime (CLR) liegt, wird der Breakpoint ignoriert.</span><span class="sxs-lookup"><span data-stu-id="c4136-111">If the native image offset is within the common language runtime (CLR), the breakpoint will be ignored.</span></span> <span data-ttu-id="c4136-112">Dadurch kann die CLR vermeiden, dass ein Out-of-Band-Haltepunkt versendet wird, wenn der Breakpoint vom Debugger festgelegt wird.</span><span class="sxs-lookup"><span data-stu-id="c4136-112">This allows the CLR to avoid dispatching an out-of-band breakpoint, when the breakpoint is set by the debugger.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c4136-113">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="c4136-113">Requirements</span></span>  

 <span data-ttu-id="c4136-114">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c4136-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c4136-115">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="c4136-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="c4136-116">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c4136-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c4136-117">**.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c4136-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
