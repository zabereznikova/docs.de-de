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
ms.openlocfilehash: 96f0c0c254ce255581ac2937c805096918ab29e8
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/27/2020
ms.locfileid: "84008052"
---
# <a name="imetadatadispenserex-interface"></a><span data-ttu-id="13255-102">IMetaDataDispenserEx-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="13255-102">IMetaDataDispenserEx Interface</span></span>
<span data-ttu-id="13255-103">Erweitert die Schnittstelle der [IMetaDataDispenser-Schnittstelle](imetadatadispenser-interface.md) und bietet die Möglichkeit, zu steuern, wie die Metadaten-APIs mit dem aktuellen Metadatenbereich arbeiten.</span><span class="sxs-lookup"><span data-stu-id="13255-103">Extends the [IMetaDataDispenser Interface](imetadatadispenser-interface.md) interface to provide the capability to control how the metadata APIs operate on the current metadata scope.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="13255-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="13255-104">Methods</span></span>  
  
|<span data-ttu-id="13255-105">Methode</span><span class="sxs-lookup"><span data-stu-id="13255-105">Method</span></span>|<span data-ttu-id="13255-106">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="13255-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="13255-107">FindAssembly-Methode</span><span class="sxs-lookup"><span data-stu-id="13255-107">FindAssembly Method</span></span>](imetadatadispenserex-findassembly-method.md)|<span data-ttu-id="13255-108">Diese Methode ist nicht implementiert.</span><span class="sxs-lookup"><span data-stu-id="13255-108">This method is not implemented.</span></span> <span data-ttu-id="13255-109">Wenn Sie aufgerufen wird, wird E_NOTIMPL zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="13255-109">If called, it returns E_NOTIMPL.</span></span>|  
|[<span data-ttu-id="13255-110">FindAssemblyModule-Methode</span><span class="sxs-lookup"><span data-stu-id="13255-110">FindAssemblyModule Method</span></span>](imetadatadispenserex-findassemblymodule-method.md)|<span data-ttu-id="13255-111">Diese Methode ist nicht implementiert.</span><span class="sxs-lookup"><span data-stu-id="13255-111">This method is not implemented.</span></span> <span data-ttu-id="13255-112">Wenn Sie aufgerufen wird, wird E_NOTIMPL zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="13255-112">If called, it returns E_NOTIMPL.</span></span>|  
|[<span data-ttu-id="13255-113">GetCORSystemDirectory-Methode</span><span class="sxs-lookup"><span data-stu-id="13255-113">GetCORSystemDirectory Method</span></span>](imetadatadispenserex-getcorsystemdirectory-method.md)|<span data-ttu-id="13255-114">Ruft das Verzeichnis ab, das die aktuelle Common Language Runtime (CLR) enthält.</span><span class="sxs-lookup"><span data-stu-id="13255-114">Gets the directory that holds the current common language runtime (CLR).</span></span> <span data-ttu-id="13255-115">Diese Methode wird nur für die Verwendung durch out-of-Process-debuggger unterstützt.</span><span class="sxs-lookup"><span data-stu-id="13255-115">This method is supported only for use by out-of-process debuggers.</span></span> <span data-ttu-id="13255-116">Wenn Sie von einer anderen Komponente aufgerufen wird, wird E_NOTIMPL zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="13255-116">If called from another component, it will return E_NOTIMPL.</span></span>|  
|[<span data-ttu-id="13255-117">GetOption-Methode</span><span class="sxs-lookup"><span data-stu-id="13255-117">GetOption Method</span></span>](imetadatadispenserex-getoption-method.md)|<span data-ttu-id="13255-118">Ruft den Wert der angegebenen Option für den aktuellen Metadatenbereich ab.</span><span class="sxs-lookup"><span data-stu-id="13255-118">Gets the value of the specified option for the current metadata scope.</span></span> <span data-ttu-id="13255-119">Mit der-Option wird gesteuert, wie Aufrufe des aktuellen Metadatenbereichs behandelt werden.</span><span class="sxs-lookup"><span data-stu-id="13255-119">The option controls how calls to the current metadata scope are handled.</span></span>|  
|[<span data-ttu-id="13255-120">OpenScopeOnITypeInfo-Methode</span><span class="sxs-lookup"><span data-stu-id="13255-120">OpenScopeOnITypeInfo Method</span></span>](imetadatadispenserex-openscopeonitypeinfo-method.md)|<span data-ttu-id="13255-121">Diese Methode ist nicht implementiert.</span><span class="sxs-lookup"><span data-stu-id="13255-121">This method is not implemented.</span></span> <span data-ttu-id="13255-122">Wenn Sie aufgerufen wird, wird E_NOTIMPL zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="13255-122">If called, it returns E_NOTIMPL.</span></span>|  
|[<span data-ttu-id="13255-123">SetOption-Methode</span><span class="sxs-lookup"><span data-stu-id="13255-123">SetOption Method</span></span>](imetadatadispenserex-setoption-method.md)|<span data-ttu-id="13255-124">Legt die angegebene Option auf einen angegebenen Wert für den aktuellen Metadatenbereich fest.</span><span class="sxs-lookup"><span data-stu-id="13255-124">Sets the specified option to a given value for the current metadata scope.</span></span> <span data-ttu-id="13255-125">Mit der-Option wird gesteuert, wie Aufrufe des aktuellen Metadatenbereichs behandelt werden.</span><span class="sxs-lookup"><span data-stu-id="13255-125">The option controls how calls to the current metadata scope are handled.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="13255-126">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="13255-126">Requirements</span></span>  
 <span data-ttu-id="13255-127">**Plattform:** Siehe [System Anforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="13255-127">**Platform:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="13255-128">**Header:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="13255-128">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="13255-129">**Bibliothek:** Wird als Ressource in Mscoree. dll verwendet.</span><span class="sxs-lookup"><span data-stu-id="13255-129">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="13255-130">**.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="13255-130">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="13255-131">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="13255-131">See also</span></span>

- [<span data-ttu-id="13255-132">Metadatenschnittstellen</span><span class="sxs-lookup"><span data-stu-id="13255-132">Metadata Interfaces</span></span>](metadata-interfaces.md)
- [<span data-ttu-id="13255-133">IMetaDataDispenser-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="13255-133">IMetaDataDispenser Interface</span></span>](imetadatadispenser-interface.md)
- [<span data-ttu-id="13255-134">IMetaDataEmit-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="13255-134">IMetaDataEmit Interface</span></span>](imetadataemit-interface.md)
- [<span data-ttu-id="13255-135">IMetaDataImport-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="13255-135">IMetaDataImport Interface</span></span>](imetadataimport-interface.md)
