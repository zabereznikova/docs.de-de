---
title: ICorDebugEval::CallFunction-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugEval.CallFunction
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugEval::CallFunction
helpviewer_keywords:
- ICorDebugEval::CallFunction method [.NET Framework debugging]
- CallFunction method [.NET Framework debugging]
ms.assetid: 7f470c5c-e1c0-4d8d-aad8-830f113ae751
topic_type: apiref
caps.latest.revision: "16"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 72713d81931b53e8d61fb39cee146fd30a59bfcc
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugevalcallfunction-method"></a><span data-ttu-id="1f1b9-102">ICorDebugEval::CallFunction-Methode</span><span class="sxs-lookup"><span data-stu-id="1f1b9-102">ICorDebugEval::CallFunction Method</span></span>
<span data-ttu-id="1f1b9-103">Richtet einen Aufruf der angegebenen Funktion.</span><span class="sxs-lookup"><span data-stu-id="1f1b9-103">Sets up a call to the specified function.</span></span>  
  
 <span data-ttu-id="1f1b9-104">Diese Methode ist veraltet in .NET Framework, Version 2.0.</span><span class="sxs-lookup"><span data-stu-id="1f1b9-104">This method is obsolete in the .NET Framework version 2.0.</span></span> <span data-ttu-id="1f1b9-105">Verwendung [ICorDebugEval2:: CallParameterizedFunction](../../../../docs/framework/unmanaged-api/debugging/icordebugeval2-callparameterizedfunction-method.md) stattdessen.</span><span class="sxs-lookup"><span data-stu-id="1f1b9-105">Use [ICorDebugEval2::CallParameterizedFunction](../../../../docs/framework/unmanaged-api/debugging/icordebugeval2-callparameterizedfunction-method.md) instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1f1b9-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="1f1b9-106">Syntax</span></span>  
  
```  
HRESULT CallFunction (  
    [in] ICorDebugFunction  *pFunction,  
    [in] ULONG32            nArgs,  
    [in, size_is(nArgs)] ICorDebugValue *ppArgs[]  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="1f1b9-107">Parameter</span><span class="sxs-lookup"><span data-stu-id="1f1b9-107">Parameters</span></span>  
 `pFunction`  
 <span data-ttu-id="1f1b9-108">[in] Ein Zeiger auf ein ICorDebugFunction-Objekt, das die aufzurufende Funktion angibt.</span><span class="sxs-lookup"><span data-stu-id="1f1b9-108">[in] Pointer to an ICorDebugFunction object that specifies the function to be called.</span></span>  
  
 `nArgs`  
 <span data-ttu-id="1f1b9-109">[in] Die Anzahl von Argumenten für die Funktion.</span><span class="sxs-lookup"><span data-stu-id="1f1b9-109">[in] The number of arguments for the function.</span></span>  
  
 `ppArgs`  
 <span data-ttu-id="1f1b9-110">[in] Ein Array von Zeigern, von denen jedes auf ICorDebugValue-Objekts verweist, der angibt, ein Argument an die Funktion übergeben werden.</span><span class="sxs-lookup"><span data-stu-id="1f1b9-110">[in] An array of pointers, each of which points to an ICorDebugValue object that specifies an argument to be passed to the function.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="1f1b9-111">Hinweise</span><span class="sxs-lookup"><span data-stu-id="1f1b9-111">Remarks</span></span>  
 <span data-ttu-id="1f1b9-112">Wenn die Funktion virtuell ist, wird `CallFunction` virtuellen Dispatch führt.</span><span class="sxs-lookup"><span data-stu-id="1f1b9-112">If the function is virtual, `CallFunction` will perform virtual dispatch.</span></span> <span data-ttu-id="1f1b9-113">Wenn die Funktion in einer anderen Anwendungsdomäne ist, wird ein Übergang erfolgen, solange alle Argumente in der Anwendungsdomäne ebenfalls enthalten sind.</span><span class="sxs-lookup"><span data-stu-id="1f1b9-113">If the function is in a different application domain, a transition will occur as long as all arguments are also in that application domain.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1f1b9-114">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="1f1b9-114">Requirements</span></span>  
 <span data-ttu-id="1f1b9-115">**Plattformen:** WindowSee [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1f1b9-115">**Platforms:** WindowSee [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1f1b9-116">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="1f1b9-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="1f1b9-117">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="1f1b9-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="1f1b9-118">**.NET Framework-Versionen:** 1.1, 1.0</span><span class="sxs-lookup"><span data-stu-id="1f1b9-118">**.NET Framework Versions:** 1.1, 1.0</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1f1b9-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="1f1b9-119">See Also</span></span>  
 [<span data-ttu-id="1f1b9-120">CallParameterizedFunction-Methode</span><span class="sxs-lookup"><span data-stu-id="1f1b9-120">CallParameterizedFunction Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugeval2-callparameterizedfunction-method.md)
