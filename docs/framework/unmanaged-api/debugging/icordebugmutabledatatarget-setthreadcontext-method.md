---
title: ICorDebugMutableDataTarget::SetThreadContext Method
ms.date: 03/30/2017
ms.assetid: 8c0d01d5-67e5-4522-9ccf-c8f3a78cb4fd
ms.openlocfilehash: a6df6bf030ad339f5d02b95cd191b30db60aa167
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/12/2020
ms.locfileid: "83210149"
---
# <a name="icordebugmutabledatatargetsetthreadcontext-method"></a><span data-ttu-id="e5f89-102">ICorDebugMutableDataTarget::SetThreadContext Method</span><span class="sxs-lookup"><span data-stu-id="e5f89-102">ICorDebugMutableDataTarget::SetThreadContext Method</span></span>
<span data-ttu-id="e5f89-103">Legt den Kontext (Registerwerte) für einen Thread fest.</span><span class="sxs-lookup"><span data-stu-id="e5f89-103">Sets the context (register values) for a thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e5f89-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="e5f89-104">Syntax</span></span>  
  
```cpp  
HRESULT SetThreadContext(  
   [in] DWORD dwThreadID,  
   [in] ULONG32 contextSize,   [in, size_is(contextSize)] const BYTE * pContext);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e5f89-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="e5f89-105">Parameters</span></span>  
 `dwThreadID`  
 <span data-ttu-id="e5f89-106">[in] Der vom Betriebssystem definierte Threadbezeichner.</span><span class="sxs-lookup"><span data-stu-id="e5f89-106">[in] The operating system-defined thread identifier.</span></span>  
  
 `contextSize`  
 <span data-ttu-id="e5f89-107">[in] Die Größe des zu schreibenden `pContext`-Puffers.</span><span class="sxs-lookup"><span data-stu-id="e5f89-107">[in] The size of the `pContext` buffer to be written.</span></span>  
  
 `pContext`  
 <span data-ttu-id="e5f89-108">[in] Ein Zeiger auf die zu schreibenden Bytes.</span><span class="sxs-lookup"><span data-stu-id="e5f89-108">[in] A pointer to the bytes to be written.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e5f89-109">Hinweise</span><span class="sxs-lookup"><span data-stu-id="e5f89-109">Remarks</span></span>  
 <span data-ttu-id="e5f89-110">Die `SetThreadContext`-Methode aktualisiert den aktuellen Kontext für den Thread, der durch das vom Betriebssystem definierte `dwThreadID`-Argument angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="e5f89-110">The `SetThreadContext` method updates the current context for the thread specified by the operating system-defined `dwThreadID` argument.</span></span> <span data-ttu-id="e5f89-111">Das Format des Kontext Datensatzes wird von der durch die [ICorDebugDataTarget:: GetPlatform](icordebugdatatarget-getplatform-method.md) -Methode festgelegten Plattform bestimmt.</span><span class="sxs-lookup"><span data-stu-id="e5f89-111">The format of the context record is determined by the platform indicated by the [ICorDebugDataTarget::GetPlatform](icordebugdatatarget-getplatform-method.md) method.</span></span> <span data-ttu-id="e5f89-112">Unter Windows handelt es sich hierbei um eine [Kontext](/windows/win32/api/winnt/ns-winnt-arm64_nt_context) Struktur.</span><span class="sxs-lookup"><span data-stu-id="e5f89-112">On Windows, this is a [CONTEXT](/windows/win32/api/winnt/ns-winnt-arm64_nt_context) structure.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e5f89-113">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="e5f89-113">Requirements</span></span>  
 <span data-ttu-id="e5f89-114">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e5f89-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e5f89-115">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="e5f89-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="e5f89-116">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e5f89-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e5f89-117">**.NET Framework Versionen:**[!INCLUDE[net_current_v46plus](../../../../includes/net-current-v46plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e5f89-117">**.NET Framework Versions:** [!INCLUDE[net_current_v46plus](../../../../includes/net-current-v46plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e5f89-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e5f89-118">See also</span></span>

- [<span data-ttu-id="e5f89-119">ICorDebugMutableDataTarget-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="e5f89-119">ICorDebugMutableDataTarget Interface</span></span>](icordebugmutabledatatarget-interface.md)
- [<span data-ttu-id="e5f89-120">Debugschnittstellen</span><span class="sxs-lookup"><span data-stu-id="e5f89-120">Debugging Interfaces</span></span>](debugging-interfaces.md)
