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
ms.openlocfilehash: 362c01e0b08145919793cec011a856f0090e5c47
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67752991"
---
# <a name="icordebugevalnewobject-method"></a><span data-ttu-id="b9777-102">ICorDebugEval::NewObject-Methode</span><span class="sxs-lookup"><span data-stu-id="b9777-102">ICorDebugEval::NewObject Method</span></span>
<span data-ttu-id="b9777-103">Reserviert eine neue Objektinstanz, und der angegebene Konstruktor-Methode aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="b9777-103">Allocates a new object instance and calls the specified constructor method.</span></span>  
  
 <span data-ttu-id="b9777-104">Diese Methode ist in .NET Framework, Version 2.0, veraltet.</span><span class="sxs-lookup"><span data-stu-id="b9777-104">This method is obsolete in the .NET Framework version 2.0.</span></span> <span data-ttu-id="b9777-105">Verwendung [ICorDebugEval2:: NewParameterizedObject](../../../../docs/framework/unmanaged-api/debugging/icordebugeval2-newparameterizedobject-method.md) stattdessen.</span><span class="sxs-lookup"><span data-stu-id="b9777-105">Use [ICorDebugEval2::NewParameterizedObject](../../../../docs/framework/unmanaged-api/debugging/icordebugeval2-newparameterizedobject-method.md) instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b9777-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="b9777-106">Syntax</span></span>  
  
```cpp  
HRESULT NewObject (  
    [in] ICorDebugFunction  *pConstructor,  
    [in] ULONG32            nArgs,  
    [in, size_is(nArgs)] ICorDebugValue *ppArgs[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b9777-107">Parameter</span><span class="sxs-lookup"><span data-stu-id="b9777-107">Parameters</span></span>  
 `pConstructor`  
 <span data-ttu-id="b9777-108">[in] Der Konstruktor aufgerufen werden soll.</span><span class="sxs-lookup"><span data-stu-id="b9777-108">[in] The constructor to be called.</span></span>  
  
 `nArgs`  
 <span data-ttu-id="b9777-109">[in] Die Größe des `ppArgs`-Arrays.</span><span class="sxs-lookup"><span data-stu-id="b9777-109">[in] The size of the `ppArgs` array.</span></span>  
  
 `ppArgs`  
 <span data-ttu-id="b9777-110">[in] Ein Array von ICorDebugValue-Objekten, von denen jeder ein Argument an den Konstruktor zu übergebenden darstellt.</span><span class="sxs-lookup"><span data-stu-id="b9777-110">[in] An array of ICorDebugValue objects, each of which represents an argument to be passed to the constructor.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b9777-111">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="b9777-111">Requirements</span></span>  
 <span data-ttu-id="b9777-112">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b9777-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b9777-113">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="b9777-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="b9777-114">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b9777-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b9777-115">**.NET Framework-Versionen:** 1.1, 1.0</span><span class="sxs-lookup"><span data-stu-id="b9777-115">**.NET Framework Versions:** 1.1, 1.0</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b9777-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b9777-116">See also</span></span>

- [<span data-ttu-id="b9777-117">NewParameterizedObject-Methode</span><span class="sxs-lookup"><span data-stu-id="b9777-117">NewParameterizedObject Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugeval2-newparameterizedobject-method.md)
