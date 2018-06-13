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
ms.openlocfilehash: 050bfb08dfd95e29b6534f69dbd35400d59e6099
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33419603"
---
# <a name="icordebugthreadenumnext-method"></a><span data-ttu-id="4a5c6-102">ICorDebugThreadEnum::Next-Methode</span><span class="sxs-lookup"><span data-stu-id="4a5c6-102">ICorDebugThreadEnum::Next Method</span></span>
<span data-ttu-id="4a5c6-103">Ruft die Anzahl der angegebenen ICorDebugThread-Instanzen aus der Enumeration, beginnend mit der aktuellen Position ab.</span><span class="sxs-lookup"><span data-stu-id="4a5c6-103">Gets the number of specified ICorDebugThread instances from the enumeration, starting at the current position.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4a5c6-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="4a5c6-104">Syntax</span></span>  
  
```  
HRESULT Next (  
    [in] ULONG celt,  
    [out, size_is(celt), length_is(*pceltFetched)]  
        ICorDebugThread *threads[],  
    [out] ULONG *pceltFetched  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="4a5c6-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="4a5c6-105">Parameters</span></span>  
 `celt`  
 <span data-ttu-id="4a5c6-106">[in] Die Anzahl der `ICorDebugThread` Instanzen abgerufen werden sollen.</span><span class="sxs-lookup"><span data-stu-id="4a5c6-106">[in] The number of `ICorDebugThread` instances to be retrieved.</span></span>  
  
 `threads`  
 <span data-ttu-id="4a5c6-107">[out] Ein Array von Zeigern, die jeweils auf ein `ICorDebugThread` Objekt, das einen Thread darstellt.</span><span class="sxs-lookup"><span data-stu-id="4a5c6-107">[out] An array of pointers, each of which points to an `ICorDebugThread` object that represents a thread.</span></span>  
  
 `pceltFetched`  
 <span data-ttu-id="4a5c6-108">[out] Zeiger auf die Anzahl der `ICorDebugThread` Instanzen, die tatsächlich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="4a5c6-108">[out] Pointer to the number of `ICorDebugThread` instances actually returned.</span></span> <span data-ttu-id="4a5c6-109">Dieser Wert kann null sein, wenn `celt` ist ein.</span><span class="sxs-lookup"><span data-stu-id="4a5c6-109">This value may be null if `celt` is one.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4a5c6-110">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="4a5c6-110">Requirements</span></span>  
 <span data-ttu-id="4a5c6-111">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4a5c6-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4a5c6-112">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="4a5c6-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="4a5c6-113">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="4a5c6-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="4a5c6-114">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4a5c6-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
