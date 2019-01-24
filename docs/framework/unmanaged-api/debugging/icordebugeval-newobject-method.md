---
title: ICorDebugEval::NewObject-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugEval.NewObject
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugEval::NewObject
helpviewer_keywords:
- NewObject method [.NET Framework debugging]
- ICorDebugEval::NewObject method [.NET Framework debugging]
ms.assetid: ce3025e8-defa-4c5e-8298-f49d71fa5736
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 9ff4f86105fd1dfbd12360c01046492f3a6dbdcd
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54589893"
---
# <a name="icordebugevalnewobject-method"></a><span data-ttu-id="a490d-102">ICorDebugEval::NewObject-Methode</span><span class="sxs-lookup"><span data-stu-id="a490d-102">ICorDebugEval::NewObject Method</span></span>
<span data-ttu-id="a490d-103">Reserviert eine neue Objektinstanz, und der angegebene Konstruktor-Methode aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="a490d-103">Allocates a new object instance and calls the specified constructor method.</span></span>  
  
 <span data-ttu-id="a490d-104">Diese Methode ist in .NET Framework, Version 2.0, veraltet.</span><span class="sxs-lookup"><span data-stu-id="a490d-104">This method is obsolete in the .NET Framework version 2.0.</span></span> <span data-ttu-id="a490d-105">Verwendung [ICorDebugEval2:: NewParameterizedObject](../../../../docs/framework/unmanaged-api/debugging/icordebugeval2-newparameterizedobject-method.md) stattdessen.</span><span class="sxs-lookup"><span data-stu-id="a490d-105">Use [ICorDebugEval2::NewParameterizedObject](../../../../docs/framework/unmanaged-api/debugging/icordebugeval2-newparameterizedobject-method.md) instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a490d-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="a490d-106">Syntax</span></span>  
  
```  
HRESULT NewObject (  
    [in] ICorDebugFunction  *pConstructor,  
    [in] ULONG32            nArgs,  
    [in, size_is(nArgs)] ICorDebugValue *ppArgs[]  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="a490d-107">Parameter</span><span class="sxs-lookup"><span data-stu-id="a490d-107">Parameters</span></span>  
 `pConstructor`  
 <span data-ttu-id="a490d-108">[in] Der Konstruktor aufgerufen werden soll.</span><span class="sxs-lookup"><span data-stu-id="a490d-108">[in] The constructor to be called.</span></span>  
  
 `nArgs`  
 <span data-ttu-id="a490d-109">[in] Die Größe des `ppArgs`-Arrays.</span><span class="sxs-lookup"><span data-stu-id="a490d-109">[in] The size of the `ppArgs` array.</span></span>  
  
 `ppArgs`  
 <span data-ttu-id="a490d-110">[in] Ein Array von ICorDebugValue-Objekten, von denen jeder ein Argument an den Konstruktor zu übergebenden darstellt.</span><span class="sxs-lookup"><span data-stu-id="a490d-110">[in] An array of ICorDebugValue objects, each of which represents an argument to be passed to the constructor.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a490d-111">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="a490d-111">Requirements</span></span>  
 <span data-ttu-id="a490d-112">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a490d-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a490d-113">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="a490d-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="a490d-114">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a490d-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a490d-115">**.NET Framework-Versionen:** 1.1, 1.0</span><span class="sxs-lookup"><span data-stu-id="a490d-115">**.NET Framework Versions:** 1.1, 1.0</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a490d-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a490d-116">See also</span></span>
- [<span data-ttu-id="a490d-117">NewParameterizedObject-Methode</span><span class="sxs-lookup"><span data-stu-id="a490d-117">NewParameterizedObject Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugeval2-newparameterizedobject-method.md)
