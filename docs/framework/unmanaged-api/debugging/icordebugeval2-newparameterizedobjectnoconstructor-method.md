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
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61667027"
---
# <a name="icordebugeval2newparameterizedobjectnoconstructor-method"></a><span data-ttu-id="fedb1-102">ICorDebugEval2::NewParameterizedObjectNoConstructor-Methode</span><span class="sxs-lookup"><span data-stu-id="fedb1-102">ICorDebugEval2::NewParameterizedObjectNoConstructor Method</span></span>
<span data-ttu-id="fedb1-103">Instanziiert ein neues parametrisierten Typ-Objekt der angegebenen Klasse ohne zu versuchen, eine Konstruktormethode aufrufen.</span><span class="sxs-lookup"><span data-stu-id="fedb1-103">Instantiates a new parameterized type object of the specified class without attempting to call a constructor method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fedb1-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="fedb1-104">Syntax</span></span>  
  
```  
HRESULT NewParameterizedObjectNoConstructor (  
    [in] ICorDebugClass        *pClass,  
    [in] ULONG32               nTypeArgs,  
    [in, size_is(nTypeArgs)] ICorDebugType *ppTypeArgs[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="fedb1-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="fedb1-105">Parameters</span></span>  
 `pClass`  
 <span data-ttu-id="fedb1-106">[in] Ein Zeiger auf ein ICorDebugClass-Objekt, das die Klasse des Objekts zu instanziierenden darstellt.</span><span class="sxs-lookup"><span data-stu-id="fedb1-106">[in] A pointer to an ICorDebugClass object that represents the class of the object to be instantiated.</span></span>  
  
 `nTypeArgs`  
 <span data-ttu-id="fedb1-107">[in] Die Anzahl von Typargumenten übergeben.</span><span class="sxs-lookup"><span data-stu-id="fedb1-107">[in] The number of type arguments passed.</span></span>  
  
 `ppTypeArgs`  
 <span data-ttu-id="fedb1-108">[in] Ein Array von Zeigern, von denen jeder zu einem ICorDebugType-Objekt verweist, die ein Typargument für das Objekt darstellt, die instanziiert wird.</span><span class="sxs-lookup"><span data-stu-id="fedb1-108">[in] An array of pointers, each of which points to an ICorDebugType object that represents a type argument for the object that is being instantiated.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="fedb1-109">Hinweise</span><span class="sxs-lookup"><span data-stu-id="fedb1-109">Remarks</span></span>  
 <span data-ttu-id="fedb1-110">Die `NewParameterizedObjectNoConstructor` Methode schlägt fehl, wenn eine falsche Anzahl von Typargumenten, oder die falschen Arten von Typargumenten übergeben werden.</span><span class="sxs-lookup"><span data-stu-id="fedb1-110">The `NewParameterizedObjectNoConstructor` method will fail if an incorrect number of type arguments or the wrong types of type arguments are passed.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fedb1-111">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="fedb1-111">Requirements</span></span>  
 <span data-ttu-id="fedb1-112">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="fedb1-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fedb1-113">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="fedb1-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="fedb1-114">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="fedb1-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="fedb1-115">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fedb1-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
