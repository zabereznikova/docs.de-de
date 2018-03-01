---
title: ICorDebugThread::GetProcess-Methode
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
- ICorDebugThread.GetProcess
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugThread::GetProcess
helpviewer_keywords:
- ICorDebugThread::GetProcess method [.NET Framework debugging]
- GetProcess method, ICorDebugThread interface [.NET Framework debugging]
ms.assetid: 163816e7-0739-4566-b3df-cd256be8b8a4
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 04410024dfe145b7df96dc0f3d8df6fab230f2c8
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugthreadgetprocess-method"></a><span data-ttu-id="d6231-102">ICorDebugThread::GetProcess-Methode</span><span class="sxs-lookup"><span data-stu-id="d6231-102">ICorDebugThread::GetProcess Method</span></span>
<span data-ttu-id="d6231-103">Ruft einen Schnittstellenzeiger an den Prozess, von dem diese ICorDebugThread zwingend bildet.</span><span class="sxs-lookup"><span data-stu-id="d6231-103">Gets an interface pointer to the process of which this ICorDebugThread forms a part.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d6231-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="d6231-104">Syntax</span></span>  
  
```  
HRESULT GetProcess (  
    [out] ICorDebugProcess   **ppProcess  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="d6231-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="d6231-105">Parameters</span></span>  
 `ppProcess`  
 <span data-ttu-id="d6231-106">[out] Ein Zeiger auf die Adresse eines ICorDebugProcess-Schnittstellenobjekts, das den Prozess darstellt.</span><span class="sxs-lookup"><span data-stu-id="d6231-106">[out] A pointer to the address of an ICorDebugProcess interface object that represents the process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d6231-107">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="d6231-107">Requirements</span></span>  
 <span data-ttu-id="d6231-108">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d6231-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d6231-109">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="d6231-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="d6231-110">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d6231-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d6231-111">**.NET Framework-Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d6231-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
