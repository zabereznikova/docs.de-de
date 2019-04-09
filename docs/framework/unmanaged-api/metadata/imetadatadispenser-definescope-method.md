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
ms.openlocfilehash: 76a439effad9cb3f6dcdd232590cf2196ee7ab99
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59101405"
---
# <a name="imetadatadispenserdefinescope-method"></a><span data-ttu-id="c6dff-102">IMetaDataDispenser::DefineScope-Methode</span><span class="sxs-lookup"><span data-stu-id="c6dff-102">IMetaDataDispenser::DefineScope Method</span></span>
<span data-ttu-id="c6dff-103">Erstellt einen neuen Bereich im Arbeitsspeicher, in dem Sie neue Metadaten erstellen können.</span><span class="sxs-lookup"><span data-stu-id="c6dff-103">Creates a new area in memory in which you can create new metadata.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c6dff-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="c6dff-104">Syntax</span></span>  
  
```  
HRESULT DefineScope (  
    [in]  REFCLSID    rclsid,  
    [in]  DWORD       dwCreateFlags,  
    [in]  REFIID      riid,   
    [out] IUnknown    **ppIUnk  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c6dff-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="c6dff-105">Parameters</span></span>  
 `rclsid`  
 <span data-ttu-id="c6dff-106">[in] Die CLSID der Version von Systemmetadaten-Strukturen erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="c6dff-106">[in] The CLSID of the version of metadata structures to be created.</span></span> <span data-ttu-id="c6dff-107">Dieser Wert muss es sich um CLSID_CorMetaDataRuntime für .NET Framework, Version 2.0 sein.</span><span class="sxs-lookup"><span data-stu-id="c6dff-107">This value must be CLSID_CorMetaDataRuntime for the .NET Framework version 2.0.</span></span>  
  
 `dwCreateFlags`  
 <span data-ttu-id="c6dff-108">[in] Flags, die Optionen angeben.</span><span class="sxs-lookup"><span data-stu-id="c6dff-108">[in] Flags that specify options.</span></span> <span data-ttu-id="c6dff-109">Dieser Wert muss 0 (null) für .NET Framework 2.0 sein.</span><span class="sxs-lookup"><span data-stu-id="c6dff-109">This value must be zero for the .NET Framework 2.0.</span></span>  
  
 `riid`  
 <span data-ttu-id="c6dff-110">[in] Die IID der Metadatenschnittstelle gewünschten zurückgegeben werden; der Aufrufer wird die Schnittstelle verwenden, um die neuen Metadaten zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="c6dff-110">[in] The IID of the desired metadata interface to be returned; the caller will use the interface to create the new metadata.</span></span>  
  
 <span data-ttu-id="c6dff-111">Der Wert des `riid` müssen eine der Schnittstellen "Ausgabe" angeben.</span><span class="sxs-lookup"><span data-stu-id="c6dff-111">The value of `riid` must specify one of the "emit" interfaces.</span></span> <span data-ttu-id="c6dff-112">Gültige Werte sind IID_IMetaDataEmit, IID_IMetaDataAssemblyEmit oder IID_IMetaDataEmit2.</span><span class="sxs-lookup"><span data-stu-id="c6dff-112">Valid values are IID_IMetaDataEmit, IID_IMetaDataAssemblyEmit, or IID_IMetaDataEmit2.</span></span>  
  
 `ppIUnk`  
 <span data-ttu-id="c6dff-113">[out] Der Zeiger auf die zurückgegebene Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="c6dff-113">[out] The pointer to the returned interface.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c6dff-114">Hinweise</span><span class="sxs-lookup"><span data-stu-id="c6dff-114">Remarks</span></span>  
 `DefineScope` <span data-ttu-id="c6dff-115">erstellt einen Satz von in-Memory-Tabellen, generiert eine eindeutige GUID für die Metadaten (Modul Versions-ID oder MVID) und erstellt einen Eintrag in der Modultabelle für die Kompilierungseinheit ausgegeben wird.</span><span class="sxs-lookup"><span data-stu-id="c6dff-115">creates a set of in-memory metadata tables, generates a unique GUID (module version identifier, or MVID) for the metadata, and creates an entry in the module table for the compilation unit being emitted.</span></span>  
  
 <span data-ttu-id="c6dff-116">Sie können Attribute als Ganzes an den Metadatenbereich anfügen, indem Sie mit der [IMetaDataEmit:: SetModuleProps](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-setmoduleprops-method.md) oder [DefineCustomAttribute](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definecustomattribute-method.md) Methode, nach Bedarf.</span><span class="sxs-lookup"><span data-stu-id="c6dff-116">You can attach attributes to the metadata scope as a whole by using the [IMetaDataEmit::SetModuleProps](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-setmoduleprops-method.md) or [IMetaDataEmit::DefineCustomAttribute](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definecustomattribute-method.md) method, as appropriate.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c6dff-117">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="c6dff-117">Requirements</span></span>  
 <span data-ttu-id="c6dff-118">**Plattform:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c6dff-118">**Platform:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c6dff-119">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="c6dff-119">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="c6dff-120">**Bibliothek:** Als Ressource in MsCorEE.dll verwendet</span><span class="sxs-lookup"><span data-stu-id="c6dff-120">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 **<span data-ttu-id="c6dff-121">.NET Framework-Versionen:</span><span class="sxs-lookup"><span data-stu-id="c6dff-121">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="c6dff-122">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c6dff-122">See also</span></span>

- [<span data-ttu-id="c6dff-123">IMetaDataDispenser-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="c6dff-123">IMetaDataDispenser Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-interface.md)
- [<span data-ttu-id="c6dff-124">IMetaDataDispenserEx-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="c6dff-124">IMetaDataDispenserEx Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenserex-interface.md)
- [<span data-ttu-id="c6dff-125">IMetaDataAssemblyEmit-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="c6dff-125">IMetaDataAssemblyEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md)
- [<span data-ttu-id="c6dff-126">IMetaDataEmit-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="c6dff-126">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="c6dff-127">IMetaDataEmit2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="c6dff-127">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
