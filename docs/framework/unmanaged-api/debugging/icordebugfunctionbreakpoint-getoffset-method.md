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
ms.openlocfilehash: 0f6fe5d7eb5926d48809bb6490ba75df9d4a5033
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/12/2020
ms.locfileid: "83213152"
---
# <a name="icordebugfunctionbreakpointgetoffset-method"></a><span data-ttu-id="17201-102">ICorDebugFunctionBreakpoint::GetOffset-Methode</span><span class="sxs-lookup"><span data-stu-id="17201-102">ICorDebugFunctionBreakpoint::GetOffset Method</span></span>
<span data-ttu-id="17201-103">Ruft den Offset des Breakpoints innerhalb der Funktion ab.</span><span class="sxs-lookup"><span data-stu-id="17201-103">Gets the offset of the breakpoint within the function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="17201-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="17201-104">Syntax</span></span>  
  
```cpp  
HRESULT GetOffset (  
    [out] ULONG32  *pnOffset  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="17201-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="17201-105">Parameters</span></span>  
 `pnOffset`  
 <span data-ttu-id="17201-106">vorgenommen Ein Zeiger auf den Offset des Breakpoints.</span><span class="sxs-lookup"><span data-stu-id="17201-106">[out] A pointer to the offset of the breakpoint.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="17201-107">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="17201-107">Requirements</span></span>  
 <span data-ttu-id="17201-108">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="17201-108">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="17201-109">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="17201-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="17201-110">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="17201-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="17201-111">**.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="17201-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
