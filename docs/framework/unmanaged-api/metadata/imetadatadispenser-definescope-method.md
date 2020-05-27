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
ms.openlocfilehash: 021ef8de602d6dd928f49e69e36f8d4a61425745
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/27/2020
ms.locfileid: "84008364"
---
# <a name="imetadatadispenserdefinescope-method"></a><span data-ttu-id="9b411-102">IMetaDataDispenser::DefineScope-Methode</span><span class="sxs-lookup"><span data-stu-id="9b411-102">IMetaDataDispenser::DefineScope Method</span></span>
<span data-ttu-id="9b411-103">Erstellt einen neuen Bereich im Arbeitsspeicher, in dem Sie neue Metadaten erstellen können.</span><span class="sxs-lookup"><span data-stu-id="9b411-103">Creates a new area in memory in which you can create new metadata.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9b411-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="9b411-104">Syntax</span></span>  
  
```cpp  
HRESULT DefineScope (  
    [in]  REFCLSID    rclsid,  
    [in]  DWORD       dwCreateFlags,  
    [in]  REFIID      riid,
    [out] IUnknown    **ppIUnk  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9b411-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="9b411-105">Parameters</span></span>  
 `rclsid`  
 <span data-ttu-id="9b411-106">in Die CLSID der Version der zu erstellenden Metadatenstrukturen.</span><span class="sxs-lookup"><span data-stu-id="9b411-106">[in] The CLSID of the version of metadata structures to be created.</span></span> <span data-ttu-id="9b411-107">Dieser Wert muss für die .NET Framework Version 2,0 CLSID_CorMetaDataRuntime werden.</span><span class="sxs-lookup"><span data-stu-id="9b411-107">This value must be CLSID_CorMetaDataRuntime for the .NET Framework version 2.0.</span></span>  
  
 `dwCreateFlags`  
 <span data-ttu-id="9b411-108">in Flags, die Optionen angeben.</span><span class="sxs-lookup"><span data-stu-id="9b411-108">[in] Flags that specify options.</span></span> <span data-ttu-id="9b411-109">Dieser Wert muss für den .NET Framework 2,0 den Wert 0 (null) aufweisen.</span><span class="sxs-lookup"><span data-stu-id="9b411-109">This value must be zero for the .NET Framework 2.0.</span></span>  
  
 `riid`  
 <span data-ttu-id="9b411-110">in Die IID der gewünschten Metadatenschnittstelle, die zurückgegeben werden soll. der Aufrufer verwendet die-Schnittstelle, um die neuen Metadaten zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="9b411-110">[in] The IID of the desired metadata interface to be returned; the caller will use the interface to create the new metadata.</span></span>  
  
 <span data-ttu-id="9b411-111">Der Wert von `riid` muss eine der "Auswertungs Schnittstellen" angeben.</span><span class="sxs-lookup"><span data-stu-id="9b411-111">The value of `riid` must specify one of the "emit" interfaces.</span></span> <span data-ttu-id="9b411-112">Gültige Werte sind IID_IMetaDataEmit, IID_IMetaDataAssemblyEmit oder IID_IMetaDataEmit2.</span><span class="sxs-lookup"><span data-stu-id="9b411-112">Valid values are IID_IMetaDataEmit, IID_IMetaDataAssemblyEmit, or IID_IMetaDataEmit2.</span></span>  
  
 `ppIUnk`  
 <span data-ttu-id="9b411-113">vorgenommen Der Zeiger auf die zurückgegebene Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="9b411-113">[out] The pointer to the returned interface.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9b411-114">Hinweise</span><span class="sxs-lookup"><span data-stu-id="9b411-114">Remarks</span></span>  
 <span data-ttu-id="9b411-115">`DefineScope`erstellt eine Gruppe von in-Memory-Metadatentabellen, generiert eine eindeutige GUID (Modul Versions Bezeichner oder MVID) für die Metadaten und erstellt einen Eintrag in der Modul Tabelle für die ausgegebene Kompilierungseinheit.</span><span class="sxs-lookup"><span data-stu-id="9b411-115">`DefineScope` creates a set of in-memory metadata tables, generates a unique GUID (module version identifier, or MVID) for the metadata, and creates an entry in the module table for the compilation unit being emitted.</span></span>  
  
 <span data-ttu-id="9b411-116">Sie können Attribute an den Metadatenbereich als Ganzes anfügen, indem Sie je nach Bedarf die [IMetaDataEmit:: setmodulerequior](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-setmoduleprops-method.md) [IMetaDataEmit::D efinecustomattribute](imetadataemit-definecustomattribute-method.md) -Methode verwenden.</span><span class="sxs-lookup"><span data-stu-id="9b411-116">You can attach attributes to the metadata scope as a whole by using the [IMetaDataEmit::SetModuleProps](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-setmoduleprops-method.md) or [IMetaDataEmit::DefineCustomAttribute](imetadataemit-definecustomattribute-method.md) method, as appropriate.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9b411-117">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="9b411-117">Requirements</span></span>  
 <span data-ttu-id="9b411-118">**Plattform:** Siehe [System Anforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9b411-118">**Platform:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9b411-119">**Header:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="9b411-119">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="9b411-120">**Bibliothek:** Wird als Ressource in Mscoree. dll verwendet.</span><span class="sxs-lookup"><span data-stu-id="9b411-120">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="9b411-121">**.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9b411-121">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9b411-122">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="9b411-122">See also</span></span>

- [<span data-ttu-id="9b411-123">IMetaDataDispenser-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="9b411-123">IMetaDataDispenser Interface</span></span>](imetadatadispenser-interface.md)
- [<span data-ttu-id="9b411-124">IMetaDataDispenserEx-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="9b411-124">IMetaDataDispenserEx Interface</span></span>](imetadatadispenserex-interface.md)
- [<span data-ttu-id="9b411-125">IMetaDataAssemblyEmit-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="9b411-125">IMetaDataAssemblyEmit Interface</span></span>](imetadataassemblyemit-interface.md)
- [<span data-ttu-id="9b411-126">IMetaDataEmit-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="9b411-126">IMetaDataEmit Interface</span></span>](imetadataemit-interface.md)
- [<span data-ttu-id="9b411-127">IMetaDataEmit2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="9b411-127">IMetaDataEmit2 Interface</span></span>](imetadataemit2-interface.md)
