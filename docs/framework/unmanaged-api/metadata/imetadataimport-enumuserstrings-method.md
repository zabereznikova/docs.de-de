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
ms.openlocfilehash: 1c9f15881d3515f24a63f29e9337a7a356937f2d
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/23/2019
ms.locfileid: "74449947"
---
# <a name="imetadataimportenumuserstrings-method"></a><span data-ttu-id="99530-102">IMetaDataImport::EnumUserStrings-Methode</span><span class="sxs-lookup"><span data-stu-id="99530-102">IMetaDataImport::EnumUserStrings Method</span></span>
<span data-ttu-id="99530-103">Zählt String-Token auf, die hartcodierte Zeichenfolgen im aktuellen Metadatenbereich darstellen.</span><span class="sxs-lookup"><span data-stu-id="99530-103">Enumerates String tokens representing hard-coded strings in the current metadata scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="99530-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="99530-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumUserStrings (  
   [in, out]  HCORENUM    *phEnum,  
   [out]  mdString        rStrings[],  
   [in]   ULONG           cMax,  
   [out]  ULONG           *pcStrings  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="99530-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="99530-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="99530-106">[in, out] Ein Zeiger auf den Enumerator.</span><span class="sxs-lookup"><span data-stu-id="99530-106">[in, out] A pointer to the enumerator.</span></span> <span data-ttu-id="99530-107">Dieser Wert muss für den ersten-Rückruf dieser Methode NULL sein.</span><span class="sxs-lookup"><span data-stu-id="99530-107">This must be NULL for the first call of this method.</span></span>  
  
 `rStrings`  
 <span data-ttu-id="99530-108">vorgenommen Das Array, das zum Speichern der Zeichen folgen Token verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="99530-108">[out] The array used to store the String tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="99530-109">[in] Die maximale Größe des `rStrings`-Arrays.</span><span class="sxs-lookup"><span data-stu-id="99530-109">[in] The maximum size of the `rStrings` array.</span></span>  
  
 `pcStrings`  
 <span data-ttu-id="99530-110">vorgenommen Die Anzahl der Zeichen folgen Token, die in `rStrings`zurückgegeben werden.</span><span class="sxs-lookup"><span data-stu-id="99530-110">[out] The number of String tokens returned in `rStrings`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="99530-111">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="99530-111">Return Value</span></span>  
  
|<span data-ttu-id="99530-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="99530-112">HRESULT</span></span>|<span data-ttu-id="99530-113">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="99530-113">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="99530-114">`EnumUserStrings` erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="99530-114">`EnumUserStrings` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="99530-115">Es sind keine Token zum Auflisten vorhanden.</span><span class="sxs-lookup"><span data-stu-id="99530-115">There are no tokens to enumerate.</span></span> <span data-ttu-id="99530-116">In diesem Fall `pcStrings` gleich 0 (null) ist.</span><span class="sxs-lookup"><span data-stu-id="99530-116">In that case, `pcStrings` is zero.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="99530-117">Hinweise</span><span class="sxs-lookup"><span data-stu-id="99530-117">Remarks</span></span>  
 <span data-ttu-id="99530-118">Die Zeichen folgen Token werden von der [IMetaDataEmit::D efineuserstring](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-defineuserstring-method.md) -Methode erstellt.</span><span class="sxs-lookup"><span data-stu-id="99530-118">The String tokens are created by the [IMetaDataEmit::DefineUserString](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-defineuserstring-method.md) method.</span></span> <span data-ttu-id="99530-119">Diese Methode ist so konzipiert, dass Sie von einem Metadatenbrowser anstelle eines Compilers verwendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="99530-119">This method is designed to be used by a metadata browser rather than by a compiler.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="99530-120">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="99530-120">Requirements</span></span>  
 <span data-ttu-id="99530-121">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="99530-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="99530-122">**Header:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="99530-122">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="99530-123">**Bibliothek:** Als Ressource in Mscoree. dll enthalten</span><span class="sxs-lookup"><span data-stu-id="99530-123">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="99530-124">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="99530-124">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="99530-125">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="99530-125">See also</span></span>

- [<span data-ttu-id="99530-126">IMetaDataImport-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="99530-126">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="99530-127">IMetaDataImport2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="99530-127">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
