---
title: ICorDebugThread::GetCurrentException-Methode
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
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: c18e2dfa68d425e5ec23d4573428018bc971f8b2
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugthreadgetcurrentexception-method"></a><span data-ttu-id="44d16-102">ICorDebugThread::GetCurrentException-Methode</span><span class="sxs-lookup"><span data-stu-id="44d16-102">ICorDebugThread::GetCurrentException Method</span></span>
<span data-ttu-id="44d16-103">Ruft einen Schnittstellenzeiger auf ein ICorDebugValue-Objekt, das eine Ausnahme darstellt, die derzeit von verwaltetem Code ausgelöst wird.</span><span class="sxs-lookup"><span data-stu-id="44d16-103">Gets an interface pointer to an ICorDebugValue object that represents an exception that is currently being thrown by managed code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="44d16-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="44d16-104">Syntax</span></span>  
  
```  
HRESULT GetCurrentException (  
    [out] ICorDebugValue **ppExceptionObject  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="44d16-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="44d16-105">Parameters</span></span>  
 `ppExceptionObject`  
 <span data-ttu-id="44d16-106">[out] Ein Zeiger auf die Adresse des ein `ICorDebugValue` Objekt, das die Ausnahme darstellt, die derzeit von ausgelöst wird, verwalteten Code.</span><span class="sxs-lookup"><span data-stu-id="44d16-106">[out] A pointer to the address of an `ICorDebugValue` object that represents the exception that is currently being thrown by managed code.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="44d16-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="44d16-107">Remarks</span></span>  
 <span data-ttu-id="44d16-108">Das Ausnahmeobjekt ist vorhanden, ab dem Zeitpunkt, der die Ausnahme, bis zum Ende ausgelöst wird der `catch` Block.</span><span class="sxs-lookup"><span data-stu-id="44d16-108">The exception object will exist from the time the exception is thrown until the end of the `catch` block.</span></span> <span data-ttu-id="44d16-109">Eine funktionsauswertung, die von den ICorDebugEval-Methoden erfolgt, wird das Ausnahmeobjekt Setup löschen und bei Abschluss wiederherstellen.</span><span class="sxs-lookup"><span data-stu-id="44d16-109">A function evaluation, which is performed by the ICorDebugEval methods, will clear out the exception object on setup and restore it on completion.</span></span>  
  
 <span data-ttu-id="44d16-110">Ausnahmen können geschachtelt sein (beispielsweise, wenn eine Ausnahme in einen Filter oder eine funktionsauswertung ausgelöst wird), sodass mehrere ausstehende Ausnahmen in einem einzelnen Thread.</span><span class="sxs-lookup"><span data-stu-id="44d16-110">Exceptions can be nested (for example, if an exception is thrown in a filter or in a function evaluation), so there may be multiple outstanding exceptions on a single thread.</span></span> <span data-ttu-id="44d16-111">`GetCurrentException`Gibt die aktuelle Ausnahme zurück.</span><span class="sxs-lookup"><span data-stu-id="44d16-111">`GetCurrentException` returns the most current exception.</span></span>  
  
 <span data-ttu-id="44d16-112">Die Lebensdauer der Ausnahme können die Exception-Objekt und den Typ ändern.</span><span class="sxs-lookup"><span data-stu-id="44d16-112">The exception object and type may change throughout the life of the exception.</span></span> <span data-ttu-id="44d16-113">Nachdem eine Ausnahme vom Typ X ausgelöst wird, kann die common Language Runtime (CLR) z. B. nicht über ausreichend Arbeitsspeicher und höher stufen sie auf eine Out-of-Memory-Ausnahme.</span><span class="sxs-lookup"><span data-stu-id="44d16-113">For example, after an exception of type x is thrown, the common language runtime (CLR) may run out of memory and promote it to an out-of-memory exception.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="44d16-114">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="44d16-114">Requirements</span></span>  
 <span data-ttu-id="44d16-115">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="44d16-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="44d16-116">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="44d16-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="44d16-117">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="44d16-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="44d16-118">**.NET Framework-Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="44d16-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
