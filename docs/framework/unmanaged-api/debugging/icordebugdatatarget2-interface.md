---
title: ICorDebugDataTarget2-Schnittstelle
ms.date: 03/30/2017
ms.assetid: 13f11388-2f91-48d8-98d6-6a4a63cb5746
ms.openlocfilehash: 472ea0b3d54c025cdd69957765ad2663c7288b15
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/28/2020
ms.locfileid: "76783568"
---
# <a name="icordebugdatatarget2-interface"></a><span data-ttu-id="68769-102">ICorDebugDataTarget2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="68769-102">ICorDebugDataTarget2 Interface</span></span>
<span data-ttu-id="68769-103">Erweitert logisch die [ICorDebug DataTarget](icordebugdatatarget-interface.md)-Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="68769-103">Logically extends the [ICorDebugDataTarget](icordebugdatatarget-interface.md)interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="68769-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="68769-104">Methods</span></span>  
  
|<span data-ttu-id="68769-105">-Methode</span><span class="sxs-lookup"><span data-stu-id="68769-105">Method</span></span>|<span data-ttu-id="68769-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="68769-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="68769-107">CreateVirtualUnwinder-Methode</span><span class="sxs-lookup"><span data-stu-id="68769-107">CreateVirtualUnwinder Method</span></span>](icordebugdatatarget2-createvirtualunwinder-method.md)|<span data-ttu-id="68769-108">Erstellt einen neuen Stapelentlader, der mit dem Entladen bei einem Anfangskontext beginnt (welcher nicht unbedingt das Blatt eines Threads ist).</span><span class="sxs-lookup"><span data-stu-id="68769-108">Creates a new stack unwinder that starts unwinding from an initial context (which isn't necessarily the leaf of a thread).</span></span>|  
|[<span data-ttu-id="68769-109">EnumerateThreadIDs-Methode</span><span class="sxs-lookup"><span data-stu-id="68769-109">EnumerateThreadIDs Method</span></span>](icordebugdatatarget2-enumeratethreadids-method.md)|<span data-ttu-id="68769-110">Gibt eine Liste der aktiven Thread-IDs aus.</span><span class="sxs-lookup"><span data-stu-id="68769-110">Returns a list of active thread IDs.</span></span>|  
|[<span data-ttu-id="68769-111">GetImageFromPointer-Methode</span><span class="sxs-lookup"><span data-stu-id="68769-111">GetImageFromPointer Method</span></span>](icordebugdatatarget2-getimagefrompointer-method.md)|<span data-ttu-id="68769-112">Gibt die Basisadresse des Moduls und die Größe von einer Adresse in diesem Modul aus.</span><span class="sxs-lookup"><span data-stu-id="68769-112">Returns the module base address and size from an address in that module.</span></span>|  
|[<span data-ttu-id="68769-113">GetImageLocation-Methode</span><span class="sxs-lookup"><span data-stu-id="68769-113">GetImageLocation Method</span></span>](icordebugdatatarget2-getimagelocation-method.md)|<span data-ttu-id="68769-114">Gibt den Pfad eines Moduls aus der Basisadresse des Moduls zurück.</span><span class="sxs-lookup"><span data-stu-id="68769-114">Returns the path of a module from the module's base address.</span></span>|  
|[<span data-ttu-id="68769-115">GetSymbolProviderForImage-Methode</span><span class="sxs-lookup"><span data-stu-id="68769-115">GetSymbolProviderForImage Method</span></span>](icordebugdatatarget2-getsymbolproviderforimage-method.md)|<span data-ttu-id="68769-116">Gibt anhand der Basisadresse des Moduls den Symbol-Anbieter für ein Modul aus.</span><span class="sxs-lookup"><span data-stu-id="68769-116">Returns the symbol-provider for a module from the base address of that module.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="68769-117">Hinweise</span><span class="sxs-lookup"><span data-stu-id="68769-117">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="68769-118">Diese Schnittstelle ist nur in Verbindung mit .NET Native verfügbar.</span><span class="sxs-lookup"><span data-stu-id="68769-118">This interface is available with .NET Native only.</span></span> <span data-ttu-id="68769-119">Wenn Sie diese Schnittstelle für ICorDebug-Szenarien außerhalb von .NET Native implementieren, ignoriert die Common Language Runtime diese Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="68769-119">If you implement this interface for ICorDebug scenarios outside of .NET Native, the common language runtime will ignore this interface.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="68769-120">-Anforderungen</span><span class="sxs-lookup"><span data-stu-id="68769-120">Requirements</span></span>  
 <span data-ttu-id="68769-121">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="68769-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="68769-122">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="68769-122">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="68769-123">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="68769-123">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="68769-124">**.NET Framework Versionen:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="68769-124">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="68769-125">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="68769-125">See also</span></span>

- [<span data-ttu-id="68769-126">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="68769-126">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="68769-127">Debuggen</span><span class="sxs-lookup"><span data-stu-id="68769-127">Debugging</span></span>](index.md)
