---
title: ICorDebugThread::GetActiveFrame-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugThread.GetActiveFrame
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugThread::GetActiveFrame
helpviewer_keywords:
- ICorDebugThread::GetActiveFrame method [.NET Framework debugging]
- GetActiveFrame method, ICorDebugThread interface [.NET Framework debugging]
ms.assetid: 8d6d3a1a-fef6-4f2f-a22c-3bdd30d70e07
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 390a2c64508bf407296d318a47bfd2972b7ef9d9
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67762561"
---
# <a name="icordebugthreadgetactiveframe-method"></a><span data-ttu-id="e897f-102">ICorDebugThread::GetActiveFrame-Methode</span><span class="sxs-lookup"><span data-stu-id="e897f-102">ICorDebugThread::GetActiveFrame Method</span></span>
<span data-ttu-id="e897f-103">Ruft einen Schnittstellenzeiger auf den aktiven Frame für (am jüngstes) für dieses ICorDebugThread-Objekt ab.</span><span class="sxs-lookup"><span data-stu-id="e897f-103">Gets an interface pointer to the active (most recent) frame on this ICorDebugThread object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e897f-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="e897f-104">Syntax</span></span>  
  
```cpp  
HRESULT GetActiveFrame (  
    [out] ICorDebugFrame   **ppFrame  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e897f-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="e897f-105">Parameters</span></span>  
 `ppFrame`  
 <span data-ttu-id="e897f-106">[out] Ein Zeiger auf die Adresse des ICorDebugFrame-Schnittstellenobjekts, das einen Frame darstellt.</span><span class="sxs-lookup"><span data-stu-id="e897f-106">[out] A pointer to the address of an ICorDebugFrame interface object that represents a frame.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e897f-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="e897f-107">Remarks</span></span>  
 <span data-ttu-id="e897f-108">Die `ppFrame` -Parameter ist null, wenn kein Frame gerade aktiv ist.</span><span class="sxs-lookup"><span data-stu-id="e897f-108">The `ppFrame` parameter is null if no frame is currently active.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e897f-109">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="e897f-109">Requirements</span></span>  
 <span data-ttu-id="e897f-110">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e897f-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e897f-111">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="e897f-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="e897f-112">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e897f-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e897f-113">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e897f-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
