---
title: ICorDebugFrame::GetCaller-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugFrame.GetCaller
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugFrame::GetCaller
helpviewer_keywords:
- GetCaller method, ICorDebugFrame interface [.NET Framework debugging]
- ICorDebugFrame::GetCaller method [.NET Framework debugging]
ms.assetid: bfdc946b-8238-4eb9-8a85-884049fb0fd4
topic_type:
- apiref
ms.openlocfilehash: b52499e509bf172b03b5e4d2b1e4c677dc800281
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95690472"
---
# <a name="icordebugframegetcaller-method"></a><span data-ttu-id="478a2-102">ICorDebugFrame::GetCaller-Methode</span><span class="sxs-lookup"><span data-stu-id="478a2-102">ICorDebugFrame::GetCaller Method</span></span>

<span data-ttu-id="478a2-103">Ruft einen Zeiger auf das ICorDebug Frame-Objekt in der aktuellen Kette ab, das diesen Frame aufgerufen hat.</span><span class="sxs-lookup"><span data-stu-id="478a2-103">Gets a pointer to the ICorDebugFrame object in the current chain that called this frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="478a2-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="478a2-104">Syntax</span></span>  
  
```cpp  
HRESULT GetCaller (  
    [out] ICorDebugFrame     **ppFrame  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="478a2-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="478a2-105">Parameters</span></span>  

 `ppFrame`  
 <span data-ttu-id="478a2-106">vorgenommen Ein Zeiger auf die Adresse eines `ICorDebugFrame` Objekts, das den aufrufenden Frame darstellt.</span><span class="sxs-lookup"><span data-stu-id="478a2-106">[out] A pointer to the address of an `ICorDebugFrame` object that represents the calling frame.</span></span> <span data-ttu-id="478a2-107">Dieser Wert ist NULL, wenn der aufgerufene Frame der äußerste Frame in der aktuellen Kette ist.</span><span class="sxs-lookup"><span data-stu-id="478a2-107">This value is null if the called frame is the outermost frame in the current chain.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="478a2-108">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="478a2-108">Requirements</span></span>  

 <span data-ttu-id="478a2-109">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="478a2-109">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="478a2-110">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="478a2-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="478a2-111">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="478a2-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="478a2-112">**.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="478a2-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
