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
ms.openlocfilehash: 95b463b23c230d620d746e48da49d75238ef2cb7
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69955377"
---
# <a name="icorprofilerinfo7readinmemorysymbols"></a><span data-ttu-id="051e9-102">ICorProfilerInfo7::ReadInMemorySymbols</span><span class="sxs-lookup"><span data-stu-id="051e9-102">ICorProfilerInfo7::ReadInMemorySymbols</span></span>
<span data-ttu-id="051e9-103">[Wird nur in .NET Framework 4.6.1 und höheren Versionen unterstützt]</span><span class="sxs-lookup"><span data-stu-id="051e9-103">[Supported in the .NET Framework 4.6.1 and later versions]</span></span>  
  
 <span data-ttu-id="051e9-104">Liest Bytes aus einem in-Memory-symbolstream.</span><span class="sxs-lookup"><span data-stu-id="051e9-104">Reads bytes from an in-memory symbol stream.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="051e9-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="051e9-105">Syntax</span></span>  
  
```cpp  
HRESULT ReadInMemorySymbols(  
        [in] ModuleID moduleId,  
        [in] DWORD symbolsReadOffset,  
        [out] BYTE* pSymbolBytes,  
        [in] DWORD countSymbolBytes,  
        [out] DWORD* pCountSymbolBytesRead  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="051e9-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="051e9-106">Parameters</span></span>  
 `moduleId`  
 <span data-ttu-id="051e9-107">in Der Bezeichner des Moduls, das den in-Memory-Datenstrom enthält.</span><span class="sxs-lookup"><span data-stu-id="051e9-107">[in] The identifier of the module containing the in-memory stream.</span></span>  
  
 `symbolsReadOffset`  
 <span data-ttu-id="051e9-108">in Der Offset innerhalb des in-Memory-Streams, an dem mit dem Lesen von Bytes begonnen werden soll.</span><span class="sxs-lookup"><span data-stu-id="051e9-108">[in] The offset within the in-memory stream at which to start reading bytes.</span></span>  
  
 `pSymbolBytes`  
 <span data-ttu-id="051e9-109">vorgenommen Ein Zeiger auf den Puffer, in den die Daten kopiert werden.</span><span class="sxs-lookup"><span data-stu-id="051e9-109">[out] A pointer to the buffer to which the data will be copied.</span></span> <span data-ttu-id="051e9-110">Für den Puffer muss `countSymbolBytes` Speicherplatz verfügbar sein.</span><span class="sxs-lookup"><span data-stu-id="051e9-110">The buffer should have `countSymbolBytes` of space available.</span></span>  
  
 `countSymbolBytes`  
 <span data-ttu-id="051e9-111">in Die Anzahl der zu kopierenden Bytes.</span><span class="sxs-lookup"><span data-stu-id="051e9-111">[in] The number of bytes to copy.</span></span>  
  
 `pCountSymbolBytesRead`  
 <span data-ttu-id="051e9-112">vorgenommen Diese Methode gibt die tatsächliche Anzahl von gelesenen Bytes zurück.</span><span class="sxs-lookup"><span data-stu-id="051e9-112">[out] When the method returns, contains the actual number of bytes read.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="051e9-113">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="051e9-113">Return Value</span></span>  
 <span data-ttu-id="051e9-114">`S_OK`, wenn eine Anzahl von Bytes ungleich 0 (null) gelesen wurde.</span><span class="sxs-lookup"><span data-stu-id="051e9-114">`S_OK`, if a non-zero number of bytes were read.</span></span>  
  
 <span data-ttu-id="051e9-115">`CORPROF_E_MODULE_IS_DYNAMIC`, wenn das Modul mithilfe <xref:System.Reflection.Emit>von erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="051e9-115">`CORPROF_E_MODULE_IS_DYNAMIC`, if the module was created using <xref:System.Reflection.Emit>.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="051e9-116">Hinweise</span><span class="sxs-lookup"><span data-stu-id="051e9-116">Remarks</span></span>  
 <span data-ttu-id="051e9-117">Die `ReadInMemorySymbols` -Methode versucht, `countSymbolBytes` die Daten zu lesen, `symbolsReadOffset` beginnend beim Offset innerhalb des in-Memory-Streams.</span><span class="sxs-lookup"><span data-stu-id="051e9-117">The `ReadInMemorySymbols` method attempts to read `countSymbolBytes` of data starting at offset      `symbolsReadOffset` within the in-memory stream.</span></span> <span data-ttu-id="051e9-118">Die Daten werden in `pSymbolBytes`kopiert, und es wird erwartet `countSymbolBytes` , dass genügend Speicherplatz verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="051e9-118">The data is copied to `pSymbolBytes`, which is expected to have `countSymbolBytes` of space available.</span></span>     <span data-ttu-id="051e9-119">`pCountSymbolsBytesRead`enthält die tatsächliche Anzahl von gelesenen Bytes, die kleiner als `countSymbolBytes` sein kann, wenn das Ende des Streams erreicht ist.</span><span class="sxs-lookup"><span data-stu-id="051e9-119">`pCountSymbolsBytesRead` contains the actual number of bytes read, which may be less than `countSymbolBytes` if the end of the stream is reached.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="051e9-120">Die aktuelle Implementierung unterstützt Reflektion. ausgeben nicht.</span><span class="sxs-lookup"><span data-stu-id="051e9-120">The current implementation does not support Reflection.Emit.</span></span> <span data-ttu-id="051e9-121">Wenn das Modul mithilfe von Reflection. ausgeben erstellt wurde, gibt die Methode `CORPROF_E_MODULE_IS_DYNAMIC`zurück.</span><span class="sxs-lookup"><span data-stu-id="051e9-121">If the module was created by using Reflection.Emit, the method returns `CORPROF_E_MODULE_IS_DYNAMIC`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="051e9-122">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="051e9-122">Requirements</span></span>  
 <span data-ttu-id="051e9-123">**Formen** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="051e9-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="051e9-124">**Header:** Corprof. idl, Corprof. h</span><span class="sxs-lookup"><span data-stu-id="051e9-124">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="051e9-125">**Fern** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="051e9-125">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="051e9-126">**.NET Framework-Versionen:** [!INCLUDE[net_current_v461plus](../../../../includes/net-current-v461plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="051e9-126">**.NET Framework Versions:** [!INCLUDE[net_current_v461plus](../../../../includes/net-current-v461plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="051e9-127">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="051e9-127">See also</span></span>

- [<span data-ttu-id="051e9-128">ICorProfilerInfo7-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="051e9-128">ICorProfilerInfo7 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo7-interface.md)
