---
title: ICorDebugProcess5::GetArrayLayout-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugProcess5.GetArrayLayout
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugProcess5::GetArrayLayout
helpviewer_keywords:
- ICorDebugProcess5::GetArrayLayout method [.NET Framework debugging]
- GetArrayLayout method, ICorDebugProcess5 interface [.NET Framework debugging]
ms.assetid: 9a7393b9-9735-43c6-8616-afb103c432fd
topic_type: apiref
caps.latest.revision: "5"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 608cf003d71599a141b1009ef16c7b7bf89161aa
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugprocess5getarraylayout-method"></a><span data-ttu-id="1e697-102">ICorDebugProcess5::GetArrayLayout-Methode</span><span class="sxs-lookup"><span data-stu-id="1e697-102">ICorDebugProcess5::GetArrayLayout Method</span></span>
<span data-ttu-id="1e697-103">Enthält Informationen zum Layout von Arraytypen dar.</span><span class="sxs-lookup"><span data-stu-id="1e697-103">Provides information about the layout of array types.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1e697-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="1e697-104">Syntax</span></span>  
  
```  
HRESULT GetArrayLayout(    [in] COR_TYPEID id,     [out] COR_ARRAY_LAYOUT *pLayout);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="1e697-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="1e697-105">Parameters</span></span>  
 `id`  
 <span data-ttu-id="1e697-106">[in] Ein [COR_TYPEID](../../../../docs/framework/unmanaged-api/debugging/cor-typeid-structure.md) Token, das das Array gibt an, deren Layout erwünscht ist.</span><span class="sxs-lookup"><span data-stu-id="1e697-106">[in] A [COR_TYPEID](../../../../docs/framework/unmanaged-api/debugging/cor-typeid-structure.md) token that specifies the array whose layout is desired.</span></span>  
  
 `pLayout`  
 <span data-ttu-id="1e697-107">[out] Ein Zeiger auf eine [COR_ARRAY_LAYOUT](../../../../docs/framework/unmanaged-api/debugging/cor-array-layout-structure.md) -Struktur, die Informationen zum Layout des Arrays im Arbeitsspeicher enthält.</span><span class="sxs-lookup"><span data-stu-id="1e697-107">[out] A pointer to a [COR_ARRAY_LAYOUT](../../../../docs/framework/unmanaged-api/debugging/cor-array-layout-structure.md) structure that contains information about the layout of the array in memory.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="1e697-108">Hinweise</span><span class="sxs-lookup"><span data-stu-id="1e697-108">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1e697-109">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="1e697-109">Requirements</span></span>  
 <span data-ttu-id="1e697-110">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1e697-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1e697-111">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="1e697-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="1e697-112">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="1e697-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="1e697-113">**.NET Framework-Versionen:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1e697-113">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1e697-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="1e697-114">See Also</span></span>  
 [<span data-ttu-id="1e697-115">ICorDebugProcess5-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="1e697-115">ICorDebugProcess5 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-interface.md)  
 [<span data-ttu-id="1e697-116">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="1e697-116">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
