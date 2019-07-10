---
title: ICorProfilerInfo3::GetModuleInfo2-Methode
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo3.GetModuleInfo2
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo3::GetModuleInfo2
helpviewer_keywords:
- ICorProfilerInfo3::GetModuleInfo2 method [.NET Framework profiling]
- GetModuleInfo2 method [.NET Framework profiling]
ms.assetid: f1f6b8f3-dcfc-49e8-be76-ea50ea90d5a7
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 5ead38d54d470c3f443ae5e27e4a2d045bc27c79
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67783033"
---
# <a name="icorprofilerinfo3getmoduleinfo2-method"></a><span data-ttu-id="4d63b-102">ICorProfilerInfo3::GetModuleInfo2-Methode</span><span class="sxs-lookup"><span data-stu-id="4d63b-102">ICorProfilerInfo3::GetModuleInfo2 Method</span></span>
<span data-ttu-id="4d63b-103">Gibt bei Angabe einer Modul-ID den Dateinamen des Moduls, die ID der übergeordneten Assembly des Moduls und eine Bitmaske zurück, die die Eigenschaften des Moduls beschreibt.</span><span class="sxs-lookup"><span data-stu-id="4d63b-103">Given a module ID, returns the file name of the module, the ID of the module's parent assembly, and a bitmask that describes the properties of the module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4d63b-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="4d63b-104">Syntax</span></span>  
  
```cpp  
HRESULT GetModuleInfo2(  
    [in]  ModuleID   moduleId,  
    [out] LPCBYTE    *ppBaseLoadAddress,  
    [in]  ULONG      cchName,  
    [out] ULONG      *pcchName,  
    [out, annotation("__out_ecount_part(cchName, *pcchName)")]  
          WCHAR      szName[] ,  
    [out] AssemblyID *pAssemblyId);  
    [out] DWORD                 *pdwModuleFlags);  
```  
  
## <a name="parameters"></a><span data-ttu-id="4d63b-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="4d63b-105">Parameters</span></span>  
 `moduleId`  
 <span data-ttu-id="4d63b-106">[in] Die ID des Moduls, für das Informationen abgerufen werden sollen.</span><span class="sxs-lookup"><span data-stu-id="4d63b-106">[in] The ID of the module for which information will be retrieved.</span></span>  
  
 `ppBaseLoadAddress`  
 <span data-ttu-id="4d63b-107">[out] Die Basisadresse, an der das Modul geladen wird.</span><span class="sxs-lookup"><span data-stu-id="4d63b-107">[out] The base address at which the module is loaded.</span></span>  
  
 `cchName`  
 <span data-ttu-id="4d63b-108">[in] Die Länge des `szName`-Rückgabepuffers in Zeichen.</span><span class="sxs-lookup"><span data-stu-id="4d63b-108">[in] The length, in characters, of the `szName` return buffer.</span></span>  
  
 `pcchName`  
 <span data-ttu-id="4d63b-109">[out] Ein Zeiger auf die gesamte Zeichenlänge des zurückgegebenen Dateinamens des Moduls.</span><span class="sxs-lookup"><span data-stu-id="4d63b-109">[out] A pointer to the total character length of the module's file name that is returned.</span></span>  
  
 `szName`  
 <span data-ttu-id="4d63b-110">[out] Ein vom Aufrufer bereitgestellter Breitzeichenpuffer.</span><span class="sxs-lookup"><span data-stu-id="4d63b-110">[out] A caller-provided wide character buffer.</span></span> <span data-ttu-id="4d63b-111">Wenn die Methode abgeschlossen ist, enthält dieser Puffer den Dateinamen des Moduls.</span><span class="sxs-lookup"><span data-stu-id="4d63b-111">When the method returns, this buffer contains the file name of the module.</span></span>  
  
 `pAssemblyId`  
 <span data-ttu-id="4d63b-112">[out] Ein Zeiger auf die ID der übergeordneten Assembly des Moduls.</span><span class="sxs-lookup"><span data-stu-id="4d63b-112">[out] A pointer to the ID of the module's parent assembly.</span></span>  
  
 `pdwModuleFlags`  
 <span data-ttu-id="4d63b-113">[out] Eine Bitmaske der Werte aus der [COR_PRF_MODULE_FLAGS](../../../../docs/framework/unmanaged-api/profiling/cor-prf-module-flags-enumeration.md) -Enumeration, die die Eigenschaften des Moduls angeben.</span><span class="sxs-lookup"><span data-stu-id="4d63b-113">[out] A bitmask of values from the [COR_PRF_MODULE_FLAGS](../../../../docs/framework/unmanaged-api/profiling/cor-prf-module-flags-enumeration.md) enumeration that specify the properties of the module.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="4d63b-114">Hinweise</span><span class="sxs-lookup"><span data-stu-id="4d63b-114">Remarks</span></span>  
 <span data-ttu-id="4d63b-115">Bei dynamischen Modulen ist der `szName`-Parameter der Metadatenname des Moduls, und die Basisadresse ist 0 (null).</span><span class="sxs-lookup"><span data-stu-id="4d63b-115">For dynamic modules, the `szName` parameter is the metadata name of the module, and the base address is 0 (zero).</span></span> <span data-ttu-id="4d63b-116">Der Metadatenname ist der Wert in der Spalte "Name" der Modultabelle innerhalb der Metadaten.</span><span class="sxs-lookup"><span data-stu-id="4d63b-116">The metadata name is the value in the Name column from the Module table inside metadata.</span></span> <span data-ttu-id="4d63b-117">Wird auch als verfügbar gemacht der <xref:System.Reflection.Module.ScopeName%2A?displayProperty=nameWithType> Eigenschaft, die an verwalteten Code und als die `szName` Parameter, der die [IMetaDataImport:: GetScopeProps](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-getscopeprops-method.md) Methode, um nicht verwalteten metadatenclientcode.</span><span class="sxs-lookup"><span data-stu-id="4d63b-117">This is also exposed as the <xref:System.Reflection.Module.ScopeName%2A?displayProperty=nameWithType> property to managed code, and as the `szName` parameter of the [IMetaDataImport::GetScopeProps](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-getscopeprops-method.md) method to unmanaged metadata client code.</span></span>  
  
 <span data-ttu-id="4d63b-118">Obwohl die `GetModuleInfo2` Methode aufgerufen werden kann, sobald die Modul ID vorhanden ist, die ID der übergeordneten Assembly wird nicht zur Verfügung, bis die empfängt der Profiler die [ICorProfilerCallback:: ModuleAttachedToAssembly](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleattachedtoassembly-method.md) Rückruf.</span><span class="sxs-lookup"><span data-stu-id="4d63b-118">Although the `GetModuleInfo2` method may be called as soon as the module's ID exists, the ID of the parent assembly will not be available until the profiler receives the [ICorProfilerCallback::ModuleAttachedToAssembly](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleattachedtoassembly-method.md) callback.</span></span>  
  
 <span data-ttu-id="4d63b-119">Nachdem `GetModuleInfo2` abgeschlossen ist, müssen Sie überprüfen, ob der `szName`-Puffer groß genug war, um den vollständigen Dateinamen des Moduls aufzunehmen.</span><span class="sxs-lookup"><span data-stu-id="4d63b-119">When `GetModuleInfo2` returns, you must verify that the `szName` buffer was large enough to contain the full file name of the module.</span></span> <span data-ttu-id="4d63b-120">Vergleichen Sie zu diesem Zweck den Wert, auf den `pcchName` verweist, mit dem Wert des Parameters `cchName`.</span><span class="sxs-lookup"><span data-stu-id="4d63b-120">To do this, compare the value that `pcchName` points to with the value of the `cchName` parameter.</span></span> <span data-ttu-id="4d63b-121">Wenn `pcchName` auf einen Wert verweist, der größer als `cchName` ist, weisen Sie einen größeren `szName`-Puffer zu, aktualisieren Sie `cchName` mit der neuen Größe, und rufen Sie `GetModuleInfo2` erneut auf.</span><span class="sxs-lookup"><span data-stu-id="4d63b-121">If `pcchName` points to a value that is larger than `cchName`, allocate a larger `szName` buffer, update `cchName` with the new, larger size, and call `GetModuleInfo2` again.</span></span>  
  
 <span data-ttu-id="4d63b-122">Alternativ können Sie zuerst `GetModuleInfo2` mit einem `szName`-Puffer der Länge 0 (NULL) aufrufen, um die richtige Puffergröße zu ermitteln.</span><span class="sxs-lookup"><span data-stu-id="4d63b-122">Alternatively, you can first call `GetModuleInfo2` with a zero-length `szName` buffer to obtain the correct buffer size.</span></span> <span data-ttu-id="4d63b-123">Sie können die Puffergröße dann auf den Wert festlegen, der von `pcchName` zurückgegeben wurde, und `GetModuleInfo2` erneut aufrufen.</span><span class="sxs-lookup"><span data-stu-id="4d63b-123">You can then set the buffer size to the value returned in `pcchName` and call `GetModuleInfo2` again.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4d63b-124">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="4d63b-124">Requirements</span></span>  
 <span data-ttu-id="4d63b-125">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4d63b-125">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4d63b-126">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="4d63b-126">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="4d63b-127">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="4d63b-127">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="4d63b-128">**.NET Framework-Versionen:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4d63b-128">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4d63b-129">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="4d63b-129">See also</span></span>

- [<span data-ttu-id="4d63b-130">ICorProfilerInfo-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="4d63b-130">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
- [<span data-ttu-id="4d63b-131">Profilerstellungsschnittstellen</span><span class="sxs-lookup"><span data-stu-id="4d63b-131">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
- [<span data-ttu-id="4d63b-132">Profilerstellung</span><span class="sxs-lookup"><span data-stu-id="4d63b-132">Profiling</span></span>](../../../../docs/framework/unmanaged-api/profiling/index.md)
