---
title: ICorDebugNativeFrame-Schnittstelle
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
ms.openlocfilehash: fbdb17bcd502b75da0a73d9a36cf36d6564320bc
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/28/2019
ms.locfileid: "56975484"
---
# <a name="icordebugnativeframe-interface"></a><span data-ttu-id="0e837-102">ICorDebugNativeFrame-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="0e837-102">ICorDebugNativeFrame Interface</span></span>

<span data-ttu-id="0e837-103">Eine spezielle Implementierung der ICorDebugFrame für systemeigene Rahmen verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="0e837-103">A specialized implementation of ICorDebugFrame used for native frames.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="0e837-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="0e837-104">Methods</span></span>  
  
|<span data-ttu-id="0e837-105">Methode</span><span class="sxs-lookup"><span data-stu-id="0e837-105">Method</span></span>|<span data-ttu-id="0e837-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="0e837-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="0e837-107">CanSetIP-Methode</span><span class="sxs-lookup"><span data-stu-id="0e837-107">CanSetIP Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugnativeframe-cansetip-method.md)|<span data-ttu-id="0e837-108">Ruft einen Wert, der angibt, ob den Anweisungszeiger im nativen Code auf die angegebenen Offsetposition festgelegt werden kann.</span><span class="sxs-lookup"><span data-stu-id="0e837-108">Gets a value that indicates whether it is safe to set the instruction pointer to the specified offset location in native code.</span></span>|  
|[<span data-ttu-id="0e837-109">GetIP-Methode</span><span class="sxs-lookup"><span data-stu-id="0e837-109">GetIP Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugnativeframe-getip-method.md)|<span data-ttu-id="0e837-110">Ruft den Offset des Stapelrahmens in nativen Code ab.</span><span class="sxs-lookup"><span data-stu-id="0e837-110">Gets the stack frame's offset into native code.</span></span>|  
|[<span data-ttu-id="0e837-111">GetLocalDoubleRegisterValue-Methode</span><span class="sxs-lookup"><span data-stu-id="0e837-111">GetLocalDoubleRegisterValue Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugnativeframe-getlocaldoubleregistervalue-method.md)|<span data-ttu-id="0e837-112">Ruft einen Zeiger auf ICorDebugValue ab, der den Wert des Arguments oder einer lokalen Variablen gespeichert, die in zwei Speicher-Register, der ein nativer Frame darstellt.</span><span class="sxs-lookup"><span data-stu-id="0e837-112">Gets a pointer to an ICorDebugValue that represents the value of an argument or local variable stored in two memory registers of a native frame.</span></span>|  
|[<span data-ttu-id="0e837-113">GetLocalMemoryRegisterValue-Methode</span><span class="sxs-lookup"><span data-stu-id="0e837-113">GetLocalMemoryRegisterValue Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugnativeframe-getlocalmemoryregistervalue-method.md)|<span data-ttu-id="0e837-114">Ruft einen Zeiger auf ein `ICorDebugValue` , das den Wert einer lokalen Variablen, die die niedrigen Bits im angegebenen Register gespeichert sind, und die oberen Bits werden auf der angegebenen Speicheradresse gespeichert darstellt.</span><span class="sxs-lookup"><span data-stu-id="0e837-114">Gets a pointer to an `ICorDebugValue` that represents the value of a local variable, of which the low bits are stored in the specified register and the high bits are stored at the specified memory address.</span></span>|  
|[<span data-ttu-id="0e837-115">GetLocalMemoryValue-Methode</span><span class="sxs-lookup"><span data-stu-id="0e837-115">GetLocalMemoryValue Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugnativeframe-getlocalmemoryvalue-method.md)|<span data-ttu-id="0e837-116">Ruft einen Zeiger auf ein `ICorDebugValue` , das den Wert einer lokalen Variablen, die an der angegebenen Speicheradresse gespeichert darstellt.</span><span class="sxs-lookup"><span data-stu-id="0e837-116">Gets a pointer to an `ICorDebugValue` that represents the value of a local variable stored at the specified memory address.</span></span>|  
|[<span data-ttu-id="0e837-117">GetLocalRegisterMemoryValue-Methode</span><span class="sxs-lookup"><span data-stu-id="0e837-117">GetLocalRegisterMemoryValue Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugnativeframe-getlocalregistermemoryvalue-method.md)|<span data-ttu-id="0e837-118">Ruft einen Zeiger auf ein `ICorDebugValue` , das den Wert einer lokalen Variablen, die die oberen Bits werden im angegebenen Register gespeichert, und die niedrigen Bits werden auf der angegebenen Speicheradresse gespeichert darstellt.</span><span class="sxs-lookup"><span data-stu-id="0e837-118">Gets a pointer to an `ICorDebugValue` that represents the value of a local variable, of which the high bits are stored in the specified register and the low bits are stored at the specified memory address</span></span>|  
|[<span data-ttu-id="0e837-119">GetLocalRegisterValue-Methode</span><span class="sxs-lookup"><span data-stu-id="0e837-119">GetLocalRegisterValue Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugnativeframe-getlocalregistervalue-method.md)|<span data-ttu-id="0e837-120">Ruft einen Zeiger auf ein `ICorDebugValue` , das den Wert eines Arguments oder eine lokale Variable, die in der angegebenen systemeigenen Register gespeichert darstellt.</span><span class="sxs-lookup"><span data-stu-id="0e837-120">Gets a pointer to an `ICorDebugValue` that represents the value of an argument or a local variable stored in the specified native register.</span></span>|  
|[<span data-ttu-id="0e837-121">GetRegisterSet-Methode</span><span class="sxs-lookup"><span data-stu-id="0e837-121">GetRegisterSet Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugnativeframe-getregisterset-method.md)|<span data-ttu-id="0e837-122">Ruft einen Zeiger auf ein [ICorDebugRegisterSet](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-interface.md) , das darstellt, des Registers, legen Sie für dieses `ICorDebugNativeFrame`.</span><span class="sxs-lookup"><span data-stu-id="0e837-122">Gets a pointer to an [ICorDebugRegisterSet](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-interface.md) that represents the register set for this `ICorDebugNativeFrame`.</span></span>|  
|[<span data-ttu-id="0e837-123">SetIP-Methode</span><span class="sxs-lookup"><span data-stu-id="0e837-123">SetIP Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugnativeframe-setip-method.md)|<span data-ttu-id="0e837-124">Legt den Anweisungszeiger auf die angegebenen Offsetposition in systemeigenem Code fest.</span><span class="sxs-lookup"><span data-stu-id="0e837-124">Sets the instruction pointer to the specified offset location in native code.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0e837-125">Hinweise</span><span class="sxs-lookup"><span data-stu-id="0e837-125">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="0e837-126">Diese Schnittstelle kann weder computerübergreifend noch prozessübergreifend remote aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="0e837-126">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0e837-127">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="0e837-127">Requirements</span></span>  
 <span data-ttu-id="0e837-128">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0e837-128">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0e837-129">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="0e837-129">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="0e837-130">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="0e837-130">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="0e837-131">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0e837-131">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0e837-132">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="0e837-132">See also</span></span>
- [<span data-ttu-id="0e837-133">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="0e837-133">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
