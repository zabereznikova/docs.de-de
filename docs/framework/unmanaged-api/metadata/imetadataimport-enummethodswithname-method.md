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
ms.openlocfilehash: b0817288040550b5f4c3c4ec063f6a7fdb004137
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/23/2019
ms.locfileid: "74450058"
---
# <a name="imetadataimportenummethodswithname-method"></a><span data-ttu-id="30309-102">IMetaDataImport::EnumMethodsWithName-Methode</span><span class="sxs-lookup"><span data-stu-id="30309-102">IMetaDataImport::EnumMethodsWithName Method</span></span>
<span data-ttu-id="30309-103">Zählt Methoden auf, die den angegebenen Namen aufweisen und durch den Typ definiert sind, auf den durch das angegebene TypeDef-Token verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="30309-103">Enumerates methods that have the specified name and that are defined by the type referenced by the specified TypeDef token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="30309-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="30309-104">Syntax</span></span>  
  
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
  
## <a name="parameters"></a><span data-ttu-id="30309-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="30309-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="30309-106">[in, out] Ein Zeiger auf den Enumerator.</span><span class="sxs-lookup"><span data-stu-id="30309-106">[in, out] A pointer to the enumerator.</span></span> <span data-ttu-id="30309-107">Dieser Wert muss für den ersten-Rückruf dieser Methode NULL sein.</span><span class="sxs-lookup"><span data-stu-id="30309-107">This must be NULL for the first call of this method.</span></span>  
  
 `cl`  
 <span data-ttu-id="30309-108">in Ein TypeDef-Token, das den Typ darstellt, dessen Methoden aufgelistet werden sollen.</span><span class="sxs-lookup"><span data-stu-id="30309-108">[in] A TypeDef token representing the type whose methods to enumerate.</span></span>  
  
 `szName`  
 <span data-ttu-id="30309-109">in Der Name, der den Bereich der-Enumeration einschränkt.</span><span class="sxs-lookup"><span data-stu-id="30309-109">[in] The name that limits the scope of the enumeration.</span></span>  
  
 `rMethods`  
 <span data-ttu-id="30309-110">vorgenommen Das Array, das zum Speichern der MethodDef-Token verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="30309-110">[out] The array used to store the MethodDef tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="30309-111">[in] Die maximale Größe des `rMethods`-Arrays.</span><span class="sxs-lookup"><span data-stu-id="30309-111">[in] The maximum size of the `rMethods` array.</span></span>  
  
 `pcTokens`  
 <span data-ttu-id="30309-112">vorgenommen Die Anzahl der MethodDef-Token, die in `rMethods`zurückgegeben werden.</span><span class="sxs-lookup"><span data-stu-id="30309-112">[out] The number of MethodDef tokens returned in `rMethods`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="30309-113">Hinweise</span><span class="sxs-lookup"><span data-stu-id="30309-113">Remarks</span></span>  
 <span data-ttu-id="30309-114">Diese Methode listet Felder und Methoden auf, aber keine Eigenschaften oder Ereignisse.</span><span class="sxs-lookup"><span data-stu-id="30309-114">This method enumerates fields and methods, but not properties or events.</span></span> <span data-ttu-id="30309-115">Im Gegensatz zu [IMetaDataImport:: EnumMethods](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-enummethods-method.md)verwirft `EnumMethodsWithName` alle Methoden Token, die nicht über den angegebenen Namen verfügen.</span><span class="sxs-lookup"><span data-stu-id="30309-115">Unlike [IMetaDataImport::EnumMethods](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-enummethods-method.md), `EnumMethodsWithName` discards all method tokens that do not have the specified name.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="30309-116">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="30309-116">Return Value</span></span>  
  
|<span data-ttu-id="30309-117">HRESULT</span><span class="sxs-lookup"><span data-stu-id="30309-117">HRESULT</span></span>|<span data-ttu-id="30309-118">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="30309-118">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="30309-119">`EnumMethodsWithName` erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="30309-119">`EnumMethodsWithName` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="30309-120">Es sind keine Token zum Auflisten vorhanden.</span><span class="sxs-lookup"><span data-stu-id="30309-120">There are no tokens to enumerate.</span></span> <span data-ttu-id="30309-121">In diesem Fall `pcTokens` gleich 0 (null) ist.</span><span class="sxs-lookup"><span data-stu-id="30309-121">In that case, `pcTokens` is zero.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="30309-122">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="30309-122">Requirements</span></span>  
 <span data-ttu-id="30309-123">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="30309-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="30309-124">**Header:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="30309-124">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="30309-125">**Bibliothek:** Als Ressource in Mscoree. dll enthalten</span><span class="sxs-lookup"><span data-stu-id="30309-125">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="30309-126">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="30309-126">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="30309-127">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="30309-127">See also</span></span>

- [<span data-ttu-id="30309-128">IMetaDataImport-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="30309-128">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="30309-129">IMetaDataImport2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="30309-129">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
