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
ms.openlocfilehash: 69e5e05012d2b44a76a986591ec990f66bf8ae20
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/27/2020
ms.locfileid: "84007324"
---
# <a name="imetadatadispenseropenscopeonmemory-method"></a><span data-ttu-id="ed453-102">IMetaDataDispenser::OpenScopeOnMemory-Methode</span><span class="sxs-lookup"><span data-stu-id="ed453-102">IMetaDataDispenser::OpenScopeOnMemory Method</span></span>
<span data-ttu-id="ed453-103">Öffnet einen Arbeitsspeicher Bereich, der vorhandene Metadaten enthält.</span><span class="sxs-lookup"><span data-stu-id="ed453-103">Opens an area of memory that contains existing metadata.</span></span> <span data-ttu-id="ed453-104">Das heißt, diese Methode öffnet einen angegebenen Bereich des Speichers, in dem die vorhandenen Daten als Metadaten behandelt werden.</span><span class="sxs-lookup"><span data-stu-id="ed453-104">That is, this method opens a specified area of memory in which the existing data is treated as metadata.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ed453-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="ed453-105">Syntax</span></span>  
  
```cpp  
HRESULT OpenScopeOnMemory (  
    [in]  LPCVOID     pData,
    [in]  ULONG       cbData,
    [in]  DWORD       dwOpenFlags,
    [in]  REFIID      riid,
    [out] IUnknown    **ppIUnk  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ed453-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="ed453-106">Parameters</span></span>  
 `pData`  
 <span data-ttu-id="ed453-107">in Ein-Zeiger, der die Startadresse des Speicherbereichs angibt.</span><span class="sxs-lookup"><span data-stu-id="ed453-107">[in] A pointer that specifies the starting address of the memory area.</span></span>  
  
 `cbData`  
 <span data-ttu-id="ed453-108">in Die Größe des Arbeitsspeicher Bereichs in Bytes.</span><span class="sxs-lookup"><span data-stu-id="ed453-108">[in] The size of the memory area, in bytes.</span></span>  
  
 `dwOpenFlags`  
 <span data-ttu-id="ed453-109">in Ein Wert der [CorOpenFlags](coropenflags-enumeration.md) -Enumeration, mit dem der Modus (lesen, schreiben usw.) zum Öffnen angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="ed453-109">[in] A value of the [CorOpenFlags](coropenflags-enumeration.md) enumeration to specify the mode (read, write, and so on) for opening.</span></span>  
  
 `riid`  
 <span data-ttu-id="ed453-110">in Die IID der gewünschten Metadatenschnittstelle, die zurückgegeben werden soll. der Aufrufer verwendet die-Schnittstelle, um Metadaten zu importieren (lesen) oder auszugeben (schreiben).</span><span class="sxs-lookup"><span data-stu-id="ed453-110">[in] The IID of the desired metadata interface to be returned; the caller will use the interface to import (read) or emit (write) metadata.</span></span>  
  
 <span data-ttu-id="ed453-111">Der Wert von `riid` muss eine der Schnittstellen "Import" oder "ausgeben" angeben.</span><span class="sxs-lookup"><span data-stu-id="ed453-111">The value of `riid` must specify one of the "import" or "emit" interfaces.</span></span> <span data-ttu-id="ed453-112">Gültige Werte sind IID_IMetaDataEmit, IID_IMetaDataImport, IID_IMetaDataAssemblyEmit, IID_IMetaDataAssemblyImport, IID_IMetaDataEmit2 oder IID_IMetaDataImport2.</span><span class="sxs-lookup"><span data-stu-id="ed453-112">Valid values are IID_IMetaDataEmit, IID_IMetaDataImport, IID_IMetaDataAssemblyEmit, IID_IMetaDataAssemblyImport, IID_IMetaDataEmit2, or IID_IMetaDataImport2.</span></span>  
  
 `ppIUnk`  
 <span data-ttu-id="ed453-113">vorgenommen Der Zeiger auf die zurückgegebene Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="ed453-113">[out] The pointer to the returned interface.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ed453-114">Hinweise</span><span class="sxs-lookup"><span data-stu-id="ed453-114">Remarks</span></span>  
 <span data-ttu-id="ed453-115">Die in-Memory-Kopie der Metadaten kann mithilfe von Methoden einer der "Import"-Schnittstellen abgefragt oder mithilfe von Methoden aus einer der "Ausgabe"-Schnittstellen hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="ed453-115">The in-memory copy of the metadata can be queried using methods from one of the "import" interfaces, or added to using methods from the one of the "emit" interfaces.</span></span>  
  
 <span data-ttu-id="ed453-116">Die- `OpenScopeOnMemory` Methode ähnelt der [IMetaDataDispenser:: OpenScope](imetadatadispenser-openscope-method.md) -Methode, mit der Ausnahme, dass die relevanten Metadaten bereits im Arbeitsspeicher vorhanden sind, und nicht in einer Datei auf dem Datenträger.</span><span class="sxs-lookup"><span data-stu-id="ed453-116">The `OpenScopeOnMemory` method is similar to the [IMetaDataDispenser::OpenScope](imetadatadispenser-openscope-method.md) method, except that the metadata of interest already exists in memory, rather than in a file on disk.</span></span>  
  
 <span data-ttu-id="ed453-117">Wenn der Zielspeicher Bereich keine Common Language Runtime (CLR)-Metadaten enthält, schlägt die `OpenScopeOnMemory` Methode fehl.</span><span class="sxs-lookup"><span data-stu-id="ed453-117">If the target area of memory does not contain common language runtime (CLR) metadata, the `OpenScopeOnMemory` method will fail.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ed453-118">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="ed453-118">Requirements</span></span>  
 <span data-ttu-id="ed453-119">**Plattform:** Siehe [System Anforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ed453-119">**Platform:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ed453-120">**Header:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="ed453-120">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="ed453-121">**Bibliothek:** Wird als Ressource in Mscoree. dll verwendet.</span><span class="sxs-lookup"><span data-stu-id="ed453-121">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="ed453-122">**.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ed453-122">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ed453-123">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ed453-123">See also</span></span>

- [<span data-ttu-id="ed453-124">IMetaDataDispenser-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="ed453-124">IMetaDataDispenser Interface</span></span>](imetadatadispenser-interface.md)
- [<span data-ttu-id="ed453-125">IMetaDataDispenserEx-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="ed453-125">IMetaDataDispenserEx Interface</span></span>](imetadatadispenserex-interface.md)
- [<span data-ttu-id="ed453-126">IMetaDataAssemblyEmit-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="ed453-126">IMetaDataAssemblyEmit Interface</span></span>](imetadataassemblyemit-interface.md)
- [<span data-ttu-id="ed453-127">IMetaDataAssemblyImport-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="ed453-127">IMetaDataAssemblyImport Interface</span></span>](imetadataassemblyimport-interface.md)
- [<span data-ttu-id="ed453-128">IMetaDataEmit-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="ed453-128">IMetaDataEmit Interface</span></span>](imetadataemit-interface.md)
- [<span data-ttu-id="ed453-129">IMetaDataEmit2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="ed453-129">IMetaDataEmit2 Interface</span></span>](imetadataemit2-interface.md)
- [<span data-ttu-id="ed453-130">IMetaDataImport-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="ed453-130">IMetaDataImport Interface</span></span>](imetadataimport-interface.md)
- [<span data-ttu-id="ed453-131">IMetaDataImport2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="ed453-131">IMetaDataImport2 Interface</span></span>](imetadataimport2-interface.md)
