---
title: ICorDebugThread::GetActiveChain-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- ICorDebugThread.GetActiveChain
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugThread::GetActiveChain
helpviewer_keywords:
- ICorDebugThread::GetActiveChain method [.NET Framework debugging]
- GetActiveChain method [.NET Framework debugging]
ms.assetid: f50de1f7-40ef-4949-b542-1d9a61f7bfef
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 9dda9b793ca56916775ac89ad58effe5653190cb
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugthreadgetactivechain-method"></a><span data-ttu-id="b7f76-102">ICorDebugThread::GetActiveChain-Methode</span><span class="sxs-lookup"><span data-stu-id="b7f76-102">ICorDebugThread::GetActiveChain Method</span></span>
<span data-ttu-id="b7f76-103">Ruft einen Schnittstellenzeiger auf die aktive (aktuellste) Stapelkette für dieses Objekt ICorDebugThread ab.</span><span class="sxs-lookup"><span data-stu-id="b7f76-103">Gets an interface pointer to the active (most recent) stack chain on this ICorDebugThread object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b7f76-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="b7f76-104">Syntax</span></span>  
  
```  
HRESULT GetActiveChain (  
    [out] ICorDebugChain **ppChain  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="b7f76-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="b7f76-105">Parameters</span></span>  
 `ppChain`  
 <span data-ttu-id="b7f76-106">[out] Ein Zeiger auf die Adresse eines ICorDebugChain-Objekts, das die Stapelkette darstellt.</span><span class="sxs-lookup"><span data-stu-id="b7f76-106">[out] A pointer to the address of an ICorDebugChain object that represents the stack chain.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b7f76-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="b7f76-107">Remarks</span></span>  
 <span data-ttu-id="b7f76-108">Die `ppChain` -Parameter ist null, wenn keine Stapelkette gerade aktiv ist.</span><span class="sxs-lookup"><span data-stu-id="b7f76-108">The `ppChain` parameter is null if no stack chain is currently active.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b7f76-109">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="b7f76-109">Requirements</span></span>  
 <span data-ttu-id="b7f76-110">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b7f76-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b7f76-111">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="b7f76-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="b7f76-112">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b7f76-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b7f76-113">**.NET Framework-Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b7f76-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
