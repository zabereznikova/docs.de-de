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
ms.openlocfilehash: b2ba46c025c2d031f0526c6a9da5f6ab07023741
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59208448"
---
# <a name="imetadataimportenumevents-method"></a><span data-ttu-id="fbd18-102">IMetaDataImport::EnumEvents-Methode</span><span class="sxs-lookup"><span data-stu-id="fbd18-102">IMetaDataImport::EnumEvents Method</span></span>
<span data-ttu-id="fbd18-103">Zählt Ereignisdefinitionstoken für das angegebene TypeDef-Token auf.</span><span class="sxs-lookup"><span data-stu-id="fbd18-103">Enumerates event definition tokens for the specified TypeDef token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fbd18-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="fbd18-104">Syntax</span></span>  
  
```  
HRESULT EnumEvents (   
   [in, out] HCORENUM    *phEnum,   
   [in]      mdTypeDef   td,   
   [out]     mdEvent     rEvents[],   
   [in]      ULONG       cMax,  
   [out]    ULONG        *pcEvents  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="fbd18-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="fbd18-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="fbd18-106">[in, out] Ein Zeiger auf den Enumerator.</span><span class="sxs-lookup"><span data-stu-id="fbd18-106">[in, out] A pointer to the enumerator.</span></span>  
  
 `td`  
 <span data-ttu-id="fbd18-107">[in] Die TypeDef-Token, dessen Ereignisdefinitionen sind, aufgelistet werden sollen.</span><span class="sxs-lookup"><span data-stu-id="fbd18-107">[in] The TypeDef token whose event definitions are to be enumerated.</span></span>  
  
 `rEvents`  
 <span data-ttu-id="fbd18-108">[out] Das Array der zurückgegebenen Ereignisse an.</span><span class="sxs-lookup"><span data-stu-id="fbd18-108">[out] The array of returned events.</span></span>  
  
 `cMax`  
 <span data-ttu-id="fbd18-109">[in] Die maximale Größe des `rEvents`-Arrays.</span><span class="sxs-lookup"><span data-stu-id="fbd18-109">[in] The maximum size of the `rEvents` array.</span></span>  
  
 `pcEvents`  
 <span data-ttu-id="fbd18-110">[out] Die tatsächliche Anzahl der Ereignisse, die in zurückgegebenen `rEvents`.</span><span class="sxs-lookup"><span data-stu-id="fbd18-110">[out] The actual number of events returned in `rEvents`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="fbd18-111">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="fbd18-111">Return Value</span></span>  
  
|<span data-ttu-id="fbd18-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="fbd18-112">HRESULT</span></span>|<span data-ttu-id="fbd18-113">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="fbd18-113">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|`EnumEvents` <span data-ttu-id="fbd18-114">wurde erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="fbd18-114">returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="fbd18-115">Es gibt keine Ereignisse aufgelistet werden.</span><span class="sxs-lookup"><span data-stu-id="fbd18-115">There are no events to enumerate.</span></span> <span data-ttu-id="fbd18-116">In diesem Fall `pcEvents` ist 0 (null).</span><span class="sxs-lookup"><span data-stu-id="fbd18-116">In that case, `pcEvents` is zero.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="fbd18-117">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="fbd18-117">Requirements</span></span>  
 <span data-ttu-id="fbd18-118">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="fbd18-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fbd18-119">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="fbd18-119">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="fbd18-120">**Bibliothek:** Als Ressource in MsCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="fbd18-120">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 **<span data-ttu-id="fbd18-121">.NET Framework-Versionen:</span><span class="sxs-lookup"><span data-stu-id="fbd18-121">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="fbd18-122">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="fbd18-122">See also</span></span>

- [<span data-ttu-id="fbd18-123">IMetaDataImport-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="fbd18-123">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="fbd18-124">IMetaDataImport2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="fbd18-124">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
