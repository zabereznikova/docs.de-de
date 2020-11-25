---
title: ICorDebugInstanceFieldSymbol-Schnittstelle
ms.date: 03/30/2017
ms.assetid: a4a8f259-b83a-4425-ae8b-72b067dbc0d9
ms.openlocfilehash: 4ef0f7a46acf7e9df732d630c9eb22044e09d658
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95724896"
---
# <a name="icordebuginstancefieldsymbol-interface"></a><span data-ttu-id="71181-102">ICorDebugInstanceFieldSymbol-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="71181-102">ICorDebugInstanceFieldSymbol Interface</span></span>

<span data-ttu-id="71181-103">Stellt die Debugsymbolinformationen für ein Instanzfeld dar.</span><span class="sxs-lookup"><span data-stu-id="71181-103">Represents the debug symbol information for an instance field.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="71181-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="71181-104">Methods</span></span>  
  
|<span data-ttu-id="71181-105">Methode</span><span class="sxs-lookup"><span data-stu-id="71181-105">Method</span></span>|<span data-ttu-id="71181-106">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="71181-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="71181-107">GetName-Methode</span><span class="sxs-lookup"><span data-stu-id="71181-107">GetName Method</span></span>](icordebuginstancefieldsymbol-getname-method.md)|<span data-ttu-id="71181-108">Ruft den Namen des Instanzfelds ab.</span><span class="sxs-lookup"><span data-stu-id="71181-108">Gets the name of the instance field.</span></span>|  
|[<span data-ttu-id="71181-109">GetOffset-Methode</span><span class="sxs-lookup"><span data-stu-id="71181-109">GetOffset Method</span></span>](icordebuginstancefieldsymbol-getoffset-method.md)|<span data-ttu-id="71181-110">Ruft den Offset dieses Instanzenfelds in der übergeordneten Klasse in Bytes ab.</span><span class="sxs-lookup"><span data-stu-id="71181-110">Gets the offset in bytes of this instance field in its parent class.</span></span>|  
|[<span data-ttu-id="71181-111">GetSize-Methode</span><span class="sxs-lookup"><span data-stu-id="71181-111">GetSize Method</span></span>](icordebuginstancefieldsymbol-getsize-method.md)|<span data-ttu-id="71181-112">Ruft die Größe des Instanzfelds in Bytes ab.</span><span class="sxs-lookup"><span data-stu-id="71181-112">Gets the size in bytes of the instance field.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="71181-113">Hinweise</span><span class="sxs-lookup"><span data-stu-id="71181-113">Remarks</span></span>  

 <span data-ttu-id="71181-114">Die `ICorDebugInstanceFieldSymbol`-Schnittstelle wird verwendet, um Debugsymbolinformationen für ein Instanzfeld abzurufen.</span><span class="sxs-lookup"><span data-stu-id="71181-114">The `ICorDebugInstanceFieldSymbol` interface is used to retrieve the debug symbol information for an instance field.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="71181-115">Diese Schnittstelle ist nur in Verbindung mit .NET Native verfügbar.</span><span class="sxs-lookup"><span data-stu-id="71181-115">This interface is available with .NET Native only.</span></span> <span data-ttu-id="71181-116">Wenn Sie diese Schnittstelle für ICorDebug-Szenarien außerhalb von .NET Native implementieren, ignoriert die Common Language Runtime diese Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="71181-116">If you implement this interface for ICorDebug scenarios outside of .NET Native, the common language runtime will ignore this interface.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="71181-117">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="71181-117">Requirements</span></span>  

 <span data-ttu-id="71181-118">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="71181-118">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="71181-119">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="71181-119">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="71181-120">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="71181-120">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="71181-121">**.NET Framework Versionen:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="71181-121">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="71181-122">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="71181-122">See also</span></span>

- [<span data-ttu-id="71181-123">ICorDebugStaticFieldSymbol-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="71181-123">ICorDebugStaticFieldSymbol Interface</span></span>](icordebugstaticfieldsymbol-interface.md)
- [<span data-ttu-id="71181-124">Debugschnittstellen</span><span class="sxs-lookup"><span data-stu-id="71181-124">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="71181-125">Debuggen</span><span class="sxs-lookup"><span data-stu-id="71181-125">Debugging</span></span>](index.md)
