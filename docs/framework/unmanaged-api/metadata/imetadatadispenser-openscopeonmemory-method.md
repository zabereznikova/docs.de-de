---
title: IMetaDataDispenser::OpenScopeOnMemory-Methode
ms.date: 03/30/2017
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
ms.openlocfilehash: 492c37540ad68b5b134520218eedc59013c68519
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79175927"
---
# <a name="imetadatadispenseropenscopeonmemory-method"></a><span data-ttu-id="7ca88-102">IMetaDataDispenser::OpenScopeOnMemory-Methode</span><span class="sxs-lookup"><span data-stu-id="7ca88-102">IMetaDataDispenser::OpenScopeOnMemory Method</span></span>
<span data-ttu-id="7ca88-103">Öffnet einen Speicherbereich, der vorhandene Metadaten enthält.</span><span class="sxs-lookup"><span data-stu-id="7ca88-103">Opens an area of memory that contains existing metadata.</span></span> <span data-ttu-id="7ca88-104">Das heißt, diese Methode öffnet einen angegebenen Speicherbereich, in dem die vorhandenen Daten als Metadaten behandelt werden.</span><span class="sxs-lookup"><span data-stu-id="7ca88-104">That is, this method opens a specified area of memory in which the existing data is treated as metadata.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7ca88-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="7ca88-105">Syntax</span></span>  
  
```cpp  
HRESULT OpenScopeOnMemory (  
    [in]  LPCVOID     pData,
    [in]  ULONG       cbData,
    [in]  DWORD       dwOpenFlags,
    [in]  REFIID      riid,
    [out] IUnknown    **ppIUnk  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7ca88-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="7ca88-106">Parameters</span></span>  
 `pData`  
 <span data-ttu-id="7ca88-107">[in] Ein Zeiger, der die Startadresse des Speicherbereichs angibt.</span><span class="sxs-lookup"><span data-stu-id="7ca88-107">[in] A pointer that specifies the starting address of the memory area.</span></span>  
  
 `cbData`  
 <span data-ttu-id="7ca88-108">[in] Die Größe des Speicherbereichs in Bytes.</span><span class="sxs-lookup"><span data-stu-id="7ca88-108">[in] The size of the memory area, in bytes.</span></span>  
  
 `dwOpenFlags`  
 <span data-ttu-id="7ca88-109">[in] Ein Wert der CorOpenFlags-Enumeration, um den Modus (Lesen, Schreiben usw.) zum Öffnen anzugeben. [CorOpenFlags](../../../../docs/framework/unmanaged-api/metadata/coropenflags-enumeration.md)</span><span class="sxs-lookup"><span data-stu-id="7ca88-109">[in] A value of the [CorOpenFlags](../../../../docs/framework/unmanaged-api/metadata/coropenflags-enumeration.md) enumeration to specify the mode (read, write, and so on) for opening.</span></span>  
  
 `riid`  
 <span data-ttu-id="7ca88-110">[in] Die IID der gewünschten Metadatenschnittstelle, die zurückgegeben werden soll; Der Aufrufer verwendet die Schnittstelle, um Metadaten zu importieren (lesen) oder auszusenden (schreiben).</span><span class="sxs-lookup"><span data-stu-id="7ca88-110">[in] The IID of the desired metadata interface to be returned; the caller will use the interface to import (read) or emit (write) metadata.</span></span>  
  
 <span data-ttu-id="7ca88-111">Der Wert `riid` von muss eine der Schnittstellen "import" oder "emit" angeben.</span><span class="sxs-lookup"><span data-stu-id="7ca88-111">The value of `riid` must specify one of the "import" or "emit" interfaces.</span></span> <span data-ttu-id="7ca88-112">Gültige Werte sind IID_IMetaDataEmit, IID_IMetaDataImport, IID_IMetaDataAssemblyEmit, IID_IMetaDataAssemblyImport, IID_IMetaDataEmit2 oder IID_IMetaDataImport2.</span><span class="sxs-lookup"><span data-stu-id="7ca88-112">Valid values are IID_IMetaDataEmit, IID_IMetaDataImport, IID_IMetaDataAssemblyEmit, IID_IMetaDataAssemblyImport, IID_IMetaDataEmit2, or IID_IMetaDataImport2.</span></span>  
  
 `ppIUnk`  
 <span data-ttu-id="7ca88-113">[out] Der Zeiger auf die zurückgegebene Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="7ca88-113">[out] The pointer to the returned interface.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="7ca88-114">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="7ca88-114">Remarks</span></span>  
 <span data-ttu-id="7ca88-115">Die In-Memory-Kopie der Metadaten kann mithilfe von Methoden von einer der "Import"-Schnittstellen abgefragt oder mit Methoden aus einer der "emit"-Schnittstellen hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="7ca88-115">The in-memory copy of the metadata can be queried using methods from one of the "import" interfaces, or added to using methods from the one of the "emit" interfaces.</span></span>  
  
 <span data-ttu-id="7ca88-116">Die `OpenScopeOnMemory` Methode ähnelt der [IMetaDataDispenser::OpenScope-Methode,](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-openscope-method.md) mit der Ausnahme, dass die Metadaten, die von Interesse sind, bereits im Arbeitsspeicher und nicht in einer Datei auf dem Datenträger vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="7ca88-116">The `OpenScopeOnMemory` method is similar to the [IMetaDataDispenser::OpenScope](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-openscope-method.md) method, except that the metadata of interest already exists in memory, rather than in a file on disk.</span></span>  
  
 <span data-ttu-id="7ca88-117">Wenn der Zielspeicherbereich keine CLR-Metadaten (Common Language `OpenScopeOnMemory` Runtime) enthält, schlägt die Methode fehl.</span><span class="sxs-lookup"><span data-stu-id="7ca88-117">If the target area of memory does not contain common language runtime (CLR) metadata, the `OpenScopeOnMemory` method will fail.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7ca88-118">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="7ca88-118">Requirements</span></span>  
 <span data-ttu-id="7ca88-119">**Plattform:** Siehe [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7ca88-119">**Platform:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7ca88-120">**Kopfzeile:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="7ca88-120">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="7ca88-121">**Bibliothek:** Wird als Ressource in MsCorEE.dll verwendet</span><span class="sxs-lookup"><span data-stu-id="7ca88-121">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="7ca88-122">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7ca88-122">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7ca88-123">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="7ca88-123">See also</span></span>

- [<span data-ttu-id="7ca88-124">IMetaDataDispenser-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="7ca88-124">IMetaDataDispenser Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-interface.md)
- [<span data-ttu-id="7ca88-125">IMetaDataDispenserEx-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="7ca88-125">IMetaDataDispenserEx Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenserex-interface.md)
- [<span data-ttu-id="7ca88-126">IMetaDataAssemblyEmit-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="7ca88-126">IMetaDataAssemblyEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md)
- [<span data-ttu-id="7ca88-127">IMetaDataAssemblyImport-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="7ca88-127">IMetaDataAssemblyImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md)
- [<span data-ttu-id="7ca88-128">IMetaDataEmit-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="7ca88-128">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="7ca88-129">IMetaDataEmit2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="7ca88-129">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
- [<span data-ttu-id="7ca88-130">IMetaDataImport-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="7ca88-130">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="7ca88-131">IMetaDataImport2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="7ca88-131">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
