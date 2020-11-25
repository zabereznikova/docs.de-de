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
ms.openlocfilehash: 5b5345fc4819716dc6c2a00323f94546cfc67f32
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95720931"
---
# <a name="imetadataimportenummethodswithname-method"></a><span data-ttu-id="a37b9-102">IMetaDataImport::EnumMethodsWithName-Methode</span><span class="sxs-lookup"><span data-stu-id="a37b9-102">IMetaDataImport::EnumMethodsWithName Method</span></span>

<span data-ttu-id="a37b9-103">Zählt Methoden auf, die den angegebenen Namen aufweisen und durch den Typ definiert sind, auf den durch das angegebene TypeDef-Token verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="a37b9-103">Enumerates methods that have the specified name and that are defined by the type referenced by the specified TypeDef token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a37b9-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="a37b9-104">Syntax</span></span>  
  
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
  
## <a name="parameters"></a><span data-ttu-id="a37b9-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="a37b9-105">Parameters</span></span>  

 `phEnum`  
 <span data-ttu-id="a37b9-106">[in, out] Ein Zeiger auf den Enumerator.</span><span class="sxs-lookup"><span data-stu-id="a37b9-106">[in, out] A pointer to the enumerator.</span></span> <span data-ttu-id="a37b9-107">Dieser Wert muss für den ersten-Rückruf dieser Methode NULL sein.</span><span class="sxs-lookup"><span data-stu-id="a37b9-107">This must be NULL for the first call of this method.</span></span>  
  
 `cl`  
 <span data-ttu-id="a37b9-108">in Ein TypeDef-Token, das den Typ darstellt, dessen Methoden aufgelistet werden sollen.</span><span class="sxs-lookup"><span data-stu-id="a37b9-108">[in] A TypeDef token representing the type whose methods to enumerate.</span></span>  
  
 `szName`  
 <span data-ttu-id="a37b9-109">in Der Name, der den Bereich der-Enumeration einschränkt.</span><span class="sxs-lookup"><span data-stu-id="a37b9-109">[in] The name that limits the scope of the enumeration.</span></span>  
  
 `rMethods`  
 <span data-ttu-id="a37b9-110">vorgenommen Das Array, das zum Speichern der MethodDef-Token verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="a37b9-110">[out] The array used to store the MethodDef tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="a37b9-111">[in] Die maximale Größe des `rMethods`-Arrays.</span><span class="sxs-lookup"><span data-stu-id="a37b9-111">[in] The maximum size of the `rMethods` array.</span></span>  
  
 `pcTokens`  
 <span data-ttu-id="a37b9-112">vorgenommen Die Anzahl der MethodDef-Token, die in zurückgegeben werden `rMethods` .</span><span class="sxs-lookup"><span data-stu-id="a37b9-112">[out] The number of MethodDef tokens returned in `rMethods`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a37b9-113">Hinweise</span><span class="sxs-lookup"><span data-stu-id="a37b9-113">Remarks</span></span>  

 <span data-ttu-id="a37b9-114">Diese Methode listet Felder und Methoden auf, aber keine Eigenschaften oder Ereignisse.</span><span class="sxs-lookup"><span data-stu-id="a37b9-114">This method enumerates fields and methods, but not properties or events.</span></span> <span data-ttu-id="a37b9-115">Im Gegensatz zu [IMetaDataImport:: EnumMethods](imetadataimport-enummethods-method.md) `EnumMethodsWithName` verwirft alle Methoden Token, die nicht über den angegebenen Namen verfügen.</span><span class="sxs-lookup"><span data-stu-id="a37b9-115">Unlike [IMetaDataImport::EnumMethods](imetadataimport-enummethods-method.md), `EnumMethodsWithName` discards all method tokens that do not have the specified name.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="a37b9-116">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="a37b9-116">Return Value</span></span>  
  
|<span data-ttu-id="a37b9-117">HRESULT</span><span class="sxs-lookup"><span data-stu-id="a37b9-117">HRESULT</span></span>|<span data-ttu-id="a37b9-118">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="a37b9-118">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="a37b9-119">`EnumMethodsWithName` wurde erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="a37b9-119">`EnumMethodsWithName` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="a37b9-120">Es sind keine Token zum Auflisten vorhanden.</span><span class="sxs-lookup"><span data-stu-id="a37b9-120">There are no tokens to enumerate.</span></span> <span data-ttu-id="a37b9-121">In diesem Fall `pcTokens` ist 0 (null).</span><span class="sxs-lookup"><span data-stu-id="a37b9-121">In that case, `pcTokens` is zero.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="a37b9-122">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="a37b9-122">Requirements</span></span>  

 <span data-ttu-id="a37b9-123">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a37b9-123">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a37b9-124">**Header:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="a37b9-124">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="a37b9-125">**Bibliothek:** Als Ressource in MsCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="a37b9-125">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="a37b9-126">**.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a37b9-126">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a37b9-127">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="a37b9-127">See also</span></span>

- [<span data-ttu-id="a37b9-128">IMetaDataImport-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="a37b9-128">IMetaDataImport Interface</span></span>](imetadataimport-interface.md)
- [<span data-ttu-id="a37b9-129">IMetaDataImport2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="a37b9-129">IMetaDataImport2 Interface</span></span>](imetadataimport2-interface.md)
