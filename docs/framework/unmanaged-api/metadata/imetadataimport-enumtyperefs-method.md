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
ms.openlocfilehash: e5d4ddd43b27d733a63c2e0dc5e92ffd2ba94a7f
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79175433"
---
# <a name="imetadataimportenumtyperefs-method"></a><span data-ttu-id="801b9-102">IMetaDataImport::EnumTypeRefs-Methode</span><span class="sxs-lookup"><span data-stu-id="801b9-102">IMetaDataImport::EnumTypeRefs Method</span></span>
<span data-ttu-id="801b9-103">Zählt TypeRef-Token auf, die im aktuellen Metadatenbereich definiert sind.</span><span class="sxs-lookup"><span data-stu-id="801b9-103">Enumerates TypeRef tokens defined in the current metadata scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="801b9-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="801b9-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumTypeRefs (  
   [in, out] HCORENUM    *phEnum,
   [out] mdTypeRef       rTypeRefs[],  
   [in]  ULONG           cMax,
   [out] ULONG           *pcTypeRefs  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="801b9-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="801b9-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="801b9-106">[in, out] Ein Zeiger auf den Enumerator.</span><span class="sxs-lookup"><span data-stu-id="801b9-106">[in, out] A pointer to the enumerator.</span></span> <span data-ttu-id="801b9-107">Dies muss NULL für den ersten Aufruf dieser Methode sein.</span><span class="sxs-lookup"><span data-stu-id="801b9-107">This must be NULL for the first call of this method.</span></span>  
  
 `rTypeRefs`  
 <span data-ttu-id="801b9-108">[out] Das Array, das zum Speichern der TypeRef-Token verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="801b9-108">[out] The array used to store the TypeRef tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="801b9-109">[in] Die maximale Größe des `rTypeRefs`-Arrays.</span><span class="sxs-lookup"><span data-stu-id="801b9-109">[in] The maximum size of the `rTypeRefs` array.</span></span>  
  
 `pcTypeRefs`  
 <span data-ttu-id="801b9-110">[out] Ein Zeiger auf die Anzahl der TypeRef-Token, die in `rTypeRefs`zurückgegeben werden.</span><span class="sxs-lookup"><span data-stu-id="801b9-110">[out] A pointer to the number of TypeRef tokens returned in `rTypeRefs`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="801b9-111">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="801b9-111">Return Value</span></span>  
  
|<span data-ttu-id="801b9-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="801b9-112">HRESULT</span></span>|<span data-ttu-id="801b9-113">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="801b9-113">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="801b9-114">`EnumTypeRefs`erfolgreich zurückgegeben werden.</span><span class="sxs-lookup"><span data-stu-id="801b9-114">`EnumTypeRefs` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="801b9-115">Es sind keine Token zum Aufzählen vorhanden.</span><span class="sxs-lookup"><span data-stu-id="801b9-115">There are no tokens to enumerate.</span></span> <span data-ttu-id="801b9-116">In diesem `pcTypeRefs` Fall ist Null.</span><span class="sxs-lookup"><span data-stu-id="801b9-116">In that case, `pcTypeRefs` is zero.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="801b9-117">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="801b9-117">Remarks</span></span>  
 <span data-ttu-id="801b9-118">Ein TypeRef-Token stellt einen Verweis auf einen Typ dar.</span><span class="sxs-lookup"><span data-stu-id="801b9-118">A TypeRef token represents a reference to a type.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="801b9-119">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="801b9-119">Requirements</span></span>  
 <span data-ttu-id="801b9-120">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="801b9-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="801b9-121">**Kopfzeile:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="801b9-121">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="801b9-122">**Bibliothek:** Als Ressource in MsCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="801b9-122">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="801b9-123">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="801b9-123">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="801b9-124">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="801b9-124">See also</span></span>

- [<span data-ttu-id="801b9-125">IMetaDataImport-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="801b9-125">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="801b9-126">IMetaDataImport2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="801b9-126">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
