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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 65225281fe3abaa20e69e96f4cd4d2a4b03a87ce
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/15/2019
ms.locfileid: "65629939"
---
# <a name="icordebugevalcallfunction-method"></a><span data-ttu-id="c4534-102">ICorDebugEval::CallFunction-Methode</span><span class="sxs-lookup"><span data-stu-id="c4534-102">ICorDebugEval::CallFunction Method</span></span>

<span data-ttu-id="c4534-103">Richtet einen Aufruf der angegebenen Funktion.</span><span class="sxs-lookup"><span data-stu-id="c4534-103">Sets up a call to the specified function.</span></span>

<span data-ttu-id="c4534-104">Diese Methode ist in .NET Framework, Version 2.0, veraltet.</span><span class="sxs-lookup"><span data-stu-id="c4534-104">This method is obsolete in the .NET Framework version 2.0.</span></span> <span data-ttu-id="c4534-105">Verwendung [ICorDebugEval2:: CallParameterizedFunction](icordebugeval2-callparameterizedfunction-method.md) stattdessen.</span><span class="sxs-lookup"><span data-stu-id="c4534-105">Use [ICorDebugEval2::CallParameterizedFunction](icordebugeval2-callparameterizedfunction-method.md) instead.</span></span>

## <a name="syntax"></a><span data-ttu-id="c4534-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="c4534-106">Syntax</span></span>

```cpp
HRESULT CallFunction (
    [in] ICorDebugFunction  *pFunction,
    [in] ULONG32            nArgs,
    [in, size_is(nArgs)] ICorDebugValue *ppArgs[]
);
```

## <a name="parameters"></a><span data-ttu-id="c4534-107">Parameter</span><span class="sxs-lookup"><span data-stu-id="c4534-107">Parameters</span></span>

`pFunction`\
<span data-ttu-id="c4534-108">[in] Zeiger auf ein ICorDebugFunction-Objekt, das die aufzurufende Funktion angibt.</span><span class="sxs-lookup"><span data-stu-id="c4534-108">[in] Pointer to an ICorDebugFunction object that specifies the function to be called.</span></span>

`nArgs`\
<span data-ttu-id="c4534-109">[in] Die Anzahl der Argumente für die Funktion.</span><span class="sxs-lookup"><span data-stu-id="c4534-109">[in] The number of arguments for the function.</span></span>

`ppArgs`\
<span data-ttu-id="c4534-110">[in] Ein Array von Zeigern, von denen jeder zu einem ICorDebugValue-Objekt verweist, der angibt, ein Argument an die Funktion übergeben werden.</span><span class="sxs-lookup"><span data-stu-id="c4534-110">[in] An array of pointers, each of which points to an ICorDebugValue object that specifies an argument to be passed to the function.</span></span>

## <a name="remarks"></a><span data-ttu-id="c4534-111">Hinweise</span><span class="sxs-lookup"><span data-stu-id="c4534-111">Remarks</span></span>

<span data-ttu-id="c4534-112">Wenn die Funktion virtuell, `CallFunction` virtuellen Dispatch führt.</span><span class="sxs-lookup"><span data-stu-id="c4534-112">If the function is virtual, `CallFunction` will perform virtual dispatch.</span></span> <span data-ttu-id="c4534-113">Wenn die Funktion in einer anderen Anwendungsdomäne ist, wird ein Übergang erfolgen, solange alle Argumente in dieser Anwendungsdomäne ebenfalls enthalten sind.</span><span class="sxs-lookup"><span data-stu-id="c4534-113">If the function is in a different application domain, a transition will occur as long as all arguments are also in that application domain.</span></span>

## <a name="requirements"></a><span data-ttu-id="c4534-114">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="c4534-114">Requirements</span></span>

<span data-ttu-id="c4534-115">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c4534-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>

<span data-ttu-id="c4534-116">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="c4534-116">**Header:** CorDebug.idl, CorDebug.h</span></span>

<span data-ttu-id="c4534-117">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c4534-117">**Library:** CorGuids.lib</span></span>

<span data-ttu-id="c4534-118">**.NET Framework-Versionen:** 1.1, 1.0</span><span class="sxs-lookup"><span data-stu-id="c4534-118">**.NET Framework Versions:** 1.1, 1.0</span></span>

## <a name="see-also"></a><span data-ttu-id="c4534-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c4534-119">See also</span></span>

- [<span data-ttu-id="c4534-120">CallParameterizedFunction-Methode</span><span class="sxs-lookup"><span data-stu-id="c4534-120">CallParameterizedFunction Method</span></span>](icordebugeval2-callparameterizedfunction-method.md)
