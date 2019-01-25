---
title: ICorDebugDataTarget2-Schnittstelle
ms.date: 03/30/2017
ms.assetid: 13f11388-2f91-48d8-98d6-6a4a63cb5746
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 0931cb5ed133d4de82473ae786f28f13fd396db5
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54743005"
---
# <a name="icordebugdatatarget2-interface"></a><span data-ttu-id="13c52-102">ICorDebugDataTarget2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="13c52-102">ICorDebugDataTarget2 Interface</span></span>
<span data-ttu-id="13c52-103">Erweitert logisch die [ICorDebugDataTarget](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget-interface.md)Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="13c52-103">Logically extends the [ICorDebugDataTarget](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget-interface.md)interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="13c52-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="13c52-104">Methods</span></span>  
  
|<span data-ttu-id="13c52-105">Methode</span><span class="sxs-lookup"><span data-stu-id="13c52-105">Method</span></span>|<span data-ttu-id="13c52-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="13c52-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="13c52-107">CreateVirtualUnwinder-Methode</span><span class="sxs-lookup"><span data-stu-id="13c52-107">CreateVirtualUnwinder Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget2-createvirtualunwinder-method.md)|<span data-ttu-id="13c52-108">Erstellt einen neuen Stapelentlader, der mit dem Entladen bei einem Anfangskontext beginnt (welcher nicht unbedingt das Blatt eines Threads ist).</span><span class="sxs-lookup"><span data-stu-id="13c52-108">Creates a new stack unwinder that starts unwinding from an initial context (which isn't necessarily the leaf of a thread).</span></span>|  
|[<span data-ttu-id="13c52-109">EnumerateThreadIDs-Methode</span><span class="sxs-lookup"><span data-stu-id="13c52-109">EnumerateThreadIDs Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget2-enumeratethreadids-method.md)|<span data-ttu-id="13c52-110">Gibt eine Liste der aktiven Thread-IDs aus.</span><span class="sxs-lookup"><span data-stu-id="13c52-110">Returns a list of active thread IDs.</span></span>|  
|[<span data-ttu-id="13c52-111">GetImageFromPointer-Methode</span><span class="sxs-lookup"><span data-stu-id="13c52-111">GetImageFromPointer Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget2-getimagefrompointer-method.md)|<span data-ttu-id="13c52-112">Gibt die Basisadresse des Moduls und die Größe von einer Adresse in diesem Modul aus.</span><span class="sxs-lookup"><span data-stu-id="13c52-112">Returns the module base address and size from an address in that module.</span></span>|  
|[<span data-ttu-id="13c52-113">GetImageLocation-Methode</span><span class="sxs-lookup"><span data-stu-id="13c52-113">GetImageLocation Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget2-getimagelocation-method.md)|<span data-ttu-id="13c52-114">Gibt den Pfad eines Moduls aus der Basisadresse des Moduls zurück.</span><span class="sxs-lookup"><span data-stu-id="13c52-114">Returns the path of a module from the module's base address.</span></span>|  
|[<span data-ttu-id="13c52-115">GetSymbolProviderForImage-Methode</span><span class="sxs-lookup"><span data-stu-id="13c52-115">GetSymbolProviderForImage Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget2-getsymbolproviderforimage-method.md)|<span data-ttu-id="13c52-116">Gibt anhand der Basisadresse des Moduls den Symbol-Anbieter für ein Modul aus.</span><span class="sxs-lookup"><span data-stu-id="13c52-116">Returns the symbol-provider for a module from the base address of that module.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="13c52-117">Hinweise</span><span class="sxs-lookup"><span data-stu-id="13c52-117">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="13c52-118">Diese Schnittstelle ist nur in Verbindung mit .NET Native verfügbar.</span><span class="sxs-lookup"><span data-stu-id="13c52-118">This interface is available with .NET Native only.</span></span> <span data-ttu-id="13c52-119">Wenn Sie diese Schnittstelle für ICorDebug-Szenarien außerhalb von .NET Native implementieren, ignoriert die Common Language Runtime diese Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="13c52-119">If you implement this interface for ICorDebug scenarios outside of .NET Native, the common language runtime will ignore this interface.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="13c52-120">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="13c52-120">Requirements</span></span>  
 <span data-ttu-id="13c52-121">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="13c52-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="13c52-122">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="13c52-122">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="13c52-123">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="13c52-123">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="13c52-124">**.NET Framework-Versionen:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="13c52-124">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="13c52-125">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="13c52-125">See also</span></span>
- [<span data-ttu-id="13c52-126">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="13c52-126">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="13c52-127">Debuggen</span><span class="sxs-lookup"><span data-stu-id="13c52-127">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
