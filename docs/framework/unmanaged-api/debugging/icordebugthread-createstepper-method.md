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
ms.openlocfilehash: 95a00e8646589e7897636c1698b7c2647cd233fd
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67771804"
---
# <a name="icordebugthreadcreatestepper-method"></a><span data-ttu-id="38f35-102">ICorDebugThread::CreateStepper-Methode</span><span class="sxs-lookup"><span data-stu-id="38f35-102">ICorDebugThread::CreateStepper Method</span></span>
<span data-ttu-id="38f35-103">Erstellt ein ICorDebugStepper-Objekt, die schrittweise Ausführung des aktiven Frames dieses ICorDebugThread ermöglicht.</span><span class="sxs-lookup"><span data-stu-id="38f35-103">Creates an ICorDebugStepper object that allows stepping through the active frame of this ICorDebugThread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="38f35-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="38f35-104">Syntax</span></span>  
  
```cpp  
HRESULT CreateStepper (  
    [out] ICorDebugStepper **ppStepper  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="38f35-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="38f35-105">Parameters</span></span>  
 `ppStepper`  
 <span data-ttu-id="38f35-106">[out] Ein Zeiger auf die Adresse einer `ICorDebugStepper` -Objekt, das schrittweise Ausführung des aktiven Frames dieses Threads ermöglicht.</span><span class="sxs-lookup"><span data-stu-id="38f35-106">[out] A pointer to the address of an `ICorDebugStepper` object that allows stepping through the active frame of this thread.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="38f35-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="38f35-107">Remarks</span></span>  
 <span data-ttu-id="38f35-108">Des aktiven Frames möglicherweise nicht verwaltetem Code.</span><span class="sxs-lookup"><span data-stu-id="38f35-108">The active frame may be unmanaged code.</span></span>  
  
 <span data-ttu-id="38f35-109">Die `ICorDebugStepper` Schnittstelle muss für die schrittweise Ausführung verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="38f35-109">The `ICorDebugStepper` interface must be used to perform the actual stepping.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="38f35-110">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="38f35-110">Requirements</span></span>  
 <span data-ttu-id="38f35-111">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="38f35-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="38f35-112">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="38f35-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="38f35-113">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="38f35-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="38f35-114">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="38f35-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
