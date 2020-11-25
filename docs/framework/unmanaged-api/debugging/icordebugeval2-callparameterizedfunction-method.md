---
title: ICorDebugEval2::CallParameterizedFunction-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugEval2.CallParameterizedFunction
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugEval2::CallParameterizedFunction
helpviewer_keywords:
- ICorDebugEval2::CallParameterizedFunction method [.NET Framework debugging]
- CallParameterizedFunction method [.NET Framework debugging]
ms.assetid: 72f54a45-dbe6-4bb4-8c99-e879a27368e5
topic_type:
- apiref
ms.openlocfilehash: c36dec80b6885b0ee56670b94dbd0b155a9710b4
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95729706"
---
# <a name="icordebugeval2callparameterizedfunction-method"></a><span data-ttu-id="a4246-102">ICorDebugEval2::CallParameterizedFunction-Methode</span><span class="sxs-lookup"><span data-stu-id="a4246-102">ICorDebugEval2::CallParameterizedFunction Method</span></span>

<span data-ttu-id="a4246-103">Richtet einen Aufrufen der angegebenen ICorDebugFunction ein, die in einer Klasse geschachtelt werden kann, deren Konstruktor <xref:System.Type> Parameter annimmt, oder selbst Parameter annehmen kann <xref:System.Type> .</span><span class="sxs-lookup"><span data-stu-id="a4246-103">Sets up a call to the specified ICorDebugFunction, which can be nested inside a class whose constructor takes <xref:System.Type> parameters, or can itself take <xref:System.Type> parameters.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a4246-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="a4246-104">Syntax</span></span>  
  
```cpp  
HRESULT CallParameterizedFunction (  
    [in] ICorDebugFunction     *pFunction,  
    [in] ULONG32               nTypeArgs,  
    [in, size_is(nTypeArgs)] ICorDebugType *ppTypeArgs[],  
    [in] ULONG32               nArgs,  
    [in, size_is(nArgs)] ICorDebugValue *ppArgs[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a4246-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="a4246-105">Parameters</span></span>  

 `pFunction`  
 <span data-ttu-id="a4246-106">in Ein Zeiger auf ein `ICorDebugFunction` Objekt, das die aufzurufende Funktion darstellt.</span><span class="sxs-lookup"><span data-stu-id="a4246-106">[in] A pointer to an `ICorDebugFunction` object that represents the function to be called.</span></span>  
  
 `nTypeArgs`  
 <span data-ttu-id="a4246-107">in Die Anzahl von Argumenten, die von der Funktion benötigt werden.</span><span class="sxs-lookup"><span data-stu-id="a4246-107">[in] The number of arguments that the function takes.</span></span>  
  
 `ppTypeArgs`  
 <span data-ttu-id="a4246-108">in Ein Array von Zeigern, von denen jedes auf ein ICorDebugType-Objekt verweist, das ein Funktions Argument darstellt.</span><span class="sxs-lookup"><span data-stu-id="a4246-108">[in] An array of pointers, each of which points to an ICorDebugType object that represents a function argument.</span></span>  
  
 `nArgs`  
 <span data-ttu-id="a4246-109">in Die Anzahl der in der Funktion bestandenen Werte.</span><span class="sxs-lookup"><span data-stu-id="a4246-109">[in] The number of values passed in the function.</span></span>  
  
 `ppArgs`  
 <span data-ttu-id="a4246-110">in Ein Array von Zeigern, von denen jedes auf ein ICorDebug Value-Objekt verweist, das einen Wert darstellt, der in einem Funktions Argument übergeben wird.</span><span class="sxs-lookup"><span data-stu-id="a4246-110">[in] An array of pointers, each of which points to an ICorDebugValue object that represents a value passed in a function argument.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a4246-111">Hinweise</span><span class="sxs-lookup"><span data-stu-id="a4246-111">Remarks</span></span>  

 <span data-ttu-id="a4246-112">`CallParameterizedFunction` ist wie [ICorDebugEval:: CallFunction](icordebugeval-callfunction-method.md) , mit dem Unterschied, dass sich die Funktion in einer Klasse mit Typparametern befinden kann, dass Sie selbst Typparameter oder beides annehmen kann.</span><span class="sxs-lookup"><span data-stu-id="a4246-112">`CallParameterizedFunction` is like [ICorDebugEval::CallFunction](icordebugeval-callfunction-method.md) except that the function may be inside a class with type parameters, may itself take type parameters, or both.</span></span> <span data-ttu-id="a4246-113">Die Typargumente sollten zuerst für die-Klasse und dann für die-Funktion angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="a4246-113">The type arguments should be given first for the class, and then for the function.</span></span>  
  
 <span data-ttu-id="a4246-114">Wenn sich die Funktion in einer anderen Anwendungsdomäne befindet, erfolgt ein Übergang.</span><span class="sxs-lookup"><span data-stu-id="a4246-114">If the function is in a different application domain, a transition will occur.</span></span> <span data-ttu-id="a4246-115">Alle Type-und Value-Argumente müssen sich jedoch in der Ziel Anwendungsdomäne befinden.</span><span class="sxs-lookup"><span data-stu-id="a4246-115">However, all type and value arguments must be in the target application domain.</span></span>  
  
 <span data-ttu-id="a4246-116">Die Funktions Auswertung kann nur in begrenzten Szenarios ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="a4246-116">Function evaluation can be performed only in limited scenarios.</span></span> <span data-ttu-id="a4246-117">Wenn `CallParameterizedFunction` oder `ICorDebugEval::CallFunction` fehlschlägt, gibt das zurückgegebene HRESULT den allgemeineren möglichen Grund für den Fehler an.</span><span class="sxs-lookup"><span data-stu-id="a4246-117">If `CallParameterizedFunction` or `ICorDebugEval::CallFunction` fails, the returned HRESULT will indicate the most general possible reason for failure.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a4246-118">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="a4246-118">Requirements</span></span>  

 <span data-ttu-id="a4246-119">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a4246-119">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a4246-120">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="a4246-120">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="a4246-121">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a4246-121">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a4246-122">**.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a4246-122">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
