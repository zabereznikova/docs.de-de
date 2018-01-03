---
title: ICorDebugThread::CreateStepper-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugThread.CreateStepper
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugThread::CreateStepper
helpviewer_keywords:
- ICorDebugThread::CreateStepper method [.NET Framework debugging]
- CreateStepper method, ICorDebugThread interface [.NET Framework debugging]
ms.assetid: 4657443f-dd12-431b-a648-175c23f13c83
topic_type: apiref
caps.latest.revision: "13"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 869b1862e479c42c1ea43c90a276e95adcd5c321
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugthreadcreatestepper-method"></a><span data-ttu-id="99d82-102">ICorDebugThread::CreateStepper-Methode</span><span class="sxs-lookup"><span data-stu-id="99d82-102">ICorDebugThread::CreateStepper Method</span></span>
<span data-ttu-id="99d82-103">Erstellt ein ICorDebugStepper-Objekt, das schrittweise Ausführen des aktiven Frames dieses ICorDebugThread ermöglicht.</span><span class="sxs-lookup"><span data-stu-id="99d82-103">Creates an ICorDebugStepper object that allows stepping through the active frame of this ICorDebugThread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="99d82-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="99d82-104">Syntax</span></span>  
  
```  
HRESULT CreateStepper (  
    [out] ICorDebugStepper **ppStepper  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="99d82-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="99d82-105">Parameters</span></span>  
 `ppStepper`  
 <span data-ttu-id="99d82-106">[out] Ein Zeiger auf die Adresse des ein `ICorDebugStepper` Objekt, das schrittweise Ausführen des aktiven Frames dieses Threads ermöglicht.</span><span class="sxs-lookup"><span data-stu-id="99d82-106">[out] A pointer to the address of an `ICorDebugStepper` object that allows stepping through the active frame of this thread.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="99d82-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="99d82-107">Remarks</span></span>  
 <span data-ttu-id="99d82-108">Der aktive Frame möglicherweise nicht verwaltetem Code.</span><span class="sxs-lookup"><span data-stu-id="99d82-108">The active frame may be unmanaged code.</span></span>  
  
 <span data-ttu-id="99d82-109">Die `ICorDebugStepper` Schnittstelle muss für die schrittweise Ausführung verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="99d82-109">The `ICorDebugStepper` interface must be used to perform the actual stepping.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="99d82-110">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="99d82-110">Requirements</span></span>  
 <span data-ttu-id="99d82-111">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="99d82-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="99d82-112">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="99d82-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="99d82-113">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="99d82-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="99d82-114">**.NET Framework-Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="99d82-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
