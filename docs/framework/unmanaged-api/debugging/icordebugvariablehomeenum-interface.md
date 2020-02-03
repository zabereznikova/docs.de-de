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
ms.openlocfilehash: 74b3c7bed54f3735efbd5d2c56962d427518f71a
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/28/2020
ms.locfileid: "76790946"
---
# <a name="icordebugvariablehomeenum-interface"></a><span data-ttu-id="3ade2-102">ICorDebugVariableHomeEnum-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="3ade2-102">ICorDebugVariableHomeEnum Interface</span></span>
<span data-ttu-id="3ade2-103">Stellt einen Enumerator für die lokalen Variablen und Argumente in einer Funktion bereit.</span><span class="sxs-lookup"><span data-stu-id="3ade2-103">Provides an enumerator to the local variables and arguments in a function.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="3ade2-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="3ade2-104">Methods</span></span>  
  
|<span data-ttu-id="3ade2-105">-Methode</span><span class="sxs-lookup"><span data-stu-id="3ade2-105">Method</span></span>|<span data-ttu-id="3ade2-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="3ade2-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="3ade2-107">Next-Methode</span><span class="sxs-lookup"><span data-stu-id="3ade2-107">Next Method</span></span>](icordebugvariablehomeenum-next-method.md)|<span data-ttu-id="3ade2-108">Ruft die angegebene Anzahl von [icordebugvariablehome](icordebugvariablehome-interface.md) -Instanzen ab, die Informationen zu den lokalen Variablen und Argumenten in einer Funktion enthalten.</span><span class="sxs-lookup"><span data-stu-id="3ade2-108">Gets the specified number of [ICorDebugVariableHome](icordebugvariablehome-interface.md) instances that contain information about the local variables and arguments in a function.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3ade2-109">Hinweise</span><span class="sxs-lookup"><span data-stu-id="3ade2-109">Remarks</span></span>  
 <span data-ttu-id="3ade2-110">Die `ICorDebugVariableHomeEnum`-Schnittstelle implementiert die ICorDebugEnum-Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="3ade2-110">The `ICorDebugVariableHomeEnum` interface implements the ICorDebugEnum interface.</span></span>  
  
 <span data-ttu-id="3ade2-111">Eine `ICorDebugVariableHomeEnum` Instanz wird mit [icordebugvariablehome](icordebugvariablehome-interface.md) -Instanzen aufgefüllt, indem die [ICorDebugCode4:: enumeratevariablehomes](icordebugcode4-enumeratevariablehomes-method.md) -Methode aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="3ade2-111">An `ICorDebugVariableHomeEnum` instance is populated with [ICorDebugVariableHome](icordebugvariablehome-interface.md) instances by calling the [ICorDebugCode4::EnumerateVariableHomes](icordebugcode4-enumeratevariablehomes-method.md) method.</span></span> <span data-ttu-id="3ade2-112">Jede [icorentbugvariablehome](icordebugvariablehome-interface.md) -Instanz in der Auflistung stellt eine lokale Variable oder ein Argument in einer Funktion dar.</span><span class="sxs-lookup"><span data-stu-id="3ade2-112">Each [ICorDebugVariableHome](icordebugvariablehome-interface.md) instance in the collection represents a local variable or argument in a function.</span></span> <span data-ttu-id="3ade2-113">Die [icordebugvariablehome](icordebugvariablehome-interface.md) -Objekte in der Auflistung können durch Aufrufen der [icordebugvariablehomedenum:: Next](icordebugvariablehomeenum-next-method.md) -Methode aufgelistet werden.</span><span class="sxs-lookup"><span data-stu-id="3ade2-113">The  [ICorDebugVariableHome](icordebugvariablehome-interface.md) objects in the collection can be enumerated by calling the [ICorDebugVariableHomeEnum::Next](icordebugvariablehomeenum-next-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3ade2-114">-Anforderungen</span><span class="sxs-lookup"><span data-stu-id="3ade2-114">Requirements</span></span>  
 <span data-ttu-id="3ade2-115">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3ade2-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3ade2-116">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="3ade2-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="3ade2-117">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3ade2-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="3ade2-118">**.NET Framework Versionen:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3ade2-118">**.NET Framework Versions:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3ade2-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="3ade2-119">See also</span></span>

- [<span data-ttu-id="3ade2-120">ICorDebugVariableHome-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="3ade2-120">ICorDebugVariableHome Interface</span></span>](icordebugvariablehome-interface.md)
- [<span data-ttu-id="3ade2-121">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="3ade2-121">Debugging Interfaces</span></span>](debugging-interfaces.md)
