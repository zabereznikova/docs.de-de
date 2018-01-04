---
title: IMetaDataDispenserEx::GetOption-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataDispenserEx.GetOption
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataDispenserEx::GetOption
helpviewer_keywords:
- GetOption method [.NET Framework metadata]
- IMetaDataDispenserEx::GetOption method [.NET Framework metadata]
ms.assetid: d7f794e5-8e25-4d65-850a-7c34fbfce87d
topic_type: apiref
caps.latest.revision: "16"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 1fd59fa20e95de8486eaa7f18a63333459361ac8
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="imetadatadispenserexgetoption-method"></a><span data-ttu-id="a362a-102">IMetaDataDispenserEx::GetOption-Methode</span><span class="sxs-lookup"><span data-stu-id="a362a-102">IMetaDataDispenserEx::GetOption Method</span></span>
<span data-ttu-id="a362a-103">Ruft den Wert der angegebenen Option für den aktuellen Metadatenbereich ab.</span><span class="sxs-lookup"><span data-stu-id="a362a-103">Gets the value of the specified option for the current metadata scope.</span></span> <span data-ttu-id="a362a-104">Die Option wird gesteuert, wie Aufrufe im aktuellen Metadatenbereich behandelt werden.</span><span class="sxs-lookup"><span data-stu-id="a362a-104">The option controls how calls to the current metadata scope are handled.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a362a-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="a362a-105">Syntax</span></span>  
  
```  
HRESULT GetOption (  
    [in]  REFGUID         optionId,   
    [out] const VARIANT   *pValue  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="a362a-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="a362a-106">Parameters</span></span>  
 `optionId`  
 <span data-ttu-id="a362a-107">[in] Ein Zeiger auf eine GUID fest, der angibt, die Option abgerufen werden sollen.</span><span class="sxs-lookup"><span data-stu-id="a362a-107">[in] A pointer to a GUID that specifies the option to be retrieved.</span></span> <span data-ttu-id="a362a-108">Finden Sie im Abschnitt "Hinweise" eine Liste der unterstützten GUIDs.</span><span class="sxs-lookup"><span data-stu-id="a362a-108">See the Remarks section for a list of supported GUIDs.</span></span>  
  
 `pValue`  
 <span data-ttu-id="a362a-109">[out] Der Wert der Option "zurückgegebenen".</span><span class="sxs-lookup"><span data-stu-id="a362a-109">[out] The value of the returned option.</span></span> <span data-ttu-id="a362a-110">Der Typ dieses Werts wird eine Variante des Typs für die angegebene Option sein.</span><span class="sxs-lookup"><span data-stu-id="a362a-110">The type of this value will be a variant of the specified option's type.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a362a-111">Hinweise</span><span class="sxs-lookup"><span data-stu-id="a362a-111">Remarks</span></span>  
 <span data-ttu-id="a362a-112">Die folgende Liste enthält die GUIDs, die für diese Methode unterstützt werden.</span><span class="sxs-lookup"><span data-stu-id="a362a-112">The following list shows the GUIDs that are supported for this method.</span></span> <span data-ttu-id="a362a-113">Beschreibungen finden Sie die [IMetaDataDispenserEx:: SetOption](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenserex-setoption-method.md) Methode.</span><span class="sxs-lookup"><span data-stu-id="a362a-113">For descriptions, see the [IMetaDataDispenserEx::SetOption](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenserex-setoption-method.md) method.</span></span> <span data-ttu-id="a362a-114">Wenn `optionId` ist nicht in dieser Liste, gibt diese Methode HRESULT `E_INVALIDARG`, einen falschen Parameter angibt.</span><span class="sxs-lookup"><span data-stu-id="a362a-114">If `optionId` is not in this list, this method returns HRESULT `E_INVALIDARG`, indicating an incorrect parameter.</span></span>  
  
-   <span data-ttu-id="a362a-115">MetaDataCheckDuplicatesFor</span><span class="sxs-lookup"><span data-stu-id="a362a-115">MetaDataCheckDuplicatesFor</span></span>  
  
-   <span data-ttu-id="a362a-116">MetaDataRefToDefCheck</span><span class="sxs-lookup"><span data-stu-id="a362a-116">MetaDataRefToDefCheck</span></span>  
  
-   <span data-ttu-id="a362a-117">MetaDataNotificationForTokenMovement</span><span class="sxs-lookup"><span data-stu-id="a362a-117">MetaDataNotificationForTokenMovement</span></span>  
  
-   <span data-ttu-id="a362a-118">MetaDataSetENC</span><span class="sxs-lookup"><span data-stu-id="a362a-118">MetaDataSetENC</span></span>  
  
-   <span data-ttu-id="a362a-119">MetaDataErrorIfEmitOutOfOrder</span><span class="sxs-lookup"><span data-stu-id="a362a-119">MetaDataErrorIfEmitOutOfOrder</span></span>  
  
-   <span data-ttu-id="a362a-120">MetaDataGenerateTCEAdapters</span><span class="sxs-lookup"><span data-stu-id="a362a-120">MetaDataGenerateTCEAdapters</span></span>  
  
-   <span data-ttu-id="a362a-121">MetaDataLinkerOptions</span><span class="sxs-lookup"><span data-stu-id="a362a-121">MetaDataLinkerOptions</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a362a-122">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="a362a-122">Requirements</span></span>  
 <span data-ttu-id="a362a-123">**Plattform:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a362a-123">**Platform:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a362a-124">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="a362a-124">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="a362a-125">**Bibliothek:** als Ressource in MsCorEE.dll verwendet</span><span class="sxs-lookup"><span data-stu-id="a362a-125">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="a362a-126">**.NET Framework-Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a362a-126">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a362a-127">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a362a-127">See Also</span></span>  
 [<span data-ttu-id="a362a-128">IMetaDataDispenserEx-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="a362a-128">IMetaDataDispenserEx Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenserex-interface.md)  
 [<span data-ttu-id="a362a-129">IMetaDataDispenser-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="a362a-129">IMetaDataDispenser Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-interface.md)
