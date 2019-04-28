---
title: IMetaDataImport::EnumUserStrings-Methode
ms.date: 03/30/2017
api_name:
- IMetaDataImport.EnumUserStrings
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::EnumUserStrings
helpviewer_keywords:
- IMetaDataImport::EnumUserStrings method [.NET Framework metadata]
- EnumUserStrings method [.NET Framework metadata]
ms.assetid: 2b1f1418-4be8-4cdb-b418-b3abccc527a7
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: f4be12e46851b11a5e6db60c351094a356fa61f2
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61777923"
---
# <a name="imetadataimportenumuserstrings-method"></a><span data-ttu-id="20ad9-102">IMetaDataImport::EnumUserStrings-Methode</span><span class="sxs-lookup"><span data-stu-id="20ad9-102">IMetaDataImport::EnumUserStrings Method</span></span>
<span data-ttu-id="20ad9-103">Zählt String-Token auf, die hartcodierte Zeichenfolgen im aktuellen Metadatenbereich darstellen.</span><span class="sxs-lookup"><span data-stu-id="20ad9-103">Enumerates String tokens representing hard-coded strings in the current metadata scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="20ad9-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="20ad9-104">Syntax</span></span>  
  
```  
HRESULT EnumUserStrings (  
   [in, out]  HCORENUM    *phEnum,  
   [out]  mdString        rStrings[],  
   [in]   ULONG           cMax,  
   [out]  ULONG           *pcStrings  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="20ad9-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="20ad9-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="20ad9-106">[in, out] Ein Zeiger auf den Enumerator.</span><span class="sxs-lookup"><span data-stu-id="20ad9-106">[in, out] A pointer to the enumerator.</span></span> <span data-ttu-id="20ad9-107">Dies muss NULL sein, für den ersten Aufruf dieser Methode.</span><span class="sxs-lookup"><span data-stu-id="20ad9-107">This must be NULL for the first call of this method.</span></span>  
  
 `rStrings`  
 <span data-ttu-id="20ad9-108">[out] Das Array zum Speichern der Zeichenfolge-Token verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="20ad9-108">[out] The array used to store the String tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="20ad9-109">[in] Die maximale Größe des `rStrings`-Arrays.</span><span class="sxs-lookup"><span data-stu-id="20ad9-109">[in] The maximum size of the `rStrings` array.</span></span>  
  
 `pcStrings`  
 <span data-ttu-id="20ad9-110">[out] Die Anzahl der zurückgegebenen im String-Token `rStrings`.</span><span class="sxs-lookup"><span data-stu-id="20ad9-110">[out] The number of String tokens returned in `rStrings`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="20ad9-111">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="20ad9-111">Return Value</span></span>  
  
|<span data-ttu-id="20ad9-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="20ad9-112">HRESULT</span></span>|<span data-ttu-id="20ad9-113">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="20ad9-113">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="20ad9-114">`EnumUserStrings` wurde erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="20ad9-114">`EnumUserStrings` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="20ad9-115">Es gibt keine Token aufgelistet werden.</span><span class="sxs-lookup"><span data-stu-id="20ad9-115">There are no tokens to enumerate.</span></span> <span data-ttu-id="20ad9-116">In diesem Fall `pcStrings` ist 0 (null).</span><span class="sxs-lookup"><span data-stu-id="20ad9-116">In that case, `pcStrings` is zero.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="20ad9-117">Hinweise</span><span class="sxs-lookup"><span data-stu-id="20ad9-117">Remarks</span></span>  
 <span data-ttu-id="20ad9-118">Die Zeichenfolgentoken werden erstellt, durch die [IMetaDataEmit:: DefineUserString](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-defineuserstring-method.md) Methode.</span><span class="sxs-lookup"><span data-stu-id="20ad9-118">The String tokens are created by the [IMetaDataEmit::DefineUserString](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-defineuserstring-method.md) method.</span></span> <span data-ttu-id="20ad9-119">Diese Methode dient, über einen Metadatenbrowser statt über den ein Compiler verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="20ad9-119">This method is designed to be used by a metadata browser rather than by a compiler.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="20ad9-120">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="20ad9-120">Requirements</span></span>  
 <span data-ttu-id="20ad9-121">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="20ad9-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="20ad9-122">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="20ad9-122">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="20ad9-123">**Bibliothek:** Als Ressource in MsCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="20ad9-123">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="20ad9-124">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="20ad9-124">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="20ad9-125">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="20ad9-125">See also</span></span>

- [<span data-ttu-id="20ad9-126">IMetaDataImport-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="20ad9-126">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="20ad9-127">IMetaDataImport2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="20ad9-127">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
