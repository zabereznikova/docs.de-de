---
title: ICorDebugAppDomain2::GetFunctionPointerType-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugAppDomain2.GetFunctionPointerType
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugAppDomain2::GetFunctionPointerType
helpviewer_keywords:
- ICorDebugAppDomain2::GetFunctionPointerType method [.NET Framework debugging]
- GetFunctionPointerType method [.NET Framework debugging]
ms.assetid: 0aba6096-5b38-435c-a72a-86d35db4daef
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: d497fd8e659a24add25df63c4ce48e710dcb0c6d
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33403792"
---
# <a name="icordebugappdomain2getfunctionpointertype-method"></a><span data-ttu-id="e2d69-102">ICorDebugAppDomain2::GetFunctionPointerType-Methode</span><span class="sxs-lookup"><span data-stu-id="e2d69-102">ICorDebugAppDomain2::GetFunctionPointerType Method</span></span>
<span data-ttu-id="e2d69-103">Ruft einen Zeiger auf eine Funktion, die einer bestimmten Signatur ab.</span><span class="sxs-lookup"><span data-stu-id="e2d69-103">Gets a pointer to a function that has a given signature.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e2d69-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="e2d69-104">Syntax</span></span>  
  
```  
HRESULT GetFunctionPointerType (  
    [in] ULONG32                             nTypeArgs,  
    [in, size_is(nTypeArgs)] ICorDebugType   *ppTypeArgs[],  
    [out] ICorDebugType                      **ppType  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="e2d69-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="e2d69-105">Parameters</span></span>  
 `nTypeArgs`  
 <span data-ttu-id="e2d69-106">[in] Die Anzahl der Argumente des Typs für die Funktion.</span><span class="sxs-lookup"><span data-stu-id="e2d69-106">[in] The number of type arguments for the function.</span></span>  
  
 `ppTypeArgs`  
 <span data-ttu-id="e2d69-107">[in] Ein Array von Zeigern, von denen jedes auf ein ICorDebugType verweist, die ein Type-Argument der Funktion darstellt.</span><span class="sxs-lookup"><span data-stu-id="e2d69-107">[in] An array of pointers, each of which points to an ICorDebugType object that represents a type argument of the function.</span></span> <span data-ttu-id="e2d69-108">Das erste Element ist der Rückgabetyp; jedes andere Element ist ein Parameter.</span><span class="sxs-lookup"><span data-stu-id="e2d69-108">The first element is the return type; each of the other elements is a parameter type.</span></span>  
  
 `ppType`  
 <span data-ttu-id="e2d69-109">[out] Ein Zeiger auf die Adresse des ein `ICorDebugType` -Objekt, das der Zeiger auf die Funktion darstellt.</span><span class="sxs-lookup"><span data-stu-id="e2d69-109">[out] A pointer to the address of an `ICorDebugType` object that represents the pointer to the function.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e2d69-110">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="e2d69-110">Requirements</span></span>  
 <span data-ttu-id="e2d69-111">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e2d69-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e2d69-112">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="e2d69-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="e2d69-113">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e2d69-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e2d69-114">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e2d69-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
