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
ms.openlocfilehash: 68098895b2ad7f5c08d30f222777e52d4ee3f063
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61995799"
---
# <a name="icordebugframeenumnext-method"></a><span data-ttu-id="441e1-102">ICorDebugFrameEnum::Next-Methode</span><span class="sxs-lookup"><span data-stu-id="441e1-102">ICorDebugFrameEnum::Next Method</span></span>
<span data-ttu-id="441e1-103">Ruft die angegebene Anzahl von ICorDebugFrame-Instanzen, beginnend bei der aktuellen Position ab.</span><span class="sxs-lookup"><span data-stu-id="441e1-103">Gets the specified number of ICorDebugFrame instances, starting at the current position.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="441e1-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="441e1-104">Syntax</span></span>  
  
```  
HRESULT Next (  
    [in] ULONG  celt,  
    [out, size_is(celt), length_is(*pceltFetched)]  
        ICorDebugFrame *frames[],  
    [out] ULONG *pceltFetched  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="441e1-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="441e1-105">Parameters</span></span>  
 `celt`  
 <span data-ttu-id="441e1-106">[in] Die Anzahl der `ICorDebugFrame` Instanzen abgerufen werden sollen.</span><span class="sxs-lookup"><span data-stu-id="441e1-106">[in] The number of `ICorDebugFrame` instances to be retrieved.</span></span>  
  
 `frames`  
 <span data-ttu-id="441e1-107">[out] Ein Array von Zeigern, die jeweils auf eine `ICorDebugFrame` Objekt.</span><span class="sxs-lookup"><span data-stu-id="441e1-107">[out] An array of pointers, each of which points to an `ICorDebugFrame` object.</span></span>  
  
 `pceltFetched`  
 <span data-ttu-id="441e1-108">[out] Ein Zeiger auf die Anzahl der `ICorDebugFrame` Instanzen, die tatsächlich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="441e1-108">[out] A pointer to the number of `ICorDebugFrame` instances actually returned.</span></span> <span data-ttu-id="441e1-109">Dieser Wert kann null sein, wenn `celt` ist.</span><span class="sxs-lookup"><span data-stu-id="441e1-109">This value may be null if `celt` is one.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="441e1-110">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="441e1-110">Requirements</span></span>  
 <span data-ttu-id="441e1-111">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="441e1-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="441e1-112">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="441e1-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="441e1-113">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="441e1-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="441e1-114">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="441e1-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
