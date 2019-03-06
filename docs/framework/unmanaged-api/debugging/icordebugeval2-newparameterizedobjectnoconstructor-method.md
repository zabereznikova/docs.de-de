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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 6feef7b1e1f09107cd2a57555df07bebec86effa
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/06/2019
ms.locfileid: "57466981"
---
# <a name="icordebugeval2newparameterizedobjectnoconstructor-method"></a><span data-ttu-id="7e8fe-102">ICorDebugEval2::NewParameterizedObjectNoConstructor-Methode</span><span class="sxs-lookup"><span data-stu-id="7e8fe-102">ICorDebugEval2::NewParameterizedObjectNoConstructor Method</span></span>
<span data-ttu-id="7e8fe-103">Instanziiert ein neues parametrisierten Typ-Objekt der angegebenen Klasse ohne zu versuchen, eine Konstruktormethode aufrufen.</span><span class="sxs-lookup"><span data-stu-id="7e8fe-103">Instantiates a new parameterized type object of the specified class without attempting to call a constructor method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7e8fe-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="7e8fe-104">Syntax</span></span>  
  
```  
HRESULT NewParameterizedObjectNoConstructor (  
    [in] ICorDebugClass        *pClass,  
    [in] ULONG32               nTypeArgs,  
    [in, size_is(nTypeArgs)] ICorDebugType *ppTypeArgs[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7e8fe-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="7e8fe-105">Parameters</span></span>  
 `pClass`  
 <span data-ttu-id="7e8fe-106">[in] Ein Zeiger auf ein ICorDebugClass-Objekt, das die Klasse des Objekts zu instanziierenden darstellt.</span><span class="sxs-lookup"><span data-stu-id="7e8fe-106">[in] A pointer to an ICorDebugClass object that represents the class of the object to be instantiated.</span></span>  
  
 `nTypeArgs`  
 <span data-ttu-id="7e8fe-107">[in] Die Anzahl von Typargumenten übergeben.</span><span class="sxs-lookup"><span data-stu-id="7e8fe-107">[in] The number of type arguments passed.</span></span>  
  
 `ppTypeArgs`  
 <span data-ttu-id="7e8fe-108">[in] Ein Array von Zeigern, von denen jeder zu einem ICorDebugType-Objekt verweist, die ein Typargument für das Objekt darstellt, die instanziiert wird.</span><span class="sxs-lookup"><span data-stu-id="7e8fe-108">[in] An array of pointers, each of which points to an ICorDebugType object that represents a type argument for the object that is being instantiated.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="7e8fe-109">Hinweise</span><span class="sxs-lookup"><span data-stu-id="7e8fe-109">Remarks</span></span>  
 <span data-ttu-id="7e8fe-110">Die `NewParameterizedObjectNoConstructor` Methode schlägt fehl, wenn eine falsche Anzahl von Typargumenten, oder die falschen Arten von Typargumenten übergeben werden.</span><span class="sxs-lookup"><span data-stu-id="7e8fe-110">The `NewParameterizedObjectNoConstructor` method will fail if an incorrect number of type arguments or the wrong types of type arguments are passed.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7e8fe-111">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="7e8fe-111">Requirements</span></span>  
 <span data-ttu-id="7e8fe-112">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7e8fe-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7e8fe-113">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="7e8fe-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="7e8fe-114">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="7e8fe-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="7e8fe-115">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7e8fe-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
