---
title: ICorDebugEval2::NewParameterizedObjectNoConstructor-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugEval2.NewParameterizedObjectNoConstructor
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugEval2::NewParameterizedObjectNoConstructor
helpviewer_keywords:
- NewParameterizedObjectNoConstructor method [.NET Framework debugging]
- ICorDebugEval2::NewParameterizedObjectNoConstructor method [.NET Framework debugging]
ms.assetid: f15b5b78-94f4-4eb9-b3b3-a621272f357c
topic_type: apiref
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 27e4693b39f9ce27ac18eb2fa542b5a0196f21cb
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugeval2newparameterizedobjectnoconstructor-method"></a><span data-ttu-id="342e3-102">ICorDebugEval2::NewParameterizedObjectNoConstructor-Methode</span><span class="sxs-lookup"><span data-stu-id="342e3-102">ICorDebugEval2::NewParameterizedObjectNoConstructor Method</span></span>
<span data-ttu-id="342e3-103">Instanziiert ein neue parametrisierter Typ-Objekt der angegebenen Klasse ohne zu versuchen, eine Konstruktormethode aufrufen.</span><span class="sxs-lookup"><span data-stu-id="342e3-103">Instantiates a new parameterized type object of the specified class without attempting to call a constructor method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="342e3-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="342e3-104">Syntax</span></span>  
  
```  
HRESULT NewParameterizedObjectNoConstructor (  
    [in] ICorDebugClass        *pClass,  
    [in] ULONG32               nTypeArgs,  
    [in, size_is(nTypeArgs)] ICorDebugType *ppTypeArgs[]  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="342e3-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="342e3-105">Parameters</span></span>  
 `pClass`  
 <span data-ttu-id="342e3-106">[in] Ein Zeiger auf ein ICorDebugClass-Objekt, das die Klasse des Objekts zu instanziierenden darstellt.</span><span class="sxs-lookup"><span data-stu-id="342e3-106">[in] A pointer to an ICorDebugClass object that represents the class of the object to be instantiated.</span></span>  
  
 `nTypeArgs`  
 <span data-ttu-id="342e3-107">[in] Die Anzahl von Typargumenten übergeben.</span><span class="sxs-lookup"><span data-stu-id="342e3-107">[in] The number of type arguments passed.</span></span>  
  
 `ppTypeArgs`  
 <span data-ttu-id="342e3-108">[in] Ein Array von Zeigern, von denen jedes auf ein ICorDebugType verweist, die ein Type-Argument für das Objekt darstellt, die instanziiert wird.</span><span class="sxs-lookup"><span data-stu-id="342e3-108">[in] An array of pointers, each of which points to an ICorDebugType object that represents a type argument for the object that is being instantiated.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="342e3-109">Hinweise</span><span class="sxs-lookup"><span data-stu-id="342e3-109">Remarks</span></span>  
 <span data-ttu-id="342e3-110">Die `NewParameterizedObjectNoConstructor` Methode schlägt fehl, wenn eine falsche Anzahl von Typargumenten oder die falschen Arten von Typargumenten übergeben werden.</span><span class="sxs-lookup"><span data-stu-id="342e3-110">The `NewParameterizedObjectNoConstructor` method will fail if an incorrect number of type arguments or the wrong types of type arguments are passed.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="342e3-111">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="342e3-111">Requirements</span></span>  
 <span data-ttu-id="342e3-112">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="342e3-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="342e3-113">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="342e3-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="342e3-114">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="342e3-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="342e3-115">**.NET Framework-Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="342e3-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
