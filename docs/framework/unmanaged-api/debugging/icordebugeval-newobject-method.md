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
ms.openlocfilehash: e9570d3c916123093f69e7f26d3778f1c7184b1f
ms.sourcegitcommit: fff146ba3fd1762c8c432d95c8b877825ae536fc
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/08/2020
ms.locfileid: "82976186"
---
# <a name="icordebugevalnewobject-method"></a><span data-ttu-id="b8ba5-102">ICorDebugEval::NewObject-Methode</span><span class="sxs-lookup"><span data-stu-id="b8ba5-102">ICorDebugEval::NewObject Method</span></span>
<span data-ttu-id="b8ba5-103">Ordnet eine neue Objektinstanz zu und ruft die angegebene Konstruktormethode auf.</span><span class="sxs-lookup"><span data-stu-id="b8ba5-103">Allocates a new object instance and calls the specified constructor method.</span></span>  
  
 <span data-ttu-id="b8ba5-104">Diese Methode ist in der .NET Framework Version 2,0 veraltet.</span><span class="sxs-lookup"><span data-stu-id="b8ba5-104">This method is obsolete in the .NET Framework version 2.0.</span></span> <span data-ttu-id="b8ba5-105">Verwenden Sie stattdessen [ICorDebugEval2:: NewParameterizedObject](icordebugeval2-newparameterizedobject-method.md) .</span><span class="sxs-lookup"><span data-stu-id="b8ba5-105">Use [ICorDebugEval2::NewParameterizedObject](icordebugeval2-newparameterizedobject-method.md) instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b8ba5-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="b8ba5-106">Syntax</span></span>  
  
```cpp  
HRESULT NewObject (  
    [in] ICorDebugFunction  *pConstructor,  
    [in] ULONG32            nArgs,  
    [in, size_is(nArgs)] ICorDebugValue *ppArgs[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b8ba5-107">Parameter</span><span class="sxs-lookup"><span data-stu-id="b8ba5-107">Parameters</span></span>  
 `pConstructor`  
 <span data-ttu-id="b8ba5-108">in Der aufzurufende Konstruktor.</span><span class="sxs-lookup"><span data-stu-id="b8ba5-108">[in] The constructor to be called.</span></span>  
  
 `nArgs`  
 <span data-ttu-id="b8ba5-109">[in] Die Größe des `ppArgs`-Arrays.</span><span class="sxs-lookup"><span data-stu-id="b8ba5-109">[in] The size of the `ppArgs` array.</span></span>  
  
 `ppArgs`  
 <span data-ttu-id="b8ba5-110">in Ein Array von ICorDebugValue-Objekten, von denen jedes ein Argument darstellt, das an den Konstruktor übergeben werden soll.</span><span class="sxs-lookup"><span data-stu-id="b8ba5-110">[in] An array of ICorDebugValue objects, each of which represents an argument to be passed to the constructor.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b8ba5-111">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="b8ba5-111">Requirements</span></span>  
 <span data-ttu-id="b8ba5-112">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b8ba5-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b8ba5-113">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="b8ba5-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="b8ba5-114">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b8ba5-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b8ba5-115">**.NET Framework Versionen:** 1,1, 1,0</span><span class="sxs-lookup"><span data-stu-id="b8ba5-115">**.NET Framework Versions:** 1.1, 1.0</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b8ba5-116">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="b8ba5-116">See also</span></span>

- [<span data-ttu-id="b8ba5-117">NewParameterizedObject-Methode</span><span class="sxs-lookup"><span data-stu-id="b8ba5-117">NewParameterizedObject Method</span></span>](icordebugeval2-newparameterizedobject-method.md)
