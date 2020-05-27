---
title: IMetaDataEmit::GetTokenFromTypeSpec-Methode
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.GetTokenFromTypeSpec
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::GetTokenFromTypeSpec
helpviewer_keywords:
- GetTokenFromTypeSpec method [.NET Framework metadata]
- IMetaDataEmit::GetTokenFromTypeSpec method [.NET Framework metadata]
ms.assetid: 7de6447a-a751-49d8-87e2-951cee77b536
topic_type:
- apiref
ms.openlocfilehash: 1cd09fe785bb37c892417ddbf1efaaaa90e121bf
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/27/2020
ms.locfileid: "84009235"
---
# <a name="imetadataemitgettokenfromtypespec-method"></a><span data-ttu-id="aa8ba-102">IMetaDataEmit::GetTokenFromTypeSpec-Methode</span><span class="sxs-lookup"><span data-stu-id="aa8ba-102">IMetaDataEmit::GetTokenFromTypeSpec Method</span></span>
<span data-ttu-id="aa8ba-103">Ruft ein Metadatentoken für den Typ mit der angegebenen Metadatensignatur ab.</span><span class="sxs-lookup"><span data-stu-id="aa8ba-103">Gets a metadata token for the type with the specified metadata signature.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="aa8ba-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="aa8ba-104">Syntax</span></span>  
  
```cpp  
HRESULT GetTokenFromTypeSpec (
    [in]  PCCOR_SIGNATURE       pvSig,
    [in]  ULONG                 cbSig,
    [out] mdTypeSpec            *ptypespec
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="aa8ba-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="aa8ba-105">Parameters</span></span>  
 `pvSig`  
 <span data-ttu-id="aa8ba-106">in Die Signatur, die definiert wird.</span><span class="sxs-lookup"><span data-stu-id="aa8ba-106">[in] The signature being defined.</span></span>  
  
 `cbSig`  
 <span data-ttu-id="aa8ba-107">in Die Anzahl von Bytes in `pvSig` .</span><span class="sxs-lookup"><span data-stu-id="aa8ba-107">[in] The count of bytes in `pvSig`.</span></span>  
  
 `ptypespec`  
 <span data-ttu-id="aa8ba-108">vorgenommen Das `mdTypeSpec` zugewiesene Token.</span><span class="sxs-lookup"><span data-stu-id="aa8ba-108">[out] The `mdTypeSpec` token assigned.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="aa8ba-109">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="aa8ba-109">Requirements</span></span>  
 <span data-ttu-id="aa8ba-110">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="aa8ba-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="aa8ba-111">**Header:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="aa8ba-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="aa8ba-112">**Bibliothek:** Wird als Ressource in Mscoree. dll verwendet.</span><span class="sxs-lookup"><span data-stu-id="aa8ba-112">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="aa8ba-113">**.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="aa8ba-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="aa8ba-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="aa8ba-114">See also</span></span>

- [<span data-ttu-id="aa8ba-115">IMetaDataEmit-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="aa8ba-115">IMetaDataEmit Interface</span></span>](imetadataemit-interface.md)
- [<span data-ttu-id="aa8ba-116">IMetaDataEmit2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="aa8ba-116">IMetaDataEmit2 Interface</span></span>](imetadataemit2-interface.md)
