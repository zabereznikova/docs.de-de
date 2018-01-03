---
title: ICorDebugEval2::NewParameterizedObject-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugEval2.NewParameterizedObject
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugEval2::NewParameterizedObject
helpviewer_keywords:
- NewParameterizedObject method [.NET Framework debugging]
- ICorDebugEval2::NewParameterizedObject method [.NET Framework debugging]
ms.assetid: 3d705463-e640-4249-8036-4e8206d03cfe
topic_type: apiref
caps.latest.revision: "16"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 39b69a82f25ab6df5f2bd2f6dc70caf1bf13a0f9
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugeval2newparameterizedobject-method"></a><span data-ttu-id="66d4e-102">ICorDebugEval2::NewParameterizedObject-Methode</span><span class="sxs-lookup"><span data-stu-id="66d4e-102">ICorDebugEval2::NewParameterizedObject Method</span></span>
<span data-ttu-id="66d4e-103">Instanziiert ein neue parametrisierter Typ-Objekt, und die Konstruktormethode des Objekts aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="66d4e-103">Instantiates a new parameterized type object and calls the object's constructor method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="66d4e-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="66d4e-104">Syntax</span></span>  
  
```  
HRESULT NewParameterizedObject (  
    [in] ICorDebugFunction     *pConstructor,  
    [in] ULONG32               nTypeArgs,  
    [in, size_is(nTypeArgs)] ICorDebugType *ppTypeArgs[],  
    [in] ULONG32               nArgs,  
    [in, size_is(nArgs)] ICorDebugValue *ppArgs[]  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="66d4e-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="66d4e-105">Parameters</span></span>  
 `pConstructor`  
 <span data-ttu-id="66d4e-106">[in] Ein Zeiger auf ein ICorDebugFunction-Objekt, das den Konstruktor des Objekts zu instanziierenden darstellt.</span><span class="sxs-lookup"><span data-stu-id="66d4e-106">[in] A pointer to an ICorDebugFunction object that represents the constructor of the object to be instantiated.</span></span>  
  
 `nTypeArgs`  
 <span data-ttu-id="66d4e-107">[in] Die Anzahl von Typargumenten übergeben.</span><span class="sxs-lookup"><span data-stu-id="66d4e-107">[in] The number of type arguments passed.</span></span>  
  
 `ppTypeArgs`  
 <span data-ttu-id="66d4e-108">[in] Ein Array von Zeigern, von denen jedes auf ein ICorDebugType verweist, die ein Type-Argument für das Objekt darstellt, die instanziiert wird.</span><span class="sxs-lookup"><span data-stu-id="66d4e-108">[in] An array of pointers, each of which points to an ICorDebugType object that represents a type argument for the object that is being instantiated.</span></span>  
  
 `nArgs`  
 <span data-ttu-id="66d4e-109">[in] Die Anzahl von Argumenten an den Konstruktor übergeben.</span><span class="sxs-lookup"><span data-stu-id="66d4e-109">[in] The number of arguments passed to the constructor.</span></span>  
  
 `ppArgs`  
 <span data-ttu-id="66d4e-110">[in] Ein Array von Zeigern, von denen jedes auf ein ICorDebugValue-Objekt verweist, die einen Wert des Arguments darstellt, der an den Konstruktor übergeben wird.</span><span class="sxs-lookup"><span data-stu-id="66d4e-110">[in] An array of pointers, each of which points to an ICorDebugValue object that represents an argument value that is passed to the constructor.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="66d4e-111">Hinweise</span><span class="sxs-lookup"><span data-stu-id="66d4e-111">Remarks</span></span>  
 <span data-ttu-id="66d4e-112">Der Konstruktor des Objekts dauert <xref:System.Type> Parameter.</span><span class="sxs-lookup"><span data-stu-id="66d4e-112">The object's constructor may take <xref:System.Type> parameters.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="66d4e-113">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="66d4e-113">Requirements</span></span>  
 <span data-ttu-id="66d4e-114">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="66d4e-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="66d4e-115">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="66d4e-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="66d4e-116">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="66d4e-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="66d4e-117">**.NET Framework-Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="66d4e-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
