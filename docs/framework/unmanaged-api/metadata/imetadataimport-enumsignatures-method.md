---
title: IMetaDataImport::EnumSignatures-Methode
ms.date: 03/30/2017
api_name:
- IMetaDataImport.EnumSignatures
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::EnumSignatures
helpviewer_keywords:
- EnumSignatures method [.NET Framework metadata]
- IMetaDataImport::EnumSignatures method [.NET Framework metadata]
ms.assetid: d0d65060-6f90-42a2-95cf-6ffb04352996
topic_type:
- apiref
ms.openlocfilehash: 652ebf1be6a58e08da27aaed5b2e84a8f2aee98a
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/08/2020
ms.locfileid: "84503769"
---
# <a name="imetadataimportenumsignatures-method"></a><span data-ttu-id="7cf82-102">IMetaDataImport::EnumSignatures-Methode</span><span class="sxs-lookup"><span data-stu-id="7cf82-102">IMetaDataImport::EnumSignatures Method</span></span>
<span data-ttu-id="7cf82-103">Zählt Signaturtoken auf, die eigenständige Signaturen im aktuellen Bereich darstellen.</span><span class="sxs-lookup"><span data-stu-id="7cf82-103">Enumerates Signature tokens representing stand-alone signatures in the current scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7cf82-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="7cf82-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumSignatures (  
   [in, out] HCORENUM     *phEnum,  
   [out]     mdSignature  rSignatures[],  
   [in]      ULONG        cMax,  
   [out]     ULONG        *pcSignatures  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7cf82-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="7cf82-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="7cf82-106">[in, out] Ein Zeiger auf den Enumerator.</span><span class="sxs-lookup"><span data-stu-id="7cf82-106">[in, out] A pointer to the enumerator.</span></span> <span data-ttu-id="7cf82-107">Dieser Wert muss für den ersten-Rückruf dieser Methode NULL sein.</span><span class="sxs-lookup"><span data-stu-id="7cf82-107">This must be NULL for the first call of this method.</span></span>  
  
 `rSignatures`  
 <span data-ttu-id="7cf82-108">vorgenommen Das Array, das zum Speichern der Signatur Token verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="7cf82-108">[out] The array used to store the Signature tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="7cf82-109">[in] Die maximale Größe des `rSignatures`-Arrays.</span><span class="sxs-lookup"><span data-stu-id="7cf82-109">[in] The maximum size of the `rSignatures` array.</span></span>  
  
 `pcSignatures`  
 <span data-ttu-id="7cf82-110">vorgenommen Die Anzahl der Signatur Token, die in zurückgegeben werden `rSignatures` .</span><span class="sxs-lookup"><span data-stu-id="7cf82-110">[out] The number of Signature tokens returned in `rSignatures`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="7cf82-111">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="7cf82-111">Return Value</span></span>  
  
|<span data-ttu-id="7cf82-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="7cf82-112">HRESULT</span></span>|<span data-ttu-id="7cf82-113">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="7cf82-113">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="7cf82-114">`EnumSignatures`wurde erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="7cf82-114">`EnumSignatures` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="7cf82-115">Es sind keine Token zum Auflisten vorhanden.</span><span class="sxs-lookup"><span data-stu-id="7cf82-115">There are no tokens to enumerate.</span></span> <span data-ttu-id="7cf82-116">In diesem Fall `pcSignatures` ist 0 (null).</span><span class="sxs-lookup"><span data-stu-id="7cf82-116">In that case, `pcSignatures` is zero.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="7cf82-117">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="7cf82-117">Remarks</span></span>  
 <span data-ttu-id="7cf82-118">Die Signatur Token werden von der [IMetaDataEmit:: GetTokenFromSig](imetadataemit-gettokenfromsig-method.md) -Methode erstellt.</span><span class="sxs-lookup"><span data-stu-id="7cf82-118">The Signature tokens are created by the [IMetaDataEmit::GetTokenFromSig](imetadataemit-gettokenfromsig-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7cf82-119">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="7cf82-119">Requirements</span></span>  
 <span data-ttu-id="7cf82-120">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7cf82-120">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7cf82-121">**Header:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="7cf82-121">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="7cf82-122">**Bibliothek:** Als Ressource in Mscoree. dll enthalten</span><span class="sxs-lookup"><span data-stu-id="7cf82-122">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="7cf82-123">**.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7cf82-123">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7cf82-124">Weitere Informationen:</span><span class="sxs-lookup"><span data-stu-id="7cf82-124">See also</span></span>

- [<span data-ttu-id="7cf82-125">IMetaDataImport-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="7cf82-125">IMetaDataImport Interface</span></span>](imetadataimport-interface.md)
- [<span data-ttu-id="7cf82-126">IMetaDataImport2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="7cf82-126">IMetaDataImport2 Interface</span></span>](imetadataimport2-interface.md)
