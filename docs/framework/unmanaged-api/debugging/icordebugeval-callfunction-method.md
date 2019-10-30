---
title: ICorDebugEval::CallFunction-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugEval.CallFunction
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugEval::CallFunction
helpviewer_keywords:
- ICorDebugEval::CallFunction method [.NET Framework debugging]
- CallFunction method [.NET Framework debugging]
ms.assetid: 7f470c5c-e1c0-4d8d-aad8-830f113ae751
topic_type:
- apiref
ms.openlocfilehash: 4ac26ef4449dc02230f26b1247616b4587d217b7
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73085156"
---
# <a name="icordebugevalcallfunction-method"></a><span data-ttu-id="8b77a-102">ICorDebugEval::CallFunction-Methode</span><span class="sxs-lookup"><span data-stu-id="8b77a-102">ICorDebugEval::CallFunction Method</span></span>

<span data-ttu-id="8b77a-103">Richtet einen Rückruf für die angegebene Funktion ein.</span><span class="sxs-lookup"><span data-stu-id="8b77a-103">Sets up a call to the specified function.</span></span>

<span data-ttu-id="8b77a-104">Diese Methode ist in der .NET Framework Version 2,0 veraltet.</span><span class="sxs-lookup"><span data-stu-id="8b77a-104">This method is obsolete in the .NET Framework version 2.0.</span></span> <span data-ttu-id="8b77a-105">Verwenden Sie stattdessen [ICorDebugEval2:: CallParameterizedFunction](icordebugeval2-callparameterizedfunction-method.md) .</span><span class="sxs-lookup"><span data-stu-id="8b77a-105">Use [ICorDebugEval2::CallParameterizedFunction](icordebugeval2-callparameterizedfunction-method.md) instead.</span></span>

## <a name="syntax"></a><span data-ttu-id="8b77a-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="8b77a-106">Syntax</span></span>

```cpp
HRESULT CallFunction (
    [in] ICorDebugFunction  *pFunction,
    [in] ULONG32            nArgs,
    [in, size_is(nArgs)] ICorDebugValue *ppArgs[]
);
```

## <a name="parameters"></a><span data-ttu-id="8b77a-107">Parameter</span><span class="sxs-lookup"><span data-stu-id="8b77a-107">Parameters</span></span>

`pFunction`\
<span data-ttu-id="8b77a-108">in Zeiger auf ein ICorDebug Function-Objekt, das die aufzurufende Funktion angibt.</span><span class="sxs-lookup"><span data-stu-id="8b77a-108">[in] Pointer to an ICorDebugFunction object that specifies the function to be called.</span></span>

`nArgs`\
<span data-ttu-id="8b77a-109">in Die Anzahl von Argumenten für die Funktion.</span><span class="sxs-lookup"><span data-stu-id="8b77a-109">[in] The number of arguments for the function.</span></span>

`ppArgs`\
<span data-ttu-id="8b77a-110">in Ein Array von Zeigern, von denen jedes auf ein ICorDebug Value-Objekt verweist, das ein Argument angibt, das an die Funktion übergeben werden soll.</span><span class="sxs-lookup"><span data-stu-id="8b77a-110">[in] An array of pointers, each of which points to an ICorDebugValue object that specifies an argument to be passed to the function.</span></span>

## <a name="remarks"></a><span data-ttu-id="8b77a-111">Hinweise</span><span class="sxs-lookup"><span data-stu-id="8b77a-111">Remarks</span></span>

<span data-ttu-id="8b77a-112">Wenn die Funktion virtuell ist, führt `CallFunction` eine virtuelle Dispatch aus.</span><span class="sxs-lookup"><span data-stu-id="8b77a-112">If the function is virtual, `CallFunction` will perform virtual dispatch.</span></span> <span data-ttu-id="8b77a-113">Wenn sich die Funktion in einer anderen Anwendungsdomäne befindet, tritt ein Übergang auf, solange sich alle Argumente auch in dieser Anwendungsdomäne befinden.</span><span class="sxs-lookup"><span data-stu-id="8b77a-113">If the function is in a different application domain, a transition will occur as long as all arguments are also in that application domain.</span></span>

## <a name="requirements"></a><span data-ttu-id="8b77a-114">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="8b77a-114">Requirements</span></span>

<span data-ttu-id="8b77a-115">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8b77a-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>

<span data-ttu-id="8b77a-116">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="8b77a-116">**Header:** CorDebug.idl, CorDebug.h</span></span>

<span data-ttu-id="8b77a-117">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="8b77a-117">**Library:** CorGuids.lib</span></span>

<span data-ttu-id="8b77a-118">**.NET Framework Versionen:** 1,1, 1,0</span><span class="sxs-lookup"><span data-stu-id="8b77a-118">**.NET Framework Versions:** 1.1, 1.0</span></span>

## <a name="see-also"></a><span data-ttu-id="8b77a-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="8b77a-119">See also</span></span>

- [<span data-ttu-id="8b77a-120">CallParameterizedFunction-Methode</span><span class="sxs-lookup"><span data-stu-id="8b77a-120">CallParameterizedFunction Method</span></span>](icordebugeval2-callparameterizedfunction-method.md)
