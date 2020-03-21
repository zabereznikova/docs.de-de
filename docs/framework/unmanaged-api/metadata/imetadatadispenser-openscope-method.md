---
title: IMetaDataDispenser::OpenScope-Methode
ms.date: 03/30/2017
api_name:
- IMetaDataDispenser.OpenScope
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataDispenser::OpenScope
helpviewer_keywords:
- IMetaDataDispenser::OpenScope method [.NET Framework metadata]
- OpenScope method, IMetaDataDispenser interface [.NET Framework metadata]
ms.assetid: 65063ad5-e0d9-4c01-8f8b-9a5950109fa6
topic_type:
- apiref
ms.openlocfilehash: 5185fb6663910c85ce5dae1225b9b10c5dd8bb28
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79175940"
---
# <a name="imetadatadispenseropenscope-method"></a><span data-ttu-id="2cbf5-102">IMetaDataDispenser::OpenScope-Methode</span><span class="sxs-lookup"><span data-stu-id="2cbf5-102">IMetaDataDispenser::OpenScope Method</span></span>
<span data-ttu-id="2cbf5-103">Öffnet eine vorhandene Datei auf der Festplatte und ordnet ihre Metadaten dem Speicher zu.</span><span class="sxs-lookup"><span data-stu-id="2cbf5-103">Opens an existing, on-disk file and maps its metadata into memory.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2cbf5-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="2cbf5-104">Syntax</span></span>  
  
```cpp  
HRESULT OpenScope (  
    [in]  LPCWSTR     szScope,
    [in]  DWORD       dwOpenFlags,
    [in]  REFIID      riid,
    [out] IUnknown    **ppIUnk  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2cbf5-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="2cbf5-105">Parameters</span></span>  
 `szScope`  
 <span data-ttu-id="2cbf5-106">[in] Der Name der zu öffnenden Datei.</span><span class="sxs-lookup"><span data-stu-id="2cbf5-106">[in] The name of the file to be opened.</span></span> <span data-ttu-id="2cbf5-107">Die Datei muss CLR-Metadaten (Common Language Runtime) enthalten.</span><span class="sxs-lookup"><span data-stu-id="2cbf5-107">The file must contain common language runtime (CLR) metadata.</span></span>  
  
 `dwOpenFlags`  
 <span data-ttu-id="2cbf5-108">[in] Ein Wert der CorOpenFlags-Enumeration, um den Modus (Lesen, Schreiben usw.) zum Öffnen anzugeben. [CorOpenFlags](../../../../docs/framework/unmanaged-api/metadata/coropenflags-enumeration.md)</span><span class="sxs-lookup"><span data-stu-id="2cbf5-108">[in] A value of the [CorOpenFlags](../../../../docs/framework/unmanaged-api/metadata/coropenflags-enumeration.md) enumeration to specify the mode (read, write, and so on) for opening.</span></span>  
  
 `riid`  
 <span data-ttu-id="2cbf5-109">[in] Die IID der gewünschten Metadatenschnittstelle, die zurückgegeben werden soll; Der Aufrufer verwendet die Schnittstelle, um Metadaten zu importieren (lesen) oder auszusenden (schreiben).</span><span class="sxs-lookup"><span data-stu-id="2cbf5-109">[in] The IID of the desired metadata interface to be returned; the caller will use the interface to import (read) or emit (write) metadata.</span></span>  
  
 <span data-ttu-id="2cbf5-110">Der Wert `riid` von muss eine der Schnittstellen "import" oder "emit" angeben.</span><span class="sxs-lookup"><span data-stu-id="2cbf5-110">The value of `riid` must specify one of the "import" or "emit" interfaces.</span></span> <span data-ttu-id="2cbf5-111">Gültige Werte sind IID_IMetaDataEmit, IID_IMetaDataImport, IID_IMetaDataAssemblyEmit, IID_IMetaDataAssemblyImport, IID_IMetaDataEmit2 oder IID_IMetaDataImport2.</span><span class="sxs-lookup"><span data-stu-id="2cbf5-111">Valid values are IID_IMetaDataEmit, IID_IMetaDataImport, IID_IMetaDataAssemblyEmit, IID_IMetaDataAssemblyImport, IID_IMetaDataEmit2, or IID_IMetaDataImport2.</span></span>  
  
 `ppIUnk`  
 <span data-ttu-id="2cbf5-112">[out] Der Zeiger auf die zurückgegebene Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="2cbf5-112">[out] The pointer to the returned interface.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2cbf5-113">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="2cbf5-113">Remarks</span></span>  
 <span data-ttu-id="2cbf5-114">Die In-Memory-Kopie der Metadaten kann mithilfe von Methoden von einer der "Import"-Schnittstellen abgefragt oder mit Methoden aus einer der "emit"-Schnittstellen hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="2cbf5-114">The in-memory copy of the metadata can be queried using methods from one of the "import" interfaces, or added to using methods from the one of the "emit" interfaces.</span></span>  
  
 <span data-ttu-id="2cbf5-115">Wenn die Zieldatei keine CLR-Metadaten enthält, schlägt die `OpenScope` Methode fehl.</span><span class="sxs-lookup"><span data-stu-id="2cbf5-115">If the target file does not contain CLR metadata, the `OpenScope` method will fail.</span></span>  
  
 <span data-ttu-id="2cbf5-116">Wenn in .NET Framework Version 1.0 und Version 1.1 ein Bereich mit `dwOpenFlags` Satz auf Read geöffnet wird, kann er freigegeben werden.</span><span class="sxs-lookup"><span data-stu-id="2cbf5-116">In the .NET Framework version 1.0 and version 1.1, if a scope is opened with `dwOpenFlags` set to ofRead, it is eligible for sharing.</span></span> <span data-ttu-id="2cbf5-117">Das heißt, wenn `OpenScope` nachfolgende Aufrufe im Namen einer zuvor geöffneten Datei übergeben werden, wird der vorhandene Bereich wiederverwendet, und es wird kein neuer Satz von Datenstrukturen erstellt.</span><span class="sxs-lookup"><span data-stu-id="2cbf5-117">That is, if subsequent calls to `OpenScope` pass in the name of a file that was previously opened, the existing scope is reused and a new set of data structures is not created.</span></span> <span data-ttu-id="2cbf5-118">Aufgrund dieser Freigabe können jedoch Probleme auftreten.</span><span class="sxs-lookup"><span data-stu-id="2cbf5-118">However, problems can arise due to this sharing.</span></span>  
  
 <span data-ttu-id="2cbf5-119">In .NET Framework Version 2.0 werden `dwOpenFlags` Bereiche, die mit Set auf Read geöffnet wurden, nicht mehr freigegeben.</span><span class="sxs-lookup"><span data-stu-id="2cbf5-119">In the .NET Framework version 2.0, scopes opened with `dwOpenFlags` set to ofRead are no longer shared.</span></span> <span data-ttu-id="2cbf5-120">Verwenden Sie den Wert ofReadOnly, damit der Bereich freigegeben werden kann.</span><span class="sxs-lookup"><span data-stu-id="2cbf5-120">Use the ofReadOnly value to allow the scope to be shared.</span></span> <span data-ttu-id="2cbf5-121">Wenn ein Bereich freigegeben wird, schlagen Abfragen fehl, die "Lese-/Schreib"-Metadatenschnittstellen verwenden.</span><span class="sxs-lookup"><span data-stu-id="2cbf5-121">When a scope is shared, queries that use "read/write" metadata interfaces will fail.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2cbf5-122">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="2cbf5-122">Requirements</span></span>  
 <span data-ttu-id="2cbf5-123">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2cbf5-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2cbf5-124">**Kopfzeile:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="2cbf5-124">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="2cbf5-125">**Bibliothek:** Wird als Ressource in MsCorEE.dll verwendet</span><span class="sxs-lookup"><span data-stu-id="2cbf5-125">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="2cbf5-126">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2cbf5-126">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2cbf5-127">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="2cbf5-127">See also</span></span>

- [<span data-ttu-id="2cbf5-128">IMetaDataDispenser-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="2cbf5-128">IMetaDataDispenser Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-interface.md)
- [<span data-ttu-id="2cbf5-129">IMetaDataDispenserEx-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="2cbf5-129">IMetaDataDispenserEx Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenserex-interface.md)
- [<span data-ttu-id="2cbf5-130">IMetaDataAssemblyEmit-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="2cbf5-130">IMetaDataAssemblyEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md)
- [<span data-ttu-id="2cbf5-131">IMetaDataAssemblyImport-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="2cbf5-131">IMetaDataAssemblyImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md)
- [<span data-ttu-id="2cbf5-132">IMetaDataEmit-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="2cbf5-132">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="2cbf5-133">IMetaDataEmit2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="2cbf5-133">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
- [<span data-ttu-id="2cbf5-134">IMetaDataImport-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="2cbf5-134">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="2cbf5-135">IMetaDataImport2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="2cbf5-135">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
