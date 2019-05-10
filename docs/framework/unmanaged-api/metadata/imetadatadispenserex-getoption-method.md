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
ms.openlocfilehash: 4afbe64979ec69a192af955400ca8f4118102bd4
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/28/2019
ms.locfileid: "64665040"
---
# <a name="imetadatadispenserexgetoption-method"></a><span data-ttu-id="03952-102">IMetaDataDispenserEx::GetOption-Methode</span><span class="sxs-lookup"><span data-stu-id="03952-102">IMetaDataDispenserEx::GetOption Method</span></span>
<span data-ttu-id="03952-103">Ruft den Wert der angegebenen Option für den aktuellen Metadatenbereich.</span><span class="sxs-lookup"><span data-stu-id="03952-103">Gets the value of the specified option for the current metadata scope.</span></span> <span data-ttu-id="03952-104">Die Option wird gesteuert, wie Aufrufe im aktuellen Metadatenbereich behandelt werden.</span><span class="sxs-lookup"><span data-stu-id="03952-104">The option controls how calls to the current metadata scope are handled.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="03952-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="03952-105">Syntax</span></span>  
  
```  
HRESULT GetOption (  
    [in]  REFGUID         optionId,   
    [out] const VARIANT   *pValue  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="03952-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="03952-106">Parameters</span></span>  
 `optionId`  
 <span data-ttu-id="03952-107">[in] Ein Zeiger auf eine GUID, der angibt, die Möglichkeit, die abgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="03952-107">[in] A pointer to a GUID that specifies the option to be retrieved.</span></span> <span data-ttu-id="03952-108">Finden Sie im Abschnitt "Hinweise" eine Liste der unterstützten GUIDs.</span><span class="sxs-lookup"><span data-stu-id="03952-108">See the Remarks section for a list of supported GUIDs.</span></span>  
  
 `pValue`  
 <span data-ttu-id="03952-109">[out] Der Wert der Option "zurückgegebene".</span><span class="sxs-lookup"><span data-stu-id="03952-109">[out] The value of the returned option.</span></span> <span data-ttu-id="03952-110">Der Typ dieses Werts wird eine Variante des Typs für die angegebene Option sein.</span><span class="sxs-lookup"><span data-stu-id="03952-110">The type of this value will be a variant of the specified option's type.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="03952-111">Hinweise</span><span class="sxs-lookup"><span data-stu-id="03952-111">Remarks</span></span>  
 <span data-ttu-id="03952-112">Die folgende Liste enthält die GUIDs, die für diese Methode unterstützt werden.</span><span class="sxs-lookup"><span data-stu-id="03952-112">The following list shows the GUIDs that are supported for this method.</span></span> <span data-ttu-id="03952-113">Beschreibungen, finden Sie unter den [IMetaDataDispenserEx:: SetOption](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenserex-setoption-method.md) Methode.</span><span class="sxs-lookup"><span data-stu-id="03952-113">For descriptions, see the [IMetaDataDispenserEx::SetOption](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenserex-setoption-method.md) method.</span></span> <span data-ttu-id="03952-114">Wenn `optionId` ist nicht in der Liste, gibt diese Methode HRESULT zurück, mit denen `E_INVALIDARG`, was einen falschen Parameter angibt.</span><span class="sxs-lookup"><span data-stu-id="03952-114">If `optionId` is not in this list, this method returns HRESULT `E_INVALIDARG`, indicating an incorrect parameter.</span></span>  
  
- <span data-ttu-id="03952-115">MetaDataCheckDuplicatesFor</span><span class="sxs-lookup"><span data-stu-id="03952-115">MetaDataCheckDuplicatesFor</span></span>  
  
- <span data-ttu-id="03952-116">MetaDataRefToDefCheck</span><span class="sxs-lookup"><span data-stu-id="03952-116">MetaDataRefToDefCheck</span></span>  
  
- <span data-ttu-id="03952-117">MetaDataNotificationForTokenMovement</span><span class="sxs-lookup"><span data-stu-id="03952-117">MetaDataNotificationForTokenMovement</span></span>  
  
- <span data-ttu-id="03952-118">MetaDataSetENC</span><span class="sxs-lookup"><span data-stu-id="03952-118">MetaDataSetENC</span></span>  
  
- <span data-ttu-id="03952-119">MetaDataErrorIfEmitOutOfOrder</span><span class="sxs-lookup"><span data-stu-id="03952-119">MetaDataErrorIfEmitOutOfOrder</span></span>  
  
- <span data-ttu-id="03952-120">MetaDataGenerateTCEAdapters</span><span class="sxs-lookup"><span data-stu-id="03952-120">MetaDataGenerateTCEAdapters</span></span>  
  
- <span data-ttu-id="03952-121">MetaDataLinkerOptions</span><span class="sxs-lookup"><span data-stu-id="03952-121">MetaDataLinkerOptions</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="03952-122">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="03952-122">Requirements</span></span>  
 <span data-ttu-id="03952-123">**Plattform:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="03952-123">**Platform:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="03952-124">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="03952-124">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="03952-125">**Bibliothek:** Als Ressource in MsCorEE.dll verwendet</span><span class="sxs-lookup"><span data-stu-id="03952-125">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="03952-126">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="03952-126">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="03952-127">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="03952-127">See also</span></span>

- [<span data-ttu-id="03952-128">IMetaDataDispenserEx-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="03952-128">IMetaDataDispenserEx Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenserex-interface.md)
- [<span data-ttu-id="03952-129">IMetaDataDispenser-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="03952-129">IMetaDataDispenser Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-interface.md)
