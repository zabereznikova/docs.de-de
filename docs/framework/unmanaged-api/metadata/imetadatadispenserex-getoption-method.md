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
ms.openlocfilehash: ab74b02df959fe6e6457273e67ba3b82ae6a015c
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/23/2019
ms.locfileid: "74435989"
---
# <a name="imetadatadispenserexgetoption-method"></a><span data-ttu-id="15a7e-102">IMetaDataDispenserEx::GetOption-Methode</span><span class="sxs-lookup"><span data-stu-id="15a7e-102">IMetaDataDispenserEx::GetOption Method</span></span>
<span data-ttu-id="15a7e-103">Ruft den Wert der angegebenen Option für den aktuellen Metadatenbereich ab.</span><span class="sxs-lookup"><span data-stu-id="15a7e-103">Gets the value of the specified option for the current metadata scope.</span></span> <span data-ttu-id="15a7e-104">Mit der-Option wird gesteuert, wie Aufrufe des aktuellen Metadatenbereichs behandelt werden.</span><span class="sxs-lookup"><span data-stu-id="15a7e-104">The option controls how calls to the current metadata scope are handled.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="15a7e-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="15a7e-105">Syntax</span></span>  
  
```cpp  
HRESULT GetOption (  
    [in]  REFGUID         optionId,   
    [out] const VARIANT   *pValue  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="15a7e-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="15a7e-106">Parameters</span></span>  
 `optionId`  
 <span data-ttu-id="15a7e-107">in Ein Zeiger auf eine GUID, die die abzurufende Option angibt.</span><span class="sxs-lookup"><span data-stu-id="15a7e-107">[in] A pointer to a GUID that specifies the option to be retrieved.</span></span> <span data-ttu-id="15a7e-108">Eine Liste der unterstützten GUIDs finden Sie im Abschnitt "Hinweise".</span><span class="sxs-lookup"><span data-stu-id="15a7e-108">See the Remarks section for a list of supported GUIDs.</span></span>  
  
 `pValue`  
 <span data-ttu-id="15a7e-109">vorgenommen Der Wert der zurückgegebenen Option.</span><span class="sxs-lookup"><span data-stu-id="15a7e-109">[out] The value of the returned option.</span></span> <span data-ttu-id="15a7e-110">Der Typ dieses Werts ist eine Variante des Typs der angegebenen Option.</span><span class="sxs-lookup"><span data-stu-id="15a7e-110">The type of this value will be a variant of the specified option's type.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="15a7e-111">Hinweise</span><span class="sxs-lookup"><span data-stu-id="15a7e-111">Remarks</span></span>  
 <span data-ttu-id="15a7e-112">In der folgenden Liste werden die GUIDs angezeigt, die für diese Methode unterstützt werden.</span><span class="sxs-lookup"><span data-stu-id="15a7e-112">The following list shows the GUIDs that are supported for this method.</span></span> <span data-ttu-id="15a7e-113">Beschreibungen finden Sie unter der [IMetaDataDispenserEx:: SetOption](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenserex-setoption-method.md) -Methode.</span><span class="sxs-lookup"><span data-stu-id="15a7e-113">For descriptions, see the [IMetaDataDispenserEx::SetOption](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenserex-setoption-method.md) method.</span></span> <span data-ttu-id="15a7e-114">Wenn `optionId` nicht in dieser Liste enthalten ist, gibt diese Methode HRESULT `E_INVALIDARG`zurück, was auf einen falschen Parameter hinweist.</span><span class="sxs-lookup"><span data-stu-id="15a7e-114">If `optionId` is not in this list, this method returns HRESULT `E_INVALIDARG`, indicating an incorrect parameter.</span></span>  
  
- <span data-ttu-id="15a7e-115">MetaDataCheckDuplicatesFor</span><span class="sxs-lookup"><span data-stu-id="15a7e-115">MetaDataCheckDuplicatesFor</span></span>  
  
- <span data-ttu-id="15a7e-116">MetaDataRefToDefCheck</span><span class="sxs-lookup"><span data-stu-id="15a7e-116">MetaDataRefToDefCheck</span></span>  
  
- <span data-ttu-id="15a7e-117">MetaDataNotificationForTokenMovement</span><span class="sxs-lookup"><span data-stu-id="15a7e-117">MetaDataNotificationForTokenMovement</span></span>  
  
- <span data-ttu-id="15a7e-118">MetaDataSetENC</span><span class="sxs-lookup"><span data-stu-id="15a7e-118">MetaDataSetENC</span></span>  
  
- <span data-ttu-id="15a7e-119">MetaDataErrorIfEmitOutOfOrder</span><span class="sxs-lookup"><span data-stu-id="15a7e-119">MetaDataErrorIfEmitOutOfOrder</span></span>  
  
- <span data-ttu-id="15a7e-120">MetaDataGenerateTCEAdapters</span><span class="sxs-lookup"><span data-stu-id="15a7e-120">MetaDataGenerateTCEAdapters</span></span>  
  
- <span data-ttu-id="15a7e-121">MetaDataLinkerOptions</span><span class="sxs-lookup"><span data-stu-id="15a7e-121">MetaDataLinkerOptions</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="15a7e-122">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="15a7e-122">Requirements</span></span>  
 <span data-ttu-id="15a7e-123">**Plattform:** Siehe [System Anforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="15a7e-123">**Platform:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="15a7e-124">**Header:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="15a7e-124">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="15a7e-125">**Bibliothek:** Wird als Ressource in Mscoree. dll verwendet.</span><span class="sxs-lookup"><span data-stu-id="15a7e-125">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="15a7e-126">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="15a7e-126">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="15a7e-127">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="15a7e-127">See also</span></span>

- [<span data-ttu-id="15a7e-128">IMetaDataDispenserEx-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="15a7e-128">IMetaDataDispenserEx Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenserex-interface.md)
- [<span data-ttu-id="15a7e-129">IMetaDataDispenser-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="15a7e-129">IMetaDataDispenser Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-interface.md)
