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
ms.openlocfilehash: 2452f4be0acde300676bf56011416e0a9ef16464
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33411715"
---
# <a name="icordebugframegetcaller-method"></a><span data-ttu-id="efeea-102">ICorDebugFrame::GetCaller-Methode</span><span class="sxs-lookup"><span data-stu-id="efeea-102">ICorDebugFrame::GetCaller Method</span></span>
<span data-ttu-id="efeea-103">Ruft einen Zeiger auf das ICorDebugFrame-Objekt in der aktuellen Kette, die dieses Rahmens aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="efeea-103">Gets a pointer to the ICorDebugFrame object in the current chain that called this frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="efeea-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="efeea-104">Syntax</span></span>  
  
```  
HRESULT GetCaller (  
    [out] ICorDebugFrame     **ppFrame  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="efeea-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="efeea-105">Parameters</span></span>  
 `ppFrame`  
 <span data-ttu-id="efeea-106">[out] Ein Zeiger auf die Adresse des ein `ICorDebugFrame` Objekt, das den Aufrufframe darstellt.</span><span class="sxs-lookup"><span data-stu-id="efeea-106">[out] A pointer to the address of an `ICorDebugFrame` object that represents the calling frame.</span></span> <span data-ttu-id="efeea-107">Dieser Wert ist null, wenn der aufgerufene Frame der äußerste Rahmen in der aktuellen Kette ist.</span><span class="sxs-lookup"><span data-stu-id="efeea-107">This value is null if the called frame is the outermost frame in the current chain.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="efeea-108">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="efeea-108">Requirements</span></span>  
 <span data-ttu-id="efeea-109">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="efeea-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="efeea-110">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="efeea-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="efeea-111">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="efeea-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="efeea-112">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="efeea-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
