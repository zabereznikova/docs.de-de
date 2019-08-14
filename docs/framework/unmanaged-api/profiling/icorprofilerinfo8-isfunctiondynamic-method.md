---
title: 'ICorProfilerInfo8:: isfunctiondynamic'
ms.date: 08/06/2019
dev_langs:
- cpp
api_name:
- ICorProfilerInfo8.IsFunctionDynamic
api_location:
- mscorwks.dll
api_type:
- COM
author: davmason
ms.author: davmason
ms.openlocfilehash: 71c4e749368dce65d5250b9ab78fd8713e9d61a0
ms.sourcegitcommit: a97ecb94437362b21fffc5eb3c38b6c0b4368999
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/13/2019
ms.locfileid: "68973870"
---
# <a name="icorprofilerinfo8isfunctiondynamic-method"></a><span data-ttu-id="1351b-102">ICorProfilerInfo8:: isfunctiondynamic-Methode</span><span class="sxs-lookup"><span data-stu-id="1351b-102">ICorProfilerInfo8::IsFunctionDynamic Method</span></span>
  
  <span data-ttu-id="1351b-103">Bestimmt, ob einer Funktion keine zugeordneten Metadaten zugeordnet sind.</span><span class="sxs-lookup"><span data-stu-id="1351b-103">Determines if a function does not have associated metadata.</span></span>    
  
## <a name="syntax"></a><span data-ttu-id="1351b-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="1351b-104">Syntax</span></span>  
  
```cpp
HRESULT IsFunctionDynamic( [in]  FunctionID  functionId,
                           [out] BOOL        *isDynamic);
```  
  
#### <a name="parameters"></a><span data-ttu-id="1351b-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="1351b-105">Parameters</span></span>  
 `functionId` \
  <span data-ttu-id="1351b-106">in  Der `FunctionID` , der die betreffende Funktion identifiziert.</span><span class="sxs-lookup"><span data-stu-id="1351b-106">[in]  The `FunctionID` that identifies the function in question.</span></span>

  `isDynamic` \
  <span data-ttu-id="1351b-107">vorgenommen Ein Zeiger auf einen `BOOL` , der einen Wert enthält, der angibt, ob die Funktion über keine Metadaten verfügt.</span><span class="sxs-lookup"><span data-stu-id="1351b-107">[out] A pointer to a `BOOL` that will contain a value indicating if the function has no metadata.</span></span>

## <a name="remarks"></a><span data-ttu-id="1351b-108">Hinweise</span><span class="sxs-lookup"><span data-stu-id="1351b-108">Remarks</span></span>  
 <span data-ttu-id="1351b-109">Eine Funktion wird als dynamisch angesehen, wenn Sie über keine Metadaten verfügt.</span><span class="sxs-lookup"><span data-stu-id="1351b-109">A function is considered dynamic if it has no metadata.</span></span> <span data-ttu-id="1351b-110">Bestimmte Methoden wie IL-Stub-oder LCG-Methoden haben keine zugeordneten Metadaten, die mit den IMetaDataImport-APIs abgerufen werden können.</span><span class="sxs-lookup"><span data-stu-id="1351b-110">Certain methods like IL Stubs or LCG Methods do not have associated metadata that can be retrieved using the IMetaDataImport APIs.</span></span> <span data-ttu-id="1351b-111">Diese Methoden können von profinern durch Anweisungs Zeiger oder durch lauschen auf [ICorProfilerCallback::D ynamicmethodjitcompilationstarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback8-dynamicmethodjitcompilationstarted-method.md)gefunden werden.</span><span class="sxs-lookup"><span data-stu-id="1351b-111">These methods can be encountered by profilers through instruction pointers or by listening to [ICorProfilerCallback::DynamicMethodJITCompilationStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback8-dynamicmethodjitcompilationstarted-method.md).</span></span>

## <a name="requirements"></a><span data-ttu-id="1351b-112">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="1351b-112">Requirements</span></span>  
 <span data-ttu-id="1351b-113">**Formen** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1351b-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1351b-114">**Header:** Corprof. idl, Corprof. h</span><span class="sxs-lookup"><span data-stu-id="1351b-114">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="1351b-115">**Fern** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="1351b-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="1351b-116">**.NET Framework Versionen:** [! [Net_current_v472plus](../../../../includes/net-current-v472plus.md) einschließen</span><span class="sxs-lookup"><span data-stu-id="1351b-116">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1351b-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="1351b-117">See also</span></span>
- [<span data-ttu-id="1351b-118">ICorProfilerInfo8-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="1351b-118">ICorProfilerInfo8 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo8-interface.md)

