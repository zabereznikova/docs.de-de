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
ms.openlocfilehash: e8dd9f21803021975f4651ba3e6e5f4d3da0ea82
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95674995"
---
# <a name="cor_prf_ex_clause_info-structure"></a><span data-ttu-id="d0bc5-102">COR_PRF_EX_CLAUSE_INFO-Struktur</span><span class="sxs-lookup"><span data-stu-id="d0bc5-102">COR_PRF_EX_CLAUSE_INFO Structure</span></span>

<span data-ttu-id="d0bc5-103">Speichert Informationen über eine bestimmte Instanz einer Ausnahmeklausel und deren zugeordneten Rahmen.</span><span class="sxs-lookup"><span data-stu-id="d0bc5-103">Stores information about a specific exception clause instance and its associated frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d0bc5-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="d0bc5-104">Syntax</span></span>  
  
```cpp  
typedef struct COR_PRF_EX_CLAUSE_INFO {  
    COR_PRF_CLAUSE_TYPE clauseType;  
    UINT_PTR programCounter;  
    UINT_PTR framePointer;  
    UINT_PTR shadowStackPointer;  
} COR_PRF_EX_CLAUSE_INFO;  
```  
  
## <a name="members"></a><span data-ttu-id="d0bc5-105">Member</span><span class="sxs-lookup"><span data-stu-id="d0bc5-105">Members</span></span>  
  
|<span data-ttu-id="d0bc5-106">Member</span><span class="sxs-lookup"><span data-stu-id="d0bc5-106">Member</span></span>|<span data-ttu-id="d0bc5-107">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="d0bc5-107">Description</span></span>|  
|------------|-----------------|  
|`clauseType`|<span data-ttu-id="d0bc5-108">Ein Wert der [COR_PRF_CLAUSE_TYPE](cor-prf-clause-type-enumeration.md) -Enumeration, die den Typ der Ausnahmeklausel angibt, den der Code soeben eingegeben oder Links eingegeben hat.</span><span class="sxs-lookup"><span data-stu-id="d0bc5-108">A value of the [COR_PRF_CLAUSE_TYPE](cor-prf-clause-type-enumeration.md) enumeration that specifies the type of exception clause the code just entered or left.</span></span>|  
|`programCounter`|<span data-ttu-id="d0bc5-109">Der Native Einstiegspunkt des Klauselhandlers – z. b. der Inhalt des x86 EIP-Registers.</span><span class="sxs-lookup"><span data-stu-id="d0bc5-109">The native entry point of the clause handler — for example, the contents of the X86 EIP register.</span></span>|  
|`framePointer`|<span data-ttu-id="d0bc5-110">Der Zeiger auf den logischen Frame für den klauselhandler – z. b. der Inhalt des x86-EBP-Registers.</span><span class="sxs-lookup"><span data-stu-id="d0bc5-110">The pointer to the logical frame for the clause handler — for example, the contents of the X86 EBP register.</span></span>|  
|`shadowStackPointer`|<span data-ttu-id="d0bc5-111">Der Zeiger auf den Schatten Stapel.</span><span class="sxs-lookup"><span data-stu-id="d0bc5-111">The pointer to the shadow stack.</span></span> <span data-ttu-id="d0bc5-112">Dieser Wert ist der Inhalt des BSP-Registers und gilt nur für ia64.</span><span class="sxs-lookup"><span data-stu-id="d0bc5-112">This value is the contents of the BSP register and applies only to IA64.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d0bc5-113">Hinweise</span><span class="sxs-lookup"><span data-stu-id="d0bc5-113">Remarks</span></span>  

 <span data-ttu-id="d0bc5-114">Wenn eine Ausnahme Benachrichtigung empfangen wird, kann [ICorProfilerInfo2:: GetNotifiedExceptionClauseInfo](icorprofilerinfo2-getnotifiedexceptionclauseinfo-method.md) verwendet werden, um die nativen Adress-und Frame Informationen für die Ausnahmeklausel (/Filter) zu erhalten, die `catch` / `finally` gerade ausgeführt wird oder gerade ausgeführt wurde.</span><span class="sxs-lookup"><span data-stu-id="d0bc5-114">When an exception notification is received, [ICorProfilerInfo2::GetNotifiedExceptionClauseInfo](icorprofilerinfo2-getnotifiedexceptionclauseinfo-method.md) can be used to get the native address and frame information for the exception clause (`catch`/`finally`/filter) that is about to be run or has just been run.</span></span>  
  
 <span data-ttu-id="d0bc5-115">Die Ausführung einer Exception-Klausel umfasst diese Rückrufe vom Common Language Runtime (CLR):</span><span class="sxs-lookup"><span data-stu-id="d0bc5-115">Execution of an exception clause involves these callbacks from the common language runtime (CLR):</span></span>  
  
- [<span data-ttu-id="d0bc5-116">ICorProfilerCallback:: exceptioncallcherenter</span><span class="sxs-lookup"><span data-stu-id="d0bc5-116">ICorProfilerCallback::ExceptionCatcherEnter</span></span>](icorprofilercallback-exceptioncatcherenter-method.md)  
  
- [<span data-ttu-id="d0bc5-117">ICorProfilerCallback:: ExceptionUnwindFinallyEnter</span><span class="sxs-lookup"><span data-stu-id="d0bc5-117">ICorProfilerCallback::ExceptionUnwindFinallyEnter</span></span>](icorprofilercallback-exceptionunwindfinallyenter-method.md)  
  
- [<span data-ttu-id="d0bc5-118">ICorProfilerCallback:: ExceptionSearchFilterEnter</span><span class="sxs-lookup"><span data-stu-id="d0bc5-118">ICorProfilerCallback::ExceptionSearchFilterEnter</span></span>](icorprofilercallback-exceptionsearchfilterenter-method.md)  
  
- [<span data-ttu-id="d0bc5-119">ICorProfilerCallback:: exceptioncallcherleave</span><span class="sxs-lookup"><span data-stu-id="d0bc5-119">ICorProfilerCallback::ExceptionCatcherLeave</span></span>](icorprofilercallback-exceptioncatcherleave-method.md)  
  
- [<span data-ttu-id="d0bc5-120">ICorProfilerCallback:: ExceptionUnwindFinallyLeave</span><span class="sxs-lookup"><span data-stu-id="d0bc5-120">ICorProfilerCallback::ExceptionUnwindFinallyLeave</span></span>](icorprofilercallback-exceptionunwindfinallyleave-method.md)  
  
- [<span data-ttu-id="d0bc5-121">ICorProfilerCallback:: ExceptionSearchFilterLeave</span><span class="sxs-lookup"><span data-stu-id="d0bc5-121">ICorProfilerCallback::ExceptionSearchFilterLeave</span></span>](icorprofilercallback-exceptionsearchfilterleave-method.md)  
  
## <a name="requirements"></a><span data-ttu-id="d0bc5-122">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="d0bc5-122">Requirements</span></span>  

 <span data-ttu-id="d0bc5-123">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d0bc5-123">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d0bc5-124">**Header:** Corprof. idl</span><span class="sxs-lookup"><span data-stu-id="d0bc5-124">**Header:** CorProf.idl</span></span>  
  
 <span data-ttu-id="d0bc5-125">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d0bc5-125">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d0bc5-126">**.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d0bc5-126">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d0bc5-127">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="d0bc5-127">See also</span></span>

- [<span data-ttu-id="d0bc5-128">Profilerstellungsstrukturen</span><span class="sxs-lookup"><span data-stu-id="d0bc5-128">Profiling Structures</span></span>](profiling-structures.md)
