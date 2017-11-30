---
title: ICorDebugSymbolProvider-Schnittstelle
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: 85b24196-b6c6-4bda-9de3-47180bd6ff96
caps.latest.revision: "4"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 96f5d897b1f426fd85fd274d5e56e8726b8cb892
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="icordebugsymbolprovider-interface"></a><span data-ttu-id="97748-102">ICorDebugSymbolProvider-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="97748-102">ICorDebugSymbolProvider Interface</span></span>
<span data-ttu-id="97748-103">Stellt Methoden bereit, die zum Abrufen von Debugsymbolinformationen verwendet werden können.</span><span class="sxs-lookup"><span data-stu-id="97748-103">Provides methods that can be used to retrieve debug symbol information.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="97748-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="97748-104">Methods</span></span>  
  
|<span data-ttu-id="97748-105">Methode</span><span class="sxs-lookup"><span data-stu-id="97748-105">Method</span></span>|<span data-ttu-id="97748-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="97748-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="97748-107">GetAssemblyImageBytes-Methode</span><span class="sxs-lookup"><span data-stu-id="97748-107">GetAssemblyImageBytes Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugsymbolprovider-getassemblyimagebytes-method.md)|<span data-ttu-id="97748-108">Liest Daten aus einer zusammengeführten Assembly, wenn eine relative virtuelle Adresse (RVA) in der zusammengeführten Assembly angegeben ist.</span><span class="sxs-lookup"><span data-stu-id="97748-108">Reads data from a merged assembly given a relative virtual address (RVA) in the merged assembly.</span></span>|  
|[<span data-ttu-id="97748-109">GetAssemblyImageMetadata-Methode</span><span class="sxs-lookup"><span data-stu-id="97748-109">GetAssemblyImageMetadata Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugsymbolprovider-getassemblyimagemetadata-method.md)|<span data-ttu-id="97748-110">Gibt die Metadaten aus einer zusammengeführten Assembly zurück.</span><span class="sxs-lookup"><span data-stu-id="97748-110">Returns the metadata from a merged assembly.</span></span>|  
|[<span data-ttu-id="97748-111">GetCodeRange-Methode</span><span class="sxs-lookup"><span data-stu-id="97748-111">GetCodeRange Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugsymbolprovider-getcoderange-method.md)|<span data-ttu-id="97748-112">Ruft die Startadresse und Größe einer Methode ab, wenn eine relative virtuelle Adresse (RVA) in der Methode angegeben ist.</span><span class="sxs-lookup"><span data-stu-id="97748-112">Gets the method start address and size given a relative virtual address (RVA) in a method.</span></span>|  
|[<span data-ttu-id="97748-113">GetInstanceFieldSymbols-Methode</span><span class="sxs-lookup"><span data-stu-id="97748-113">GetInstanceFieldSymbols Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugsymbolprovider-getinstancefieldsymbols-method.md)|<span data-ttu-id="97748-114">Ruft die Instanzenfeldsymbole ab, die einer TypeSpec-Signatur entsprechen.</span><span class="sxs-lookup"><span data-stu-id="97748-114">Gets the instance field symbols that correspond to a typespec signature.</span></span>|  
|[<span data-ttu-id="97748-115">GetMergedAssemblyRecords-Methode</span><span class="sxs-lookup"><span data-stu-id="97748-115">GetMergedAssemblyRecords Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugsymbolprovider-getmergedassemblyrecords-method.md)|<span data-ttu-id="97748-116">Ruft die Symboldatensätze für alle zusammengeführten Assemblys ab.</span><span class="sxs-lookup"><span data-stu-id="97748-116">Gets the symbol records for all the merged assemblies.</span></span>|  
|[<span data-ttu-id="97748-117">GetMethodLocalSymbols-Methode</span><span class="sxs-lookup"><span data-stu-id="97748-117">GetMethodLocalSymbols Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugsymbolprovider-getmethodlocalsymbols-method.md)|<span data-ttu-id="97748-118">Ruft die lokalen Symbole einer Methode ab, wenn die relative virtuelle Adresse (RVA) der Methode angegeben ist.</span><span class="sxs-lookup"><span data-stu-id="97748-118">Gets a method's local symbols given the relative virtual address (RVA) of that method.</span></span>|  
|[<span data-ttu-id="97748-119">GetMethodParameterSymbols-Methode</span><span class="sxs-lookup"><span data-stu-id="97748-119">GetMethodParameterSymbols Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugsymbolprovider-getmethodparametersymbols-method.md)|<span data-ttu-id="97748-120">Ruft die Parametersymbole einer Methode ab, wenn die relative virtuelle Adresse (RVA) der Methode angegeben ist.</span><span class="sxs-lookup"><span data-stu-id="97748-120">Gets a method's parameter symbols given the relative virtual address (RVA) of that method.</span></span>|  
|[<span data-ttu-id="97748-121">GetMethodProps-Methode</span><span class="sxs-lookup"><span data-stu-id="97748-121">GetMethodProps Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugsymbolprovider-getmethodprops-method.md)|<span data-ttu-id="97748-122">Gibt Informationen zu Methodeneigenschaften wie das Metadatentoken der Methode und Informationen zu den generischen Parametern der Methode zurück, wenn eine relative virtuelle Adresse (RVA) in der Methode angegeben ist.</span><span class="sxs-lookup"><span data-stu-id="97748-122">Returns information about method properties, such as the method's metadata token and information about its generic parameters, given a relative virtual address (RVA) in that method.</span></span>|  
|[<span data-ttu-id="97748-123">GetObjectSize-Methode</span><span class="sxs-lookup"><span data-stu-id="97748-123">GetObjectSize Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugsymbolprovider-getobjectsize-method.md)|<span data-ttu-id="97748-124">Gibt die Objektgröße eines Objekts basierend auf seiner TypeSpec-Signatur zurück.</span><span class="sxs-lookup"><span data-stu-id="97748-124">Returns the object size for an object based on its typespec signature.</span></span>|  
|[<span data-ttu-id="97748-125">GetStaticFieldSymbols-Methode</span><span class="sxs-lookup"><span data-stu-id="97748-125">GetStaticFieldSymbols Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugsymbolprovider-getstaticfieldsymbols-method.md)|<span data-ttu-id="97748-126">Ruft die statischen Feldsymbole ab, die einer typespec-Signatur entsprechen.</span><span class="sxs-lookup"><span data-stu-id="97748-126">Gets the static field symbols that correspond to a typespec signature.</span></span>|  
|[<span data-ttu-id="97748-127">GetTypeProps-Methode</span><span class="sxs-lookup"><span data-stu-id="97748-127">GetTypeProps Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugsymbolprovider-gettypeprops-method.md)|<span data-ttu-id="97748-128">Gibt Informationen zu den Eigenschaften eines Typs wie die Anzahl der Signaturen der generischen Parameter zurück, wenn eine relative virtuelle Adresse (RVA) in einer Vtable angegeben ist.</span><span class="sxs-lookup"><span data-stu-id="97748-128">Returns information about a type's properties, such as the number of signature of its generic parameters, given a relative virtual address (RVA) in a vtable.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="97748-129">Hinweise</span><span class="sxs-lookup"><span data-stu-id="97748-129">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="97748-130">Diese Schnittstelle ist nur in Verbindung mit .NET Native verfügbar.</span><span class="sxs-lookup"><span data-stu-id="97748-130">This interface is available with .NET Native only.</span></span> <span data-ttu-id="97748-131">Wenn Sie diese Schnittstelle für ICorDebug-Szenarien außerhalb von .NET Native implementieren, ignoriert die Common Language Runtime diese Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="97748-131">If you implement this interface for ICorDebug scenarios outside of .NET Native, the common language runtime will ignore this interface.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="97748-132">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="97748-132">Requirements</span></span>  
 <span data-ttu-id="97748-133">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="97748-133">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="97748-134">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="97748-134">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="97748-135">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="97748-135">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="97748-136">**.NET Framework-Versionen:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="97748-136">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="97748-137">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="97748-137">See Also</span></span>  
 [<span data-ttu-id="97748-138">Debugschnittstellen</span><span class="sxs-lookup"><span data-stu-id="97748-138">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [<span data-ttu-id="97748-139">Debuggen</span><span class="sxs-lookup"><span data-stu-id="97748-139">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
