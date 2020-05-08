---
title: ICorDebugAppDomain::Attach-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugAppDomain.Attach
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugAppDomain::Attach
helpviewer_keywords:
- ICorDebugAppDomain::Attach method [.NET Framework debugging]
- Attach method [.NET Framework debugging]
ms.assetid: 0358b84a-4236-4c34-945b-4babff7df570
topic_type:
- apiref
ms.openlocfilehash: 92cc6c3ce15d8391a43ff130a82476a4363ff5bd
ms.sourcegitcommit: 957c49696eaf048c284ef8f9f8ffeb562357ad95
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/07/2020
ms.locfileid: "82895300"
---
# <a name="icordebugappdomainattach-method"></a><span data-ttu-id="be860-102">ICorDebugAppDomain::Attach-Methode</span><span class="sxs-lookup"><span data-stu-id="be860-102">ICorDebugAppDomain::Attach Method</span></span>
<span data-ttu-id="be860-103">Fügt den Debugger an die Anwendungsdomäne an.</span><span class="sxs-lookup"><span data-stu-id="be860-103">Attaches the debugger to the application domain.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="be860-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="be860-104">Syntax</span></span>  
  
```cpp  
HRESULT Attach ();  
```  
  
## <a name="remarks"></a><span data-ttu-id="be860-105">Hinweise</span><span class="sxs-lookup"><span data-stu-id="be860-105">Remarks</span></span>  
 <span data-ttu-id="be860-106">Der Debugger muss an die Anwendungsdomäne angefügt werden, um Ereignisse zu empfangen und das Debuggen der Anwendungsdomäne zu ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="be860-106">The debugger must be attached to the application domain to receive events and to enable debugging of the application domain.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="be860-107">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="be860-107">Requirements</span></span>  
 <span data-ttu-id="be860-108">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="be860-108">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="be860-109">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="be860-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="be860-110">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="be860-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="be860-111">**.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="be860-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
