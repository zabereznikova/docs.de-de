---
title: ICorProfilerFunctionEnum::Clone-Methode
ms.date: 03/30/2017
api_name:
- ICorProfilerFunctionEnum.Clone Method
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerFunctionEnum::Clone
helpviewer_keywords:
- ICorProfilerFunctionEnum::Clone method [.NET Framework profiling]
- Clone method, ICorProfilerFunctionEnum interface [.NET Framework profiling]
ms.assetid: 0c3d4835-e111-4e82-af6d-53f140b8f2c9
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: ce5d5187ee4082bb851fa24bbcda2b099e37b89f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33453130"
---
# <a name="icorprofilerfunctionenumclone-method"></a><span data-ttu-id="cdaeb-102">ICorProfilerFunctionEnum::Clone-Methode</span><span class="sxs-lookup"><span data-stu-id="cdaeb-102">ICorProfilerFunctionEnum::Clone Method</span></span>
<span data-ttu-id="cdaeb-103">Ruft einen Schnittstellenzeiger auf eine Kopie dieser [ICorProfilerFunctionEnum](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctionenum-interface.md) Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="cdaeb-103">Gets an interface pointer to a copy of this [ICorProfilerFunctionEnum](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctionenum-interface.md) interface.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cdaeb-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="cdaeb-104">Syntax</span></span>  
  
```  
HRESULT Clone([out] ICorProfilerFunctionEnum **ppEnum);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="cdaeb-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="cdaeb-105">Parameters</span></span>  
 `ppEnum`  
 <span data-ttu-id="cdaeb-106">[out] Ein Zeiger auf den Schnittstellenzeiger auf, die, die wiederum auf die Kopie von dieser verweist [ICorProfilerFunctionEnum](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctionenum-interface.md) Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="cdaeb-106">[out] A pointer to the interface pointer, which, in turn, points to the copy of this [ICorProfilerFunctionEnum](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctionenum-interface.md) interface.</span></span> <span data-ttu-id="cdaeb-107">Die Kopie des Enumerators behält ihren eigenen Enumerationszustand separat von diesem Enumerator.</span><span class="sxs-lookup"><span data-stu-id="cdaeb-107">The copy of the enumerator maintains its own enumeration state separately from this enumerator.</span></span> <span data-ttu-id="cdaeb-108">Allerdings ist die ursprüngliche Cursorposition der Kopie identisch mit der aktuellen Cursorposition des Enumerators.</span><span class="sxs-lookup"><span data-stu-id="cdaeb-108">However, the copy's initial cursor position is the same as this enumerator's current cursor position.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cdaeb-109">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="cdaeb-109">Requirements</span></span>  
 <span data-ttu-id="cdaeb-110">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="cdaeb-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cdaeb-111">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="cdaeb-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="cdaeb-112">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="cdaeb-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="cdaeb-113">**.NET Framework-Versionen:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cdaeb-113">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cdaeb-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="cdaeb-114">See Also</span></span>  
 [<span data-ttu-id="cdaeb-115">ICorProfilerFunctionEnum-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="cdaeb-115">ICorProfilerFunctionEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctionenum-interface.md)  
 [<span data-ttu-id="cdaeb-116">Profilerstellungsschnittstellen</span><span class="sxs-lookup"><span data-stu-id="cdaeb-116">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
