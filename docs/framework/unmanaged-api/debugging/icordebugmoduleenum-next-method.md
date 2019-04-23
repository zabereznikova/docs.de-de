---
title: ICorDebugModuleEnum::Next-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugModuleEnum.Next
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugModuleEnum::Next
helpviewer_keywords:
- ICorDebugModuleEnum::Next method [.NET Framework debugging]
- Next method, ICorDebugModuleEnum interface [.NET Framework debugging]
ms.assetid: 9ff3fcd6-38fe-41f8-bfd3-f0ab6c7d77ca
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: aa341c726ba84dc1d12b6c5628253a100d65a719
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59167101"
---
# <a name="icordebugmoduleenumnext-method"></a><span data-ttu-id="a8bf1-102">ICorDebugModuleEnum::Next-Methode</span><span class="sxs-lookup"><span data-stu-id="a8bf1-102">ICorDebugModuleEnum::Next Method</span></span>
<span data-ttu-id="a8bf1-103">Ruft die Anzahl der "ICorDebugModule"-Instanzen, die anhand des `celt` aus der Enumeration, die an der aktuellen Position ab.</span><span class="sxs-lookup"><span data-stu-id="a8bf1-103">Gets the number of "ICorDebugModule" instances specified by `celt` from the enumeration, starting at the current position.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a8bf1-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="a8bf1-104">Syntax</span></span>  
  
```  
HRESULT Next (  
    [in]  ULONG celt,  
    [out, size_is(celt), length_is(*pceltFetched)]  
        ICorDebugModule *modules[],  
    [out] ULONG *pceltFetched  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a8bf1-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="a8bf1-105">Parameters</span></span>  
 `celt`  
 <span data-ttu-id="a8bf1-106">[in] Die Anzahl der `ICorDebugModule` Instanzen abgerufen werden sollen.</span><span class="sxs-lookup"><span data-stu-id="a8bf1-106">[in] The number of `ICorDebugModule` instances to be retrieved.</span></span>  
  
 `modules`  
 <span data-ttu-id="a8bf1-107">[out] Ein Array von Zeigern, die jeweils auf eine `ICorDebugModule` Objekt.</span><span class="sxs-lookup"><span data-stu-id="a8bf1-107">[out] An array of pointers, each of which points to an `ICorDebugModule` object.</span></span>  
  
 `pceltFetched`  
 <span data-ttu-id="a8bf1-108">[out] Zeiger auf die Anzahl der `ICorDebugModule` Instanzen, die tatsächlich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="a8bf1-108">[out] Pointer to the number of `ICorDebugModule` instances actually returned.</span></span> <span data-ttu-id="a8bf1-109">Dieser Wert kann null sein, wenn `celt` ist.</span><span class="sxs-lookup"><span data-stu-id="a8bf1-109">This value may be null if `celt` is one.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a8bf1-110">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="a8bf1-110">Requirements</span></span>  
 <span data-ttu-id="a8bf1-111">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a8bf1-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a8bf1-112">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="a8bf1-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="a8bf1-113">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a8bf1-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a8bf1-114">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a8bf1-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a8bf1-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a8bf1-115">See also</span></span>
