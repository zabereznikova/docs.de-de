---
title: ICorDebugModuleDebugEvent::GetModule-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: b1141c35-4253-4e34-b3e4-ed406a9dea4f
caps.latest.revision: "5"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: b11ab8991a9f44cf2868474a8a0f6dcc1c3308c6
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugmoduledebugeventgetmodule-method"></a><span data-ttu-id="2cc22-102">ICorDebugModuleDebugEvent::GetModule-Methode</span><span class="sxs-lookup"><span data-stu-id="2cc22-102">ICorDebugModuleDebugEvent::GetModule Method</span></span>
<span data-ttu-id="2cc22-103">Ruft das zusammengeführte Modul ab, das soeben geladen oder entladen wurde.</span><span class="sxs-lookup"><span data-stu-id="2cc22-103">Gets the merged module that was just loaded or unloaded.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2cc22-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="2cc22-104">Syntax</span></span>  
  
```  
HRESULT GetModule(  
   [out]ICorDebugModule **ppModule  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="2cc22-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="2cc22-105">Parameters</span></span>  
 `ppModule`  
 <span data-ttu-id="2cc22-106">[out] Ein Zeiger auf die Adresse eines ICorDebugModule-Objekts, das das zusammengeführte Modul darstellt, das soeben geladen oder entladen wurde.</span><span class="sxs-lookup"><span data-stu-id="2cc22-106">[out] A pointer to the address of an ICorDebugModule object that represents the merged module that was just loaded or unloaded.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2cc22-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="2cc22-107">Remarks</span></span>  
 <span data-ttu-id="2cc22-108">Sie erreichen die [GetEventKind](../../../../docs/framework/unmanaged-api/debugging/icordebugdebugevent-geteventkind-method.md) Methode, um zu bestimmen, ob das Modul geladen oder entladen wurde.</span><span class="sxs-lookup"><span data-stu-id="2cc22-108">You can call the [GetEventKind](../../../../docs/framework/unmanaged-api/debugging/icordebugdebugevent-geteventkind-method.md) method to determine whether the module was loaded or unloaded.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="2cc22-109">Diese Methode ist nur mit .NET Native verfügbar.</span><span class="sxs-lookup"><span data-stu-id="2cc22-109">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2cc22-110">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="2cc22-110">Requirements</span></span>  
 <span data-ttu-id="2cc22-111">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2cc22-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2cc22-112">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="2cc22-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="2cc22-113">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2cc22-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2cc22-114">**.NET Framework-Versionen:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2cc22-114">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2cc22-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="2cc22-115">See Also</span></span>  
 [<span data-ttu-id="2cc22-116">ICorDebugModuleDebugEvent-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="2cc22-116">ICorDebugModuleDebugEvent Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmoduledebugevent-interface.md)  
 [<span data-ttu-id="2cc22-117">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="2cc22-117">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
