---
title: ICorProfilerInfo3::GetAppDomainsContainingModule-Methode
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo3.GetAppDomainsContainingModule Method
api_location:
- Mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo3::GetAppDomainsContainingModule
helpviewer_keywords:
- GetAppDomainsContainingModule method [.NET Framework profiling]
- ICorProfilerInfo3::GetAppDomainsContainingModule method [.NET Framework profiling]
ms.assetid: 603b3881-ea94-4dca-95cd-91eebac873a0
topic_type:
- apiref
ms.openlocfilehash: 5cc3436716bcfc2ed0f9fd7ff7982bac7a48de9a
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95731201"
---
# <a name="icorprofilerinfo3getappdomainscontainingmodule-method"></a><span data-ttu-id="b089c-102">ICorProfilerInfo3::GetAppDomainsContainingModule-Methode</span><span class="sxs-lookup"><span data-stu-id="b089c-102">ICorProfilerInfo3::GetAppDomainsContainingModule Method</span></span>

<span data-ttu-id="b089c-103">Ruft die Bezeichner der Anwendungsdomänen ab, in denen das angegebene Modul geladen wurde.</span><span class="sxs-lookup"><span data-stu-id="b089c-103">Gets the identifiers of the application domains in which the given module has been loaded.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b089c-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="b089c-104">Syntax</span></span>  
  
```cpp  
HRESULT GetAppDomainsContainingModule(  
            [in] ModuleID moduleId,  
            [in] ULONG32 cAppDomainIds,  
            [out] ULONG32 *pcAppDomainIds,  
            [out, size_is(cAppDomainIds), length_is(*pcAppDomainIds)]  
                    AppDomainID appDomainIds[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b089c-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="b089c-105">Parameters</span></span>  

 `moduleId`  
 <span data-ttu-id="b089c-106">[in] Die ID des geladenen Moduls.</span><span class="sxs-lookup"><span data-stu-id="b089c-106">[in] The ID of the loaded module.</span></span>  
  
 `cAppDomainIds`  
 <span data-ttu-id="b089c-107">[in] Die Größe des `appDomainIds`-Arrays.</span><span class="sxs-lookup"><span data-stu-id="b089c-107">[in] The size of the `appDomainIds` array.</span></span>  
  
 `pcAppDomainIds`  
 <span data-ttu-id="b089c-108">[out] Ein Zeiger auf die Gesamtzahl von zurückgegebenen Elementen.</span><span class="sxs-lookup"><span data-stu-id="b089c-108">[out] A pointer to the total number of returned elements.</span></span>  
  
 `appDomainIds`  
 <span data-ttu-id="b089c-109">[out] Ein Array von ID-Werten der Anwendungsdomänen.</span><span class="sxs-lookup"><span data-stu-id="b089c-109">[out] An array of application domain ID values.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b089c-110">Hinweise</span><span class="sxs-lookup"><span data-stu-id="b089c-110">Remarks</span></span>  

 <span data-ttu-id="b089c-111">Die Methode verwendet vom Aufrufer reservierte Puffer.</span><span class="sxs-lookup"><span data-stu-id="b089c-111">The method uses caller allocated buffers.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b089c-112">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="b089c-112">Requirements</span></span>  

 <span data-ttu-id="b089c-113">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b089c-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b089c-114">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="b089c-114">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="b089c-115">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b089c-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b089c-116">**.NET Framework Versionen:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b089c-116">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b089c-117">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="b089c-117">See also</span></span>

- [<span data-ttu-id="b089c-118">ICorProfilerFunctionEnum-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="b089c-118">ICorProfilerFunctionEnum Interface</span></span>](icorprofilerfunctionenum-interface.md)
- [<span data-ttu-id="b089c-119">ICorProfilerInfo3-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="b089c-119">ICorProfilerInfo3 Interface</span></span>](icorprofilerinfo3-interface.md)
- [<span data-ttu-id="b089c-120">Profilerstellungsschnittstellen</span><span class="sxs-lookup"><span data-stu-id="b089c-120">Profiling Interfaces</span></span>](profiling-interfaces.md)
- [<span data-ttu-id="b089c-121">Profilerstellung</span><span class="sxs-lookup"><span data-stu-id="b089c-121">Profiling</span></span>](index.md)
