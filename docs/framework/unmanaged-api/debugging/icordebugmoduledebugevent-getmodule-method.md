---
title: ICorDebugModuleDebugEvent::GetModule-Methode
ms.date: 03/30/2017
ms.assetid: b1141c35-4253-4e34-b3e4-ed406a9dea4f
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 56ce5b3f5fb3c6d2a00c407afc303895273c2251
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33419489"
---
# <a name="icordebugmoduledebugeventgetmodule-method"></a><span data-ttu-id="f0c55-102">ICorDebugModuleDebugEvent::GetModule-Methode</span><span class="sxs-lookup"><span data-stu-id="f0c55-102">ICorDebugModuleDebugEvent::GetModule Method</span></span>
<span data-ttu-id="f0c55-103">Ruft das zusammengeführte Modul ab, das soeben geladen oder entladen wurde.</span><span class="sxs-lookup"><span data-stu-id="f0c55-103">Gets the merged module that was just loaded or unloaded.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f0c55-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="f0c55-104">Syntax</span></span>  
  
```  
HRESULT GetModule(  
   [out]ICorDebugModule **ppModule  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="f0c55-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="f0c55-105">Parameters</span></span>  
 `ppModule`  
 <span data-ttu-id="f0c55-106">[out] Ein Zeiger auf die Adresse eines ICorDebugModule-Objekts, das das zusammengeführte Modul darstellt, das soeben geladen oder entladen wurde.</span><span class="sxs-lookup"><span data-stu-id="f0c55-106">[out] A pointer to the address of an ICorDebugModule object that represents the merged module that was just loaded or unloaded.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f0c55-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="f0c55-107">Remarks</span></span>  
 <span data-ttu-id="f0c55-108">Sie erreichen die [GetEventKind](../../../../docs/framework/unmanaged-api/debugging/icordebugdebugevent-geteventkind-method.md) Methode, um zu bestimmen, ob das Modul geladen oder entladen wurde.</span><span class="sxs-lookup"><span data-stu-id="f0c55-108">You can call the [GetEventKind](../../../../docs/framework/unmanaged-api/debugging/icordebugdebugevent-geteventkind-method.md) method to determine whether the module was loaded or unloaded.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="f0c55-109">Diese Methode ist nur mit .NET Native verfügbar.</span><span class="sxs-lookup"><span data-stu-id="f0c55-109">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f0c55-110">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="f0c55-110">Requirements</span></span>  
 <span data-ttu-id="f0c55-111">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f0c55-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f0c55-112">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="f0c55-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="f0c55-113">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f0c55-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f0c55-114">**.NET Framework-Versionen:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f0c55-114">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f0c55-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f0c55-115">See Also</span></span>  
 [<span data-ttu-id="f0c55-116">ICorDebugModuleDebugEvent-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="f0c55-116">ICorDebugModuleDebugEvent Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmoduledebugevent-interface.md)  
 [<span data-ttu-id="f0c55-117">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="f0c55-117">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
