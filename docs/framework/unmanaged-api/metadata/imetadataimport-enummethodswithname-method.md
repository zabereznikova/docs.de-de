---
title: IMetaDataImport::EnumMethodsWithName-Methode
ms.date: 03/30/2017
api_name:
- IMetaDataImport.EnumMethodsWithName
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::EnumMethodsWithName
helpviewer_keywords:
- IMetaDataImport::EnumMethodsWithName method [.NET Framework metadata]
- EnumMethodsWithName method [.NET Framework metadata]
ms.assetid: a8624913-2e23-46ad-a0c1-bb8eccbbf20f
topic_type:
- apiref
ms.openlocfilehash: 66a09baea1df2e2de418bdce8821672802f1f51f
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/08/2020
ms.locfileid: "84491731"
---
# <a name="imetadataimportenummethodswithname-method"></a><span data-ttu-id="f820f-102">IMetaDataImport::EnumMethodsWithName-Methode</span><span class="sxs-lookup"><span data-stu-id="f820f-102">IMetaDataImport::EnumMethodsWithName Method</span></span>
<span data-ttu-id="f820f-103">Zählt Methoden auf, die den angegebenen Namen aufweisen und durch den Typ definiert sind, auf den durch das angegebene TypeDef-Token verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="f820f-103">Enumerates methods that have the specified name and that are defined by the type referenced by the specified TypeDef token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f820f-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="f820f-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumMethodsWithName (  
   [in, out] HCORENUM    *phEnum,  
   [in]  mdTypeDef       cl,  
   [in]  LPCWSTR         szName,  
   [out] mdMethodDef     rMethods[],  
   [in]  ULONG           cMax,  
   [out] ULONG           *pcTokens  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f820f-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="f820f-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="f820f-106">[in, out] Ein Zeiger auf den Enumerator.</span><span class="sxs-lookup"><span data-stu-id="f820f-106">[in, out] A pointer to the enumerator.</span></span> <span data-ttu-id="f820f-107">Dieser Wert muss für den ersten-Rückruf dieser Methode NULL sein.</span><span class="sxs-lookup"><span data-stu-id="f820f-107">This must be NULL for the first call of this method.</span></span>  
  
 `cl`  
 <span data-ttu-id="f820f-108">in Ein TypeDef-Token, das den Typ darstellt, dessen Methoden aufgelistet werden sollen.</span><span class="sxs-lookup"><span data-stu-id="f820f-108">[in] A TypeDef token representing the type whose methods to enumerate.</span></span>  
  
 `szName`  
 <span data-ttu-id="f820f-109">in Der Name, der den Bereich der-Enumeration einschränkt.</span><span class="sxs-lookup"><span data-stu-id="f820f-109">[in] The name that limits the scope of the enumeration.</span></span>  
  
 `rMethods`  
 <span data-ttu-id="f820f-110">vorgenommen Das Array, das zum Speichern der MethodDef-Token verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="f820f-110">[out] The array used to store the MethodDef tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="f820f-111">[in] Die maximale Größe des `rMethods`-Arrays.</span><span class="sxs-lookup"><span data-stu-id="f820f-111">[in] The maximum size of the `rMethods` array.</span></span>  
  
 `pcTokens`  
 <span data-ttu-id="f820f-112">vorgenommen Die Anzahl der MethodDef-Token, die in zurückgegeben werden `rMethods` .</span><span class="sxs-lookup"><span data-stu-id="f820f-112">[out] The number of MethodDef tokens returned in `rMethods`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f820f-113">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="f820f-113">Remarks</span></span>  
 <span data-ttu-id="f820f-114">Diese Methode listet Felder und Methoden auf, aber keine Eigenschaften oder Ereignisse.</span><span class="sxs-lookup"><span data-stu-id="f820f-114">This method enumerates fields and methods, but not properties or events.</span></span> <span data-ttu-id="f820f-115">Im Gegensatz zu [IMetaDataImport:: EnumMethods](imetadataimport-enummethods-method.md) `EnumMethodsWithName` verwirft alle Methoden Token, die nicht über den angegebenen Namen verfügen.</span><span class="sxs-lookup"><span data-stu-id="f820f-115">Unlike [IMetaDataImport::EnumMethods](imetadataimport-enummethods-method.md), `EnumMethodsWithName` discards all method tokens that do not have the specified name.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="f820f-116">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="f820f-116">Return Value</span></span>  
  
|<span data-ttu-id="f820f-117">HRESULT</span><span class="sxs-lookup"><span data-stu-id="f820f-117">HRESULT</span></span>|<span data-ttu-id="f820f-118">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="f820f-118">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="f820f-119">`EnumMethodsWithName`wurde erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="f820f-119">`EnumMethodsWithName` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="f820f-120">Es sind keine Token zum Auflisten vorhanden.</span><span class="sxs-lookup"><span data-stu-id="f820f-120">There are no tokens to enumerate.</span></span> <span data-ttu-id="f820f-121">In diesem Fall `pcTokens` ist 0 (null).</span><span class="sxs-lookup"><span data-stu-id="f820f-121">In that case, `pcTokens` is zero.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="f820f-122">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="f820f-122">Requirements</span></span>  
 <span data-ttu-id="f820f-123">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f820f-123">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f820f-124">**Header:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="f820f-124">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="f820f-125">**Bibliothek:** Als Ressource in Mscoree. dll enthalten</span><span class="sxs-lookup"><span data-stu-id="f820f-125">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="f820f-126">**.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f820f-126">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f820f-127">Weitere Informationen:</span><span class="sxs-lookup"><span data-stu-id="f820f-127">See also</span></span>

- [<span data-ttu-id="f820f-128">IMetaDataImport-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="f820f-128">IMetaDataImport Interface</span></span>](imetadataimport-interface.md)
- [<span data-ttu-id="f820f-129">IMetaDataImport2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="f820f-129">IMetaDataImport2 Interface</span></span>](imetadataimport2-interface.md)
