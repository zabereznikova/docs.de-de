---
title: IMetaDataImport::EnumParams-Methode
ms.date: 03/30/2017
api_name:
- IMetaDataImport.EnumParams
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::EnumParams
helpviewer_keywords:
- IMetaDataImport::EnumParams method [.NET Framework metadata]
- EnumParams method [.NET Framework metadata]
ms.assetid: 52118dc9-fe6e-4b39-aa48-c3cc3ea4214d
topic_type:
- apiref
ms.openlocfilehash: b41f9bb05a43ac4c6dd8a89c45ef4826741e5679
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95728263"
---
# <a name="imetadataimportenumparams-method"></a><span data-ttu-id="099ec-102">IMetaDataImport::EnumParams-Methode</span><span class="sxs-lookup"><span data-stu-id="099ec-102">IMetaDataImport::EnumParams Method</span></span>

<span data-ttu-id="099ec-103">Zählt ParamDef-Token auf, die die Parameter der Methode darstellen, auf die vom angegebenen MethodDef-Token verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="099ec-103">Enumerates ParamDef tokens representing the parameters of the method referenced by the specified MethodDef token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="099ec-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="099ec-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumParams (  
   [in, out] HCORENUM    *phEnum,  
   [in]  mdMethodDef     mb,  
   [out] mdParamDef      rParams[],  
   [in]  ULONG           cMax,  
   [out] ULONG          *pcTokens  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="099ec-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="099ec-105">Parameters</span></span>  

 `phEnum`  
 <span data-ttu-id="099ec-106">[in, out] Ein Zeiger auf den Enumerator.</span><span class="sxs-lookup"><span data-stu-id="099ec-106">[in, out] A pointer to the enumerator.</span></span> <span data-ttu-id="099ec-107">Dieser Wert muss für den ersten-Rückruf dieser Methode NULL sein.</span><span class="sxs-lookup"><span data-stu-id="099ec-107">This must be NULL for the first call of this method.</span></span>  
  
 `mb`  
 <span data-ttu-id="099ec-108">in Ein MethodDef-Token, das die Methode mit den aufzuzählenden Parametern darstellt.</span><span class="sxs-lookup"><span data-stu-id="099ec-108">[in] A MethodDef token representing the method with the parameters to enumerate.</span></span>  
  
 `rParams`  
 <span data-ttu-id="099ec-109">vorgenommen Das Array, das zum Speichern der ParamDef-Token verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="099ec-109">[out] The array used to store the ParamDef tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="099ec-110">[in] Die maximale Größe des `rParams`-Arrays.</span><span class="sxs-lookup"><span data-stu-id="099ec-110">[in] The maximum size of the `rParams` array.</span></span>  
  
 `pcTokens`  
 <span data-ttu-id="099ec-111">vorgenommen Die Anzahl der ParamDef-Token, die in zurückgegeben werden `rParams` .</span><span class="sxs-lookup"><span data-stu-id="099ec-111">[out] The number of ParamDef tokens returned in `rParams`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="099ec-112">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="099ec-112">Return Value</span></span>  
  
|<span data-ttu-id="099ec-113">HRESULT</span><span class="sxs-lookup"><span data-stu-id="099ec-113">HRESULT</span></span>|<span data-ttu-id="099ec-114">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="099ec-114">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="099ec-115">`EnumParams` wurde erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="099ec-115">`EnumParams` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="099ec-116">Es sind keine Token zum Auflisten vorhanden.</span><span class="sxs-lookup"><span data-stu-id="099ec-116">There are no tokens to enumerate.</span></span> <span data-ttu-id="099ec-117">In diesem Fall `pcTokens` ist 0 (null).</span><span class="sxs-lookup"><span data-stu-id="099ec-117">In that case, `pcTokens` is zero.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="099ec-118">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="099ec-118">Requirements</span></span>  

 <span data-ttu-id="099ec-119">**Plattform:** Siehe [System Anforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="099ec-119">**Platform:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="099ec-120">**Header:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="099ec-120">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="099ec-121">**Bibliothek:** Wird als Ressource in MsCorEE.dll verwendet.</span><span class="sxs-lookup"><span data-stu-id="099ec-121">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="099ec-122">**.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="099ec-122">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="099ec-123">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="099ec-123">See also</span></span>

- [<span data-ttu-id="099ec-124">IMetaDataImport-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="099ec-124">IMetaDataImport Interface</span></span>](imetadataimport-interface.md)
- [<span data-ttu-id="099ec-125">IMetaDataImport2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="099ec-125">IMetaDataImport2 Interface</span></span>](imetadataimport2-interface.md)
