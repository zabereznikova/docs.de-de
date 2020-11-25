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
ms.openlocfilehash: 0c38269ea4d730d8f3f9ba5d2c5d8f0edf6d7d45
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95731835"
---
# <a name="icordebugmanagedcallbackcontrolctrap-method"></a><span data-ttu-id="38c74-102">ICorDebugManagedCallback::ControlCTrap-Methode</span><span class="sxs-lookup"><span data-stu-id="38c74-102">ICorDebugManagedCallback::ControlCTrap Method</span></span>

<span data-ttu-id="38c74-103">Benachrichtigt den Debugger, dass ein STRG + C in dem Prozess, der debuggt wird, eingeklemmt ist.</span><span class="sxs-lookup"><span data-stu-id="38c74-103">Notifies the debugger that a CTRL+C is trapped in the process that is being debugged.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="38c74-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="38c74-104">Syntax</span></span>  
  
```cpp  
HRESULT ControlCTrap (  
    [in] ICorDebugProcess *pProcess  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="38c74-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="38c74-105">Parameters</span></span>  

 `pProcess`  
 <span data-ttu-id="38c74-106">in Ein Zeiger auf ein ICorDebugProcess-Objekt, das den Prozess darstellt, in dem STRG + C eingefangen wird.</span><span class="sxs-lookup"><span data-stu-id="38c74-106">[in] A pointer to an ICorDebugProcess object that represents the process in which the CTRL+C is trapped.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="38c74-107">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="38c74-107">Return Value</span></span>  
  
|<span data-ttu-id="38c74-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="38c74-108">HRESULT</span></span>|<span data-ttu-id="38c74-109">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="38c74-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="38c74-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="38c74-110">S_OK</span></span>|<span data-ttu-id="38c74-111">Der Debugger verarbeitet den STRG + C-Trap.</span><span class="sxs-lookup"><span data-stu-id="38c74-111">The debugger will handle the CTRL+C trap.</span></span>|  
|<span data-ttu-id="38c74-112">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="38c74-112">S_FALSE</span></span>|<span data-ttu-id="38c74-113">Der Debugger verarbeitet den STRG + C-Trap nicht.</span><span class="sxs-lookup"><span data-stu-id="38c74-113">The debugger will not handle the CTRL+C trap.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="38c74-114">Hinweise</span><span class="sxs-lookup"><span data-stu-id="38c74-114">Remarks</span></span>  

 <span data-ttu-id="38c74-115">Alle Anwendungs Domänen innerhalb des Prozesses werden für diesen Rückruf beendet.</span><span class="sxs-lookup"><span data-stu-id="38c74-115">All application domains within the process are stopped for this callback.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="38c74-116">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="38c74-116">Requirements</span></span>  

 <span data-ttu-id="38c74-117">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="38c74-117">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="38c74-118">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="38c74-118">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="38c74-119">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="38c74-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="38c74-120">**.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="38c74-120">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="38c74-121">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="38c74-121">See also</span></span>

- [<span data-ttu-id="38c74-122">ICorDebugManagedCallback-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="38c74-122">ICorDebugManagedCallback Interface</span></span>](icordebugmanagedcallback-interface.md)
