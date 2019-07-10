---
title: ICorDebugFrameEnum::Next-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugFrameEnum.Next
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugFrameEnum::Next
helpviewer_keywords:
- ICorDebugFrameEnum::Next method [.NET Framework debugging]
- Next method, ICorDebugFrameEnum interface [.NET Framework debugging]
ms.assetid: 0bc96acb-6179-4328-a447-cda562ce9e98
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 9be126e45d8428d8786e9aadf2195133d1957440
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67754831"
---
# <a name="icordebugframeenumnext-method"></a><span data-ttu-id="66e23-102">ICorDebugFrameEnum::Next-Methode</span><span class="sxs-lookup"><span data-stu-id="66e23-102">ICorDebugFrameEnum::Next Method</span></span>
<span data-ttu-id="66e23-103">Ruft die angegebene Anzahl von ICorDebugFrame-Instanzen, beginnend bei der aktuellen Position ab.</span><span class="sxs-lookup"><span data-stu-id="66e23-103">Gets the specified number of ICorDebugFrame instances, starting at the current position.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="66e23-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="66e23-104">Syntax</span></span>  
  
```cpp  
HRESULT Next (  
    [in] ULONG  celt,  
    [out, size_is(celt), length_is(*pceltFetched)]  
        ICorDebugFrame *frames[],  
    [out] ULONG *pceltFetched  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="66e23-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="66e23-105">Parameters</span></span>  
 `celt`  
 <span data-ttu-id="66e23-106">[in] Die Anzahl der `ICorDebugFrame` Instanzen abgerufen werden sollen.</span><span class="sxs-lookup"><span data-stu-id="66e23-106">[in] The number of `ICorDebugFrame` instances to be retrieved.</span></span>  
  
 `frames`  
 <span data-ttu-id="66e23-107">[out] Ein Array von Zeigern, die jeweils auf eine `ICorDebugFrame` Objekt.</span><span class="sxs-lookup"><span data-stu-id="66e23-107">[out] An array of pointers, each of which points to an `ICorDebugFrame` object.</span></span>  
  
 `pceltFetched`  
 <span data-ttu-id="66e23-108">[out] Ein Zeiger auf die Anzahl der `ICorDebugFrame` Instanzen, die tatsächlich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="66e23-108">[out] A pointer to the number of `ICorDebugFrame` instances actually returned.</span></span> <span data-ttu-id="66e23-109">Dieser Wert kann null sein, wenn `celt` ist.</span><span class="sxs-lookup"><span data-stu-id="66e23-109">This value may be null if `celt` is one.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="66e23-110">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="66e23-110">Requirements</span></span>  
 <span data-ttu-id="66e23-111">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="66e23-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="66e23-112">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="66e23-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="66e23-113">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="66e23-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="66e23-114">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="66e23-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
