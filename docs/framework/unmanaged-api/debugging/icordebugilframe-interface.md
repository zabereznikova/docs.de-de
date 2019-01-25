---
title: ICorDebugILFrame-Schnittstelle1
ms.date: 03/30/2017
api_name:
- ICorDebugILFrame
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugILFrame
helpviewer_keywords:
- ICorDebugILFrame interface [.NET Framework debugging]
ms.assetid: d5cf5056-da4d-4629-914d-afe42a5393df
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 73cf7f26b228fa5aa458a6de312df3bf777e0206
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54580511"
---
# <a name="icordebugilframe-interface1"></a><span data-ttu-id="33e72-102">ICorDebugILFrame-Schnittstelle1</span><span class="sxs-lookup"><span data-stu-id="33e72-102">ICorDebugILFrame Interface1</span></span>
<span data-ttu-id="33e72-103">Stellt einen Stapelrahmen des Microsoft intermediate Language (MSIL)-Code dar.</span><span class="sxs-lookup"><span data-stu-id="33e72-103">Represents a stack frame of Microsoft intermediate language (MSIL) code.</span></span> <span data-ttu-id="33e72-104">Diese Schnittstelle ist eine Unterklasse der ICorDebugFrame-Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="33e72-104">This interface is a subclass of the ICorDebugFrame interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="33e72-105">Methoden</span><span class="sxs-lookup"><span data-stu-id="33e72-105">Methods</span></span>  
  
|<span data-ttu-id="33e72-106">Methode</span><span class="sxs-lookup"><span data-stu-id="33e72-106">Method</span></span>|<span data-ttu-id="33e72-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="33e72-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="33e72-108">CanSetIP-Methode</span><span class="sxs-lookup"><span data-stu-id="33e72-108">CanSetIP Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe-cansetip-method.md)|<span data-ttu-id="33e72-109">Ruft einen Wert, der angibt, ob der Anweisungszeiger sich am angegebenen Offset Speicherort festgelegt werden kann.</span><span class="sxs-lookup"><span data-stu-id="33e72-109">Gets a value that indicates whether it is safe to set the instruction pointer to the specified offset location.</span></span>|  
|[<span data-ttu-id="33e72-110">EnumerateArguments-Methode</span><span class="sxs-lookup"><span data-stu-id="33e72-110">EnumerateArguments Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe-enumeratearguments-method.md)|<span data-ttu-id="33e72-111">Ruft einen Enumerator für die Argumente in diesem Frame ab.</span><span class="sxs-lookup"><span data-stu-id="33e72-111">Gets an enumerator for the arguments in this frame.</span></span>|  
|[<span data-ttu-id="33e72-112">EnumerateLocalVariables-Methode</span><span class="sxs-lookup"><span data-stu-id="33e72-112">EnumerateLocalVariables Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe-enumeratelocalvariables-method.md)|<span data-ttu-id="33e72-113">Ruft einen Enumerator für die lokalen Variablen in diesem Frame ab.</span><span class="sxs-lookup"><span data-stu-id="33e72-113">Gets an enumerator for the local variables in this frame.</span></span>|  
|[<span data-ttu-id="33e72-114">GetArgument-Methode</span><span class="sxs-lookup"><span data-stu-id="33e72-114">GetArgument Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe-getargument-method.md)|<span data-ttu-id="33e72-115">Ruft den Wert des angegebenen Arguments in MSIL-Stapelrahmens ab.</span><span class="sxs-lookup"><span data-stu-id="33e72-115">Gets the value of the specified argument in this MSIL stack frame.</span></span>|  
|[<span data-ttu-id="33e72-116">GetIP-Methode</span><span class="sxs-lookup"><span data-stu-id="33e72-116">GetIP Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe-getip-method.md)|<span data-ttu-id="33e72-117">Ruft den Wert des Anweisungszeigers und eine bitweise Kombination-Wert, der beschreibt, wie der Wert des Anweisungszeigers abgerufen wurde.</span><span class="sxs-lookup"><span data-stu-id="33e72-117">Gets the value of the instruction pointer and a bitwise combination value that describes how the value of the instruction pointer was obtained.</span></span>|  
|[<span data-ttu-id="33e72-118">GetLocalVariable-Methode</span><span class="sxs-lookup"><span data-stu-id="33e72-118">GetLocalVariable Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe-getlocalvariable-method.md)|<span data-ttu-id="33e72-119">Ruft den Wert der angegebenen lokalen Variable in MSIL-Stapelrahmens ab.</span><span class="sxs-lookup"><span data-stu-id="33e72-119">Gets the value of the specified local variable in this MSIL stack frame.</span></span>|  
|[<span data-ttu-id="33e72-120">GetStackDepth-Methode</span><span class="sxs-lookup"><span data-stu-id="33e72-120">GetStackDepth Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe-getstackdepth-method.md)|<span data-ttu-id="33e72-121">Nicht implementiert.</span><span class="sxs-lookup"><span data-stu-id="33e72-121">Not implemented.</span></span>|  
|[<span data-ttu-id="33e72-122">GetStackValue-Methode</span><span class="sxs-lookup"><span data-stu-id="33e72-122">GetStackValue Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe-getstackvalue-method.md)|<span data-ttu-id="33e72-123">Nicht implementiert.</span><span class="sxs-lookup"><span data-stu-id="33e72-123">Not implemented.</span></span>|  
|[<span data-ttu-id="33e72-124">SetIP-Methode</span><span class="sxs-lookup"><span data-stu-id="33e72-124">SetIP Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe-setip-method.md)|<span data-ttu-id="33e72-125">Legt den Anweisungszeiger am angegebenen Offset Speicherort in den MSIL-Code fest.</span><span class="sxs-lookup"><span data-stu-id="33e72-125">Sets the instruction pointer to the specified offset location in the MSIL code.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="33e72-126">Hinweise</span><span class="sxs-lookup"><span data-stu-id="33e72-126">Remarks</span></span>  
 <span data-ttu-id="33e72-127">Die `ICorDebugILFrame` Schnittstelle ist eine spezielle ICorDebugFrame-Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="33e72-127">The `ICorDebugILFrame` interface is a specialized ICorDebugFrame interface.</span></span> <span data-ttu-id="33e72-128">Hiermit wird für die MSIL-Code-Frames oder für die just-in-Time (JIT) kompiliert Frames.</span><span class="sxs-lookup"><span data-stu-id="33e72-128">It is used either for MSIL code frames or for just-in-time (JIT) compiled frames.</span></span> <span data-ttu-id="33e72-129">Der JIT-kompilierten Rahmen implementieren sowohl die `ICorDebugILFrame` und die ICorDebugNativeFrame-Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="33e72-129">The JIT-compiled frames implement both the `ICorDebugILFrame` interface and the ICorDebugNativeFrame interface.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="33e72-130">Diese Schnittstelle kann weder computerübergreifend noch prozessübergreifend remote aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="33e72-130">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="33e72-131">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="33e72-131">Requirements</span></span>  
 <span data-ttu-id="33e72-132">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="33e72-132">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="33e72-133">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="33e72-133">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="33e72-134">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="33e72-134">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="33e72-135">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="33e72-135">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="33e72-136">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="33e72-136">See also</span></span>
- [<span data-ttu-id="33e72-137">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="33e72-137">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
