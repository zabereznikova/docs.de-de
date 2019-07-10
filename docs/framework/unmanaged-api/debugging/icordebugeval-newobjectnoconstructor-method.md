---
title: ICorDebugEval::NewObjectNoConstructor-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugEval.NewObjectNoConstructor
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugEval::NewObjectNoConstructor
helpviewer_keywords:
- NewObjectNoConstructor method [.NET Framework debugging]
- ICorDebugEval::NewObjectNoConstructor method [.NET Framework debugging]
ms.assetid: 80d509ca-b5e3-4c46-9c14-800db73d9bf7
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 8e4a09db3cedce7b0ae6049c7e550c0c3e21cc8c
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67753171"
---
# <a name="icordebugevalnewobjectnoconstructor-method"></a><span data-ttu-id="ee6af-102">ICorDebugEval::NewObjectNoConstructor-Methode</span><span class="sxs-lookup"><span data-stu-id="ee6af-102">ICorDebugEval::NewObjectNoConstructor Method</span></span>
<span data-ttu-id="ee6af-103">Weist eine neue Objektinstanz des angegebenen Typs, ohne zu versuchen, eine Konstruktormethode aufrufen.</span><span class="sxs-lookup"><span data-stu-id="ee6af-103">Allocates a new object instance of the specified type, without attempting to call a constructor method.</span></span>  
  
 <span data-ttu-id="ee6af-104">Diese Methode ist in .NET Framework, Version 2.0, veraltet.</span><span class="sxs-lookup"><span data-stu-id="ee6af-104">This method is obsolete in the .NET Framework version 2.0.</span></span> <span data-ttu-id="ee6af-105">Verwendung [ICorDebugEval2:: NewParameterizedObjectNoConstructor](../../../../docs/framework/unmanaged-api/debugging/icordebugeval2-newparameterizedobjectnoconstructor-method.md) stattdessen.</span><span class="sxs-lookup"><span data-stu-id="ee6af-105">Use [ICorDebugEval2::NewParameterizedObjectNoConstructor](../../../../docs/framework/unmanaged-api/debugging/icordebugeval2-newparameterizedobjectnoconstructor-method.md) instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ee6af-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="ee6af-106">Syntax</span></span>  
  
```cpp  
HRESULT NewObjectNoConstructor (  
    [in] ICorDebugClass     *pClass  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ee6af-107">Parameter</span><span class="sxs-lookup"><span data-stu-id="ee6af-107">Parameters</span></span>  
 `pClass`  
 <span data-ttu-id="ee6af-108">[in] Zeiger auf ein ICorDebugClass-Objekt, das den Typ des Objekts instanziiert werden.</span><span class="sxs-lookup"><span data-stu-id="ee6af-108">[in] Pointer to an ICorDebugClass object that represents the type of object to be instantiated.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ee6af-109">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="ee6af-109">Requirements</span></span>  
 <span data-ttu-id="ee6af-110">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ee6af-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ee6af-111">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="ee6af-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="ee6af-112">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ee6af-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ee6af-113">**.NET Framework-Versionen:** 1.1, 1.0</span><span class="sxs-lookup"><span data-stu-id="ee6af-113">**.NET Framework Versions:** 1.1, 1.0</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ee6af-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ee6af-114">See also</span></span>

- [<span data-ttu-id="ee6af-115">NewParameterizedObjectNoConstructor-Methode</span><span class="sxs-lookup"><span data-stu-id="ee6af-115">NewParameterizedObjectNoConstructor Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugeval2-newparameterizedobjectnoconstructor-method.md)
