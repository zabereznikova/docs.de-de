---
title: ICorDebugManagedCallback::LoadClass-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugManagedCallback.LoadClass
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugManagedCallback::LoadClass
helpviewer_keywords:
- ICorDebugManagedCallback::LoadClass method [.NET Framework debugging]
- LoadClass method [.NET Framework debugging]
ms.assetid: e58dac7b-85c3-41ca-b9aa-3a7fc9ae6680
topic_type:
- apiref
ms.openlocfilehash: 5d35ab4610ffa04d15dd2404fdf8010308bcb42a
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/12/2020
ms.locfileid: "83212731"
---
# <a name="icordebugmanagedcallbackloadclass-method"></a><span data-ttu-id="2ceca-102">ICorDebugManagedCallback::LoadClass-Methode</span><span class="sxs-lookup"><span data-stu-id="2ceca-102">ICorDebugManagedCallback::LoadClass Method</span></span>
<span data-ttu-id="2ceca-103">Benachrichtigt den Debugger, dass eine Klasse geladen wurde.</span><span class="sxs-lookup"><span data-stu-id="2ceca-103">Notifies the debugger that a class has been loaded.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2ceca-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="2ceca-104">Syntax</span></span>  
  
```cpp  
HRESULT LoadClass (  
    [in] ICorDebugAppDomain *pAppDomain,  
    [in] ICorDebugClass     *c  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2ceca-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="2ceca-105">Parameters</span></span>  
 `pAppDomain`  
 <span data-ttu-id="2ceca-106">in Ein Zeiger auf ein ICorDebugAppDomain-Objekt, das die Anwendungsdomäne darstellt, in die die-Klasse geladen wurde.</span><span class="sxs-lookup"><span data-stu-id="2ceca-106">[in] A pointer to an ICorDebugAppDomain object that represents the application domain into which the class has been loaded.</span></span>  
  
 `c`  
 <span data-ttu-id="2ceca-107">in Ein Zeiger auf ein ICorDebugClass-Objekt, das die-Klasse darstellt.</span><span class="sxs-lookup"><span data-stu-id="2ceca-107">[in] A pointer to an ICorDebugClass object that represents the class.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2ceca-108">Hinweise</span><span class="sxs-lookup"><span data-stu-id="2ceca-108">Remarks</span></span>  
 <span data-ttu-id="2ceca-109">Dieser Rückruf tritt nur auf, wenn das Laden von Klassen für das Modul aktiviert wurde, das die-Klasse enthält.</span><span class="sxs-lookup"><span data-stu-id="2ceca-109">This callback occurs only if class loading has been enabled for the module that contains the class.</span></span> <span data-ttu-id="2ceca-110">Das Laden von Klassen ist für dynamische Module immer aktiviert.</span><span class="sxs-lookup"><span data-stu-id="2ceca-110">Class loading is always enabled for dynamic modules.</span></span>  
  
 <span data-ttu-id="2ceca-111">Der `LoadClass` Rückruf bietet eine angemessene Zeit zum Binden von Breakpoints an neu generierte Klassen in dynamischen Modulen.</span><span class="sxs-lookup"><span data-stu-id="2ceca-111">The `LoadClass` callback provides an appropriate time to bind breakpoints to newly generated classes in dynamic modules.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2ceca-112">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="2ceca-112">Requirements</span></span>  
 <span data-ttu-id="2ceca-113">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2ceca-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2ceca-114">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="2ceca-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="2ceca-115">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2ceca-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2ceca-116">**.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2ceca-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2ceca-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="2ceca-117">See also</span></span>

- [<span data-ttu-id="2ceca-118">UnloadClass-Methode</span><span class="sxs-lookup"><span data-stu-id="2ceca-118">UnloadClass Method</span></span>](icordebugmanagedcallback-unloadclass-method.md)
- [<span data-ttu-id="2ceca-119">ICorDebugManagedCallback-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="2ceca-119">ICorDebugManagedCallback Interface</span></span>](icordebugmanagedcallback-interface.md)
