---
title: IMetaDataImport::EnumTypeRefs-Methode
ms.date: 03/30/2017
api_name:
- IMetaDataImport.EnumTypeRefs
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::EnumTypeRefs
helpviewer_keywords:
- EnumTypeRefs method [.NET Framework metadata]
- IMetaDataImport::EnumTypeRefs method [.NET Framework metadata]
ms.assetid: b4896b8f-8e97-469c-8089-e72a025661b5
topic_type:
- apiref
ms.openlocfilehash: e77520552eea9b58e4358cc5928e5ce666037009
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95678154"
---
# <a name="imetadataimportenumtyperefs-method"></a><span data-ttu-id="ba168-102">IMetaDataImport::EnumTypeRefs-Methode</span><span class="sxs-lookup"><span data-stu-id="ba168-102">IMetaDataImport::EnumTypeRefs Method</span></span>

<span data-ttu-id="ba168-103">Zählt TypeRef-Token auf, die im aktuellen Metadatenbereich definiert sind.</span><span class="sxs-lookup"><span data-stu-id="ba168-103">Enumerates TypeRef tokens defined in the current metadata scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ba168-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="ba168-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumTypeRefs (  
   [in, out] HCORENUM    *phEnum,
   [out] mdTypeRef       rTypeRefs[],  
   [in]  ULONG           cMax,
   [out] ULONG           *pcTypeRefs  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ba168-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="ba168-105">Parameters</span></span>  

 `phEnum`  
 <span data-ttu-id="ba168-106">[in, out] Ein Zeiger auf den Enumerator.</span><span class="sxs-lookup"><span data-stu-id="ba168-106">[in, out] A pointer to the enumerator.</span></span> <span data-ttu-id="ba168-107">Dieser Wert muss für den ersten-Rückruf dieser Methode NULL sein.</span><span class="sxs-lookup"><span data-stu-id="ba168-107">This must be NULL for the first call of this method.</span></span>  
  
 `rTypeRefs`  
 <span data-ttu-id="ba168-108">vorgenommen Das Array, das zum Speichern der TypeRef-Token verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="ba168-108">[out] The array used to store the TypeRef tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="ba168-109">[in] Die maximale Größe des `rTypeRefs`-Arrays.</span><span class="sxs-lookup"><span data-stu-id="ba168-109">[in] The maximum size of the `rTypeRefs` array.</span></span>  
  
 `pcTypeRefs`  
 <span data-ttu-id="ba168-110">vorgenommen Ein Zeiger auf die Anzahl der TypeRef-Token, die in zurückgegeben werden `rTypeRefs` .</span><span class="sxs-lookup"><span data-stu-id="ba168-110">[out] A pointer to the number of TypeRef tokens returned in `rTypeRefs`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="ba168-111">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="ba168-111">Return Value</span></span>  
  
|<span data-ttu-id="ba168-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="ba168-112">HRESULT</span></span>|<span data-ttu-id="ba168-113">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="ba168-113">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="ba168-114">`EnumTypeRefs` wurde erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="ba168-114">`EnumTypeRefs` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="ba168-115">Es sind keine Token zum Auflisten vorhanden.</span><span class="sxs-lookup"><span data-stu-id="ba168-115">There are no tokens to enumerate.</span></span> <span data-ttu-id="ba168-116">In diesem Fall `pcTypeRefs` ist 0 (null).</span><span class="sxs-lookup"><span data-stu-id="ba168-116">In that case, `pcTypeRefs` is zero.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ba168-117">Hinweise</span><span class="sxs-lookup"><span data-stu-id="ba168-117">Remarks</span></span>  

 <span data-ttu-id="ba168-118">Ein TypeRef-Token stellt einen Verweis auf einen Typ dar.</span><span class="sxs-lookup"><span data-stu-id="ba168-118">A TypeRef token represents a reference to a type.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ba168-119">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="ba168-119">Requirements</span></span>  

 <span data-ttu-id="ba168-120">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ba168-120">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ba168-121">**Header:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="ba168-121">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="ba168-122">**Bibliothek:** Als Ressource in MsCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="ba168-122">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="ba168-123">**.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ba168-123">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ba168-124">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="ba168-124">See also</span></span>

- [<span data-ttu-id="ba168-125">IMetaDataImport-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="ba168-125">IMetaDataImport Interface</span></span>](imetadataimport-interface.md)
- [<span data-ttu-id="ba168-126">IMetaDataImport2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="ba168-126">IMetaDataImport2 Interface</span></span>](imetadataimport2-interface.md)
