---
title: ICorDebugILFrame-Schnittstelle
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
ms.openlocfilehash: 1f1e42cd929d2d6282d282cf62dce00104b3a925
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/12/2020
ms.locfileid: "83210240"
---
# <a name="icordebugilframe-interface"></a><span data-ttu-id="83f76-102">ICorDebugILFrame-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="83f76-102">ICorDebugILFrame Interface</span></span>

<span data-ttu-id="83f76-103">Stellt einen Stapel Rahmen von MSIL-Code (Microsoft Intermediate Language) dar.</span><span class="sxs-lookup"><span data-stu-id="83f76-103">Represents a stack frame of Microsoft intermediate language (MSIL) code.</span></span> <span data-ttu-id="83f76-104">Diese Schnittstelle ist eine Unterklasse der ICorDebugFrame-Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="83f76-104">This interface is a subclass of the ICorDebugFrame interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="83f76-105">Methoden</span><span class="sxs-lookup"><span data-stu-id="83f76-105">Methods</span></span>  
  
|<span data-ttu-id="83f76-106">Methode</span><span class="sxs-lookup"><span data-stu-id="83f76-106">Method</span></span>|<span data-ttu-id="83f76-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="83f76-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="83f76-108">CanSetIP-Methode</span><span class="sxs-lookup"><span data-stu-id="83f76-108">CanSetIP Method</span></span>](icordebugilframe-cansetip-method.md)|<span data-ttu-id="83f76-109">Ruft einen Wert ab, der angibt, ob es sicher ist, den Anweisungs Zeiger auf die angegebene Offset Position festzulegen.</span><span class="sxs-lookup"><span data-stu-id="83f76-109">Gets a value that indicates whether it is safe to set the instruction pointer to the specified offset location.</span></span>|  
|[<span data-ttu-id="83f76-110">EnumerateArguments-Methode</span><span class="sxs-lookup"><span data-stu-id="83f76-110">EnumerateArguments Method</span></span>](icordebugilframe-enumeratearguments-method.md)|<span data-ttu-id="83f76-111">Ruft einen Enumerator für die Argumente in diesem Frame ab.</span><span class="sxs-lookup"><span data-stu-id="83f76-111">Gets an enumerator for the arguments in this frame.</span></span>|  
|[<span data-ttu-id="83f76-112">EnumerateLocalVariables-Methode</span><span class="sxs-lookup"><span data-stu-id="83f76-112">EnumerateLocalVariables Method</span></span>](icordebugilframe-enumeratelocalvariables-method.md)|<span data-ttu-id="83f76-113">Ruft einen Enumerator für die lokalen Variablen in diesem Frame ab.</span><span class="sxs-lookup"><span data-stu-id="83f76-113">Gets an enumerator for the local variables in this frame.</span></span>|  
|[<span data-ttu-id="83f76-114">GetArgument-Methode</span><span class="sxs-lookup"><span data-stu-id="83f76-114">GetArgument Method</span></span>](icordebugilframe-getargument-method.md)|<span data-ttu-id="83f76-115">Ruft den Wert des angegebenen Arguments in diesem MSIL-Stapel Rahmen ab.</span><span class="sxs-lookup"><span data-stu-id="83f76-115">Gets the value of the specified argument in this MSIL stack frame.</span></span>|  
|[<span data-ttu-id="83f76-116">GetIP-Methode</span><span class="sxs-lookup"><span data-stu-id="83f76-116">GetIP Method</span></span>](icordebugilframe-getip-method.md)|<span data-ttu-id="83f76-117">Ruft den Wert des Anweisungs Zeigers und einen bitweisen Kombinationswert ab, der beschreibt, wie der Wert des Anweisungs Zeigers abgerufen wurde.</span><span class="sxs-lookup"><span data-stu-id="83f76-117">Gets the value of the instruction pointer and a bitwise combination value that describes how the value of the instruction pointer was obtained.</span></span>|  
|[<span data-ttu-id="83f76-118">GetLocalVariable-Methode</span><span class="sxs-lookup"><span data-stu-id="83f76-118">GetLocalVariable Method</span></span>](icordebugilframe-getlocalvariable-method.md)|<span data-ttu-id="83f76-119">Ruft den Wert der angegebenen lokalen Variablen in diesem MSIL-Stapel Rahmen ab.</span><span class="sxs-lookup"><span data-stu-id="83f76-119">Gets the value of the specified local variable in this MSIL stack frame.</span></span>|  
|[<span data-ttu-id="83f76-120">GetStackDepth-Methode</span><span class="sxs-lookup"><span data-stu-id="83f76-120">GetStackDepth Method</span></span>](icordebugilframe-getstackdepth-method.md)|<span data-ttu-id="83f76-121">Nicht implementiert.</span><span class="sxs-lookup"><span data-stu-id="83f76-121">Not implemented.</span></span>|  
|[<span data-ttu-id="83f76-122">GetStackValue-Methode</span><span class="sxs-lookup"><span data-stu-id="83f76-122">GetStackValue Method</span></span>](icordebugilframe-getstackvalue-method.md)|<span data-ttu-id="83f76-123">Nicht implementiert.</span><span class="sxs-lookup"><span data-stu-id="83f76-123">Not implemented.</span></span>|  
|[<span data-ttu-id="83f76-124">SetIP-Methode</span><span class="sxs-lookup"><span data-stu-id="83f76-124">SetIP Method</span></span>](icordebugilframe-setip-method.md)|<span data-ttu-id="83f76-125">Legt den Anweisungs Zeiger auf die angegebene Offset Position im MSIL-Code fest.</span><span class="sxs-lookup"><span data-stu-id="83f76-125">Sets the instruction pointer to the specified offset location in the MSIL code.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="83f76-126">Hinweise</span><span class="sxs-lookup"><span data-stu-id="83f76-126">Remarks</span></span>  
 <span data-ttu-id="83f76-127">Die- `ICorDebugILFrame` Schnittstelle ist eine spezialisierte ICorDebug-Frame-Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="83f76-127">The `ICorDebugILFrame` interface is a specialized ICorDebugFrame interface.</span></span> <span data-ttu-id="83f76-128">Sie wird entweder für MSIL-Code Rahmen oder for just-in-time (JIT)-kompilierte Frames verwendet.</span><span class="sxs-lookup"><span data-stu-id="83f76-128">It is used either for MSIL code frames or for just-in-time (JIT) compiled frames.</span></span> <span data-ttu-id="83f76-129">Die JIT-kompilierten Frames implementieren sowohl die `ICorDebugILFrame` -Schnittstelle als auch die ICorDebugNativeFrame-Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="83f76-129">The JIT-compiled frames implement both the `ICorDebugILFrame` interface and the ICorDebugNativeFrame interface.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="83f76-130">Diese Schnittstelle kann weder computerübergreifend noch prozessübergreifend remote aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="83f76-130">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="83f76-131">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="83f76-131">Requirements</span></span>  
 <span data-ttu-id="83f76-132">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="83f76-132">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="83f76-133">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="83f76-133">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="83f76-134">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="83f76-134">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="83f76-135">**.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="83f76-135">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="83f76-136">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="83f76-136">See also</span></span>

- [<span data-ttu-id="83f76-137">Debugschnittstellen</span><span class="sxs-lookup"><span data-stu-id="83f76-137">Debugging Interfaces</span></span>](debugging-interfaces.md)
