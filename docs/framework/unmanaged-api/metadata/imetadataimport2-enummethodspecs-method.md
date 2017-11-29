---
title: IMetaDataImport2::EnumMethodSpecs-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataImport2.EnumMethodSpecs
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataImport2::EnumMethodSpecs
helpviewer_keywords:
- IMetaDataImport2::EnumMethodSpecs method [.NET Framework metadata]
- EnumMethodSpecs method [.NET Framework metadata]
ms.assetid: b3fc1e6c-bcb6-4915-baf8-7dc0a31b8724
topic_type: apiref
caps.latest.revision: "11"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: db1968c73d5a1c6e0687bc86f249c70b6c21712c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="imetadataimport2enummethodspecs-method"></a><span data-ttu-id="3457b-102">IMetaDataImport2::EnumMethodSpecs-Methode</span><span class="sxs-lookup"><span data-stu-id="3457b-102">IMetaDataImport2::EnumMethodSpecs Method</span></span>
<span data-ttu-id="3457b-103">Ruft einen Enumerator für ein Array von MethodSpec-Token mit der angegebenen MethodDef oder MemberRef token.</span><span class="sxs-lookup"><span data-stu-id="3457b-103">Gets an enumerator for an array of MethodSpec tokens associated with the specified MethodDef or MemberRef token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3457b-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="3457b-104">Syntax</span></span>  
  
```  
HRESULT EnumMethodSpecs (  
    [in, out] HCORENUM      *phEnum,   
    [in]      mdToken       tk,  
    [out]     mdMethodSpec  rMethodSpecs[],  
    [in]      ULONG         cMax,  
    [out]     ULONG         *pcMethodSpecs  
);   
```  
  
#### <a name="parameters"></a><span data-ttu-id="3457b-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="3457b-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="3457b-106">[in, out] Ein Zeiger auf den Enumerator für `rMethodSpecs`.</span><span class="sxs-lookup"><span data-stu-id="3457b-106">[in, out] A pointer to the enumerator for `rMethodSpecs`.</span></span>  
  
 `tk`  
 <span data-ttu-id="3457b-107">[in] Das MemberRef oder MethodDef-Token, das die Methode darstellt, deren MethodSpec-Token aufgelistet werden sollen.</span><span class="sxs-lookup"><span data-stu-id="3457b-107">[in] The MemberRef or MethodDef token that represents the method whose MethodSpec tokens are to be enumerated.</span></span> <span data-ttu-id="3457b-108">Wenn der Wert der `tk` ist 0 (null), werden alle MethodSpec-Token im Bereich aufgezählt werden.</span><span class="sxs-lookup"><span data-stu-id="3457b-108">If the value of `tk` is 0 (zero), all MethodSpec tokens in the scope will be enumerated.</span></span>  
  
 `rMethodSpecs`  
 <span data-ttu-id="3457b-109">[out] Das Array von aufzulistenden MethodSpec-Token.</span><span class="sxs-lookup"><span data-stu-id="3457b-109">[out] The array of MethodSpec tokens to enumerate.</span></span>  
  
 `cMax`  
 <span data-ttu-id="3457b-110">[in] Die angeforderte maximale Anzahl von Token zu versehen `rMethodSpecs`.</span><span class="sxs-lookup"><span data-stu-id="3457b-110">[in] The requested maximum number of tokens to place in `rMethodSpecs`.</span></span>  
  
 `pcMethodSpecs`  
 <span data-ttu-id="3457b-111">[out] Die zurückgegebene Anzahl von Token in platziert `rMethodSpecs`.</span><span class="sxs-lookup"><span data-stu-id="3457b-111">[out] The returned number of tokens placed in `rMethodSpecs`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="3457b-112">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="3457b-112">Return Value</span></span>  
  
|<span data-ttu-id="3457b-113">HRESULT</span><span class="sxs-lookup"><span data-stu-id="3457b-113">HRESULT</span></span>|<span data-ttu-id="3457b-114">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="3457b-114">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="3457b-115">`EnumMethodSpecs`wurde erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="3457b-115">`EnumMethodSpecs` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="3457b-116">`phEnum`verfügt über keine Memberelemente.</span><span class="sxs-lookup"><span data-stu-id="3457b-116">`phEnum` has no member elements.</span></span> <span data-ttu-id="3457b-117">In diesem Fall `pcMethodSpecs` auf 0 (null) festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="3457b-117">In this case, `pcMethodSpecs` is set to 0 (zero).</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="3457b-118">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="3457b-118">Requirements</span></span>  
 <span data-ttu-id="3457b-119">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3457b-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3457b-120">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="3457b-120">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="3457b-121">**Bibliothek:** als Ressource in MsCorEE.dll verwendet</span><span class="sxs-lookup"><span data-stu-id="3457b-121">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="3457b-122">**.NET Framework-Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3457b-122">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3457b-123">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="3457b-123">See Also</span></span>  
 [<span data-ttu-id="3457b-124">IMetaDataImport2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="3457b-124">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)  
 [<span data-ttu-id="3457b-125">IMetaDataImport-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="3457b-125">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
