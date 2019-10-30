---
title: ICorDebugCode-Schnittstelle
ms.date: 03/30/2017
api_name:
- ICorDebugCode
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugCode
helpviewer_keywords:
- ICorDebugCode interface [.NET Framework debugging]
ms.assetid: 7bd14fb6-8b54-4484-a891-e3c21859c019
topic_type:
- apiref
ms.openlocfilehash: 8cb95fad4394e2ce9b7f922e720071d8c4434edb
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73125593"
---
# <a name="icordebugcode-interface"></a><span data-ttu-id="bdccf-102">ICorDebugCode-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="bdccf-102">ICorDebugCode Interface</span></span>

<span data-ttu-id="bdccf-103">Stellt ein Segment von Microsoft Intermediate Language (MSIL)-Code oder nativem Code dar.</span><span class="sxs-lookup"><span data-stu-id="bdccf-103">Represents a segment of either Microsoft intermediate language (MSIL) code or native code.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="bdccf-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="bdccf-104">Methods</span></span>  
  
|<span data-ttu-id="bdccf-105">Methode</span><span class="sxs-lookup"><span data-stu-id="bdccf-105">Method</span></span>|<span data-ttu-id="bdccf-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="bdccf-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="bdccf-107">CreateBreakpoint-Methode</span><span class="sxs-lookup"><span data-stu-id="bdccf-107">CreateBreakpoint Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcode-createbreakpoint-method.md)|<span data-ttu-id="bdccf-108">Erstellt am angegebenen Offset einen Haltepunkt.</span><span class="sxs-lookup"><span data-stu-id="bdccf-108">Creates a breakpoint at the specified offset.</span></span>|  
|[<span data-ttu-id="bdccf-109">GetAddress-Methode</span><span class="sxs-lookup"><span data-stu-id="bdccf-109">GetAddress Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcode-getaddress-method.md)|<span data-ttu-id="bdccf-110">Ruft die relative virtuelle Adresse (RVA) des Codesegments ab, das diesen `ICorDebugCode` darstellt.</span><span class="sxs-lookup"><span data-stu-id="bdccf-110">Gets the relative virtual address (RVA) of the code segment that this `ICorDebugCode` represents.</span></span>|  
|[<span data-ttu-id="bdccf-111">GetCode-Methode</span><span class="sxs-lookup"><span data-stu-id="bdccf-111">GetCode Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcode-getcode-method.md)|<span data-ttu-id="bdccf-112">Ruft den gesamten für die Disassembly formatierten Code für die angegebene Funktion ab.</span><span class="sxs-lookup"><span data-stu-id="bdccf-112">Gets all the code for the specified function, formatted for disassembly.</span></span> <span data-ttu-id="bdccf-113">Diese Methode ist veraltet. Verwenden Sie stattdessen [ICorDebugCode2:: getcodechunert](../../../../docs/framework/unmanaged-api/debugging/icordebugcode2-getcodechunks-method.md) .</span><span class="sxs-lookup"><span data-stu-id="bdccf-113">This method has been deprecated; use [ICorDebugCode2::GetCodeChunks](../../../../docs/framework/unmanaged-api/debugging/icordebugcode2-getcodechunks-method.md) instead.</span></span>|  
|[<span data-ttu-id="bdccf-114">GetEnCRemapSequencePoints-Methode</span><span class="sxs-lookup"><span data-stu-id="bdccf-114">GetEnCRemapSequencePoints Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcode-getencremapsequencepoints-method.md)|<span data-ttu-id="bdccf-115">Nicht implementiert.</span><span class="sxs-lookup"><span data-stu-id="bdccf-115">Not implemented.</span></span>|  
|[<span data-ttu-id="bdccf-116">GetFunction-Methode</span><span class="sxs-lookup"><span data-stu-id="bdccf-116">GetFunction Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcode-getfunction-method.md)|<span data-ttu-id="bdccf-117">Ruft den "ICorDebug Function" ab, der diesem `ICorDebugCode`zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="bdccf-117">Gets the "ICorDebugFunction" associated with this `ICorDebugCode`.</span></span>|  
|[<span data-ttu-id="bdccf-118">GetILToNativeMapping-Methode</span><span class="sxs-lookup"><span data-stu-id="bdccf-118">GetILToNativeMapping Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcode-getiltonativemapping-method.md)|<span data-ttu-id="bdccf-119">Ruft ein Array von "COR_DEBUG_IL_TO_NATIVE_MAP"-Instanzen ab, die Zuordnungen von MSIL-Offsets zu systemeigenen Offsets darstellen.</span><span class="sxs-lookup"><span data-stu-id="bdccf-119">Gets an array of "COR_DEBUG_IL_TO_NATIVE_MAP" instances that represent mappings from MSIL offsets to native offsets.</span></span>|  
|[<span data-ttu-id="bdccf-120">GetSize-Methode</span><span class="sxs-lookup"><span data-stu-id="bdccf-120">GetSize Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcode-getsize-method.md)|<span data-ttu-id="bdccf-121">Ruft die Größe des Binärcodes in Bytes ab, der durch diesen `ICorDebugCode` dargestellt wird.</span><span class="sxs-lookup"><span data-stu-id="bdccf-121">Gets the size, in bytes, of the binary code represented by this `ICorDebugCode`.</span></span>|  
|[<span data-ttu-id="bdccf-122">GetVersionNumber-Methode</span><span class="sxs-lookup"><span data-stu-id="bdccf-122">GetVersionNumber Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcode-getversionnumber-method.md)|<span data-ttu-id="bdccf-123">Ruft die mit eins beginnende Zahl ab, die die Version des Codes angibt, den dieser `ICorDebugCode` darstellt.</span><span class="sxs-lookup"><span data-stu-id="bdccf-123">Gets the one-based number that identifies the version of the code that this `ICorDebugCode` represents.</span></span>|  
|[<span data-ttu-id="bdccf-124">IsIL-Methode</span><span class="sxs-lookup"><span data-stu-id="bdccf-124">IsIL Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcode-isil-method.md)|<span data-ttu-id="bdccf-125">Ruft einen Wert ab, der angibt, ob dieser `ICorDebugCode` in MSIL kompiliert wird.</span><span class="sxs-lookup"><span data-stu-id="bdccf-125">Gets a value that indicates whether this `ICorDebugCode` is compiled in MSIL.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="bdccf-126">Hinweise</span><span class="sxs-lookup"><span data-stu-id="bdccf-126">Remarks</span></span>  
 <span data-ttu-id="bdccf-127">`ICorDebugCode` kann entweder MSIL- oder systemeigenen Code darstellen.</span><span class="sxs-lookup"><span data-stu-id="bdccf-127">`ICorDebugCode` can represent either MSIL or native code.</span></span> <span data-ttu-id="bdccf-128">Ein ICorDebugFunction-Objekt, das MSIL-Code darstellt, kann entweder 0 (null) oder einen `ICorDebugCode` zugeordneten Objekten aufweisen.</span><span class="sxs-lookup"><span data-stu-id="bdccf-128">An "ICorDebugFunction" object that represents MSIL code can have either zero or one `ICorDebugCode` objects associated with it.</span></span> <span data-ttu-id="bdccf-129">Einem ICorDebugFunction-Objekt, das systemeigenen Code darstellt, kann eine beliebige Anzahl von `ICorDebugCode`-Objekten zugeordnet sein.</span><span class="sxs-lookup"><span data-stu-id="bdccf-129">An "ICorDebugFunction" object that represents native code can have any number of `ICorDebugCode` objects associated with it.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="bdccf-130">Diese Schnittstelle kann weder computerübergreifend noch prozessübergreifend remote aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="bdccf-130">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bdccf-131">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="bdccf-131">Requirements</span></span>  
 <span data-ttu-id="bdccf-132">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="bdccf-132">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bdccf-133">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="bdccf-133">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="bdccf-134">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="bdccf-134">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="bdccf-135">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bdccf-135">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bdccf-136">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="bdccf-136">See also</span></span>

- [<span data-ttu-id="bdccf-137">ICorDebugCode3-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="bdccf-137">ICorDebugCode3 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcode3-interface.md)
- [<span data-ttu-id="bdccf-138">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="bdccf-138">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
