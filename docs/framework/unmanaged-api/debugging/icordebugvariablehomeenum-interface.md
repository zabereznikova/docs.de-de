---
title: ICorDebugVariableHomeEnum-Schnittstelle
ms.date: 03/30/2017
api_name:
- ICorDebugVariableHomeEnum
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugVariableHomeEnum
helpviewer_keywords:
- ICorDebugVariableHomeEnum interface [.NET Framework debugging]
ms.assetid: c312ae6d-c8dc-48d6-9f1e-ead515c88fdf
topic_type:
- apiref
ms.openlocfilehash: 8e8caad9f0fc60121dbd1c738a6024da3e4d02f6
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95726001"
---
# <a name="icordebugvariablehomeenum-interface"></a><span data-ttu-id="30f81-102">ICorDebugVariableHomeEnum-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="30f81-102">ICorDebugVariableHomeEnum Interface</span></span>

<span data-ttu-id="30f81-103">Stellt einen Enumerator für die lokalen Variablen und Argumente in einer Funktion bereit.</span><span class="sxs-lookup"><span data-stu-id="30f81-103">Provides an enumerator to the local variables and arguments in a function.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="30f81-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="30f81-104">Methods</span></span>  
  
|<span data-ttu-id="30f81-105">Methode</span><span class="sxs-lookup"><span data-stu-id="30f81-105">Method</span></span>|<span data-ttu-id="30f81-106">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="30f81-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="30f81-107">Next-Methode</span><span class="sxs-lookup"><span data-stu-id="30f81-107">Next Method</span></span>](icordebugvariablehomeenum-next-method.md)|<span data-ttu-id="30f81-108">Ruft die angegebene Anzahl von [icordebugvariablehome](icordebugvariablehome-interface.md) -Instanzen ab, die Informationen zu den lokalen Variablen und Argumenten in einer Funktion enthalten.</span><span class="sxs-lookup"><span data-stu-id="30f81-108">Gets the specified number of [ICorDebugVariableHome](icordebugvariablehome-interface.md) instances that contain information about the local variables and arguments in a function.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="30f81-109">Hinweise</span><span class="sxs-lookup"><span data-stu-id="30f81-109">Remarks</span></span>  

 <span data-ttu-id="30f81-110">Die `ICorDebugVariableHomeEnum` Schnittstelle implementiert die ICorDebugEnum-Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="30f81-110">The `ICorDebugVariableHomeEnum` interface implements the ICorDebugEnum interface.</span></span>  
  
 <span data-ttu-id="30f81-111">Eine `ICorDebugVariableHomeEnum` Instanz wird mit [icordebugvariablehome](icordebugvariablehome-interface.md) -Instanzen aufgefüllt, indem die [ICorDebugCode4:: enumeratevariablehomes](icordebugcode4-enumeratevariablehomes-method.md) -Methode aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="30f81-111">An `ICorDebugVariableHomeEnum` instance is populated with [ICorDebugVariableHome](icordebugvariablehome-interface.md) instances by calling the [ICorDebugCode4::EnumerateVariableHomes](icordebugcode4-enumeratevariablehomes-method.md) method.</span></span> <span data-ttu-id="30f81-112">Jede [icorentbugvariablehome](icordebugvariablehome-interface.md) -Instanz in der Auflistung stellt eine lokale Variable oder ein Argument in einer Funktion dar.</span><span class="sxs-lookup"><span data-stu-id="30f81-112">Each [ICorDebugVariableHome](icordebugvariablehome-interface.md) instance in the collection represents a local variable or argument in a function.</span></span> <span data-ttu-id="30f81-113">Die  [icordebugvariablehome](icordebugvariablehome-interface.md) -Objekte in der Auflistung können durch Aufrufen der [icordebugvariablehomedenum:: Next](icordebugvariablehomeenum-next-method.md) -Methode aufgelistet werden.</span><span class="sxs-lookup"><span data-stu-id="30f81-113">The  [ICorDebugVariableHome](icordebugvariablehome-interface.md) objects in the collection can be enumerated by calling the [ICorDebugVariableHomeEnum::Next](icordebugvariablehomeenum-next-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="30f81-114">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="30f81-114">Requirements</span></span>  

 <span data-ttu-id="30f81-115">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="30f81-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="30f81-116">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="30f81-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="30f81-117">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="30f81-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="30f81-118">**.NET Framework Versionen:**[!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="30f81-118">**.NET Framework Versions:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="30f81-119">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="30f81-119">See also</span></span>

- [<span data-ttu-id="30f81-120">ICorDebugVariableHome-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="30f81-120">ICorDebugVariableHome Interface</span></span>](icordebugvariablehome-interface.md)
- [<span data-ttu-id="30f81-121">Debugschnittstellen</span><span class="sxs-lookup"><span data-stu-id="30f81-121">Debugging Interfaces</span></span>](debugging-interfaces.md)
