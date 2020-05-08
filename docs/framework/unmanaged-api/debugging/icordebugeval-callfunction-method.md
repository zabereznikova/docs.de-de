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
ms.openlocfilehash: 1cf0080945ad78565fae3fedb454ceba7825cb4a
ms.sourcegitcommit: fff146ba3fd1762c8c432d95c8b877825ae536fc
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/08/2020
ms.locfileid: "82976238"
---
# <a name="icordebugevalcallfunction-method"></a><span data-ttu-id="011c4-102">ICorDebugEval::CallFunction-Methode</span><span class="sxs-lookup"><span data-stu-id="011c4-102">ICorDebugEval::CallFunction Method</span></span>

<span data-ttu-id="011c4-103">Richtet einen Rückruf für die angegebene Funktion ein.</span><span class="sxs-lookup"><span data-stu-id="011c4-103">Sets up a call to the specified function.</span></span>

<span data-ttu-id="011c4-104">Diese Methode ist in der .NET Framework Version 2,0 veraltet.</span><span class="sxs-lookup"><span data-stu-id="011c4-104">This method is obsolete in the .NET Framework version 2.0.</span></span> <span data-ttu-id="011c4-105">Verwenden Sie stattdessen [ICorDebugEval2:: CallParameterizedFunction](icordebugeval2-callparameterizedfunction-method.md) .</span><span class="sxs-lookup"><span data-stu-id="011c4-105">Use [ICorDebugEval2::CallParameterizedFunction](icordebugeval2-callparameterizedfunction-method.md) instead.</span></span>

## <a name="syntax"></a><span data-ttu-id="011c4-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="011c4-106">Syntax</span></span>

```cpp
HRESULT CallFunction (
    [in] ICorDebugFunction  *pFunction,
    [in] ULONG32            nArgs,
    [in, size_is(nArgs)] ICorDebugValue *ppArgs[]
);
```

## <a name="parameters"></a><span data-ttu-id="011c4-107">Parameter</span><span class="sxs-lookup"><span data-stu-id="011c4-107">Parameters</span></span>

`pFunction`\
<span data-ttu-id="011c4-108">in Zeiger auf ein ICorDebug Function-Objekt, das die aufzurufende Funktion angibt.</span><span class="sxs-lookup"><span data-stu-id="011c4-108">[in] Pointer to an ICorDebugFunction object that specifies the function to be called.</span></span>

`nArgs`\
<span data-ttu-id="011c4-109">in Die Anzahl von Argumenten für die Funktion.</span><span class="sxs-lookup"><span data-stu-id="011c4-109">[in] The number of arguments for the function.</span></span>

`ppArgs`\
<span data-ttu-id="011c4-110">in Ein Array von Zeigern, von denen jedes auf ein ICorDebug Value-Objekt verweist, das ein Argument angibt, das an die Funktion übergeben werden soll.</span><span class="sxs-lookup"><span data-stu-id="011c4-110">[in] An array of pointers, each of which points to an ICorDebugValue object that specifies an argument to be passed to the function.</span></span>

## <a name="remarks"></a><span data-ttu-id="011c4-111">Hinweise</span><span class="sxs-lookup"><span data-stu-id="011c4-111">Remarks</span></span>

<span data-ttu-id="011c4-112">Wenn die Funktion virtuell ist, `CallFunction` wird eine virtuelle Dispatch durchgeführt.</span><span class="sxs-lookup"><span data-stu-id="011c4-112">If the function is virtual, `CallFunction` will perform virtual dispatch.</span></span> <span data-ttu-id="011c4-113">Wenn sich die Funktion in einer anderen Anwendungsdomäne befindet, tritt ein Übergang auf, solange sich alle Argumente auch in dieser Anwendungsdomäne befinden.</span><span class="sxs-lookup"><span data-stu-id="011c4-113">If the function is in a different application domain, a transition will occur as long as all arguments are also in that application domain.</span></span>

## <a name="requirements"></a><span data-ttu-id="011c4-114">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="011c4-114">Requirements</span></span>

<span data-ttu-id="011c4-115">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="011c4-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>

<span data-ttu-id="011c4-116">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="011c4-116">**Header:** CorDebug.idl, CorDebug.h</span></span>

<span data-ttu-id="011c4-117">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="011c4-117">**Library:** CorGuids.lib</span></span>

<span data-ttu-id="011c4-118">**.NET Framework Versionen:** 1,1, 1,0</span><span class="sxs-lookup"><span data-stu-id="011c4-118">**.NET Framework Versions:** 1.1, 1.0</span></span>

## <a name="see-also"></a><span data-ttu-id="011c4-119">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="011c4-119">See also</span></span>

- [<span data-ttu-id="011c4-120">CallParameterizedFunction-Methode</span><span class="sxs-lookup"><span data-stu-id="011c4-120">CallParameterizedFunction Method</span></span>](icordebugeval2-callparameterizedfunction-method.md)
