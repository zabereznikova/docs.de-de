---
title: ICorDebugMergedAssemblyRecord-Schnittstelle
ms.date: 03/30/2017
ms.assetid: fe280b11-9479-4e34-a07c-0d1ea8088422
ms.openlocfilehash: 6d5d862110cd91e8ac81c96e50486be10c579903
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/28/2020
ms.locfileid: "76793061"
---
# <a name="icordebugmergedassemblyrecord-interface"></a><span data-ttu-id="87020-102">ICorDebugMergedAssemblyRecord-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="87020-102">ICorDebugMergedAssemblyRecord Interface</span></span>
<span data-ttu-id="87020-103">Enthält Informationen zu einer zusammengeführten Assembly.</span><span class="sxs-lookup"><span data-stu-id="87020-103">Provides information about a merged assembly.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="87020-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="87020-104">Methods</span></span>  
  
|<span data-ttu-id="87020-105">-Methode</span><span class="sxs-lookup"><span data-stu-id="87020-105">Method</span></span>|<span data-ttu-id="87020-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="87020-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="87020-107">GetCulture-Methode</span><span class="sxs-lookup"><span data-stu-id="87020-107">GetCulture Method</span></span>](icordebugmergedassemblyrecord-getculture-method.md)|<span data-ttu-id="87020-108">Ruft die Kulturnamen-Zeichenfolge der Assembly ab.</span><span class="sxs-lookup"><span data-stu-id="87020-108">Gets the culture name string of the assembly.</span></span>|  
|[<span data-ttu-id="87020-109">GetIndex-Methode</span><span class="sxs-lookup"><span data-stu-id="87020-109">GetIndex Method</span></span>](icordebugmergedassemblyrecord-getindex-method.md)|<span data-ttu-id="87020-110">Ruft den Präfixindex der Assembly ab.</span><span class="sxs-lookup"><span data-stu-id="87020-110">Gets the assembly's prefix index.</span></span>|  
|[<span data-ttu-id="87020-111">GetPublicKey-Methode</span><span class="sxs-lookup"><span data-stu-id="87020-111">GetPublicKey Method</span></span>](icordebugmergedassemblyrecord-getpublickey-method.md)|<span data-ttu-id="87020-112">Ruft den öffentlichen Schlüssel der Assembly ab.</span><span class="sxs-lookup"><span data-stu-id="87020-112">Gets the assembly's public key.</span></span>|  
|[<span data-ttu-id="87020-113">GetPublicKeyToken-Methode</span><span class="sxs-lookup"><span data-stu-id="87020-113">GetPublicKeyToken Method</span></span>](icordebugmergedassemblyrecord-getpublickeytoken-method.md)|<span data-ttu-id="87020-114">Ruft das öffentliche Schlüsseltoken der Assembly ab.</span><span class="sxs-lookup"><span data-stu-id="87020-114">Gets the assembly's public key token.</span></span>|  
|[<span data-ttu-id="87020-115">GetSimpleName-Methode</span><span class="sxs-lookup"><span data-stu-id="87020-115">GetSimpleName Method</span></span>](icordebugmergedassemblyrecord-getsimplename-method.md)|<span data-ttu-id="87020-116">Ruft den einfachen Namen der Assembly ab.</span><span class="sxs-lookup"><span data-stu-id="87020-116">Gets the simple name of the assembly.</span></span>|  
|[<span data-ttu-id="87020-117">GetVersion-Methode</span><span class="sxs-lookup"><span data-stu-id="87020-117">GetVersion Method</span></span>](icordebugmergedassemblyrecord-getversion-method.md)|<span data-ttu-id="87020-118">Ruft Versionsinformationen zur Assembly ab.</span><span class="sxs-lookup"><span data-stu-id="87020-118">Gets the assembly's version information.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="87020-119">Hinweise</span><span class="sxs-lookup"><span data-stu-id="87020-119">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="87020-120">Diese Schnittstelle ist nur in Verbindung mit .NET Native verfügbar.</span><span class="sxs-lookup"><span data-stu-id="87020-120">This interface is available with .NET Native only.</span></span> <span data-ttu-id="87020-121">Wenn Sie diese Schnittstelle für ICorDebug-Szenarien außerhalb von .NET Native implementieren, ignoriert die Common Language Runtime diese Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="87020-121">If you implement this interface for ICorDebug scenarios outside of .NET Native, the common language runtime will ignore this interface.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="87020-122">-Anforderungen</span><span class="sxs-lookup"><span data-stu-id="87020-122">Requirements</span></span>  
 <span data-ttu-id="87020-123">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="87020-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="87020-124">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="87020-124">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="87020-125">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="87020-125">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="87020-126">**.NET Framework Versionen:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="87020-126">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="87020-127">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="87020-127">See also</span></span>

- [<span data-ttu-id="87020-128">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="87020-128">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="87020-129">Debuggen</span><span class="sxs-lookup"><span data-stu-id="87020-129">Debugging</span></span>](index.md)
