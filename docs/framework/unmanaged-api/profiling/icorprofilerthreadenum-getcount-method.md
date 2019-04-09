---
title: ICorProfilerThreadEnum::GetCount-Methode
ms.date: 03/30/2017
api_name:
- ICorProfilerThreadEnum.GetCount
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerThreadEnum::GetCount
helpviewer_keywords:
- ICorProfilerThreadEnum::GetCount method [.NET Framework profiling]
- GetCount method, ICorProfilerThreadEnum interface [.NET Framework profiling]
ms.assetid: d6dbdc4a-6115-455d-a3f3-704a81d3646b
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 8b02f70f22a7d35bf0fe7816a52c490f88b31217
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59218432"
---
# <a name="icorprofilerthreadenumgetcount-method"></a><span data-ttu-id="d27b8-102">ICorProfilerThreadEnum::GetCount-Methode</span><span class="sxs-lookup"><span data-stu-id="d27b8-102">ICorProfilerThreadEnum::GetCount Method</span></span>
<span data-ttu-id="d27b8-103">Ruft die Anzahl der Threads ab, die von der Anwendung verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="d27b8-103">Gets the number of threads that are used by the application.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d27b8-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="d27b8-104">Syntax</span></span>  
  
```  
HRESULT GetCount (    [out] ULONG * pcelt  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d27b8-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="d27b8-105">Parameters</span></span>  
 `celt`  
 <span data-ttu-id="d27b8-106">[out] Die Anzahl der Threads, die von der Anwendung verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="d27b8-106">[out] The number of threads used by the application.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d27b8-107">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="d27b8-107">Requirements</span></span>  
 <span data-ttu-id="d27b8-108">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d27b8-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d27b8-109">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="d27b8-109">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="d27b8-110">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d27b8-110">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="d27b8-111">.NET Framework-Versionen:</span><span class="sxs-lookup"><span data-stu-id="d27b8-111">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="d27b8-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d27b8-112">See also</span></span>

- [<span data-ttu-id="d27b8-113">ICorProfilerThreadEnum-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="d27b8-113">ICorProfilerThreadEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerthreadenum-interface.md)
- [<span data-ttu-id="d27b8-114">Profilerstellungsschnittstellen</span><span class="sxs-lookup"><span data-stu-id="d27b8-114">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
