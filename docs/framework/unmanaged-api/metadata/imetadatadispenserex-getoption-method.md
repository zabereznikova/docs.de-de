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
ms.openlocfilehash: 816e2f2dc7d4d00f74f67720ee45d7b3483e57fa
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79177716"
---
# <a name="imetadatadispenserexgetoption-method"></a><span data-ttu-id="6d523-102">IMetaDataDispenserEx::GetOption-Methode</span><span class="sxs-lookup"><span data-stu-id="6d523-102">IMetaDataDispenserEx::GetOption Method</span></span>
<span data-ttu-id="6d523-103">Ruft den Wert der angegebenen Option für den aktuellen Metadatenbereich ab.</span><span class="sxs-lookup"><span data-stu-id="6d523-103">Gets the value of the specified option for the current metadata scope.</span></span> <span data-ttu-id="6d523-104">Die Option steuert, wie Aufrufe des aktuellen Metadatenbereichs verarbeitet werden.</span><span class="sxs-lookup"><span data-stu-id="6d523-104">The option controls how calls to the current metadata scope are handled.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6d523-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="6d523-105">Syntax</span></span>  
  
```cpp  
HRESULT GetOption (  
    [in]  REFGUID         optionId,
    [out] const VARIANT   *pValue  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6d523-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="6d523-106">Parameters</span></span>  
 `optionId`  
 <span data-ttu-id="6d523-107">[in] Ein Zeiger auf eine GUID, der die abzudannende Option angibt.</span><span class="sxs-lookup"><span data-stu-id="6d523-107">[in] A pointer to a GUID that specifies the option to be retrieved.</span></span> <span data-ttu-id="6d523-108">Eine Liste der unterstützten GUIDs finden Sie im Abschnitt "Hinweise".</span><span class="sxs-lookup"><span data-stu-id="6d523-108">See the Remarks section for a list of supported GUIDs.</span></span>  
  
 `pValue`  
 <span data-ttu-id="6d523-109">[out] Der Wert der zurückgegebenen Option.</span><span class="sxs-lookup"><span data-stu-id="6d523-109">[out] The value of the returned option.</span></span> <span data-ttu-id="6d523-110">Der Typ dieses Werts ist eine Variante des Typs der angegebenen Option.</span><span class="sxs-lookup"><span data-stu-id="6d523-110">The type of this value will be a variant of the specified option's type.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6d523-111">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="6d523-111">Remarks</span></span>  
 <span data-ttu-id="6d523-112">Die folgende Liste zeigt die GUIDs, die für diese Methode unterstützt werden.</span><span class="sxs-lookup"><span data-stu-id="6d523-112">The following list shows the GUIDs that are supported for this method.</span></span> <span data-ttu-id="6d523-113">Beschreibungen finden Sie in der [IMetaDataDispenserEx::SetOption-Methode.](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenserex-setoption-method.md)</span><span class="sxs-lookup"><span data-stu-id="6d523-113">For descriptions, see the [IMetaDataDispenserEx::SetOption](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenserex-setoption-method.md) method.</span></span> <span data-ttu-id="6d523-114">Wenn `optionId` dies nicht in dieser Liste `E_INVALIDARG`enthalten ist, gibt diese Methode HRESULT zurück, was auf einen falschen Parameter hinweist.</span><span class="sxs-lookup"><span data-stu-id="6d523-114">If `optionId` is not in this list, this method returns HRESULT `E_INVALIDARG`, indicating an incorrect parameter.</span></span>  
  
- <span data-ttu-id="6d523-115">MetaDataCheckDuplicatesFor</span><span class="sxs-lookup"><span data-stu-id="6d523-115">MetaDataCheckDuplicatesFor</span></span>  
  
- <span data-ttu-id="6d523-116">MetaDataRefToDefCheck</span><span class="sxs-lookup"><span data-stu-id="6d523-116">MetaDataRefToDefCheck</span></span>  
  
- <span data-ttu-id="6d523-117">MetaDataNotificationForTokenMovement</span><span class="sxs-lookup"><span data-stu-id="6d523-117">MetaDataNotificationForTokenMovement</span></span>  
  
- <span data-ttu-id="6d523-118">MetaDataSetENC</span><span class="sxs-lookup"><span data-stu-id="6d523-118">MetaDataSetENC</span></span>  
  
- <span data-ttu-id="6d523-119">MetaDataErrorIfEmitOutOfOrder</span><span class="sxs-lookup"><span data-stu-id="6d523-119">MetaDataErrorIfEmitOutOfOrder</span></span>  
  
- <span data-ttu-id="6d523-120">MetaDataGenerateTCEAdapter</span><span class="sxs-lookup"><span data-stu-id="6d523-120">MetaDataGenerateTCEAdapters</span></span>  
  
- <span data-ttu-id="6d523-121">MetaDataLinkerOptionen</span><span class="sxs-lookup"><span data-stu-id="6d523-121">MetaDataLinkerOptions</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6d523-122">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="6d523-122">Requirements</span></span>  
 <span data-ttu-id="6d523-123">**Plattform:** Siehe [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6d523-123">**Platform:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6d523-124">**Kopfzeile:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="6d523-124">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="6d523-125">**Bibliothek:** Wird als Ressource in MsCorEE.dll verwendet</span><span class="sxs-lookup"><span data-stu-id="6d523-125">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="6d523-126">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6d523-126">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6d523-127">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="6d523-127">See also</span></span>

- [<span data-ttu-id="6d523-128">IMetaDataDispenserEx-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="6d523-128">IMetaDataDispenserEx Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenserex-interface.md)
- [<span data-ttu-id="6d523-129">IMetaDataDispenser-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="6d523-129">IMetaDataDispenser Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-interface.md)
