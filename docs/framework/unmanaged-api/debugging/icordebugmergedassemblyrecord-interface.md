---
title: ICorDebugMergedAssemblyRecord-Schnittstelle
ms.date: 03/30/2017
ms.assetid: fe280b11-9479-4e34-a07c-0d1ea8088422
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 8fd7a5f630bcf97277a4f98f2408ecaf04883fa3
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69916990"
---
# <a name="icordebugmergedassemblyrecord-interface"></a><span data-ttu-id="35a5a-102">ICorDebugMergedAssemblyRecord-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="35a5a-102">ICorDebugMergedAssemblyRecord Interface</span></span>
<span data-ttu-id="35a5a-103">Enthält Informationen zu einer zusammengeführten Assembly.</span><span class="sxs-lookup"><span data-stu-id="35a5a-103">Provides information about a merged assembly.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="35a5a-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="35a5a-104">Methods</span></span>  
  
|<span data-ttu-id="35a5a-105">Methode</span><span class="sxs-lookup"><span data-stu-id="35a5a-105">Method</span></span>|<span data-ttu-id="35a5a-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="35a5a-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="35a5a-107">GetCulture-Methode</span><span class="sxs-lookup"><span data-stu-id="35a5a-107">GetCulture Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmergedassemblyrecord-getculture-method.md)|<span data-ttu-id="35a5a-108">Ruft die Kulturnamen-Zeichenfolge der Assembly ab.</span><span class="sxs-lookup"><span data-stu-id="35a5a-108">Gets the culture name string of the assembly.</span></span>|  
|[<span data-ttu-id="35a5a-109">GetIndex-Methode</span><span class="sxs-lookup"><span data-stu-id="35a5a-109">GetIndex Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmergedassemblyrecord-getindex-method.md)|<span data-ttu-id="35a5a-110">Ruft den Präfixindex der Assembly ab.</span><span class="sxs-lookup"><span data-stu-id="35a5a-110">Gets the assembly's prefix index.</span></span>|  
|[<span data-ttu-id="35a5a-111">GetPublicKey-Methode</span><span class="sxs-lookup"><span data-stu-id="35a5a-111">GetPublicKey Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmergedassemblyrecord-getpublickey-method.md)|<span data-ttu-id="35a5a-112">Ruft den öffentlichen Schlüssel der Assembly ab.</span><span class="sxs-lookup"><span data-stu-id="35a5a-112">Gets the assembly's public key.</span></span>|  
|[<span data-ttu-id="35a5a-113">GetPublicKeyToken-Methode</span><span class="sxs-lookup"><span data-stu-id="35a5a-113">GetPublicKeyToken Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmergedassemblyrecord-getpublickeytoken-method.md)|<span data-ttu-id="35a5a-114">Ruft das öffentliche Schlüsseltoken der Assembly ab.</span><span class="sxs-lookup"><span data-stu-id="35a5a-114">Gets the assembly's public key token.</span></span>|  
|[<span data-ttu-id="35a5a-115">GetSimpleName-Methode</span><span class="sxs-lookup"><span data-stu-id="35a5a-115">GetSimpleName Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmergedassemblyrecord-getsimplename-method.md)|<span data-ttu-id="35a5a-116">Ruft den einfachen Namen der Assembly ab.</span><span class="sxs-lookup"><span data-stu-id="35a5a-116">Gets the simple name of the assembly.</span></span>|  
|[<span data-ttu-id="35a5a-117">GetVersion-Methode</span><span class="sxs-lookup"><span data-stu-id="35a5a-117">GetVersion Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmergedassemblyrecord-getversion-method.md)|<span data-ttu-id="35a5a-118">Ruft Versionsinformationen zur Assembly ab.</span><span class="sxs-lookup"><span data-stu-id="35a5a-118">Gets the assembly's version information.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="35a5a-119">Hinweise</span><span class="sxs-lookup"><span data-stu-id="35a5a-119">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="35a5a-120">Diese Schnittstelle ist nur in Verbindung mit .NET Native verfügbar.</span><span class="sxs-lookup"><span data-stu-id="35a5a-120">This interface is available with .NET Native only.</span></span> <span data-ttu-id="35a5a-121">Wenn Sie diese Schnittstelle für ICorDebug-Szenarien außerhalb von .NET Native implementieren, ignoriert die Common Language Runtime diese Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="35a5a-121">If you implement this interface for ICorDebug scenarios outside of .NET Native, the common language runtime will ignore this interface.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="35a5a-122">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="35a5a-122">Requirements</span></span>  
 <span data-ttu-id="35a5a-123">**Formen** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="35a5a-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="35a5a-124">**Header:** Cordebug. idl, Cordebug. h</span><span class="sxs-lookup"><span data-stu-id="35a5a-124">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="35a5a-125">**Fern** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="35a5a-125">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="35a5a-126">**.NET Framework-Versionen:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="35a5a-126">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="35a5a-127">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="35a5a-127">See also</span></span>

- [<span data-ttu-id="35a5a-128">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="35a5a-128">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="35a5a-129">Debuggen</span><span class="sxs-lookup"><span data-stu-id="35a5a-129">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
