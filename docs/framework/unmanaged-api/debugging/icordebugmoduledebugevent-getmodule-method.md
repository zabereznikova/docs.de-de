---
title: ICorDebugModuleDebugEvent::GetModule-Methode
ms.date: 03/30/2017
ms.assetid: b1141c35-4253-4e34-b3e4-ed406a9dea4f
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 1ad20bdee5fee83b62d5da7f52c607835055616f
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54672330"
---
# <a name="icordebugmoduledebugeventgetmodule-method"></a><span data-ttu-id="dbd27-102">ICorDebugModuleDebugEvent::GetModule-Methode</span><span class="sxs-lookup"><span data-stu-id="dbd27-102">ICorDebugModuleDebugEvent::GetModule Method</span></span>
<span data-ttu-id="dbd27-103">Ruft das zusammengeführte Modul ab, das soeben geladen oder entladen wurde.</span><span class="sxs-lookup"><span data-stu-id="dbd27-103">Gets the merged module that was just loaded or unloaded.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dbd27-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="dbd27-104">Syntax</span></span>  
  
```  
HRESULT GetModule(  
   [out]ICorDebugModule **ppModule  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="dbd27-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="dbd27-105">Parameters</span></span>  
 `ppModule`  
 <span data-ttu-id="dbd27-106">[out] Ein Zeiger auf die Adresse eines ICorDebugModule-Objekts, das das zusammengeführte Modul darstellt, das soeben geladen oder entladen wurde.</span><span class="sxs-lookup"><span data-stu-id="dbd27-106">[out] A pointer to the address of an ICorDebugModule object that represents the merged module that was just loaded or unloaded.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="dbd27-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="dbd27-107">Remarks</span></span>  
 <span data-ttu-id="dbd27-108">Rufen Sie die [GetEventKind](../../../../docs/framework/unmanaged-api/debugging/icordebugdebugevent-geteventkind-method.md) Methode, um zu bestimmen, ob das Modul geladen oder entladen wurde.</span><span class="sxs-lookup"><span data-stu-id="dbd27-108">You can call the [GetEventKind](../../../../docs/framework/unmanaged-api/debugging/icordebugdebugevent-geteventkind-method.md) method to determine whether the module was loaded or unloaded.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="dbd27-109">Diese Methode ist nur mit .NET Native verfügbar.</span><span class="sxs-lookup"><span data-stu-id="dbd27-109">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="dbd27-110">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="dbd27-110">Requirements</span></span>  
 <span data-ttu-id="dbd27-111">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="dbd27-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="dbd27-112">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="dbd27-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="dbd27-113">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="dbd27-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="dbd27-114">**.NET Framework-Versionen:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="dbd27-114">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dbd27-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="dbd27-115">See also</span></span>
- [<span data-ttu-id="dbd27-116">ICorDebugModuleDebugEvent-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="dbd27-116">ICorDebugModuleDebugEvent Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmoduledebugevent-interface.md)
- [<span data-ttu-id="dbd27-117">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="dbd27-117">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
