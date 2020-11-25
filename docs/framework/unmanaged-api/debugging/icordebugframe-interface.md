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
ms.openlocfilehash: bdc17e2c6c63deae1420fe738eac51153f6b368e
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95726339"
---
# <a name="icordebugframe-interface"></a><span data-ttu-id="fd3d7-102">ICorDebugFrame-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="fd3d7-102">ICorDebugFrame Interface</span></span>

<span data-ttu-id="fd3d7-103">Stellt einen Rahmen auf dem aktuellen Stapel dar.</span><span class="sxs-lookup"><span data-stu-id="fd3d7-103">Represents a frame on the current stack.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="fd3d7-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="fd3d7-104">Methods</span></span>  
  
|<span data-ttu-id="fd3d7-105">Methode</span><span class="sxs-lookup"><span data-stu-id="fd3d7-105">Method</span></span>|<span data-ttu-id="fd3d7-106">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="fd3d7-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="fd3d7-107">CreateStepper-Methode</span><span class="sxs-lookup"><span data-stu-id="fd3d7-107">CreateStepper Method</span></span>](icordebugframe-createstepper-method.md)|<span data-ttu-id="fd3d7-108">Ruft einen ICorDebugStepper ab, um schrittweise Vorgänge in Bezug auf diesen auszuführen `ICorDebugFrame` .</span><span class="sxs-lookup"><span data-stu-id="fd3d7-108">Gets an ICorDebugStepper to perform stepping operations relative to this `ICorDebugFrame`.</span></span>|  
|[<span data-ttu-id="fd3d7-109">GetCallee-Methode</span><span class="sxs-lookup"><span data-stu-id="fd3d7-109">GetCallee Method</span></span>](icordebugframe-getcallee-method.md)|<span data-ttu-id="fd3d7-110">Ruft einen Zeiger auf den `ICorDebugFrame` in der aktuellen Kette ab, den dieser Frame aufrief, oder gibt NULL zurück, wenn dies der innerste Frame in der Kette ist.</span><span class="sxs-lookup"><span data-stu-id="fd3d7-110">Gets a pointer to the `ICorDebugFrame` in the current chain that this frame called, or returns null if this is the innermost frame in the chain.</span></span>|  
|[<span data-ttu-id="fd3d7-111">GetCaller-Methode</span><span class="sxs-lookup"><span data-stu-id="fd3d7-111">GetCaller Method</span></span>](icordebugframe-getcaller-method.md)|<span data-ttu-id="fd3d7-112">Ruft einen Zeiger auf den `ICorDebugFrame` in der aktuellen Kette ab, der diesen Frame aufgerufen hat, oder gibt NULL zurück, wenn dies der äußerste Frame in der Kette ist.</span><span class="sxs-lookup"><span data-stu-id="fd3d7-112">Gets a pointer to the `ICorDebugFrame` in the current chain that called this frame, or returns null if this is the outermost frame in the chain.</span></span>|  
|[<span data-ttu-id="fd3d7-113">GetChain-Methode</span><span class="sxs-lookup"><span data-stu-id="fd3d7-113">GetChain Method</span></span>](icordebugframe-getchain-method.md)|<span data-ttu-id="fd3d7-114">Ruft einen Zeiger auf die ICorDebug-Kette ab, zu `ICorDebugFrame` der gehört.</span><span class="sxs-lookup"><span data-stu-id="fd3d7-114">Gets a pointer to the ICorDebugChain this `ICorDebugFrame` is a part of.</span></span>|  
|[<span data-ttu-id="fd3d7-115">GetCode-Methode</span><span class="sxs-lookup"><span data-stu-id="fd3d7-115">GetCode Method</span></span>](icordebugframe-getcode-method.md)|<span data-ttu-id="fd3d7-116">Ruft einen Zeiger auf den ICorDebugCode ab, der diesem Stapel Rahmen zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="fd3d7-116">Gets a pointer to the ICorDebugCode associated with this stack frame.</span></span>|  
|[<span data-ttu-id="fd3d7-117">GetFunction-Methode</span><span class="sxs-lookup"><span data-stu-id="fd3d7-117">GetFunction Method</span></span>](icordebugframe-getfunction-method.md)|<span data-ttu-id="fd3d7-118">Ruft einen Zeiger auf die ICorDebugFunction ab, die den Code enthält, der diesem Stapel Rahmen zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="fd3d7-118">Gets a pointer to the ICorDebugFunction that contains the code associated with this stack frame.</span></span>|  
|[<span data-ttu-id="fd3d7-119">GetFunctionToken-Methode</span><span class="sxs-lookup"><span data-stu-id="fd3d7-119">GetFunctionToken Method</span></span>](icordebugframe-getfunctiontoken-method.md)|<span data-ttu-id="fd3d7-120">Ruft das Metadatentoken für die Funktion ab, die den Code enthält, der diesem Stapel Rahmen zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="fd3d7-120">Gets the metadata token for the function that contains the code associated with this stack frame.</span></span>|  
|[<span data-ttu-id="fd3d7-121">GetStackRange-Methode</span><span class="sxs-lookup"><span data-stu-id="fd3d7-121">GetStackRange Method</span></span>](icordebugframe-getstackrange-method.md)|<span data-ttu-id="fd3d7-122">Ruft den absoluten Adressbereich des Stapel Rahmens ab, der von diesem dargestellt wird `ICorDebugFrame` .</span><span class="sxs-lookup"><span data-stu-id="fd3d7-122">Gets the absolute address range of the stack frame represented by this `ICorDebugFrame`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="fd3d7-123">Hinweise</span><span class="sxs-lookup"><span data-stu-id="fd3d7-123">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="fd3d7-124">Diese Schnittstelle kann weder computerübergreifend noch prozessübergreifend remote aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="fd3d7-124">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fd3d7-125">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="fd3d7-125">Requirements</span></span>  

 <span data-ttu-id="fd3d7-126">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="fd3d7-126">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fd3d7-127">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="fd3d7-127">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="fd3d7-128">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="fd3d7-128">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="fd3d7-129">**.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fd3d7-129">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fd3d7-130">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="fd3d7-130">See also</span></span>

- [<span data-ttu-id="fd3d7-131">Debugschnittstellen</span><span class="sxs-lookup"><span data-stu-id="fd3d7-131">Debugging Interfaces</span></span>](debugging-interfaces.md)
