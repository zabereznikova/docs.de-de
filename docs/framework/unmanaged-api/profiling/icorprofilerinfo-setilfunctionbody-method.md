---
title: ICorProfilerInfo::SetILFunctionBody-Methode
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo.SetILFunctionBody
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo::SetILFunctionBody
helpviewer_keywords:
- ICorProfilerInfo::SetILFunctionBody method [.NET Framework profiling]
- SetILFunctionBody method [.NET Framework profiling]
ms.assetid: b159c712-00f4-4fc7-a990-40bf9f642e8f
topic_type:
- apiref
ms.openlocfilehash: 462fc7222243f8cad4e1d03d1717eedace549836
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/08/2020
ms.locfileid: "84502937"
---
# <a name="icorprofilerinfosetilfunctionbody-method"></a><span data-ttu-id="ec0bd-102">ICorProfilerInfo::SetILFunctionBody-Methode</span><span class="sxs-lookup"><span data-stu-id="ec0bd-102">ICorProfilerInfo::SetILFunctionBody Method</span></span>
<span data-ttu-id="ec0bd-103">Ersetzt den Text der angegebenen Funktion im angegebenen Modul.</span><span class="sxs-lookup"><span data-stu-id="ec0bd-103">Replaces the body of the specified function in the specified module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ec0bd-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="ec0bd-104">Syntax</span></span>  
  
```cpp  
HRESULT SetILFunctionBody(  
    [in] ModuleID    moduleId,  
    [in] mdMethodDef methodid,  
    [in] LPCBYTE     pbNewILMethodHeader);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ec0bd-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="ec0bd-105">Parameters</span></span>  
 `moduleId`  
 <span data-ttu-id="ec0bd-106">in Die ID des Moduls, in dem sich die Funktion befindet.</span><span class="sxs-lookup"><span data-stu-id="ec0bd-106">[in] The ID of the module in which the function resides.</span></span>  
  
 `methodid`  
 <span data-ttu-id="ec0bd-107">in Das Token der Funktion, für die der Text ersetzt werden soll.</span><span class="sxs-lookup"><span data-stu-id="ec0bd-107">[in] The token of the function for which to replace the body.</span></span>  
  
 `pbNewILMethodHeader`  
 <span data-ttu-id="ec0bd-108">in Der neue Header für die Funktion.</span><span class="sxs-lookup"><span data-stu-id="ec0bd-108">[in] The new header for the function.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ec0bd-109">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="ec0bd-109">Remarks</span></span>  
 <span data-ttu-id="ec0bd-110">Die- `SetILFunctionBody` Methode ersetzt die relative virtuelle Adresse der-Funktion in den Metadaten, sodass Sie auf den neuen Funktions Text verweist, und passt alle internen Datenstrukturen nach Bedarf an.</span><span class="sxs-lookup"><span data-stu-id="ec0bd-110">The `SetILFunctionBody` method replaces the relative virtual address of the function in the metadata so that it points to the new function body, and adjusts any internal data structures as required.</span></span>  
  
 <span data-ttu-id="ec0bd-111">Die- `SetILFunctionBody` Methode kann nur für die Funktionen aufgerufen werden, die noch nie von einem JIT-Compiler (Just-in-Time) kompiliert wurden.</span><span class="sxs-lookup"><span data-stu-id="ec0bd-111">The `SetILFunctionBody` method can be called on only those functions that have never been compiled by a just-in-time (JIT) compiler.</span></span>  
  
 <span data-ttu-id="ec0bd-112">Verwenden Sie die [ICorProfilerInfo:: GetILFunctionBodyAllocator](icorprofilerinfo-getilfunctionbodyallocator-method.md) -Methode, um Speicherplatz für die neue Methode zuzuweisen, um sicherzustellen, dass der Puffer kompatibel ist.</span><span class="sxs-lookup"><span data-stu-id="ec0bd-112">Use the [ICorProfilerInfo::GetILFunctionBodyAllocator](icorprofilerinfo-getilfunctionbodyallocator-method.md) method to allocate space for the new method to ensure that the buffer is compatible.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ec0bd-113">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="ec0bd-113">Requirements</span></span>  
 <span data-ttu-id="ec0bd-114">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ec0bd-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ec0bd-115">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="ec0bd-115">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="ec0bd-116">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ec0bd-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ec0bd-117">**.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ec0bd-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ec0bd-118">Weitere Informationen:</span><span class="sxs-lookup"><span data-stu-id="ec0bd-118">See also</span></span>

- [<span data-ttu-id="ec0bd-119">ICorProfilerInfo-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="ec0bd-119">ICorProfilerInfo Interface</span></span>](icorprofilerinfo-interface.md)
