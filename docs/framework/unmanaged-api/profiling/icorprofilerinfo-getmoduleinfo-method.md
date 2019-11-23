---
title: ICorProfilerInfo::GetModuleInfo-Methode
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo.GetModuleInfo
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo::GetModuleInfo
helpviewer_keywords:
- GetModuleInfo method [.NET Framework profiling]
- ICorProfilerInfo::GetModuleInfo method [.NET Framework profiling]
ms.assetid: 5a90d16f-7929-4987-8f83-a631becf564d
topic_type:
- apiref
ms.openlocfilehash: aae6d33166a7685e07c4d82f654f803600e37eec
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/23/2019
ms.locfileid: "74438891"
---
# <a name="icorprofilerinfogetmoduleinfo-method"></a><span data-ttu-id="23d4d-102">ICorProfilerInfo::GetModuleInfo-Methode</span><span class="sxs-lookup"><span data-stu-id="23d4d-102">ICorProfilerInfo::GetModuleInfo Method</span></span>
<span data-ttu-id="23d4d-103">Gibt für die übergebene Modul-ID den Dateinamen des Moduls und die ID der übergeordneten Assembly des Moduls zurück.</span><span class="sxs-lookup"><span data-stu-id="23d4d-103">Given a module ID, returns the file name of the module and the ID of the module's parent assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="23d4d-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="23d4d-104">Syntax</span></span>  
  
```cpp  
HRESULT GetModuleInfo(  
    [in]  ModuleID   moduleId,  
    [out] LPCBYTE    *ppBaseLoadAddress,  
    [in]  ULONG      cchName,  
    [out] ULONG      *pcchName,  
    [out, size_is(cchName), length_is(*pcchName)]  
          WCHAR      szName[] ,  
    [out] AssemblyID *pAssemblyId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="23d4d-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="23d4d-105">Parameters</span></span>  
 `moduleId`  
 <span data-ttu-id="23d4d-106">[in] Die ID des Moduls, für das Informationen abgerufen werden sollen.</span><span class="sxs-lookup"><span data-stu-id="23d4d-106">[in] The ID of the module for which information will be retrieved.</span></span>  
  
 `ppBaseLoadAddress`  
 <span data-ttu-id="23d4d-107">[out] Die Basisadresse, an der das Modul geladen wird.</span><span class="sxs-lookup"><span data-stu-id="23d4d-107">[out] The base address at which the module is loaded.</span></span>  
  
 `cchName`  
 <span data-ttu-id="23d4d-108">[in] Die Länge des `szName`-Rückgabepuffers in Zeichen.</span><span class="sxs-lookup"><span data-stu-id="23d4d-108">[in] The length, in characters, of the `szName` return buffer.</span></span>  
  
 `pcchName`  
 <span data-ttu-id="23d4d-109">[out] Ein Zeiger auf die gesamte Zeichenlänge des zurückgegebenen Dateinamens des Moduls.</span><span class="sxs-lookup"><span data-stu-id="23d4d-109">[out] A pointer to the total character length of the module's file name that is returned.</span></span>  
  
 `szName`  
 <span data-ttu-id="23d4d-110">[out] Ein vom Aufrufer bereitgestellter Breitzeichenpuffer.</span><span class="sxs-lookup"><span data-stu-id="23d4d-110">[out] A caller-provided wide character buffer.</span></span> <span data-ttu-id="23d4d-111">Wenn die Methode abgeschlossen ist, enthält dieser Puffer den Dateinamen des Moduls.</span><span class="sxs-lookup"><span data-stu-id="23d4d-111">When the method returns, this buffer contains the file name of the module.</span></span>  
  
 `pAssemblyId`  
 <span data-ttu-id="23d4d-112">[out] Ein Zeiger auf die ID der übergeordneten Assembly des Moduls.</span><span class="sxs-lookup"><span data-stu-id="23d4d-112">[out] A pointer to the ID of the module's parent assembly.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="23d4d-113">Hinweise</span><span class="sxs-lookup"><span data-stu-id="23d4d-113">Remarks</span></span>  
 <span data-ttu-id="23d4d-114">Bei dynamischen Modulen ist der `szName` Parameter ist eine leere Zeichenfolge, und die Basisadresse ist 0 (null).</span><span class="sxs-lookup"><span data-stu-id="23d4d-114">For dynamic modules, the `szName` parameter is an empty string, and the base address is 0 (zero).</span></span>  
  
 <span data-ttu-id="23d4d-115">Although the `GetModuleInfo` method may be called as soon as the module's ID exists, the ID of the parent assembly will not be available until the profiler receives the [ICorProfilerCallback::ModuleAttachedToAssembly](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleattachedtoassembly-method.md) callback.</span><span class="sxs-lookup"><span data-stu-id="23d4d-115">Although the `GetModuleInfo` method may be called as soon as the module's ID exists, the ID of the parent assembly will not be available until the profiler receives the [ICorProfilerCallback::ModuleAttachedToAssembly](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleattachedtoassembly-method.md) callback.</span></span>  
  
 <span data-ttu-id="23d4d-116">Nachdem `GetModuleInfo` abgeschlossen ist, müssen Sie überprüfen, ob der `szName`-Puffer groß genug war, um den vollständigen Dateinamen des Moduls aufzunehmen.</span><span class="sxs-lookup"><span data-stu-id="23d4d-116">When `GetModuleInfo` returns, you must verify that the `szName` buffer was large enough to contain the full file name of the module.</span></span> <span data-ttu-id="23d4d-117">Vergleichen Sie zu diesem Zweck den Wert, auf den `pcchName` verweist, mit dem Wert des Parameters `cchName`.</span><span class="sxs-lookup"><span data-stu-id="23d4d-117">To do this, compare the value that `pcchName` points to with the value of the `cchName` parameter.</span></span> <span data-ttu-id="23d4d-118">Wenn `pcchName` auf einen Wert verweist, der größer als `cchName` ist, weisen Sie einen größeren `szName`-Puffer zu, aktualisieren Sie `cchName` mit der neuen Größe, und rufen Sie `GetModuleInfo` erneut auf.</span><span class="sxs-lookup"><span data-stu-id="23d4d-118">If `pcchName` points to a value that is larger than `cchName`, allocate a larger `szName` buffer, update `cchName` with the new, larger size, and call `GetModuleInfo` again.</span></span>  
  
 <span data-ttu-id="23d4d-119">Alternativ können Sie zuerst `GetModuleInfo` mit einem `szName`-Puffer der Länge 0 (NULL) aufrufen, um die richtige Puffergröße zu ermitteln.</span><span class="sxs-lookup"><span data-stu-id="23d4d-119">Alternatively, you can first call `GetModuleInfo` with a zero-length `szName` buffer to obtain the correct buffer size.</span></span> <span data-ttu-id="23d4d-120">Sie können die Puffergröße dann auf den Wert festlegen, der von `pcchName` zurückgegeben wurde, und `GetModuleInfo` erneut aufrufen.</span><span class="sxs-lookup"><span data-stu-id="23d4d-120">You can then set the buffer size to the value returned in `pcchName` and call `GetModuleInfo` again.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="23d4d-121">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="23d4d-121">Requirements</span></span>  
 <span data-ttu-id="23d4d-122">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="23d4d-122">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="23d4d-123">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="23d4d-123">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="23d4d-124">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="23d4d-124">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="23d4d-125">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="23d4d-125">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="23d4d-126">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="23d4d-126">See also</span></span>

- [<span data-ttu-id="23d4d-127">ICorProfilerInfo-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="23d4d-127">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
- [<span data-ttu-id="23d4d-128">Profilerstellungsschnittstellen</span><span class="sxs-lookup"><span data-stu-id="23d4d-128">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
- [<span data-ttu-id="23d4d-129">Profilerstellung</span><span class="sxs-lookup"><span data-stu-id="23d4d-129">Profiling</span></span>](../../../../docs/framework/unmanaged-api/profiling/index.md)
- [<span data-ttu-id="23d4d-130">GetModuleInfo2-Methode</span><span class="sxs-lookup"><span data-stu-id="23d4d-130">GetModuleInfo2 Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-getmoduleinfo2-method.md)
