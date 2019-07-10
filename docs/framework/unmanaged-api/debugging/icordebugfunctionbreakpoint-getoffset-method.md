---
title: ICorDebugFunctionBreakpoint::GetOffset-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugFunctionBreakpoint.GetOffset
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugFunctionBreakpoint::GetOffset
helpviewer_keywords:
- ICorDebugFunctionBreakpoint::GetOffset method [.NET Framework debugging]
- GetOffset method, ICorDebugFunctionBreakpoint interface [.NET Framework debugging]
ms.assetid: e619eae4-3ac3-4c37-bba4-55e59989b9cb
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 67e71002a78023ad6e8ef89c7a57d484a65aaeb3
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67756382"
---
# <a name="icordebugfunctionbreakpointgetoffset-method"></a><span data-ttu-id="58f16-102">ICorDebugFunctionBreakpoint::GetOffset-Methode</span><span class="sxs-lookup"><span data-stu-id="58f16-102">ICorDebugFunctionBreakpoint::GetOffset Method</span></span>
<span data-ttu-id="58f16-103">Ruft den Offset des Haltepunkts in der Funktion.</span><span class="sxs-lookup"><span data-stu-id="58f16-103">Gets the offset of the breakpoint within the function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="58f16-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="58f16-104">Syntax</span></span>  
  
```cpp  
HRESULT GetOffset (  
    [out] ULONG32  *pnOffset  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="58f16-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="58f16-105">Parameters</span></span>  
 `pnOffset`  
 <span data-ttu-id="58f16-106">[out] Ein Zeiger auf den Offset des Haltepunkts.</span><span class="sxs-lookup"><span data-stu-id="58f16-106">[out] A pointer to the offset of the breakpoint.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="58f16-107">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="58f16-107">Requirements</span></span>  
 <span data-ttu-id="58f16-108">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="58f16-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="58f16-109">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="58f16-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="58f16-110">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="58f16-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="58f16-111">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="58f16-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
