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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: c4baa4eb4da48b923ab0137ca25d9d819c94e33d
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61994031"
---
# <a name="icordebugthreadgetcurrentexception-method"></a><span data-ttu-id="c2a75-102">ICorDebugThread::GetCurrentException-Methode</span><span class="sxs-lookup"><span data-stu-id="c2a75-102">ICorDebugThread::GetCurrentException Method</span></span>
<span data-ttu-id="c2a75-103">Ruft einen Schnittstellenzeiger auf ein ICorDebugValue-Objekt, das eine Ausnahme darstellt, die derzeit von verwaltetem Code ausgelöst wird.</span><span class="sxs-lookup"><span data-stu-id="c2a75-103">Gets an interface pointer to an ICorDebugValue object that represents an exception that is currently being thrown by managed code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c2a75-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="c2a75-104">Syntax</span></span>  
  
```  
HRESULT GetCurrentException (  
    [out] ICorDebugValue **ppExceptionObject  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c2a75-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="c2a75-105">Parameters</span></span>  
 `ppExceptionObject`  
 <span data-ttu-id="c2a75-106">[out] Ein Zeiger auf die Adresse einer `ICorDebugValue` -Objekt, das die Ausnahme darstellt, die aktuell von ausgelöst wird, wird von verwaltetem Code.</span><span class="sxs-lookup"><span data-stu-id="c2a75-106">[out] A pointer to the address of an `ICorDebugValue` object that represents the exception that is currently being thrown by managed code.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c2a75-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="c2a75-107">Remarks</span></span>  
 <span data-ttu-id="c2a75-108">Die Exception-Objekt ist vorhanden, ab dem Zeitpunkt, der die Ausnahme, bis zum Ende ausgelöst wird der `catch` Block.</span><span class="sxs-lookup"><span data-stu-id="c2a75-108">The exception object will exist from the time the exception is thrown until the end of the `catch` block.</span></span> <span data-ttu-id="c2a75-109">Eine funktionsauswertung, die von den ICorDebugEval-Methoden ausgeführt wird, wird das Ausnahmeobjekt Setup lösche und stellen sie bei Abschluss.</span><span class="sxs-lookup"><span data-stu-id="c2a75-109">A function evaluation, which is performed by the ICorDebugEval methods, will clear out the exception object on setup and restore it on completion.</span></span>  
  
 <span data-ttu-id="c2a75-110">Ausnahmen können geschachtelt sein (beispielsweise, wenn eine Ausnahme in einem Filter oder eine funktionsauswertung ausgelöst wird), sodass mehrere ausstehende Ausnahmen in einem einzelnen Thread möglicherweise.</span><span class="sxs-lookup"><span data-stu-id="c2a75-110">Exceptions can be nested (for example, if an exception is thrown in a filter or in a function evaluation), so there may be multiple outstanding exceptions on a single thread.</span></span> <span data-ttu-id="c2a75-111">`GetCurrentException` Gibt die aktuelle Ausnahme zurück.</span><span class="sxs-lookup"><span data-stu-id="c2a75-111">`GetCurrentException` returns the most current exception.</span></span>  
  
 <span data-ttu-id="c2a75-112">Die Exception-Objekt und der Typ können über die gesamte Lebensdauer der Ausnahme ändern.</span><span class="sxs-lookup"><span data-stu-id="c2a75-112">The exception object and type may change throughout the life of the exception.</span></span> <span data-ttu-id="c2a75-113">Nachdem eine Ausnahme vom Typ X ausgelöst wird, kann die common Language Runtime (CLR) z. B. nicht über ausreichend Arbeitsspeicher und Stufen Sie ihn auf eine Out-of-Memory-Ausnahme.</span><span class="sxs-lookup"><span data-stu-id="c2a75-113">For example, after an exception of type x is thrown, the common language runtime (CLR) may run out of memory and promote it to an out-of-memory exception.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c2a75-114">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="c2a75-114">Requirements</span></span>  
 <span data-ttu-id="c2a75-115">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c2a75-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c2a75-116">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="c2a75-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="c2a75-117">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c2a75-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c2a75-118">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c2a75-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
