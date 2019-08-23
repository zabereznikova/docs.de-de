---
title: 'ICorProfilerInfo7:: getinmemorysymbolslength-Methode'
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo7.GetInMemorySymbolsLength
api_location:
- mscorwks.dll
- icorprof.idl
api_type:
- COM
ms.assetid: d62c4a4c-8a62-45aa-8f01-a8387cf36159
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 157b0e215f8afa58cccb3d54a65baa9c307ba966
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69955427"
---
# <a name="icorprofilerinfo7getinmemorysymbolslength-method"></a><span data-ttu-id="35d3a-102">ICorProfilerInfo7:: getinmemorysymbolslength-Methode</span><span class="sxs-lookup"><span data-stu-id="35d3a-102">ICorProfilerInfo7::GetInMemorySymbolsLength Method</span></span>
<span data-ttu-id="35d3a-103">[Wird nur in .NET Framework 4.6.1 und höheren Versionen unterstützt]</span><span class="sxs-lookup"><span data-stu-id="35d3a-103">[Supported in the .NET Framework 4.6.1 and later versions]</span></span>  
  
 <span data-ttu-id="35d3a-104">Gibt die Länge eines in-Memory-Symbol Datenstroms zurück.</span><span class="sxs-lookup"><span data-stu-id="35d3a-104">Returns the length of an in-memory symbol stream.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="35d3a-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="35d3a-105">Syntax</span></span>  
  
```cpp  
HRESULT GetInMemorySymbolsLength(  
        [in] ModuleID moduleId,  
        [out] DWORD* pCountSymbolBytes  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="35d3a-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="35d3a-106">Parameters</span></span>  
 `moduleId`  
 <span data-ttu-id="35d3a-107">in Der Bezeichner des Moduls, das den in-Memory-Datenstrom enthält.</span><span class="sxs-lookup"><span data-stu-id="35d3a-107">[in] The identifier of the module containing the in-memory stream.</span></span>  
  
 <span data-ttu-id="35d3a-108">pCountSymbolBytes</span><span class="sxs-lookup"><span data-stu-id="35d3a-108">pCountSymbolBytes</span></span>  
 <span data-ttu-id="35d3a-109">vorgenommen Ein Zeiger auf einen `DWORD` Wert, der bei Rückgabe der Methode die Länge des Streams in Bytes enthält.</span><span class="sxs-lookup"><span data-stu-id="35d3a-109">[out] A pointer to a `DWORD` value that, when the method returns, contains the length of the stream in bytes.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="35d3a-110">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="35d3a-110">Return Value</span></span>  
 <span data-ttu-id="35d3a-111">Die-Methode `S_OK` gibt zurück, wenn die Länge des Speicherdaten Stroms bestimmt werden kann, auch wenn Sie 0 (null) ist.</span><span class="sxs-lookup"><span data-stu-id="35d3a-111">The method returns `S_OK` if the length of the memory stream can be determined, even if it is zero (0).</span></span>  
  
 <span data-ttu-id="35d3a-112">Die Methode gibt `CORPROF_E_MODULE_IS_DYNAMIC` zurück, wenn die Methode mithilfe <xref:System.Reflection.Emit?displayProperty=nameWithType>von erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="35d3a-112">The method returns `CORPROF_E_MODULE_IS_DYNAMIC` if the method was created using <xref:System.Reflection.Emit?displayProperty=nameWithType>.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="35d3a-113">Hinweise</span><span class="sxs-lookup"><span data-stu-id="35d3a-113">Remarks</span></span>  
 <span data-ttu-id="35d3a-114">Wenn das Modul über in-Memory-Symbole verfügt, wird die Länge des Streams in `pCountSymbolBytes`eingefügt.</span><span class="sxs-lookup"><span data-stu-id="35d3a-114">If the module has in-memory symbols, the length of the stream is placed in `pCountSymbolBytes`.</span></span> <span data-ttu-id="35d3a-115">, `*pCountSymbolBytes = 0`Wenn das Modul nicht über Speicher interne Symbole verfügt.</span><span class="sxs-lookup"><span data-stu-id="35d3a-115">If the module doesn't have in-memory     symbols, `*pCountSymbolBytes = 0`.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="35d3a-116">Die aktuelle Implementierung unterstützt Reflektion. ausgeben nicht.</span><span class="sxs-lookup"><span data-stu-id="35d3a-116">The current implementation does not support Reflection.Emit.</span></span> <span data-ttu-id="35d3a-117">Wenn das Modul mithilfe von Reflection. ausgeben erstellt wurde, gibt die Methode `CORPROF_E_MODULE_IS_DYNAMIC`zurück.</span><span class="sxs-lookup"><span data-stu-id="35d3a-117">If the module was created by using Reflection.Emit, the method returns `CORPROF_E_MODULE_IS_DYNAMIC`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="35d3a-118">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="35d3a-118">Requirements</span></span>  
 <span data-ttu-id="35d3a-119">**Formen** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="35d3a-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="35d3a-120">**Header:** Corprof. idl, Corprof. h</span><span class="sxs-lookup"><span data-stu-id="35d3a-120">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="35d3a-121">**Fern** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="35d3a-121">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="35d3a-122">**.NET Framework-Versionen:** [!INCLUDE[net_current_v461plus](../../../../includes/net-current-v461plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="35d3a-122">**.NET Framework Versions:** [!INCLUDE[net_current_v461plus](../../../../includes/net-current-v461plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="35d3a-123">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="35d3a-123">See also</span></span>

- [<span data-ttu-id="35d3a-124">ICorProfilerInfo7-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="35d3a-124">ICorProfilerInfo7 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo7-interface.md)
