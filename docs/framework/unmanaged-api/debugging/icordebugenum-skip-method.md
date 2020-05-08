---
title: ICorDebugEnum::Skip-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugEnum.Skip
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugEnum::Skip
helpviewer_keywords:
- ICorDebugEnum::Skip method [.NET Framework debugging]
- Skip method, ICorDebugEnum interface [.NET Framework debugging]
ms.assetid: e925d88a-67a5-4f76-88b8-09cedeed0232
topic_type:
- apiref
ms.openlocfilehash: 64d9db09b3e604247ab6a26cdca9eca22adbaace
ms.sourcegitcommit: fff146ba3fd1762c8c432d95c8b877825ae536fc
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/08/2020
ms.locfileid: "82976303"
---
# <a name="icordebugenumskip-method"></a><span data-ttu-id="e9924-102">ICorDebugEnum::Skip-Methode</span><span class="sxs-lookup"><span data-stu-id="e9924-102">ICorDebugEnum::Skip Method</span></span>
<span data-ttu-id="e9924-103">Verschiebt den Cursor in der-Enumeration um die angegebene Anzahl von Elementen vorwärts.</span><span class="sxs-lookup"><span data-stu-id="e9924-103">Moves the cursor forward in the enumeration by the specified number of items.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e9924-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="e9924-104">Syntax</span></span>  
  
```cpp  
HRESULT Skip (  
    [in] ULONG celt  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e9924-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="e9924-105">Parameters</span></span>  
 `celt`  
 <span data-ttu-id="e9924-106">in Die Anzahl der Elemente, um die der Cursor vorwärts verschoben werden soll.</span><span class="sxs-lookup"><span data-stu-id="e9924-106">[in] The number of items by which to move the cursor forward.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e9924-107">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="e9924-107">Requirements</span></span>  
 <span data-ttu-id="e9924-108">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e9924-108">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e9924-109">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="e9924-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="e9924-110">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e9924-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e9924-111">**.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e9924-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e9924-112">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="e9924-112">See also</span></span>

- [<span data-ttu-id="e9924-113">ICorDebugEnum-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="e9924-113">ICorDebugEnum Interface</span></span>](icordebugenum-interface1.md)
