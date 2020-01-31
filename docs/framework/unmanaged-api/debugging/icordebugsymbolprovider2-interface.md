---
title: ICorDebugSymbolProvider2-Schnittstelle
ms.date: 03/30/2017
ms.assetid: 1c9c3d92-f0de-4d4d-87f1-0c702a4808af
ms.openlocfilehash: ca5bb822be515c936560eb4888c72ea306888ff3
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/28/2020
ms.locfileid: "76791490"
---
# <a name="icordebugsymbolprovider2-interface"></a><span data-ttu-id="29d72-102">ICorDebugSymbolProvider2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="29d72-102">ICorDebugSymbolProvider2 Interface</span></span>
<span data-ttu-id="29d72-103">Erweitert logisch die [icordebugsymbolprovider](icordebugsymbolprovider-interface.md) -Schnittstelle, um zusätzliche Debugsymbolinformationen abzurufen.</span><span class="sxs-lookup"><span data-stu-id="29d72-103">Logically extends the [ICorDebugSymbolProvider](icordebugsymbolprovider-interface.md) interface to retrieve additional debug symbol information.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="29d72-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="29d72-104">Methods</span></span>  
  
|<span data-ttu-id="29d72-105">-Methode</span><span class="sxs-lookup"><span data-stu-id="29d72-105">Method</span></span>|<span data-ttu-id="29d72-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="29d72-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="29d72-107">GetFrameProps-Methode</span><span class="sxs-lookup"><span data-stu-id="29d72-107">GetFrameProps Method</span></span>](icordebugsymbolprovider2-getframeprops-method.md)|<span data-ttu-id="29d72-108">Gibt die relative virtuelle Startadresse einer Methode und den übergeordneten Frame zurück, wenn eine coderelative virtuelle Adresse angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="29d72-108">Returns the method starting relative virtual address of a method and the parent frame given a code relative virtual address.</span></span>|  
|[<span data-ttu-id="29d72-109">GetGenericDictionaryInfo-Methode</span><span class="sxs-lookup"><span data-stu-id="29d72-109">GetGenericDictionaryInfo Method</span></span>](icordebugsymbolprovider2-getgenericdictionaryinfo-method.md)|<span data-ttu-id="29d72-110">Ruft eine generische Wörterbuchzuordnung ab.</span><span class="sxs-lookup"><span data-stu-id="29d72-110">Retrieves a generic dictionary map.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="29d72-111">Hinweise</span><span class="sxs-lookup"><span data-stu-id="29d72-111">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="29d72-112">Diese Schnittstelle ist nur in Verbindung mit .NET Native verfügbar.</span><span class="sxs-lookup"><span data-stu-id="29d72-112">This interface is available with .NET Native only.</span></span> <span data-ttu-id="29d72-113">Wenn Sie diese Schnittstelle für ICorDebug-Szenarien außerhalb von .NET Native implementieren, ignoriert die Common Language Runtime diese Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="29d72-113">If you implement this interface for ICorDebug scenarios outside of .NET Native, the common language runtime will ignore this interface.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="29d72-114">-Anforderungen</span><span class="sxs-lookup"><span data-stu-id="29d72-114">Requirements</span></span>  
 <span data-ttu-id="29d72-115">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="29d72-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="29d72-116">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="29d72-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="29d72-117">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="29d72-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="29d72-118">**.NET Framework Versionen:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="29d72-118">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="29d72-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="29d72-119">See also</span></span>

- [<span data-ttu-id="29d72-120">ICorDebugSymbolProvider-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="29d72-120">ICorDebugSymbolProvider Interface</span></span>](icordebugsymbolprovider-interface.md)
- [<span data-ttu-id="29d72-121">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="29d72-121">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="29d72-122">Debuggen</span><span class="sxs-lookup"><span data-stu-id="29d72-122">Debugging</span></span>](index.md)
