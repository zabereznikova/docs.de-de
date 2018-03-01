---
title: ICorDebugThread::EnumerateChains-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- ICorDebugThread.EnumerateChains
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugThread::EnumerateChains
helpviewer_keywords:
- EnumerateChains method [.NET Framework debugging]
- ICorDebugThread::EnumerateChains method [.NET Framework debugging]
ms.assetid: ec00bc21-117e-4acd-9301-2cfafd5be8d3
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 8e6a9637edb4a846b4d10dd6565533a9219ad558
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugthreadenumeratechains-method"></a><span data-ttu-id="b926e-102">ICorDebugThread::EnumerateChains-Methode</span><span class="sxs-lookup"><span data-stu-id="b926e-102">ICorDebugThread::EnumerateChains Method</span></span>
<span data-ttu-id="b926e-103">Ruft einen Schnittstellenzeiger auf einem ICorDebugChainEnum-Enumerator, der alle Stapelketten in diesem ICorDebugThread-Objekt enthält.</span><span class="sxs-lookup"><span data-stu-id="b926e-103">Gets an interface pointer to an ICorDebugChainEnum enumerator that contains all the stack chains in this ICorDebugThread object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b926e-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="b926e-104">Syntax</span></span>  
  
```  
HRESULT EnumerateChains (  
    [out] ICorDebugChainEnum **ppChains  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="b926e-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="b926e-105">Parameters</span></span>  
 `ppChains`  
 <span data-ttu-id="b926e-106">[out] Ein Zeiger auf die Adresse des ein `ICorDebugChainEnum` Objekt, das Enumeration aller ermöglicht, die in diesem Thread, beginnend mit der Kette aktiv (d. h. die aktuellste) verkettet ist.</span><span class="sxs-lookup"><span data-stu-id="b926e-106">[out] A pointer to the address of an `ICorDebugChainEnum` object that allows enumeration of all the stack chains in this thread, starting at the active (that is, the most recent) chain.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b926e-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="b926e-107">Remarks</span></span>  
 <span data-ttu-id="b926e-108">Die Stapelkette stellt die physische Aufrufliste für den Thread dar.</span><span class="sxs-lookup"><span data-stu-id="b926e-108">The stack chain represents the physical call stack for the thread.</span></span> <span data-ttu-id="b926e-109">Die folgenden Situationen erstellen Stapel Kette Grenze:</span><span class="sxs-lookup"><span data-stu-id="b926e-109">The following circumstances create a stack chain boundary:</span></span>  
  
-   <span data-ttu-id="b926e-110">Ein Übergang verwaltet, nicht verwaltete oder nicht verwaltet zu verwaltet.</span><span class="sxs-lookup"><span data-stu-id="b926e-110">A managed-to-unmanaged or unmanaged-to-managed transition.</span></span>  
  
-   <span data-ttu-id="b926e-111">Ein Wechsel des Ausführungskontexts.</span><span class="sxs-lookup"><span data-stu-id="b926e-111">A context switch.</span></span>  
  
-   <span data-ttu-id="b926e-112">Ein debugger Übernahme eines Benutzerthreads.</span><span class="sxs-lookup"><span data-stu-id="b926e-112">A debugger hijacking of a user thread.</span></span>  
  
 <span data-ttu-id="b926e-113">Im einfachen Fall für einen Thread, der ausschließlich verwalteten Code in einem einzigen Kontext ausgeführt wird, wird eine 1: 1-Entsprechung zwischen Threads und Stapelketten vorhanden sein.</span><span class="sxs-lookup"><span data-stu-id="b926e-113">In the simple case for a thread that is running purely managed code in a single context, a one-to-one correspondence will exist between threads and stack chains.</span></span>  
  
 <span data-ttu-id="b926e-114">Ein Debugger möchte die physischen Aufruflisten aller Threads in logischen Aufruflisten neu anzuordnen.</span><span class="sxs-lookup"><span data-stu-id="b926e-114">A debugger may want to rearrange the physical call stacks of all threads into logical call stacks.</span></span> <span data-ttu-id="b926e-115">Dies würde das Sortieren der Threads Ketten ihre Aufrufer-/Aufgerufener-Beziehungen und liefern ihnen.</span><span class="sxs-lookup"><span data-stu-id="b926e-115">This would involve sorting all the threads' chains by their caller/callee relationships and regrouping them.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b926e-116">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="b926e-116">Requirements</span></span>  
 <span data-ttu-id="b926e-117">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b926e-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b926e-118">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="b926e-118">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="b926e-119">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b926e-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b926e-120">**.NET Framework-Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b926e-120">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
