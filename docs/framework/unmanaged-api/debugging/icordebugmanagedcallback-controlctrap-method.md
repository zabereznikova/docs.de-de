---
title: ICorDebugManagedCallback::ControlCTrap-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugManagedCallback.ControlCTrap
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugManagedCallback::ControlCTrap
helpviewer_keywords:
- ICorDebugManagedCallback::ControlCTrap method [.NET Framework debugging]
- ControlCTrap method [.NET Framework debugging]
ms.assetid: 0500854e-2121-43d9-a028-64312da35258
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 7f4794fb0383435f828626497036ad3458df2173
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61995331"
---
# <a name="icordebugmanagedcallbackcontrolctrap-method"></a><span data-ttu-id="a6581-102">ICorDebugManagedCallback::ControlCTrap-Methode</span><span class="sxs-lookup"><span data-stu-id="a6581-102">ICorDebugManagedCallback::ControlCTrap Method</span></span>
<span data-ttu-id="a6581-103">Benachrichtigt den Debugger, dass im Prozess, der debuggt wird, STRG + C drücken aufgefangen wird.</span><span class="sxs-lookup"><span data-stu-id="a6581-103">Notifies the debugger that a CTRL+C is trapped in the process that is being debugged.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a6581-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="a6581-104">Syntax</span></span>  
  
```  
HRESULT ControlCTrap (  
    [in] ICorDebugProcess *pProcess  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a6581-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="a6581-105">Parameters</span></span>  
 `pProcess`  
 <span data-ttu-id="a6581-106">[in] Ein Zeiger auf ein ICorDebugProcess-Objekt, das den Prozess darstellt, in dem die STRG + C aufgefangen wird.</span><span class="sxs-lookup"><span data-stu-id="a6581-106">[in] A pointer to an ICorDebugProcess object that represents the process in which the CTRL+C is trapped.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="a6581-107">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="a6581-107">Return Value</span></span>  
  
|<span data-ttu-id="a6581-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="a6581-108">HRESULT</span></span>|<span data-ttu-id="a6581-109">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="a6581-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="a6581-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="a6581-110">S_OK</span></span>|<span data-ttu-id="a6581-111">Der Debugger behandelt das Trap STRG + C.</span><span class="sxs-lookup"><span data-stu-id="a6581-111">The debugger will handle the CTRL+C trap.</span></span>|  
|<span data-ttu-id="a6581-112">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="a6581-112">S_FALSE</span></span>|<span data-ttu-id="a6581-113">Der Debugger behandelt nicht das Trap STRG + C.</span><span class="sxs-lookup"><span data-stu-id="a6581-113">The debugger will not handle the CTRL+C trap.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a6581-114">Hinweise</span><span class="sxs-lookup"><span data-stu-id="a6581-114">Remarks</span></span>  
 <span data-ttu-id="a6581-115">Alle Anwendungsdomänen innerhalb des Prozesses werden für diesen Rückruf beendet.</span><span class="sxs-lookup"><span data-stu-id="a6581-115">All application domains within the process are stopped for this callback.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a6581-116">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="a6581-116">Requirements</span></span>  
 <span data-ttu-id="a6581-117">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a6581-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a6581-118">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="a6581-118">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="a6581-119">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a6581-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a6581-120">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a6581-120">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a6581-121">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a6581-121">See also</span></span>

- [<span data-ttu-id="a6581-122">ICorDebugManagedCallback-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="a6581-122">ICorDebugManagedCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
