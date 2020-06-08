---
title: IMetaDataImport::EnumTypeSpecs-Methode
ms.date: 03/30/2017
api_name:
- IMetaDataImport.EnumTypeSpecs
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::EnumTypeSpecs
helpviewer_keywords:
- EnumTypeSpecs method [.NET Framework metadata]
- IMetaDataImport::EnumTypeSpecs method [.NET Framework metadata]
ms.assetid: 75331c7b-988b-436c-9eb9-a270d37b4f06
topic_type:
- apiref
ms.openlocfilehash: 94b4c3935c949c0c4008e41244713b6bfa4dba84
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/08/2020
ms.locfileid: "84503717"
---
# <a name="imetadataimportenumtypespecs-method"></a><span data-ttu-id="f14c5-102">IMetaDataImport::EnumTypeSpecs-Methode</span><span class="sxs-lookup"><span data-stu-id="f14c5-102">IMetaDataImport::EnumTypeSpecs Method</span></span>
<span data-ttu-id="f14c5-103">Zählt TypeSpec-Token auf, die im aktuellen Metadatenbereich definiert sind.</span><span class="sxs-lookup"><span data-stu-id="f14c5-103">Enumerates TypeSpec tokens defined in the current metadata scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f14c5-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="f14c5-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumTypeSpecs (  
   [in, out] HCORENUM    *phEnum,  
   [out] mdTypeSpec      rTypeSpecs[],  
   [in]  ULONG           cMax,  
   [out] ULONG           *pcTypeSpecs  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f14c5-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="f14c5-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="f14c5-106">[in, out] Ein Zeiger auf den Enumerator.</span><span class="sxs-lookup"><span data-stu-id="f14c5-106">[in, out] A pointer to the enumerator.</span></span> <span data-ttu-id="f14c5-107">Dieser Wert muss für den ersten-Rückruf dieser Methode NULL sein.</span><span class="sxs-lookup"><span data-stu-id="f14c5-107">This value must be NULL for the first call of this method.</span></span>  
  
 `rTypeSpecs`  
 <span data-ttu-id="f14c5-108">vorgenommen Das Array, das zum Speichern der TypeSpec-Token verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="f14c5-108">[out] The array used to store the TypeSpec tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="f14c5-109">[in] Die maximale Größe des `rTypeSpecs`-Arrays.</span><span class="sxs-lookup"><span data-stu-id="f14c5-109">[in] The maximum size of the `rTypeSpecs` array.</span></span>  
  
 `pcTypeSpecs`  
 <span data-ttu-id="f14c5-110">vorgenommen Die Anzahl der in zurückgegebenen TypeSpec-Token `rTypeSpecs` .</span><span class="sxs-lookup"><span data-stu-id="f14c5-110">[out] The number of TypeSpec tokens returned in `rTypeSpecs`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="f14c5-111">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="f14c5-111">Return Value</span></span>  
  
|<span data-ttu-id="f14c5-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="f14c5-112">HRESULT</span></span>|<span data-ttu-id="f14c5-113">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="f14c5-113">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="f14c5-114">`EnumTypeSpecs`wurde erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="f14c5-114">`EnumTypeSpecs` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="f14c5-115">Es sind keine Token zum Auflisten vorhanden.</span><span class="sxs-lookup"><span data-stu-id="f14c5-115">There are no tokens to enumerate.</span></span> <span data-ttu-id="f14c5-116">In diesem Fall `pcTypeSpecs` ist 0 (null).</span><span class="sxs-lookup"><span data-stu-id="f14c5-116">In that case, `pcTypeSpecs` is zero.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f14c5-117">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="f14c5-117">Remarks</span></span>  
 <span data-ttu-id="f14c5-118">Die TypeSpec-Token werden von der [IMetaDataEmit:: GetTokenFromTypeSpec](imetadataemit-gettokenfromtypespec-method.md) -Methode erstellt.</span><span class="sxs-lookup"><span data-stu-id="f14c5-118">The TypeSpec tokens are created by the [IMetaDataEmit::GetTokenFromTypeSpec](imetadataemit-gettokenfromtypespec-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f14c5-119">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="f14c5-119">Requirements</span></span>  
 <span data-ttu-id="f14c5-120">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f14c5-120">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f14c5-121">**Header:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="f14c5-121">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="f14c5-122">**Bibliothek:** Als Ressource in Mscoree. dll enthalten</span><span class="sxs-lookup"><span data-stu-id="f14c5-122">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="f14c5-123">**.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f14c5-123">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f14c5-124">Weitere Informationen:</span><span class="sxs-lookup"><span data-stu-id="f14c5-124">See also</span></span>

- [<span data-ttu-id="f14c5-125">IMetaDataImport-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="f14c5-125">IMetaDataImport Interface</span></span>](imetadataimport-interface.md)
- [<span data-ttu-id="f14c5-126">IMetaDataImport2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="f14c5-126">IMetaDataImport2 Interface</span></span>](imetadataimport2-interface.md)
