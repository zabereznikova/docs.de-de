---
title: ICorDebugEval2::NewParameterizedObjectNoConstructor-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugEval2.NewParameterizedObjectNoConstructor
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugEval2::NewParameterizedObjectNoConstructor
helpviewer_keywords:
- NewParameterizedObjectNoConstructor method [.NET Framework debugging]
- ICorDebugEval2::NewParameterizedObjectNoConstructor method [.NET Framework debugging]
ms.assetid: f15b5b78-94f4-4eb9-b3b3-a621272f357c
topic_type:
- apiref
ms.openlocfilehash: 770a9280d27c84b950e00e71328c9b28e61c9e7c
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73084810"
---
# <a name="icordebugeval2newparameterizedobjectnoconstructor-method"></a><span data-ttu-id="17b82-102">ICorDebugEval2::NewParameterizedObjectNoConstructor-Methode</span><span class="sxs-lookup"><span data-stu-id="17b82-102">ICorDebugEval2::NewParameterizedObjectNoConstructor Method</span></span>
<span data-ttu-id="17b82-103">Instanziiert ein neues parametrisiertes Typobjekt der angegebenen Klasse, ohne dass versucht wird, eine Konstruktormethode aufzurufen.</span><span class="sxs-lookup"><span data-stu-id="17b82-103">Instantiates a new parameterized type object of the specified class without attempting to call a constructor method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="17b82-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="17b82-104">Syntax</span></span>  
  
```cpp  
HRESULT NewParameterizedObjectNoConstructor (  
    [in] ICorDebugClass        *pClass,  
    [in] ULONG32               nTypeArgs,  
    [in, size_is(nTypeArgs)] ICorDebugType *ppTypeArgs[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="17b82-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="17b82-105">Parameters</span></span>  
 `pClass`  
 <span data-ttu-id="17b82-106">in Ein Zeiger auf ein ICorDebugClass-Objekt, das die Klasse des Objekts darstellt, das instanziiert werden soll.</span><span class="sxs-lookup"><span data-stu-id="17b82-106">[in] A pointer to an ICorDebugClass object that represents the class of the object to be instantiated.</span></span>  
  
 `nTypeArgs`  
 <span data-ttu-id="17b82-107">in Die Anzahl der bestandenen Typargumente.</span><span class="sxs-lookup"><span data-stu-id="17b82-107">[in] The number of type arguments passed.</span></span>  
  
 `ppTypeArgs`  
 <span data-ttu-id="17b82-108">in Ein Array von Zeigern, von denen jedes auf ein ICorDebugType-Objekt verweist, das ein Typargument für das Objekt darstellt, das instanziiert wird.</span><span class="sxs-lookup"><span data-stu-id="17b82-108">[in] An array of pointers, each of which points to an ICorDebugType object that represents a type argument for the object that is being instantiated.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="17b82-109">Hinweise</span><span class="sxs-lookup"><span data-stu-id="17b82-109">Remarks</span></span>  
 <span data-ttu-id="17b82-110">Bei der `NewParameterizedObjectNoConstructor`-Methode tritt ein Fehler auf, wenn eine falsche Anzahl von Typargumenten oder falsche Typen von Typargumenten bestanden werden.</span><span class="sxs-lookup"><span data-stu-id="17b82-110">The `NewParameterizedObjectNoConstructor` method will fail if an incorrect number of type arguments or the wrong types of type arguments are passed.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="17b82-111">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="17b82-111">Requirements</span></span>  
 <span data-ttu-id="17b82-112">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="17b82-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="17b82-113">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="17b82-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="17b82-114">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="17b82-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="17b82-115">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="17b82-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
