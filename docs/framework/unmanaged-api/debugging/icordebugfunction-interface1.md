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
ms.openlocfilehash: 668b27932ea7a2bdc244e1ac0bb8e6891cbd4d17
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95726294"
---
# <a name="icordebugfunction-interface"></a><span data-ttu-id="c64df-102">ICorDebugFunction-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="c64df-102">ICorDebugFunction Interface</span></span>

<span data-ttu-id="c64df-103">Stellt eine verwaltete Funktion oder Methode dar.</span><span class="sxs-lookup"><span data-stu-id="c64df-103">Represents a managed function or method.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="c64df-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="c64df-104">Methods</span></span>  
  
|<span data-ttu-id="c64df-105">Methode</span><span class="sxs-lookup"><span data-stu-id="c64df-105">Method</span></span>|<span data-ttu-id="c64df-106">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="c64df-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="c64df-107">CreateBreakpoint-Methode</span><span class="sxs-lookup"><span data-stu-id="c64df-107">CreateBreakpoint Method</span></span>](icordebugfunction-createbreakpoint-method.md)|<span data-ttu-id="c64df-108">Erstellt am Anfang dieser Funktion einen Haltepunkt.</span><span class="sxs-lookup"><span data-stu-id="c64df-108">Creates a breakpoint at the beginning of this function.</span></span>|  
|[<span data-ttu-id="c64df-109">GetClass-Methode</span><span class="sxs-lookup"><span data-stu-id="c64df-109">GetClass Method</span></span>](icordebugfunction-getclass-method.md)|<span data-ttu-id="c64df-110">Ruft ein ICorDebugClass-Objekt ab, das die Klasse darstellt, deren Member diese Funktion ist.</span><span class="sxs-lookup"><span data-stu-id="c64df-110">Gets an ICorDebugClass object that represents the class this function is a member of.</span></span>|  
|[<span data-ttu-id="c64df-111">GetCurrentVersionNumber-Methode</span><span class="sxs-lookup"><span data-stu-id="c64df-111">GetCurrentVersionNumber Method</span></span>](icordebugfunction-getcurrentversionnumber-method.md)|<span data-ttu-id="c64df-112">Ruft die Versionsnummer der aktuellen Bearbeitung ab, die an dieser Funktion vorgenommen wurde.</span><span class="sxs-lookup"><span data-stu-id="c64df-112">Gets the version number of the latest edit made to this function.</span></span>|  
|[<span data-ttu-id="c64df-113">GetILCode-Methode</span><span class="sxs-lookup"><span data-stu-id="c64df-113">GetILCode Method</span></span>](icordebugfunction-getilcode-method.md)|<span data-ttu-id="c64df-114">Ruft den MSIL-Code (Microsoft Intermediate Language) für diese Funktion ab.</span><span class="sxs-lookup"><span data-stu-id="c64df-114">Gets the Microsoft intermediate language (MSIL) code for this function.</span></span>|  
|[<span data-ttu-id="c64df-115">GetLocalVarSigToken-Methode</span><span class="sxs-lookup"><span data-stu-id="c64df-115">GetLocalVarSigToken Method</span></span>](icordebugfunction-getlocalvarsigtoken-method.md)|<span data-ttu-id="c64df-116">Ruft das Metadatentoken für die Signatur der lokalen Variablen der Funktion ab, die durch diese Instanz dargestellt wird `ICorDebugFunction` .</span><span class="sxs-lookup"><span data-stu-id="c64df-116">Gets the metadata token for the local variable signature of the function that is represented by this `ICorDebugFunction` instance.</span></span>|  
|[<span data-ttu-id="c64df-117">GetModule-Methode</span><span class="sxs-lookup"><span data-stu-id="c64df-117">GetModule Method</span></span>](icordebugfunction-getmodule-method.md)|<span data-ttu-id="c64df-118">Ruft das Modul ab, in dem diese Funktion definiert ist.</span><span class="sxs-lookup"><span data-stu-id="c64df-118">Gets the module in which this function is defined.</span></span>|  
|[<span data-ttu-id="c64df-119">GetNativeCode-Methode</span><span class="sxs-lookup"><span data-stu-id="c64df-119">GetNativeCode Method</span></span>](icordebugfunction-getnativecode-method.md)|<span data-ttu-id="c64df-120">Ruft den nativen Code für diese Funktion ab.</span><span class="sxs-lookup"><span data-stu-id="c64df-120">Gets the native code for this function.</span></span>|  
|[<span data-ttu-id="c64df-121">GetToken-Methode</span><span class="sxs-lookup"><span data-stu-id="c64df-121">GetToken Method</span></span>](icordebugfunction-gettoken-method.md)|<span data-ttu-id="c64df-122">Ruft das Metadatentoken für diese Funktion ab.</span><span class="sxs-lookup"><span data-stu-id="c64df-122">Gets the metadata token for this function.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c64df-123">Hinweise</span><span class="sxs-lookup"><span data-stu-id="c64df-123">Remarks</span></span>  

 <span data-ttu-id="c64df-124">Die- `ICorDebugFunction` Schnittstelle stellt keine Funktion mit generischen Typparametern dar.</span><span class="sxs-lookup"><span data-stu-id="c64df-124">The `ICorDebugFunction` interface does not represent a function with generic type parameters.</span></span> <span data-ttu-id="c64df-125">Beispielsweise würde eine `ICorDebugFunction` Instanz, `Func<T>` jedoch nicht, darstellen `Func<string>` .</span><span class="sxs-lookup"><span data-stu-id="c64df-125">For example, an `ICorDebugFunction` instance would represent `Func<T>` but not `Func<string>`.</span></span> <span data-ttu-id="c64df-126">Ruft [ICorDebugILFrame2:: enumeratetypeer Parameters](icordebugilframe2-enumeratetypeparameters-method.md) auf, um die generischen Typparameter abzurufen.</span><span class="sxs-lookup"><span data-stu-id="c64df-126">Call [ICorDebugILFrame2::EnumerateTypeParameters](icordebugilframe2-enumeratetypeparameters-method.md) to get the generic type parameters.</span></span>  
  
 <span data-ttu-id="c64df-127">Die Beziehung zwischen dem Metadatentoken einer Methode, `mdMethodDef` und dem-Objekt einer Methode `ICorDebugFunction` hängt davon ab, ob "Bearbeiten und Fortfahren" für die Funktion zulässig ist:</span><span class="sxs-lookup"><span data-stu-id="c64df-127">The relationship between a method's metadata token, `mdMethodDef`, and a method's `ICorDebugFunction` object is dependent upon whether Edit and Continue is allowed on the function:</span></span>  
  
- <span data-ttu-id="c64df-128">Wenn für die Funktion "Bearbeiten und Fortfahren" nicht zulässig ist, besteht eine 1:1-Beziehung zwischen dem `ICorDebugFunction` Objekt und dem `mdMethodDef` Token.</span><span class="sxs-lookup"><span data-stu-id="c64df-128">If Edit and Continue is not allowed on the function, a one-to-one relationship exists between the `ICorDebugFunction` object and the `mdMethodDef` token.</span></span> <span data-ttu-id="c64df-129">Das heißt, die Funktion verfügt über ein `ICorDebugFunction` Objekt und ein `mdMethodDef` Token.</span><span class="sxs-lookup"><span data-stu-id="c64df-129">That is, the function has one `ICorDebugFunction` object and one `mdMethodDef` token.</span></span>  
  
- <span data-ttu-id="c64df-130">Wenn für die Funktion "Bearbeiten und Fortfahren" zulässig ist, besteht eine n:1-Beziehung zwischen dem `ICorDebugFunction` Objekt und dem `mdMethodDef` Token.</span><span class="sxs-lookup"><span data-stu-id="c64df-130">If Edit and Continue is allowed on the function, a many-to-one relationship exists between the `ICorDebugFunction` object and the `mdMethodDef` token.</span></span> <span data-ttu-id="c64df-131">Das heißt, die Funktion verfügt möglicherweise über viele Instanzen von `ICorDebugFunction` , eine für jede Version der Funktion, aber nur ein `mdMethodDef` Token.</span><span class="sxs-lookup"><span data-stu-id="c64df-131">That is, the function may have many instances of `ICorDebugFunction`, one for each version of the function, but only one `mdMethodDef` token.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="c64df-132">Diese Schnittstelle kann weder computerübergreifend noch prozessübergreifend remote aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="c64df-132">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c64df-133">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="c64df-133">Requirements</span></span>  

 <span data-ttu-id="c64df-134">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c64df-134">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c64df-135">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="c64df-135">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="c64df-136">**Bibliothek:**  Corguids. lib</span><span class="sxs-lookup"><span data-stu-id="c64df-136">**Library:**  CorGuids.lib</span></span>  
  
 <span data-ttu-id="c64df-137">**.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c64df-137">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c64df-138">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="c64df-138">See also</span></span>

- [<span data-ttu-id="c64df-139">Debugschnittstellen</span><span class="sxs-lookup"><span data-stu-id="c64df-139">Debugging Interfaces</span></span>](debugging-interfaces.md)
