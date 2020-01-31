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
ms.openlocfilehash: 63f7bf8c09480b9ce2cfb8eb8dc66e4a6133ef8f
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/28/2020
ms.locfileid: "76777487"
---
# <a name="icordebugmanagedcallbackcontrolctrap-method"></a><span data-ttu-id="67149-102">ICorDebugManagedCallback::ControlCTrap-Methode</span><span class="sxs-lookup"><span data-stu-id="67149-102">ICorDebugManagedCallback::ControlCTrap Method</span></span>
<span data-ttu-id="67149-103">Benachrichtigt den Debugger, dass ein STRG + C in dem Prozess, der debuggt wird, eingeklemmt ist.</span><span class="sxs-lookup"><span data-stu-id="67149-103">Notifies the debugger that a CTRL+C is trapped in the process that is being debugged.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="67149-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="67149-104">Syntax</span></span>  
  
```cpp  
HRESULT ControlCTrap (  
    [in] ICorDebugProcess *pProcess  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="67149-105">Parameters</span><span class="sxs-lookup"><span data-stu-id="67149-105">Parameters</span></span>  
 `pProcess`  
 <span data-ttu-id="67149-106">in Ein Zeiger auf ein ICorDebugProcess-Objekt, das den Prozess darstellt, in dem STRG + C eingefangen wird.</span><span class="sxs-lookup"><span data-stu-id="67149-106">[in] A pointer to an ICorDebugProcess object that represents the process in which the CTRL+C is trapped.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="67149-107">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="67149-107">Return Value</span></span>  
  
|<span data-ttu-id="67149-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="67149-108">HRESULT</span></span>|<span data-ttu-id="67149-109">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="67149-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="67149-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="67149-110">S_OK</span></span>|<span data-ttu-id="67149-111">Der Debugger verarbeitet den STRG + C-Trap.</span><span class="sxs-lookup"><span data-stu-id="67149-111">The debugger will handle the CTRL+C trap.</span></span>|  
|<span data-ttu-id="67149-112">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="67149-112">S_FALSE</span></span>|<span data-ttu-id="67149-113">Der Debugger verarbeitet den STRG + C-Trap nicht.</span><span class="sxs-lookup"><span data-stu-id="67149-113">The debugger will not handle the CTRL+C trap.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="67149-114">Hinweise</span><span class="sxs-lookup"><span data-stu-id="67149-114">Remarks</span></span>  
 <span data-ttu-id="67149-115">Alle Anwendungs Domänen innerhalb des Prozesses werden für diesen Rückruf beendet.</span><span class="sxs-lookup"><span data-stu-id="67149-115">All application domains within the process are stopped for this callback.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="67149-116">-Anforderungen</span><span class="sxs-lookup"><span data-stu-id="67149-116">Requirements</span></span>  
 <span data-ttu-id="67149-117">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="67149-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="67149-118">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="67149-118">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="67149-119">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="67149-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="67149-120">**.NET Framework Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="67149-120">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="67149-121">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="67149-121">See also</span></span>

- [<span data-ttu-id="67149-122">ICorDebugManagedCallback-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="67149-122">ICorDebugManagedCallback Interface</span></span>](icordebugmanagedcallback-interface.md)
