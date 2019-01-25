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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 61285b3de76f556b498c9815508275989eb96807
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54630982"
---
# <a name="imetadataimportenumsignatures-method"></a><span data-ttu-id="db32d-102">IMetaDataImport::EnumSignatures-Methode</span><span class="sxs-lookup"><span data-stu-id="db32d-102">IMetaDataImport::EnumSignatures Method</span></span>
<span data-ttu-id="db32d-103">Zählt Signaturtoken auf, die eigenständige Signaturen im aktuellen Bereich darstellen.</span><span class="sxs-lookup"><span data-stu-id="db32d-103">Enumerates Signature tokens representing stand-alone signatures in the current scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="db32d-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="db32d-104">Syntax</span></span>  
  
```  
HRESULT EnumSignatures (  
   [in, out] HCORENUM     *phEnum,  
   [out]     mdSignature  rSignatures[],  
   [in]      ULONG        cMax,  
   [out]     ULONG        *pcSignatures  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="db32d-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="db32d-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="db32d-106">[in, out] Ein Zeiger auf den Enumerator.</span><span class="sxs-lookup"><span data-stu-id="db32d-106">[in, out] A pointer to the enumerator.</span></span> <span data-ttu-id="db32d-107">Dies muss NULL sein, für den ersten Aufruf dieser Methode.</span><span class="sxs-lookup"><span data-stu-id="db32d-107">This must be NULL for the first call of this method.</span></span>  
  
 `rSignatures`  
 <span data-ttu-id="db32d-108">[out] Das Array zum Speichern der Signature-Token verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="db32d-108">[out] The array used to store the Signature tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="db32d-109">[in] Die maximale Größe des `rSignatures`-Arrays.</span><span class="sxs-lookup"><span data-stu-id="db32d-109">[in] The maximum size of the `rSignatures` array.</span></span>  
  
 `pcSignatures`  
 <span data-ttu-id="db32d-110">[out] Die Anzahl der SAS-Token, die in zurückgegebenen `rSignatures`.</span><span class="sxs-lookup"><span data-stu-id="db32d-110">[out] The number of Signature tokens returned in `rSignatures`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="db32d-111">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="db32d-111">Return Value</span></span>  
  
|<span data-ttu-id="db32d-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="db32d-112">HRESULT</span></span>|<span data-ttu-id="db32d-113">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="db32d-113">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="db32d-114">`EnumSignatures` wurde erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="db32d-114">`EnumSignatures` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="db32d-115">Es gibt keine Token aufgelistet werden.</span><span class="sxs-lookup"><span data-stu-id="db32d-115">There are no tokens to enumerate.</span></span> <span data-ttu-id="db32d-116">In diesem Fall `pcSignatures` ist 0 (null).</span><span class="sxs-lookup"><span data-stu-id="db32d-116">In that case, `pcSignatures` is zero.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="db32d-117">Hinweise</span><span class="sxs-lookup"><span data-stu-id="db32d-117">Remarks</span></span>  
 <span data-ttu-id="db32d-118">Die Signatur-Tokens werden erstellt, durch die [IMetaDataEmit:: GetTokenFromSig](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-gettokenfromsig-method.md) Methode.</span><span class="sxs-lookup"><span data-stu-id="db32d-118">The Signature tokens are created by the [IMetaDataEmit::GetTokenFromSig](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-gettokenfromsig-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="db32d-119">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="db32d-119">Requirements</span></span>  
 <span data-ttu-id="db32d-120">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="db32d-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="db32d-121">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="db32d-121">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="db32d-122">**Bibliothek:** Als Ressource in MsCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="db32d-122">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="db32d-123">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="db32d-123">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="db32d-124">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="db32d-124">See also</span></span>
- [<span data-ttu-id="db32d-125">IMetaDataImport-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="db32d-125">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="db32d-126">IMetaDataImport2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="db32d-126">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
