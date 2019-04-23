---
title: ICorDebugMergedAssemblyRecord-Schnittstelle
ms.date: 03/30/2017
ms.assetid: fe280b11-9479-4e34-a07c-0d1ea8088422
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 1118c879da4376bda0c73368a8b15df4f7a3d014
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59180465"
---
# <a name="icordebugmergedassemblyrecord-interface"></a><span data-ttu-id="95bae-102">ICorDebugMergedAssemblyRecord-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="95bae-102">ICorDebugMergedAssemblyRecord Interface</span></span>
<span data-ttu-id="95bae-103">Enthält Informationen zu einer zusammengeführten Assembly.</span><span class="sxs-lookup"><span data-stu-id="95bae-103">Provides information about a merged assembly.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="95bae-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="95bae-104">Methods</span></span>  
  
|<span data-ttu-id="95bae-105">Methode</span><span class="sxs-lookup"><span data-stu-id="95bae-105">Method</span></span>|<span data-ttu-id="95bae-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="95bae-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="95bae-107">GetCulture-Methode</span><span class="sxs-lookup"><span data-stu-id="95bae-107">GetCulture Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmergedassemblyrecord-getculture-method.md)|<span data-ttu-id="95bae-108">Ruft die Kulturnamen-Zeichenfolge der Assembly ab.</span><span class="sxs-lookup"><span data-stu-id="95bae-108">Gets the culture name string of the assembly.</span></span>|  
|[<span data-ttu-id="95bae-109">GetIndex-Methode</span><span class="sxs-lookup"><span data-stu-id="95bae-109">GetIndex Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmergedassemblyrecord-getindex-method.md)|<span data-ttu-id="95bae-110">Ruft den Präfixindex der Assembly ab.</span><span class="sxs-lookup"><span data-stu-id="95bae-110">Gets the assembly's prefix index.</span></span>|  
|[<span data-ttu-id="95bae-111">GetPublicKey-Methode</span><span class="sxs-lookup"><span data-stu-id="95bae-111">GetPublicKey Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmergedassemblyrecord-getpublickey-method.md)|<span data-ttu-id="95bae-112">Ruft den öffentlichen Schlüssel der Assembly ab.</span><span class="sxs-lookup"><span data-stu-id="95bae-112">Gets the assembly's public key.</span></span>|  
|[<span data-ttu-id="95bae-113">GetPublicKeyToken-Methode</span><span class="sxs-lookup"><span data-stu-id="95bae-113">GetPublicKeyToken Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmergedassemblyrecord-getpublickeytoken-method.md)|<span data-ttu-id="95bae-114">Ruft das öffentliche Schlüsseltoken der Assembly ab.</span><span class="sxs-lookup"><span data-stu-id="95bae-114">Gets the assembly's public key token.</span></span>|  
|[<span data-ttu-id="95bae-115">GetSimpleName-Methode</span><span class="sxs-lookup"><span data-stu-id="95bae-115">GetSimpleName Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmergedassemblyrecord-getsimplename-method.md)|<span data-ttu-id="95bae-116">Ruft den einfachen Namen der Assembly ab.</span><span class="sxs-lookup"><span data-stu-id="95bae-116">Gets the simple name of the assembly.</span></span>|  
|[<span data-ttu-id="95bae-117">GetVersion-Methode</span><span class="sxs-lookup"><span data-stu-id="95bae-117">GetVersion Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmergedassemblyrecord-getversion-method.md)|<span data-ttu-id="95bae-118">Ruft Versionsinformationen zur Assembly ab.</span><span class="sxs-lookup"><span data-stu-id="95bae-118">Gets the assembly's version information.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="95bae-119">Hinweise</span><span class="sxs-lookup"><span data-stu-id="95bae-119">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="95bae-120">Diese Schnittstelle ist nur in Verbindung mit .NET Native verfügbar.</span><span class="sxs-lookup"><span data-stu-id="95bae-120">This interface is available with .NET Native only.</span></span> <span data-ttu-id="95bae-121">Wenn Sie diese Schnittstelle für ICorDebug-Szenarien außerhalb von .NET Native implementieren, ignoriert die Common Language Runtime diese Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="95bae-121">If you implement this interface for ICorDebug scenarios outside of .NET Native, the common language runtime will ignore this interface.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="95bae-122">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="95bae-122">Requirements</span></span>  
 <span data-ttu-id="95bae-123">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="95bae-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="95bae-124">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="95bae-124">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="95bae-125">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="95bae-125">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="95bae-126">**.NET Framework-Versionen:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="95bae-126">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="95bae-127">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="95bae-127">See also</span></span>

- [<span data-ttu-id="95bae-128">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="95bae-128">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="95bae-129">Debuggen</span><span class="sxs-lookup"><span data-stu-id="95bae-129">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
