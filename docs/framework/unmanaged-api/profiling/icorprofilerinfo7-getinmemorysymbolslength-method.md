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
ms.openlocfilehash: 46ffa5cb4fac6988240d32cb1939cc25bdf0a412
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95686071"
---
# <a name="icorprofilerinfo7getinmemorysymbolslength-method"></a><span data-ttu-id="2dd32-102">ICorProfilerInfo7:: getinmemorysymbolslength-Methode</span><span class="sxs-lookup"><span data-stu-id="2dd32-102">ICorProfilerInfo7::GetInMemorySymbolsLength Method</span></span>

<span data-ttu-id="2dd32-103">[Wird nur in .NET Framework 4.6.1 und höheren Versionen unterstützt]</span><span class="sxs-lookup"><span data-stu-id="2dd32-103">[Supported in the .NET Framework 4.6.1 and later versions]</span></span>  
  
 <span data-ttu-id="2dd32-104">Gibt die Länge eines in-Memory-Symbol Datenstroms zurück.</span><span class="sxs-lookup"><span data-stu-id="2dd32-104">Returns the length of an in-memory symbol stream.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2dd32-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="2dd32-105">Syntax</span></span>  
  
```cpp  
HRESULT GetInMemorySymbolsLength(  
        [in] ModuleID moduleId,  
        [out] DWORD* pCountSymbolBytes  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2dd32-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="2dd32-106">Parameters</span></span>  

 `moduleId`  
 <span data-ttu-id="2dd32-107">in Der Bezeichner des Moduls, das den in-Memory-Datenstrom enthält.</span><span class="sxs-lookup"><span data-stu-id="2dd32-107">[in] The identifier of the module containing the in-memory stream.</span></span>  
  
 <span data-ttu-id="2dd32-108">pzähl-symbolbytes</span><span class="sxs-lookup"><span data-stu-id="2dd32-108">pCountSymbolBytes</span></span>  
 <span data-ttu-id="2dd32-109">vorgenommen Ein Zeiger auf einen `DWORD` Wert, der bei Rückgabe der Methode die Länge des Streams in Bytes enthält.</span><span class="sxs-lookup"><span data-stu-id="2dd32-109">[out] A pointer to a `DWORD` value that, when the method returns, contains the length of the stream in bytes.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="2dd32-110">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="2dd32-110">Return Value</span></span>  

 <span data-ttu-id="2dd32-111">Die-Methode gibt zurück `S_OK` , wenn die Länge des Speicherdaten Stroms bestimmt werden kann, auch wenn Sie 0 (null) ist.</span><span class="sxs-lookup"><span data-stu-id="2dd32-111">The method returns `S_OK` if the length of the memory stream can be determined, even if it is zero (0).</span></span>  
  
 <span data-ttu-id="2dd32-112">Die Methode gibt zurück, `CORPROF_E_MODULE_IS_DYNAMIC` Wenn die Methode mithilfe von erstellt wurde <xref:System.Reflection.Emit?displayProperty=nameWithType> .</span><span class="sxs-lookup"><span data-stu-id="2dd32-112">The method returns `CORPROF_E_MODULE_IS_DYNAMIC` if the method was created using <xref:System.Reflection.Emit?displayProperty=nameWithType>.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2dd32-113">Hinweise</span><span class="sxs-lookup"><span data-stu-id="2dd32-113">Remarks</span></span>  

 <span data-ttu-id="2dd32-114">Wenn das Modul über in-Memory-Symbole verfügt, wird die Länge des Streams in eingefügt `pCountSymbolBytes` .</span><span class="sxs-lookup"><span data-stu-id="2dd32-114">If the module has in-memory symbols, the length of the stream is placed in `pCountSymbolBytes`.</span></span> <span data-ttu-id="2dd32-115">, Wenn das Modul nicht über Speicher interne Symbole verfügt `*pCountSymbolBytes = 0` .</span><span class="sxs-lookup"><span data-stu-id="2dd32-115">If the module doesn't have in-memory     symbols, `*pCountSymbolBytes = 0`.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="2dd32-116">Die aktuelle Implementierung unterstützt Reflektion. ausgeben nicht.</span><span class="sxs-lookup"><span data-stu-id="2dd32-116">The current implementation does not support Reflection.Emit.</span></span> <span data-ttu-id="2dd32-117">Wenn das Modul mithilfe von Reflection. ausgeben erstellt wurde, gibt die Methode zurück `CORPROF_E_MODULE_IS_DYNAMIC` .</span><span class="sxs-lookup"><span data-stu-id="2dd32-117">If the module was created by using Reflection.Emit, the method returns `CORPROF_E_MODULE_IS_DYNAMIC`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2dd32-118">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="2dd32-118">Requirements</span></span>  

 <span data-ttu-id="2dd32-119">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2dd32-119">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2dd32-120">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="2dd32-120">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="2dd32-121">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2dd32-121">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2dd32-122">**.NET Framework Versionen:**[!INCLUDE[net_current_v461plus](../../../../includes/net-current-v461plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2dd32-122">**.NET Framework Versions:** [!INCLUDE[net_current_v461plus](../../../../includes/net-current-v461plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2dd32-123">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="2dd32-123">See also</span></span>

- [<span data-ttu-id="2dd32-124">ICorProfilerInfo7-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="2dd32-124">ICorProfilerInfo7 Interface</span></span>](icorprofilerinfo7-interface.md)
