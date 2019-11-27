---
title: IMetaDataDispenserEx-Schnittstelle
ms.date: 03/30/2017
api_name:
- IMetaDataDispenserEx
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataDispenserEx
helpviewer_keywords:
- IMetaDataDispenserEx interface [.NET Framework metadata]
ms.assetid: 78b3629e-77a2-4406-89c3-56b5cc2c4594
topic_type:
- apiref
ms.openlocfilehash: 985cdea670714394119fb846e9e55a01713559a9
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/23/2019
ms.locfileid: "74431146"
---
# <a name="imetadatadispenserex-interface"></a><span data-ttu-id="3b643-102">IMetaDataDispenserEx-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="3b643-102">IMetaDataDispenserEx Interface</span></span>
<span data-ttu-id="3b643-103">Erweitert die Schnittstelle der [IMetaDataDispenser-Schnittstelle](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-interface.md) und bietet die Möglichkeit, zu steuern, wie die Metadaten-APIs mit dem aktuellen Metadatenbereich arbeiten.</span><span class="sxs-lookup"><span data-stu-id="3b643-103">Extends the [IMetaDataDispenser Interface](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-interface.md) interface to provide the capability to control how the metadata APIs operate on the current metadata scope.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="3b643-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="3b643-104">Methods</span></span>  
  
|<span data-ttu-id="3b643-105">Methode</span><span class="sxs-lookup"><span data-stu-id="3b643-105">Method</span></span>|<span data-ttu-id="3b643-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="3b643-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="3b643-107">FindAssembly-Methode</span><span class="sxs-lookup"><span data-stu-id="3b643-107">FindAssembly Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenserex-findassembly-method.md)|<span data-ttu-id="3b643-108">Diese Methode ist nicht implementiert.</span><span class="sxs-lookup"><span data-stu-id="3b643-108">This method is not implemented.</span></span> <span data-ttu-id="3b643-109">Wenn Sie aufgerufen wird, wird E_NOTIMPL zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="3b643-109">If called, it returns E_NOTIMPL.</span></span>|  
|[<span data-ttu-id="3b643-110">FindAssemblyModule-Methode</span><span class="sxs-lookup"><span data-stu-id="3b643-110">FindAssemblyModule Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenserex-findassemblymodule-method.md)|<span data-ttu-id="3b643-111">Diese Methode ist nicht implementiert.</span><span class="sxs-lookup"><span data-stu-id="3b643-111">This method is not implemented.</span></span> <span data-ttu-id="3b643-112">Wenn Sie aufgerufen wird, wird E_NOTIMPL zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="3b643-112">If called, it returns E_NOTIMPL.</span></span>|  
|[<span data-ttu-id="3b643-113">GetCORSystemDirectory-Methode</span><span class="sxs-lookup"><span data-stu-id="3b643-113">GetCORSystemDirectory Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenserex-getcorsystemdirectory-method.md)|<span data-ttu-id="3b643-114">Ruft das Verzeichnis ab, das die aktuelle Common Language Runtime (CLR) enthält.</span><span class="sxs-lookup"><span data-stu-id="3b643-114">Gets the directory that holds the current common language runtime (CLR).</span></span> <span data-ttu-id="3b643-115">Diese Methode wird nur für die Verwendung durch out-of-Process-debuggger unterstützt.</span><span class="sxs-lookup"><span data-stu-id="3b643-115">This method is supported only for use by out-of-process debuggers.</span></span> <span data-ttu-id="3b643-116">Wenn Sie von einer anderen Komponente aufgerufen wird, wird E_NOTIMPL zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="3b643-116">If called from another component, it will return E_NOTIMPL.</span></span>|  
|[<span data-ttu-id="3b643-117">GetOption-Methode</span><span class="sxs-lookup"><span data-stu-id="3b643-117">GetOption Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenserex-getoption-method.md)|<span data-ttu-id="3b643-118">Ruft den Wert der angegebenen Option für den aktuellen Metadatenbereich ab.</span><span class="sxs-lookup"><span data-stu-id="3b643-118">Gets the value of the specified option for the current metadata scope.</span></span> <span data-ttu-id="3b643-119">Mit der-Option wird gesteuert, wie Aufrufe des aktuellen Metadatenbereichs behandelt werden.</span><span class="sxs-lookup"><span data-stu-id="3b643-119">The option controls how calls to the current metadata scope are handled.</span></span>|  
|[<span data-ttu-id="3b643-120">OpenScopeOnITypeInfo-Methode</span><span class="sxs-lookup"><span data-stu-id="3b643-120">OpenScopeOnITypeInfo Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenserex-openscopeonitypeinfo-method.md)|<span data-ttu-id="3b643-121">Diese Methode ist nicht implementiert.</span><span class="sxs-lookup"><span data-stu-id="3b643-121">This method is not implemented.</span></span> <span data-ttu-id="3b643-122">Wenn Sie aufgerufen wird, wird E_NOTIMPL zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="3b643-122">If called, it returns E_NOTIMPL.</span></span>|  
|[<span data-ttu-id="3b643-123">SetOption-Methode</span><span class="sxs-lookup"><span data-stu-id="3b643-123">SetOption Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenserex-setoption-method.md)|<span data-ttu-id="3b643-124">Legt die angegebene Option auf einen angegebenen Wert für den aktuellen Metadatenbereich fest.</span><span class="sxs-lookup"><span data-stu-id="3b643-124">Sets the specified option to a given value for the current metadata scope.</span></span> <span data-ttu-id="3b643-125">Mit der-Option wird gesteuert, wie Aufrufe des aktuellen Metadatenbereichs behandelt werden.</span><span class="sxs-lookup"><span data-stu-id="3b643-125">The option controls how calls to the current metadata scope are handled.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="3b643-126">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="3b643-126">Requirements</span></span>  
 <span data-ttu-id="3b643-127">**Plattform:** Siehe [System Anforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3b643-127">**Platform:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3b643-128">**Header:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="3b643-128">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="3b643-129">**Bibliothek:** Wird als Ressource in Mscoree. dll verwendet.</span><span class="sxs-lookup"><span data-stu-id="3b643-129">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="3b643-130">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3b643-130">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3b643-131">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="3b643-131">See also</span></span>

- [<span data-ttu-id="3b643-132">Metadatenschnittstellen</span><span class="sxs-lookup"><span data-stu-id="3b643-132">Metadata Interfaces</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-interfaces.md)
- [<span data-ttu-id="3b643-133">IMetaDataDispenser-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="3b643-133">IMetaDataDispenser Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-interface.md)
- [<span data-ttu-id="3b643-134">IMetaDataEmit-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="3b643-134">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="3b643-135">IMetaDataImport-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="3b643-135">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
