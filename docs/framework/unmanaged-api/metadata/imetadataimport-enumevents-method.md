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
ms.openlocfilehash: bd50d63b1f7080f510c29f90979b7b36242af1c0
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79177370"
---
# <a name="imetadataimportenumevents-method"></a><span data-ttu-id="79e11-102">IMetaDataImport::EnumEvents-Methode</span><span class="sxs-lookup"><span data-stu-id="79e11-102">IMetaDataImport::EnumEvents Method</span></span>
<span data-ttu-id="79e11-103">Zählt Ereignisdefinitionstoken für das angegebene TypeDef-Token auf.</span><span class="sxs-lookup"><span data-stu-id="79e11-103">Enumerates event definition tokens for the specified TypeDef token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="79e11-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="79e11-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumEvents (
   [in, out] HCORENUM    *phEnum,
   [in]      mdTypeDef   td,
   [out]     mdEvent     rEvents[],
   [in]      ULONG       cMax,  
   [out]    ULONG        *pcEvents  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="79e11-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="79e11-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="79e11-106">[in, out] Ein Zeiger auf den Enumerator.</span><span class="sxs-lookup"><span data-stu-id="79e11-106">[in, out] A pointer to the enumerator.</span></span>  
  
 `td`  
 <span data-ttu-id="79e11-107">[in] Das TypeDef-Token, dessen Ereignisdefinitionen aufgezählt werden sollen.</span><span class="sxs-lookup"><span data-stu-id="79e11-107">[in] The TypeDef token whose event definitions are to be enumerated.</span></span>  
  
 `rEvents`  
 <span data-ttu-id="79e11-108">[out] Das Array der zurückgegebenen Ereignisse.</span><span class="sxs-lookup"><span data-stu-id="79e11-108">[out] The array of returned events.</span></span>  
  
 `cMax`  
 <span data-ttu-id="79e11-109">[in] Die maximale Größe des `rEvents`-Arrays.</span><span class="sxs-lookup"><span data-stu-id="79e11-109">[in] The maximum size of the `rEvents` array.</span></span>  
  
 `pcEvents`  
 <span data-ttu-id="79e11-110">[out] Die tatsächliche Anzahl der `rEvents`in zurückgegebenen Ereignisse.</span><span class="sxs-lookup"><span data-stu-id="79e11-110">[out] The actual number of events returned in `rEvents`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="79e11-111">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="79e11-111">Return Value</span></span>  
  
|<span data-ttu-id="79e11-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="79e11-112">HRESULT</span></span>|<span data-ttu-id="79e11-113">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="79e11-113">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="79e11-114">`EnumEvents`erfolgreich zurückgegeben werden.</span><span class="sxs-lookup"><span data-stu-id="79e11-114">`EnumEvents` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="79e11-115">Es sind keine Ereignisse zum Aufzählen vorhanden.</span><span class="sxs-lookup"><span data-stu-id="79e11-115">There are no events to enumerate.</span></span> <span data-ttu-id="79e11-116">In diesem `pcEvents` Fall ist Null.</span><span class="sxs-lookup"><span data-stu-id="79e11-116">In that case, `pcEvents` is zero.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="79e11-117">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="79e11-117">Requirements</span></span>  
 <span data-ttu-id="79e11-118">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="79e11-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="79e11-119">**Kopfzeile:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="79e11-119">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="79e11-120">**Bibliothek:** Als Ressource in MsCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="79e11-120">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="79e11-121">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="79e11-121">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="79e11-122">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="79e11-122">See also</span></span>

- [<span data-ttu-id="79e11-123">IMetaDataImport-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="79e11-123">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="79e11-124">IMetaDataImport2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="79e11-124">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
