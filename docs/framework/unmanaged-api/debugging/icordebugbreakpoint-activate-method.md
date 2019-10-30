---
title: ICorDebugBreakpoint::Activate-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugBreakpoint.Activate
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugBreakpoint::Activate
helpviewer_keywords:
- ICorDebugBreakpoint::Activate method [.NET Framework debugging]
- Activate method [.NET Framework debugging]
ms.assetid: e30c29f7-3f19-4081-b572-a731aa14cd44
topic_type:
- apiref
ms.openlocfilehash: 50794e96484432c8b7c203f6b8caa60130068a8c
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73122786"
---
# <a name="icordebugbreakpointactivate-method"></a><span data-ttu-id="8b032-102">ICorDebugBreakpoint::Activate-Methode</span><span class="sxs-lookup"><span data-stu-id="8b032-102">ICorDebugBreakpoint::Activate Method</span></span>
<span data-ttu-id="8b032-103">Legt den aktiven Zustand dieses `ICorDebugBreakpoint`fest.</span><span class="sxs-lookup"><span data-stu-id="8b032-103">Sets the active state of this `ICorDebugBreakpoint`.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8b032-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="8b032-104">Syntax</span></span>  
  
```cpp  
HRESULT Activate (  
    [in] BOOL bActive  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8b032-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="8b032-105">Parameters</span></span>  
 `bActive`  
 <span data-ttu-id="8b032-106">in Legen Sie diesen Wert auf `true` fest, um den Status als aktiv anzugeben. andernfalls legen Sie diesen Wert auf `false`fest.</span><span class="sxs-lookup"><span data-stu-id="8b032-106">[in] Set this value to `true` to specify the state as active; otherwise, set this value to `false`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8b032-107">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="8b032-107">Requirements</span></span>  
 <span data-ttu-id="8b032-108">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8b032-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8b032-109">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="8b032-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="8b032-110">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="8b032-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="8b032-111">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8b032-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
