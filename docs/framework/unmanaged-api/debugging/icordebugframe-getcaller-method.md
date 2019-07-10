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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: a637cebb9e1aef20c600353eb14fe900ad7513c7
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67754169"
---
# <a name="icordebugframegetcaller-method"></a><span data-ttu-id="37f83-102">ICorDebugFrame::GetCaller-Methode</span><span class="sxs-lookup"><span data-stu-id="37f83-102">ICorDebugFrame::GetCaller Method</span></span>
<span data-ttu-id="37f83-103">Ruft einen Zeiger auf das ICorDebugFrame-Objekt, in der aktuellen Kette, die diesem Frame aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="37f83-103">Gets a pointer to the ICorDebugFrame object in the current chain that called this frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="37f83-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="37f83-104">Syntax</span></span>  
  
```cpp  
HRESULT GetCaller (  
    [out] ICorDebugFrame     **ppFrame  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="37f83-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="37f83-105">Parameters</span></span>  
 `ppFrame`  
 <span data-ttu-id="37f83-106">[out] Ein Zeiger auf die Adresse einer `ICorDebugFrame` -Objekt, das den Aufrufframe darstellt.</span><span class="sxs-lookup"><span data-stu-id="37f83-106">[out] A pointer to the address of an `ICorDebugFrame` object that represents the calling frame.</span></span> <span data-ttu-id="37f83-107">Dieser Wert ist null, wenn der aufgerufene Frame in der aktuellen Kette der äußerste Frame ist.</span><span class="sxs-lookup"><span data-stu-id="37f83-107">This value is null if the called frame is the outermost frame in the current chain.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="37f83-108">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="37f83-108">Requirements</span></span>  
 <span data-ttu-id="37f83-109">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="37f83-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="37f83-110">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="37f83-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="37f83-111">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="37f83-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="37f83-112">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="37f83-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
