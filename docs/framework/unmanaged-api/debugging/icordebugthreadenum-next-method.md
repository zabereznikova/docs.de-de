---
title: ICorDebugThreadEnum::Next-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugThreadEnum.Next
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugThreadEnum::Next
helpviewer_keywords:
- ICorDebugThreadEnum::Next method [.NET Framework debugging]
- Next method, ICorDebugThreadEnum interface [.NET Framework debugging]
ms.assetid: f967c93d-9a7f-4aaf-99a1-a1317899ff3f
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b80e0cc026ce80950c14436abb2e84548f9adb64
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/06/2019
ms.locfileid: "57499575"
---
# <a name="icordebugthreadenumnext-method"></a><span data-ttu-id="c7d4e-102">ICorDebugThreadEnum::Next-Methode</span><span class="sxs-lookup"><span data-stu-id="c7d4e-102">ICorDebugThreadEnum::Next Method</span></span>
<span data-ttu-id="c7d4e-103">Ruft die Anzahl der angegebenen ICorDebugThread-Instanzen aus der Enumeration ab, an der aktuellen Position ab.</span><span class="sxs-lookup"><span data-stu-id="c7d4e-103">Gets the number of specified ICorDebugThread instances from the enumeration, starting at the current position.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c7d4e-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="c7d4e-104">Syntax</span></span>  
  
```  
HRESULT Next (  
    [in] ULONG celt,  
    [out, size_is(celt), length_is(*pceltFetched)]  
        ICorDebugThread *threads[],  
    [out] ULONG *pceltFetched  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c7d4e-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="c7d4e-105">Parameters</span></span>  
 `celt`  
 <span data-ttu-id="c7d4e-106">[in] Die Anzahl der `ICorDebugThread` Instanzen abgerufen werden sollen.</span><span class="sxs-lookup"><span data-stu-id="c7d4e-106">[in] The number of `ICorDebugThread` instances to be retrieved.</span></span>  
  
 `threads`  
 <span data-ttu-id="c7d4e-107">[out] Ein Array von Zeigern, die jeweils auf eine `ICorDebugThread` -Objekt, das einen Thread darstellt.</span><span class="sxs-lookup"><span data-stu-id="c7d4e-107">[out] An array of pointers, each of which points to an `ICorDebugThread` object that represents a thread.</span></span>  
  
 `pceltFetched`  
 <span data-ttu-id="c7d4e-108">[out] Zeiger auf die Anzahl der `ICorDebugThread` Instanzen, die tatsächlich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="c7d4e-108">[out] Pointer to the number of `ICorDebugThread` instances actually returned.</span></span> <span data-ttu-id="c7d4e-109">Dieser Wert kann null sein, wenn `celt` ist.</span><span class="sxs-lookup"><span data-stu-id="c7d4e-109">This value may be null if `celt` is one.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c7d4e-110">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="c7d4e-110">Requirements</span></span>  
 <span data-ttu-id="c7d4e-111">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c7d4e-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c7d4e-112">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="c7d4e-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="c7d4e-113">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c7d4e-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c7d4e-114">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c7d4e-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
