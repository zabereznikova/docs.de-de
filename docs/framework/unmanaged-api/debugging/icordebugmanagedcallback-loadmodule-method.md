---
title: ICorDebugManagedCallback::LoadModule-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugManagedCallback.LoadModule
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugManagedCallback::LoadModule
helpviewer_keywords:
- ICorDebugManagedCallback::LoadModule method [.NET Framework debugging]
- LoadModule method [.NET Framework debugging]
ms.assetid: 66ec04e9-87cb-42ce-9720-81522abb5d5a
topic_type:
- apiref
ms.openlocfilehash: 21a97f140a41f8f380c1334652bc2417e19659c6
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/28/2020
ms.locfileid: "76777137"
---
# <a name="icordebugmanagedcallbackloadmodule-method"></a><span data-ttu-id="de047-102">ICorDebugManagedCallback::LoadModule-Methode</span><span class="sxs-lookup"><span data-stu-id="de047-102">ICorDebugManagedCallback::LoadModule Method</span></span>
<span data-ttu-id="de047-103">Benachrichtigt den Debugger, dass ein Common Language Runtime (CLR)-Modul erfolgreich geladen wurde.</span><span class="sxs-lookup"><span data-stu-id="de047-103">Notifies the debugger that a common language runtime (CLR) module has been successfully loaded.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="de047-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="de047-104">Syntax</span></span>  
  
```cpp  
HRESULT LoadModule (  
    [in] ICorDebugAppDomain *pAppDomain,  
    [in] ICorDebugModule    *pModule  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="de047-105">Parameters</span><span class="sxs-lookup"><span data-stu-id="de047-105">Parameters</span></span>  
 `pAppDomain`  
 <span data-ttu-id="de047-106">in Ein Zeiger auf ein ICorDebugAppDomain-Objekt, das die Anwendungsdomäne darstellt, in die das Modul geladen wurde.</span><span class="sxs-lookup"><span data-stu-id="de047-106">[in] A pointer to an ICorDebugAppDomain object that represents the application domain into which the module has been loaded.</span></span>  
  
 `pModule`  
 <span data-ttu-id="de047-107">in Ein Zeiger auf ein ICorDebug Module-Objekt, das das CLR-Modul darstellt.</span><span class="sxs-lookup"><span data-stu-id="de047-107">[in] A pointer to an ICorDebugModule object that represents the CLR module.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="de047-108">Hinweise</span><span class="sxs-lookup"><span data-stu-id="de047-108">Remarks</span></span>  
 <span data-ttu-id="de047-109">Der `LoadModule`-Rückruf bietet eine angemessene Zeit zum Überprüfen der Metadaten für das Modul, zum Festlegen von Just-in-time (JIT)-Compilerflags oder zum Aktivieren oder Deaktivieren von Rückrufe zum Laden von Klassen für das Modul.</span><span class="sxs-lookup"><span data-stu-id="de047-109">The `LoadModule` callback provides an appropriate time to examine metadata for the module, set just-in-time (JIT) compiler flags, or enable or disable class loading callbacks for the module.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="de047-110">-Anforderungen</span><span class="sxs-lookup"><span data-stu-id="de047-110">Requirements</span></span>  
 <span data-ttu-id="de047-111">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="de047-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="de047-112">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="de047-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="de047-113">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="de047-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="de047-114">**.NET Framework Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="de047-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="de047-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="de047-115">See also</span></span>

- [<span data-ttu-id="de047-116">UnloadModule-Methode</span><span class="sxs-lookup"><span data-stu-id="de047-116">UnloadModule Method</span></span>](icordebugmanagedcallback-unloadmodule-method.md)
- [<span data-ttu-id="de047-117">ICorDebugManagedCallback-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="de047-117">ICorDebugManagedCallback Interface</span></span>](icordebugmanagedcallback-interface.md)
