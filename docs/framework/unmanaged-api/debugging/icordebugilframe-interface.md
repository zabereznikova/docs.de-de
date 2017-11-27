---
title: ICorDebugILFrame Schnittstelle1
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugILFrame
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugILFrame
helpviewer_keywords: ICorDebugILFrame interface [.NET Framework debugging]
ms.assetid: d5cf5056-da4d-4629-914d-afe42a5393df
topic_type: apiref
caps.latest.revision: "14"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: d8d370fa971f698eb694127c72ff96499b85143d
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugilframe-interface1"></a><span data-ttu-id="9a6f7-102">ICorDebugILFrame Schnittstelle1</span><span class="sxs-lookup"><span data-stu-id="9a6f7-102">ICorDebugILFrame Interface1</span></span>
<span data-ttu-id="9a6f7-103">Stellt einen Stapelrahmen von Microsoft intermediate Language (MSIL)-Code dar.</span><span class="sxs-lookup"><span data-stu-id="9a6f7-103">Represents a stack frame of Microsoft intermediate language (MSIL) code.</span></span> <span data-ttu-id="9a6f7-104">Diese Schnittstelle ist eine Unterklasse von ICorDebugFrame-Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="9a6f7-104">This interface is a subclass of the ICorDebugFrame interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="9a6f7-105">Methoden</span><span class="sxs-lookup"><span data-stu-id="9a6f7-105">Methods</span></span>  
  
|<span data-ttu-id="9a6f7-106">Methode</span><span class="sxs-lookup"><span data-stu-id="9a6f7-106">Method</span></span>|<span data-ttu-id="9a6f7-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="9a6f7-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="9a6f7-108">CanSetIP-Methode</span><span class="sxs-lookup"><span data-stu-id="9a6f7-108">CanSetIP Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe-cansetip-method.md)|<span data-ttu-id="9a6f7-109">Ruft einen Wert, der angibt, ob den Anweisungszeiger am angegebenen Offset Speicherort festgelegt werden kann.</span><span class="sxs-lookup"><span data-stu-id="9a6f7-109">Gets a value that indicates whether it is safe to set the instruction pointer to the specified offset location.</span></span>|  
|[<span data-ttu-id="9a6f7-110">EnumerateArguments-Methode</span><span class="sxs-lookup"><span data-stu-id="9a6f7-110">EnumerateArguments Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe-enumeratearguments-method.md)|<span data-ttu-id="9a6f7-111">Ruft einen Enumerator für die Argumente in diesem Frame ab.</span><span class="sxs-lookup"><span data-stu-id="9a6f7-111">Gets an enumerator for the arguments in this frame.</span></span>|  
|[<span data-ttu-id="9a6f7-112">EnumerateLocalVariables-Methode</span><span class="sxs-lookup"><span data-stu-id="9a6f7-112">EnumerateLocalVariables Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe-enumeratelocalvariables-method.md)|<span data-ttu-id="9a6f7-113">Ruft einen Enumerator für die lokalen Variablen in diesem Frame ab.</span><span class="sxs-lookup"><span data-stu-id="9a6f7-113">Gets an enumerator for the local variables in this frame.</span></span>|  
|[<span data-ttu-id="9a6f7-114">GetArgument-Methode</span><span class="sxs-lookup"><span data-stu-id="9a6f7-114">GetArgument Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe-getargument-method.md)|<span data-ttu-id="9a6f7-115">Ruft den Wert des angegebenen Arguments in MSIL-Stapelrahmen ab.</span><span class="sxs-lookup"><span data-stu-id="9a6f7-115">Gets the value of the specified argument in this MSIL stack frame.</span></span>|  
|[<span data-ttu-id="9a6f7-116">GetIP-Methode</span><span class="sxs-lookup"><span data-stu-id="9a6f7-116">GetIP Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe-getip-method.md)|<span data-ttu-id="9a6f7-117">Ruft den Wert des Anweisungszeigers und eine bitweise Kombination-Wert, der beschreibt, wie der Wert des Anweisungszeigers abgerufen wurde.</span><span class="sxs-lookup"><span data-stu-id="9a6f7-117">Gets the value of the instruction pointer and a bitwise combination value that describes how the value of the instruction pointer was obtained.</span></span>|  
|[<span data-ttu-id="9a6f7-118">GetLocalVariable-Methode</span><span class="sxs-lookup"><span data-stu-id="9a6f7-118">GetLocalVariable Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe-getlocalvariable-method.md)|<span data-ttu-id="9a6f7-119">Ruft den Wert der angegebenen lokalen Variablen in MSIL-Stapelrahmen ab.</span><span class="sxs-lookup"><span data-stu-id="9a6f7-119">Gets the value of the specified local variable in this MSIL stack frame.</span></span>|  
|[<span data-ttu-id="9a6f7-120">GetStackDepth-Methode</span><span class="sxs-lookup"><span data-stu-id="9a6f7-120">GetStackDepth Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe-getstackdepth-method.md)|<span data-ttu-id="9a6f7-121">Nicht implementiert.</span><span class="sxs-lookup"><span data-stu-id="9a6f7-121">Not implemented.</span></span>|  
|[<span data-ttu-id="9a6f7-122">GetStackValue-Methode</span><span class="sxs-lookup"><span data-stu-id="9a6f7-122">GetStackValue Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe-getstackvalue-method.md)|<span data-ttu-id="9a6f7-123">Nicht implementiert.</span><span class="sxs-lookup"><span data-stu-id="9a6f7-123">Not implemented.</span></span>|  
|[<span data-ttu-id="9a6f7-124">SetIP-Methode</span><span class="sxs-lookup"><span data-stu-id="9a6f7-124">SetIP Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe-setip-method.md)|<span data-ttu-id="9a6f7-125">Legt den Anweisungszeiger auf die angegebene Offsetposition im MSIL-Code fest.</span><span class="sxs-lookup"><span data-stu-id="9a6f7-125">Sets the instruction pointer to the specified offset location in the MSIL code.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="9a6f7-126">Hinweise</span><span class="sxs-lookup"><span data-stu-id="9a6f7-126">Remarks</span></span>  
 <span data-ttu-id="9a6f7-127">Die `ICorDebugILFrame` Schnittstelle ist eine spezielle ICorDebugFrame-Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="9a6f7-127">The `ICorDebugILFrame` interface is a specialized ICorDebugFrame interface.</span></span> <span data-ttu-id="9a6f7-128">Es dient für Rahmen der MSIL-Code oder für Just-in-Time (JIT) kompilierten Frames.</span><span class="sxs-lookup"><span data-stu-id="9a6f7-128">It is used either for MSIL code frames or for just-in-time (JIT) compiled frames.</span></span> <span data-ttu-id="9a6f7-129">Die JIT-kompilierten Rahmen implementieren sowohl die `ICorDebugILFrame` Schnittstelle und die ICorDebugNativeFrame-Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="9a6f7-129">The JIT-compiled frames implement both the `ICorDebugILFrame` interface and the ICorDebugNativeFrame interface.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="9a6f7-130">Diese Schnittstelle kann weder computerübergreifend noch prozessübergreifend remote aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="9a6f7-130">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9a6f7-131">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="9a6f7-131">Requirements</span></span>  
 <span data-ttu-id="9a6f7-132">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9a6f7-132">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9a6f7-133">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="9a6f7-133">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="9a6f7-134">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="9a6f7-134">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="9a6f7-135">**.NET Framework-Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9a6f7-135">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9a6f7-136">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="9a6f7-136">See Also</span></span>  
 [<span data-ttu-id="9a6f7-137">Debugschnittstellen</span><span class="sxs-lookup"><span data-stu-id="9a6f7-137">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
