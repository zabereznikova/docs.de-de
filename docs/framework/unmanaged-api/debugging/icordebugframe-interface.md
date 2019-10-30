---
title: ICorDebugFrame-Schnittstelle
ms.date: 03/30/2017
api_name:
- ICorDebugFrame
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugFrame
helpviewer_keywords:
- ICorDebugFrame interface [.NET Framework debugging]
ms.assetid: 0c48f764-3c64-4602-b2f4-4ffc60eb2c65
topic_type:
- apiref
ms.openlocfilehash: 5aeea11b7e61869968aafe3425e27d6004f495ea
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73124075"
---
# <a name="icordebugframe-interface"></a><span data-ttu-id="af0b3-102">ICorDebugFrame-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="af0b3-102">ICorDebugFrame Interface</span></span>

<span data-ttu-id="af0b3-103">Stellt einen Rahmen auf dem aktuellen Stapel dar.</span><span class="sxs-lookup"><span data-stu-id="af0b3-103">Represents a frame on the current stack.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="af0b3-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="af0b3-104">Methods</span></span>  
  
|<span data-ttu-id="af0b3-105">Methode</span><span class="sxs-lookup"><span data-stu-id="af0b3-105">Method</span></span>|<span data-ttu-id="af0b3-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="af0b3-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="af0b3-107">CreateStepper-Methode</span><span class="sxs-lookup"><span data-stu-id="af0b3-107">CreateStepper Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugframe-createstepper-method.md)|<span data-ttu-id="af0b3-108">Ruft ein ICorDebugStepper-Element ab, um schrittweise Vorgänge in Relation zu diesem `ICorDebugFrame`auszuführen.</span><span class="sxs-lookup"><span data-stu-id="af0b3-108">Gets an ICorDebugStepper to perform stepping operations relative to this `ICorDebugFrame`.</span></span>|  
|[<span data-ttu-id="af0b3-109">GetCallee-Methode</span><span class="sxs-lookup"><span data-stu-id="af0b3-109">GetCallee Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugframe-getcallee-method.md)|<span data-ttu-id="af0b3-110">Ruft einen Zeiger auf den `ICorDebugFrame` in der aktuellen Kette ab, den dieser Frame aufrief, oder gibt NULL zurück, wenn dies der innerste Frame in der Kette ist.</span><span class="sxs-lookup"><span data-stu-id="af0b3-110">Gets a pointer to the `ICorDebugFrame` in the current chain that this frame called, or returns null if this is the innermost frame in the chain.</span></span>|  
|[<span data-ttu-id="af0b3-111">GetCaller-Methode</span><span class="sxs-lookup"><span data-stu-id="af0b3-111">GetCaller Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugframe-getcaller-method.md)|<span data-ttu-id="af0b3-112">Ruft einen Zeiger auf den `ICorDebugFrame` in der aktuellen Kette ab, der diesen Frame aufgerufen hat, oder gibt NULL zurück, wenn dies der äußerste Frame in der Kette ist.</span><span class="sxs-lookup"><span data-stu-id="af0b3-112">Gets a pointer to the `ICorDebugFrame` in the current chain that called this frame, or returns null if this is the outermost frame in the chain.</span></span>|  
|[<span data-ttu-id="af0b3-113">GetChain-Methode</span><span class="sxs-lookup"><span data-stu-id="af0b3-113">GetChain Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugframe-getchain-method.md)|<span data-ttu-id="af0b3-114">Ruft einen Zeiger auf die ICorDebug-Kette ab, zu der dieser `ICorDebugFrame` gehört.</span><span class="sxs-lookup"><span data-stu-id="af0b3-114">Gets a pointer to the ICorDebugChain this `ICorDebugFrame` is a part of.</span></span>|  
|[<span data-ttu-id="af0b3-115">GetCode-Methode</span><span class="sxs-lookup"><span data-stu-id="af0b3-115">GetCode Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugframe-getcode-method.md)|<span data-ttu-id="af0b3-116">Ruft einen Zeiger auf den ICorDebugCode ab, der diesem Stapel Rahmen zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="af0b3-116">Gets a pointer to the ICorDebugCode associated with this stack frame.</span></span>|  
|[<span data-ttu-id="af0b3-117">GetFunction-Methode</span><span class="sxs-lookup"><span data-stu-id="af0b3-117">GetFunction Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugframe-getfunction-method.md)|<span data-ttu-id="af0b3-118">Ruft einen Zeiger auf die ICorDebugFunction ab, die den Code enthält, der diesem Stapel Rahmen zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="af0b3-118">Gets a pointer to the ICorDebugFunction that contains the code associated with this stack frame.</span></span>|  
|[<span data-ttu-id="af0b3-119">GetFunctionToken-Methode</span><span class="sxs-lookup"><span data-stu-id="af0b3-119">GetFunctionToken Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugframe-getfunctiontoken-method.md)|<span data-ttu-id="af0b3-120">Ruft das Metadatentoken für die Funktion ab, die den Code enthält, der diesem Stapel Rahmen zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="af0b3-120">Gets the metadata token for the function that contains the code associated with this stack frame.</span></span>|  
|[<span data-ttu-id="af0b3-121">GetStackRange-Methode</span><span class="sxs-lookup"><span data-stu-id="af0b3-121">GetStackRange Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugframe-getstackrange-method.md)|<span data-ttu-id="af0b3-122">Ruft den absoluten Adressbereich des von diesem `ICorDebugFrame`dargestellten Stapel Rahmens ab.</span><span class="sxs-lookup"><span data-stu-id="af0b3-122">Gets the absolute address range of the stack frame represented by this `ICorDebugFrame`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="af0b3-123">Hinweise</span><span class="sxs-lookup"><span data-stu-id="af0b3-123">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="af0b3-124">Diese Schnittstelle kann weder computerübergreifend noch prozessübergreifend remote aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="af0b3-124">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="af0b3-125">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="af0b3-125">Requirements</span></span>  
 <span data-ttu-id="af0b3-126">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="af0b3-126">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="af0b3-127">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="af0b3-127">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="af0b3-128">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="af0b3-128">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="af0b3-129">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="af0b3-129">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="af0b3-130">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="af0b3-130">See also</span></span>

- [<span data-ttu-id="af0b3-131">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="af0b3-131">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
