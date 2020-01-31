---
title: ICorDebugStaticFieldSymbol-Schnittstelle
ms.date: 03/30/2017
ms.assetid: c0b93609-631e-4b15-878a-189ede922631
ms.openlocfilehash: b50b9c8435f19e1a77229f01dc85514f5f75c9f5
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/28/2020
ms.locfileid: "76791804"
---
# <a name="icordebugstaticfieldsymbol-interface"></a><span data-ttu-id="f4c20-102">ICorDebugStaticFieldSymbol-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="f4c20-102">ICorDebugStaticFieldSymbol Interface</span></span>
<span data-ttu-id="f4c20-103">Stellt die Debugsymbolinformationen für ein statisches Feld dar.</span><span class="sxs-lookup"><span data-stu-id="f4c20-103">Represents the debug symbol information for a static field.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="f4c20-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="f4c20-104">Methods</span></span>  
  
|<span data-ttu-id="f4c20-105">-Methode</span><span class="sxs-lookup"><span data-stu-id="f4c20-105">Method</span></span>|<span data-ttu-id="f4c20-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="f4c20-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="f4c20-107">GetAddress-Methode</span><span class="sxs-lookup"><span data-stu-id="f4c20-107">GetAddress Method</span></span>](icordebugstaticfieldsymbol-getaddress-method.md)|<span data-ttu-id="f4c20-108">Ruft die Adresse des statischen Felds ab.</span><span class="sxs-lookup"><span data-stu-id="f4c20-108">Gets the address of the static field.</span></span>|  
|[<span data-ttu-id="f4c20-109">GetName-Methode</span><span class="sxs-lookup"><span data-stu-id="f4c20-109">GetName Method</span></span>](icordebugstaticfieldsymbol-getname-method.md)|<span data-ttu-id="f4c20-110">Ruft den Namen des statischen Felds ab.</span><span class="sxs-lookup"><span data-stu-id="f4c20-110">Gets the name of the static field.</span></span>|  
|[<span data-ttu-id="f4c20-111">GetSize-Methode</span><span class="sxs-lookup"><span data-stu-id="f4c20-111">GetSize Method</span></span>](icordebugstaticfieldsymbol-getsize-method.md)|<span data-ttu-id="f4c20-112">Ruft die Größe des statischen Felds in Bytes ab.</span><span class="sxs-lookup"><span data-stu-id="f4c20-112">Gets the size in bytes of the static field.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f4c20-113">Hinweise</span><span class="sxs-lookup"><span data-stu-id="f4c20-113">Remarks</span></span>  
 <span data-ttu-id="f4c20-114">Die `ICorDebugStaticFieldSymbol`-Schnittstelle wird verwendet, um Debugsymbolinformationen für ein statisches Feld abzurufen.</span><span class="sxs-lookup"><span data-stu-id="f4c20-114">The `ICorDebugStaticFieldSymbol` interface is used to retrieve the debug symbol information for a static field.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="f4c20-115">Diese Schnittstelle ist nur in Verbindung mit .NET Native verfügbar.</span><span class="sxs-lookup"><span data-stu-id="f4c20-115">This interface is available with .NET Native only.</span></span> <span data-ttu-id="f4c20-116">Wenn Sie diese Schnittstelle für ICorDebug-Szenarien außerhalb von .NET Native implementieren, ignoriert die Common Language Runtime diese Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="f4c20-116">If you implement this interface for ICorDebug scenarios outside of .NET Native, the common language runtime will ignore this interface.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f4c20-117">-Anforderungen</span><span class="sxs-lookup"><span data-stu-id="f4c20-117">Requirements</span></span>  
 <span data-ttu-id="f4c20-118">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f4c20-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f4c20-119">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="f4c20-119">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="f4c20-120">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f4c20-120">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f4c20-121">**.NET Framework Versionen:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f4c20-121">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f4c20-122">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f4c20-122">See also</span></span>

- [<span data-ttu-id="f4c20-123">ICorDebugInstanceFieldSymbol-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="f4c20-123">ICorDebugInstanceFieldSymbol Interface</span></span>](icordebuginstancefieldsymbol-interface.md)
- [<span data-ttu-id="f4c20-124">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="f4c20-124">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="f4c20-125">Debuggen</span><span class="sxs-lookup"><span data-stu-id="f4c20-125">Debugging</span></span>](index.md)
