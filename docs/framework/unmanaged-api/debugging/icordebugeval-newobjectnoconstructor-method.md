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
ms.openlocfilehash: 255d88dcdd880c73a7535cddcad410dcfdcf1d70
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73132659"
---
# <a name="icordebugevalnewobjectnoconstructor-method"></a><span data-ttu-id="f0b61-102">ICorDebugEval::NewObjectNoConstructor-Methode</span><span class="sxs-lookup"><span data-stu-id="f0b61-102">ICorDebugEval::NewObjectNoConstructor Method</span></span>
<span data-ttu-id="f0b61-103">Ordnet eine neue Objektinstanz des angegebenen Typs zu, ohne zu versuchen, eine Konstruktormethode aufzurufen.</span><span class="sxs-lookup"><span data-stu-id="f0b61-103">Allocates a new object instance of the specified type, without attempting to call a constructor method.</span></span>  
  
 <span data-ttu-id="f0b61-104">Diese Methode ist in der .NET Framework Version 2,0 veraltet.</span><span class="sxs-lookup"><span data-stu-id="f0b61-104">This method is obsolete in the .NET Framework version 2.0.</span></span> <span data-ttu-id="f0b61-105">Verwenden Sie stattdessen [ICorDebugEval2:: NewParameterizedObjectNoConstructor](../../../../docs/framework/unmanaged-api/debugging/icordebugeval2-newparameterizedobjectnoconstructor-method.md) .</span><span class="sxs-lookup"><span data-stu-id="f0b61-105">Use [ICorDebugEval2::NewParameterizedObjectNoConstructor](../../../../docs/framework/unmanaged-api/debugging/icordebugeval2-newparameterizedobjectnoconstructor-method.md) instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f0b61-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="f0b61-106">Syntax</span></span>  
  
```cpp  
HRESULT NewObjectNoConstructor (  
    [in] ICorDebugClass     *pClass  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f0b61-107">Parameter</span><span class="sxs-lookup"><span data-stu-id="f0b61-107">Parameters</span></span>  
 `pClass`  
 <span data-ttu-id="f0b61-108">in Zeiger auf ein ICorDebugClass-Objekt, das den Objekttyp darstellt, der instanziiert werden soll.</span><span class="sxs-lookup"><span data-stu-id="f0b61-108">[in] Pointer to an ICorDebugClass object that represents the type of object to be instantiated.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f0b61-109">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="f0b61-109">Requirements</span></span>  
 <span data-ttu-id="f0b61-110">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f0b61-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f0b61-111">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="f0b61-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="f0b61-112">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f0b61-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f0b61-113">**.NET Framework Versionen:** 1,1, 1,0</span><span class="sxs-lookup"><span data-stu-id="f0b61-113">**.NET Framework Versions:** 1.1, 1.0</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f0b61-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f0b61-114">See also</span></span>

- [<span data-ttu-id="f0b61-115">NewParameterizedObjectNoConstructor-Methode</span><span class="sxs-lookup"><span data-stu-id="f0b61-115">NewParameterizedObjectNoConstructor Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugeval2-newparameterizedobjectnoconstructor-method.md)
