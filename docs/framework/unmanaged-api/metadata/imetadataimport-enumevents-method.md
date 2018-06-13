---
title: IMetaDataImport::EnumEvents-Methode
ms.date: 03/30/2017
api_name:
- IMetaDataImport.EnumEvents
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::EnumEvents
helpviewer_keywords:
- IMetaDataImport::EnumEvents method [.NET Framework metadata]
- EnumEvents method [.NET Framework metadata]
ms.assetid: e1efedcb-3dd7-42ae-a399-21c24728aec5
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 608b4a7d147124ede60e9d81f91600dfdaad0a65
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33446495"
---
# <a name="imetadataimportenumevents-method"></a><span data-ttu-id="69f27-102">IMetaDataImport::EnumEvents-Methode</span><span class="sxs-lookup"><span data-stu-id="69f27-102">IMetaDataImport::EnumEvents Method</span></span>
<span data-ttu-id="69f27-103">Zählt Ereignisdefinitionstoken für das angegebene TypeDef-Token auf.</span><span class="sxs-lookup"><span data-stu-id="69f27-103">Enumerates event definition tokens for the specified TypeDef token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="69f27-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="69f27-104">Syntax</span></span>  
  
```  
HRESULT EnumEvents (   
   [in, out] HCORENUM    *phEnum,   
   [in]      mdTypeDef   td,   
   [out]     mdEvent     rEvents[],   
   [in]      ULONG       cMax,  
   [out]    ULONG        *pcEvents  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="69f27-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="69f27-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="69f27-106">[in, out] Ein Zeiger auf den Enumerator.</span><span class="sxs-lookup"><span data-stu-id="69f27-106">[in, out] A pointer to the enumerator.</span></span>  
  
 `td`  
 <span data-ttu-id="69f27-107">[in] Die TypeDef-Token, dessen Ereignisdefinitionen sind, aufgelistet werden sollen.</span><span class="sxs-lookup"><span data-stu-id="69f27-107">[in] The TypeDef token whose event definitions are to be enumerated.</span></span>  
  
 `rEvents`  
 <span data-ttu-id="69f27-108">[out] Das Array der zurückgegebenen Ereignisse.</span><span class="sxs-lookup"><span data-stu-id="69f27-108">[out] The array of returned events.</span></span>  
  
 `cMax`  
 <span data-ttu-id="69f27-109">[in] Die maximale Größe des `rEvents`-Arrays.</span><span class="sxs-lookup"><span data-stu-id="69f27-109">[in] The maximum size of the `rEvents` array.</span></span>  
  
 `pcEvents`  
 <span data-ttu-id="69f27-110">[out] Die tatsächliche Anzahl der Ereignisse, die im zurückgegebenen `rEvents`.</span><span class="sxs-lookup"><span data-stu-id="69f27-110">[out] The actual number of events returned in `rEvents`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="69f27-111">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="69f27-111">Return Value</span></span>  
  
|<span data-ttu-id="69f27-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="69f27-112">HRESULT</span></span>|<span data-ttu-id="69f27-113">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="69f27-113">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="69f27-114">`EnumEvents` wurde erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="69f27-114">`EnumEvents` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="69f27-115">Es sind keine Ereignisse aufgelistet werden.</span><span class="sxs-lookup"><span data-stu-id="69f27-115">There are no events to enumerate.</span></span> <span data-ttu-id="69f27-116">In diesem Fall `pcEvents` 0 (null).</span><span class="sxs-lookup"><span data-stu-id="69f27-116">In that case, `pcEvents` is zero.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="69f27-117">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="69f27-117">Requirements</span></span>  
 <span data-ttu-id="69f27-118">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="69f27-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="69f27-119">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="69f27-119">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="69f27-120">**Bibliothek:** als Ressource in MsCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="69f27-120">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="69f27-121">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="69f27-121">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="69f27-122">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="69f27-122">See Also</span></span>  
 [<span data-ttu-id="69f27-123">IMetaDataImport-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="69f27-123">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)  
 [<span data-ttu-id="69f27-124">IMetaDataImport2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="69f27-124">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
