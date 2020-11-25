---
title: IMetaDataImport2::EnumGenericParams-Methode
ms.date: 03/30/2017
api_name:
- IMetaDataImport2.EnumGenericParams
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport2::EnumGenericParams
helpviewer_keywords:
- EnumGenericParams method [.NET Framework metadata]
- IMetaDataImport2::EnumGenericParams method [.NET Framework metadata]
ms.assetid: b50488a5-3cf0-483c-82dc-2892a3ec61ac
topic_type:
- apiref
ms.openlocfilehash: 6b1a8e66eea6caec9dfc8d99e343c987cefa1b0c
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95702757"
---
# <a name="imetadataimport2enumgenericparams-method"></a><span data-ttu-id="f8595-102">IMetaDataImport2::EnumGenericParams-Methode</span><span class="sxs-lookup"><span data-stu-id="f8595-102">IMetaDataImport2::EnumGenericParams Method</span></span>

<span data-ttu-id="f8595-103">Ruft einen Enumerator für ein Array von generischen Parameter Token ab, die dem angegebenen TypeDef-oder MethodDef-Token zugeordnet sind.</span><span class="sxs-lookup"><span data-stu-id="f8595-103">Gets an enumerator for an array of generic parameter tokens associated with the specified TypeDef or MethodDef token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f8595-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="f8595-104">Syntax</span></span>  
  
```cpp
HRESULT EnumGenericParams (  
   [in, out] HCORENUM     *phEnum,
   [in]  mdToken          tk,  
   [out] mdGenericParam   rGenericParams[],
   [in]  ULONG            cMax,
   [out] ULONG            *pcGenericParams  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f8595-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="f8595-105">Parameters</span></span>  

 `phEnum`  
 <span data-ttu-id="f8595-106">[in, out] Ein Zeiger auf den Enumerator.</span><span class="sxs-lookup"><span data-stu-id="f8595-106">[in, out] A pointer to the enumerator.</span></span>  
  
 `tk`  
 <span data-ttu-id="f8595-107">in Das TypeDef-oder MethodDef-Token, dessen generische Parameter aufgezählt werden sollen.</span><span class="sxs-lookup"><span data-stu-id="f8595-107">[in] The TypeDef or MethodDef token whose generic parameters are to be enumerated.</span></span>  
  
 `rGenericParams`  
 <span data-ttu-id="f8595-108">vorgenommen Das Array von generischen Parametern, die aufgelistet werden sollen.</span><span class="sxs-lookup"><span data-stu-id="f8595-108">[out] The array of generic parameters to enumerate.</span></span>  
  
 `cMax`  
 <span data-ttu-id="f8595-109">in Die angeforderte maximale Anzahl von Token, die in platziert werden sollen `rGenericParams` .</span><span class="sxs-lookup"><span data-stu-id="f8595-109">[in] The requested maximum number of tokens to place in `rGenericParams`.</span></span>  
  
 `pcGenericParams`  
 <span data-ttu-id="f8595-110">vorgenommen Die zurückgegebene Anzahl von Token, die in platziert werden `rGenericParams` .</span><span class="sxs-lookup"><span data-stu-id="f8595-110">[out] The returned number of tokens placed in `rGenericParams`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="f8595-111">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="f8595-111">Return Value</span></span>  
  
|<span data-ttu-id="f8595-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="f8595-112">HRESULT</span></span>|<span data-ttu-id="f8595-113">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="f8595-113">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="f8595-114">`EnumGenericParams` wurde erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="f8595-114">`EnumGenericParams` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="f8595-115">`phEnum` hat keine Member-Elemente.</span><span class="sxs-lookup"><span data-stu-id="f8595-115">`phEnum` has no member elements.</span></span> <span data-ttu-id="f8595-116">In diesem Fall `pcGenericParams` wird auf 0 (null) festgelegt.</span><span class="sxs-lookup"><span data-stu-id="f8595-116">In this case, `pcGenericParams` is set to 0 (zero).</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="f8595-117">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="f8595-117">Requirements</span></span>  

 <span data-ttu-id="f8595-118">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f8595-118">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f8595-119">**Header:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="f8595-119">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="f8595-120">**Bibliothek:** Wird als Ressource in MsCorEE.dll verwendet.</span><span class="sxs-lookup"><span data-stu-id="f8595-120">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="f8595-121">**.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f8595-121">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f8595-122">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="f8595-122">See also</span></span>

- [<span data-ttu-id="f8595-123">IMetaDataImport2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="f8595-123">IMetaDataImport2 Interface</span></span>](imetadataimport2-interface.md)
- [<span data-ttu-id="f8595-124">IMetaDataImport-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="f8595-124">IMetaDataImport Interface</span></span>](imetadataimport-interface.md)
