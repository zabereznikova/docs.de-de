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
ms.openlocfilehash: aad5a285fc2280dc062b0f4cbb69977a7e605e9c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33412768"
---
# <a name="icordebugeval2newparameterizedobjectnoconstructor-method"></a><span data-ttu-id="60c59-102">ICorDebugEval2::NewParameterizedObjectNoConstructor-Methode</span><span class="sxs-lookup"><span data-stu-id="60c59-102">ICorDebugEval2::NewParameterizedObjectNoConstructor Method</span></span>
<span data-ttu-id="60c59-103">Instanziiert ein neue parametrisierter Typ-Objekt der angegebenen Klasse ohne zu versuchen, eine Konstruktormethode aufrufen.</span><span class="sxs-lookup"><span data-stu-id="60c59-103">Instantiates a new parameterized type object of the specified class without attempting to call a constructor method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="60c59-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="60c59-104">Syntax</span></span>  
  
```  
HRESULT NewParameterizedObjectNoConstructor (  
    [in] ICorDebugClass        *pClass,  
    [in] ULONG32               nTypeArgs,  
    [in, size_is(nTypeArgs)] ICorDebugType *ppTypeArgs[]  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="60c59-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="60c59-105">Parameters</span></span>  
 `pClass`  
 <span data-ttu-id="60c59-106">[in] Ein Zeiger auf ein ICorDebugClass-Objekt, das die Klasse des Objekts zu instanziierenden darstellt.</span><span class="sxs-lookup"><span data-stu-id="60c59-106">[in] A pointer to an ICorDebugClass object that represents the class of the object to be instantiated.</span></span>  
  
 `nTypeArgs`  
 <span data-ttu-id="60c59-107">[in] Die Anzahl von Typargumenten übergeben.</span><span class="sxs-lookup"><span data-stu-id="60c59-107">[in] The number of type arguments passed.</span></span>  
  
 `ppTypeArgs`  
 <span data-ttu-id="60c59-108">[in] Ein Array von Zeigern, von denen jedes auf ein ICorDebugType verweist, die ein Type-Argument für das Objekt darstellt, die instanziiert wird.</span><span class="sxs-lookup"><span data-stu-id="60c59-108">[in] An array of pointers, each of which points to an ICorDebugType object that represents a type argument for the object that is being instantiated.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="60c59-109">Hinweise</span><span class="sxs-lookup"><span data-stu-id="60c59-109">Remarks</span></span>  
 <span data-ttu-id="60c59-110">Die `NewParameterizedObjectNoConstructor` Methode schlägt fehl, wenn eine falsche Anzahl von Typargumenten oder die falschen Arten von Typargumenten übergeben werden.</span><span class="sxs-lookup"><span data-stu-id="60c59-110">The `NewParameterizedObjectNoConstructor` method will fail if an incorrect number of type arguments or the wrong types of type arguments are passed.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="60c59-111">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="60c59-111">Requirements</span></span>  
 <span data-ttu-id="60c59-112">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="60c59-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="60c59-113">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="60c59-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="60c59-114">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="60c59-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="60c59-115">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="60c59-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
