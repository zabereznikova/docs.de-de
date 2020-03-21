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
ms.openlocfilehash: 2f9325f3795262a0c33af02f87fc5d3a020658cf
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79177644"
---
# <a name="imetadatadispenserdefinescope-method"></a><span data-ttu-id="a0c7e-102">IMetaDataDispenser::DefineScope-Methode</span><span class="sxs-lookup"><span data-stu-id="a0c7e-102">IMetaDataDispenser::DefineScope Method</span></span>
<span data-ttu-id="a0c7e-103">Erstellt einen neuen Bereich im Arbeitsspeicher, in dem Sie neue Metadaten erstellen können.</span><span class="sxs-lookup"><span data-stu-id="a0c7e-103">Creates a new area in memory in which you can create new metadata.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a0c7e-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="a0c7e-104">Syntax</span></span>  
  
```cpp  
HRESULT DefineScope (  
    [in]  REFCLSID    rclsid,  
    [in]  DWORD       dwCreateFlags,  
    [in]  REFIID      riid,
    [out] IUnknown    **ppIUnk  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a0c7e-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="a0c7e-105">Parameters</span></span>  
 `rclsid`  
 <span data-ttu-id="a0c7e-106">[in] Die CLSID der Version der zu erstellenden Metadatenstrukturen.</span><span class="sxs-lookup"><span data-stu-id="a0c7e-106">[in] The CLSID of the version of metadata structures to be created.</span></span> <span data-ttu-id="a0c7e-107">Dieser Wert muss für .NET Framework Version 2.0 CLSID_CorMetaDataRuntime werden.</span><span class="sxs-lookup"><span data-stu-id="a0c7e-107">This value must be CLSID_CorMetaDataRuntime for the .NET Framework version 2.0.</span></span>  
  
 `dwCreateFlags`  
 <span data-ttu-id="a0c7e-108">[in] Flags, die Optionen angeben.</span><span class="sxs-lookup"><span data-stu-id="a0c7e-108">[in] Flags that specify options.</span></span> <span data-ttu-id="a0c7e-109">Dieser Wert muss für .NET Framework 2.0 Null sein.</span><span class="sxs-lookup"><span data-stu-id="a0c7e-109">This value must be zero for the .NET Framework 2.0.</span></span>  
  
 `riid`  
 <span data-ttu-id="a0c7e-110">[in] Die IID der gewünschten Metadatenschnittstelle, die zurückgegeben werden soll; Der Aufrufer verwendet die Schnittstelle, um die neuen Metadaten zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="a0c7e-110">[in] The IID of the desired metadata interface to be returned; the caller will use the interface to create the new metadata.</span></span>  
  
 <span data-ttu-id="a0c7e-111">Der Wert `riid` von muss eine der "emit"-Schnittstellen angeben.</span><span class="sxs-lookup"><span data-stu-id="a0c7e-111">The value of `riid` must specify one of the "emit" interfaces.</span></span> <span data-ttu-id="a0c7e-112">Gültige Werte sind IID_IMetaDataEmit, IID_IMetaDataAssemblyEmit oder IID_IMetaDataEmit2.</span><span class="sxs-lookup"><span data-stu-id="a0c7e-112">Valid values are IID_IMetaDataEmit, IID_IMetaDataAssemblyEmit, or IID_IMetaDataEmit2.</span></span>  
  
 `ppIUnk`  
 <span data-ttu-id="a0c7e-113">[out] Der Zeiger auf die zurückgegebene Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="a0c7e-113">[out] The pointer to the returned interface.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a0c7e-114">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="a0c7e-114">Remarks</span></span>  
 <span data-ttu-id="a0c7e-115">`DefineScope`erstellt einen Satz in-Memory-Metadatentabellen, generiert eine eindeutige GUID (Modulversionsbezeichner oder MVID) für die Metadaten und erstellt einen Eintrag in der Modultabelle für die emittierte Kompilierungseinheit.</span><span class="sxs-lookup"><span data-stu-id="a0c7e-115">`DefineScope` creates a set of in-memory metadata tables, generates a unique GUID (module version identifier, or MVID) for the metadata, and creates an entry in the module table for the compilation unit being emitted.</span></span>  
  
 <span data-ttu-id="a0c7e-116">Sie können Attribute an den Metadatenbereich als Ganzes anfügen, indem Sie die [IMetaDataEmit::SetModuleProps](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-setmoduleprops-method.md) oder [die IMetaDataEmit::DefineCustomAttribute-Methode](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definecustomattribute-method.md) verwenden.</span><span class="sxs-lookup"><span data-stu-id="a0c7e-116">You can attach attributes to the metadata scope as a whole by using the [IMetaDataEmit::SetModuleProps](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-setmoduleprops-method.md) or [IMetaDataEmit::DefineCustomAttribute](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definecustomattribute-method.md) method, as appropriate.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a0c7e-117">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="a0c7e-117">Requirements</span></span>  
 <span data-ttu-id="a0c7e-118">**Plattform:** Siehe [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a0c7e-118">**Platform:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a0c7e-119">**Kopfzeile:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="a0c7e-119">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="a0c7e-120">**Bibliothek:** Wird als Ressource in MsCorEE.dll verwendet</span><span class="sxs-lookup"><span data-stu-id="a0c7e-120">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="a0c7e-121">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a0c7e-121">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a0c7e-122">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="a0c7e-122">See also</span></span>

- [<span data-ttu-id="a0c7e-123">IMetaDataDispenser-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="a0c7e-123">IMetaDataDispenser Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-interface.md)
- [<span data-ttu-id="a0c7e-124">IMetaDataDispenserEx-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="a0c7e-124">IMetaDataDispenserEx Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenserex-interface.md)
- [<span data-ttu-id="a0c7e-125">IMetaDataAssemblyEmit-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="a0c7e-125">IMetaDataAssemblyEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md)
- [<span data-ttu-id="a0c7e-126">IMetaDataEmit-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="a0c7e-126">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="a0c7e-127">IMetaDataEmit2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="a0c7e-127">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
