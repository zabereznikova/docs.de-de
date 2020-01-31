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
ms.openlocfilehash: 41ac0b29ade2f78b893df72e8a17624373f6dd78
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/28/2020
ms.locfileid: "76792791"
---
# <a name="icordebugnativeframe-interface"></a><span data-ttu-id="2fdfd-102">ICorDebugNativeFrame-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="2fdfd-102">ICorDebugNativeFrame Interface</span></span>

<span data-ttu-id="2fdfd-103">Eine spezielle Implementierung von ICorDebug Frame, die für Native Frames verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="2fdfd-103">A specialized implementation of ICorDebugFrame used for native frames.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="2fdfd-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="2fdfd-104">Methods</span></span>  
  
|<span data-ttu-id="2fdfd-105">-Methode</span><span class="sxs-lookup"><span data-stu-id="2fdfd-105">Method</span></span>|<span data-ttu-id="2fdfd-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="2fdfd-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="2fdfd-107">CanSetIP-Methode</span><span class="sxs-lookup"><span data-stu-id="2fdfd-107">CanSetIP Method</span></span>](icordebugnativeframe-cansetip-method.md)|<span data-ttu-id="2fdfd-108">Ruft einen Wert ab, der angibt, ob es sicher ist, den Anweisungs Zeiger auf die angegebene Offset Position in nativem Code festzulegen.</span><span class="sxs-lookup"><span data-stu-id="2fdfd-108">Gets a value that indicates whether it is safe to set the instruction pointer to the specified offset location in native code.</span></span>|  
|[<span data-ttu-id="2fdfd-109">GetIP-Methode</span><span class="sxs-lookup"><span data-stu-id="2fdfd-109">GetIP Method</span></span>](icordebugnativeframe-getip-method.md)|<span data-ttu-id="2fdfd-110">Ruft den Offset des Stapel Rahmens in systemeigenen Code ab.</span><span class="sxs-lookup"><span data-stu-id="2fdfd-110">Gets the stack frame's offset into native code.</span></span>|  
|[<span data-ttu-id="2fdfd-111">GetLocalDoubleRegisterValue-Methode</span><span class="sxs-lookup"><span data-stu-id="2fdfd-111">GetLocalDoubleRegisterValue Method</span></span>](icordebugnativeframe-getlocaldoubleregistervalue-method.md)|<span data-ttu-id="2fdfd-112">Ruft einen Zeiger auf einen ICorDebug-Wert ab, der den Wert eines Arguments oder einer lokalen Variablen darstellt, die in zwei Speicher Registern eines systemeigenen Frames gespeichert ist.</span><span class="sxs-lookup"><span data-stu-id="2fdfd-112">Gets a pointer to an ICorDebugValue that represents the value of an argument or local variable stored in two memory registers of a native frame.</span></span>|  
|[<span data-ttu-id="2fdfd-113">GetLocalMemoryRegisterValue-Methode</span><span class="sxs-lookup"><span data-stu-id="2fdfd-113">GetLocalMemoryRegisterValue Method</span></span>](icordebugnativeframe-getlocalmemoryregistervalue-method.md)|<span data-ttu-id="2fdfd-114">Ruft einen Zeiger auf einen `ICorDebugValue` ab, der den Wert einer lokalen Variablen darstellt, von der die unteren Bits im angegebenen Register gespeichert werden und die hohen Bits an der angegebenen Speicheradresse gespeichert werden.</span><span class="sxs-lookup"><span data-stu-id="2fdfd-114">Gets a pointer to an `ICorDebugValue` that represents the value of a local variable, of which the low bits are stored in the specified register and the high bits are stored at the specified memory address.</span></span>|  
|[<span data-ttu-id="2fdfd-115">GetLocalMemoryValue-Methode</span><span class="sxs-lookup"><span data-stu-id="2fdfd-115">GetLocalMemoryValue Method</span></span>](icordebugnativeframe-getlocalmemoryvalue-method.md)|<span data-ttu-id="2fdfd-116">Ruft einen Zeiger auf einen `ICorDebugValue` ab, der den Wert einer lokalen Variablen darstellt, die an der angegebenen Speicheradresse gespeichert ist.</span><span class="sxs-lookup"><span data-stu-id="2fdfd-116">Gets a pointer to an `ICorDebugValue` that represents the value of a local variable stored at the specified memory address.</span></span>|  
|[<span data-ttu-id="2fdfd-117">GetLocalRegisterMemoryValue-Methode</span><span class="sxs-lookup"><span data-stu-id="2fdfd-117">GetLocalRegisterMemoryValue Method</span></span>](icordebugnativeframe-getlocalregistermemoryvalue-method.md)|<span data-ttu-id="2fdfd-118">Ruft einen Zeiger auf einen `ICorDebugValue` ab, der den Wert einer lokalen Variablen darstellt, von der die hohen Bits im angegebenen Register gespeichert werden und die unteren Bits an der angegebenen Speicheradresse gespeichert werden.</span><span class="sxs-lookup"><span data-stu-id="2fdfd-118">Gets a pointer to an `ICorDebugValue` that represents the value of a local variable, of which the high bits are stored in the specified register and the low bits are stored at the specified memory address</span></span>|  
|[<span data-ttu-id="2fdfd-119">GetLocalRegisterValue-Methode</span><span class="sxs-lookup"><span data-stu-id="2fdfd-119">GetLocalRegisterValue Method</span></span>](icordebugnativeframe-getlocalregistervalue-method.md)|<span data-ttu-id="2fdfd-120">Ruft einen Zeiger auf einen `ICorDebugValue` ab, der den Wert eines Arguments oder eine lokale Variable darstellt, die im angegebenen systemeigenen Register gespeichert ist.</span><span class="sxs-lookup"><span data-stu-id="2fdfd-120">Gets a pointer to an `ICorDebugValue` that represents the value of an argument or a local variable stored in the specified native register.</span></span>|  
|[<span data-ttu-id="2fdfd-121">GetRegisterSet-Methode</span><span class="sxs-lookup"><span data-stu-id="2fdfd-121">GetRegisterSet Method</span></span>](icordebugnativeframe-getregisterset-method.md)|<span data-ttu-id="2fdfd-122">Ruft einen Zeiger auf ein [ICorDebugRegisterSet](icordebugregisterset-interface.md) ab, das den Register Satz für dieses `ICorDebugNativeFrame`darstellt.</span><span class="sxs-lookup"><span data-stu-id="2fdfd-122">Gets a pointer to an [ICorDebugRegisterSet](icordebugregisterset-interface.md) that represents the register set for this `ICorDebugNativeFrame`.</span></span>|  
|[<span data-ttu-id="2fdfd-123">SetIP-Methode</span><span class="sxs-lookup"><span data-stu-id="2fdfd-123">SetIP Method</span></span>](icordebugnativeframe-setip-method.md)|<span data-ttu-id="2fdfd-124">Legt den Anweisungs Zeiger auf die angegebene Offset Position in nativem Code fest.</span><span class="sxs-lookup"><span data-stu-id="2fdfd-124">Sets the instruction pointer to the specified offset location in native code.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2fdfd-125">Hinweise</span><span class="sxs-lookup"><span data-stu-id="2fdfd-125">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="2fdfd-126">Diese Schnittstelle kann weder computerübergreifend noch prozessübergreifend remote aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="2fdfd-126">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2fdfd-127">-Anforderungen</span><span class="sxs-lookup"><span data-stu-id="2fdfd-127">Requirements</span></span>  
 <span data-ttu-id="2fdfd-128">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2fdfd-128">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2fdfd-129">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="2fdfd-129">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="2fdfd-130">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2fdfd-130">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2fdfd-131">**.NET Framework Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2fdfd-131">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2fdfd-132">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="2fdfd-132">See also</span></span>

- [<span data-ttu-id="2fdfd-133">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="2fdfd-133">Debugging Interfaces</span></span>](debugging-interfaces.md)
