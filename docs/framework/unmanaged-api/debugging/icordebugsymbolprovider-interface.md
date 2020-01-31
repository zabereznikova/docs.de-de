---
title: ICorDebugSymbolProvider-Schnittstelle
ms.date: 03/30/2017
ms.assetid: 85b24196-b6c6-4bda-9de3-47180bd6ff96
ms.openlocfilehash: 6f7a8a2b12c047b956a3b6e85fe8365e0360b3f2
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/28/2020
ms.locfileid: "76791531"
---
# <a name="icordebugsymbolprovider-interface"></a><span data-ttu-id="53940-102">ICorDebugSymbolProvider-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="53940-102">ICorDebugSymbolProvider Interface</span></span>
<span data-ttu-id="53940-103">Stellt Methoden bereit, die zum Abrufen von Debugsymbolinformationen verwendet werden können.</span><span class="sxs-lookup"><span data-stu-id="53940-103">Provides methods that can be used to retrieve debug symbol information.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="53940-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="53940-104">Methods</span></span>  
  
|<span data-ttu-id="53940-105">-Methode</span><span class="sxs-lookup"><span data-stu-id="53940-105">Method</span></span>|<span data-ttu-id="53940-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="53940-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="53940-107">GetAssemblyImageBytes-Methode</span><span class="sxs-lookup"><span data-stu-id="53940-107">GetAssemblyImageBytes Method</span></span>](icordebugsymbolprovider-getassemblyimagebytes-method.md)|<span data-ttu-id="53940-108">Liest Daten aus einer zusammengeführten Assembly, wenn eine relative virtuelle Adresse (RVA) in der zusammengeführten Assembly angegeben ist.</span><span class="sxs-lookup"><span data-stu-id="53940-108">Reads data from a merged assembly given a relative virtual address (RVA) in the merged assembly.</span></span>|  
|[<span data-ttu-id="53940-109">GetAssemblyImageMetadata-Methode</span><span class="sxs-lookup"><span data-stu-id="53940-109">GetAssemblyImageMetadata Method</span></span>](icordebugsymbolprovider-getassemblyimagemetadata-method.md)|<span data-ttu-id="53940-110">Gibt die Metadaten aus einer zusammengeführten Assembly zurück.</span><span class="sxs-lookup"><span data-stu-id="53940-110">Returns the metadata from a merged assembly.</span></span>|  
|[<span data-ttu-id="53940-111">GetCodeRange-Methode</span><span class="sxs-lookup"><span data-stu-id="53940-111">GetCodeRange Method</span></span>](icordebugsymbolprovider-getcoderange-method.md)|<span data-ttu-id="53940-112">Ruft die Startadresse und Größe einer Methode ab, wenn eine relative virtuelle Adresse (RVA) in der Methode angegeben ist.</span><span class="sxs-lookup"><span data-stu-id="53940-112">Gets the method start address and size given a relative virtual address (RVA) in a method.</span></span>|  
|[<span data-ttu-id="53940-113">GetInstanceFieldSymbols-Methode</span><span class="sxs-lookup"><span data-stu-id="53940-113">GetInstanceFieldSymbols Method</span></span>](icordebugsymbolprovider-getinstancefieldsymbols-method.md)|<span data-ttu-id="53940-114">Ruft die Instanzenfeldsymbole ab, die einer TypeSpec-Signatur entsprechen.</span><span class="sxs-lookup"><span data-stu-id="53940-114">Gets the instance field symbols that correspond to a typespec signature.</span></span>|  
|[<span data-ttu-id="53940-115">GetMergedAssemblyRecords-Methode</span><span class="sxs-lookup"><span data-stu-id="53940-115">GetMergedAssemblyRecords Method</span></span>](icordebugsymbolprovider-getmergedassemblyrecords-method.md)|<span data-ttu-id="53940-116">Ruft die Symboldatensätze für alle zusammengeführten Assemblys ab.</span><span class="sxs-lookup"><span data-stu-id="53940-116">Gets the symbol records for all the merged assemblies.</span></span>|  
|[<span data-ttu-id="53940-117">GetMethodLocalSymbols-Methode</span><span class="sxs-lookup"><span data-stu-id="53940-117">GetMethodLocalSymbols Method</span></span>](icordebugsymbolprovider-getmethodlocalsymbols-method.md)|<span data-ttu-id="53940-118">Ruft die lokalen Symbole einer Methode ab, wenn die relative virtuelle Adresse (RVA) der Methode angegeben ist.</span><span class="sxs-lookup"><span data-stu-id="53940-118">Gets a method's local symbols given the relative virtual address (RVA) of that method.</span></span>|  
|[<span data-ttu-id="53940-119">GetMethodParameterSymbols-Methode</span><span class="sxs-lookup"><span data-stu-id="53940-119">GetMethodParameterSymbols Method</span></span>](icordebugsymbolprovider-getmethodparametersymbols-method.md)|<span data-ttu-id="53940-120">Ruft die Parametersymbole einer Methode ab, wenn die relative virtuelle Adresse (RVA) der Methode angegeben ist.</span><span class="sxs-lookup"><span data-stu-id="53940-120">Gets a method's parameter symbols given the relative virtual address (RVA) of that method.</span></span>|  
|[<span data-ttu-id="53940-121">GetMethodProps-Methode</span><span class="sxs-lookup"><span data-stu-id="53940-121">GetMethodProps Method</span></span>](icordebugsymbolprovider-getmethodprops-method.md)|<span data-ttu-id="53940-122">Gibt Informationen zu Methodeneigenschaften wie das Metadatentoken der Methode und Informationen zu den generischen Parametern der Methode zurück, wenn eine relative virtuelle Adresse (RVA) in der Methode angegeben ist.</span><span class="sxs-lookup"><span data-stu-id="53940-122">Returns information about method properties, such as the method's metadata token and information about its generic parameters, given a relative virtual address (RVA) in that method.</span></span>|  
|[<span data-ttu-id="53940-123">GetObjectSize-Methode</span><span class="sxs-lookup"><span data-stu-id="53940-123">GetObjectSize Method</span></span>](icordebugsymbolprovider-getobjectsize-method.md)|<span data-ttu-id="53940-124">Gibt die Objektgröße eines Objekts basierend auf seiner TypeSpec-Signatur zurück.</span><span class="sxs-lookup"><span data-stu-id="53940-124">Returns the object size for an object based on its typespec signature.</span></span>|  
|[<span data-ttu-id="53940-125">GetStaticFieldSymbols-Methode</span><span class="sxs-lookup"><span data-stu-id="53940-125">GetStaticFieldSymbols Method</span></span>](icordebugsymbolprovider-getstaticfieldsymbols-method.md)|<span data-ttu-id="53940-126">Ruft die statischen Feldsymbole ab, die einer TypeSpec-Signatur entsprechen.</span><span class="sxs-lookup"><span data-stu-id="53940-126">Gets the static field symbols that correspond to a typespec signature.</span></span>|  
|[<span data-ttu-id="53940-127">GetTypeProps-Methode</span><span class="sxs-lookup"><span data-stu-id="53940-127">GetTypeProps Method</span></span>](icordebugsymbolprovider-gettypeprops-method.md)|<span data-ttu-id="53940-128">Gibt anhand einer relativen virtuellen Adresse (RVA) in einem VTable Informationen zu den Eigenschaften eines Typs wie die Anzahl der Signaturen der generischen Parameter zurück.</span><span class="sxs-lookup"><span data-stu-id="53940-128">Returns information about a type's properties, such as the number of signature of its generic parameters, given a relative virtual address (RVA) in a vtable.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="53940-129">Hinweise</span><span class="sxs-lookup"><span data-stu-id="53940-129">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="53940-130">Diese Schnittstelle ist nur in Verbindung mit .NET Native verfügbar.</span><span class="sxs-lookup"><span data-stu-id="53940-130">This interface is available with .NET Native only.</span></span> <span data-ttu-id="53940-131">Wenn Sie diese Schnittstelle für ICorDebug-Szenarien außerhalb von .NET Native implementieren, ignoriert die Common Language Runtime diese Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="53940-131">If you implement this interface for ICorDebug scenarios outside of .NET Native, the common language runtime will ignore this interface.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="53940-132">-Anforderungen</span><span class="sxs-lookup"><span data-stu-id="53940-132">Requirements</span></span>  
 <span data-ttu-id="53940-133">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="53940-133">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="53940-134">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="53940-134">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="53940-135">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="53940-135">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="53940-136">**.NET Framework Versionen:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="53940-136">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="53940-137">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="53940-137">See also</span></span>

- [<span data-ttu-id="53940-138">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="53940-138">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="53940-139">Debuggen</span><span class="sxs-lookup"><span data-stu-id="53940-139">Debugging</span></span>](index.md)
