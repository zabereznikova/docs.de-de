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
ms.openlocfilehash: 711fccd65379bc3e5e178869e7220dd84fd07fbe
ms.sourcegitcommit: d6bd7903d7d46698e9d89d3725f3bb4876891aa3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/13/2020
ms.locfileid: "83379702"
---
# <a name="icordebugthreadenumeratechains-method"></a><span data-ttu-id="ab342-102">ICorDebugThread::EnumerateChains-Methode</span><span class="sxs-lookup"><span data-stu-id="ab342-102">ICorDebugThread::EnumerateChains Method</span></span>
<span data-ttu-id="ab342-103">Ruft einen Schnittstellen Zeiger auf einen ICorDebugChainEnum-Enumerator ab, der alle Stapel Ketten in diesem ICorDebugThread-Objekt enthält.</span><span class="sxs-lookup"><span data-stu-id="ab342-103">Gets an interface pointer to an ICorDebugChainEnum enumerator that contains all the stack chains in this ICorDebugThread object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ab342-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="ab342-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumerateChains (  
    [out] ICorDebugChainEnum **ppChains  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ab342-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="ab342-105">Parameters</span></span>  
 `ppChains`  
 <span data-ttu-id="ab342-106">vorgenommen Ein Zeiger auf die Adresse eines `ICorDebugChainEnum` Objekts, das die Enumeration aller Stapel Ketten in diesem Thread ermöglicht, beginnend bei der aktiven (d. h. der neuesten) Kette.</span><span class="sxs-lookup"><span data-stu-id="ab342-106">[out] A pointer to the address of an `ICorDebugChainEnum` object that allows enumeration of all the stack chains in this thread, starting at the active (that is, the most recent) chain.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ab342-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="ab342-107">Remarks</span></span>  
 <span data-ttu-id="ab342-108">Die Stapel Kette stellt die physische aufrufsstapel für den Thread dar.</span><span class="sxs-lookup"><span data-stu-id="ab342-108">The stack chain represents the physical call stack for the thread.</span></span> <span data-ttu-id="ab342-109">In den folgenden Situationen wird eine Stapel Ketten Grenze erstellt:</span><span class="sxs-lookup"><span data-stu-id="ab342-109">The following circumstances create a stack chain boundary:</span></span>  
  
- <span data-ttu-id="ab342-110">Ein durchgängig verwalteter oder nicht verwalteter Übergang.</span><span class="sxs-lookup"><span data-stu-id="ab342-110">A managed-to-unmanaged or unmanaged-to-managed transition.</span></span>  
  
- <span data-ttu-id="ab342-111">Ein Kontextwechsel.</span><span class="sxs-lookup"><span data-stu-id="ab342-111">A context switch.</span></span>  
  
- <span data-ttu-id="ab342-112">Ein Debugger, der einen Benutzer Thread Hijacking hat.</span><span class="sxs-lookup"><span data-stu-id="ab342-112">A debugger hijacking of a user thread.</span></span>  
  
 <span data-ttu-id="ab342-113">Im einfachen Fall für einen Thread, der reinen verwalteten Code in einem einzigen Kontext ausführen wird, besteht eine 1:1-Entsprechung zwischen Threads und Stapel Ketten.</span><span class="sxs-lookup"><span data-stu-id="ab342-113">In the simple case for a thread that is running purely managed code in a single context, a one-to-one correspondence will exist between threads and stack chains.</span></span>  
  
 <span data-ttu-id="ab342-114">Möglicherweise möchte ein Debugger die physischen Aufruf Listen aller Threads in logischen Aufruf Listen neu anordnen.</span><span class="sxs-lookup"><span data-stu-id="ab342-114">A debugger may want to rearrange the physical call stacks of all threads into logical call stacks.</span></span> <span data-ttu-id="ab342-115">Dies würde dazu führen, dass alle Threads der Threads nach ihren Aufrufer-/Aufgerufener-Beziehungen sortiert und erneut gruppiert werden.</span><span class="sxs-lookup"><span data-stu-id="ab342-115">This would involve sorting all the threads' chains by their caller/callee relationships and regrouping them.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ab342-116">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="ab342-116">Requirements</span></span>  
 <span data-ttu-id="ab342-117">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ab342-117">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ab342-118">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="ab342-118">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="ab342-119">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ab342-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ab342-120">**.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ab342-120">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
