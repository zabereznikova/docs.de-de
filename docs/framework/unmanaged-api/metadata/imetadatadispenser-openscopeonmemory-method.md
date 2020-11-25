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
ms.openlocfilehash: 26293e38a275ca691c7d48dceb12c1e7dd316536
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95713417"
---
# <a name="imetadatadispenseropenscopeonmemory-method"></a><span data-ttu-id="24e77-102">IMetaDataDispenser::OpenScopeOnMemory-Methode</span><span class="sxs-lookup"><span data-stu-id="24e77-102">IMetaDataDispenser::OpenScopeOnMemory Method</span></span>

<span data-ttu-id="24e77-103">Öffnet einen Arbeitsspeicher Bereich, der vorhandene Metadaten enthält.</span><span class="sxs-lookup"><span data-stu-id="24e77-103">Opens an area of memory that contains existing metadata.</span></span> <span data-ttu-id="24e77-104">Das heißt, diese Methode öffnet einen angegebenen Bereich des Speichers, in dem die vorhandenen Daten als Metadaten behandelt werden.</span><span class="sxs-lookup"><span data-stu-id="24e77-104">That is, this method opens a specified area of memory in which the existing data is treated as metadata.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="24e77-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="24e77-105">Syntax</span></span>  
  
```cpp  
HRESULT OpenScopeOnMemory (  
    [in]  LPCVOID     pData,
    [in]  ULONG       cbData,
    [in]  DWORD       dwOpenFlags,
    [in]  REFIID      riid,
    [out] IUnknown    **ppIUnk  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="24e77-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="24e77-106">Parameters</span></span>  

 `pData`  
 <span data-ttu-id="24e77-107">in Ein-Zeiger, der die Startadresse des Speicherbereichs angibt.</span><span class="sxs-lookup"><span data-stu-id="24e77-107">[in] A pointer that specifies the starting address of the memory area.</span></span>  
  
 `cbData`  
 <span data-ttu-id="24e77-108">in Die Größe des Arbeitsspeicher Bereichs in Bytes.</span><span class="sxs-lookup"><span data-stu-id="24e77-108">[in] The size of the memory area, in bytes.</span></span>  
  
 `dwOpenFlags`  
 <span data-ttu-id="24e77-109">in Ein Wert der [CorOpenFlags](coropenflags-enumeration.md) -Enumeration, mit dem der Modus (lesen, schreiben usw.) zum Öffnen angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="24e77-109">[in] A value of the [CorOpenFlags](coropenflags-enumeration.md) enumeration to specify the mode (read, write, and so on) for opening.</span></span>  
  
 `riid`  
 <span data-ttu-id="24e77-110">in Die IID der gewünschten Metadatenschnittstelle, die zurückgegeben werden soll. der Aufrufer verwendet die-Schnittstelle, um Metadaten zu importieren (lesen) oder auszugeben (schreiben).</span><span class="sxs-lookup"><span data-stu-id="24e77-110">[in] The IID of the desired metadata interface to be returned; the caller will use the interface to import (read) or emit (write) metadata.</span></span>  
  
 <span data-ttu-id="24e77-111">Der Wert von `riid` muss eine der Schnittstellen "Import" oder "ausgeben" angeben.</span><span class="sxs-lookup"><span data-stu-id="24e77-111">The value of `riid` must specify one of the "import" or "emit" interfaces.</span></span> <span data-ttu-id="24e77-112">Gültige Werte sind IID_IMetaDataEmit, IID_IMetaDataImport, IID_IMetaDataAssemblyEmit, IID_IMetaDataAssemblyImport, IID_IMetaDataEmit2 oder IID_IMetaDataImport2.</span><span class="sxs-lookup"><span data-stu-id="24e77-112">Valid values are IID_IMetaDataEmit, IID_IMetaDataImport, IID_IMetaDataAssemblyEmit, IID_IMetaDataAssemblyImport, IID_IMetaDataEmit2, or IID_IMetaDataImport2.</span></span>  
  
 `ppIUnk`  
 <span data-ttu-id="24e77-113">vorgenommen Der Zeiger auf die zurückgegebene Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="24e77-113">[out] The pointer to the returned interface.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="24e77-114">Hinweise</span><span class="sxs-lookup"><span data-stu-id="24e77-114">Remarks</span></span>  

 <span data-ttu-id="24e77-115">Die in-Memory-Kopie der Metadaten kann mithilfe von Methoden einer der "Import"-Schnittstellen abgefragt oder mithilfe von Methoden aus einer der "Ausgabe"-Schnittstellen hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="24e77-115">The in-memory copy of the metadata can be queried using methods from one of the "import" interfaces, or added to using methods from the one of the "emit" interfaces.</span></span>  
  
 <span data-ttu-id="24e77-116">Die- `OpenScopeOnMemory` Methode ähnelt der [IMetaDataDispenser:: OpenScope](imetadatadispenser-openscope-method.md) -Methode, mit der Ausnahme, dass die relevanten Metadaten bereits im Arbeitsspeicher vorhanden sind, und nicht in einer Datei auf dem Datenträger.</span><span class="sxs-lookup"><span data-stu-id="24e77-116">The `OpenScopeOnMemory` method is similar to the [IMetaDataDispenser::OpenScope](imetadatadispenser-openscope-method.md) method, except that the metadata of interest already exists in memory, rather than in a file on disk.</span></span>  
  
 <span data-ttu-id="24e77-117">Wenn der Zielspeicher Bereich keine Common Language Runtime (CLR)-Metadaten enthält, schlägt die `OpenScopeOnMemory` Methode fehl.</span><span class="sxs-lookup"><span data-stu-id="24e77-117">If the target area of memory does not contain common language runtime (CLR) metadata, the `OpenScopeOnMemory` method will fail.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="24e77-118">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="24e77-118">Requirements</span></span>  

 <span data-ttu-id="24e77-119">**Plattform:** Siehe [System Anforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="24e77-119">**Platform:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="24e77-120">**Header:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="24e77-120">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="24e77-121">**Bibliothek:** Wird als Ressource in MsCorEE.dll verwendet.</span><span class="sxs-lookup"><span data-stu-id="24e77-121">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="24e77-122">**.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="24e77-122">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="24e77-123">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="24e77-123">See also</span></span>

- [<span data-ttu-id="24e77-124">IMetaDataDispenser-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="24e77-124">IMetaDataDispenser Interface</span></span>](imetadatadispenser-interface.md)
- [<span data-ttu-id="24e77-125">IMetaDataDispenserEx-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="24e77-125">IMetaDataDispenserEx Interface</span></span>](imetadatadispenserex-interface.md)
- [<span data-ttu-id="24e77-126">IMetaDataAssemblyEmit-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="24e77-126">IMetaDataAssemblyEmit Interface</span></span>](imetadataassemblyemit-interface.md)
- [<span data-ttu-id="24e77-127">IMetaDataAssemblyImport-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="24e77-127">IMetaDataAssemblyImport Interface</span></span>](imetadataassemblyimport-interface.md)
- [<span data-ttu-id="24e77-128">IMetaDataEmit-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="24e77-128">IMetaDataEmit Interface</span></span>](imetadataemit-interface.md)
- [<span data-ttu-id="24e77-129">IMetaDataEmit2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="24e77-129">IMetaDataEmit2 Interface</span></span>](imetadataemit2-interface.md)
- [<span data-ttu-id="24e77-130">IMetaDataImport-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="24e77-130">IMetaDataImport Interface</span></span>](imetadataimport-interface.md)
- [<span data-ttu-id="24e77-131">IMetaDataImport2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="24e77-131">IMetaDataImport2 Interface</span></span>](imetadataimport2-interface.md)
