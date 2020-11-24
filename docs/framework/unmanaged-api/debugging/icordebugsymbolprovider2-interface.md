---
title: ICorDebugSymbolProvider2-Schnittstelle
ms.date: 03/30/2017
ms.assetid: 1c9c3d92-f0de-4d4d-87f1-0c702a4808af
ms.openlocfilehash: 3bef03e9e85224058bc17e1f0ce8746e98aa30f6
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95688340"
---
# <a name="icordebugsymbolprovider2-interface"></a><span data-ttu-id="195a6-102">ICorDebugSymbolProvider2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="195a6-102">ICorDebugSymbolProvider2 Interface</span></span>

<span data-ttu-id="195a6-103">Erweitert logisch die [icordebugsymbolprovider](icordebugsymbolprovider-interface.md) -Schnittstelle, um zusätzliche Debugsymbolinformationen abzurufen.</span><span class="sxs-lookup"><span data-stu-id="195a6-103">Logically extends the [ICorDebugSymbolProvider](icordebugsymbolprovider-interface.md) interface to retrieve additional debug symbol information.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="195a6-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="195a6-104">Methods</span></span>  
  
|<span data-ttu-id="195a6-105">Methode</span><span class="sxs-lookup"><span data-stu-id="195a6-105">Method</span></span>|<span data-ttu-id="195a6-106">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="195a6-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="195a6-107">GetFrameProps-Methode</span><span class="sxs-lookup"><span data-stu-id="195a6-107">GetFrameProps Method</span></span>](icordebugsymbolprovider2-getframeprops-method.md)|<span data-ttu-id="195a6-108">Gibt die relative virtuelle Startadresse einer Methode und den übergeordneten Frame zurück, wenn eine coderelative virtuelle Adresse angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="195a6-108">Returns the method starting relative virtual address of a method and the parent frame given a code relative virtual address.</span></span>|  
|[<span data-ttu-id="195a6-109">GetGenericDictionaryInfo-Methode</span><span class="sxs-lookup"><span data-stu-id="195a6-109">GetGenericDictionaryInfo Method</span></span>](icordebugsymbolprovider2-getgenericdictionaryinfo-method.md)|<span data-ttu-id="195a6-110">Ruft eine generische Wörterbuchzuordnung ab.</span><span class="sxs-lookup"><span data-stu-id="195a6-110">Retrieves a generic dictionary map.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="195a6-111">Hinweise</span><span class="sxs-lookup"><span data-stu-id="195a6-111">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="195a6-112">Diese Schnittstelle ist nur in Verbindung mit .NET Native verfügbar.</span><span class="sxs-lookup"><span data-stu-id="195a6-112">This interface is available with .NET Native only.</span></span> <span data-ttu-id="195a6-113">Wenn Sie diese Schnittstelle für ICorDebug-Szenarien außerhalb von .NET Native implementieren, ignoriert die Common Language Runtime diese Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="195a6-113">If you implement this interface for ICorDebug scenarios outside of .NET Native, the common language runtime will ignore this interface.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="195a6-114">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="195a6-114">Requirements</span></span>  

 <span data-ttu-id="195a6-115">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="195a6-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="195a6-116">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="195a6-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="195a6-117">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="195a6-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="195a6-118">**.NET Framework Versionen:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="195a6-118">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="195a6-119">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="195a6-119">See also</span></span>

- [<span data-ttu-id="195a6-120">ICorDebugSymbolProvider-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="195a6-120">ICorDebugSymbolProvider Interface</span></span>](icordebugsymbolprovider-interface.md)
- [<span data-ttu-id="195a6-121">Debugschnittstellen</span><span class="sxs-lookup"><span data-stu-id="195a6-121">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="195a6-122">Debuggen</span><span class="sxs-lookup"><span data-stu-id="195a6-122">Debugging</span></span>](index.md)
