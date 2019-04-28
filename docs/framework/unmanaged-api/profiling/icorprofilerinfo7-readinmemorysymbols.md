---
title: ICorProfilerInfo7::ReadInMemorySymbols
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo7.ReadInMemorySymbols
api_location:
- CorProf.idl
- CorProf.h
- CorGuids.lib
api_type:
- COM
ms.assetid: 1745a0b9-8332-4777-a670-b549bff3b901
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 662863ec69e464dafe893552f1d81755313acc75
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61786210"
---
# <a name="icorprofilerinfo7readinmemorysymbols"></a><span data-ttu-id="73874-102">ICorProfilerInfo7::ReadInMemorySymbols</span><span class="sxs-lookup"><span data-stu-id="73874-102">ICorProfilerInfo7::ReadInMemorySymbols</span></span>
<span data-ttu-id="73874-103">[Unterstützt in [!INCLUDE[net_v461](../../../../includes/net-v461-md.md)] und höheren Versionen]</span><span class="sxs-lookup"><span data-stu-id="73874-103">[Supported in the [!INCLUDE[net_v461](../../../../includes/net-v461-md.md)] and later versions]</span></span>  
  
 <span data-ttu-id="73874-104">Liest Bytes aus einem in-Memory symbolstream.</span><span class="sxs-lookup"><span data-stu-id="73874-104">Reads bytes from an in-memory symbol stream.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="73874-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="73874-105">Syntax</span></span>  
  
```  
HRESULT ReadInMemorySymbols(  
        [in] ModuleID moduleId,  
        [in] DWORD symbolsReadOffset,  
        [out] BYTE* pSymbolBytes,  
        [in] DWORD countSymbolBytes,  
        [out] DWORD* pCountSymbolBytesRead  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="73874-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="73874-106">Parameters</span></span>  
 `moduleId`  
 <span data-ttu-id="73874-107">[in] Der Bezeichner des Moduls mit den in-Memory-Datenstrom.</span><span class="sxs-lookup"><span data-stu-id="73874-107">[in] The identifier of the module containing the in-memory stream.</span></span>  
  
 `symbolsReadOffset`  
 <span data-ttu-id="73874-108">[in] Der Offset in den Datenstrom im Arbeitsspeicher, an dem mit dem Lesen von Bytes begonnen werden soll.</span><span class="sxs-lookup"><span data-stu-id="73874-108">[in] The offset within the in-memory stream at which to start reading bytes.</span></span>  
  
 `pSymbolBytes`  
 <span data-ttu-id="73874-109">[out] Ein Zeiger auf den Puffer, den die Daten kopiert werden.</span><span class="sxs-lookup"><span data-stu-id="73874-109">[out] A pointer to the buffer to which the data will be copied.</span></span> <span data-ttu-id="73874-110">Der Puffer müssen `countSymbolBytes` des verfügbaren Speicherplatzes.</span><span class="sxs-lookup"><span data-stu-id="73874-110">The buffer should have `countSymbolBytes` of space available.</span></span>  
  
 `countSymbolBytes`  
 <span data-ttu-id="73874-111">[in] Die Anzahl der zu kopierenden Bytes an.</span><span class="sxs-lookup"><span data-stu-id="73874-111">[in] The number of bytes to copy.</span></span>  
  
 `pCountSymbolBytesRead`  
 <span data-ttu-id="73874-112">[out] Wenn die Methode zurückgibt, enthält die tatsächliche Anzahl der gelesenen Bytes.</span><span class="sxs-lookup"><span data-stu-id="73874-112">[out] When the method returns, contains the actual number of bytes read.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="73874-113">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="73874-113">Return Value</span></span>  
 <span data-ttu-id="73874-114">`S_OK`, wenn eine gewisse Anzahl von Bytes gelesen wurden.</span><span class="sxs-lookup"><span data-stu-id="73874-114">`S_OK`, if a non-zero number of bytes were read.</span></span>  
  
 <span data-ttu-id="73874-115">`CORPROF_E_MODULE_IS_DYNAMIC`, wenn es sich bei der Erstellung des Moduls mit <xref:System.Reflection.Emit>.</span><span class="sxs-lookup"><span data-stu-id="73874-115">`CORPROF_E_MODULE_IS_DYNAMIC`, if the module was created using <xref:System.Reflection.Emit>.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="73874-116">Hinweise</span><span class="sxs-lookup"><span data-stu-id="73874-116">Remarks</span></span>  
 <span data-ttu-id="73874-117">Die `ReadInMemorySymbols` Methode versucht, lesen Sie `countSymbolBytes` von Daten, die beginnend am Offset `symbolsReadOffset` im in-Memory-Stream.</span><span class="sxs-lookup"><span data-stu-id="73874-117">The `ReadInMemorySymbols` method attempts to read `countSymbolBytes` of data starting at offset      `symbolsReadOffset` within the in-memory stream.</span></span> <span data-ttu-id="73874-118">Die Daten werden kopiert, um `pSymbolBytes`, das wird erwartet, damit `countSymbolBytes` des verfügbaren Speicherplatzes.</span><span class="sxs-lookup"><span data-stu-id="73874-118">The data is copied to `pSymbolBytes`, which is expected to have `countSymbolBytes` of space available.</span></span>     <span data-ttu-id="73874-119">`pCountSymbolsBytesRead` enthält die tatsächliche Anzahl der gelesenen Bytes an, die möglicherweise kleiner als `countSymbolBytes` , wenn das Ende des Streams erreicht ist.</span><span class="sxs-lookup"><span data-stu-id="73874-119">`pCountSymbolsBytesRead` contains the actual number of bytes read, which may be less than `countSymbolBytes` if the end of the stream is reached.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="73874-120">Die aktuelle Implementierung unterstützt keine Reflection.Emit.</span><span class="sxs-lookup"><span data-stu-id="73874-120">The current implementation does not support Reflection.Emit.</span></span> <span data-ttu-id="73874-121">Wenn das Modul mithilfe von "Reflection.Emit" erstellt wurde, gibt die Methode `CORPROF_E_MODULE_IS_DYNAMIC`.</span><span class="sxs-lookup"><span data-stu-id="73874-121">If the module was created by using Reflection.Emit, the method returns `CORPROF_E_MODULE_IS_DYNAMIC`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="73874-122">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="73874-122">Requirements</span></span>  
 <span data-ttu-id="73874-123">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="73874-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="73874-124">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="73874-124">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="73874-125">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="73874-125">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="73874-126">**.NET Framework-Versionen:** [!INCLUDE[net_current_v461plus](../../../../includes/net-current-v461plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="73874-126">**.NET Framework Versions:** [!INCLUDE[net_current_v461plus](../../../../includes/net-current-v461plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="73874-127">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="73874-127">See also</span></span>

- [<span data-ttu-id="73874-128">ICorProfilerInfo7-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="73874-128">ICorProfilerInfo7 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo7-interface.md)
