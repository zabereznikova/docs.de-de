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
ms.openlocfilehash: e96dccdd2836eebb08e88fe09dda531cd62baeee
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33420000"
---
# <a name="icordebugprocess5getarraylayout-method"></a><span data-ttu-id="61c75-102">ICorDebugProcess5::GetArrayLayout-Methode</span><span class="sxs-lookup"><span data-stu-id="61c75-102">ICorDebugProcess5::GetArrayLayout Method</span></span>
<span data-ttu-id="61c75-103">Enthält Informationen zum Layout von Arraytypen dar.</span><span class="sxs-lookup"><span data-stu-id="61c75-103">Provides information about the layout of array types.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="61c75-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="61c75-104">Syntax</span></span>  
  
```  
HRESULT GetArrayLayout(    [in] COR_TYPEID id,     [out] COR_ARRAY_LAYOUT *pLayout);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="61c75-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="61c75-105">Parameters</span></span>  
 `id`  
 <span data-ttu-id="61c75-106">[in] Ein [COR_TYPEID](../../../../docs/framework/unmanaged-api/debugging/cor-typeid-structure.md) Token, das das Array gibt an, deren Layout erwünscht ist.</span><span class="sxs-lookup"><span data-stu-id="61c75-106">[in] A [COR_TYPEID](../../../../docs/framework/unmanaged-api/debugging/cor-typeid-structure.md) token that specifies the array whose layout is desired.</span></span>  
  
 `pLayout`  
 <span data-ttu-id="61c75-107">[out] Ein Zeiger auf eine [COR_ARRAY_LAYOUT](../../../../docs/framework/unmanaged-api/debugging/cor-array-layout-structure.md) -Struktur, die Informationen zum Layout des Arrays im Arbeitsspeicher enthält.</span><span class="sxs-lookup"><span data-stu-id="61c75-107">[out] A pointer to a [COR_ARRAY_LAYOUT](../../../../docs/framework/unmanaged-api/debugging/cor-array-layout-structure.md) structure that contains information about the layout of the array in memory.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="61c75-108">Hinweise</span><span class="sxs-lookup"><span data-stu-id="61c75-108">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="61c75-109">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="61c75-109">Requirements</span></span>  
 <span data-ttu-id="61c75-110">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="61c75-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="61c75-111">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="61c75-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="61c75-112">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="61c75-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="61c75-113">**.NET Framework-Versionen:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="61c75-113">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="61c75-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="61c75-114">See Also</span></span>  
 [<span data-ttu-id="61c75-115">ICorDebugProcess5-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="61c75-115">ICorDebugProcess5 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-interface.md)  
 [<span data-ttu-id="61c75-116">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="61c75-116">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
