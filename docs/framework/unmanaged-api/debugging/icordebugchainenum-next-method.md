---
title: ICorDebugChainEnum::Next-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugChainEnum.Next
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugChainEnum::Next
helpviewer_keywords:
- ICorDebugChainEnum::Next method [.NET Framework debugging]
- Next method, ICorDebugChainEnum interface [.NET Framework debugging]
ms.assetid: 6b791351-bcc5-4ddd-9cab-eff2f7dd5142
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 26df40297d080d1ccc9464f7b09e7731f135e270
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/06/2019
ms.locfileid: "57489825"
---
# <a name="icordebugchainenumnext-method"></a><span data-ttu-id="221b9-102">ICorDebugChainEnum::Next-Methode</span><span class="sxs-lookup"><span data-stu-id="221b9-102">ICorDebugChainEnum::Next Method</span></span>
<span data-ttu-id="221b9-103">Ruft die angegebene Anzahl von ICorDebugChain-Instanzen aus der Enumeration ab, an der aktuellen Position ab.</span><span class="sxs-lookup"><span data-stu-id="221b9-103">Gets the specified number of ICorDebugChain instances from the enumeration, starting at the current position.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="221b9-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="221b9-104">Syntax</span></span>  
  
```  
HRESULT Next (  
    [in] ULONG  celt,  
    [out, size_is(celt), length_is(*pceltFetched)]  
        ICorDebugChain *chains[],  
    [out] ULONG *pceltFetched  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="221b9-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="221b9-105">Parameters</span></span>  
 `celt`  
 <span data-ttu-id="221b9-106">[in] Die Anzahl der `ICorDebugChain` Instanzen abgerufen werden sollen.</span><span class="sxs-lookup"><span data-stu-id="221b9-106">[in] The number of `ICorDebugChain` instances to be retrieved.</span></span>  
  
 `chains`  
 <span data-ttu-id="221b9-107">[out] Ein Array von Zeigern, die jeweils auf eine `ICorDebugChain` Objekt, das eine Kette darstellt.</span><span class="sxs-lookup"><span data-stu-id="221b9-107">[out] An array of pointers, each of which points to an `ICorDebugChain` object that represents a chain.</span></span>  
  
 `pceltFetched`  
 <span data-ttu-id="221b9-108">[out] Ein Zeiger auf die Anzahl der `ICorDebugChain` Instanzen, die tatsächlich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="221b9-108">[out] A pointer to the number of `ICorDebugChain` instances actually returned.</span></span> <span data-ttu-id="221b9-109">Dieser Wert kann null sein, wenn `celt` ist.</span><span class="sxs-lookup"><span data-stu-id="221b9-109">This value may be null if `celt` is one.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="221b9-110">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="221b9-110">Requirements</span></span>  
 <span data-ttu-id="221b9-111">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="221b9-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="221b9-112">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="221b9-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="221b9-113">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="221b9-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="221b9-114">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="221b9-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
