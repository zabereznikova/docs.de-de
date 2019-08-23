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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: d4744ea67d0ce0d9ad2b13c45bdef65f884ef925
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69937008"
---
# <a name="icordebugframe-interface"></a><span data-ttu-id="b3273-102">ICorDebugFrame-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="b3273-102">ICorDebugFrame Interface</span></span>

<span data-ttu-id="b3273-103">Stellt einen Rahmen auf dem aktuellen Stapel dar.</span><span class="sxs-lookup"><span data-stu-id="b3273-103">Represents a frame on the current stack.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="b3273-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="b3273-104">Methods</span></span>  
  
|<span data-ttu-id="b3273-105">Methode</span><span class="sxs-lookup"><span data-stu-id="b3273-105">Method</span></span>|<span data-ttu-id="b3273-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="b3273-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="b3273-107">CreateStepper-Methode</span><span class="sxs-lookup"><span data-stu-id="b3273-107">CreateStepper Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugframe-createstepper-method.md)|<span data-ttu-id="b3273-108">Ruft einen ICorDebugStepper ab, um schrittweise Vorgänge in `ICorDebugFrame`Bezug auf diesen auszuführen.</span><span class="sxs-lookup"><span data-stu-id="b3273-108">Gets an ICorDebugStepper to perform stepping operations relative to this `ICorDebugFrame`.</span></span>|  
|[<span data-ttu-id="b3273-109">GetCallee-Methode</span><span class="sxs-lookup"><span data-stu-id="b3273-109">GetCallee Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugframe-getcallee-method.md)|<span data-ttu-id="b3273-110">Ruft einen Zeiger auf den `ICorDebugFrame` in der aktuellen Kette ab, den dieser Frame aufrief, oder gibt NULL zurück, wenn dies der innerste Frame in der Kette ist.</span><span class="sxs-lookup"><span data-stu-id="b3273-110">Gets a pointer to the `ICorDebugFrame` in the current chain that this frame called, or returns null if this is the innermost frame in the chain.</span></span>|  
|[<span data-ttu-id="b3273-111">GetCaller-Methode</span><span class="sxs-lookup"><span data-stu-id="b3273-111">GetCaller Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugframe-getcaller-method.md)|<span data-ttu-id="b3273-112">Ruft einen Zeiger auf den `ICorDebugFrame` in der aktuellen Kette ab, der diesen Frame aufgerufen hat, oder gibt NULL zurück, wenn dies der äußerste Frame in der Kette ist.</span><span class="sxs-lookup"><span data-stu-id="b3273-112">Gets a pointer to the `ICorDebugFrame` in the current chain that called this frame, or returns null if this is the outermost frame in the chain.</span></span>|  
|[<span data-ttu-id="b3273-113">GetChain-Methode</span><span class="sxs-lookup"><span data-stu-id="b3273-113">GetChain Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugframe-getchain-method.md)|<span data-ttu-id="b3273-114">Ruft einen Zeiger auf die ICorDebug-Kette `ICorDebugFrame` ab, zu der gehört.</span><span class="sxs-lookup"><span data-stu-id="b3273-114">Gets a pointer to the ICorDebugChain this `ICorDebugFrame` is a part of.</span></span>|  
|[<span data-ttu-id="b3273-115">GetCode-Methode</span><span class="sxs-lookup"><span data-stu-id="b3273-115">GetCode Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugframe-getcode-method.md)|<span data-ttu-id="b3273-116">Ruft einen Zeiger auf den ICorDebugCode ab, der diesem Stapel Rahmen zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="b3273-116">Gets a pointer to the ICorDebugCode associated with this stack frame.</span></span>|  
|[<span data-ttu-id="b3273-117">GetFunction-Methode</span><span class="sxs-lookup"><span data-stu-id="b3273-117">GetFunction Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugframe-getfunction-method.md)|<span data-ttu-id="b3273-118">Ruft einen Zeiger auf die ICorDebugFunction ab, die den Code enthält, der diesem Stapel Rahmen zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="b3273-118">Gets a pointer to the ICorDebugFunction that contains the code associated with this stack frame.</span></span>|  
|[<span data-ttu-id="b3273-119">GetFunctionToken-Methode</span><span class="sxs-lookup"><span data-stu-id="b3273-119">GetFunctionToken Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugframe-getfunctiontoken-method.md)|<span data-ttu-id="b3273-120">Ruft das Metadatentoken für die Funktion ab, die den Code enthält, der diesem Stapel Rahmen zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="b3273-120">Gets the metadata token for the function that contains the code associated with this stack frame.</span></span>|  
|[<span data-ttu-id="b3273-121">GetStackRange-Methode</span><span class="sxs-lookup"><span data-stu-id="b3273-121">GetStackRange Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugframe-getstackrange-method.md)|<span data-ttu-id="b3273-122">Ruft den absoluten Adressbereich des Stapel Rahmens ab, der von `ICorDebugFrame`diesem dargestellt wird.</span><span class="sxs-lookup"><span data-stu-id="b3273-122">Gets the absolute address range of the stack frame represented by this `ICorDebugFrame`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b3273-123">Hinweise</span><span class="sxs-lookup"><span data-stu-id="b3273-123">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="b3273-124">Diese Schnittstelle kann weder computerübergreifend noch prozessübergreifend remote aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="b3273-124">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b3273-125">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="b3273-125">Requirements</span></span>  
 <span data-ttu-id="b3273-126">**Formen** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b3273-126">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b3273-127">**Header:** Cordebug. idl, Cordebug. h</span><span class="sxs-lookup"><span data-stu-id="b3273-127">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="b3273-128">**Fern** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b3273-128">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b3273-129">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b3273-129">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b3273-130">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b3273-130">See also</span></span>

- [<span data-ttu-id="b3273-131">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="b3273-131">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
