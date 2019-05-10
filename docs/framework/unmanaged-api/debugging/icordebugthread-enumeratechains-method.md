---
title: ICorDebugThread::EnumerateChains-Methode
ms.date: 03/30/2017
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: f131f7566376d6474f3189d5eb612b30bec2e2b7
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/28/2019
ms.locfileid: "64648437"
---
# <a name="icordebugthreadenumeratechains-method"></a><span data-ttu-id="ada87-102">ICorDebugThread::EnumerateChains-Methode</span><span class="sxs-lookup"><span data-stu-id="ada87-102">ICorDebugThread::EnumerateChains Method</span></span>
<span data-ttu-id="ada87-103">Ruft einen Schnittstellenzeiger auf einem ICorDebugChainEnum-Enumerator, der alle Stapelketten in diesem ICorDebugThread-Objekt enthält.</span><span class="sxs-lookup"><span data-stu-id="ada87-103">Gets an interface pointer to an ICorDebugChainEnum enumerator that contains all the stack chains in this ICorDebugThread object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ada87-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="ada87-104">Syntax</span></span>  
  
```  
HRESULT EnumerateChains (  
    [out] ICorDebugChainEnum **ppChains  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ada87-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="ada87-105">Parameters</span></span>  
 `ppChains`  
 <span data-ttu-id="ada87-106">[out] Ein Zeiger auf die Adresse einer `ICorDebugChainEnum` -Objekt, das ermöglicht die Enumeration des alle-Stapels in diesem Thread, beginnend ab der Kette aktiv (d. h. die aktuellste) verkettet.</span><span class="sxs-lookup"><span data-stu-id="ada87-106">[out] A pointer to the address of an `ICorDebugChainEnum` object that allows enumeration of all the stack chains in this thread, starting at the active (that is, the most recent) chain.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ada87-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="ada87-107">Remarks</span></span>  
 <span data-ttu-id="ada87-108">Die Stapelkette stellt die physische Aufrufliste für den Thread dar.</span><span class="sxs-lookup"><span data-stu-id="ada87-108">The stack chain represents the physical call stack for the thread.</span></span> <span data-ttu-id="ada87-109">Die folgenden Situationen erstellen Sie eine Kette-Grenze von Stack:</span><span class="sxs-lookup"><span data-stu-id="ada87-109">The following circumstances create a stack chain boundary:</span></span>  
  
- <span data-ttu-id="ada87-110">Ein Übergang verwalteten zum nicht verwalteten oder nicht verwaltet zu verwaltet.</span><span class="sxs-lookup"><span data-stu-id="ada87-110">A managed-to-unmanaged or unmanaged-to-managed transition.</span></span>  
  
- <span data-ttu-id="ada87-111">Ein Wechsel des Ausführungskontexts.</span><span class="sxs-lookup"><span data-stu-id="ada87-111">A context switch.</span></span>  
  
- <span data-ttu-id="ada87-112">Ein debugger-Hijacking eines Benutzerthreads.</span><span class="sxs-lookup"><span data-stu-id="ada87-112">A debugger hijacking of a user thread.</span></span>  
  
 <span data-ttu-id="ada87-113">Im einfachen Fall für einen Thread, der ausschließlich verwalteten Code in einem einzelnen Kontext ausgeführt wird, wird eine 1: 1-Entsprechung zwischen Threads und Stapelketten vorhanden.</span><span class="sxs-lookup"><span data-stu-id="ada87-113">In the simple case for a thread that is running purely managed code in a single context, a one-to-one correspondence will exist between threads and stack chains.</span></span>  
  
 <span data-ttu-id="ada87-114">Ein Debugger sollten die physischen Aufruflisten aller Threads in logischen Aufruflisten neu anzuordnen.</span><span class="sxs-lookup"><span data-stu-id="ada87-114">A debugger may want to rearrange the physical call stacks of all threads into logical call stacks.</span></span> <span data-ttu-id="ada87-115">Dies würde betreffen, sortieren die Threads Ketten nach deren Aufrufer-/Aufgerufener-Beziehungen und liefern sie.</span><span class="sxs-lookup"><span data-stu-id="ada87-115">This would involve sorting all the threads' chains by their caller/callee relationships and regrouping them.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ada87-116">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="ada87-116">Requirements</span></span>  
 <span data-ttu-id="ada87-117">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ada87-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ada87-118">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="ada87-118">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="ada87-119">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ada87-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ada87-120">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ada87-120">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
