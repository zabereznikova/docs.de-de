---
title: ICorProfilerInfo::GetAssemblyInfo-Methode
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo.GetAssemblyInfo
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- GetAssemblyInfo Method
helpviewer_keywords:
- GetAssemblyInfo method [.NET Framework profiling]
- ICorProfilerInfo::GetAssemblyInfo method [.NET Framework profiling]
ms.assetid: 7a3c97c3-1e31-47b1-bf23-386785c509c4
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: ad4ebe4e1255ce13974063eef3d0a4feeb5dd92b
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59083054"
---
# <a name="icorprofilerinfogetassemblyinfo-method"></a><span data-ttu-id="c399b-102">ICorProfilerInfo::GetAssemblyInfo-Methode</span><span class="sxs-lookup"><span data-stu-id="c399b-102">ICorProfilerInfo::GetAssemblyInfo Method</span></span>
<span data-ttu-id="c399b-103">Akzeptiert eine Assembly-ID und gibt den Namen der Assembly und die ID ihres Manifestmoduls zurück.</span><span class="sxs-lookup"><span data-stu-id="c399b-103">Accepts an assembly ID, and returns the assembly's name and the ID of its manifest module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c399b-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="c399b-104">Syntax</span></span>  
  
```  
HRESULT GetAssemblyInfo(  
    [in]  AssemblyID  assemblyId,  
    [in]  ULONG       cchName,  
    [out] ULONG       *pcchName,  
    [out, size_is(cchName), length_is(*pcchName)]  
          WCHAR       szName[] ,  
    [out] AppDomainID *pAppDomainId,  
    [out] ModuleID    *pModuleId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c399b-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="c399b-105">Parameters</span></span>  
 `assemblyId`  
 <span data-ttu-id="c399b-106">[in] Der Bezeichner der Assembly.</span><span class="sxs-lookup"><span data-stu-id="c399b-106">[in] The identifier of the assembly.</span></span>  
  
 `cchName`  
 <span data-ttu-id="c399b-107">[in] Die Länge von `szName` als Anzahl von Zeichen. </span><span class="sxs-lookup"><span data-stu-id="c399b-107">[in] The length, in characters, of `szName`.</span></span>  
  
 `pcchName`  
 <span data-ttu-id="c399b-108">[out] Ein Zeiger auf die Gesamtzeichenanzahl des Assemblynamens.</span><span class="sxs-lookup"><span data-stu-id="c399b-108">[out] A pointer to the total character length of the assembly's name.</span></span>  
  
 `szName`  
 <span data-ttu-id="c399b-109">[out] Ein vom Aufrufer bereitgestellter Breitzeichenpuffer.</span><span class="sxs-lookup"><span data-stu-id="c399b-109">[out] A caller-provided wide character buffer.</span></span> <span data-ttu-id="c399b-110">Bei Rückgabe der Funktion enthält er den Namen der Assembly.</span><span class="sxs-lookup"><span data-stu-id="c399b-110">When the function returns, it will contain the assembly's name.</span></span>  
  
 `pAppDomainId`  
 <span data-ttu-id="c399b-111">[out] Ein Zeiger auf die ID der Anwendungsdomäne, die die Assembly enthält.</span><span class="sxs-lookup"><span data-stu-id="c399b-111">[out] A pointer to the ID of the application domain that contains the assembly.</span></span>  
  
 `pModuleId`  
 <span data-ttu-id="c399b-112">[out] Ein Zeiger auf die ID des Manifestmoduls der Assembly.</span><span class="sxs-lookup"><span data-stu-id="c399b-112">[out] A pointer to the ID of the assembly's manifest module.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c399b-113">Hinweise</span><span class="sxs-lookup"><span data-stu-id="c399b-113">Remarks</span></span>  
 <span data-ttu-id="c399b-114">Nach der Methodenrückgabe müssen Sie überprüfen, ob der `szName`-Puffer groß genug war, um den vollständigen Namen der Assembly aufzunehmen.</span><span class="sxs-lookup"><span data-stu-id="c399b-114">After this method returns, you must verify that the `szName` buffer was large enough to contain the full name of the assembly.</span></span> <span data-ttu-id="c399b-115">Vergleichen Sie zu diesem Zweck den Wert, auf den `pcchName` verweist, mit dem Wert des Parameters `cchName`.</span><span class="sxs-lookup"><span data-stu-id="c399b-115">To do this, compare the value that `pcchName` points to with the value of the `cchName` parameter.</span></span> <span data-ttu-id="c399b-116">Wenn `pcchName` auf einen Wert verweist, der größer als `cchName` ist, weisen Sie einen größeren `szName`-Puffer zu, aktualisieren Sie `cchName` mit der neuen Größe, und rufen Sie `GetAssemblyInfo` erneut auf.</span><span class="sxs-lookup"><span data-stu-id="c399b-116">If `pcchName` points to a value that is larger than `cchName`, allocate a larger `szName` buffer, update `cchName` with the new, larger size, and call `GetAssemblyInfo` again.</span></span>  
  
 <span data-ttu-id="c399b-117">Alternativ können Sie zuerst `GetAssemblyInfo` mit einem `szName`-Puffer der Länge 0 (NULL) aufrufen, um die richtige Puffergröße zu ermitteln.</span><span class="sxs-lookup"><span data-stu-id="c399b-117">Alternatively, you can first call `GetAssemblyInfo` with a zero-length `szName` buffer to obtain the correct buffer size.</span></span> <span data-ttu-id="c399b-118">Sie können die Puffergröße dann auf Basis des Werts anpassen, der von `pcchName` zurückgegeben wurde, und `GetAssemblyInfo` erneut aufrufen.</span><span class="sxs-lookup"><span data-stu-id="c399b-118">You can then adjust the buffer size based on the value returned in `pcchName` and call `GetAssemblyInfo` again.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c399b-119">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="c399b-119">Requirements</span></span>  
 <span data-ttu-id="c399b-120">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c399b-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c399b-121">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="c399b-121">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="c399b-122">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c399b-122">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c399b-123">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c399b-123">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c399b-124">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c399b-124">See also</span></span>

- [<span data-ttu-id="c399b-125">ICorProfilerInfo-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="c399b-125">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
- [<span data-ttu-id="c399b-126">Profilerstellungsschnittstellen</span><span class="sxs-lookup"><span data-stu-id="c399b-126">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
- [<span data-ttu-id="c399b-127">Profilerstellung</span><span class="sxs-lookup"><span data-stu-id="c399b-127">Profiling</span></span>](../../../../docs/framework/unmanaged-api/profiling/index.md)
