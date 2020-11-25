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
ms.openlocfilehash: 0b17bd729733665fbc4645aecd2e588b7eba14bb
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95729693"
---
# <a name="icordebugeval2createvaluefortype-method"></a><span data-ttu-id="9389f-102">ICorDebugEval2::CreateValueForType-Methode</span><span class="sxs-lookup"><span data-stu-id="9389f-102">ICorDebugEval2::CreateValueForType Method</span></span>

<span data-ttu-id="9389f-103">Ruft einen Zeiger auf einen neuen ICorDebugValue des angegebenen Typs mit einem Anfangswert von 0 (null) oder NULL ab.</span><span class="sxs-lookup"><span data-stu-id="9389f-103">Gets a pointer to a new ICorDebugValue of the specified type, with an initial value of zero or null.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9389f-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="9389f-104">Syntax</span></span>  
  
```cpp  
HRESULT CreateValueForType (  
    [in] ICorDebugType         *pType,  
    [out] ICorDebugValue       **ppValue  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9389f-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="9389f-105">Parameters</span></span>  

 `pType`  
 <span data-ttu-id="9389f-106">in Zeiger auf ein ICorDebugType-Objekt, das den Typ darstellt.</span><span class="sxs-lookup"><span data-stu-id="9389f-106">[in] Pointer to an ICorDebugType object that represents the type.</span></span>  
  
 `ppValue`  
 <span data-ttu-id="9389f-107">vorgenommen Ein Zeiger auf die Adresse eines `ICorDebugValue` Objekts, das den Wert darstellt.</span><span class="sxs-lookup"><span data-stu-id="9389f-107">[out] Pointer to the address of an `ICorDebugValue` object that represents the value.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9389f-108">Hinweise</span><span class="sxs-lookup"><span data-stu-id="9389f-108">Remarks</span></span>  

 <span data-ttu-id="9389f-109">`CreateValueForType` generalisiert [ICorDebugEval:: foratevalue](icordebugeval-createvalue-method.md) , indem es Ihnen ermöglicht, einen beliebigen Objekttyp anzugeben, einschließlich konstruierter Typen wie `List<int>` .</span><span class="sxs-lookup"><span data-stu-id="9389f-109">`CreateValueForType` generalizes [ICorDebugEval::CreateValue](icordebugeval-createvalue-method.md) by allowing you to specify an arbitrary object type, including constructed types such as `List<int>`.</span></span> <span data-ttu-id="9389f-110">Der einzige Zweck dieser Methode besteht darin, einen Wert zu generieren, der an eine Funktions Auswertung übermittelt werden kann.</span><span class="sxs-lookup"><span data-stu-id="9389f-110">The only purpose of this method is to generate a value that can be passed to a function evaluation.</span></span>  
  
 <span data-ttu-id="9389f-111">Der Typ muss eine Klasse oder ein Werttyp sein.</span><span class="sxs-lookup"><span data-stu-id="9389f-111">The type must be a class or a value type.</span></span> <span data-ttu-id="9389f-112">Sie können diese Methode nicht verwenden, um Array Werte oder Zeichen folgen Werte zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="9389f-112">You cannot use this method to create array values or string values.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9389f-113">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="9389f-113">Requirements</span></span>  

 <span data-ttu-id="9389f-114">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9389f-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9389f-115">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="9389f-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="9389f-116">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="9389f-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="9389f-117">**.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9389f-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
