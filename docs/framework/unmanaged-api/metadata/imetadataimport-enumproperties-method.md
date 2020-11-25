---
title: IMetaDataImport::EnumProperties-Methode
ms.date: 03/30/2017
api_name:
- IMetaDataImport.EnumProperties
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::EnumProperties
helpviewer_keywords:
- IMetaDataImport::EnumProperties method [.NET Framework metadata]
- EnumProperties method [.NET Framework metadata]
ms.assetid: 60573ad7-8821-4721-a068-3f7a6d25926a
topic_type:
- apiref
ms.openlocfilehash: 24ee37a36e34c74258e1c750ba424640c0496f0a
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95728250"
---
# <a name="imetadataimportenumproperties-method"></a><span data-ttu-id="3d41b-102">IMetaDataImport::EnumProperties-Methode</span><span class="sxs-lookup"><span data-stu-id="3d41b-102">IMetaDataImport::EnumProperties Method</span></span>

<span data-ttu-id="3d41b-103">Zählt PropertyDef-Token auf, die die Eigenschaften des Typs darstellen, auf den vom angegebenen TypeDef-Token verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="3d41b-103">Enumerates PropertyDef tokens representing the properties of the type referenced by the specified TypeDef token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3d41b-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="3d41b-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumProperties (  
   [in, out] HCORENUM    *phEnum,  
   [in]      mdTypeDef   td,  
   [out]     mdProperty  rProperties[],  
   [in]      ULONG       cMax,  
   [out]     ULONG       *pcProperties  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3d41b-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="3d41b-105">Parameters</span></span>  

 `phEnum`  
 <span data-ttu-id="3d41b-106">[in, out] Ein Zeiger auf den Enumerator.</span><span class="sxs-lookup"><span data-stu-id="3d41b-106">[in, out] A pointer to the enumerator.</span></span> <span data-ttu-id="3d41b-107">Dieser Wert muss für den ersten-Rückruf dieser Methode NULL sein.</span><span class="sxs-lookup"><span data-stu-id="3d41b-107">This must be NULL for the first call of this method.</span></span>  
  
 `td`  
 <span data-ttu-id="3d41b-108">in Ein TypeDef-Token, das den Typ mit aufzuzählenden Eigenschaften darstellt.</span><span class="sxs-lookup"><span data-stu-id="3d41b-108">[in] A TypeDef token representing the type with properties to enumerate.</span></span>  
  
 `rProperties`  
 <span data-ttu-id="3d41b-109">vorgenommen Das Array, das zum Speichern der PropertyDef-Token verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="3d41b-109">[out] The array used to store the PropertyDef tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="3d41b-110">[in] Die maximale Größe des `rProperties`-Arrays.</span><span class="sxs-lookup"><span data-stu-id="3d41b-110">[in] The maximum size of the `rProperties` array.</span></span>  
  
 `pcProperties`  
 <span data-ttu-id="3d41b-111">vorgenommen Die Anzahl der in zurückgegebenen PropertyDef-Token `rProperties` .</span><span class="sxs-lookup"><span data-stu-id="3d41b-111">[out] The number of PropertyDef tokens returned in `rProperties`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="3d41b-112">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="3d41b-112">Return Value</span></span>  
  
|<span data-ttu-id="3d41b-113">HRESULT</span><span class="sxs-lookup"><span data-stu-id="3d41b-113">HRESULT</span></span>|<span data-ttu-id="3d41b-114">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="3d41b-114">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="3d41b-115">`EnumProperties` wurde erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="3d41b-115">`EnumProperties` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="3d41b-116">Es sind keine Token zum Auflisten vorhanden.</span><span class="sxs-lookup"><span data-stu-id="3d41b-116">There are no tokens to enumerate.</span></span> <span data-ttu-id="3d41b-117">In diesem Fall `pcProperties` ist 0 (null).</span><span class="sxs-lookup"><span data-stu-id="3d41b-117">In that case, `pcProperties` is zero.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="3d41b-118">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="3d41b-118">Requirements</span></span>  

 <span data-ttu-id="3d41b-119">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3d41b-119">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3d41b-120">**Header:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="3d41b-120">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="3d41b-121">**Bibliothek:** Als Ressource in MsCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="3d41b-121">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="3d41b-122">**.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3d41b-122">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3d41b-123">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="3d41b-123">See also</span></span>

- [<span data-ttu-id="3d41b-124">IMetaDataImport-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="3d41b-124">IMetaDataImport Interface</span></span>](imetadataimport-interface.md)
- [<span data-ttu-id="3d41b-125">IMetaDataImport2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="3d41b-125">IMetaDataImport2 Interface</span></span>](imetadataimport2-interface.md)
