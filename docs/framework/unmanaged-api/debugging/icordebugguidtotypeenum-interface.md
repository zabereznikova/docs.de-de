---
title: ICorDebugGuidToTypeEnum-Schnittstelle
ms.date: 03/30/2017
api_name:
- ICorDebugGuidToTypeEnum
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugGuidToTypeEnum
helpviewer_keywords:
- ICorDebugGuidToTypeEnum interface [.NET Framework debugging]
ms.assetid: aa32b12b-05fc-4ea8-a904-adae25034269
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: f2ea67c6e4d860d41cfe67aaab73babb51f3ce45
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59210658"
---
# <a name="icordebugguidtotypeenum-interface"></a><span data-ttu-id="365c2-102">ICorDebugGuidToTypeEnum-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="365c2-102">ICorDebugGuidToTypeEnum Interface</span></span>
<span data-ttu-id="365c2-103">Stellt einen Enumerator, der definiert die Zuordnung zwischen einem Satz von GUIDs und die zugehörigen Typen, die von ICorDebugType-Instanzen dargestellt werden.</span><span class="sxs-lookup"><span data-stu-id="365c2-103">Provides an enumerator that defines the mapping between a set of GUIDs and their corresponding types, which are represented by ICorDebugType instances.</span></span> <span data-ttu-id="365c2-104">Diese Schnittstelle erbt die Methoden aus der ICorDebugEnum-Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="365c2-104">This interface inherits the methods from the ICorDebugEnum interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="365c2-105">Methoden</span><span class="sxs-lookup"><span data-stu-id="365c2-105">Methods</span></span>  
  
|<span data-ttu-id="365c2-106">Methode</span><span class="sxs-lookup"><span data-stu-id="365c2-106">Method</span></span>|<span data-ttu-id="365c2-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="365c2-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="365c2-108">ICorDebugGuidToTypeEnum::Next</span><span class="sxs-lookup"><span data-stu-id="365c2-108">ICorDebugGuidToTypeEnum::Next</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugguidtotypeenum-next-method.md)|<span data-ttu-id="365c2-109">Ruft die angegebene Anzahl von [CorDebugGuidToTypeMapping](../../../../docs/framework/unmanaged-api/debugging/cordebugguidtotypemapping-structure.md) Instanzen, die GUIDs, die Typinformationen zuordnen.</span><span class="sxs-lookup"><span data-stu-id="365c2-109">Gets the specified number of [CorDebugGuidToTypeMapping](../../../../docs/framework/unmanaged-api/debugging/cordebugguidtotypemapping-structure.md) instances that map GUIDs to type information.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="365c2-110">Hinweise</span><span class="sxs-lookup"><span data-stu-id="365c2-110">Remarks</span></span>  
 <span data-ttu-id="365c2-111">Ein `ICorDebugGuidToTypeEnum` Schnittstellenobjekt abgerufen werden kann, durch den Aufruf der [icordebugappdomain3:: Getcachedwinrttypes](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain3-getcachedwinrttypes-method.md) Methode.</span><span class="sxs-lookup"><span data-stu-id="365c2-111">An `ICorDebugGuidToTypeEnum` interface object can be retrieved by calling the [ICorDebugAppDomain3::GetCachedWinRTTypes](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain3-getcachedwinrttypes-method.md) method.</span></span> <span data-ttu-id="365c2-112">Ein Debugger kann dieser Schnittstelle aufrufen [Weiter](../../../../docs/framework/unmanaged-api/debugging/icordebugguidtotypeenum-next-method.md) Methode zum Abrufen [CorDebugGuidToTypeMapping](../../../../docs/framework/unmanaged-api/debugging/cordebugguidtotypemapping-structure.md) Zuordnungen von darstellende – Objekte verwaltete Darstellungen von [!INCLUDE[wrt](../../../../includes/wrt-md.md)] Typen geladen werden, der die Anwendungsdomäne für den Aufruf verwendet die [icordebugappdomain3:: Getcachedwinrttypes](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain3-getcachedwinrttypes-method.md) Methode.</span><span class="sxs-lookup"><span data-stu-id="365c2-112">A debugger can call this interface's [Next](../../../../docs/framework/unmanaged-api/debugging/icordebugguidtotypeenum-next-method.md) method to retrieve [CorDebugGuidToTypeMapping](../../../../docs/framework/unmanaged-api/debugging/cordebugguidtotypemapping-structure.md) objects that represent mappings of managed representations of [!INCLUDE[wrt](../../../../includes/wrt-md.md)] types loaded in the application domain used for the call to the [ICorDebugAppDomain3::GetCachedWinRTTypes](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain3-getcachedwinrttypes-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="365c2-113">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="365c2-113">Requirements</span></span>  
 <span data-ttu-id="365c2-114">**Plattformen:** [!INCLUDE[wrt](../../../../includes/wrt-md.md)]</span><span class="sxs-lookup"><span data-stu-id="365c2-114">**Platforms:** [!INCLUDE[wrt](../../../../includes/wrt-md.md)]</span></span>  
  
 <span data-ttu-id="365c2-115">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="365c2-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="365c2-116">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="365c2-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="365c2-117">**.NET Framework-Versionen:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="365c2-117">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="365c2-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="365c2-118">See also</span></span>

- [<span data-ttu-id="365c2-119">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="365c2-119">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
