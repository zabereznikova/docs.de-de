---
title: ICorProfilerFunctionEnum::GetCount-Methode
ms.date: 03/30/2017
api_name:
- ICorProfilerFunctionEnum.GetCount Method
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerFunctionEnum::GetCount
helpviewer_keywords:
- ICorProfilerFunctionEnum::GetCount method [.NET Framework profiling]
- GetCount method, ICorProfilerFunctionEnum interface [.NET Framework profiling]
ms.assetid: 62ec65e3-3e9d-400b-ae61-d24b8963995b
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: a5061750489c74e0385f2ce020c88518604b3167
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59169285"
---
# <a name="icorprofilerfunctionenumgetcount-method"></a><span data-ttu-id="78bdb-102">ICorProfilerFunctionEnum::GetCount-Methode</span><span class="sxs-lookup"><span data-stu-id="78bdb-102">ICorProfilerFunctionEnum::GetCount Method</span></span>
<span data-ttu-id="78bdb-103">Ruft die Anzahl der Funktionen ab, die von der Anwendung oder erzwungen vom Profiler geladen wurden.</span><span class="sxs-lookup"><span data-stu-id="78bdb-103">Gets the number of functions that were loaded by the application or forcibly loaded by the profiler.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="78bdb-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="78bdb-104">Syntax</span></span>  
  
```  
HRESULT GetCount([out] ULONG * pcelt);  
```  
  
## <a name="parameters"></a><span data-ttu-id="78bdb-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="78bdb-105">Parameters</span></span>  
 `celt`  
 <span data-ttu-id="78bdb-106">[out] Die Anzahl der Funktionen, die geladen wurden.</span><span class="sxs-lookup"><span data-stu-id="78bdb-106">[out] The number of functions that were loaded.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="78bdb-107">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="78bdb-107">Requirements</span></span>  
 <span data-ttu-id="78bdb-108">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="78bdb-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="78bdb-109">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="78bdb-109">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="78bdb-110">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="78bdb-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="78bdb-111">**.NET Framework-Versionen:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="78bdb-111">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="78bdb-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="78bdb-112">See also</span></span>

- [<span data-ttu-id="78bdb-113">ICorProfilerFunctionEnum-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="78bdb-113">ICorProfilerFunctionEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctionenum-interface.md)
- [<span data-ttu-id="78bdb-114">Profilerstellungsschnittstellen</span><span class="sxs-lookup"><span data-stu-id="78bdb-114">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
