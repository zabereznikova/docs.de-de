---
title: ICorDebugMutableDataTarget::SetThreadContext Method
ms.date: 03/30/2017
ms.assetid: 8c0d01d5-67e5-4522-9ccf-c8f3a78cb4fd
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: d8b3fd9940bd11c3d026b46247e0657c82b18099
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59120002"
---
# <a name="icordebugmutabledatatargetsetthreadcontext-method"></a><span data-ttu-id="b2cd4-102">ICorDebugMutableDataTarget::SetThreadContext Method</span><span class="sxs-lookup"><span data-stu-id="b2cd4-102">ICorDebugMutableDataTarget::SetThreadContext Method</span></span>
<span data-ttu-id="b2cd4-103">Legt den Kontext (Registerwerte) für einen Thread fest.</span><span class="sxs-lookup"><span data-stu-id="b2cd4-103">Sets the context (register values) for a thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b2cd4-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="b2cd4-104">Syntax</span></span>  
  
```  
HRESULT SetThreadContext(  
   [in] DWORD dwThreadID,  
   [in] ULONG32 contextSize,   [in, size_is(contextSize)] const BYTE * pContext);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b2cd4-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="b2cd4-105">Parameters</span></span>  
 `dwThreadID`  
 <span data-ttu-id="b2cd4-106">[in] Der vom Betriebssystem definierte Threadbezeichner.</span><span class="sxs-lookup"><span data-stu-id="b2cd4-106">[in] The operating system-defined thread identifier.</span></span>  
  
 `contextSize`  
 <span data-ttu-id="b2cd4-107">[in] Die Größe des zu schreibenden `pContext`-Puffers.</span><span class="sxs-lookup"><span data-stu-id="b2cd4-107">[in] The size of the `pContext` buffer to be written.</span></span>  
  
 `pContext`  
 <span data-ttu-id="b2cd4-108">[in] Ein Zeiger auf die zu schreibenden Bytes.</span><span class="sxs-lookup"><span data-stu-id="b2cd4-108">[in] A pointer to the bytes to be written.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b2cd4-109">Hinweise</span><span class="sxs-lookup"><span data-stu-id="b2cd4-109">Remarks</span></span>  
 <span data-ttu-id="b2cd4-110">Die `SetThreadContext`-Methode aktualisiert den aktuellen Kontext für den Thread, der durch das vom Betriebssystem definierte `dwThreadID`-Argument angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="b2cd4-110">The `SetThreadContext` method updates the current context for the thread specified by the operating system-defined `dwThreadID` argument.</span></span> <span data-ttu-id="b2cd4-111">Das Format des Kontextdatensatzes wird von der Plattform erkennbar bestimmt die [ICorDebugDataTarget:: GetPlatform](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget-getplatform-method.md) Methode.</span><span class="sxs-lookup"><span data-stu-id="b2cd4-111">The format of the context record is determined by the platform indicated by the [ICorDebugDataTarget::GetPlatform](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget-getplatform-method.md) method.</span></span> <span data-ttu-id="b2cd4-112">Auf Windows, dies ist eine [Kontext](/windows/desktop/api/winnt/ns-winnt-_arm64_nt_context) Struktur.</span><span class="sxs-lookup"><span data-stu-id="b2cd4-112">On Windows, this is a [CONTEXT](/windows/desktop/api/winnt/ns-winnt-_arm64_nt_context) structure.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b2cd4-113">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="b2cd4-113">Requirements</span></span>  
 <span data-ttu-id="b2cd4-114">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b2cd4-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b2cd4-115">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="b2cd4-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="b2cd4-116">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b2cd4-116">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="b2cd4-117">.NET Framework-Versionen:</span><span class="sxs-lookup"><span data-stu-id="b2cd4-117">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v46plus](../../../../includes/net-current-v46plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="b2cd4-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b2cd4-118">See also</span></span>

- [<span data-ttu-id="b2cd4-119">ICorDebugMutableDataTarget-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="b2cd4-119">ICorDebugMutableDataTarget Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmutabledatatarget-interface.md)
- [<span data-ttu-id="b2cd4-120">Debugschnittstellen</span><span class="sxs-lookup"><span data-stu-id="b2cd4-120">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
