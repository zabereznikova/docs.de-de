---
title: IMetaDataDispenser::DefineScope-Methode
ms.date: 03/30/2017
api_name:
- IMetaDataDispenser.DefineScope
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataDispenser::DefineScope
helpviewer_keywords:
- DefineScope method [.NET Framework metadata]
- IMetaDataDispenser::DefineScope method [.NET Framework metadata]
ms.assetid: af28db02-29af-45ac-aec6-8d6c6123c2ff
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 1763f9341af2d90cf465cb554bf7f282a4d92058
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67777810"
---
# <a name="imetadatadispenserdefinescope-method"></a><span data-ttu-id="49b4f-102">IMetaDataDispenser::DefineScope-Methode</span><span class="sxs-lookup"><span data-stu-id="49b4f-102">IMetaDataDispenser::DefineScope Method</span></span>
<span data-ttu-id="49b4f-103">Erstellt einen neuen Bereich im Arbeitsspeicher, in dem Sie neue Metadaten erstellen können.</span><span class="sxs-lookup"><span data-stu-id="49b4f-103">Creates a new area in memory in which you can create new metadata.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="49b4f-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="49b4f-104">Syntax</span></span>  
  
```cpp  
HRESULT DefineScope (  
    [in]  REFCLSID    rclsid,  
    [in]  DWORD       dwCreateFlags,  
    [in]  REFIID      riid,   
    [out] IUnknown    **ppIUnk  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="49b4f-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="49b4f-105">Parameters</span></span>  
 `rclsid`  
 <span data-ttu-id="49b4f-106">[in] Die CLSID der Version von Systemmetadaten-Strukturen erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="49b4f-106">[in] The CLSID of the version of metadata structures to be created.</span></span> <span data-ttu-id="49b4f-107">Dieser Wert muss es sich um CLSID_CorMetaDataRuntime für .NET Framework, Version 2.0 sein.</span><span class="sxs-lookup"><span data-stu-id="49b4f-107">This value must be CLSID_CorMetaDataRuntime for the .NET Framework version 2.0.</span></span>  
  
 `dwCreateFlags`  
 <span data-ttu-id="49b4f-108">[in] Flags, die Optionen angeben.</span><span class="sxs-lookup"><span data-stu-id="49b4f-108">[in] Flags that specify options.</span></span> <span data-ttu-id="49b4f-109">Dieser Wert muss 0 (null) für .NET Framework 2.0 sein.</span><span class="sxs-lookup"><span data-stu-id="49b4f-109">This value must be zero for the .NET Framework 2.0.</span></span>  
  
 `riid`  
 <span data-ttu-id="49b4f-110">[in] Die IID der Metadatenschnittstelle gewünschten zurückgegeben werden; der Aufrufer wird die Schnittstelle verwenden, um die neuen Metadaten zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="49b4f-110">[in] The IID of the desired metadata interface to be returned; the caller will use the interface to create the new metadata.</span></span>  
  
 <span data-ttu-id="49b4f-111">Der Wert des `riid` müssen eine der Schnittstellen "Ausgabe" angeben.</span><span class="sxs-lookup"><span data-stu-id="49b4f-111">The value of `riid` must specify one of the "emit" interfaces.</span></span> <span data-ttu-id="49b4f-112">Gültige Werte sind IID_IMetaDataEmit, IID_IMetaDataAssemblyEmit oder IID_IMetaDataEmit2.</span><span class="sxs-lookup"><span data-stu-id="49b4f-112">Valid values are IID_IMetaDataEmit, IID_IMetaDataAssemblyEmit, or IID_IMetaDataEmit2.</span></span>  
  
 `ppIUnk`  
 <span data-ttu-id="49b4f-113">[out] Der Zeiger auf die zurückgegebene Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="49b4f-113">[out] The pointer to the returned interface.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="49b4f-114">Hinweise</span><span class="sxs-lookup"><span data-stu-id="49b4f-114">Remarks</span></span>  
 <span data-ttu-id="49b4f-115">`DefineScope` erstellt einen Satz von in-Memory-Tabellen, generiert eine eindeutige GUID für die Metadaten (Modul Versions-ID oder MVID) und erstellt einen Eintrag in der Modultabelle für die Kompilierungseinheit ausgegeben wird.</span><span class="sxs-lookup"><span data-stu-id="49b4f-115">`DefineScope` creates a set of in-memory metadata tables, generates a unique GUID (module version identifier, or MVID) for the metadata, and creates an entry in the module table for the compilation unit being emitted.</span></span>  
  
 <span data-ttu-id="49b4f-116">Sie können Attribute als Ganzes an den Metadatenbereich anfügen, indem Sie mit der [IMetaDataEmit:: SetModuleProps](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-setmoduleprops-method.md) oder [DefineCustomAttribute](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definecustomattribute-method.md) Methode, nach Bedarf.</span><span class="sxs-lookup"><span data-stu-id="49b4f-116">You can attach attributes to the metadata scope as a whole by using the [IMetaDataEmit::SetModuleProps](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-setmoduleprops-method.md) or [IMetaDataEmit::DefineCustomAttribute](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definecustomattribute-method.md) method, as appropriate.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="49b4f-117">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="49b4f-117">Requirements</span></span>  
 <span data-ttu-id="49b4f-118">**Plattform:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="49b4f-118">**Platform:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="49b4f-119">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="49b4f-119">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="49b4f-120">**Bibliothek:** Als Ressource in MsCorEE.dll verwendet</span><span class="sxs-lookup"><span data-stu-id="49b4f-120">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="49b4f-121">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="49b4f-121">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="49b4f-122">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="49b4f-122">See also</span></span>

- [<span data-ttu-id="49b4f-123">IMetaDataDispenser-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="49b4f-123">IMetaDataDispenser Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-interface.md)
- [<span data-ttu-id="49b4f-124">IMetaDataDispenserEx-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="49b4f-124">IMetaDataDispenserEx Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenserex-interface.md)
- [<span data-ttu-id="49b4f-125">IMetaDataAssemblyEmit-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="49b4f-125">IMetaDataAssemblyEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md)
- [<span data-ttu-id="49b4f-126">IMetaDataEmit-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="49b4f-126">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="49b4f-127">IMetaDataEmit2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="49b4f-127">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
