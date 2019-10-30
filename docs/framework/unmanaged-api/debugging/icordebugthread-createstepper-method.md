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
ms.openlocfilehash: d1b058aef66ed32c2cadcc3cfd72320dd8eb7729
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73133596"
---
# <a name="icordebugthreadcreatestepper-method"></a><span data-ttu-id="2fd6a-102">ICorDebugThread::CreateStepper-Methode</span><span class="sxs-lookup"><span data-stu-id="2fd6a-102">ICorDebugThread::CreateStepper Method</span></span>
<span data-ttu-id="2fd6a-103">Erstellt ein ICorDebugStepper-Objekt, mit dem der aktive Frame dieses ICorDebugThread schrittweise durchlaufen werden kann.</span><span class="sxs-lookup"><span data-stu-id="2fd6a-103">Creates an ICorDebugStepper object that allows stepping through the active frame of this ICorDebugThread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2fd6a-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="2fd6a-104">Syntax</span></span>  
  
```cpp  
HRESULT CreateStepper (  
    [out] ICorDebugStepper **ppStepper  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2fd6a-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="2fd6a-105">Parameters</span></span>  
 `ppStepper`  
 <span data-ttu-id="2fd6a-106">vorgenommen Ein Zeiger auf die Adresse eines `ICorDebugStepper` Objekts, das das schrittweise durchlaufen des aktiven Frames dieses Threads ermöglicht.</span><span class="sxs-lookup"><span data-stu-id="2fd6a-106">[out] A pointer to the address of an `ICorDebugStepper` object that allows stepping through the active frame of this thread.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2fd6a-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="2fd6a-107">Remarks</span></span>  
 <span data-ttu-id="2fd6a-108">Der aktive Frame kann nicht verwalteter Code sein.</span><span class="sxs-lookup"><span data-stu-id="2fd6a-108">The active frame may be unmanaged code.</span></span>  
  
 <span data-ttu-id="2fd6a-109">Die `ICorDebugStepper`-Schnittstelle muss verwendet werden, um die tatsächliche Schritt Ausführung auszuführen.</span><span class="sxs-lookup"><span data-stu-id="2fd6a-109">The `ICorDebugStepper` interface must be used to perform the actual stepping.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2fd6a-110">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="2fd6a-110">Requirements</span></span>  
 <span data-ttu-id="2fd6a-111">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2fd6a-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2fd6a-112">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="2fd6a-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="2fd6a-113">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2fd6a-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2fd6a-114">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2fd6a-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
