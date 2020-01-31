---
title: 'ICorProfilerInfo8:: getdynamicfunctioninfo'
ms.date: 08/06/2019
dev_langs:
- cpp
api_name:
- ICorProfilerInfo8.GetDynamicFunctionInfo
api_location:
- mscorwks.dll
api_type:
- COM
author: davmason
ms.author: davmason
ms.openlocfilehash: 66a08cf60ae4ca9bb6e373d230d0819ee6f9b28c
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/28/2020
ms.locfileid: "76790008"
---
# <a name="icorprofilerinfo8getdynamicfunctioninfo-method"></a><span data-ttu-id="c6547-102">ICorProfilerInfo8:: getdynamicfunctioninfo-Methode</span><span class="sxs-lookup"><span data-stu-id="c6547-102">ICorProfilerInfo8::GetDynamicFunctionInfo Method</span></span>

<span data-ttu-id="c6547-103">Ruft Informationen zu dynamischen Methoden ab.</span><span class="sxs-lookup"><span data-stu-id="c6547-103">Retrieves information about dynamic methods.</span></span>

## <a name="syntax"></a><span data-ttu-id="c6547-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="c6547-104">Syntax</span></span>

```cpp
HRESULT GetDynamicFunctionInfo( [in]  FunctionID              functionId,
                                [out] ModuleID                *moduleId,
                                [out] PCCOR_SIGNATURE         *ppvSig,
                                [out] ULONG                   *pbSig,
                                [in]  ULONG                   cchName,
                                [out] ULONG                   *pcchName,
                                [out] WCHAR                   wszName[]);
```

## <a name="parameters"></a><span data-ttu-id="c6547-105">Parameters</span><span class="sxs-lookup"><span data-stu-id="c6547-105">Parameters</span></span>

- `functionId`

  <span data-ttu-id="c6547-106">\[in] die ID der Funktion, für die Informationen abgerufen werden sollen.</span><span class="sxs-lookup"><span data-stu-id="c6547-106">\[in] The ID of the function for which to retrieve information.</span></span>

- `moduleId`

  <span data-ttu-id="c6547-107">\[in] ein Zeiger auf das Modul, in dem die übergeordnete Klasse der Funktion definiert ist.</span><span class="sxs-lookup"><span data-stu-id="c6547-107">\[in] A pointer to the module in which the function's parent class is defined.</span></span>

- `ppvSig`

  <span data-ttu-id="c6547-108">\[out] ein Zeiger auf die Signatur der Funktion.</span><span class="sxs-lookup"><span data-stu-id="c6547-108">\[out] A pointer to the signature for the function.</span></span>

- `pbSig`

  <span data-ttu-id="c6547-109">\[out] ein Zeiger auf die Anzahl von Bytes für die Funktions Signatur.</span><span class="sxs-lookup"><span data-stu-id="c6547-109">\[out] A pointer to the count of bytes for the function signature.</span></span>

- `cchName`

  <span data-ttu-id="c6547-110">\[in] die maximale Größe des `wszName` Arrays.</span><span class="sxs-lookup"><span data-stu-id="c6547-110">\[in] The maximum size of the `wszName` array.</span></span>

- `pcchName`

  <span data-ttu-id="c6547-111">\[out] die Anzahl der Zeichen im `wszName` Array.</span><span class="sxs-lookup"><span data-stu-id="c6547-111">\[out] The number of characters in the `wszName` array.</span></span>

- `wszName`

  <span data-ttu-id="c6547-112">\[out] ein Array von `WCHAR`, bei dem es sich um den Namen der Funktion handelt, sofern vorhanden.</span><span class="sxs-lookup"><span data-stu-id="c6547-112">\[out] An array of `WCHAR` which is the name of the function, if one exists.</span></span>

## <a name="remarks"></a><span data-ttu-id="c6547-113">Hinweise</span><span class="sxs-lookup"><span data-stu-id="c6547-113">Remarks</span></span>

<span data-ttu-id="c6547-114">Bestimmte Methoden wie IL-Stub oder LCG verfügen über keine zugeordneten Metadaten, die mithilfe der APIs [IMetaDataImport](../metadata/imetadataimport-interface.md) und [IMetaDataImport2](../metadata/imetadataimport2-interface.md) abgerufen werden können.</span><span class="sxs-lookup"><span data-stu-id="c6547-114">Certain methods like IL Stubs or LCG do not have associated metadata that can be retrieved using the [IMetaDataImport](../metadata/imetadataimport-interface.md) and [IMetaDataImport2](../metadata/imetadataimport2-interface.md) APIs.</span></span> <span data-ttu-id="c6547-115">Solche Methoden können von profinern durch Anweisungs Zeiger oder durch lauschen auf [ICorProfilerCallback8::D ynamicmethodjitcompilationstarted](icorprofilercallback8-dynamicmethodjitcompilationstarted-method.md)gefunden werden.</span><span class="sxs-lookup"><span data-stu-id="c6547-115">Such methods can be encountered by profilers through instruction pointers or by listening to [ICorProfilerCallback8::DynamicMethodJITCompilationStarted](icorprofilercallback8-dynamicmethodjitcompilationstarted-method.md).</span></span>

<span data-ttu-id="c6547-116">Diese API kann verwendet werden, um Informationen zu dynamischen Methoden, einschließlich eines anzeigen Amens, abzurufen, falls verfügbar.</span><span class="sxs-lookup"><span data-stu-id="c6547-116">This API can be used to retrieve information about dynamic methods, including a friendly name, if available.</span></span>

## <a name="requirements"></a><span data-ttu-id="c6547-117">-Anforderungen</span><span class="sxs-lookup"><span data-stu-id="c6547-117">Requirements</span></span>

<span data-ttu-id="c6547-118">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c6547-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>

<span data-ttu-id="c6547-119">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="c6547-119">**Header:** CorProf.idl, CorProf.h</span></span>

<span data-ttu-id="c6547-120">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c6547-120">**Library:** CorGuids.lib</span></span>

<span data-ttu-id="c6547-121">**.NET Framework Versionen:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="c6547-121">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="c6547-122">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c6547-122">See also</span></span>

- [<span data-ttu-id="c6547-123">ICorProfilerInfo8-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="c6547-123">ICorProfilerInfo8 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo8-interface.md)
