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
ms.openlocfilehash: 93fff7ec315edec8b20b4149650b27e7792fb2f1
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/06/2019
ms.locfileid: "57475046"
---
# <a name="icordebugevalnewobjectnoconstructor-method"></a><span data-ttu-id="2a460-102">ICorDebugEval::NewObjectNoConstructor-Methode</span><span class="sxs-lookup"><span data-stu-id="2a460-102">ICorDebugEval::NewObjectNoConstructor Method</span></span>
<span data-ttu-id="2a460-103">Weist eine neue Objektinstanz des angegebenen Typs, ohne zu versuchen, eine Konstruktormethode aufrufen.</span><span class="sxs-lookup"><span data-stu-id="2a460-103">Allocates a new object instance of the specified type, without attempting to call a constructor method.</span></span>  
  
 <span data-ttu-id="2a460-104">Diese Methode ist in .NET Framework, Version 2.0, veraltet.</span><span class="sxs-lookup"><span data-stu-id="2a460-104">This method is obsolete in the .NET Framework version 2.0.</span></span> <span data-ttu-id="2a460-105">Verwendung [ICorDebugEval2:: NewParameterizedObjectNoConstructor](../../../../docs/framework/unmanaged-api/debugging/icordebugeval2-newparameterizedobjectnoconstructor-method.md) stattdessen.</span><span class="sxs-lookup"><span data-stu-id="2a460-105">Use [ICorDebugEval2::NewParameterizedObjectNoConstructor](../../../../docs/framework/unmanaged-api/debugging/icordebugeval2-newparameterizedobjectnoconstructor-method.md) instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2a460-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="2a460-106">Syntax</span></span>  
  
```  
HRESULT NewObjectNoConstructor (  
    [in] ICorDebugClass     *pClass  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2a460-107">Parameter</span><span class="sxs-lookup"><span data-stu-id="2a460-107">Parameters</span></span>  
 `pClass`  
 <span data-ttu-id="2a460-108">[in] Zeiger auf ein ICorDebugClass-Objekt, das den Typ des Objekts instanziiert werden.</span><span class="sxs-lookup"><span data-stu-id="2a460-108">[in] Pointer to an ICorDebugClass object that represents the type of object to be instantiated.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2a460-109">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="2a460-109">Requirements</span></span>  
 <span data-ttu-id="2a460-110">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2a460-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2a460-111">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="2a460-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="2a460-112">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2a460-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2a460-113">**.NET Framework-Versionen:** 1.1, 1.0</span><span class="sxs-lookup"><span data-stu-id="2a460-113">**.NET Framework Versions:** 1.1, 1.0</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2a460-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="2a460-114">See also</span></span>
- [<span data-ttu-id="2a460-115">NewParameterizedObjectNoConstructor-Methode</span><span class="sxs-lookup"><span data-stu-id="2a460-115">NewParameterizedObjectNoConstructor Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugeval2-newparameterizedobjectnoconstructor-method.md)
