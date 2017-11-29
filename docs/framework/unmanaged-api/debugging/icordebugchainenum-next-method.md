---
title: ICorDebugChainEnum::Next-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugChainEnum.Next
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugChainEnum::Next
helpviewer_keywords:
- ICorDebugChainEnum::Next method [.NET Framework debugging]
- Next method, ICorDebugChainEnum interface [.NET Framework debugging]
ms.assetid: 6b791351-bcc5-4ddd-9cab-eff2f7dd5142
topic_type: apiref
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 3d6d587b1a249d08ffb250453fb9c007dc3df3e2
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugchainenumnext-method"></a><span data-ttu-id="8a41f-102">ICorDebugChainEnum::Next-Methode</span><span class="sxs-lookup"><span data-stu-id="8a41f-102">ICorDebugChainEnum::Next Method</span></span>
<span data-ttu-id="8a41f-103">Ruft die angegebene Anzahl von Instanzen ICorDebugChain aus der Enumeration, beginnend mit der aktuellen Position ab.</span><span class="sxs-lookup"><span data-stu-id="8a41f-103">Gets the specified number of ICorDebugChain instances from the enumeration, starting at the current position.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8a41f-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="8a41f-104">Syntax</span></span>  
  
```  
HRESULT Next (  
    [in] ULONG  celt,  
    [out, size_is(celt), length_is(*pceltFetched)]  
        ICorDebugChain *chains[],  
    [out] ULONG *pceltFetched  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="8a41f-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="8a41f-105">Parameters</span></span>  
 `celt`  
 <span data-ttu-id="8a41f-106">[in] Die Anzahl der `ICorDebugChain` Instanzen abgerufen werden sollen.</span><span class="sxs-lookup"><span data-stu-id="8a41f-106">[in] The number of `ICorDebugChain` instances to be retrieved.</span></span>  
  
 `chains`  
 <span data-ttu-id="8a41f-107">[out] Ein Array von Zeigern, die jeweils auf ein `ICorDebugChain` Objekt, das eine Kette darstellt.</span><span class="sxs-lookup"><span data-stu-id="8a41f-107">[out] An array of pointers, each of which points to an `ICorDebugChain` object that represents a chain.</span></span>  
  
 `pceltFetched`  
 <span data-ttu-id="8a41f-108">[out] Ein Zeiger auf die Anzahl der `ICorDebugChain` Instanzen, die tatsächlich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="8a41f-108">[out] A pointer to the number of `ICorDebugChain` instances actually returned.</span></span> <span data-ttu-id="8a41f-109">Dieser Wert kann null sein, wenn `celt` ist ein.</span><span class="sxs-lookup"><span data-stu-id="8a41f-109">This value may be null if `celt` is one.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8a41f-110">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="8a41f-110">Requirements</span></span>  
 <span data-ttu-id="8a41f-111">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8a41f-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8a41f-112">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="8a41f-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="8a41f-113">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="8a41f-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="8a41f-114">**.NET Framework-Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8a41f-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
