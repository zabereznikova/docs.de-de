---
title: IMetaDataEmit::DefineField-Methode
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.DefineField
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::DefineField
helpviewer_keywords:
- IMetaDataEmit::DefineField method [.NET Framework metadata]
- DefineField method, IMetaDataEmit interface [.NET Framework metadata
ms.assetid: 6b5be4fc-2e86-499c-8b09-833160bca767
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: b54ceb099df15855b6b30b8c28d7d8917a9c71eb
ms.sourcegitcommit: c93fd5139f9efcf6db514e3474301738a6d1d649
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/27/2018
ms.locfileid: "50184948"
---
# <a name="imetadataemitdefinefield-method"></a><span data-ttu-id="d58b6-102">IMetaDataEmit::DefineField-Methode</span><span class="sxs-lookup"><span data-stu-id="d58b6-102">IMetaDataEmit::DefineField Method</span></span>
<span data-ttu-id="d58b6-103">Erstellt eine Definition für ein Feld mit der angegebenen Metadaten-Signatur und ruft ein Token, Field-Definition ab.</span><span class="sxs-lookup"><span data-stu-id="d58b6-103">Creates a definition for a field with the specified metadata signature, and gets a token to that field definition.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d58b6-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="d58b6-104">Syntax</span></span>  
  
```  
HRESULT DefineField (   
    [in]  mdTypeDef   td,   
    [in]  LPCWSTR     szName,   
    [in]  DWORD       dwFieldFlags,   
    [in]  PCCOR_SIGNATURE pvSigBlob,   
    [in]  ULONG       cbSigBlob,   
    [in]  DWORD       dwCPlusTypeFlag,   
    [in]  void const  *pValue,   
    [in]  ULONG       cchValue,   
    [out] mdFieldDef  *pmd   
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="d58b6-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="d58b6-105">Parameters</span></span>  
 `td`  
 <span data-ttu-id="d58b6-106">[in] Die `mdTypeDef` token für die einschließende Klasse oder Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="d58b6-106">[in] The `mdTypeDef` token for the enclosing class or interface.</span></span>  
  
 `szName`  
 <span data-ttu-id="d58b6-107">[in] Der Name des Felds im Unicode-Format.</span><span class="sxs-lookup"><span data-stu-id="d58b6-107">[in] The field name in Unicode.</span></span>  
  
 `dwFieldFlags`  
 <span data-ttu-id="d58b6-108">[in] Die Attribute des Felds.</span><span class="sxs-lookup"><span data-stu-id="d58b6-108">[in] The field attributes.</span></span> <span data-ttu-id="d58b6-109">Dies ist eine Bitmaske der `CorFieldAttr` Werte.</span><span class="sxs-lookup"><span data-stu-id="d58b6-109">This is a bitmask of `CorFieldAttr` values.</span></span>  
  
 `pvSigBlob`  
 <span data-ttu-id="d58b6-110">[in] Die Feldsignatur als BLOB.</span><span class="sxs-lookup"><span data-stu-id="d58b6-110">[in] The field signature as a BLOB.</span></span>  
  
 `cbSigBlob`  
 <span data-ttu-id="d58b6-111">[in] Die Anzahl der Bytes im `pvSigBlob`.</span><span class="sxs-lookup"><span data-stu-id="d58b6-111">[in] The count of bytes in `pvSigBlob`.</span></span>  
  
 `dwCPlusTypeFlag`  
 <span data-ttu-id="d58b6-112">[in] Die `ELEMENT_TYPE_` *\** für den konstanten Wert.</span><span class="sxs-lookup"><span data-stu-id="d58b6-112">[in] The `ELEMENT_TYPE_`*\** for the constant value.</span></span> <span data-ttu-id="d58b6-113">Dies ist eine `CorElementType` Wert.</span><span class="sxs-lookup"><span data-stu-id="d58b6-113">This is a `CorElementType` value.</span></span> <span data-ttu-id="d58b6-114">Wenn einen konstanten Wert für das Feld nicht zu definieren, verwenden Sie `ELEMENT_TYPE_END`.</span><span class="sxs-lookup"><span data-stu-id="d58b6-114">If not defining a constant value for the field, use `ELEMENT_TYPE_END`.</span></span>  
  
 `pValue`  
 <span data-ttu-id="d58b6-115">[in] Der Konstante Wert für das Feld.</span><span class="sxs-lookup"><span data-stu-id="d58b6-115">[in] The constant value for the field.</span></span>  
  
 `cchValue`  
 <span data-ttu-id="d58b6-116">[in] Die Größe in Zeichen (Unicode) der `pValue`.</span><span class="sxs-lookup"><span data-stu-id="d58b6-116">[in] The size in (Unicode) characters of `pValue`.</span></span>  
  
 `pmd`  
 <span data-ttu-id="d58b6-117">[out] Die `mdFieldDef` zugewiesene Token.</span><span class="sxs-lookup"><span data-stu-id="d58b6-117">[out] The `mdFieldDef` token assigned.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d58b6-118">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="d58b6-118">Requirements</span></span>  
 <span data-ttu-id="d58b6-119">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d58b6-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d58b6-120">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="d58b6-120">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="d58b6-121">**Bibliothek:** als Ressource in MSCorEE.dll verwendet</span><span class="sxs-lookup"><span data-stu-id="d58b6-121">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="d58b6-122">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d58b6-122">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d58b6-123">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d58b6-123">See Also</span></span>  
 [<span data-ttu-id="d58b6-124">IMetaDataEmit-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="d58b6-124">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)  
 [<span data-ttu-id="d58b6-125">IMetaDataEmit2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="d58b6-125">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
