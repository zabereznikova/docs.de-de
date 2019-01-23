---
title: ICorDebugSymbolProvider2-Schnittstelle
ms.date: 03/30/2017
ms.assetid: 1c9c3d92-f0de-4d4d-87f1-0c702a4808af
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: ea60ecd542300bf3833c4977b7f0910399a2e409
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54504027"
---
# <a name="icordebugsymbolprovider2-interface"></a><span data-ttu-id="ae1bd-102">ICorDebugSymbolProvider2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="ae1bd-102">ICorDebugSymbolProvider2 Interface</span></span>
<span data-ttu-id="ae1bd-103">Erweitert logisch die [ICorDebugSymbolProvider](../../../../docs/framework/unmanaged-api/debugging/icordebugsymbolprovider-interface.md) Schnittstelle, um zusätzliche Debugsymbolinformationen abzurufen.</span><span class="sxs-lookup"><span data-stu-id="ae1bd-103">Logically extends the [ICorDebugSymbolProvider](../../../../docs/framework/unmanaged-api/debugging/icordebugsymbolprovider-interface.md) interface to retrieve additional debug symbol information.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="ae1bd-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="ae1bd-104">Methods</span></span>  
  
|<span data-ttu-id="ae1bd-105">Methode</span><span class="sxs-lookup"><span data-stu-id="ae1bd-105">Method</span></span>|<span data-ttu-id="ae1bd-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="ae1bd-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="ae1bd-107">GetFrameProps-Methode</span><span class="sxs-lookup"><span data-stu-id="ae1bd-107">GetFrameProps Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugsymbolprovider2-getframeprops-method.md)|<span data-ttu-id="ae1bd-108">Gibt die relative virtuelle Startadresse einer Methode und den übergeordneten Frame zurück, wenn eine coderelative virtuelle Adresse angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="ae1bd-108">Returns the method starting relative virtual address of a method and the parent frame given a code relative virtual address.</span></span>|  
|[<span data-ttu-id="ae1bd-109">GetGenericDictionaryInfo-Methode</span><span class="sxs-lookup"><span data-stu-id="ae1bd-109">GetGenericDictionaryInfo Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugsymbolprovider2-getgenericdictionaryinfo-method.md)|<span data-ttu-id="ae1bd-110">Ruft eine generische Wörterbuchzuordnung ab.</span><span class="sxs-lookup"><span data-stu-id="ae1bd-110">Retrieves a generic dictionary map.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ae1bd-111">Hinweise</span><span class="sxs-lookup"><span data-stu-id="ae1bd-111">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="ae1bd-112">Diese Schnittstelle ist nur in Verbindung mit .NET Native verfügbar.</span><span class="sxs-lookup"><span data-stu-id="ae1bd-112">This interface is available with .NET Native only.</span></span> <span data-ttu-id="ae1bd-113">Wenn Sie diese Schnittstelle für ICorDebug-Szenarien außerhalb von .NET Native implementieren, ignoriert die Common Language Runtime diese Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="ae1bd-113">If you implement this interface for ICorDebug scenarios outside of .NET Native, the common language runtime will ignore this interface.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ae1bd-114">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="ae1bd-114">Requirements</span></span>  
 <span data-ttu-id="ae1bd-115">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ae1bd-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ae1bd-116">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="ae1bd-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="ae1bd-117">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ae1bd-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ae1bd-118">**.NET Framework-Versionen:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ae1bd-118">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ae1bd-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ae1bd-119">See also</span></span>
- [<span data-ttu-id="ae1bd-120">ICorDebugSymbolProvider-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="ae1bd-120">ICorDebugSymbolProvider Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugsymbolprovider-interface.md)
- [<span data-ttu-id="ae1bd-121">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="ae1bd-121">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="ae1bd-122">Debuggen</span><span class="sxs-lookup"><span data-stu-id="ae1bd-122">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
