---
title: IMetaDataDispenserEx::GetOption-Methode
ms.date: 03/30/2017
api_name:
- IMetaDataDispenserEx.GetOption
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataDispenserEx::GetOption
helpviewer_keywords:
- GetOption method [.NET Framework metadata]
- IMetaDataDispenserEx::GetOption method [.NET Framework metadata]
ms.assetid: d7f794e5-8e25-4d65-850a-7c34fbfce87d
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: a117fcdf2ba9d37fb5483cc85fb575e5d3476794
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33447673"
---
# <a name="imetadatadispenserexgetoption-method"></a><span data-ttu-id="92f86-102">IMetaDataDispenserEx::GetOption-Methode</span><span class="sxs-lookup"><span data-stu-id="92f86-102">IMetaDataDispenserEx::GetOption Method</span></span>
<span data-ttu-id="92f86-103">Ruft den Wert der angegebenen Option für den aktuellen Metadatenbereich ab.</span><span class="sxs-lookup"><span data-stu-id="92f86-103">Gets the value of the specified option for the current metadata scope.</span></span> <span data-ttu-id="92f86-104">Die Option wird gesteuert, wie Aufrufe im aktuellen Metadatenbereich behandelt werden.</span><span class="sxs-lookup"><span data-stu-id="92f86-104">The option controls how calls to the current metadata scope are handled.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="92f86-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="92f86-105">Syntax</span></span>  
  
```  
HRESULT GetOption (  
    [in]  REFGUID         optionId,   
    [out] const VARIANT   *pValue  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="92f86-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="92f86-106">Parameters</span></span>  
 `optionId`  
 <span data-ttu-id="92f86-107">[in] Ein Zeiger auf eine GUID fest, der angibt, die Option abgerufen werden sollen.</span><span class="sxs-lookup"><span data-stu-id="92f86-107">[in] A pointer to a GUID that specifies the option to be retrieved.</span></span> <span data-ttu-id="92f86-108">Finden Sie im Abschnitt "Hinweise" eine Liste der unterstützten GUIDs.</span><span class="sxs-lookup"><span data-stu-id="92f86-108">See the Remarks section for a list of supported GUIDs.</span></span>  
  
 `pValue`  
 <span data-ttu-id="92f86-109">[out] Der Wert der Option "zurückgegebenen".</span><span class="sxs-lookup"><span data-stu-id="92f86-109">[out] The value of the returned option.</span></span> <span data-ttu-id="92f86-110">Der Typ dieses Werts wird eine Variante des Typs für die angegebene Option sein.</span><span class="sxs-lookup"><span data-stu-id="92f86-110">The type of this value will be a variant of the specified option's type.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="92f86-111">Hinweise</span><span class="sxs-lookup"><span data-stu-id="92f86-111">Remarks</span></span>  
 <span data-ttu-id="92f86-112">Die folgende Liste enthält die GUIDs, die für diese Methode unterstützt werden.</span><span class="sxs-lookup"><span data-stu-id="92f86-112">The following list shows the GUIDs that are supported for this method.</span></span> <span data-ttu-id="92f86-113">Beschreibungen finden Sie die [IMetaDataDispenserEx:: SetOption](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenserex-setoption-method.md) Methode.</span><span class="sxs-lookup"><span data-stu-id="92f86-113">For descriptions, see the [IMetaDataDispenserEx::SetOption](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenserex-setoption-method.md) method.</span></span> <span data-ttu-id="92f86-114">Wenn `optionId` ist nicht in dieser Liste, gibt diese Methode HRESULT `E_INVALIDARG`, einen falschen Parameter angibt.</span><span class="sxs-lookup"><span data-stu-id="92f86-114">If `optionId` is not in this list, this method returns HRESULT `E_INVALIDARG`, indicating an incorrect parameter.</span></span>  
  
-   <span data-ttu-id="92f86-115">MetaDataCheckDuplicatesFor</span><span class="sxs-lookup"><span data-stu-id="92f86-115">MetaDataCheckDuplicatesFor</span></span>  
  
-   <span data-ttu-id="92f86-116">MetaDataRefToDefCheck</span><span class="sxs-lookup"><span data-stu-id="92f86-116">MetaDataRefToDefCheck</span></span>  
  
-   <span data-ttu-id="92f86-117">MetaDataNotificationForTokenMovement</span><span class="sxs-lookup"><span data-stu-id="92f86-117">MetaDataNotificationForTokenMovement</span></span>  
  
-   <span data-ttu-id="92f86-118">MetaDataSetENC</span><span class="sxs-lookup"><span data-stu-id="92f86-118">MetaDataSetENC</span></span>  
  
-   <span data-ttu-id="92f86-119">MetaDataErrorIfEmitOutOfOrder</span><span class="sxs-lookup"><span data-stu-id="92f86-119">MetaDataErrorIfEmitOutOfOrder</span></span>  
  
-   <span data-ttu-id="92f86-120">MetaDataGenerateTCEAdapters</span><span class="sxs-lookup"><span data-stu-id="92f86-120">MetaDataGenerateTCEAdapters</span></span>  
  
-   <span data-ttu-id="92f86-121">MetaDataLinkerOptions</span><span class="sxs-lookup"><span data-stu-id="92f86-121">MetaDataLinkerOptions</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="92f86-122">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="92f86-122">Requirements</span></span>  
 <span data-ttu-id="92f86-123">**Plattform:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="92f86-123">**Platform:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="92f86-124">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="92f86-124">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="92f86-125">**Bibliothek:** als Ressource in MsCorEE.dll verwendet</span><span class="sxs-lookup"><span data-stu-id="92f86-125">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="92f86-126">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="92f86-126">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="92f86-127">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="92f86-127">See Also</span></span>  
 [<span data-ttu-id="92f86-128">IMetaDataDispenserEx-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="92f86-128">IMetaDataDispenserEx Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenserex-interface.md)  
 [<span data-ttu-id="92f86-129">IMetaDataDispenser-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="92f86-129">IMetaDataDispenser Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-interface.md)
