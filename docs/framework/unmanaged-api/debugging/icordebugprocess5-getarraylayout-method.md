---
title: ICorDebugProcess5::GetArrayLayout-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugProcess5.GetArrayLayout
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess5::GetArrayLayout
helpviewer_keywords:
- ICorDebugProcess5::GetArrayLayout method [.NET Framework debugging]
- GetArrayLayout method, ICorDebugProcess5 interface [.NET Framework debugging]
ms.assetid: 9a7393b9-9735-43c6-8616-afb103c432fd
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: f5cff3f3f577a0c7ef04a226ec70a2722c89b5c8
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/06/2019
ms.locfileid: "57496884"
---
# <a name="icordebugprocess5getarraylayout-method"></a><span data-ttu-id="5f32f-102">ICorDebugProcess5::GetArrayLayout-Methode</span><span class="sxs-lookup"><span data-stu-id="5f32f-102">ICorDebugProcess5::GetArrayLayout Method</span></span>
<span data-ttu-id="5f32f-103">Enthält Informationen über das Layout von Arraytypen dar.</span><span class="sxs-lookup"><span data-stu-id="5f32f-103">Provides information about the layout of array types.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5f32f-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="5f32f-104">Syntax</span></span>  
  
```  
HRESULT GetArrayLayout(    [in] COR_TYPEID id,     [out] COR_ARRAY_LAYOUT *pLayout);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5f32f-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="5f32f-105">Parameters</span></span>  
 `id`  
 <span data-ttu-id="5f32f-106">[in] Ein [COR_TYPEID](../../../../docs/framework/unmanaged-api/debugging/cor-typeid-structure.md) Token, das das Array gibt an, deren Layout erwünscht ist.</span><span class="sxs-lookup"><span data-stu-id="5f32f-106">[in] A [COR_TYPEID](../../../../docs/framework/unmanaged-api/debugging/cor-typeid-structure.md) token that specifies the array whose layout is desired.</span></span>  
  
 `pLayout`  
 <span data-ttu-id="5f32f-107">[out] Ein Zeiger auf eine [COR_ARRAY_LAYOUT](../../../../docs/framework/unmanaged-api/debugging/cor-array-layout-structure.md) -Struktur, die Informationen über das Layout des Arrays im Arbeitsspeicher enthält.</span><span class="sxs-lookup"><span data-stu-id="5f32f-107">[out] A pointer to a [COR_ARRAY_LAYOUT](../../../../docs/framework/unmanaged-api/debugging/cor-array-layout-structure.md) structure that contains information about the layout of the array in memory.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5f32f-108">Hinweise</span><span class="sxs-lookup"><span data-stu-id="5f32f-108">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5f32f-109">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="5f32f-109">Requirements</span></span>  
 <span data-ttu-id="5f32f-110">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5f32f-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5f32f-111">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="5f32f-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="5f32f-112">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5f32f-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="5f32f-113">**.NET Framework-Versionen:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5f32f-113">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5f32f-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="5f32f-114">See also</span></span>
- [<span data-ttu-id="5f32f-115">ICorDebugProcess5-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="5f32f-115">ICorDebugProcess5 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-interface.md)
- [<span data-ttu-id="5f32f-116">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="5f32f-116">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
