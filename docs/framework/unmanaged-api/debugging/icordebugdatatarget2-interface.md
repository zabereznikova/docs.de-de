---
title: ICorDebugDataTarget2-Schnittstelle
ms.date: 03/30/2017
ms.assetid: 13f11388-2f91-48d8-98d6-6a4a63cb5746
ms.openlocfilehash: 1c598d23cac77e50cf302e6936b88b5eb6e558c2
ms.sourcegitcommit: fff146ba3fd1762c8c432d95c8b877825ae536fc
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/08/2020
ms.locfileid: "82976433"
---
# <a name="icordebugdatatarget2-interface"></a><span data-ttu-id="fe62d-102">ICorDebugDataTarget2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="fe62d-102">ICorDebugDataTarget2 Interface</span></span>
<span data-ttu-id="fe62d-103">Erweitert logisch die [ICorDebug DataTarget](icordebugdatatarget-interface.md)-Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="fe62d-103">Logically extends the [ICorDebugDataTarget](icordebugdatatarget-interface.md)interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="fe62d-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="fe62d-104">Methods</span></span>  
  
|<span data-ttu-id="fe62d-105">Methode</span><span class="sxs-lookup"><span data-stu-id="fe62d-105">Method</span></span>|<span data-ttu-id="fe62d-106">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="fe62d-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="fe62d-107">CreateVirtualUnwinder-Methode</span><span class="sxs-lookup"><span data-stu-id="fe62d-107">CreateVirtualUnwinder Method</span></span>](icordebugdatatarget2-createvirtualunwinder-method.md)|<span data-ttu-id="fe62d-108">Erstellt einen neuen Stapelentlader, der mit dem Entladen bei einem Anfangskontext beginnt (welcher nicht unbedingt das Blatt eines Threads ist).</span><span class="sxs-lookup"><span data-stu-id="fe62d-108">Creates a new stack unwinder that starts unwinding from an initial context (which isn't necessarily the leaf of a thread).</span></span>|  
|[<span data-ttu-id="fe62d-109">EnumerateThreadIDs-Methode</span><span class="sxs-lookup"><span data-stu-id="fe62d-109">EnumerateThreadIDs Method</span></span>](icordebugdatatarget2-enumeratethreadids-method.md)|<span data-ttu-id="fe62d-110">Gibt eine Liste der aktiven Thread-IDs aus.</span><span class="sxs-lookup"><span data-stu-id="fe62d-110">Returns a list of active thread IDs.</span></span>|  
|[<span data-ttu-id="fe62d-111">GetImageFromPointer-Methode</span><span class="sxs-lookup"><span data-stu-id="fe62d-111">GetImageFromPointer Method</span></span>](icordebugdatatarget2-getimagefrompointer-method.md)|<span data-ttu-id="fe62d-112">Gibt die Basisadresse des Moduls und die Größe von einer Adresse in diesem Modul aus.</span><span class="sxs-lookup"><span data-stu-id="fe62d-112">Returns the module base address and size from an address in that module.</span></span>|  
|[<span data-ttu-id="fe62d-113">GetImageLocation-Methode</span><span class="sxs-lookup"><span data-stu-id="fe62d-113">GetImageLocation Method</span></span>](icordebugdatatarget2-getimagelocation-method.md)|<span data-ttu-id="fe62d-114">Gibt den Pfad eines Moduls aus der Basisadresse des Moduls zurück.</span><span class="sxs-lookup"><span data-stu-id="fe62d-114">Returns the path of a module from the module's base address.</span></span>|  
|[<span data-ttu-id="fe62d-115">GetSymbolProviderForImage-Methode</span><span class="sxs-lookup"><span data-stu-id="fe62d-115">GetSymbolProviderForImage Method</span></span>](icordebugdatatarget2-getsymbolproviderforimage-method.md)|<span data-ttu-id="fe62d-116">Gibt anhand der Basisadresse des Moduls den Symbol-Anbieter für ein Modul aus.</span><span class="sxs-lookup"><span data-stu-id="fe62d-116">Returns the symbol-provider for a module from the base address of that module.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="fe62d-117">Hinweise</span><span class="sxs-lookup"><span data-stu-id="fe62d-117">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="fe62d-118">Diese Schnittstelle ist nur in Verbindung mit .NET Native verfügbar.</span><span class="sxs-lookup"><span data-stu-id="fe62d-118">This interface is available with .NET Native only.</span></span> <span data-ttu-id="fe62d-119">Wenn Sie diese Schnittstelle für ICorDebug-Szenarien außerhalb von .NET Native implementieren, ignoriert die Common Language Runtime diese Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="fe62d-119">If you implement this interface for ICorDebug scenarios outside of .NET Native, the common language runtime will ignore this interface.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fe62d-120">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="fe62d-120">Requirements</span></span>  
 <span data-ttu-id="fe62d-121">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="fe62d-121">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fe62d-122">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="fe62d-122">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="fe62d-123">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="fe62d-123">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="fe62d-124">**.NET Framework Versionen:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fe62d-124">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fe62d-125">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="fe62d-125">See also</span></span>

- [<span data-ttu-id="fe62d-126">Debugschnittstellen</span><span class="sxs-lookup"><span data-stu-id="fe62d-126">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="fe62d-127">Debuggen</span><span class="sxs-lookup"><span data-stu-id="fe62d-127">Debugging</span></span>](index.md)
