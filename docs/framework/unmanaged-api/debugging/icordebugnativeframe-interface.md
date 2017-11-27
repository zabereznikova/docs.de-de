---
title: ICorDebugNativeFrame Schnittstelle1
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugNativeFrame
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugNativeFrame
helpviewer_keywords: ICorDebugNativeFrame interface [.NET Framework debugging]
ms.assetid: 04819c58-7246-4b32-befb-680cf1dbc436
topic_type: apiref
caps.latest.revision: "13"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 63d631dec00e63d6ee383cd36d79382a529d9ddb
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugnativeframe-interface1"></a><span data-ttu-id="ada38-102">ICorDebugNativeFrame Schnittstelle1</span><span class="sxs-lookup"><span data-stu-id="ada38-102">ICorDebugNativeFrame Interface1</span></span>
<span data-ttu-id="ada38-103">Eine spezielle Implementierung von ICorDebugFrame für systemeigene Rahmen verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="ada38-103">A specialized implementation of ICorDebugFrame used for native frames.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="ada38-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="ada38-104">Methods</span></span>  
  
|<span data-ttu-id="ada38-105">Methode</span><span class="sxs-lookup"><span data-stu-id="ada38-105">Method</span></span>|<span data-ttu-id="ada38-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="ada38-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="ada38-107">CanSetIP-Methode</span><span class="sxs-lookup"><span data-stu-id="ada38-107">CanSetIP Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugnativeframe-cansetip-method.md)|<span data-ttu-id="ada38-108">Ruft einen Wert, der angibt, ob den Anweisungszeiger auf die angegebene Offsetposition in systemeigenem Code festgelegt werden kann.</span><span class="sxs-lookup"><span data-stu-id="ada38-108">Gets a value that indicates whether it is safe to set the instruction pointer to the specified offset location in native code.</span></span>|  
|[<span data-ttu-id="ada38-109">GetIP-Methode</span><span class="sxs-lookup"><span data-stu-id="ada38-109">GetIP Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugnativeframe-getip-method.md)|<span data-ttu-id="ada38-110">Ruft den Offset des Stapelrahmens in systemeigenen Code ab.</span><span class="sxs-lookup"><span data-stu-id="ada38-110">Gets the stack frame's offset into native code.</span></span>|  
|[<span data-ttu-id="ada38-111">GetLocalDoubleRegisterValue-Methode</span><span class="sxs-lookup"><span data-stu-id="ada38-111">GetLocalDoubleRegisterValue Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugnativeframe-getlocaldoubleregistervalue-method.md)|<span data-ttu-id="ada38-112">Ruft einen Zeiger auf einen ICorDebugValue den Wert eines Arguments oder einer lokalen Variablen in zwei Speicher-Register vom systemeigenen Frames gespeichert.</span><span class="sxs-lookup"><span data-stu-id="ada38-112">Gets a pointer to an ICorDebugValue that represents the value of an argument or local variable stored in two memory registers of a native frame.</span></span>|  
|[<span data-ttu-id="ada38-113">GetLocalMemoryRegisterValue-Methode</span><span class="sxs-lookup"><span data-stu-id="ada38-113">GetLocalMemoryRegisterValue Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugnativeframe-getlocalmemoryregistervalue-method.md)|<span data-ttu-id="ada38-114">Ruft einen Zeiger auf eine `ICorDebugValue` , die den Wert einer lokalen Variablen, von denen die niedrigen Bits im angegebenen Register gespeichert sind, und die oberen Bits an der angegebenen Speicheradresse gespeichert sind darstellt.</span><span class="sxs-lookup"><span data-stu-id="ada38-114">Gets a pointer to an `ICorDebugValue` that represents the value of a local variable, of which the low bits are stored in the specified register and the high bits are stored at the specified memory address.</span></span>|  
|[<span data-ttu-id="ada38-115">GetLocalMemoryValue-Methode</span><span class="sxs-lookup"><span data-stu-id="ada38-115">GetLocalMemoryValue Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugnativeframe-getlocalmemoryvalue-method.md)|<span data-ttu-id="ada38-116">Ruft einen Zeiger auf eine `ICorDebugValue` , die den Wert einer lokalen Variablen, die an der angegebenen Speicheradresse gespeichert darstellt.</span><span class="sxs-lookup"><span data-stu-id="ada38-116">Gets a pointer to an `ICorDebugValue` that represents the value of a local variable stored at the specified memory address.</span></span>|  
|[<span data-ttu-id="ada38-117">GetLocalRegisterMemoryValue-Methode</span><span class="sxs-lookup"><span data-stu-id="ada38-117">GetLocalRegisterMemoryValue Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugnativeframe-getlocalregistermemoryvalue-method.md)|<span data-ttu-id="ada38-118">Ruft einen Zeiger auf ein `ICorDebugValue` , das den Wert einer lokalen Variablen, von denen die oberen Bits im angegebenen Register gespeichert sind, und die niedrigen Bits an der angegebenen Speicheradresse gespeichert sind darstellt.</span><span class="sxs-lookup"><span data-stu-id="ada38-118">Gets a pointer to an `ICorDebugValue` that represents the value of a local variable, of which the high bits are stored in the specified register and the low bits are stored at the specified memory address</span></span>|  
|[<span data-ttu-id="ada38-119">GetLocalRegisterValue-Methode</span><span class="sxs-lookup"><span data-stu-id="ada38-119">GetLocalRegisterValue Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugnativeframe-getlocalregistervalue-method.md)|<span data-ttu-id="ada38-120">Ruft einen Zeiger auf eine `ICorDebugValue` , die den Wert eines Arguments oder einer lokalen Variablen in der angegebenen systemeigenen Register gespeichert darstellt.</span><span class="sxs-lookup"><span data-stu-id="ada38-120">Gets a pointer to an `ICorDebugValue` that represents the value of an argument or a local variable stored in the specified native register.</span></span>|  
|[<span data-ttu-id="ada38-121">GetRegisterSet-Methode</span><span class="sxs-lookup"><span data-stu-id="ada38-121">GetRegisterSet Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugnativeframe-getregisterset-method.md)|<span data-ttu-id="ada38-122">Ruft einen Zeiger auf eine [ICorDebugRegisterSet](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-interface.md) , die den Registersatz dafür darstellt `ICorDebugNativeFrame`.</span><span class="sxs-lookup"><span data-stu-id="ada38-122">Gets a pointer to an [ICorDebugRegisterSet](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-interface.md) that represents the register set for this `ICorDebugNativeFrame`.</span></span>|  
|[<span data-ttu-id="ada38-123">SetIP-Methode</span><span class="sxs-lookup"><span data-stu-id="ada38-123">SetIP Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugnativeframe-setip-method.md)|<span data-ttu-id="ada38-124">Legt den Anweisungszeiger am angegebenen Offset Speicherort in systemeigenem Code.</span><span class="sxs-lookup"><span data-stu-id="ada38-124">Sets the instruction pointer to the specified offset location in native code.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ada38-125">Hinweise</span><span class="sxs-lookup"><span data-stu-id="ada38-125">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="ada38-126">Diese Schnittstelle kann weder computerübergreifend noch prozessübergreifend remote aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="ada38-126">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ada38-127">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="ada38-127">Requirements</span></span>  
 <span data-ttu-id="ada38-128">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ada38-128">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ada38-129">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="ada38-129">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="ada38-130">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ada38-130">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ada38-131">**.NET Framework-Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ada38-131">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ada38-132">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ada38-132">See Also</span></span>  
 [<span data-ttu-id="ada38-133">Debugschnittstellen</span><span class="sxs-lookup"><span data-stu-id="ada38-133">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
