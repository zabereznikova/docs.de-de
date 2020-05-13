---
title: ICorDebugMergedAssemblyRecord-Schnittstelle
ms.date: 03/30/2017
ms.assetid: fe280b11-9479-4e34-a07c-0d1ea8088422
ms.openlocfilehash: 721f6c1cf468b3b518d2ea213588ae2410249690
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/12/2020
ms.locfileid: "83208719"
---
# <a name="icordebugmergedassemblyrecord-interface"></a><span data-ttu-id="c8530-102">ICorDebugMergedAssemblyRecord-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="c8530-102">ICorDebugMergedAssemblyRecord Interface</span></span>
<span data-ttu-id="c8530-103">Enthält Informationen zu einer zusammengeführten Assembly.</span><span class="sxs-lookup"><span data-stu-id="c8530-103">Provides information about a merged assembly.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="c8530-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="c8530-104">Methods</span></span>  
  
|<span data-ttu-id="c8530-105">Methode</span><span class="sxs-lookup"><span data-stu-id="c8530-105">Method</span></span>|<span data-ttu-id="c8530-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="c8530-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="c8530-107">GetCulture-Methode</span><span class="sxs-lookup"><span data-stu-id="c8530-107">GetCulture Method</span></span>](icordebugmergedassemblyrecord-getculture-method.md)|<span data-ttu-id="c8530-108">Ruft die Kulturnamen-Zeichenfolge der Assembly ab.</span><span class="sxs-lookup"><span data-stu-id="c8530-108">Gets the culture name string of the assembly.</span></span>|  
|[<span data-ttu-id="c8530-109">GetIndex-Methode</span><span class="sxs-lookup"><span data-stu-id="c8530-109">GetIndex Method</span></span>](icordebugmergedassemblyrecord-getindex-method.md)|<span data-ttu-id="c8530-110">Ruft den Präfixindex der Assembly ab.</span><span class="sxs-lookup"><span data-stu-id="c8530-110">Gets the assembly's prefix index.</span></span>|  
|[<span data-ttu-id="c8530-111">GetPublicKey-Methode</span><span class="sxs-lookup"><span data-stu-id="c8530-111">GetPublicKey Method</span></span>](icordebugmergedassemblyrecord-getpublickey-method.md)|<span data-ttu-id="c8530-112">Ruft den öffentlichen Schlüssel der Assembly ab.</span><span class="sxs-lookup"><span data-stu-id="c8530-112">Gets the assembly's public key.</span></span>|  
|[<span data-ttu-id="c8530-113">GetPublicKeyToken-Methode</span><span class="sxs-lookup"><span data-stu-id="c8530-113">GetPublicKeyToken Method</span></span>](icordebugmergedassemblyrecord-getpublickeytoken-method.md)|<span data-ttu-id="c8530-114">Ruft das öffentliche Schlüsseltoken der Assembly ab.</span><span class="sxs-lookup"><span data-stu-id="c8530-114">Gets the assembly's public key token.</span></span>|  
|[<span data-ttu-id="c8530-115">GetSimpleName-Methode</span><span class="sxs-lookup"><span data-stu-id="c8530-115">GetSimpleName Method</span></span>](icordebugmergedassemblyrecord-getsimplename-method.md)|<span data-ttu-id="c8530-116">Ruft den einfachen Namen der Assembly ab.</span><span class="sxs-lookup"><span data-stu-id="c8530-116">Gets the simple name of the assembly.</span></span>|  
|[<span data-ttu-id="c8530-117">GetVersion-Methode</span><span class="sxs-lookup"><span data-stu-id="c8530-117">GetVersion Method</span></span>](icordebugmergedassemblyrecord-getversion-method.md)|<span data-ttu-id="c8530-118">Ruft Versionsinformationen zur Assembly ab.</span><span class="sxs-lookup"><span data-stu-id="c8530-118">Gets the assembly's version information.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c8530-119">Hinweise</span><span class="sxs-lookup"><span data-stu-id="c8530-119">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="c8530-120">Diese Schnittstelle ist nur in Verbindung mit .NET Native verfügbar.</span><span class="sxs-lookup"><span data-stu-id="c8530-120">This interface is available with .NET Native only.</span></span> <span data-ttu-id="c8530-121">Wenn Sie diese Schnittstelle für ICorDebug-Szenarien außerhalb von .NET Native implementieren, ignoriert die Common Language Runtime diese Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="c8530-121">If you implement this interface for ICorDebug scenarios outside of .NET Native, the common language runtime will ignore this interface.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c8530-122">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="c8530-122">Requirements</span></span>  
 <span data-ttu-id="c8530-123">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c8530-123">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c8530-124">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="c8530-124">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="c8530-125">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c8530-125">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c8530-126">**.NET Framework Versionen:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c8530-126">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c8530-127">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c8530-127">See also</span></span>

- [<span data-ttu-id="c8530-128">Debugschnittstellen</span><span class="sxs-lookup"><span data-stu-id="c8530-128">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="c8530-129">Debuggen</span><span class="sxs-lookup"><span data-stu-id="c8530-129">Debugging</span></span>](index.md)
