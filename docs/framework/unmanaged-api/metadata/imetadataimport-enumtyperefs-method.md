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
ms.openlocfilehash: 778ebf1d4fad0c8703964be88fdc3ff8c033bc28
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/23/2019
ms.locfileid: "74449978"
---
# <a name="imetadataimportenumtyperefs-method"></a><span data-ttu-id="6113d-102">IMetaDataImport::EnumTypeRefs-Methode</span><span class="sxs-lookup"><span data-stu-id="6113d-102">IMetaDataImport::EnumTypeRefs Method</span></span>
<span data-ttu-id="6113d-103">Zählt TypeRef-Token auf, die im aktuellen Metadatenbereich definiert sind.</span><span class="sxs-lookup"><span data-stu-id="6113d-103">Enumerates TypeRef tokens defined in the current metadata scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6113d-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="6113d-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumTypeRefs (  
   [in, out] HCORENUM    *phEnum,   
   [out] mdTypeRef       rTypeRefs[],  
   [in]  ULONG           cMax,   
   [out] ULONG           *pcTypeRefs  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6113d-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="6113d-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="6113d-106">[in, out] Ein Zeiger auf den Enumerator.</span><span class="sxs-lookup"><span data-stu-id="6113d-106">[in, out] A pointer to the enumerator.</span></span> <span data-ttu-id="6113d-107">Dieser Wert muss für den ersten-Rückruf dieser Methode NULL sein.</span><span class="sxs-lookup"><span data-stu-id="6113d-107">This must be NULL for the first call of this method.</span></span>  
  
 `rTypeRefs`  
 <span data-ttu-id="6113d-108">vorgenommen Das Array, das zum Speichern der TypeRef-Token verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="6113d-108">[out] The array used to store the TypeRef tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="6113d-109">[in] Die maximale Größe des `rTypeRefs`-Arrays.</span><span class="sxs-lookup"><span data-stu-id="6113d-109">[in] The maximum size of the `rTypeRefs` array.</span></span>  
  
 `pcTypeRefs`  
 <span data-ttu-id="6113d-110">vorgenommen Ein Zeiger auf die Anzahl der TypeRef-Token, die in `rTypeRefs`zurückgegeben werden.</span><span class="sxs-lookup"><span data-stu-id="6113d-110">[out] A pointer to the number of TypeRef tokens returned in `rTypeRefs`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="6113d-111">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="6113d-111">Return Value</span></span>  
  
|<span data-ttu-id="6113d-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="6113d-112">HRESULT</span></span>|<span data-ttu-id="6113d-113">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="6113d-113">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="6113d-114">`EnumTypeRefs` erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="6113d-114">`EnumTypeRefs` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="6113d-115">Es sind keine Token zum Auflisten vorhanden.</span><span class="sxs-lookup"><span data-stu-id="6113d-115">There are no tokens to enumerate.</span></span> <span data-ttu-id="6113d-116">In diesem Fall `pcTypeRefs` gleich 0 (null) ist.</span><span class="sxs-lookup"><span data-stu-id="6113d-116">In that case, `pcTypeRefs` is zero.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="6113d-117">Hinweise</span><span class="sxs-lookup"><span data-stu-id="6113d-117">Remarks</span></span>  
 <span data-ttu-id="6113d-118">Ein TypeRef-Token stellt einen Verweis auf einen Typ dar.</span><span class="sxs-lookup"><span data-stu-id="6113d-118">A TypeRef token represents a reference to a type.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6113d-119">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="6113d-119">Requirements</span></span>  
 <span data-ttu-id="6113d-120">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6113d-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6113d-121">**Header:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="6113d-121">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="6113d-122">**Bibliothek:** Als Ressource in Mscoree. dll enthalten</span><span class="sxs-lookup"><span data-stu-id="6113d-122">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="6113d-123">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6113d-123">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6113d-124">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="6113d-124">See also</span></span>

- [<span data-ttu-id="6113d-125">IMetaDataImport-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="6113d-125">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="6113d-126">IMetaDataImport2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="6113d-126">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
