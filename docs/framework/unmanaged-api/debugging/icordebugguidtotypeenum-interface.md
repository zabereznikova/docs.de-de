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
ms.openlocfilehash: da921644c4d967efb0d88060ada0332c5eb63965
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73138529"
---
# <a name="icordebugguidtotypeenum-interface"></a><span data-ttu-id="6eb81-102">ICorDebugGuidToTypeEnum-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="6eb81-102">ICorDebugGuidToTypeEnum Interface</span></span>
<span data-ttu-id="6eb81-103">Stellt einen Enumerator bereit, der die Zuordnung zwischen einem Satz von GUIDs und den entsprechenden Typen definiert, die von ICorDebugType-Instanzen dargestellt werden.</span><span class="sxs-lookup"><span data-stu-id="6eb81-103">Provides an enumerator that defines the mapping between a set of GUIDs and their corresponding types, which are represented by ICorDebugType instances.</span></span> <span data-ttu-id="6eb81-104">Diese Schnittstelle erbt die Methoden von der ICorDebugEnum-Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="6eb81-104">This interface inherits the methods from the ICorDebugEnum interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="6eb81-105">Methoden</span><span class="sxs-lookup"><span data-stu-id="6eb81-105">Methods</span></span>  
  
|<span data-ttu-id="6eb81-106">Methode</span><span class="sxs-lookup"><span data-stu-id="6eb81-106">Method</span></span>|<span data-ttu-id="6eb81-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="6eb81-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="6eb81-108">ICorDebug Type:: Next</span><span class="sxs-lookup"><span data-stu-id="6eb81-108">ICorDebugGuidToTypeEnum::Next</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugguidtotypeenum-next-method.md)|<span data-ttu-id="6eb81-109">Ruft die angegebene Anzahl von [cordebugguidtoidetypemapping](../../../../docs/framework/unmanaged-api/debugging/cordebugguidtotypemapping-structure.md) -Instanzen ab, die GUIDs Typinformationen zuordnen.</span><span class="sxs-lookup"><span data-stu-id="6eb81-109">Gets the specified number of [CorDebugGuidToTypeMapping](../../../../docs/framework/unmanaged-api/debugging/cordebugguidtotypemapping-structure.md) instances that map GUIDs to type information.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="6eb81-110">Hinweise</span><span class="sxs-lookup"><span data-stu-id="6eb81-110">Remarks</span></span>  
 <span data-ttu-id="6eb81-111">Ein `ICorDebugGuidToTypeEnum` Interface-Objekt kann durch Aufrufen der [ICorDebugAppDomain3:: getcachedwinrttypes](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain3-getcachedwinrttypes-method.md) -Methode abgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="6eb81-111">An `ICorDebugGuidToTypeEnum` interface object can be retrieved by calling the [ICorDebugAppDomain3::GetCachedWinRTTypes](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain3-getcachedwinrttypes-method.md) method.</span></span> <span data-ttu-id="6eb81-112">Ein Debugger kann die [Next](../../../../docs/framework/unmanaged-api/debugging/icordebugguidtotypeenum-next-method.md) -Methode dieser Schnittstelle aufrufen, um [cordebugguidtotypemapping](../../../../docs/framework/unmanaged-api/debugging/cordebugguidtotypemapping-structure.md) -Objekte abzurufen, die Zuordnungen verwalteter Darstellungen von Windows-Runtime Typen darstellen, die in der Anwendungsdomäne geladen werden, die für den Aufrufen [des ICorDebugAppDomain3:: getcachedwinrttypes](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain3-getcachedwinrttypes-method.md) -Methode.</span><span class="sxs-lookup"><span data-stu-id="6eb81-112">A debugger can call this interface's [Next](../../../../docs/framework/unmanaged-api/debugging/icordebugguidtotypeenum-next-method.md) method to retrieve [CorDebugGuidToTypeMapping](../../../../docs/framework/unmanaged-api/debugging/cordebugguidtotypemapping-structure.md) objects that represent mappings of managed representations of Windows Runtime types loaded in the application domain used for the call to the [ICorDebugAppDomain3::GetCachedWinRTTypes](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain3-getcachedwinrttypes-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6eb81-113">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="6eb81-113">Requirements</span></span>  
 <span data-ttu-id="6eb81-114">**Plattformen:** Windows-Runtime</span><span class="sxs-lookup"><span data-stu-id="6eb81-114">**Platforms:** Windows Runtime</span></span>  
  
 <span data-ttu-id="6eb81-115">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="6eb81-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="6eb81-116">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="6eb81-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="6eb81-117">**.NET Framework-Versionen:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6eb81-117">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6eb81-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="6eb81-118">See also</span></span>

- [<span data-ttu-id="6eb81-119">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="6eb81-119">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
