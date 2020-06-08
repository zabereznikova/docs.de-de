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
ms.openlocfilehash: 53b1234a176cade5876d70da0cb4eadc18802c69
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/08/2020
ms.locfileid: "84492303"
---
# <a name="imetadataimportenumevents-method"></a><span data-ttu-id="6a4c9-102">IMetaDataImport::EnumEvents-Methode</span><span class="sxs-lookup"><span data-stu-id="6a4c9-102">IMetaDataImport::EnumEvents Method</span></span>
<span data-ttu-id="6a4c9-103">Zählt Ereignisdefinitionstoken für das angegebene TypeDef-Token auf.</span><span class="sxs-lookup"><span data-stu-id="6a4c9-103">Enumerates event definition tokens for the specified TypeDef token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6a4c9-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="6a4c9-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumEvents (
   [in, out] HCORENUM    *phEnum,
   [in]      mdTypeDef   td,
   [out]     mdEvent     rEvents[],
   [in]      ULONG       cMax,  
   [out]    ULONG        *pcEvents  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6a4c9-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="6a4c9-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="6a4c9-106">[in, out] Ein Zeiger auf den Enumerator.</span><span class="sxs-lookup"><span data-stu-id="6a4c9-106">[in, out] A pointer to the enumerator.</span></span>  
  
 `td`  
 <span data-ttu-id="6a4c9-107">in Das TypeDef-Token, dessen Ereignis Definitionen aufgelistet werden sollen.</span><span class="sxs-lookup"><span data-stu-id="6a4c9-107">[in] The TypeDef token whose event definitions are to be enumerated.</span></span>  
  
 `rEvents`  
 <span data-ttu-id="6a4c9-108">vorgenommen Das Array von zurückgegebenen Ereignissen.</span><span class="sxs-lookup"><span data-stu-id="6a4c9-108">[out] The array of returned events.</span></span>  
  
 `cMax`  
 <span data-ttu-id="6a4c9-109">[in] Die maximale Größe des `rEvents`-Arrays.</span><span class="sxs-lookup"><span data-stu-id="6a4c9-109">[in] The maximum size of the `rEvents` array.</span></span>  
  
 `pcEvents`  
 <span data-ttu-id="6a4c9-110">vorgenommen Die tatsächliche Anzahl der in zurückgegebenen Ereignisse `rEvents` .</span><span class="sxs-lookup"><span data-stu-id="6a4c9-110">[out] The actual number of events returned in `rEvents`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="6a4c9-111">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="6a4c9-111">Return Value</span></span>  
  
|<span data-ttu-id="6a4c9-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="6a4c9-112">HRESULT</span></span>|<span data-ttu-id="6a4c9-113">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="6a4c9-113">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="6a4c9-114">`EnumEvents`wurde erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="6a4c9-114">`EnumEvents` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="6a4c9-115">Es sind keine aufzuzählenden Ereignisse vorhanden.</span><span class="sxs-lookup"><span data-stu-id="6a4c9-115">There are no events to enumerate.</span></span> <span data-ttu-id="6a4c9-116">In diesem Fall `pcEvents` ist 0 (null).</span><span class="sxs-lookup"><span data-stu-id="6a4c9-116">In that case, `pcEvents` is zero.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="6a4c9-117">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="6a4c9-117">Requirements</span></span>  
 <span data-ttu-id="6a4c9-118">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6a4c9-118">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6a4c9-119">**Header:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="6a4c9-119">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="6a4c9-120">**Bibliothek:** Als Ressource in Mscoree. dll enthalten</span><span class="sxs-lookup"><span data-stu-id="6a4c9-120">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="6a4c9-121">**.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6a4c9-121">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6a4c9-122">Weitere Informationen:</span><span class="sxs-lookup"><span data-stu-id="6a4c9-122">See also</span></span>

- [<span data-ttu-id="6a4c9-123">IMetaDataImport-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="6a4c9-123">IMetaDataImport Interface</span></span>](imetadataimport-interface.md)
- [<span data-ttu-id="6a4c9-124">IMetaDataImport2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="6a4c9-124">IMetaDataImport2 Interface</span></span>](imetadataimport2-interface.md)
