---
title: COR_PRF_EX_CLAUSE_INFO-Struktur
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: COR_PRF_EX_CLAUSE_INFO
api_location: mscorwks.dll
api_type: COM
f1_keywords: COR_PRF_EX_CLAUSE_INFO
helpviewer_keywords: COR_PRF_EX_CLAUSE_INFO structure [.NET Framework profiling]
ms.assetid: 7d0d6fb7-bc9d-40f0-8163-c0d162eaba7d
topic_type: apiref
caps.latest.revision: "11"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 65025384aa94ac363336bae7f37f8ea88a3bab67
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="corprfexclauseinfo-structure"></a><span data-ttu-id="7b730-102">COR_PRF_EX_CLAUSE_INFO-Struktur</span><span class="sxs-lookup"><span data-stu-id="7b730-102">COR_PRF_EX_CLAUSE_INFO Structure</span></span>
<span data-ttu-id="7b730-103">Speichert Informationen über eine bestimmte Instanz einer Ausnahmeklausel und deren zugeordneten Rahmen.</span><span class="sxs-lookup"><span data-stu-id="7b730-103">Stores information about a specific exception clause instance and its associated frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7b730-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="7b730-104">Syntax</span></span>  
  
```  
typedef struct COR_PRF_EX_CLAUSE_INFO {  
    COR_PRF_CLAUSE_TYPE clauseType;  
    UINT_PTR programCounter;  
    UINT_PTR framePointer;  
    UINT_PTR shadowStackPointer;  
} COR_PRF_EX_CLAUSE_INFO;  
```  
  
## <a name="members"></a><span data-ttu-id="7b730-105">Member</span><span class="sxs-lookup"><span data-stu-id="7b730-105">Members</span></span>  
  
|<span data-ttu-id="7b730-106">Member</span><span class="sxs-lookup"><span data-stu-id="7b730-106">Member</span></span>|<span data-ttu-id="7b730-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="7b730-107">Description</span></span>|  
|------------|-----------------|  
|`clauseType`|<span data-ttu-id="7b730-108">Der Wert der [COR_PRF_CLAUSE_TYPE](../../../../docs/framework/unmanaged-api/profiling/cor-prf-clause-type-enumeration.md) -Enumeration, der den Typ der Ausnahmeklausel an der Code gerade eben eingegeben oder zurückgelassen angibt.</span><span class="sxs-lookup"><span data-stu-id="7b730-108">A value of the [COR_PRF_CLAUSE_TYPE](../../../../docs/framework/unmanaged-api/profiling/cor-prf-clause-type-enumeration.md) enumeration that specifies the type of exception clause the code just entered or left.</span></span>|  
|`programCounter`|<span data-ttu-id="7b730-109">Den systemeigenen Einstiegspunkt des Handlers Klausel – z. B. den Inhalt des Registers X86 EIP.</span><span class="sxs-lookup"><span data-stu-id="7b730-109">The native entry point of the clause handler — for example, the contents of the X86 EIP register.</span></span>|  
|`framePointer`|<span data-ttu-id="7b730-110">Der Zeiger auf den logischen Frame für den Handler Klausel – z. B. den Inhalt des Registers X86 EBP.</span><span class="sxs-lookup"><span data-stu-id="7b730-110">The pointer to the logical frame for the clause handler — for example, the contents of the X86 EBP register.</span></span>|  
|`shadowStackPointer`|<span data-ttu-id="7b730-111">Der Zeiger auf den Schattenstapel.</span><span class="sxs-lookup"><span data-stu-id="7b730-111">The pointer to the shadow stack.</span></span> <span data-ttu-id="7b730-112">Dieser Wert ist der Inhalt des Registers BSP und gilt nur für IA64.</span><span class="sxs-lookup"><span data-stu-id="7b730-112">This value is the contents of the BSP register and applies only to IA64.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="7b730-113">Hinweise</span><span class="sxs-lookup"><span data-stu-id="7b730-113">Remarks</span></span>  
 <span data-ttu-id="7b730-114">Wenn eine Ausnahme Benachrichtigung empfangen wird, [ICorProfilerInfo2:: GetNotifiedExceptionClauseInfo](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getnotifiedexceptionclauseinfo-method.md) dienen zum Abrufen der systemeigenen Adresse und Frame-Informationen für die Ausnahmeklausel (`catch` / `finally`/Filtern), die auszuführende ist oder gerade ausgeführt wurde.</span><span class="sxs-lookup"><span data-stu-id="7b730-114">When an exception notification is received, [ICorProfilerInfo2::GetNotifiedExceptionClauseInfo](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getnotifiedexceptionclauseinfo-method.md) can be used to get the native address and frame information for the exception clause (`catch`/`finally`/filter) that is about to be run or has just been run.</span></span>  
  
 <span data-ttu-id="7b730-115">Die Ausführung einer Ausnahmeklausel umfasst diese Rückrufe aus die common Language Runtime (CLR):</span><span class="sxs-lookup"><span data-stu-id="7b730-115">Execution of an exception clause involves these callbacks from the common language runtime (CLR):</span></span>  
  
-   [<span data-ttu-id="7b730-116">ICorProfilerCallback:: ExceptionCatcherEnter</span><span class="sxs-lookup"><span data-stu-id="7b730-116">ICorProfilerCallback::ExceptionCatcherEnter</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptioncatcherenter-method.md)  
  
-   [<span data-ttu-id="7b730-117">ICorProfilerCallback:: ExceptionUnwindFinallyEnter</span><span class="sxs-lookup"><span data-stu-id="7b730-117">ICorProfilerCallback::ExceptionUnwindFinallyEnter</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionunwindfinallyenter-method.md)  
  
-   [<span data-ttu-id="7b730-118">ICorProfilerCallback:: ExceptionSearchFilterEnter</span><span class="sxs-lookup"><span data-stu-id="7b730-118">ICorProfilerCallback::ExceptionSearchFilterEnter</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionsearchfilterenter-method.md)  
  
-   [<span data-ttu-id="7b730-119">ICorProfilerCallback:: ExceptionCatcherLeave</span><span class="sxs-lookup"><span data-stu-id="7b730-119">ICorProfilerCallback::ExceptionCatcherLeave</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptioncatcherleave-method.md)  
  
-   [<span data-ttu-id="7b730-120">ICorProfilerCallback:: ExceptionUnwindFinallyLeave</span><span class="sxs-lookup"><span data-stu-id="7b730-120">ICorProfilerCallback::ExceptionUnwindFinallyLeave</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionunwindfinallyleave-method.md)  
  
-   [<span data-ttu-id="7b730-121">ICorProfilerCallback:: ExceptionSearchFilterLeave</span><span class="sxs-lookup"><span data-stu-id="7b730-121">ICorProfilerCallback::ExceptionSearchFilterLeave</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionsearchfilterleave-method.md)  
  
## <a name="requirements"></a><span data-ttu-id="7b730-122">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="7b730-122">Requirements</span></span>  
 <span data-ttu-id="7b730-123">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7b730-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7b730-124">**Header:** CorProf.idl</span><span class="sxs-lookup"><span data-stu-id="7b730-124">**Header:** CorProf.idl</span></span>  
  
 <span data-ttu-id="7b730-125">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="7b730-125">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="7b730-126">**.NET Framework-Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7b730-126">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7b730-127">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="7b730-127">See Also</span></span>  
 [<span data-ttu-id="7b730-128">Profilerstellungsstrukturen</span><span class="sxs-lookup"><span data-stu-id="7b730-128">Profiling Structures</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-structures.md)
