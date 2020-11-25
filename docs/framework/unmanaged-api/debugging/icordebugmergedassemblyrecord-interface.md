---
title: ICorDebugMergedAssemblyRecord-Schnittstelle
ms.date: 03/30/2017
ms.assetid: fe280b11-9479-4e34-a07c-0d1ea8088422
ms.openlocfilehash: a26702c6b21e4bfe352d861387a80b976a8dc556
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95710492"
---
# <a name="icordebugmergedassemblyrecord-interface"></a><span data-ttu-id="9e266-102">ICorDebugMergedAssemblyRecord-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="9e266-102">ICorDebugMergedAssemblyRecord Interface</span></span>

<span data-ttu-id="9e266-103">Enthält Informationen zu einer zusammengeführten Assembly.</span><span class="sxs-lookup"><span data-stu-id="9e266-103">Provides information about a merged assembly.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="9e266-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="9e266-104">Methods</span></span>  
  
|<span data-ttu-id="9e266-105">Methode</span><span class="sxs-lookup"><span data-stu-id="9e266-105">Method</span></span>|<span data-ttu-id="9e266-106">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="9e266-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="9e266-107">GetCulture-Methode</span><span class="sxs-lookup"><span data-stu-id="9e266-107">GetCulture Method</span></span>](icordebugmergedassemblyrecord-getculture-method.md)|<span data-ttu-id="9e266-108">Ruft die Kulturnamen-Zeichenfolge der Assembly ab.</span><span class="sxs-lookup"><span data-stu-id="9e266-108">Gets the culture name string of the assembly.</span></span>|  
|[<span data-ttu-id="9e266-109">GetIndex-Methode</span><span class="sxs-lookup"><span data-stu-id="9e266-109">GetIndex Method</span></span>](icordebugmergedassemblyrecord-getindex-method.md)|<span data-ttu-id="9e266-110">Ruft den Präfixindex der Assembly ab.</span><span class="sxs-lookup"><span data-stu-id="9e266-110">Gets the assembly's prefix index.</span></span>|  
|[<span data-ttu-id="9e266-111">GetPublicKey-Methode</span><span class="sxs-lookup"><span data-stu-id="9e266-111">GetPublicKey Method</span></span>](icordebugmergedassemblyrecord-getpublickey-method.md)|<span data-ttu-id="9e266-112">Ruft den öffentlichen Schlüssel der Assembly ab.</span><span class="sxs-lookup"><span data-stu-id="9e266-112">Gets the assembly's public key.</span></span>|  
|[<span data-ttu-id="9e266-113">GetPublicKeyToken-Methode</span><span class="sxs-lookup"><span data-stu-id="9e266-113">GetPublicKeyToken Method</span></span>](icordebugmergedassemblyrecord-getpublickeytoken-method.md)|<span data-ttu-id="9e266-114">Ruft das öffentliche Schlüsseltoken der Assembly ab.</span><span class="sxs-lookup"><span data-stu-id="9e266-114">Gets the assembly's public key token.</span></span>|  
|[<span data-ttu-id="9e266-115">GetSimpleName-Methode</span><span class="sxs-lookup"><span data-stu-id="9e266-115">GetSimpleName Method</span></span>](icordebugmergedassemblyrecord-getsimplename-method.md)|<span data-ttu-id="9e266-116">Ruft den einfachen Namen der Assembly ab.</span><span class="sxs-lookup"><span data-stu-id="9e266-116">Gets the simple name of the assembly.</span></span>|  
|[<span data-ttu-id="9e266-117">GetVersion-Methode</span><span class="sxs-lookup"><span data-stu-id="9e266-117">GetVersion Method</span></span>](icordebugmergedassemblyrecord-getversion-method.md)|<span data-ttu-id="9e266-118">Ruft Versionsinformationen zur Assembly ab.</span><span class="sxs-lookup"><span data-stu-id="9e266-118">Gets the assembly's version information.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="9e266-119">Hinweise</span><span class="sxs-lookup"><span data-stu-id="9e266-119">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="9e266-120">Diese Schnittstelle ist nur in Verbindung mit .NET Native verfügbar.</span><span class="sxs-lookup"><span data-stu-id="9e266-120">This interface is available with .NET Native only.</span></span> <span data-ttu-id="9e266-121">Wenn Sie diese Schnittstelle für ICorDebug-Szenarien außerhalb von .NET Native implementieren, ignoriert die Common Language Runtime diese Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="9e266-121">If you implement this interface for ICorDebug scenarios outside of .NET Native, the common language runtime will ignore this interface.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9e266-122">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="9e266-122">Requirements</span></span>  

 <span data-ttu-id="9e266-123">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9e266-123">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9e266-124">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="9e266-124">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="9e266-125">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="9e266-125">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="9e266-126">**.NET Framework Versionen:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9e266-126">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9e266-127">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="9e266-127">See also</span></span>

- [<span data-ttu-id="9e266-128">Debugschnittstellen</span><span class="sxs-lookup"><span data-stu-id="9e266-128">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="9e266-129">Debuggen</span><span class="sxs-lookup"><span data-stu-id="9e266-129">Debugging</span></span>](index.md)
