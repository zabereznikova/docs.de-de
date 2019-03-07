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
ms.openlocfilehash: 82902e6a395fe62464065ccea4cca5b52c960f0d
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/06/2019
ms.locfileid: "57492217"
---
# <a name="icordebugframegetcaller-method"></a><span data-ttu-id="205d8-102">ICorDebugFrame::GetCaller-Methode</span><span class="sxs-lookup"><span data-stu-id="205d8-102">ICorDebugFrame::GetCaller Method</span></span>
<span data-ttu-id="205d8-103">Ruft einen Zeiger auf das ICorDebugFrame-Objekt, in der aktuellen Kette, die diesem Frame aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="205d8-103">Gets a pointer to the ICorDebugFrame object in the current chain that called this frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="205d8-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="205d8-104">Syntax</span></span>  
  
```  
HRESULT GetCaller (  
    [out] ICorDebugFrame     **ppFrame  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="205d8-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="205d8-105">Parameters</span></span>  
 `ppFrame`  
 <span data-ttu-id="205d8-106">[out] Ein Zeiger auf die Adresse einer `ICorDebugFrame` -Objekt, das den Aufrufframe darstellt.</span><span class="sxs-lookup"><span data-stu-id="205d8-106">[out] A pointer to the address of an `ICorDebugFrame` object that represents the calling frame.</span></span> <span data-ttu-id="205d8-107">Dieser Wert ist null, wenn der aufgerufene Frame in der aktuellen Kette der äußerste Frame ist.</span><span class="sxs-lookup"><span data-stu-id="205d8-107">This value is null if the called frame is the outermost frame in the current chain.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="205d8-108">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="205d8-108">Requirements</span></span>  
 <span data-ttu-id="205d8-109">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="205d8-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="205d8-110">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="205d8-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="205d8-111">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="205d8-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="205d8-112">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="205d8-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
