---
title: ICorDebugEval2::CreateValueForType-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugEval2.CreateValueForType
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugEval2::CreateValueForType
helpviewer_keywords:
- CreateValueForType method [.NET Framework debugging]
- ICorDebugEval2::CreateValueForType method [.NET Framework debugging]
ms.assetid: ea38ae20-7e0a-427a-be77-d78fae719d82
topic_type:
- apiref
ms.openlocfilehash: 8632799b68ae8f92835d1774472bc1432d886f3b
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/28/2020
ms.locfileid: "76793483"
---
# <a name="icordebugeval2createvaluefortype-method"></a><span data-ttu-id="db0e8-102">ICorDebugEval2::CreateValueForType-Methode</span><span class="sxs-lookup"><span data-stu-id="db0e8-102">ICorDebugEval2::CreateValueForType Method</span></span>
<span data-ttu-id="db0e8-103">Ruft einen Zeiger auf einen neuen ICorDebugValue des angegebenen Typs mit einem Anfangswert von 0 (null) oder NULL ab.</span><span class="sxs-lookup"><span data-stu-id="db0e8-103">Gets a pointer to a new ICorDebugValue of the specified type, with an initial value of zero or null.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="db0e8-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="db0e8-104">Syntax</span></span>  
  
```cpp  
HRESULT CreateValueForType (  
    [in] ICorDebugType         *pType,  
    [out] ICorDebugValue       **ppValue  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="db0e8-105">Parameters</span><span class="sxs-lookup"><span data-stu-id="db0e8-105">Parameters</span></span>  
 `pType`  
 <span data-ttu-id="db0e8-106">[in] Ein Zeiger auf ein ICorDebugType-Objekt, das den Typ darstellt.</span><span class="sxs-lookup"><span data-stu-id="db0e8-106">[in] Pointer to an ICorDebugType object that represents the type.</span></span>  
  
 `ppValue`  
 <span data-ttu-id="db0e8-107">vorgenommen Ein Zeiger auf die Adresse eines `ICorDebugValue` Objekts, das den Wert darstellt.</span><span class="sxs-lookup"><span data-stu-id="db0e8-107">[out] Pointer to the address of an `ICorDebugValue` object that represents the value.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="db0e8-108">Hinweise</span><span class="sxs-lookup"><span data-stu-id="db0e8-108">Remarks</span></span>  
 <span data-ttu-id="db0e8-109">`CreateValueForType` generalisiert [ICorDebugEval:: foratevalue](icordebugeval-createvalue-method.md) , indem es Ihnen ermöglicht, einen beliebigen Objekttyp anzugeben, einschließlich konstruierter Typen, z. b. `List<int>`.</span><span class="sxs-lookup"><span data-stu-id="db0e8-109">`CreateValueForType` generalizes [ICorDebugEval::CreateValue](icordebugeval-createvalue-method.md) by allowing you to specify an arbitrary object type, including constructed types such as `List<int>`.</span></span> <span data-ttu-id="db0e8-110">Der einzige Zweck dieser Methode besteht darin, einen Wert zu generieren, der an eine Funktions Auswertung übermittelt werden kann.</span><span class="sxs-lookup"><span data-stu-id="db0e8-110">The only purpose of this method is to generate a value that can be passed to a function evaluation.</span></span>  
  
 <span data-ttu-id="db0e8-111">Der Typ muss eine Klasse oder ein Werttyp sein.</span><span class="sxs-lookup"><span data-stu-id="db0e8-111">The type must be a class or a value type.</span></span> <span data-ttu-id="db0e8-112">Sie können diese Methode nicht verwenden, um Array Werte oder Zeichen folgen Werte zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="db0e8-112">You cannot use this method to create array values or string values.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="db0e8-113">-Anforderungen</span><span class="sxs-lookup"><span data-stu-id="db0e8-113">Requirements</span></span>  
 <span data-ttu-id="db0e8-114">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="db0e8-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="db0e8-115">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="db0e8-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="db0e8-116">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="db0e8-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="db0e8-117">**.NET Framework Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="db0e8-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
