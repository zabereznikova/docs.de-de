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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 9d30b6cb083cc2f92bcbe089bf8e990fedd8e8f7
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67738094"
---
# <a name="icordebugappdomainattach-method"></a><span data-ttu-id="153b0-102">ICorDebugAppDomain::Attach-Methode</span><span class="sxs-lookup"><span data-stu-id="153b0-102">ICorDebugAppDomain::Attach Method</span></span>
<span data-ttu-id="153b0-103">Fügt den Debugger an die Anwendungsdomäne an.</span><span class="sxs-lookup"><span data-stu-id="153b0-103">Attaches the debugger to the application domain.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="153b0-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="153b0-104">Syntax</span></span>  
  
```cpp  
HRESULT Attach ();  
```  
  
## <a name="remarks"></a><span data-ttu-id="153b0-105">Hinweise</span><span class="sxs-lookup"><span data-stu-id="153b0-105">Remarks</span></span>  
 <span data-ttu-id="153b0-106">Der Debugger muss an die Anwendungsdomäne zum Empfangen von Ereignissen und zum Aktivieren des Debuggens der Anwendungsdomäne angefügt werden.</span><span class="sxs-lookup"><span data-stu-id="153b0-106">The debugger must be attached to the application domain to receive events and to enable debugging of the application domain.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="153b0-107">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="153b0-107">Requirements</span></span>  
 <span data-ttu-id="153b0-108">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="153b0-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="153b0-109">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="153b0-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="153b0-110">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="153b0-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="153b0-111">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="153b0-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
