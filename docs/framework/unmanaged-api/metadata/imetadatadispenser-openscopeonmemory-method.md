---
title: IMetaDataDispenser::OpenScopeOnMemory-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- IMetaDataDispenser.OpenScopeOnMemory
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataDispenser::OpenScopeOnMemory
helpviewer_keywords:
- OpenScopeOnMemory method [.NET Framework metadata]
- IMetaDataDispenser::OpenScopeOnMemory method [.NET Framework metadata]
ms.assetid: 14218249-bdec-48ae-b5fc-9f57f7ca8501
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 1d206863736387df04157ed752a6269b22a884b9
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="imetadatadispenseropenscopeonmemory-method"></a><span data-ttu-id="45073-102">IMetaDataDispenser::OpenScopeOnMemory-Methode</span><span class="sxs-lookup"><span data-stu-id="45073-102">IMetaDataDispenser::OpenScopeOnMemory Method</span></span>
<span data-ttu-id="45073-103">Öffnet einen Bereich des Arbeitsspeichers, die vorhandenen Metadaten enthält.</span><span class="sxs-lookup"><span data-stu-id="45073-103">Opens an area of memory that contains existing metadata.</span></span> <span data-ttu-id="45073-104">Diese Methode öffnet, also einen angegebenen Bereich des Arbeitsspeichers, in denen die vorhandenen Daten als Metadaten behandelt werden.</span><span class="sxs-lookup"><span data-stu-id="45073-104">That is, this method opens a specified area of memory in which the existing data is treated as metadata.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="45073-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="45073-105">Syntax</span></span>  
  
```  
HRESULT OpenScopeOnMemory (  
    [in]  LPCVOID     pData,   
    [in]  ULONG       cbData,   
    [in]  DWORD       dwOpenFlags,   
    [in]  REFIID      riid,   
    [out] IUnknown    **ppIUnk  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="45073-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="45073-106">Parameters</span></span>  
 `pData`  
 <span data-ttu-id="45073-107">[in] Ein Zeiger, der die Startadresse des Speicherbereichs angibt.</span><span class="sxs-lookup"><span data-stu-id="45073-107">[in] A pointer that specifies the starting address of the memory area.</span></span>  
  
 `cbData`  
 <span data-ttu-id="45073-108">[in] Die Größe des Arbeitsspeicherbereichs in Bytes.</span><span class="sxs-lookup"><span data-stu-id="45073-108">[in] The size of the memory area, in bytes.</span></span>  
  
 `dwOpenFlags`  
 <span data-ttu-id="45073-109">[in] Der Wert der [CorOpenFlags](../../../../docs/framework/unmanaged-api/metadata/coropenflags-enumeration.md) Enumeration zum Öffnen den Modus (Lesen, schreiben und so weiter) angeben.</span><span class="sxs-lookup"><span data-stu-id="45073-109">[in] A value of the [CorOpenFlags](../../../../docs/framework/unmanaged-api/metadata/coropenflags-enumeration.md) enumeration to specify the mode (read, write, and so on) for opening.</span></span>  
  
 `riid`  
 <span data-ttu-id="45073-110">[in] Die IID der Metadatenschnittstelle für die gewünschten zurückgegeben werden sollen; der Aufrufer verwendet die Schnittstelle zum Importieren (Lesen) oder Ausgeben von Metadaten (Schreiben).</span><span class="sxs-lookup"><span data-stu-id="45073-110">[in] The IID of the desired metadata interface to be returned; the caller will use the interface to import (read) or emit (write) metadata.</span></span>  
  
 <span data-ttu-id="45073-111">Der Wert des `riid` müssen eine der Schnittstellen "Import" oder "Ausgabe" angeben.</span><span class="sxs-lookup"><span data-stu-id="45073-111">The value of `riid` must specify one of the "import" or "emit" interfaces.</span></span> <span data-ttu-id="45073-112">Gültige Werte sind IID_IMetaDataEmit, IID_IMetaDataImport auf, IID_IMetaDataAssemblyEmit, IID_IMetaDataAssemblyImport, IID_IMetaDataEmit2 oder IID_IMetaDataImport2.</span><span class="sxs-lookup"><span data-stu-id="45073-112">Valid values are IID_IMetaDataEmit, IID_IMetaDataImport, IID_IMetaDataAssemblyEmit, IID_IMetaDataAssemblyImport, IID_IMetaDataEmit2, or IID_IMetaDataImport2.</span></span>  
  
 `ppIUnk`  
 <span data-ttu-id="45073-113">[out] Der Zeiger auf die zurückgegebene Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="45073-113">[out] The pointer to the returned interface.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="45073-114">Hinweise</span><span class="sxs-lookup"><span data-stu-id="45073-114">Remarks</span></span>  
 <span data-ttu-id="45073-115">Die in-Memory-Kopie der Metadaten kann abgefragt werden, mithilfe der Methoden aus einer der Schnittstellen "Importieren" oder mit Methoden aus dem der "Ausgabe"-Schnittstellen hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="45073-115">The in-memory copy of the metadata can be queried using methods from one of the "import" interfaces, or added to using methods from the one of the "emit" interfaces.</span></span>  
  
 <span data-ttu-id="45073-116">Die `OpenScopeOnMemory` Methode ist vergleichbar mit der [IMetaDataDispenser:: OpenScope](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-openscope-method.md) -Methode, mit dem Unterschied, dass die Metadaten von Interesse sind bereits im Arbeitsspeicher und nicht in einer Datei auf dem Datenträger vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="45073-116">The `OpenScopeOnMemory` method is similar to the [IMetaDataDispenser::OpenScope](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-openscope-method.md) method, except that the metadata of interest already exists in memory, rather than in a file on disk.</span></span>  
  
 <span data-ttu-id="45073-117">Wenn der Zielbereich des Arbeitsspeichers keine common Language Runtime (CLR)-Metadaten enthält die `OpenScopeOnMemory` Methode fehl.</span><span class="sxs-lookup"><span data-stu-id="45073-117">If the target area of memory does not contain common language runtime (CLR) metadata, the `OpenScopeOnMemory` method will fail.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="45073-118">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="45073-118">Requirements</span></span>  
 <span data-ttu-id="45073-119">**Plattform:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="45073-119">**Platform:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="45073-120">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="45073-120">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="45073-121">**Bibliothek:** als Ressource in MsCorEE.dll verwendet</span><span class="sxs-lookup"><span data-stu-id="45073-121">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="45073-122">**.NET Framework-Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="45073-122">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="45073-123">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="45073-123">See Also</span></span>  
 [<span data-ttu-id="45073-124">IMetaDataDispenser-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="45073-124">IMetaDataDispenser Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-interface.md)  
 [<span data-ttu-id="45073-125">IMetaDataDispenserEx-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="45073-125">IMetaDataDispenserEx Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenserex-interface.md)  
 [<span data-ttu-id="45073-126">IMetaDataAssemblyEmit-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="45073-126">IMetaDataAssemblyEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md)  
 [<span data-ttu-id="45073-127">IMetaDataAssemblyImport-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="45073-127">IMetaDataAssemblyImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md)  
 [<span data-ttu-id="45073-128">IMetaDataEmit-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="45073-128">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)  
 [<span data-ttu-id="45073-129">IMetaDataEmit2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="45073-129">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)  
 [<span data-ttu-id="45073-130">IMetaDataImport-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="45073-130">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)  
 [<span data-ttu-id="45073-131">IMetaDataImport2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="45073-131">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
