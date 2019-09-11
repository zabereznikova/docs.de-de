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
ms.openlocfilehash: 01aa1df27dccf41060083333588e04bc5ea88520
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/10/2019
ms.locfileid: "70855925"
---
# <a name="icorprofilerinfo8isfunctiondynamic-method"></a><span data-ttu-id="c8e14-102">ICorProfilerInfo8:: isfunctiondynamic-Methode</span><span class="sxs-lookup"><span data-stu-id="c8e14-102">ICorProfilerInfo8::IsFunctionDynamic Method</span></span>

<span data-ttu-id="c8e14-103">Bestimmt, ob einer Funktion keine zugeordneten Metadaten zugeordnet sind.</span><span class="sxs-lookup"><span data-stu-id="c8e14-103">Determines if a function does not have associated metadata.</span></span>

## <a name="syntax"></a><span data-ttu-id="c8e14-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="c8e14-104">Syntax</span></span>

```cpp
HRESULT IsFunctionDynamic( [in]  FunctionID  functionId,
                           [out] BOOL        *isDynamic);
```

#### <a name="parameters"></a><span data-ttu-id="c8e14-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="c8e14-105">Parameters</span></span>

`functionId` \
<span data-ttu-id="c8e14-106">in  Der `FunctionID` , der die betreffende Funktion identifiziert.</span><span class="sxs-lookup"><span data-stu-id="c8e14-106">[in]  The `FunctionID` that identifies the function in question.</span></span>

`isDynamic` \
<span data-ttu-id="c8e14-107">vorgenommen Ein Zeiger auf einen `BOOL` , der einen Wert enthält, der angibt, ob die Funktion über keine Metadaten verfügt.</span><span class="sxs-lookup"><span data-stu-id="c8e14-107">[out] A pointer to a `BOOL` that will contain a value indicating if the function has no metadata.</span></span>

## <a name="remarks"></a><span data-ttu-id="c8e14-108">Hinweise</span><span class="sxs-lookup"><span data-stu-id="c8e14-108">Remarks</span></span>

<span data-ttu-id="c8e14-109">Eine Funktion wird als dynamisch angesehen, wenn Sie über keine Metadaten verfügt.</span><span class="sxs-lookup"><span data-stu-id="c8e14-109">A function is considered dynamic if it has no metadata.</span></span> <span data-ttu-id="c8e14-110">Bestimmte Methoden wie IL-Stub-oder LCG-Methoden haben keine zugeordneten Metadaten, die mit den IMetaDataImport-APIs abgerufen werden können.</span><span class="sxs-lookup"><span data-stu-id="c8e14-110">Certain methods like IL Stubs or LCG Methods do not have associated metadata that can be retrieved using the IMetaDataImport APIs.</span></span> <span data-ttu-id="c8e14-111">Diese Methoden können von profinern durch Anweisungs Zeiger oder durch lauschen auf [ICorProfilerCallback::D ynamicmethodjitcompilationstarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback8-dynamicmethodjitcompilationstarted-method.md)gefunden werden.</span><span class="sxs-lookup"><span data-stu-id="c8e14-111">These methods can be encountered by profilers through instruction pointers or by listening to [ICorProfilerCallback::DynamicMethodJITCompilationStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback8-dynamicmethodjitcompilationstarted-method.md).</span></span>

## <a name="requirements"></a><span data-ttu-id="c8e14-112">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="c8e14-112">Requirements</span></span>

<span data-ttu-id="c8e14-113">**Formen** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c8e14-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>

<span data-ttu-id="c8e14-114">**Header:** Corprof. idl, Corprof. h</span><span class="sxs-lookup"><span data-stu-id="c8e14-114">**Header:** CorProf.idl, CorProf.h</span></span>

<span data-ttu-id="c8e14-115">**Fern** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c8e14-115">**Library:** CorGuids.lib</span></span>

<span data-ttu-id="c8e14-116">**.NET Framework-Versionen:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="c8e14-116">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="c8e14-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c8e14-117">See also</span></span>

- [<span data-ttu-id="c8e14-118">ICorProfilerInfo8-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="c8e14-118">ICorProfilerInfo8 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo8-interface.md)
