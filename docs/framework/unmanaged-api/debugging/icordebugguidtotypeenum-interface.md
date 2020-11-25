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
ms.openlocfilehash: 149c5b09639c8809e736ade09566e7b1b530e3eb
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95705708"
---
# <a name="icordebugguidtotypeenum-interface"></a><span data-ttu-id="0b932-102">ICorDebugGuidToTypeEnum-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="0b932-102">ICorDebugGuidToTypeEnum Interface</span></span>

<span data-ttu-id="0b932-103">Stellt einen Enumerator bereit, der die Zuordnung zwischen einem Satz von GUIDs und den entsprechenden Typen definiert, die von ICorDebugType-Instanzen dargestellt werden.</span><span class="sxs-lookup"><span data-stu-id="0b932-103">Provides an enumerator that defines the mapping between a set of GUIDs and their corresponding types, which are represented by ICorDebugType instances.</span></span> <span data-ttu-id="0b932-104">Diese Schnittstelle erbt die Methoden von der ICorDebugEnum-Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="0b932-104">This interface inherits the methods from the ICorDebugEnum interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="0b932-105">Methoden</span><span class="sxs-lookup"><span data-stu-id="0b932-105">Methods</span></span>  
  
|<span data-ttu-id="0b932-106">Methode</span><span class="sxs-lookup"><span data-stu-id="0b932-106">Method</span></span>|<span data-ttu-id="0b932-107">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="0b932-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="0b932-108">ICorDebug Type:: Next</span><span class="sxs-lookup"><span data-stu-id="0b932-108">ICorDebugGuidToTypeEnum::Next</span></span>](icordebugguidtotypeenum-next-method.md)|<span data-ttu-id="0b932-109">Ruft die angegebene Anzahl von [cordebugguidtoidetypemapping](cordebugguidtotypemapping-structure.md) -Instanzen ab, die GUIDs Typinformationen zuordnen.</span><span class="sxs-lookup"><span data-stu-id="0b932-109">Gets the specified number of [CorDebugGuidToTypeMapping](cordebugguidtotypemapping-structure.md) instances that map GUIDs to type information.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0b932-110">Hinweise</span><span class="sxs-lookup"><span data-stu-id="0b932-110">Remarks</span></span>  

 <span data-ttu-id="0b932-111">Ein `ICorDebugGuidToTypeEnum` Schnittstellen Objekt kann durch Aufrufen der [ICorDebugAppDomain3:: getcachedwinrttypes](icordebugappdomain3-getcachedwinrttypes-method.md) -Methode abgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="0b932-111">An `ICorDebugGuidToTypeEnum` interface object can be retrieved by calling the [ICorDebugAppDomain3::GetCachedWinRTTypes](icordebugappdomain3-getcachedwinrttypes-method.md) method.</span></span> <span data-ttu-id="0b932-112">Ein Debugger kann die [Next](icordebugguidtotypeenum-next-method.md) -Methode dieser Schnittstelle aufrufen, um [cordebugguidtotypemapping](cordebugguidtotypemapping-structure.md) -Objekte abzurufen, die Zuordnungen verwalteter Darstellungen von Windows-Runtime Typen darstellen, die in der Anwendungsdomäne geladen wurden, die für den Aufrufen der [ICorDebugAppDomain3:: getcachedwinrttypes](icordebugappdomain3-getcachedwinrttypes-method.md) -Methode verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="0b932-112">A debugger can call this interface's [Next](icordebugguidtotypeenum-next-method.md) method to retrieve [CorDebugGuidToTypeMapping](cordebugguidtotypemapping-structure.md) objects that represent mappings of managed representations of Windows Runtime types loaded in the application domain used for the call to the [ICorDebugAppDomain3::GetCachedWinRTTypes](icordebugappdomain3-getcachedwinrttypes-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0b932-113">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="0b932-113">Requirements</span></span>  

 <span data-ttu-id="0b932-114">**Plattformen:** Windows-Runtime</span><span class="sxs-lookup"><span data-stu-id="0b932-114">**Platforms:** Windows Runtime</span></span>  
  
 <span data-ttu-id="0b932-115">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="0b932-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="0b932-116">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="0b932-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="0b932-117">**.NET Framework Versionen:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0b932-117">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0b932-118">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="0b932-118">See also</span></span>

- [<span data-ttu-id="0b932-119">Debugschnittstellen</span><span class="sxs-lookup"><span data-stu-id="0b932-119">Debugging Interfaces</span></span>](debugging-interfaces.md)
