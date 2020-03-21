---
title: IMetaDataImport2::EnumMethodSpecs-Methode
ms.date: 03/30/2017
api_name:
- IMetaDataImport2.EnumMethodSpecs
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport2::EnumMethodSpecs
helpviewer_keywords:
- IMetaDataImport2::EnumMethodSpecs method [.NET Framework metadata]
- EnumMethodSpecs method [.NET Framework metadata]
ms.assetid: b3fc1e6c-bcb6-4915-baf8-7dc0a31b8724
topic_type:
- apiref
ms.openlocfilehash: 2df53ba53c64e042abc54a1d2ac043d301acdde9
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79177174"
---
# <a name="imetadataimport2enummethodspecs-method"></a><span data-ttu-id="4267d-102">IMetaDataImport2::EnumMethodSpecs-Methode</span><span class="sxs-lookup"><span data-stu-id="4267d-102">IMetaDataImport2::EnumMethodSpecs Method</span></span>
<span data-ttu-id="4267d-103">Ruft einen Enumerator für ein Array von MethodSpec-Token ab, die dem angegebenen MethodDef- oder MemberRef-Token zugeordnet sind.</span><span class="sxs-lookup"><span data-stu-id="4267d-103">Gets an enumerator for an array of MethodSpec tokens associated with the specified MethodDef or MemberRef token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4267d-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="4267d-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumMethodSpecs (  
    [in, out] HCORENUM      *phEnum,
    [in]      mdToken       tk,  
    [out]     mdMethodSpec  rMethodSpecs[],  
    [in]      ULONG         cMax,  
    [out]     ULONG         *pcMethodSpecs  
);
```  
  
## <a name="parameters"></a><span data-ttu-id="4267d-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="4267d-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="4267d-106">[in, out] Ein Zeiger auf den Enumerator für `rMethodSpecs`.</span><span class="sxs-lookup"><span data-stu-id="4267d-106">[in, out] A pointer to the enumerator for `rMethodSpecs`.</span></span>  
  
 `tk`  
 <span data-ttu-id="4267d-107">[in] Das MemberRef- oder MethodDef-Token, das die Methode darstellt, deren MethodSpec-Token aufgezählt werden sollen.</span><span class="sxs-lookup"><span data-stu-id="4267d-107">[in] The MemberRef or MethodDef token that represents the method whose MethodSpec tokens are to be enumerated.</span></span> <span data-ttu-id="4267d-108">Wenn der `tk` Wert von 0 (Null) ist, werden alle MethodSpec-Token im Bereich aufgezählt.</span><span class="sxs-lookup"><span data-stu-id="4267d-108">If the value of `tk` is 0 (zero), all MethodSpec tokens in the scope will be enumerated.</span></span>  
  
 `rMethodSpecs`  
 <span data-ttu-id="4267d-109">[out] Das Array von MethodSpec-Token, die aufgezählt werden sollen.</span><span class="sxs-lookup"><span data-stu-id="4267d-109">[out] The array of MethodSpec tokens to enumerate.</span></span>  
  
 `cMax`  
 <span data-ttu-id="4267d-110">[in] Die angeforderte maximale Anzahl von `rMethodSpecs`Token, die in platziert werden sollen.</span><span class="sxs-lookup"><span data-stu-id="4267d-110">[in] The requested maximum number of tokens to place in `rMethodSpecs`.</span></span>  
  
 `pcMethodSpecs`  
 <span data-ttu-id="4267d-111">[out] Die zurückgegebene Anzahl von `rMethodSpecs`Token, die in platziert wurden.</span><span class="sxs-lookup"><span data-stu-id="4267d-111">[out] The returned number of tokens placed in `rMethodSpecs`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="4267d-112">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="4267d-112">Return Value</span></span>  
  
|<span data-ttu-id="4267d-113">HRESULT</span><span class="sxs-lookup"><span data-stu-id="4267d-113">HRESULT</span></span>|<span data-ttu-id="4267d-114">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="4267d-114">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="4267d-115">`EnumMethodSpecs`erfolgreich zurückgegeben werden.</span><span class="sxs-lookup"><span data-stu-id="4267d-115">`EnumMethodSpecs` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="4267d-116">`phEnum`hat keine Elementelemente.</span><span class="sxs-lookup"><span data-stu-id="4267d-116">`phEnum` has no member elements.</span></span> <span data-ttu-id="4267d-117">In diesem `pcMethodSpecs` Fall ist auf 0 (Null) gesetzt.</span><span class="sxs-lookup"><span data-stu-id="4267d-117">In this case, `pcMethodSpecs` is set to 0 (zero).</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="4267d-118">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="4267d-118">Requirements</span></span>  
 <span data-ttu-id="4267d-119">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4267d-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4267d-120">**Kopfzeile:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="4267d-120">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="4267d-121">**Bibliothek:** Wird als Ressource in MsCorEE.dll verwendet</span><span class="sxs-lookup"><span data-stu-id="4267d-121">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="4267d-122">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4267d-122">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4267d-123">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="4267d-123">See also</span></span>

- [<span data-ttu-id="4267d-124">IMetaDataImport2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="4267d-124">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
- [<span data-ttu-id="4267d-125">IMetaDataImport-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="4267d-125">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
