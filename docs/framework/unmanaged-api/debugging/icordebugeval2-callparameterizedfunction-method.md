---
title: ICorDebugEval2::CallParameterizedFunction-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugEval2.CallParameterizedFunction
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugEval2::CallParameterizedFunction
helpviewer_keywords:
- ICorDebugEval2::CallParameterizedFunction method [.NET Framework debugging]
- CallParameterizedFunction method [.NET Framework debugging]
ms.assetid: 72f54a45-dbe6-4bb4-8c99-e879a27368e5
topic_type: apiref
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 055ded7f3309ff1011d1ca390daf353cba870376
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugeval2callparameterizedfunction-method"></a><span data-ttu-id="89fa2-102">ICorDebugEval2::CallParameterizedFunction-Methode</span><span class="sxs-lookup"><span data-stu-id="89fa2-102">ICorDebugEval2::CallParameterizedFunction Method</span></span>
<span data-ttu-id="89fa2-103">Richtet einen Aufruf der angegebenen ICorDebugFunction, die innerhalb einer Klasse geschachtelt werden können, deren Konstruktor akzeptiert <xref:System.Type> akzeptieren Parameter oder kann selbst <xref:System.Type> Parameter.</span><span class="sxs-lookup"><span data-stu-id="89fa2-103">Sets up a call to the specified ICorDebugFunction, which can be nested inside a class whose constructor takes <xref:System.Type> parameters, or can itself take <xref:System.Type> parameters.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="89fa2-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="89fa2-104">Syntax</span></span>  
  
```  
HRESULT CallParameterizedFunction (  
    [in] ICorDebugFunction     *pFunction,  
    [in] ULONG32               nTypeArgs,  
    [in, size_is(nTypeArgs)] ICorDebugType *ppTypeArgs[],  
    [in] ULONG32               nArgs,  
    [in, size_is(nArgs)] ICorDebugValue *ppArgs[]  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="89fa2-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="89fa2-105">Parameters</span></span>  
 `pFunction`  
 <span data-ttu-id="89fa2-106">[in] Ein Zeiger auf ein `ICorDebugFunction` Objekt, das die aufzurufende Funktion darstellt.</span><span class="sxs-lookup"><span data-stu-id="89fa2-106">[in] A pointer to an `ICorDebugFunction` object that represents the function to be called.</span></span>  
  
 `nTypeArgs`  
 <span data-ttu-id="89fa2-107">[in] Die Anzahl von Argumenten, die die Funktion akzeptiert.</span><span class="sxs-lookup"><span data-stu-id="89fa2-107">[in] The number of arguments that the function takes.</span></span>  
  
 `ppTypeArgs`  
 <span data-ttu-id="89fa2-108">[in] Ein Array von Zeigern, von denen jedes auf ein ICorDebugType verweist, die ein Funktionsargument für die darstellt.</span><span class="sxs-lookup"><span data-stu-id="89fa2-108">[in] An array of pointers, each of which points to an ICorDebugType object that represents a function argument.</span></span>  
  
 `nArgs`  
 <span data-ttu-id="89fa2-109">[in] Die Anzahl der Werte in der Funktion übergeben.</span><span class="sxs-lookup"><span data-stu-id="89fa2-109">[in] The number of values passed in the function.</span></span>  
  
 `ppArgs`  
 <span data-ttu-id="89fa2-110">[in] Ein Array von Zeigern, von denen jedes auf ein ICorDebugValue-Objekt verweist, die einen Wert darstellt, die an ein Funktion übergeben werden.</span><span class="sxs-lookup"><span data-stu-id="89fa2-110">[in] An array of pointers, each of which points to an ICorDebugValue object that represents a value passed in a function argument.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="89fa2-111">Hinweise</span><span class="sxs-lookup"><span data-stu-id="89fa2-111">Remarks</span></span>  
 <span data-ttu-id="89fa2-112">`CallParameterizedFunction`entspricht dem [ICorDebugEval:: CallFunction](../../../../docs/framework/unmanaged-api/debugging/icordebugeval-callfunction-method.md) mit dem Unterschied, dass die Funktion innerhalb einer Klasse mit Typparametern sein kann, kann selbst dauern Typparameter oder beides.</span><span class="sxs-lookup"><span data-stu-id="89fa2-112">`CallParameterizedFunction` is like [ICorDebugEval::CallFunction](../../../../docs/framework/unmanaged-api/debugging/icordebugeval-callfunction-method.md) except that the function may be inside a class with type parameters, may itself take type parameters, or both.</span></span> <span data-ttu-id="89fa2-113">Die Typargumente müssen zuerst für die Klasse, und klicken Sie dann für die Funktion erteilt werden.</span><span class="sxs-lookup"><span data-stu-id="89fa2-113">The type arguments should be given first for the class, and then for the function.</span></span>  
  
 <span data-ttu-id="89fa2-114">Wenn die Funktion in einer anderen Anwendungsdomäne ein Übergang erfolgen wird wird.</span><span class="sxs-lookup"><span data-stu-id="89fa2-114">If the function is in a different application domain, a transition will occur.</span></span> <span data-ttu-id="89fa2-115">Allerdings müssen alle Argumente von Typ und Wert in der Zielanwendungsdomäne sein.</span><span class="sxs-lookup"><span data-stu-id="89fa2-115">However, all type and value arguments must be in the target application domain.</span></span>  
  
 <span data-ttu-id="89fa2-116">Funktionsauswertung kann nur in bestimmten Szenarien ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="89fa2-116">Function evaluation can be performed only in limited scenarios.</span></span> <span data-ttu-id="89fa2-117">Wenn `CallParameterizedFunction` oder `ICorDebugEval::CallFunction` ein Fehler auftritt, das zurückgegebene HRESULT werden die allgemeinste mögliche Ursache für Fehler angeben.</span><span class="sxs-lookup"><span data-stu-id="89fa2-117">If `CallParameterizedFunction` or `ICorDebugEval::CallFunction` fails, the returned HRESULT will indicate the most general possible reason for failure.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="89fa2-118">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="89fa2-118">Requirements</span></span>  
 <span data-ttu-id="89fa2-119">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="89fa2-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="89fa2-120">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="89fa2-120">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="89fa2-121">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="89fa2-121">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="89fa2-122">**.NET Framework-Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="89fa2-122">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
