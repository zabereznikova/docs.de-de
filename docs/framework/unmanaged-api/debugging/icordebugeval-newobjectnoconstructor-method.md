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
ms.openlocfilehash: bb27ec755fb83dc71af7dd48b5ed6e7699436335
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95729728"
---
# <a name="icordebugevalnewobjectnoconstructor-method"></a><span data-ttu-id="2b98b-102">ICorDebugEval::NewObjectNoConstructor-Methode</span><span class="sxs-lookup"><span data-stu-id="2b98b-102">ICorDebugEval::NewObjectNoConstructor Method</span></span>

<span data-ttu-id="2b98b-103">Ordnet eine neue Objektinstanz des angegebenen Typs zu, ohne zu versuchen, eine Konstruktormethode aufzurufen.</span><span class="sxs-lookup"><span data-stu-id="2b98b-103">Allocates a new object instance of the specified type, without attempting to call a constructor method.</span></span>  
  
 <span data-ttu-id="2b98b-104">Diese Methode ist in der .NET Framework Version 2,0 veraltet.</span><span class="sxs-lookup"><span data-stu-id="2b98b-104">This method is obsolete in the .NET Framework version 2.0.</span></span> <span data-ttu-id="2b98b-105">Verwenden Sie stattdessen [ICorDebugEval2:: NewParameterizedObjectNoConstructor](icordebugeval2-newparameterizedobjectnoconstructor-method.md) .</span><span class="sxs-lookup"><span data-stu-id="2b98b-105">Use [ICorDebugEval2::NewParameterizedObjectNoConstructor](icordebugeval2-newparameterizedobjectnoconstructor-method.md) instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2b98b-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="2b98b-106">Syntax</span></span>  
  
```cpp  
HRESULT NewObjectNoConstructor (  
    [in] ICorDebugClass     *pClass  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2b98b-107">Parameter</span><span class="sxs-lookup"><span data-stu-id="2b98b-107">Parameters</span></span>  

 `pClass`  
 <span data-ttu-id="2b98b-108">in Zeiger auf ein ICorDebugClass-Objekt, das den Objekttyp darstellt, der instanziiert werden soll.</span><span class="sxs-lookup"><span data-stu-id="2b98b-108">[in] Pointer to an ICorDebugClass object that represents the type of object to be instantiated.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2b98b-109">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="2b98b-109">Requirements</span></span>  

 <span data-ttu-id="2b98b-110">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2b98b-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2b98b-111">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="2b98b-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="2b98b-112">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2b98b-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2b98b-113">**.NET Framework Versionen:** 1,1, 1,0</span><span class="sxs-lookup"><span data-stu-id="2b98b-113">**.NET Framework Versions:** 1.1, 1.0</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2b98b-114">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="2b98b-114">See also</span></span>

- [<span data-ttu-id="2b98b-115">NewParameterizedObjectNoConstructor-Methode</span><span class="sxs-lookup"><span data-stu-id="2b98b-115">NewParameterizedObjectNoConstructor Method</span></span>](icordebugeval2-newparameterizedobjectnoconstructor-method.md)
