---
title: ICorDebugInstanceFieldSymbol-Schnittstelle
ms.date: 03/30/2017
ms.assetid: a4a8f259-b83a-4425-ae8b-72b067dbc0d9
ms.openlocfilehash: 092f2a8acdffa9f91176bdf0ca10b8db9cff6d37
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/12/2020
ms.locfileid: "83209928"
---
# <a name="icordebuginstancefieldsymbol-interface"></a><span data-ttu-id="39f2e-102">ICorDebugInstanceFieldSymbol-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="39f2e-102">ICorDebugInstanceFieldSymbol Interface</span></span>
<span data-ttu-id="39f2e-103">Stellt die Debugsymbolinformationen für ein Instanzfeld dar.</span><span class="sxs-lookup"><span data-stu-id="39f2e-103">Represents the debug symbol information for an instance field.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="39f2e-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="39f2e-104">Methods</span></span>  
  
|<span data-ttu-id="39f2e-105">Methode</span><span class="sxs-lookup"><span data-stu-id="39f2e-105">Method</span></span>|<span data-ttu-id="39f2e-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="39f2e-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="39f2e-107">GetName-Methode</span><span class="sxs-lookup"><span data-stu-id="39f2e-107">GetName Method</span></span>](icordebuginstancefieldsymbol-getname-method.md)|<span data-ttu-id="39f2e-108">Ruft den Namen des Instanzfelds ab.</span><span class="sxs-lookup"><span data-stu-id="39f2e-108">Gets the name of the instance field.</span></span>|  
|[<span data-ttu-id="39f2e-109">GetOffset-Methode</span><span class="sxs-lookup"><span data-stu-id="39f2e-109">GetOffset Method</span></span>](icordebuginstancefieldsymbol-getoffset-method.md)|<span data-ttu-id="39f2e-110">Ruft den Offset dieses Instanzenfelds in der übergeordneten Klasse in Bytes ab.</span><span class="sxs-lookup"><span data-stu-id="39f2e-110">Gets the offset in bytes of this instance field in its parent class.</span></span>|  
|[<span data-ttu-id="39f2e-111">GetSize-Methode</span><span class="sxs-lookup"><span data-stu-id="39f2e-111">GetSize Method</span></span>](icordebuginstancefieldsymbol-getsize-method.md)|<span data-ttu-id="39f2e-112">Ruft die Größe des Instanzfelds in Bytes ab.</span><span class="sxs-lookup"><span data-stu-id="39f2e-112">Gets the size in bytes of the instance field.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="39f2e-113">Hinweise</span><span class="sxs-lookup"><span data-stu-id="39f2e-113">Remarks</span></span>  
 <span data-ttu-id="39f2e-114">Die `ICorDebugInstanceFieldSymbol`-Schnittstelle wird verwendet, um Debugsymbolinformationen für ein Instanzfeld abzurufen.</span><span class="sxs-lookup"><span data-stu-id="39f2e-114">The `ICorDebugInstanceFieldSymbol` interface is used to retrieve the debug symbol information for an instance field.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="39f2e-115">Diese Schnittstelle ist nur in Verbindung mit .NET Native verfügbar.</span><span class="sxs-lookup"><span data-stu-id="39f2e-115">This interface is available with .NET Native only.</span></span> <span data-ttu-id="39f2e-116">Wenn Sie diese Schnittstelle für ICorDebug-Szenarien außerhalb von .NET Native implementieren, ignoriert die Common Language Runtime diese Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="39f2e-116">If you implement this interface for ICorDebug scenarios outside of .NET Native, the common language runtime will ignore this interface.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="39f2e-117">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="39f2e-117">Requirements</span></span>  
 <span data-ttu-id="39f2e-118">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="39f2e-118">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="39f2e-119">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="39f2e-119">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="39f2e-120">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="39f2e-120">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="39f2e-121">**.NET Framework Versionen:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="39f2e-121">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="39f2e-122">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="39f2e-122">See also</span></span>

- [<span data-ttu-id="39f2e-123">ICorDebugStaticFieldSymbol-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="39f2e-123">ICorDebugStaticFieldSymbol Interface</span></span>](icordebugstaticfieldsymbol-interface.md)
- [<span data-ttu-id="39f2e-124">Debugschnittstellen</span><span class="sxs-lookup"><span data-stu-id="39f2e-124">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="39f2e-125">Debuggen</span><span class="sxs-lookup"><span data-stu-id="39f2e-125">Debugging</span></span>](index.md)
