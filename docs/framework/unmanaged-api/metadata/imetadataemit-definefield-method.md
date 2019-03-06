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
ms.openlocfilehash: f8553665ba64a1c8e1cb6398d94cd1f772a566ed
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/06/2019
ms.locfileid: "57466660"
---
# <a name="imetadataemitdefinefield-method"></a><span data-ttu-id="78af7-102">IMetaDataEmit::DefineField-Methode</span><span class="sxs-lookup"><span data-stu-id="78af7-102">IMetaDataEmit::DefineField Method</span></span>
<span data-ttu-id="78af7-103">Erstellt eine Definition für ein Feld mit der angegebenen Metadaten-Signatur und ruft ein Token, Field-Definition ab.</span><span class="sxs-lookup"><span data-stu-id="78af7-103">Creates a definition for a field with the specified metadata signature, and gets a token to that field definition.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="78af7-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="78af7-104">Syntax</span></span>  
  
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
  
## <a name="parameters"></a><span data-ttu-id="78af7-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="78af7-105">Parameters</span></span>  
 `td`  
 <span data-ttu-id="78af7-106">[in] Die `mdTypeDef` token für die einschließende Klasse oder Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="78af7-106">[in] The `mdTypeDef` token for the enclosing class or interface.</span></span>  
  
 `szName`  
 <span data-ttu-id="78af7-107">[in] Der Name des Felds im Unicode-Format.</span><span class="sxs-lookup"><span data-stu-id="78af7-107">[in] The field name in Unicode.</span></span>  
  
 `dwFieldFlags`  
 <span data-ttu-id="78af7-108">[in] Die Attribute des Felds.</span><span class="sxs-lookup"><span data-stu-id="78af7-108">[in] The field attributes.</span></span> <span data-ttu-id="78af7-109">Dies ist eine Bitmaske der `CorFieldAttr` Werte.</span><span class="sxs-lookup"><span data-stu-id="78af7-109">This is a bitmask of `CorFieldAttr` values.</span></span>  
  
 `pvSigBlob`  
 <span data-ttu-id="78af7-110">[in] Die Feldsignatur als BLOB.</span><span class="sxs-lookup"><span data-stu-id="78af7-110">[in] The field signature as a BLOB.</span></span>  
  
 `cbSigBlob`  
 <span data-ttu-id="78af7-111">[in] Die Anzahl der Bytes im `pvSigBlob`.</span><span class="sxs-lookup"><span data-stu-id="78af7-111">[in] The count of bytes in `pvSigBlob`.</span></span>  
  
 `dwCPlusTypeFlag`  
 <span data-ttu-id="78af7-112">[in] Die `ELEMENT_TYPE_` *\** für den konstanten Wert.</span><span class="sxs-lookup"><span data-stu-id="78af7-112">[in] The `ELEMENT_TYPE_`*\** for the constant value.</span></span> <span data-ttu-id="78af7-113">Dies ist eine `CorElementType` Wert.</span><span class="sxs-lookup"><span data-stu-id="78af7-113">This is a `CorElementType` value.</span></span> <span data-ttu-id="78af7-114">Wenn einen konstanten Wert für das Feld nicht zu definieren, verwenden Sie `ELEMENT_TYPE_END`.</span><span class="sxs-lookup"><span data-stu-id="78af7-114">If not defining a constant value for the field, use `ELEMENT_TYPE_END`.</span></span>  
  
 `pValue`  
 <span data-ttu-id="78af7-115">[in] Der Konstante Wert für das Feld.</span><span class="sxs-lookup"><span data-stu-id="78af7-115">[in] The constant value for the field.</span></span>  
  
 `cchValue`  
 <span data-ttu-id="78af7-116">[in] Die Größe in Zeichen (Unicode) der `pValue`.</span><span class="sxs-lookup"><span data-stu-id="78af7-116">[in] The size in (Unicode) characters of `pValue`.</span></span>  
  
 `pmd`  
 <span data-ttu-id="78af7-117">[out] Die `mdFieldDef` zugewiesene Token.</span><span class="sxs-lookup"><span data-stu-id="78af7-117">[out] The `mdFieldDef` token assigned.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="78af7-118">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="78af7-118">Requirements</span></span>  
 <span data-ttu-id="78af7-119">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="78af7-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="78af7-120">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="78af7-120">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="78af7-121">**Bibliothek:** Als Ressource in MSCorEE.dll verwendet</span><span class="sxs-lookup"><span data-stu-id="78af7-121">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="78af7-122">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="78af7-122">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="78af7-123">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="78af7-123">See also</span></span>
- [<span data-ttu-id="78af7-124">IMetaDataEmit-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="78af7-124">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="78af7-125">IMetaDataEmit2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="78af7-125">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
