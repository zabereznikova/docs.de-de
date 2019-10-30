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
ms.openlocfilehash: 5a415c8f3124c08984f8101e1f4dbcae6bf96fbf
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73129613"
---
# <a name="icordebugprocess5getarraylayout-method"></a><span data-ttu-id="a2d46-102">ICorDebugProcess5::GetArrayLayout-Methode</span><span class="sxs-lookup"><span data-stu-id="a2d46-102">ICorDebugProcess5::GetArrayLayout Method</span></span>
<span data-ttu-id="a2d46-103">Stellt Informationen über das Layout von Array Typen bereit.</span><span class="sxs-lookup"><span data-stu-id="a2d46-103">Provides information about the layout of array types.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a2d46-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="a2d46-104">Syntax</span></span>  
  
```cpp  
HRESULT GetArrayLayout(    [in] COR_TYPEID id,     [out] COR_ARRAY_LAYOUT *pLayout);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a2d46-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="a2d46-105">Parameters</span></span>  
 `id`  
 <span data-ttu-id="a2d46-106">in Ein [COR_TYPEID](../../../../docs/framework/unmanaged-api/debugging/cor-typeid-structure.md) -Token, das das Array angibt, dessen Layout gewünscht wird.</span><span class="sxs-lookup"><span data-stu-id="a2d46-106">[in] A [COR_TYPEID](../../../../docs/framework/unmanaged-api/debugging/cor-typeid-structure.md) token that specifies the array whose layout is desired.</span></span>  
  
 `pLayout`  
 <span data-ttu-id="a2d46-107">vorgenommen Ein Zeiger auf eine [COR_ARRAY_LAYOUT](../../../../docs/framework/unmanaged-api/debugging/cor-array-layout-structure.md) -Struktur, die Informationen über das Layout des Arrays im Arbeitsspeicher enthält.</span><span class="sxs-lookup"><span data-stu-id="a2d46-107">[out] A pointer to a [COR_ARRAY_LAYOUT](../../../../docs/framework/unmanaged-api/debugging/cor-array-layout-structure.md) structure that contains information about the layout of the array in memory.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a2d46-108">Hinweise</span><span class="sxs-lookup"><span data-stu-id="a2d46-108">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a2d46-109">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="a2d46-109">Requirements</span></span>  
 <span data-ttu-id="a2d46-110">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a2d46-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a2d46-111">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="a2d46-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="a2d46-112">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a2d46-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a2d46-113">**.NET Framework-Versionen:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a2d46-113">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a2d46-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a2d46-114">See also</span></span>

- [<span data-ttu-id="a2d46-115">ICorDebugProcess5-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="a2d46-115">ICorDebugProcess5 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-interface.md)
- [<span data-ttu-id="a2d46-116">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="a2d46-116">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
