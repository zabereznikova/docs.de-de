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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 96475086b1244ae75ed692dd10cb693af0be9af7
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59186952"
---
# <a name="imetadatadispenserex-interface"></a><span data-ttu-id="1f35b-102">IMetaDataDispenserEx-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="1f35b-102">IMetaDataDispenserEx Interface</span></span>
<span data-ttu-id="1f35b-103">Erweitert die [IMetaDataDispenser-Schnittstelle](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-interface.md) Schnittstelle bieten die Möglichkeit, die steuern, wie die Metadaten-APIs im aktuellen Metadatenbereich ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="1f35b-103">Extends the [IMetaDataDispenser Interface](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-interface.md) interface to provide the capability to control how the metadata APIs operate on the current metadata scope.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="1f35b-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="1f35b-104">Methods</span></span>  
  
|<span data-ttu-id="1f35b-105">Methode</span><span class="sxs-lookup"><span data-stu-id="1f35b-105">Method</span></span>|<span data-ttu-id="1f35b-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="1f35b-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="1f35b-107">FindAssembly-Methode</span><span class="sxs-lookup"><span data-stu-id="1f35b-107">FindAssembly Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenserex-findassembly-method.md)|<span data-ttu-id="1f35b-108">Diese Methode ist nicht implementiert.</span><span class="sxs-lookup"><span data-stu-id="1f35b-108">This method is not implemented.</span></span> <span data-ttu-id="1f35b-109">Wird aufgerufen, gibt E_NOTIMPL zurück.</span><span class="sxs-lookup"><span data-stu-id="1f35b-109">If called, it returns E_NOTIMPL.</span></span>|  
|[<span data-ttu-id="1f35b-110">FindAssemblyModule-Methode</span><span class="sxs-lookup"><span data-stu-id="1f35b-110">FindAssemblyModule Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenserex-findassemblymodule-method.md)|<span data-ttu-id="1f35b-111">Diese Methode ist nicht implementiert.</span><span class="sxs-lookup"><span data-stu-id="1f35b-111">This method is not implemented.</span></span> <span data-ttu-id="1f35b-112">Wird aufgerufen, gibt E_NOTIMPL zurück.</span><span class="sxs-lookup"><span data-stu-id="1f35b-112">If called, it returns E_NOTIMPL.</span></span>|  
|[<span data-ttu-id="1f35b-113">GetCORSystemDirectory-Methode</span><span class="sxs-lookup"><span data-stu-id="1f35b-113">GetCORSystemDirectory Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenserex-getcorsystemdirectory-method.md)|<span data-ttu-id="1f35b-114">Ruft das Verzeichnis, das die aktuelle common Language Runtime (CLR enthält) ab.</span><span class="sxs-lookup"><span data-stu-id="1f35b-114">Gets the directory that holds the current common language runtime (CLR).</span></span> <span data-ttu-id="1f35b-115">Diese Methode wird nur für die Verwendung von Out-of-Process-Debugger unterstützt.</span><span class="sxs-lookup"><span data-stu-id="1f35b-115">This method is supported only for use by out-of-process debuggers.</span></span> <span data-ttu-id="1f35b-116">Wenn aus einer anderen Komponente aufgerufen wird, wird er E_NOTIMPL zurückgeben.</span><span class="sxs-lookup"><span data-stu-id="1f35b-116">If called from another component, it will return E_NOTIMPL.</span></span>|  
|[<span data-ttu-id="1f35b-117">GetOption-Methode</span><span class="sxs-lookup"><span data-stu-id="1f35b-117">GetOption Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenserex-getoption-method.md)|<span data-ttu-id="1f35b-118">Ruft den Wert der angegebenen Option für den aktuellen Metadatenbereich.</span><span class="sxs-lookup"><span data-stu-id="1f35b-118">Gets the value of the specified option for the current metadata scope.</span></span> <span data-ttu-id="1f35b-119">Die Option wird gesteuert, wie Aufrufe im aktuellen Metadatenbereich behandelt werden.</span><span class="sxs-lookup"><span data-stu-id="1f35b-119">The option controls how calls to the current metadata scope are handled.</span></span>|  
|[<span data-ttu-id="1f35b-120">OpenScopeOnITypeInfo-Methode</span><span class="sxs-lookup"><span data-stu-id="1f35b-120">OpenScopeOnITypeInfo Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenserex-openscopeonitypeinfo-method.md)|<span data-ttu-id="1f35b-121">Diese Methode ist nicht implementiert.</span><span class="sxs-lookup"><span data-stu-id="1f35b-121">This method is not implemented.</span></span> <span data-ttu-id="1f35b-122">Wird aufgerufen, gibt E_NOTIMPL zurück.</span><span class="sxs-lookup"><span data-stu-id="1f35b-122">If called, it returns E_NOTIMPL.</span></span>|  
|[<span data-ttu-id="1f35b-123">SetOption-Methode</span><span class="sxs-lookup"><span data-stu-id="1f35b-123">SetOption Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenserex-setoption-method.md)|<span data-ttu-id="1f35b-124">Legt die angegebene Option auf einen angegebenen Wert für den aktuellen Metadatenbereich fest.</span><span class="sxs-lookup"><span data-stu-id="1f35b-124">Sets the specified option to a given value for the current metadata scope.</span></span> <span data-ttu-id="1f35b-125">Die Option wird gesteuert, wie Aufrufe im aktuellen Metadatenbereich behandelt werden.</span><span class="sxs-lookup"><span data-stu-id="1f35b-125">The option controls how calls to the current metadata scope are handled.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="1f35b-126">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="1f35b-126">Requirements</span></span>  
 <span data-ttu-id="1f35b-127">**Plattform:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1f35b-127">**Platform:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1f35b-128">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="1f35b-128">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="1f35b-129">**Bibliothek:** Als Ressource in MsCorEE.dll verwendet</span><span class="sxs-lookup"><span data-stu-id="1f35b-129">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 **<span data-ttu-id="1f35b-130">.NET Framework-Versionen:</span><span class="sxs-lookup"><span data-stu-id="1f35b-130">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="1f35b-131">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="1f35b-131">See also</span></span>

- [<span data-ttu-id="1f35b-132">Metadatenschnittstellen</span><span class="sxs-lookup"><span data-stu-id="1f35b-132">Metadata Interfaces</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-interfaces.md)
- [<span data-ttu-id="1f35b-133">IMetaDataDispenser-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="1f35b-133">IMetaDataDispenser Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-interface.md)
- [<span data-ttu-id="1f35b-134">IMetaDataEmit-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="1f35b-134">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="1f35b-135">IMetaDataImport-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="1f35b-135">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
