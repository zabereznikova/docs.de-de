---
title: ICorDebugMergedAssemblyRecord-Schnittstelle
ms.date: 03/30/2017
ms.assetid: fe280b11-9479-4e34-a07c-0d1ea8088422
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 1118c879da4376bda0c73368a8b15df4f7a3d014
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59180465"
---
# <a name="icordebugmergedassemblyrecord-interface"></a><span data-ttu-id="258ca-102">ICorDebugMergedAssemblyRecord-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="258ca-102">ICorDebugMergedAssemblyRecord Interface</span></span>
<span data-ttu-id="258ca-103">Enthält Informationen zu einer zusammengeführten Assembly.</span><span class="sxs-lookup"><span data-stu-id="258ca-103">Provides information about a merged assembly.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="258ca-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="258ca-104">Methods</span></span>  
  
|<span data-ttu-id="258ca-105">Methode</span><span class="sxs-lookup"><span data-stu-id="258ca-105">Method</span></span>|<span data-ttu-id="258ca-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="258ca-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="258ca-107">GetCulture-Methode</span><span class="sxs-lookup"><span data-stu-id="258ca-107">GetCulture Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmergedassemblyrecord-getculture-method.md)|<span data-ttu-id="258ca-108">Ruft die Kulturnamen-Zeichenfolge der Assembly ab.</span><span class="sxs-lookup"><span data-stu-id="258ca-108">Gets the culture name string of the assembly.</span></span>|  
|[<span data-ttu-id="258ca-109">GetIndex-Methode</span><span class="sxs-lookup"><span data-stu-id="258ca-109">GetIndex Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmergedassemblyrecord-getindex-method.md)|<span data-ttu-id="258ca-110">Ruft den Präfixindex der Assembly ab.</span><span class="sxs-lookup"><span data-stu-id="258ca-110">Gets the assembly's prefix index.</span></span>|  
|[<span data-ttu-id="258ca-111">GetPublicKey-Methode</span><span class="sxs-lookup"><span data-stu-id="258ca-111">GetPublicKey Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmergedassemblyrecord-getpublickey-method.md)|<span data-ttu-id="258ca-112">Ruft den öffentlichen Schlüssel der Assembly ab.</span><span class="sxs-lookup"><span data-stu-id="258ca-112">Gets the assembly's public key.</span></span>|  
|[<span data-ttu-id="258ca-113">GetPublicKeyToken-Methode</span><span class="sxs-lookup"><span data-stu-id="258ca-113">GetPublicKeyToken Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmergedassemblyrecord-getpublickeytoken-method.md)|<span data-ttu-id="258ca-114">Ruft das öffentliche Schlüsseltoken der Assembly ab.</span><span class="sxs-lookup"><span data-stu-id="258ca-114">Gets the assembly's public key token.</span></span>|  
|[<span data-ttu-id="258ca-115">GetSimpleName-Methode</span><span class="sxs-lookup"><span data-stu-id="258ca-115">GetSimpleName Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmergedassemblyrecord-getsimplename-method.md)|<span data-ttu-id="258ca-116">Ruft den einfachen Namen der Assembly ab.</span><span class="sxs-lookup"><span data-stu-id="258ca-116">Gets the simple name of the assembly.</span></span>|  
|[<span data-ttu-id="258ca-117">GetVersion-Methode</span><span class="sxs-lookup"><span data-stu-id="258ca-117">GetVersion Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmergedassemblyrecord-getversion-method.md)|<span data-ttu-id="258ca-118">Ruft Versionsinformationen zur Assembly ab.</span><span class="sxs-lookup"><span data-stu-id="258ca-118">Gets the assembly's version information.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="258ca-119">Hinweise</span><span class="sxs-lookup"><span data-stu-id="258ca-119">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="258ca-120">Diese Schnittstelle ist nur in Verbindung mit .NET Native verfügbar.</span><span class="sxs-lookup"><span data-stu-id="258ca-120">This interface is available with .NET Native only.</span></span> <span data-ttu-id="258ca-121">Wenn Sie diese Schnittstelle für ICorDebug-Szenarien außerhalb von .NET Native implementieren, ignoriert die Common Language Runtime diese Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="258ca-121">If you implement this interface for ICorDebug scenarios outside of .NET Native, the common language runtime will ignore this interface.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="258ca-122">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="258ca-122">Requirements</span></span>  
 <span data-ttu-id="258ca-123">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="258ca-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="258ca-124">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="258ca-124">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="258ca-125">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="258ca-125">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="258ca-126">.NET Framework-Versionen:</span><span class="sxs-lookup"><span data-stu-id="258ca-126">.NET Framework Versions:</span></span>** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="258ca-127">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="258ca-127">See also</span></span>

- [<span data-ttu-id="258ca-128">Debugschnittstellen</span><span class="sxs-lookup"><span data-stu-id="258ca-128">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="258ca-129">Debuggen</span><span class="sxs-lookup"><span data-stu-id="258ca-129">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
