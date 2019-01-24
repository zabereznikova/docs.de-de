---
title: ICorDebugFunction-Schnittstelle1
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
ms.openlocfilehash: b810ce8634781438faccac25f96442624a78ea0a
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54676769"
---
# <a name="icordebugfunction-interface1"></a><span data-ttu-id="90d30-102">ICorDebugFunction-Schnittstelle1</span><span class="sxs-lookup"><span data-stu-id="90d30-102">ICorDebugFunction Interface1</span></span>
<span data-ttu-id="90d30-103">Stellt eine verwaltete Funktion oder Methode dar.</span><span class="sxs-lookup"><span data-stu-id="90d30-103">Represents a managed function or method.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="90d30-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="90d30-104">Methods</span></span>  
  
|<span data-ttu-id="90d30-105">Methode</span><span class="sxs-lookup"><span data-stu-id="90d30-105">Method</span></span>|<span data-ttu-id="90d30-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="90d30-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="90d30-107">CreateBreakpoint-Methode</span><span class="sxs-lookup"><span data-stu-id="90d30-107">CreateBreakpoint Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugfunction-createbreakpoint-method.md)|<span data-ttu-id="90d30-108">Erstellt einen Haltepunkt am Anfang dieser Funktion.</span><span class="sxs-lookup"><span data-stu-id="90d30-108">Creates a breakpoint at the beginning of this function.</span></span>|  
|[<span data-ttu-id="90d30-109">GetClass-Methode</span><span class="sxs-lookup"><span data-stu-id="90d30-109">GetClass Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugfunction-getclass-method.md)|<span data-ttu-id="90d30-110">Ruft ein ICorDebugClass-Objekt, das die Klasse darstellt, die, der diese Funktion ein Member ist.</span><span class="sxs-lookup"><span data-stu-id="90d30-110">Gets an ICorDebugClass object that represents the class this function is a member of.</span></span>|  
|[<span data-ttu-id="90d30-111">GetCurrentVersionNumber-Methode</span><span class="sxs-lookup"><span data-stu-id="90d30-111">GetCurrentVersionNumber Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugfunction-getcurrentversionnumber-method.md)|<span data-ttu-id="90d30-112">Ruft die Versionsnummer der letzten Änderung dieser Funktion ab.</span><span class="sxs-lookup"><span data-stu-id="90d30-112">Gets the version number of the latest edit made to this function.</span></span>|  
|[<span data-ttu-id="90d30-113">GetILCode-Methode</span><span class="sxs-lookup"><span data-stu-id="90d30-113">GetILCode Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugfunction-getilcode-method.md)|<span data-ttu-id="90d30-114">Ruft die Microsoft intermediate Language (MSIL)-Code für diese Funktion ab.</span><span class="sxs-lookup"><span data-stu-id="90d30-114">Gets the Microsoft intermediate language (MSIL) code for this function.</span></span>|  
|[<span data-ttu-id="90d30-115">GetLocalVarSigToken-Methode</span><span class="sxs-lookup"><span data-stu-id="90d30-115">GetLocalVarSigToken Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugfunction-getlocalvarsigtoken-method.md)|<span data-ttu-id="90d30-116">Ruft den Metadatentoken für die Signatur der lokalen Variablen der Funktion, die von diesem dargestellt wird `ICorDebugFunction` Instanz.</span><span class="sxs-lookup"><span data-stu-id="90d30-116">Gets the metadata token for the local variable signature of the function that is represented by this `ICorDebugFunction` instance.</span></span>|  
|[<span data-ttu-id="90d30-117">GetModule-Methode</span><span class="sxs-lookup"><span data-stu-id="90d30-117">GetModule Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugfunction-getmodule-method.md)|<span data-ttu-id="90d30-118">Ruft das Modul, in dem diese Funktion definiert ist.</span><span class="sxs-lookup"><span data-stu-id="90d30-118">Gets the module in which this function is defined.</span></span>|  
|[<span data-ttu-id="90d30-119">GetNativeCode-Methode</span><span class="sxs-lookup"><span data-stu-id="90d30-119">GetNativeCode Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugfunction-getnativecode-method.md)|<span data-ttu-id="90d30-120">Ruft den systemeigenen Code für diese Funktion ab.</span><span class="sxs-lookup"><span data-stu-id="90d30-120">Gets the native code for this function.</span></span>|  
|[<span data-ttu-id="90d30-121">GetToken-Methode</span><span class="sxs-lookup"><span data-stu-id="90d30-121">GetToken Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugfunction-gettoken-method.md)|<span data-ttu-id="90d30-122">Ruft den Metadatentoken für diese Funktion.</span><span class="sxs-lookup"><span data-stu-id="90d30-122">Gets the metadata token for this function.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="90d30-123">Hinweise</span><span class="sxs-lookup"><span data-stu-id="90d30-123">Remarks</span></span>  
 <span data-ttu-id="90d30-124">Die `ICorDebugFunction` Schnittstelle stellt eine Funktion mit generischen Typparametern keine dar.</span><span class="sxs-lookup"><span data-stu-id="90d30-124">The `ICorDebugFunction` interface does not represent a function with generic type parameters.</span></span> <span data-ttu-id="90d30-125">Z. B. eine `ICorDebugFunction` Instanz darstellen würde `Func<T>` , nicht jedoch `Func<string>`.</span><span class="sxs-lookup"><span data-stu-id="90d30-125">For example, an `ICorDebugFunction` instance would represent `Func<T>` but not `Func<string>`.</span></span> <span data-ttu-id="90d30-126">Rufen Sie [ICorDebugILFrame2:: EnumerateTypeParameters](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe2-enumeratetypeparameters-method.md) um die generischen Typparameter zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="90d30-126">Call [ICorDebugILFrame2::EnumerateTypeParameters](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe2-enumeratetypeparameters-method.md) to get the generic type parameters.</span></span>  
  
 <span data-ttu-id="90d30-127">Die Beziehung zwischen einer Methode Metadatentoken `mdMethodDef`, und einer Methode `ICorDebugFunction` Objekt ist abhängig davon, ob bearbeiten und Fortfahren für die Funktion zulässig ist:</span><span class="sxs-lookup"><span data-stu-id="90d30-127">The relationship between a method's metadata token, `mdMethodDef`, and a method's `ICorDebugFunction` object is dependent upon whether Edit and Continue is allowed on the function:</span></span>  
  
-   <span data-ttu-id="90d30-128">Wenn Bearbeiten und Fortfahren wird für die Funktion nicht zulässig, besteht eine direkte Beziehung zwischen der `ICorDebugFunction` Objekt und die `mdMethodDef` token.</span><span class="sxs-lookup"><span data-stu-id="90d30-128">If Edit and Continue is not allowed on the function, a one-to-one relationship exists between the `ICorDebugFunction` object and the `mdMethodDef` token.</span></span> <span data-ttu-id="90d30-129">D. h. die Funktion verfügt über eine `ICorDebugFunction` Objekt und eine `mdMethodDef` token.</span><span class="sxs-lookup"><span data-stu-id="90d30-129">That is, the function has one `ICorDebugFunction` object and one `mdMethodDef` token.</span></span>  
  
-   <span data-ttu-id="90d30-130">Wenn Bearbeiten und Fortfahren für die Funktion zulässig ist, besteht eine n: 1 Beziehung zwischen der `ICorDebugFunction` Objekt und die `mdMethodDef` token.</span><span class="sxs-lookup"><span data-stu-id="90d30-130">If Edit and Continue is allowed on the function, a many-to-one relationship exists between the `ICorDebugFunction` object and the `mdMethodDef` token.</span></span> <span data-ttu-id="90d30-131">Also möglicherweise die Funktion viele Instanzen des `ICorDebugFunction`, einen für jede Version der Funktion, aber nur eine `mdMethodDef` token.</span><span class="sxs-lookup"><span data-stu-id="90d30-131">That is, the function may have many instances of `ICorDebugFunction`, one for each version of the function, but only one `mdMethodDef` token.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="90d30-132">Diese Schnittstelle kann weder computerübergreifend noch prozessübergreifend remote aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="90d30-132">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="90d30-133">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="90d30-133">Requirements</span></span>  
 <span data-ttu-id="90d30-134">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="90d30-134">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="90d30-135">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="90d30-135">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="90d30-136">**Bibliothek:**  CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="90d30-136">**Library:**  CorGuids.lib</span></span>  
  
 <span data-ttu-id="90d30-137">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="90d30-137">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="90d30-138">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="90d30-138">See also</span></span>
- [<span data-ttu-id="90d30-139">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="90d30-139">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
