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
ms.openlocfilehash: 22cd08154268bdf1e819a0ec0067b05a81d60b22
ms.sourcegitcommit: 5bc85ad81d96b8dc2a90ce53bada475ee5662c44
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/12/2019
ms.locfileid: "67025828"
---
# <a name="icordebugguidtotypeenum-interface"></a><span data-ttu-id="28302-102">ICorDebugGuidToTypeEnum-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="28302-102">ICorDebugGuidToTypeEnum Interface</span></span>
<span data-ttu-id="28302-103">Stellt einen Enumerator, der definiert die Zuordnung zwischen einem Satz von GUIDs und die zugehörigen Typen, die von ICorDebugType-Instanzen dargestellt werden.</span><span class="sxs-lookup"><span data-stu-id="28302-103">Provides an enumerator that defines the mapping between a set of GUIDs and their corresponding types, which are represented by ICorDebugType instances.</span></span> <span data-ttu-id="28302-104">Diese Schnittstelle erbt die Methoden aus der ICorDebugEnum-Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="28302-104">This interface inherits the methods from the ICorDebugEnum interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="28302-105">Methoden</span><span class="sxs-lookup"><span data-stu-id="28302-105">Methods</span></span>  
  
|<span data-ttu-id="28302-106">Methode</span><span class="sxs-lookup"><span data-stu-id="28302-106">Method</span></span>|<span data-ttu-id="28302-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="28302-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="28302-108">ICorDebugGuidToTypeEnum::Next</span><span class="sxs-lookup"><span data-stu-id="28302-108">ICorDebugGuidToTypeEnum::Next</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugguidtotypeenum-next-method.md)|<span data-ttu-id="28302-109">Ruft die angegebene Anzahl von [CorDebugGuidToTypeMapping](../../../../docs/framework/unmanaged-api/debugging/cordebugguidtotypemapping-structure.md) Instanzen, die GUIDs, die Typinformationen zuordnen.</span><span class="sxs-lookup"><span data-stu-id="28302-109">Gets the specified number of [CorDebugGuidToTypeMapping](../../../../docs/framework/unmanaged-api/debugging/cordebugguidtotypemapping-structure.md) instances that map GUIDs to type information.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="28302-110">Hinweise</span><span class="sxs-lookup"><span data-stu-id="28302-110">Remarks</span></span>  
 <span data-ttu-id="28302-111">Ein `ICorDebugGuidToTypeEnum` Schnittstellenobjekt abgerufen werden kann, durch den Aufruf der [icordebugappdomain3:: Getcachedwinrttypes](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain3-getcachedwinrttypes-method.md) Methode.</span><span class="sxs-lookup"><span data-stu-id="28302-111">An `ICorDebugGuidToTypeEnum` interface object can be retrieved by calling the [ICorDebugAppDomain3::GetCachedWinRTTypes](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain3-getcachedwinrttypes-method.md) method.</span></span> <span data-ttu-id="28302-112">Ein Debugger kann dieser Schnittstelle aufrufen [Weiter](../../../../docs/framework/unmanaged-api/debugging/icordebugguidtotypeenum-next-method.md) Methode zum Abrufen [CorDebugGuidToTypeMapping](../../../../docs/framework/unmanaged-api/debugging/cordebugguidtotypemapping-structure.md) Zuordnungen von verwalteten Darstellungen von Windows-Runtime-Typen darstellende – Objekte geladen, der die Anwendungsdomäne für den Aufruf verwendet die [icordebugappdomain3:: Getcachedwinrttypes](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain3-getcachedwinrttypes-method.md) Methode.</span><span class="sxs-lookup"><span data-stu-id="28302-112">A debugger can call this interface's [Next](../../../../docs/framework/unmanaged-api/debugging/icordebugguidtotypeenum-next-method.md) method to retrieve [CorDebugGuidToTypeMapping](../../../../docs/framework/unmanaged-api/debugging/cordebugguidtotypemapping-structure.md) objects that represent mappings of managed representations of Windows Runtime types loaded in the application domain used for the call to the [ICorDebugAppDomain3::GetCachedWinRTTypes](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain3-getcachedwinrttypes-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="28302-113">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="28302-113">Requirements</span></span>  
 <span data-ttu-id="28302-114">**Plattformen:** Windows-Runtime</span><span class="sxs-lookup"><span data-stu-id="28302-114">**Platforms:** Windows Runtime</span></span>  
  
 <span data-ttu-id="28302-115">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="28302-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="28302-116">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="28302-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="28302-117">**.NET Framework-Versionen:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="28302-117">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="28302-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="28302-118">See also</span></span>

- [<span data-ttu-id="28302-119">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="28302-119">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
