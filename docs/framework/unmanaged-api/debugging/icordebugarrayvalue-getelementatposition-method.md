---
title: ICorDebugArrayValue::GetElementAtPosition-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugArrayValue.GetElementAtPosition
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugArrayValue::GetElementAtPosition
helpviewer_keywords:
- GetElementAtPosition method [.NET Framework debugging]
- ICorDebugArrayValue::GetElementAtPosition method [.NET Framework debugging]
ms.assetid: 6fd5eaa4-1997-4910-82f5-3887480db764
topic_type:
- apiref
ms.openlocfilehash: a6e5ecee9a89da98a73dfb20935c5ec594d5958f
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95732930"
---
# <a name="icordebugarrayvaluegetelementatposition-method"></a><span data-ttu-id="a6b86-102">ICorDebugArrayValue::GetElementAtPosition-Methode</span><span class="sxs-lookup"><span data-stu-id="a6b86-102">ICorDebugArrayValue::GetElementAtPosition Method</span></span>

<span data-ttu-id="a6b86-103">Ruft das Element an der angegebenen Position ab, wobei das Array als NULL basiertes, eindimensionales Array behandelt wird.</span><span class="sxs-lookup"><span data-stu-id="a6b86-103">Gets the element at the given position, treating the array as a zero-based, single-dimensional array.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a6b86-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="a6b86-104">Syntax</span></span>  
  
```cpp  
HRESULT GetElementAtPosition (  
    [in]  ULONG32          nPosition,  
    [out] ICorDebugValue   **ppValue  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a6b86-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="a6b86-105">Parameters</span></span>  

 `nPosition`  
 <span data-ttu-id="a6b86-106">in Die Position des abzurufenden Elements.</span><span class="sxs-lookup"><span data-stu-id="a6b86-106">[in] The position of the element to be retrieved.</span></span>  
  
 `ppValue`  
 <span data-ttu-id="a6b86-107">vorgenommen Ein Zeiger auf die Adresse eines icorentbugvalue-Objekts, das den Wert des Elements darstellt.</span><span class="sxs-lookup"><span data-stu-id="a6b86-107">[out] A pointer to the address of an ICorDebugValue object that represents the value of the element.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a6b86-108">Hinweise</span><span class="sxs-lookup"><span data-stu-id="a6b86-108">Remarks</span></span>  

 <span data-ttu-id="a6b86-109">Das Layout eines Arrays mit mehreren Dimensionen folgt dem C++-Stil des Array Layouts.</span><span class="sxs-lookup"><span data-stu-id="a6b86-109">The layout of a multi-dimension array follows the C++ style of array layout.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a6b86-110">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="a6b86-110">Requirements</span></span>  

 <span data-ttu-id="a6b86-111">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a6b86-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a6b86-112">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="a6b86-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="a6b86-113">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a6b86-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a6b86-114">**.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a6b86-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
