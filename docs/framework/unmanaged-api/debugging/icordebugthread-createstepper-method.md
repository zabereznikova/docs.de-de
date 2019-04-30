---
title: ICorDebugThread::CreateStepper-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugThread.CreateStepper
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugThread::CreateStepper
helpviewer_keywords:
- ICorDebugThread::CreateStepper method [.NET Framework debugging]
- CreateStepper method, ICorDebugThread interface [.NET Framework debugging]
ms.assetid: 4657443f-dd12-431b-a648-175c23f13c83
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 89182739633984011aaab3d7900d376b6db5ef99
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61987186"
---
# <a name="icordebugthreadcreatestepper-method"></a><span data-ttu-id="60d96-102">ICorDebugThread::CreateStepper-Methode</span><span class="sxs-lookup"><span data-stu-id="60d96-102">ICorDebugThread::CreateStepper Method</span></span>
<span data-ttu-id="60d96-103">Erstellt ein ICorDebugStepper-Objekt, die schrittweise Ausführung des aktiven Frames dieses ICorDebugThread ermöglicht.</span><span class="sxs-lookup"><span data-stu-id="60d96-103">Creates an ICorDebugStepper object that allows stepping through the active frame of this ICorDebugThread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="60d96-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="60d96-104">Syntax</span></span>  
  
```  
HRESULT CreateStepper (  
    [out] ICorDebugStepper **ppStepper  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="60d96-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="60d96-105">Parameters</span></span>  
 `ppStepper`  
 <span data-ttu-id="60d96-106">[out] Ein Zeiger auf die Adresse einer `ICorDebugStepper` -Objekt, das schrittweise Ausführung des aktiven Frames dieses Threads ermöglicht.</span><span class="sxs-lookup"><span data-stu-id="60d96-106">[out] A pointer to the address of an `ICorDebugStepper` object that allows stepping through the active frame of this thread.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="60d96-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="60d96-107">Remarks</span></span>  
 <span data-ttu-id="60d96-108">Des aktiven Frames möglicherweise nicht verwaltetem Code.</span><span class="sxs-lookup"><span data-stu-id="60d96-108">The active frame may be unmanaged code.</span></span>  
  
 <span data-ttu-id="60d96-109">Die `ICorDebugStepper` Schnittstelle muss für die schrittweise Ausführung verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="60d96-109">The `ICorDebugStepper` interface must be used to perform the actual stepping.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="60d96-110">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="60d96-110">Requirements</span></span>  
 <span data-ttu-id="60d96-111">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="60d96-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="60d96-112">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="60d96-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="60d96-113">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="60d96-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="60d96-114">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="60d96-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
