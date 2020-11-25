---
title: ICorDebugThread::GetCurrentException-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugThread.GetCurrentException
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugThread::GetCurrentException
helpviewer_keywords:
- ICorDebugThread::GetCurrentException method [.NET Framework debugging]
- GetCurrentException method [.NET Framework debugging]
ms.assetid: 331ed465-a195-4359-8584-b82c6098b29b
topic_type:
- apiref
ms.openlocfilehash: c21be7b062b7e2d4129bafabae004351442ab853
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95728055"
---
# <a name="icordebugthreadgetcurrentexception-method"></a><span data-ttu-id="580f0-102">ICorDebugThread::GetCurrentException-Methode</span><span class="sxs-lookup"><span data-stu-id="580f0-102">ICorDebugThread::GetCurrentException Method</span></span>

<span data-ttu-id="580f0-103">Ruft einen Schnittstellen Zeiger auf ein ICorDebugValue-Objekt ab, das eine Ausnahme darstellt, die zurzeit von verwaltetem Code ausgelöst wird.</span><span class="sxs-lookup"><span data-stu-id="580f0-103">Gets an interface pointer to an ICorDebugValue object that represents an exception that is currently being thrown by managed code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="580f0-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="580f0-104">Syntax</span></span>  
  
```cpp  
HRESULT GetCurrentException (  
    [out] ICorDebugValue **ppExceptionObject  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="580f0-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="580f0-105">Parameters</span></span>  

 `ppExceptionObject`  
 <span data-ttu-id="580f0-106">vorgenommen Ein Zeiger auf die Adresse eines `ICorDebugValue` Objekts, das die Ausnahme darstellt, die derzeit von verwaltetem Code ausgelöst wird.</span><span class="sxs-lookup"><span data-stu-id="580f0-106">[out] A pointer to the address of an `ICorDebugValue` object that represents the exception that is currently being thrown by managed code.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="580f0-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="580f0-107">Remarks</span></span>  

 <span data-ttu-id="580f0-108">Das Ausnahme Objekt ist von dem Zeitpunkt, an dem die Ausnahme ausgelöst wird, bis zum Ende des `catch` Blocks vorhanden.</span><span class="sxs-lookup"><span data-stu-id="580f0-108">The exception object will exist from the time the exception is thrown until the end of the `catch` block.</span></span> <span data-ttu-id="580f0-109">Bei einer Funktions Auswertung, die von den ICorDebugEval-Methoden ausgeführt wird, wird das Ausnahme Objekt beim Setup gelöscht und bei Abschluss wieder hergestellt.</span><span class="sxs-lookup"><span data-stu-id="580f0-109">A function evaluation, which is performed by the ICorDebugEval methods, will clear out the exception object on setup and restore it on completion.</span></span>  
  
 <span data-ttu-id="580f0-110">Ausnahmen können gescht werden (z. b. Wenn eine Ausnahme in einem Filter oder in einer Funktions Auswertung ausgelöst wird), sodass es möglicherweise mehrere ausstehende Ausnahmen in einem einzelnen Thread gibt.</span><span class="sxs-lookup"><span data-stu-id="580f0-110">Exceptions can be nested (for example, if an exception is thrown in a filter or in a function evaluation), so there may be multiple outstanding exceptions on a single thread.</span></span> <span data-ttu-id="580f0-111">`GetCurrentException` Gibt die aktuelle Ausnahme zurück.</span><span class="sxs-lookup"><span data-stu-id="580f0-111">`GetCurrentException` returns the most current exception.</span></span>  
  
 <span data-ttu-id="580f0-112">Das Ausnahme Objekt und der Typ können sich während der gesamten Lebensdauer der Ausnahme ändern.</span><span class="sxs-lookup"><span data-stu-id="580f0-112">The exception object and type may change throughout the life of the exception.</span></span> <span data-ttu-id="580f0-113">Wenn z. b. eine Ausnahme vom Typ "x" ausgelöst wird, kann die Common Language Runtime (CLR) nicht genügend Arbeitsspeicher aufweisen und Sie auf eine Ausnahme aufgrund von nicht genügend Arbeitsspeicher herauf Stufen.</span><span class="sxs-lookup"><span data-stu-id="580f0-113">For example, after an exception of type x is thrown, the common language runtime (CLR) may run out of memory and promote it to an out-of-memory exception.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="580f0-114">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="580f0-114">Requirements</span></span>  

 <span data-ttu-id="580f0-115">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="580f0-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="580f0-116">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="580f0-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="580f0-117">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="580f0-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="580f0-118">**.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="580f0-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
