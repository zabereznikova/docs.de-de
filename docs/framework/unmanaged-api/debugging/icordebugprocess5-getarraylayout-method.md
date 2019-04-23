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
ms.openlocfilehash: 332de11790e78b712a429365bd89cc9e41539edc
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59105520"
---
# <a name="icordebugprocess5getarraylayout-method"></a><span data-ttu-id="08557-102">ICorDebugProcess5::GetArrayLayout-Methode</span><span class="sxs-lookup"><span data-stu-id="08557-102">ICorDebugProcess5::GetArrayLayout Method</span></span>
<span data-ttu-id="08557-103">Enthält Informationen über das Layout von Arraytypen dar.</span><span class="sxs-lookup"><span data-stu-id="08557-103">Provides information about the layout of array types.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="08557-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="08557-104">Syntax</span></span>  
  
```  
HRESULT GetArrayLayout(    [in] COR_TYPEID id,     [out] COR_ARRAY_LAYOUT *pLayout);  
```  
  
## <a name="parameters"></a><span data-ttu-id="08557-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="08557-105">Parameters</span></span>  
 `id`  
 <span data-ttu-id="08557-106">[in] Ein [COR_TYPEID](../../../../docs/framework/unmanaged-api/debugging/cor-typeid-structure.md) Token, das das Array gibt an, deren Layout erwünscht ist.</span><span class="sxs-lookup"><span data-stu-id="08557-106">[in] A [COR_TYPEID](../../../../docs/framework/unmanaged-api/debugging/cor-typeid-structure.md) token that specifies the array whose layout is desired.</span></span>  
  
 `pLayout`  
 <span data-ttu-id="08557-107">[out] Ein Zeiger auf eine [COR_ARRAY_LAYOUT](../../../../docs/framework/unmanaged-api/debugging/cor-array-layout-structure.md) -Struktur, die Informationen über das Layout des Arrays im Arbeitsspeicher enthält.</span><span class="sxs-lookup"><span data-stu-id="08557-107">[out] A pointer to a [COR_ARRAY_LAYOUT](../../../../docs/framework/unmanaged-api/debugging/cor-array-layout-structure.md) structure that contains information about the layout of the array in memory.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="08557-108">Hinweise</span><span class="sxs-lookup"><span data-stu-id="08557-108">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="08557-109">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="08557-109">Requirements</span></span>  
 <span data-ttu-id="08557-110">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="08557-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="08557-111">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="08557-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="08557-112">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="08557-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="08557-113">**.NET Framework-Versionen:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="08557-113">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="08557-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="08557-114">See also</span></span>

- [<span data-ttu-id="08557-115">ICorDebugProcess5-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="08557-115">ICorDebugProcess5 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-interface.md)
- [<span data-ttu-id="08557-116">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="08557-116">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
