---
title: ICorDebugFrame::GetCallee-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugFrame.GetCallee
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugFrame::GetCallee
helpviewer_keywords:
- ICorDebugFrame::GetCallee method [.NET Framework debugging]
- GetCallee method, ICorDebugFrame interface [.NET Framework debugging]
ms.assetid: 92d8136d-0436-4c7e-a6b2-80765f892a0d
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: a179b68e2196eeadc712ae8f7d023b2943533335
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61995851"
---
# <a name="icordebugframegetcallee-method"></a><span data-ttu-id="2a37e-102">ICorDebugFrame::GetCallee-Methode</span><span class="sxs-lookup"><span data-stu-id="2a37e-102">ICorDebugFrame::GetCallee Method</span></span>
<span data-ttu-id="2a37e-103">Ruft einen Zeiger auf das ICorDebugFrame-Objekt, in der aktuellen Kette, die diesem Frame aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="2a37e-103">Gets a pointer to the ICorDebugFrame object in the current chain that this frame called.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2a37e-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="2a37e-104">Syntax</span></span>  
  
```  
HRESULT GetCallee (  
    [out] ICorDebugFrame     **ppFrame  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2a37e-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="2a37e-105">Parameters</span></span>  
 `ppFrame`  
 <span data-ttu-id="2a37e-106">[out] Ein Zeiger auf die Adresse einer `ICorDebugFrame` -Objekt, das den aufgerufenen Frame darstellt.</span><span class="sxs-lookup"><span data-stu-id="2a37e-106">[out] A pointer to the address of an `ICorDebugFrame` object that represents the called frame.</span></span> <span data-ttu-id="2a37e-107">Dieser Wert ist null, wenn der aufrufende Frame der innerste Rahmen in der aktuellen Kette ist.</span><span class="sxs-lookup"><span data-stu-id="2a37e-107">This value is null if the calling frame is the innermost frame in the current chain.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2a37e-108">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="2a37e-108">Requirements</span></span>  
 <span data-ttu-id="2a37e-109">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2a37e-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2a37e-110">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="2a37e-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="2a37e-111">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2a37e-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2a37e-112">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2a37e-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
