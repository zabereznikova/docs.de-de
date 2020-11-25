---
title: ICorDebugType::GetFirstTypeParameter-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugType.GetFirstTypeParameter
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugType::GetFirstTypeParameter
helpviewer_keywords:
- ICorDebugType::GetFirstTypeParameter method [.NET Framework debugging]
- GetFirstTypeParameter method [.NET Framework debugging]
ms.assetid: 35bb594f-af6a-4349-83fe-e98702674e03
topic_type:
- apiref
ms.openlocfilehash: be69636056d5510b72dbce39917f5e8d3b05cd87
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95723973"
---
# <a name="icordebugtypegetfirsttypeparameter-method"></a><span data-ttu-id="cf6b7-102">ICorDebugType::GetFirstTypeParameter-Methode</span><span class="sxs-lookup"><span data-stu-id="cf6b7-102">ICorDebugType::GetFirstTypeParameter Method</span></span>

<span data-ttu-id="cf6b7-103">Ruft einen Schnittstellen Zeiger auf einen ICorDebugType ab, der den ersten <xref:System.Type> Parameter des Typs darstellt, der durch diesen dargestellt wird `ICorDebugType` .</span><span class="sxs-lookup"><span data-stu-id="cf6b7-103">Gets an interface pointer to an ICorDebugType that represents the first <xref:System.Type> parameter of the type represented by this `ICorDebugType`.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cf6b7-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="cf6b7-104">Syntax</span></span>  
  
```cpp  
HRESULT GetFirstTypeParameter (  
    [out] ICorDebugType   **value  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="cf6b7-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="cf6b7-105">Parameters</span></span>  

 `value`  
 <span data-ttu-id="cf6b7-106">vorgenommen Ein Zeiger auf die Adresse eines `ICorDebugType` Objekts, das den ersten Parameter darstellt.</span><span class="sxs-lookup"><span data-stu-id="cf6b7-106">[out] A pointer to the address of an `ICorDebugType` object that represents the first parameter.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="cf6b7-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="cf6b7-107">Remarks</span></span>  

 <span data-ttu-id="cf6b7-108">`GetFirstTypeParameter` kann in Fällen aufgerufen werden, in denen die zusätzlichen Informationen über den Typ höchstens einen Typparameter umfassen.</span><span class="sxs-lookup"><span data-stu-id="cf6b7-108">`GetFirstTypeParameter` can be called in cases where the additional information about the type involves, at most, one type parameter.</span></span> <span data-ttu-id="cf6b7-109">Insbesondere kann Sie verwendet werden, wenn der Typ eine ELEMENT_TYPE_ARRAY, ELEMENT_TYPE_SZARRAY, ELEMENT_TYPE_BYREF oder ELEMENT_TYPE_PTR ist, wie durch die [ICorDebugType:: GetType](icordebugtype-gettype-method.md) -Methode angegeben.</span><span class="sxs-lookup"><span data-stu-id="cf6b7-109">In particular, it can be used if the type is an ELEMENT_TYPE_ARRAY, ELEMENT_TYPE_SZARRAY, ELEMENT_TYPE_BYREF, or ELEMENT_TYPE_PTR, as indicated by the [ICorDebugType::GetType](icordebugtype-gettype-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cf6b7-110">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="cf6b7-110">Requirements</span></span>  

 <span data-ttu-id="cf6b7-111">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="cf6b7-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cf6b7-112">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="cf6b7-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="cf6b7-113">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="cf6b7-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="cf6b7-114">**.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cf6b7-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
