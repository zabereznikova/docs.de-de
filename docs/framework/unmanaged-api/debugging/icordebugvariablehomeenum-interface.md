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
ms.openlocfilehash: a9b65449747fde42f9cd770e33741ef34d33fbb8
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73121021"
---
# <a name="icordebugvariablehomeenum-interface"></a><span data-ttu-id="19102-102">ICorDebugVariableHomeEnum-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="19102-102">ICorDebugVariableHomeEnum Interface</span></span>
<span data-ttu-id="19102-103">Stellt einen Enumerator für die lokalen Variablen und Argumente in einer Funktion bereit.</span><span class="sxs-lookup"><span data-stu-id="19102-103">Provides an enumerator to the local variables and arguments in a function.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="19102-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="19102-104">Methods</span></span>  
  
|<span data-ttu-id="19102-105">Methode</span><span class="sxs-lookup"><span data-stu-id="19102-105">Method</span></span>|<span data-ttu-id="19102-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="19102-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="19102-107">Next-Methode</span><span class="sxs-lookup"><span data-stu-id="19102-107">Next Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehomeenum-next-method.md)|<span data-ttu-id="19102-108">Ruft die angegebene Anzahl von [icordebugvariablehome](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md) -Instanzen ab, die Informationen zu den lokalen Variablen und Argumenten in einer Funktion enthalten.</span><span class="sxs-lookup"><span data-stu-id="19102-108">Gets the specified number of [ICorDebugVariableHome](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md) instances that contain information about the local variables and arguments in a function.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="19102-109">Hinweise</span><span class="sxs-lookup"><span data-stu-id="19102-109">Remarks</span></span>  
 <span data-ttu-id="19102-110">Die `ICorDebugVariableHomeEnum`-Schnittstelle implementiert die ICorDebugEnum-Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="19102-110">The `ICorDebugVariableHomeEnum` interface implements the ICorDebugEnum interface.</span></span>  
  
 <span data-ttu-id="19102-111">Eine `ICorDebugVariableHomeEnum` Instanz wird mit [icordebugvariablehome](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md) -Instanzen aufgefüllt, indem die [ICorDebugCode4:: enumeratevariablehomes](../../../../docs/framework/unmanaged-api/debugging/icordebugcode4-enumeratevariablehomes-method.md) -Methode aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="19102-111">An `ICorDebugVariableHomeEnum` instance is populated with [ICorDebugVariableHome](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md) instances by calling the [ICorDebugCode4::EnumerateVariableHomes](../../../../docs/framework/unmanaged-api/debugging/icordebugcode4-enumeratevariablehomes-method.md) method.</span></span> <span data-ttu-id="19102-112">Jede [icorentbugvariablehome](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md) -Instanz in der Auflistung stellt eine lokale Variable oder ein Argument in einer Funktion dar.</span><span class="sxs-lookup"><span data-stu-id="19102-112">Each [ICorDebugVariableHome](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md) instance in the collection represents a local variable or argument in a function.</span></span> <span data-ttu-id="19102-113">Die [icordebugvariablehome](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md) -Objekte in der Auflistung können durch Aufrufen der [icordebugvariablehomedenum:: Next](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehomeenum-next-method.md) -Methode aufgelistet werden.</span><span class="sxs-lookup"><span data-stu-id="19102-113">The  [ICorDebugVariableHome](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md) objects in the collection can be enumerated by calling the [ICorDebugVariableHomeEnum::Next](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehomeenum-next-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="19102-114">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="19102-114">Requirements</span></span>  
 <span data-ttu-id="19102-115">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="19102-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="19102-116">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="19102-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="19102-117">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="19102-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="19102-118">**.NET Framework-Versionen:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="19102-118">**.NET Framework Versions:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="19102-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="19102-119">See also</span></span>

- [<span data-ttu-id="19102-120">ICorDebugVariableHome-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="19102-120">ICorDebugVariableHome Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md)
- [<span data-ttu-id="19102-121">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="19102-121">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
