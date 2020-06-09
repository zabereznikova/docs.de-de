---
title: IMetaDataImport::EnumModuleRefs-Methode
ms.date: 03/30/2017
api_name:
- IMetaDataImport.EnumModuleRefs
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::EnumModuleRefs
helpviewer_keywords:
- EnumModuleRefs method [.NET Framework metadata]
- IMetaDataImport::EnumModuleRefs method [.NET Framework metadata]
ms.assetid: 53441f3a-68d2-477c-906e-37c55dfcfb4d
topic_type:
- apiref
ms.openlocfilehash: fe7350e6d8e400ae37b5b8b7854a56f3c5c53ea7
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/08/2020
ms.locfileid: "84491748"
---
# <a name="imetadataimportenummodulerefs-method"></a><span data-ttu-id="c48c6-102">IMetaDataImport::EnumModuleRefs-Methode</span><span class="sxs-lookup"><span data-stu-id="c48c6-102">IMetaDataImport::EnumModuleRefs Method</span></span>
<span data-ttu-id="c48c6-103">Zählt ModuleRef-Token auf, die importierte Module darstellen.</span><span class="sxs-lookup"><span data-stu-id="c48c6-103">Enumerates ModuleRef tokens that represent imported modules.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c48c6-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="c48c6-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumModuleRefs (  
   [in, out] HCORENUM     *phEnum,  
   [out]     mdModuleRef  rModuleRefs[],  
   [in]      ULONG        cMax,  
   [out]     ULONG        *pcModuleRefs  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c48c6-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="c48c6-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="c48c6-106">[in, out] Ein Zeiger auf den Enumerator.</span><span class="sxs-lookup"><span data-stu-id="c48c6-106">[in, out] A pointer to the enumerator.</span></span> <span data-ttu-id="c48c6-107">Dieser Wert muss für den ersten-Rückruf dieser Methode NULL sein.</span><span class="sxs-lookup"><span data-stu-id="c48c6-107">This must be NULL for the first call of this method.</span></span>  
  
 `rModuleRefs`  
 <span data-ttu-id="c48c6-108">vorgenommen Das Array, das zum Speichern der ModuleRef-Token verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="c48c6-108">[out] The array used to store the ModuleRef tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="c48c6-109">[in] Die maximale Größe des `rModuleRefs`-Arrays.</span><span class="sxs-lookup"><span data-stu-id="c48c6-109">[in] The maximum size of the `rModuleRefs` array.</span></span>  
  
 `pcModuleRefs`  
 <span data-ttu-id="c48c6-110">vorgenommen Die Anzahl der in zurückgegebenen ModuleRef-Token `rModuleRefs` .</span><span class="sxs-lookup"><span data-stu-id="c48c6-110">[out] The number of ModuleRef tokens returned in `rModuleRefs`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="c48c6-111">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="c48c6-111">Return Value</span></span>  
  
|<span data-ttu-id="c48c6-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="c48c6-112">HRESULT</span></span>|<span data-ttu-id="c48c6-113">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="c48c6-113">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="c48c6-114">`EnumModuleRefs`wurde erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="c48c6-114">`EnumModuleRefs` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="c48c6-115">Es sind keine Token zum Auflisten vorhanden.</span><span class="sxs-lookup"><span data-stu-id="c48c6-115">There are no tokens to enumerate.</span></span> <span data-ttu-id="c48c6-116">In diesem Fall `pcModuleRefs` ist 0 (null).</span><span class="sxs-lookup"><span data-stu-id="c48c6-116">In that case, `pcModuleRefs` is zero.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="c48c6-117">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="c48c6-117">Requirements</span></span>  
 <span data-ttu-id="c48c6-118">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c48c6-118">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c48c6-119">**Header:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="c48c6-119">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="c48c6-120">**Bibliothek:** Als Ressource in Mscoree. dll enthalten</span><span class="sxs-lookup"><span data-stu-id="c48c6-120">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="c48c6-121">**.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c48c6-121">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c48c6-122">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="c48c6-122">See also</span></span>

- [<span data-ttu-id="c48c6-123">IMetaDataImport-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="c48c6-123">IMetaDataImport Interface</span></span>](imetadataimport-interface.md)
- [<span data-ttu-id="c48c6-124">IMetaDataImport2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="c48c6-124">IMetaDataImport2 Interface</span></span>](imetadataimport2-interface.md)
