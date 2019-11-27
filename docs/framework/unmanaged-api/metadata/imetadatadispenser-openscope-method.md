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
ms.openlocfilehash: 5ce1af82631531f8f7105fbf92ba78db3cca437b
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/23/2019
ms.locfileid: "74442332"
---
# <a name="imetadatadispenseropenscope-method"></a><span data-ttu-id="ad378-102">IMetaDataDispenser::OpenScope-Methode</span><span class="sxs-lookup"><span data-stu-id="ad378-102">IMetaDataDispenser::OpenScope Method</span></span>
<span data-ttu-id="ad378-103">Öffnet eine vorhandene Datei auf dem Datenträger und ordnet Ihre Metadaten dem Arbeitsspeicher zu.</span><span class="sxs-lookup"><span data-stu-id="ad378-103">Opens an existing, on-disk file and maps its metadata into memory.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ad378-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="ad378-104">Syntax</span></span>  
  
```cpp  
HRESULT OpenScope (  
    [in]  LPCWSTR     szScope,   
    [in]  DWORD       dwOpenFlags,   
    [in]  REFIID      riid,   
    [out] IUnknown    **ppIUnk  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ad378-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="ad378-105">Parameters</span></span>  
 `szScope`  
 <span data-ttu-id="ad378-106">in Der Name der Datei, die geöffnet werden soll.</span><span class="sxs-lookup"><span data-stu-id="ad378-106">[in] The name of the file to be opened.</span></span> <span data-ttu-id="ad378-107">Die Datei muss Common Language Runtime (CLR)-Metadaten enthalten.</span><span class="sxs-lookup"><span data-stu-id="ad378-107">The file must contain common language runtime (CLR) metadata.</span></span>  
  
 `dwOpenFlags`  
 <span data-ttu-id="ad378-108">in Ein Wert der [CorOpenFlags](../../../../docs/framework/unmanaged-api/metadata/coropenflags-enumeration.md) -Enumeration, mit dem der Modus (lesen, schreiben usw.) zum Öffnen angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="ad378-108">[in] A value of the [CorOpenFlags](../../../../docs/framework/unmanaged-api/metadata/coropenflags-enumeration.md) enumeration to specify the mode (read, write, and so on) for opening.</span></span>  
  
 `riid`  
 <span data-ttu-id="ad378-109">in Die IID der gewünschten Metadatenschnittstelle, die zurückgegeben werden soll. der Aufrufer verwendet die-Schnittstelle, um Metadaten zu importieren (lesen) oder auszugeben (schreiben).</span><span class="sxs-lookup"><span data-stu-id="ad378-109">[in] The IID of the desired metadata interface to be returned; the caller will use the interface to import (read) or emit (write) metadata.</span></span>  
  
 <span data-ttu-id="ad378-110">Der Wert `riid` muss eine der Schnittstellen "Import" oder "ausgeben" angeben.</span><span class="sxs-lookup"><span data-stu-id="ad378-110">The value of `riid` must specify one of the "import" or "emit" interfaces.</span></span> <span data-ttu-id="ad378-111">Gültige Werte sind IID_IMetaDataEmit, IID_IMetaDataImport, IID_IMetaDataAssemblyEmit, IID_IMetaDataAssemblyImport, IID_IMetaDataEmit2 oder IID_IMetaDataImport2.</span><span class="sxs-lookup"><span data-stu-id="ad378-111">Valid values are IID_IMetaDataEmit, IID_IMetaDataImport, IID_IMetaDataAssemblyEmit, IID_IMetaDataAssemblyImport, IID_IMetaDataEmit2, or IID_IMetaDataImport2.</span></span>  
  
 `ppIUnk`  
 <span data-ttu-id="ad378-112">vorgenommen Der Zeiger auf die zurückgegebene Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="ad378-112">[out] The pointer to the returned interface.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ad378-113">Hinweise</span><span class="sxs-lookup"><span data-stu-id="ad378-113">Remarks</span></span>  
 <span data-ttu-id="ad378-114">Die in-Memory-Kopie der Metadaten kann mithilfe von Methoden einer der "Import"-Schnittstellen abgefragt oder mithilfe von Methoden aus einer der "Ausgabe"-Schnittstellen hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="ad378-114">The in-memory copy of the metadata can be queried using methods from one of the "import" interfaces, or added to using methods from the one of the "emit" interfaces.</span></span>  
  
 <span data-ttu-id="ad378-115">Wenn die Zieldatei keine CLR-Metadaten enthält, kann die `OpenScope` Methode nicht ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="ad378-115">If the target file does not contain CLR metadata, the `OpenScope` method will fail.</span></span>  
  
 <span data-ttu-id="ad378-116">Wenn in der .NET Framework Version 1,0 und Version 1,1 ein Bereich geöffnet wird, für den `dwOpenFlags` auf ofRead festgelegt ist, ist er für die Freigabe berechtigt.</span><span class="sxs-lookup"><span data-stu-id="ad378-116">In the .NET Framework version 1.0 and version 1.1, if a scope is opened with `dwOpenFlags` set to ofRead, it is eligible for sharing.</span></span> <span data-ttu-id="ad378-117">Das heißt, wenn bei nachfolgenden Aufrufen von `OpenScope` der Name einer zuvor geöffneten Datei übergeben wird, wird der vorhandene Bereich wieder verwendet, und es wird kein neuer Satz von Datenstrukturen erstellt.</span><span class="sxs-lookup"><span data-stu-id="ad378-117">That is, if subsequent calls to `OpenScope` pass in the name of a file that was previously opened, the existing scope is reused and a new set of data structures is not created.</span></span> <span data-ttu-id="ad378-118">Probleme können jedoch aufgrund dieser Freigabe auftreten.</span><span class="sxs-lookup"><span data-stu-id="ad378-118">However, problems can arise due to this sharing.</span></span>  
  
 <span data-ttu-id="ad378-119">In der .NET Framework Version 2,0 werden Bereiche, die mit `dwOpenFlags` auf ofRead festgelegt wurden, nicht mehr freigegeben.</span><span class="sxs-lookup"><span data-stu-id="ad378-119">In the .NET Framework version 2.0, scopes opened with `dwOpenFlags` set to ofRead are no longer shared.</span></span> <span data-ttu-id="ad378-120">Verwenden Sie den ofReadOnly-Wert, damit der Bereich freigegeben werden kann.</span><span class="sxs-lookup"><span data-stu-id="ad378-120">Use the ofReadOnly value to allow the scope to be shared.</span></span> <span data-ttu-id="ad378-121">Wenn ein Bereich freigegeben wird, schlagen Abfragen, die "Lese-/Schreib-Metadatenschnittstellen" verwenden, fehl.</span><span class="sxs-lookup"><span data-stu-id="ad378-121">When a scope is shared, queries that use "read/write" metadata interfaces will fail.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ad378-122">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="ad378-122">Requirements</span></span>  
 <span data-ttu-id="ad378-123">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ad378-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ad378-124">**Header:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="ad378-124">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="ad378-125">**Bibliothek:** Wird als Ressource in Mscoree. dll verwendet.</span><span class="sxs-lookup"><span data-stu-id="ad378-125">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="ad378-126">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ad378-126">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ad378-127">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ad378-127">See also</span></span>

- [<span data-ttu-id="ad378-128">IMetaDataDispenser-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="ad378-128">IMetaDataDispenser Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-interface.md)
- [<span data-ttu-id="ad378-129">IMetaDataDispenserEx-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="ad378-129">IMetaDataDispenserEx Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenserex-interface.md)
- [<span data-ttu-id="ad378-130">IMetaDataAssemblyEmit-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="ad378-130">IMetaDataAssemblyEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md)
- [<span data-ttu-id="ad378-131">IMetaDataAssemblyImport-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="ad378-131">IMetaDataAssemblyImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md)
- [<span data-ttu-id="ad378-132">IMetaDataEmit-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="ad378-132">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="ad378-133">IMetaDataEmit2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="ad378-133">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
- [<span data-ttu-id="ad378-134">IMetaDataImport-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="ad378-134">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="ad378-135">IMetaDataImport2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="ad378-135">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
