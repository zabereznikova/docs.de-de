---
title: ICorDebugFunction-Schnittstelle
ms.date: 03/30/2017
api_name:
- ICorDebugFunction
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugFunction
helpviewer_keywords:
- ICorDebugFunction interface [.NET Framework debugging]
ms.assetid: 783faea9-8083-41c1-b04a-51a81ac4c8f3
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 550b85474c1ccd7e125549e86df906439caf410e
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/28/2019
ms.locfileid: "64621499"
---
# <a name="icordebugfunction-interface"></a><span data-ttu-id="f450d-102">ICorDebugFunction-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="f450d-102">ICorDebugFunction Interface</span></span>

<span data-ttu-id="f450d-103">Stellt eine verwaltete Funktion oder Methode dar.</span><span class="sxs-lookup"><span data-stu-id="f450d-103">Represents a managed function or method.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="f450d-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="f450d-104">Methods</span></span>  
  
|<span data-ttu-id="f450d-105">Methode</span><span class="sxs-lookup"><span data-stu-id="f450d-105">Method</span></span>|<span data-ttu-id="f450d-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="f450d-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="f450d-107">CreateBreakpoint-Methode</span><span class="sxs-lookup"><span data-stu-id="f450d-107">CreateBreakpoint Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugfunction-createbreakpoint-method.md)|<span data-ttu-id="f450d-108">Erstellt einen Haltepunkt am Anfang dieser Funktion.</span><span class="sxs-lookup"><span data-stu-id="f450d-108">Creates a breakpoint at the beginning of this function.</span></span>|  
|[<span data-ttu-id="f450d-109">GetClass-Methode</span><span class="sxs-lookup"><span data-stu-id="f450d-109">GetClass Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugfunction-getclass-method.md)|<span data-ttu-id="f450d-110">Ruft ein ICorDebugClass-Objekt, das die Klasse darstellt, die, der diese Funktion ein Member ist.</span><span class="sxs-lookup"><span data-stu-id="f450d-110">Gets an ICorDebugClass object that represents the class this function is a member of.</span></span>|  
|[<span data-ttu-id="f450d-111">GetCurrentVersionNumber-Methode</span><span class="sxs-lookup"><span data-stu-id="f450d-111">GetCurrentVersionNumber Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugfunction-getcurrentversionnumber-method.md)|<span data-ttu-id="f450d-112">Ruft die Versionsnummer der letzten Änderung dieser Funktion ab.</span><span class="sxs-lookup"><span data-stu-id="f450d-112">Gets the version number of the latest edit made to this function.</span></span>|  
|[<span data-ttu-id="f450d-113">GetILCode-Methode</span><span class="sxs-lookup"><span data-stu-id="f450d-113">GetILCode Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugfunction-getilcode-method.md)|<span data-ttu-id="f450d-114">Ruft die Microsoft intermediate Language (MSIL)-Code für diese Funktion ab.</span><span class="sxs-lookup"><span data-stu-id="f450d-114">Gets the Microsoft intermediate language (MSIL) code for this function.</span></span>|  
|[<span data-ttu-id="f450d-115">GetLocalVarSigToken-Methode</span><span class="sxs-lookup"><span data-stu-id="f450d-115">GetLocalVarSigToken Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugfunction-getlocalvarsigtoken-method.md)|<span data-ttu-id="f450d-116">Ruft den Metadatentoken für die Signatur der lokalen Variablen der Funktion, die von diesem dargestellt wird `ICorDebugFunction` Instanz.</span><span class="sxs-lookup"><span data-stu-id="f450d-116">Gets the metadata token for the local variable signature of the function that is represented by this `ICorDebugFunction` instance.</span></span>|  
|[<span data-ttu-id="f450d-117">GetModule-Methode</span><span class="sxs-lookup"><span data-stu-id="f450d-117">GetModule Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugfunction-getmodule-method.md)|<span data-ttu-id="f450d-118">Ruft das Modul, in dem diese Funktion definiert ist.</span><span class="sxs-lookup"><span data-stu-id="f450d-118">Gets the module in which this function is defined.</span></span>|  
|[<span data-ttu-id="f450d-119">GetNativeCode-Methode</span><span class="sxs-lookup"><span data-stu-id="f450d-119">GetNativeCode Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugfunction-getnativecode-method.md)|<span data-ttu-id="f450d-120">Ruft den systemeigenen Code für diese Funktion ab.</span><span class="sxs-lookup"><span data-stu-id="f450d-120">Gets the native code for this function.</span></span>|  
|[<span data-ttu-id="f450d-121">GetToken-Methode</span><span class="sxs-lookup"><span data-stu-id="f450d-121">GetToken Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugfunction-gettoken-method.md)|<span data-ttu-id="f450d-122">Ruft den Metadatentoken für diese Funktion.</span><span class="sxs-lookup"><span data-stu-id="f450d-122">Gets the metadata token for this function.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f450d-123">Hinweise</span><span class="sxs-lookup"><span data-stu-id="f450d-123">Remarks</span></span>  
 <span data-ttu-id="f450d-124">Die `ICorDebugFunction` Schnittstelle stellt eine Funktion mit generischen Typparametern keine dar.</span><span class="sxs-lookup"><span data-stu-id="f450d-124">The `ICorDebugFunction` interface does not represent a function with generic type parameters.</span></span> <span data-ttu-id="f450d-125">Z. B. eine `ICorDebugFunction` Instanz darstellen würde `Func<T>` , nicht jedoch `Func<string>`.</span><span class="sxs-lookup"><span data-stu-id="f450d-125">For example, an `ICorDebugFunction` instance would represent `Func<T>` but not `Func<string>`.</span></span> <span data-ttu-id="f450d-126">Rufen Sie [ICorDebugILFrame2:: EnumerateTypeParameters](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe2-enumeratetypeparameters-method.md) um die generischen Typparameter zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="f450d-126">Call [ICorDebugILFrame2::EnumerateTypeParameters](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe2-enumeratetypeparameters-method.md) to get the generic type parameters.</span></span>  
  
 <span data-ttu-id="f450d-127">Die Beziehung zwischen einer Methode Metadatentoken `mdMethodDef`, und einer Methode `ICorDebugFunction` Objekt ist abhängig davon, ob bearbeiten und Fortfahren für die Funktion zulässig ist:</span><span class="sxs-lookup"><span data-stu-id="f450d-127">The relationship between a method's metadata token, `mdMethodDef`, and a method's `ICorDebugFunction` object is dependent upon whether Edit and Continue is allowed on the function:</span></span>  
  
- <span data-ttu-id="f450d-128">Wenn Bearbeiten und Fortfahren wird für die Funktion nicht zulässig, besteht eine direkte Beziehung zwischen der `ICorDebugFunction` Objekt und die `mdMethodDef` token.</span><span class="sxs-lookup"><span data-stu-id="f450d-128">If Edit and Continue is not allowed on the function, a one-to-one relationship exists between the `ICorDebugFunction` object and the `mdMethodDef` token.</span></span> <span data-ttu-id="f450d-129">D. h. die Funktion verfügt über eine `ICorDebugFunction` Objekt und eine `mdMethodDef` token.</span><span class="sxs-lookup"><span data-stu-id="f450d-129">That is, the function has one `ICorDebugFunction` object and one `mdMethodDef` token.</span></span>  
  
- <span data-ttu-id="f450d-130">Wenn Bearbeiten und Fortfahren für die Funktion zulässig ist, besteht eine n: 1 Beziehung zwischen der `ICorDebugFunction` Objekt und die `mdMethodDef` token.</span><span class="sxs-lookup"><span data-stu-id="f450d-130">If Edit and Continue is allowed on the function, a many-to-one relationship exists between the `ICorDebugFunction` object and the `mdMethodDef` token.</span></span> <span data-ttu-id="f450d-131">Also möglicherweise die Funktion viele Instanzen des `ICorDebugFunction`, einen für jede Version der Funktion, aber nur eine `mdMethodDef` token.</span><span class="sxs-lookup"><span data-stu-id="f450d-131">That is, the function may have many instances of `ICorDebugFunction`, one for each version of the function, but only one `mdMethodDef` token.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="f450d-132">Diese Schnittstelle kann weder computerübergreifend noch prozessübergreifend remote aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="f450d-132">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f450d-133">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="f450d-133">Requirements</span></span>  
 <span data-ttu-id="f450d-134">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f450d-134">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f450d-135">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="f450d-135">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="f450d-136">**Bibliothek:**  CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f450d-136">**Library:**  CorGuids.lib</span></span>  
  
 <span data-ttu-id="f450d-137">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f450d-137">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f450d-138">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f450d-138">See also</span></span>

- [<span data-ttu-id="f450d-139">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="f450d-139">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
