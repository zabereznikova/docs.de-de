---
title: ICorDebugModuleDebugEvent::GetModule-Methode
ms.date: 03/30/2017
ms.assetid: b1141c35-4253-4e34-b3e4-ed406a9dea4f
ms.openlocfilehash: 4d9eea8fb5c42002763a0ae52a186bf2c1e6d2ee
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/28/2020
ms.locfileid: "76792907"
---
# <a name="icordebugmoduledebugeventgetmodule-method"></a><span data-ttu-id="1edbf-102">ICorDebugModuleDebugEvent::GetModule-Methode</span><span class="sxs-lookup"><span data-stu-id="1edbf-102">ICorDebugModuleDebugEvent::GetModule Method</span></span>
<span data-ttu-id="1edbf-103">Ruft das zusammengeführte Modul ab, das soeben geladen oder entladen wurde.</span><span class="sxs-lookup"><span data-stu-id="1edbf-103">Gets the merged module that was just loaded or unloaded.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1edbf-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="1edbf-104">Syntax</span></span>  
  
```cpp  
HRESULT GetModule(  
   [out]ICorDebugModule **ppModule  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="1edbf-105">Parameters</span><span class="sxs-lookup"><span data-stu-id="1edbf-105">Parameters</span></span>  
 `ppModule`  
 <span data-ttu-id="1edbf-106">[out] Ein Zeiger auf die Adresse eines ICorDebugModule-Objekts, das das zusammengeführte Modul darstellt, das soeben geladen oder entladen wurde.</span><span class="sxs-lookup"><span data-stu-id="1edbf-106">[out] A pointer to the address of an ICorDebugModule object that represents the merged module that was just loaded or unloaded.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="1edbf-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="1edbf-107">Remarks</span></span>  
 <span data-ttu-id="1edbf-108">Sie können die [geteventkind](icordebugdebugevent-geteventkind-method.md) -Methode aufrufen, um zu bestimmen, ob das Modul geladen oder entladen wurde.</span><span class="sxs-lookup"><span data-stu-id="1edbf-108">You can call the [GetEventKind](icordebugdebugevent-geteventkind-method.md) method to determine whether the module was loaded or unloaded.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="1edbf-109">Diese Methode ist nur mit .NET Native verfügbar.</span><span class="sxs-lookup"><span data-stu-id="1edbf-109">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1edbf-110">-Anforderungen</span><span class="sxs-lookup"><span data-stu-id="1edbf-110">Requirements</span></span>  
 <span data-ttu-id="1edbf-111">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1edbf-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1edbf-112">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="1edbf-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="1edbf-113">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="1edbf-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="1edbf-114">**.NET Framework Versionen:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1edbf-114">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1edbf-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="1edbf-115">See also</span></span>

- [<span data-ttu-id="1edbf-116">ICorDebugModuleDebugEvent-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="1edbf-116">ICorDebugModuleDebugEvent Interface</span></span>](icordebugmoduledebugevent-interface.md)
- [<span data-ttu-id="1edbf-117">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="1edbf-117">Debugging Interfaces</span></span>](debugging-interfaces.md)
