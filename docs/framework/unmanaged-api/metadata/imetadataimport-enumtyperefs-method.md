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
ms.openlocfilehash: 0c7e96c50e59902cde4686f908047a86dd2b6a47
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/08/2020
ms.locfileid: "84503743"
---
# <a name="imetadataimportenumtyperefs-method"></a><span data-ttu-id="a95bd-102">IMetaDataImport::EnumTypeRefs-Methode</span><span class="sxs-lookup"><span data-stu-id="a95bd-102">IMetaDataImport::EnumTypeRefs Method</span></span>
<span data-ttu-id="a95bd-103">Zählt TypeRef-Token auf, die im aktuellen Metadatenbereich definiert sind.</span><span class="sxs-lookup"><span data-stu-id="a95bd-103">Enumerates TypeRef tokens defined in the current metadata scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a95bd-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="a95bd-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumTypeRefs (  
   [in, out] HCORENUM    *phEnum,
   [out] mdTypeRef       rTypeRefs[],  
   [in]  ULONG           cMax,
   [out] ULONG           *pcTypeRefs  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a95bd-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="a95bd-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="a95bd-106">[in, out] Ein Zeiger auf den Enumerator.</span><span class="sxs-lookup"><span data-stu-id="a95bd-106">[in, out] A pointer to the enumerator.</span></span> <span data-ttu-id="a95bd-107">Dieser Wert muss für den ersten-Rückruf dieser Methode NULL sein.</span><span class="sxs-lookup"><span data-stu-id="a95bd-107">This must be NULL for the first call of this method.</span></span>  
  
 `rTypeRefs`  
 <span data-ttu-id="a95bd-108">vorgenommen Das Array, das zum Speichern der TypeRef-Token verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="a95bd-108">[out] The array used to store the TypeRef tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="a95bd-109">[in] Die maximale Größe des `rTypeRefs`-Arrays.</span><span class="sxs-lookup"><span data-stu-id="a95bd-109">[in] The maximum size of the `rTypeRefs` array.</span></span>  
  
 `pcTypeRefs`  
 <span data-ttu-id="a95bd-110">vorgenommen Ein Zeiger auf die Anzahl der TypeRef-Token, die in zurückgegeben werden `rTypeRefs` .</span><span class="sxs-lookup"><span data-stu-id="a95bd-110">[out] A pointer to the number of TypeRef tokens returned in `rTypeRefs`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="a95bd-111">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="a95bd-111">Return Value</span></span>  
  
|<span data-ttu-id="a95bd-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="a95bd-112">HRESULT</span></span>|<span data-ttu-id="a95bd-113">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="a95bd-113">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="a95bd-114">`EnumTypeRefs`wurde erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="a95bd-114">`EnumTypeRefs` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="a95bd-115">Es sind keine Token zum Auflisten vorhanden.</span><span class="sxs-lookup"><span data-stu-id="a95bd-115">There are no tokens to enumerate.</span></span> <span data-ttu-id="a95bd-116">In diesem Fall `pcTypeRefs` ist 0 (null).</span><span class="sxs-lookup"><span data-stu-id="a95bd-116">In that case, `pcTypeRefs` is zero.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a95bd-117">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="a95bd-117">Remarks</span></span>  
 <span data-ttu-id="a95bd-118">Ein TypeRef-Token stellt einen Verweis auf einen Typ dar.</span><span class="sxs-lookup"><span data-stu-id="a95bd-118">A TypeRef token represents a reference to a type.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a95bd-119">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="a95bd-119">Requirements</span></span>  
 <span data-ttu-id="a95bd-120">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a95bd-120">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a95bd-121">**Header:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="a95bd-121">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="a95bd-122">**Bibliothek:** Als Ressource in Mscoree. dll enthalten</span><span class="sxs-lookup"><span data-stu-id="a95bd-122">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="a95bd-123">**.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a95bd-123">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a95bd-124">Weitere Informationen:</span><span class="sxs-lookup"><span data-stu-id="a95bd-124">See also</span></span>

- [<span data-ttu-id="a95bd-125">IMetaDataImport-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="a95bd-125">IMetaDataImport Interface</span></span>](imetadataimport-interface.md)
- [<span data-ttu-id="a95bd-126">IMetaDataImport2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="a95bd-126">IMetaDataImport2 Interface</span></span>](imetadataimport2-interface.md)
