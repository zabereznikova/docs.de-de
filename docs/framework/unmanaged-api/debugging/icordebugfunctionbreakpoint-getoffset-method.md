---
title: ICorDebugFunctionBreakpoint::GetOffset-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugFunctionBreakpoint.GetOffset
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugFunctionBreakpoint::GetOffset
helpviewer_keywords:
- ICorDebugFunctionBreakpoint::GetOffset method [.NET Framework debugging]
- GetOffset method, ICorDebugFunctionBreakpoint interface [.NET Framework debugging]
ms.assetid: e619eae4-3ac3-4c37-bba4-55e59989b9cb
topic_type: apiref
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: ca890b20451b0fab6145d8b8577f705bf3fa3202
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugfunctionbreakpointgetoffset-method"></a><span data-ttu-id="fe9ec-102">ICorDebugFunctionBreakpoint::GetOffset-Methode</span><span class="sxs-lookup"><span data-stu-id="fe9ec-102">ICorDebugFunctionBreakpoint::GetOffset Method</span></span>
<span data-ttu-id="fe9ec-103">Ruft den Offset des Haltepunkts innerhalb der Funktion ab.</span><span class="sxs-lookup"><span data-stu-id="fe9ec-103">Gets the offset of the breakpoint within the function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fe9ec-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="fe9ec-104">Syntax</span></span>  
  
```  
HRESULT GetOffset (  
    [out] ULONG32  *pnOffset  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="fe9ec-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="fe9ec-105">Parameters</span></span>  
 `pnOffset`  
 <span data-ttu-id="fe9ec-106">[out] Ein Zeiger auf den Offset des Haltepunkts.</span><span class="sxs-lookup"><span data-stu-id="fe9ec-106">[out] A pointer to the offset of the breakpoint.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fe9ec-107">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="fe9ec-107">Requirements</span></span>  
 <span data-ttu-id="fe9ec-108">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="fe9ec-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fe9ec-109">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="fe9ec-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="fe9ec-110">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="fe9ec-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="fe9ec-111">**.NET Framework-Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fe9ec-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
