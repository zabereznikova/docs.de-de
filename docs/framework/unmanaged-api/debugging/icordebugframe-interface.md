---
title: ICorDebugFrame-Schnittstelle1
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
ms.openlocfilehash: 7f160612e499ca7bd2185c95aa07a3784c5a4a19
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54635753"
---
# <a name="icordebugframe-interface1"></a><span data-ttu-id="ca256-102">ICorDebugFrame-Schnittstelle1</span><span class="sxs-lookup"><span data-stu-id="ca256-102">ICorDebugFrame Interface1</span></span>
<span data-ttu-id="ca256-103">Stellt einen Rahmen auf dem aktuellen Stapel dar.</span><span class="sxs-lookup"><span data-stu-id="ca256-103">Represents a frame on the current stack.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="ca256-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="ca256-104">Methods</span></span>  
  
|<span data-ttu-id="ca256-105">Methode</span><span class="sxs-lookup"><span data-stu-id="ca256-105">Method</span></span>|<span data-ttu-id="ca256-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="ca256-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="ca256-107">CreateStepper-Methode</span><span class="sxs-lookup"><span data-stu-id="ca256-107">CreateStepper Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugframe-createstepper-method.md)|<span data-ttu-id="ca256-108">Ruft eine ICorDebugStepper relativ zu diesem schrittweisen Operationen `ICorDebugFrame`.</span><span class="sxs-lookup"><span data-stu-id="ca256-108">Gets an ICorDebugStepper to perform stepping operations relative to this `ICorDebugFrame`.</span></span>|  
|[<span data-ttu-id="ca256-109">GetCallee-Methode</span><span class="sxs-lookup"><span data-stu-id="ca256-109">GetCallee Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugframe-getcallee-method.md)|<span data-ttu-id="ca256-110">Ruft einen Zeiger auf die `ICorDebugFrame` in der aktuellen Kette, in denen dieses Bild aufgerufen, oder Null zurück, wenn diese die innerste Rahmen in der Kette.</span><span class="sxs-lookup"><span data-stu-id="ca256-110">Gets a pointer to the `ICorDebugFrame` in the current chain that this frame called, or returns null if this is the innermost frame in the chain.</span></span>|  
|[<span data-ttu-id="ca256-111">GetCaller-Methode</span><span class="sxs-lookup"><span data-stu-id="ca256-111">GetCaller Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugframe-getcaller-method.md)|<span data-ttu-id="ca256-112">Ruft einen Zeiger auf die `ICorDebugFrame` in der aktuellen Kette, die diesem Frame aufgerufen werden soll, oder Null zurück, wenn diese ist der äußerste Frame in der Kette.</span><span class="sxs-lookup"><span data-stu-id="ca256-112">Gets a pointer to the `ICorDebugFrame` in the current chain that called this frame, or returns null if this is the outermost frame in the chain.</span></span>|  
|[<span data-ttu-id="ca256-113">GetChain-Methode</span><span class="sxs-lookup"><span data-stu-id="ca256-113">GetChain Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugframe-getchain-method.md)|<span data-ttu-id="ca256-114">Ruft einem Zeiger auf die ICorDebugChain dies `ICorDebugFrame` gehört.</span><span class="sxs-lookup"><span data-stu-id="ca256-114">Gets a pointer to the ICorDebugChain this `ICorDebugFrame` is a part of.</span></span>|  
|[<span data-ttu-id="ca256-115">GetCode-Methode</span><span class="sxs-lookup"><span data-stu-id="ca256-115">GetCode Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugframe-getcode-method.md)|<span data-ttu-id="ca256-116">Ruft einen Zeiger auf den ICorDebugCode, die diesen Stapelrahmen zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="ca256-116">Gets a pointer to the ICorDebugCode associated with this stack frame.</span></span>|  
|[<span data-ttu-id="ca256-117">GetFunction-Methode</span><span class="sxs-lookup"><span data-stu-id="ca256-117">GetFunction Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugframe-getfunction-method.md)|<span data-ttu-id="ca256-118">Ruft einen Zeiger auf die ICorDebugFunction ab, die den Code für diesen Stapelrahmen enthält.</span><span class="sxs-lookup"><span data-stu-id="ca256-118">Gets a pointer to the ICorDebugFunction that contains the code associated with this stack frame.</span></span>|  
|[<span data-ttu-id="ca256-119">GetFunctionToken-Methode</span><span class="sxs-lookup"><span data-stu-id="ca256-119">GetFunctionToken Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugframe-getfunctiontoken-method.md)|<span data-ttu-id="ca256-120">Ruft das Metadatentoken für die Funktion, die den Code für diesen Stapelrahmen enthält.</span><span class="sxs-lookup"><span data-stu-id="ca256-120">Gets the metadata token for the function that contains the code associated with this stack frame.</span></span>|  
|[<span data-ttu-id="ca256-121">GetStackRange-Methode</span><span class="sxs-lookup"><span data-stu-id="ca256-121">GetStackRange Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugframe-getstackrange-method.md)|<span data-ttu-id="ca256-122">Ruft den Bereich der absoluten Adresse des Stapelrahmens dargestellt durch diese `ICorDebugFrame`.</span><span class="sxs-lookup"><span data-stu-id="ca256-122">Gets the absolute address range of the stack frame represented by this `ICorDebugFrame`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ca256-123">Hinweise</span><span class="sxs-lookup"><span data-stu-id="ca256-123">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="ca256-124">Diese Schnittstelle kann weder computerübergreifend noch prozessübergreifend remote aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="ca256-124">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ca256-125">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="ca256-125">Requirements</span></span>  
 <span data-ttu-id="ca256-126">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ca256-126">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ca256-127">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="ca256-127">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="ca256-128">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ca256-128">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ca256-129">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ca256-129">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ca256-130">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ca256-130">See also</span></span>
- [<span data-ttu-id="ca256-131">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="ca256-131">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
