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
ms.openlocfilehash: 66186d25e8fee0d6b25c0a2069d46ff9a104c625
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/23/2019
ms.locfileid: "74450031"
---
# <a name="imetadataimportenummodulerefs-method"></a><span data-ttu-id="45e17-102">IMetaDataImport::EnumModuleRefs-Methode</span><span class="sxs-lookup"><span data-stu-id="45e17-102">IMetaDataImport::EnumModuleRefs Method</span></span>
<span data-ttu-id="45e17-103">Zählt ModuleRef-Token auf, die importierte Module darstellen.</span><span class="sxs-lookup"><span data-stu-id="45e17-103">Enumerates ModuleRef tokens that represent imported modules.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="45e17-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="45e17-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumModuleRefs (  
   [in, out] HCORENUM     *phEnum,  
   [out]     mdModuleRef  rModuleRefs[],  
   [in]      ULONG        cMax,  
   [out]     ULONG        *pcModuleRefs  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="45e17-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="45e17-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="45e17-106">[in, out] Ein Zeiger auf den Enumerator.</span><span class="sxs-lookup"><span data-stu-id="45e17-106">[in, out] A pointer to the enumerator.</span></span> <span data-ttu-id="45e17-107">Dieser Wert muss für den ersten-Rückruf dieser Methode NULL sein.</span><span class="sxs-lookup"><span data-stu-id="45e17-107">This must be NULL for the first call of this method.</span></span>  
  
 `rModuleRefs`  
 <span data-ttu-id="45e17-108">vorgenommen Das Array, das zum Speichern der ModuleRef-Token verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="45e17-108">[out] The array used to store the ModuleRef tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="45e17-109">[in] Die maximale Größe des `rModuleRefs`-Arrays.</span><span class="sxs-lookup"><span data-stu-id="45e17-109">[in] The maximum size of the `rModuleRefs` array.</span></span>  
  
 `pcModuleRefs`  
 <span data-ttu-id="45e17-110">vorgenommen Die Anzahl der in `rModuleRefs`zurückgegebenen ModuleRef-Token.</span><span class="sxs-lookup"><span data-stu-id="45e17-110">[out] The number of ModuleRef tokens returned in `rModuleRefs`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="45e17-111">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="45e17-111">Return Value</span></span>  
  
|<span data-ttu-id="45e17-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="45e17-112">HRESULT</span></span>|<span data-ttu-id="45e17-113">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="45e17-113">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="45e17-114">`EnumModuleRefs` erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="45e17-114">`EnumModuleRefs` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="45e17-115">Es sind keine Token zum Auflisten vorhanden.</span><span class="sxs-lookup"><span data-stu-id="45e17-115">There are no tokens to enumerate.</span></span> <span data-ttu-id="45e17-116">In diesem Fall `pcModuleRefs` gleich 0 (null) ist.</span><span class="sxs-lookup"><span data-stu-id="45e17-116">In that case, `pcModuleRefs` is zero.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="45e17-117">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="45e17-117">Requirements</span></span>  
 <span data-ttu-id="45e17-118">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="45e17-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="45e17-119">**Header:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="45e17-119">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="45e17-120">**Bibliothek:** Als Ressource in Mscoree. dll enthalten</span><span class="sxs-lookup"><span data-stu-id="45e17-120">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="45e17-121">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="45e17-121">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="45e17-122">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="45e17-122">See also</span></span>

- [<span data-ttu-id="45e17-123">IMetaDataImport-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="45e17-123">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="45e17-124">IMetaDataImport2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="45e17-124">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
