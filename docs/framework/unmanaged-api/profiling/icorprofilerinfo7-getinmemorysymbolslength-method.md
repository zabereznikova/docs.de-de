---
title: 'Icorprofilerinfo7:: Getinmemorysymbolslength-Methode'
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
ms.openlocfilehash: 422fdfef6bea40e0f4bcc7447df8dba1eab2896e
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59146093"
---
# <a name="icorprofilerinfo7getinmemorysymbolslength-method"></a><span data-ttu-id="f6a6f-102">Icorprofilerinfo7:: Getinmemorysymbolslength-Methode</span><span class="sxs-lookup"><span data-stu-id="f6a6f-102">ICorProfilerInfo7::GetInMemorySymbolsLength Method</span></span>
<span data-ttu-id="f6a6f-103">[Wird nur in .NET Framework 4.6.1 und höheren Versionen unterstützt]</span><span class="sxs-lookup"><span data-stu-id="f6a6f-103">[Supported in the .NET Framework 4.6.1 and later versions]</span></span>  
  
 <span data-ttu-id="f6a6f-104">Gibt die Länge einer in-Memory symbolstream zurück.</span><span class="sxs-lookup"><span data-stu-id="f6a6f-104">Returns the length of an in-memory symbol stream.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f6a6f-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="f6a6f-105">Syntax</span></span>  
  
```  
HRESULT GetInMemorySymbolsLength(  
        [in] ModuleID moduleId,  
        [out] DWORD* pCountSymbolBytes  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f6a6f-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="f6a6f-106">Parameters</span></span>  
 `moduleId`  
 <span data-ttu-id="f6a6f-107">[in] Der Bezeichner des Moduls mit den in-Memory-Datenstrom.</span><span class="sxs-lookup"><span data-stu-id="f6a6f-107">[in] The identifier of the module containing the in-memory stream.</span></span>  
  
 <span data-ttu-id="f6a6f-108">pCountSymbolBytes</span><span class="sxs-lookup"><span data-stu-id="f6a6f-108">pCountSymbolBytes</span></span>  
 <span data-ttu-id="f6a6f-109">[out] Ein Zeiger auf eine `DWORD` Wert, der beim Beenden der Methode, die Länge des Streams in Bytes enthält.</span><span class="sxs-lookup"><span data-stu-id="f6a6f-109">[out] A pointer to a `DWORD` value that, when the method returns, contains the length of the stream in bytes.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="f6a6f-110">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="f6a6f-110">Return Value</span></span>  
 <span data-ttu-id="f6a6f-111">Gibt die Methode zurück `S_OK` Wenn die Länge des Streams, der Arbeitsspeicher bestimmt werden kann, auch wenn es sich um 0 (null) ist.</span><span class="sxs-lookup"><span data-stu-id="f6a6f-111">The method returns `S_OK` if the length of the memory stream can be determined, even if it is zero (0).</span></span>  
  
 <span data-ttu-id="f6a6f-112">Gibt die Methode zurück `CORPROF_E_MODULE_IS_DYNAMIC` wurde mit die Methode erstellt <xref:System.Reflection.Emit?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="f6a6f-112">The method returns `CORPROF_E_MODULE_IS_DYNAMIC` if the method was created using <xref:System.Reflection.Emit?displayProperty=nameWithType>.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f6a6f-113">Hinweise</span><span class="sxs-lookup"><span data-stu-id="f6a6f-113">Remarks</span></span>  
 <span data-ttu-id="f6a6f-114">Wenn das Modul in-Memory-Symbole wurden, befindet sich die Länge des Streams `pCountSymbolBytes`.</span><span class="sxs-lookup"><span data-stu-id="f6a6f-114">If the module has in-memory symbols, the length of the stream is placed in `pCountSymbolBytes`.</span></span> <span data-ttu-id="f6a6f-115">Wenn das Modul in-Memory-Symbole, haben keine `*pCountSymbolBytes = 0`.</span><span class="sxs-lookup"><span data-stu-id="f6a6f-115">If the module doesn't have in-memory     symbols, `*pCountSymbolBytes = 0`.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="f6a6f-116">Die aktuelle Implementierung unterstützt keine Reflection.Emit.</span><span class="sxs-lookup"><span data-stu-id="f6a6f-116">The current implementation does not support Reflection.Emit.</span></span> <span data-ttu-id="f6a6f-117">Wenn das Modul mithilfe von "Reflection.Emit" erstellt wurde, gibt die Methode `CORPROF_E_MODULE_IS_DYNAMIC`.</span><span class="sxs-lookup"><span data-stu-id="f6a6f-117">If the module was created by using Reflection.Emit, the method returns `CORPROF_E_MODULE_IS_DYNAMIC`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f6a6f-118">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="f6a6f-118">Requirements</span></span>  
 <span data-ttu-id="f6a6f-119">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f6a6f-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f6a6f-120">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="f6a6f-120">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="f6a6f-121">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f6a6f-121">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="f6a6f-122">.NET Framework-Versionen:</span><span class="sxs-lookup"><span data-stu-id="f6a6f-122">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v461plus](../../../../includes/net-current-v461plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="f6a6f-123">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f6a6f-123">See also</span></span>

- [<span data-ttu-id="f6a6f-124">ICorProfilerInfo7-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="f6a6f-124">ICorProfilerInfo7 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo7-interface.md)
