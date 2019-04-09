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
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59169285"
---
# <a name="icorprofilerfunctionenumgetcount-method"></a><span data-ttu-id="b1078-102">ICorProfilerFunctionEnum::GetCount-Methode</span><span class="sxs-lookup"><span data-stu-id="b1078-102">ICorProfilerFunctionEnum::GetCount Method</span></span>
<span data-ttu-id="b1078-103">Ruft die Anzahl der Funktionen ab, die von der Anwendung oder erzwungen vom Profiler geladen wurden.</span><span class="sxs-lookup"><span data-stu-id="b1078-103">Gets the number of functions that were loaded by the application or forcibly loaded by the profiler.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b1078-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="b1078-104">Syntax</span></span>  
  
```  
HRESULT GetCount([out] ULONG * pcelt);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b1078-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="b1078-105">Parameters</span></span>  
 `celt`  
 <span data-ttu-id="b1078-106">[out] Die Anzahl der Funktionen, die geladen wurden.</span><span class="sxs-lookup"><span data-stu-id="b1078-106">[out] The number of functions that were loaded.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b1078-107">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="b1078-107">Requirements</span></span>  
 <span data-ttu-id="b1078-108">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b1078-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b1078-109">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="b1078-109">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="b1078-110">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b1078-110">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="b1078-111">.NET Framework-Versionen:</span><span class="sxs-lookup"><span data-stu-id="b1078-111">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="b1078-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b1078-112">See also</span></span>

- [<span data-ttu-id="b1078-113">ICorProfilerFunctionEnum-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="b1078-113">ICorProfilerFunctionEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctionenum-interface.md)
- [<span data-ttu-id="b1078-114">Profilerstellungsschnittstellen</span><span class="sxs-lookup"><span data-stu-id="b1078-114">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
