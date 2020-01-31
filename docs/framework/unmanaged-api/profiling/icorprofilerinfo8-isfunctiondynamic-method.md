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
ms.openlocfilehash: 50b4de2de3e74a5835ee5706999892735269d4c2
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/29/2020
ms.locfileid: "76861735"
---
# <a name="icorprofilerinfo8isfunctiondynamic-method"></a><span data-ttu-id="f1c57-102">ICorProfilerInfo8:: isfunctiondynamic-Methode</span><span class="sxs-lookup"><span data-stu-id="f1c57-102">ICorProfilerInfo8::IsFunctionDynamic Method</span></span>

<span data-ttu-id="f1c57-103">Bestimmt, ob einer Funktion keine zugeordneten Metadaten zugeordnet sind.</span><span class="sxs-lookup"><span data-stu-id="f1c57-103">Determines if a function does not have associated metadata.</span></span>

## <a name="syntax"></a><span data-ttu-id="f1c57-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="f1c57-104">Syntax</span></span>

```cpp
HRESULT IsFunctionDynamic( [in]  FunctionID  functionId,
                           [out] BOOL        *isDynamic);
```

## <a name="parameters"></a><span data-ttu-id="f1c57-105">Parameters</span><span class="sxs-lookup"><span data-stu-id="f1c57-105">Parameters</span></span>

- `functionId`

  <span data-ttu-id="f1c57-106">\[in] das `FunctionID`, das die betreffende Funktion identifiziert.</span><span class="sxs-lookup"><span data-stu-id="f1c57-106">\[in]  The `FunctionID` that identifies the function in question.</span></span>

- `isDynamic`

  <span data-ttu-id="f1c57-107">\[out] ein Zeiger auf eine `BOOL`, die einen Wert enthält, der angibt, ob die Funktion über keine Metadaten verfügt.</span><span class="sxs-lookup"><span data-stu-id="f1c57-107">\[out] A pointer to a `BOOL` that will contain a value indicating if the function has no metadata.</span></span>

## <a name="remarks"></a><span data-ttu-id="f1c57-108">Hinweise</span><span class="sxs-lookup"><span data-stu-id="f1c57-108">Remarks</span></span>

<span data-ttu-id="f1c57-109">Eine Funktion wird als dynamisch angesehen, wenn Sie über keine Metadaten verfügt.</span><span class="sxs-lookup"><span data-stu-id="f1c57-109">A function is considered dynamic if it has no metadata.</span></span> <span data-ttu-id="f1c57-110">Bestimmte Methoden wie IL-Stub-oder LCG-Methoden haben keine zugeordneten Metadaten, die mit den IMetaDataImport-APIs abgerufen werden können.</span><span class="sxs-lookup"><span data-stu-id="f1c57-110">Certain methods like IL Stubs or LCG Methods do not have associated metadata that can be retrieved using the IMetaDataImport APIs.</span></span> <span data-ttu-id="f1c57-111">Diese Methoden können von profinern durch Anweisungs Zeiger oder durch lauschen auf [ICorProfilerCallback::D ynamicmethodjitcompilationstarted](icorprofilercallback8-dynamicmethodjitcompilationstarted-method.md)gefunden werden.</span><span class="sxs-lookup"><span data-stu-id="f1c57-111">These methods can be encountered by profilers through instruction pointers or by listening to [ICorProfilerCallback::DynamicMethodJITCompilationStarted](icorprofilercallback8-dynamicmethodjitcompilationstarted-method.md).</span></span>

## <a name="requirements"></a><span data-ttu-id="f1c57-112">-Anforderungen</span><span class="sxs-lookup"><span data-stu-id="f1c57-112">Requirements</span></span>

<span data-ttu-id="f1c57-113">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f1c57-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>

<span data-ttu-id="f1c57-114">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="f1c57-114">**Header:** CorProf.idl, CorProf.h</span></span>

<span data-ttu-id="f1c57-115">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f1c57-115">**Library:** CorGuids.lib</span></span>

<span data-ttu-id="f1c57-116">**.NET Framework Versionen:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="f1c57-116">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="f1c57-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f1c57-117">See also</span></span>

- [<span data-ttu-id="f1c57-118">ICorProfilerInfo8-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="f1c57-118">ICorProfilerInfo8 Interface</span></span>](icorprofilerinfo8-interface.md)
