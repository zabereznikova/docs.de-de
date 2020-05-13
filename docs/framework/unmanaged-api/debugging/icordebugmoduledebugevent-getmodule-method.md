---
title: ICorDebugModuleDebugEvent::GetModule-Methode
ms.date: 03/30/2017
ms.assetid: b1141c35-4253-4e34-b3e4-ed406a9dea4f
ms.openlocfilehash: 1df71ddbf1ee76cc8202d8f9e263b9d95b4aaa09
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/12/2020
ms.locfileid: "83213360"
---
# <a name="icordebugmoduledebugeventgetmodule-method"></a><span data-ttu-id="7c371-102">ICorDebugModuleDebugEvent::GetModule-Methode</span><span class="sxs-lookup"><span data-stu-id="7c371-102">ICorDebugModuleDebugEvent::GetModule Method</span></span>
<span data-ttu-id="7c371-103">Ruft das zusammengeführte Modul ab, das soeben geladen oder entladen wurde.</span><span class="sxs-lookup"><span data-stu-id="7c371-103">Gets the merged module that was just loaded or unloaded.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7c371-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="7c371-104">Syntax</span></span>  
  
```cpp  
HRESULT GetModule(  
   [out]ICorDebugModule **ppModule  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7c371-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="7c371-105">Parameters</span></span>  
 `ppModule`  
 <span data-ttu-id="7c371-106">[out] Ein Zeiger auf die Adresse eines ICorDebugModule-Objekts, das das zusammengeführte Modul darstellt, das soeben geladen oder entladen wurde.</span><span class="sxs-lookup"><span data-stu-id="7c371-106">[out] A pointer to the address of an ICorDebugModule object that represents the merged module that was just loaded or unloaded.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="7c371-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="7c371-107">Remarks</span></span>  
 <span data-ttu-id="7c371-108">Sie können die [geteventkind](icordebugdebugevent-geteventkind-method.md) -Methode aufrufen, um zu bestimmen, ob das Modul geladen oder entladen wurde.</span><span class="sxs-lookup"><span data-stu-id="7c371-108">You can call the [GetEventKind](icordebugdebugevent-geteventkind-method.md) method to determine whether the module was loaded or unloaded.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="7c371-109">Diese Methode ist nur mit .NET Native verfügbar.</span><span class="sxs-lookup"><span data-stu-id="7c371-109">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7c371-110">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="7c371-110">Requirements</span></span>  
 <span data-ttu-id="7c371-111">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7c371-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7c371-112">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="7c371-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="7c371-113">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="7c371-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="7c371-114">**.NET Framework Versionen:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7c371-114">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7c371-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="7c371-115">See also</span></span>

- [<span data-ttu-id="7c371-116">ICorDebugModuleDebugEvent-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="7c371-116">ICorDebugModuleDebugEvent Interface</span></span>](icordebugmoduledebugevent-interface.md)
- [<span data-ttu-id="7c371-117">Debugschnittstellen</span><span class="sxs-lookup"><span data-stu-id="7c371-117">Debugging Interfaces</span></span>](debugging-interfaces.md)
