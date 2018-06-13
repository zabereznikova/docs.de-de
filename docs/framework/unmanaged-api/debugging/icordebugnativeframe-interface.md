---
title: ICorDebugNativeFrame Schnittstelle1
ms.date: 03/30/2017
api_name:
- ICorDebugNativeFrame
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugNativeFrame
helpviewer_keywords:
- ICorDebugNativeFrame interface [.NET Framework debugging]
ms.assetid: 04819c58-7246-4b32-befb-680cf1dbc436
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 7996d5800e99d8e6161e24f34604aff3e4e906bd
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33422002"
---
# <a name="icordebugnativeframe-interface1"></a><span data-ttu-id="8696e-102">ICorDebugNativeFrame Schnittstelle1</span><span class="sxs-lookup"><span data-stu-id="8696e-102">ICorDebugNativeFrame Interface1</span></span>
<span data-ttu-id="8696e-103">Eine spezielle Implementierung von ICorDebugFrame für systemeigene Rahmen verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="8696e-103">A specialized implementation of ICorDebugFrame used for native frames.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="8696e-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="8696e-104">Methods</span></span>  
  
|<span data-ttu-id="8696e-105">Methode</span><span class="sxs-lookup"><span data-stu-id="8696e-105">Method</span></span>|<span data-ttu-id="8696e-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="8696e-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="8696e-107">CanSetIP-Methode</span><span class="sxs-lookup"><span data-stu-id="8696e-107">CanSetIP Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugnativeframe-cansetip-method.md)|<span data-ttu-id="8696e-108">Ruft einen Wert, der angibt, ob den Anweisungszeiger auf die angegebene Offsetposition in systemeigenem Code festgelegt werden kann.</span><span class="sxs-lookup"><span data-stu-id="8696e-108">Gets a value that indicates whether it is safe to set the instruction pointer to the specified offset location in native code.</span></span>|  
|[<span data-ttu-id="8696e-109">GetIP-Methode</span><span class="sxs-lookup"><span data-stu-id="8696e-109">GetIP Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugnativeframe-getip-method.md)|<span data-ttu-id="8696e-110">Ruft den Offset des Stapelrahmens in systemeigenen Code ab.</span><span class="sxs-lookup"><span data-stu-id="8696e-110">Gets the stack frame's offset into native code.</span></span>|  
|[<span data-ttu-id="8696e-111">GetLocalDoubleRegisterValue-Methode</span><span class="sxs-lookup"><span data-stu-id="8696e-111">GetLocalDoubleRegisterValue Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugnativeframe-getlocaldoubleregistervalue-method.md)|<span data-ttu-id="8696e-112">Ruft einen Zeiger auf einen ICorDebugValue den Wert eines Arguments oder einer lokalen Variablen in zwei Speicher-Register vom systemeigenen Frames gespeichert.</span><span class="sxs-lookup"><span data-stu-id="8696e-112">Gets a pointer to an ICorDebugValue that represents the value of an argument or local variable stored in two memory registers of a native frame.</span></span>|  
|[<span data-ttu-id="8696e-113">GetLocalMemoryRegisterValue-Methode</span><span class="sxs-lookup"><span data-stu-id="8696e-113">GetLocalMemoryRegisterValue Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugnativeframe-getlocalmemoryregistervalue-method.md)|<span data-ttu-id="8696e-114">Ruft einen Zeiger auf eine `ICorDebugValue` , die den Wert einer lokalen Variablen, von denen die niedrigen Bits im angegebenen Register gespeichert sind, und die oberen Bits an der angegebenen Speicheradresse gespeichert sind darstellt.</span><span class="sxs-lookup"><span data-stu-id="8696e-114">Gets a pointer to an `ICorDebugValue` that represents the value of a local variable, of which the low bits are stored in the specified register and the high bits are stored at the specified memory address.</span></span>|  
|[<span data-ttu-id="8696e-115">GetLocalMemoryValue-Methode</span><span class="sxs-lookup"><span data-stu-id="8696e-115">GetLocalMemoryValue Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugnativeframe-getlocalmemoryvalue-method.md)|<span data-ttu-id="8696e-116">Ruft einen Zeiger auf eine `ICorDebugValue` , die den Wert einer lokalen Variablen, die an der angegebenen Speicheradresse gespeichert darstellt.</span><span class="sxs-lookup"><span data-stu-id="8696e-116">Gets a pointer to an `ICorDebugValue` that represents the value of a local variable stored at the specified memory address.</span></span>|  
|[<span data-ttu-id="8696e-117">GetLocalRegisterMemoryValue-Methode</span><span class="sxs-lookup"><span data-stu-id="8696e-117">GetLocalRegisterMemoryValue Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugnativeframe-getlocalregistermemoryvalue-method.md)|<span data-ttu-id="8696e-118">Ruft einen Zeiger auf ein `ICorDebugValue` , das den Wert einer lokalen Variablen, von denen die oberen Bits im angegebenen Register gespeichert sind, und die niedrigen Bits an der angegebenen Speicheradresse gespeichert sind darstellt.</span><span class="sxs-lookup"><span data-stu-id="8696e-118">Gets a pointer to an `ICorDebugValue` that represents the value of a local variable, of which the high bits are stored in the specified register and the low bits are stored at the specified memory address</span></span>|  
|[<span data-ttu-id="8696e-119">GetLocalRegisterValue-Methode</span><span class="sxs-lookup"><span data-stu-id="8696e-119">GetLocalRegisterValue Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugnativeframe-getlocalregistervalue-method.md)|<span data-ttu-id="8696e-120">Ruft einen Zeiger auf eine `ICorDebugValue` , die den Wert eines Arguments oder einer lokalen Variablen in der angegebenen systemeigenen Register gespeichert darstellt.</span><span class="sxs-lookup"><span data-stu-id="8696e-120">Gets a pointer to an `ICorDebugValue` that represents the value of an argument or a local variable stored in the specified native register.</span></span>|  
|[<span data-ttu-id="8696e-121">GetRegisterSet-Methode</span><span class="sxs-lookup"><span data-stu-id="8696e-121">GetRegisterSet Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugnativeframe-getregisterset-method.md)|<span data-ttu-id="8696e-122">Ruft einen Zeiger auf eine [ICorDebugRegisterSet](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-interface.md) , die den Registersatz dafür darstellt `ICorDebugNativeFrame`.</span><span class="sxs-lookup"><span data-stu-id="8696e-122">Gets a pointer to an [ICorDebugRegisterSet](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-interface.md) that represents the register set for this `ICorDebugNativeFrame`.</span></span>|  
|[<span data-ttu-id="8696e-123">SetIP-Methode</span><span class="sxs-lookup"><span data-stu-id="8696e-123">SetIP Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugnativeframe-setip-method.md)|<span data-ttu-id="8696e-124">Legt den Anweisungszeiger am angegebenen Offset Speicherort in systemeigenem Code.</span><span class="sxs-lookup"><span data-stu-id="8696e-124">Sets the instruction pointer to the specified offset location in native code.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="8696e-125">Hinweise</span><span class="sxs-lookup"><span data-stu-id="8696e-125">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="8696e-126">Diese Schnittstelle kann weder computerübergreifend noch prozessübergreifend remote aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="8696e-126">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8696e-127">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="8696e-127">Requirements</span></span>  
 <span data-ttu-id="8696e-128">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8696e-128">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8696e-129">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="8696e-129">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="8696e-130">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="8696e-130">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="8696e-131">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8696e-131">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8696e-132">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="8696e-132">See Also</span></span>  
 [<span data-ttu-id="8696e-133">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="8696e-133">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
