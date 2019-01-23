---
title: ICorDebugMergedAssemblyRecord-Schnittstelle
ms.date: 03/30/2017
ms.assetid: fe280b11-9479-4e34-a07c-0d1ea8088422
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: c0f42b8d6eb1a35052b25fda6e7cc9c7d00836df
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54559358"
---
# <a name="icordebugmergedassemblyrecord-interface"></a><span data-ttu-id="8de98-102">ICorDebugMergedAssemblyRecord-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="8de98-102">ICorDebugMergedAssemblyRecord Interface</span></span>
<span data-ttu-id="8de98-103">Enthält Informationen zu einer zusammengeführten Assembly.</span><span class="sxs-lookup"><span data-stu-id="8de98-103">Provides information about a merged assembly.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="8de98-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="8de98-104">Methods</span></span>  
  
|<span data-ttu-id="8de98-105">Methode</span><span class="sxs-lookup"><span data-stu-id="8de98-105">Method</span></span>|<span data-ttu-id="8de98-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="8de98-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="8de98-107">GetCulture-Methode</span><span class="sxs-lookup"><span data-stu-id="8de98-107">GetCulture Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmergedassemblyrecord-getculture-method.md)|<span data-ttu-id="8de98-108">Ruft die Kulturnamen-Zeichenfolge der Assembly ab.</span><span class="sxs-lookup"><span data-stu-id="8de98-108">Gets the culture name string of the assembly.</span></span>|  
|[<span data-ttu-id="8de98-109">GetIndex-Methode</span><span class="sxs-lookup"><span data-stu-id="8de98-109">GetIndex Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmergedassemblyrecord-getindex-method.md)|<span data-ttu-id="8de98-110">Ruft den Präfixindex der Assembly ab.</span><span class="sxs-lookup"><span data-stu-id="8de98-110">Gets the assembly's prefix index.</span></span>|  
|[<span data-ttu-id="8de98-111">GetPublicKey-Methode</span><span class="sxs-lookup"><span data-stu-id="8de98-111">GetPublicKey Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmergedassemblyrecord-getpublickey-method.md)|<span data-ttu-id="8de98-112">Ruft den öffentlichen Schlüssel der Assembly ab.</span><span class="sxs-lookup"><span data-stu-id="8de98-112">Gets the assembly's public key.</span></span>|  
|[<span data-ttu-id="8de98-113">GetPublicKeyToken-Methode</span><span class="sxs-lookup"><span data-stu-id="8de98-113">GetPublicKeyToken Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmergedassemblyrecord-getpublickeytoken-method.md)|<span data-ttu-id="8de98-114">Ruft das öffentliche Schlüsseltoken der Assembly ab.</span><span class="sxs-lookup"><span data-stu-id="8de98-114">Gets the assembly's public key token.</span></span>|  
|[<span data-ttu-id="8de98-115">GetSimpleName-Methode</span><span class="sxs-lookup"><span data-stu-id="8de98-115">GetSimpleName Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmergedassemblyrecord-getsimplename-method.md)|<span data-ttu-id="8de98-116">Ruft den einfachen Namen der Assembly ab.</span><span class="sxs-lookup"><span data-stu-id="8de98-116">Gets the simple name of the assembly.</span></span>|  
|[<span data-ttu-id="8de98-117">GetVersion-Methode</span><span class="sxs-lookup"><span data-stu-id="8de98-117">GetVersion Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmergedassemblyrecord-getversion-method.md)|<span data-ttu-id="8de98-118">Ruft Versionsinformationen zur Assembly ab.</span><span class="sxs-lookup"><span data-stu-id="8de98-118">Gets the assembly's version information.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="8de98-119">Hinweise</span><span class="sxs-lookup"><span data-stu-id="8de98-119">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="8de98-120">Diese Schnittstelle ist nur in Verbindung mit .NET Native verfügbar.</span><span class="sxs-lookup"><span data-stu-id="8de98-120">This interface is available with .NET Native only.</span></span> <span data-ttu-id="8de98-121">Wenn Sie diese Schnittstelle für ICorDebug-Szenarien außerhalb von .NET Native implementieren, ignoriert die Common Language Runtime diese Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="8de98-121">If you implement this interface for ICorDebug scenarios outside of .NET Native, the common language runtime will ignore this interface.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8de98-122">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="8de98-122">Requirements</span></span>  
 <span data-ttu-id="8de98-123">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8de98-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8de98-124">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="8de98-124">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="8de98-125">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="8de98-125">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="8de98-126">**.NET Framework-Versionen:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8de98-126">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8de98-127">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="8de98-127">See also</span></span>
- [<span data-ttu-id="8de98-128">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="8de98-128">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="8de98-129">Debuggen</span><span class="sxs-lookup"><span data-stu-id="8de98-129">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
