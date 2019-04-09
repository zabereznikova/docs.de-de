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
ms.openlocfilehash: ca21911f3d16b79887b9d6d8185f8fab17651321
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59093214"
---
# <a name="icordebugfunction-interface"></a><span data-ttu-id="140b5-102">ICorDebugFunction-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="140b5-102">ICorDebugFunction Interface</span></span>

<span data-ttu-id="140b5-103">Stellt eine verwaltete Funktion oder Methode dar.</span><span class="sxs-lookup"><span data-stu-id="140b5-103">Represents a managed function or method.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="140b5-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="140b5-104">Methods</span></span>  
  
|<span data-ttu-id="140b5-105">Methode</span><span class="sxs-lookup"><span data-stu-id="140b5-105">Method</span></span>|<span data-ttu-id="140b5-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="140b5-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="140b5-107">CreateBreakpoint-Methode</span><span class="sxs-lookup"><span data-stu-id="140b5-107">CreateBreakpoint Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugfunction-createbreakpoint-method.md)|<span data-ttu-id="140b5-108">Erstellt einen Haltepunkt am Anfang dieser Funktion.</span><span class="sxs-lookup"><span data-stu-id="140b5-108">Creates a breakpoint at the beginning of this function.</span></span>|  
|[<span data-ttu-id="140b5-109">GetClass-Methode</span><span class="sxs-lookup"><span data-stu-id="140b5-109">GetClass Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugfunction-getclass-method.md)|<span data-ttu-id="140b5-110">Ruft ein ICorDebugClass-Objekt, das die Klasse darstellt, die, der diese Funktion ein Member ist.</span><span class="sxs-lookup"><span data-stu-id="140b5-110">Gets an ICorDebugClass object that represents the class this function is a member of.</span></span>|  
|[<span data-ttu-id="140b5-111">GetCurrentVersionNumber-Methode</span><span class="sxs-lookup"><span data-stu-id="140b5-111">GetCurrentVersionNumber Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugfunction-getcurrentversionnumber-method.md)|<span data-ttu-id="140b5-112">Ruft die Versionsnummer der letzten Änderung dieser Funktion ab.</span><span class="sxs-lookup"><span data-stu-id="140b5-112">Gets the version number of the latest edit made to this function.</span></span>|  
|[<span data-ttu-id="140b5-113">GetILCode-Methode</span><span class="sxs-lookup"><span data-stu-id="140b5-113">GetILCode Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugfunction-getilcode-method.md)|<span data-ttu-id="140b5-114">Ruft die Microsoft intermediate Language (MSIL)-Code für diese Funktion ab.</span><span class="sxs-lookup"><span data-stu-id="140b5-114">Gets the Microsoft intermediate language (MSIL) code for this function.</span></span>|  
|[<span data-ttu-id="140b5-115">GetLocalVarSigToken-Methode</span><span class="sxs-lookup"><span data-stu-id="140b5-115">GetLocalVarSigToken Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugfunction-getlocalvarsigtoken-method.md)|<span data-ttu-id="140b5-116">Ruft den Metadatentoken für die Signatur der lokalen Variablen der Funktion, die von diesem dargestellt wird `ICorDebugFunction` Instanz.</span><span class="sxs-lookup"><span data-stu-id="140b5-116">Gets the metadata token for the local variable signature of the function that is represented by this `ICorDebugFunction` instance.</span></span>|  
|[<span data-ttu-id="140b5-117">GetModule-Methode</span><span class="sxs-lookup"><span data-stu-id="140b5-117">GetModule Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugfunction-getmodule-method.md)|<span data-ttu-id="140b5-118">Ruft das Modul, in dem diese Funktion definiert ist.</span><span class="sxs-lookup"><span data-stu-id="140b5-118">Gets the module in which this function is defined.</span></span>|  
|[<span data-ttu-id="140b5-119">GetNativeCode-Methode</span><span class="sxs-lookup"><span data-stu-id="140b5-119">GetNativeCode Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugfunction-getnativecode-method.md)|<span data-ttu-id="140b5-120">Ruft den systemeigenen Code für diese Funktion ab.</span><span class="sxs-lookup"><span data-stu-id="140b5-120">Gets the native code for this function.</span></span>|  
|[<span data-ttu-id="140b5-121">GetToken-Methode</span><span class="sxs-lookup"><span data-stu-id="140b5-121">GetToken Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugfunction-gettoken-method.md)|<span data-ttu-id="140b5-122">Ruft den Metadatentoken für diese Funktion.</span><span class="sxs-lookup"><span data-stu-id="140b5-122">Gets the metadata token for this function.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="140b5-123">Hinweise</span><span class="sxs-lookup"><span data-stu-id="140b5-123">Remarks</span></span>  
 <span data-ttu-id="140b5-124">Die `ICorDebugFunction` Schnittstelle stellt eine Funktion mit generischen Typparametern keine dar.</span><span class="sxs-lookup"><span data-stu-id="140b5-124">The `ICorDebugFunction` interface does not represent a function with generic type parameters.</span></span> <span data-ttu-id="140b5-125">Z. B. eine `ICorDebugFunction` Instanz darstellen würde `Func<T>` , nicht jedoch `Func<string>`.</span><span class="sxs-lookup"><span data-stu-id="140b5-125">For example, an `ICorDebugFunction` instance would represent `Func<T>` but not `Func<string>`.</span></span> <span data-ttu-id="140b5-126">Rufen Sie [ICorDebugILFrame2:: EnumerateTypeParameters](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe2-enumeratetypeparameters-method.md) um die generischen Typparameter zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="140b5-126">Call [ICorDebugILFrame2::EnumerateTypeParameters](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe2-enumeratetypeparameters-method.md) to get the generic type parameters.</span></span>  
  
 <span data-ttu-id="140b5-127">Die Beziehung zwischen einer Methode Metadatentoken `mdMethodDef`, und einer Methode `ICorDebugFunction` Objekt ist abhängig davon, ob bearbeiten und Fortfahren für die Funktion zulässig ist:</span><span class="sxs-lookup"><span data-stu-id="140b5-127">The relationship between a method's metadata token, `mdMethodDef`, and a method's `ICorDebugFunction` object is dependent upon whether Edit and Continue is allowed on the function:</span></span>  
  
-   <span data-ttu-id="140b5-128">Wenn Bearbeiten und Fortfahren wird für die Funktion nicht zulässig, besteht eine direkte Beziehung zwischen der `ICorDebugFunction` Objekt und die `mdMethodDef` token.</span><span class="sxs-lookup"><span data-stu-id="140b5-128">If Edit and Continue is not allowed on the function, a one-to-one relationship exists between the `ICorDebugFunction` object and the `mdMethodDef` token.</span></span> <span data-ttu-id="140b5-129">D. h. die Funktion verfügt über eine `ICorDebugFunction` Objekt und eine `mdMethodDef` token.</span><span class="sxs-lookup"><span data-stu-id="140b5-129">That is, the function has one `ICorDebugFunction` object and one `mdMethodDef` token.</span></span>  
  
-   <span data-ttu-id="140b5-130">Wenn Bearbeiten und Fortfahren für die Funktion zulässig ist, besteht eine n: 1 Beziehung zwischen der `ICorDebugFunction` Objekt und die `mdMethodDef` token.</span><span class="sxs-lookup"><span data-stu-id="140b5-130">If Edit and Continue is allowed on the function, a many-to-one relationship exists between the `ICorDebugFunction` object and the `mdMethodDef` token.</span></span> <span data-ttu-id="140b5-131">Also möglicherweise die Funktion viele Instanzen des `ICorDebugFunction`, einen für jede Version der Funktion, aber nur eine `mdMethodDef` token.</span><span class="sxs-lookup"><span data-stu-id="140b5-131">That is, the function may have many instances of `ICorDebugFunction`, one for each version of the function, but only one `mdMethodDef` token.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="140b5-132">Diese Schnittstelle kann weder computerübergreifend noch prozessübergreifend remote aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="140b5-132">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="140b5-133">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="140b5-133">Requirements</span></span>  
 <span data-ttu-id="140b5-134">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="140b5-134">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="140b5-135">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="140b5-135">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="140b5-136">**Bibliothek:**  CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="140b5-136">**Library:**  CorGuids.lib</span></span>  
  
 **<span data-ttu-id="140b5-137">.NET Framework-Versionen:</span><span class="sxs-lookup"><span data-stu-id="140b5-137">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="140b5-138">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="140b5-138">See also</span></span>

- [<span data-ttu-id="140b5-139">Debugschnittstellen</span><span class="sxs-lookup"><span data-stu-id="140b5-139">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
