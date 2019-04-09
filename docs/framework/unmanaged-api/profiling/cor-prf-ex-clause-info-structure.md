---
title: COR_PRF_EX_CLAUSE_INFO-Struktur
ms.date: 03/30/2017
api_name:
- COR_PRF_EX_CLAUSE_INFO
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- COR_PRF_EX_CLAUSE_INFO
helpviewer_keywords:
- COR_PRF_EX_CLAUSE_INFO structure [.NET Framework profiling]
ms.assetid: 7d0d6fb7-bc9d-40f0-8163-c0d162eaba7d
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 5e12410ab9886055dca8c3f9103c1e56475c2d5e
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59140347"
---
# <a name="corprfexclauseinfo-structure"></a><span data-ttu-id="5818e-102">COR_PRF_EX_CLAUSE_INFO-Struktur</span><span class="sxs-lookup"><span data-stu-id="5818e-102">COR_PRF_EX_CLAUSE_INFO Structure</span></span>
<span data-ttu-id="5818e-103">Speichert Informationen über eine bestimmte Instanz einer Ausnahmeklausel und deren zugeordneten Rahmen.</span><span class="sxs-lookup"><span data-stu-id="5818e-103">Stores information about a specific exception clause instance and its associated frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5818e-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="5818e-104">Syntax</span></span>  
  
```  
typedef struct COR_PRF_EX_CLAUSE_INFO {  
    COR_PRF_CLAUSE_TYPE clauseType;  
    UINT_PTR programCounter;  
    UINT_PTR framePointer;  
    UINT_PTR shadowStackPointer;  
} COR_PRF_EX_CLAUSE_INFO;  
```  
  
## <a name="members"></a><span data-ttu-id="5818e-105">Member</span><span class="sxs-lookup"><span data-stu-id="5818e-105">Members</span></span>  
  
|<span data-ttu-id="5818e-106">Member</span><span class="sxs-lookup"><span data-stu-id="5818e-106">Member</span></span>|<span data-ttu-id="5818e-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="5818e-107">Description</span></span>|  
|------------|-----------------|  
|`clauseType`|<span data-ttu-id="5818e-108">Der Wert der [COR_PRF_CLAUSE_TYPE](../../../../docs/framework/unmanaged-api/profiling/cor-prf-clause-type-enumeration.md) -Enumeration, der den Typ der Ausnahmeklausel der Code gerade eingegeben haben oder von Links angibt.</span><span class="sxs-lookup"><span data-stu-id="5818e-108">A value of the [COR_PRF_CLAUSE_TYPE](../../../../docs/framework/unmanaged-api/profiling/cor-prf-clause-type-enumeration.md) enumeration that specifies the type of exception clause the code just entered or left.</span></span>|  
|`programCounter`|<span data-ttu-id="5818e-109">Den systemeigenen Einstiegspunkt des Handlers Klausel – z. B. den Inhalt des Registers X86 EIP.</span><span class="sxs-lookup"><span data-stu-id="5818e-109">The native entry point of the clause handler — for example, the contents of the X86 EIP register.</span></span>|  
|`framePointer`|<span data-ttu-id="5818e-110">Der Zeiger auf den logischen Frame für den Handler für die Klausel, z. B. den Inhalt des Registers X86 EBP.</span><span class="sxs-lookup"><span data-stu-id="5818e-110">The pointer to the logical frame for the clause handler — for example, the contents of the X86 EBP register.</span></span>|  
|`shadowStackPointer`|<span data-ttu-id="5818e-111">Der Zeiger auf den Schattenstapel.</span><span class="sxs-lookup"><span data-stu-id="5818e-111">The pointer to the shadow stack.</span></span> <span data-ttu-id="5818e-112">Dieser Wert ist der Inhalt des Registers BSP und gilt nur für IA64.</span><span class="sxs-lookup"><span data-stu-id="5818e-112">This value is the contents of the BSP register and applies only to IA64.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="5818e-113">Hinweise</span><span class="sxs-lookup"><span data-stu-id="5818e-113">Remarks</span></span>  
 <span data-ttu-id="5818e-114">Wenn eine Ausnahme Benachrichtigung empfangen wird, [ICorProfilerInfo2:: GetNotifiedExceptionClauseInfo](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getnotifiedexceptionclauseinfo-method.md) können verwendet werden, um die systemeigenen und der Framezeiger Informationen für die Ausnahmeklausel zu erhalten (`catch` / `finally`/Filtern), wird gleich ausgeführt werden oder gerade ausgeführt wurde.</span><span class="sxs-lookup"><span data-stu-id="5818e-114">When an exception notification is received, [ICorProfilerInfo2::GetNotifiedExceptionClauseInfo](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getnotifiedexceptionclauseinfo-method.md) can be used to get the native address and frame information for the exception clause (`catch`/`finally`/filter) that is about to be run or has just been run.</span></span>  
  
 <span data-ttu-id="5818e-115">Die Ausführung einer Ausnahmeklausel umfasst diese Rückrufe von der common Language Runtime (CLR):</span><span class="sxs-lookup"><span data-stu-id="5818e-115">Execution of an exception clause involves these callbacks from the common language runtime (CLR):</span></span>  
  
-   [<span data-ttu-id="5818e-116">ICorProfilerCallback::ExceptionCatcherEnter</span><span class="sxs-lookup"><span data-stu-id="5818e-116">ICorProfilerCallback::ExceptionCatcherEnter</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptioncatcherenter-method.md)  
  
-   [<span data-ttu-id="5818e-117">ICorProfilerCallback::ExceptionUnwindFinallyEnter</span><span class="sxs-lookup"><span data-stu-id="5818e-117">ICorProfilerCallback::ExceptionUnwindFinallyEnter</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionunwindfinallyenter-method.md)  
  
-   [<span data-ttu-id="5818e-118">ICorProfilerCallback::ExceptionSearchFilterEnter</span><span class="sxs-lookup"><span data-stu-id="5818e-118">ICorProfilerCallback::ExceptionSearchFilterEnter</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionsearchfilterenter-method.md)  
  
-   [<span data-ttu-id="5818e-119">ICorProfilerCallback::ExceptionCatcherLeave</span><span class="sxs-lookup"><span data-stu-id="5818e-119">ICorProfilerCallback::ExceptionCatcherLeave</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptioncatcherleave-method.md)  
  
-   [<span data-ttu-id="5818e-120">ICorProfilerCallback::ExceptionUnwindFinallyLeave</span><span class="sxs-lookup"><span data-stu-id="5818e-120">ICorProfilerCallback::ExceptionUnwindFinallyLeave</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionunwindfinallyleave-method.md)  
  
-   [<span data-ttu-id="5818e-121">ICorProfilerCallback::ExceptionSearchFilterLeave</span><span class="sxs-lookup"><span data-stu-id="5818e-121">ICorProfilerCallback::ExceptionSearchFilterLeave</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionsearchfilterleave-method.md)  
  
## <a name="requirements"></a><span data-ttu-id="5818e-122">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="5818e-122">Requirements</span></span>  
 <span data-ttu-id="5818e-123">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5818e-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5818e-124">**Header:** CorProf.idl</span><span class="sxs-lookup"><span data-stu-id="5818e-124">**Header:** CorProf.idl</span></span>  
  
 <span data-ttu-id="5818e-125">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5818e-125">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="5818e-126">.NET Framework-Versionen:</span><span class="sxs-lookup"><span data-stu-id="5818e-126">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="5818e-127">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="5818e-127">See also</span></span>

- [<span data-ttu-id="5818e-128">Profilerstellungsstrukturen</span><span class="sxs-lookup"><span data-stu-id="5818e-128">Profiling Structures</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-structures.md)
