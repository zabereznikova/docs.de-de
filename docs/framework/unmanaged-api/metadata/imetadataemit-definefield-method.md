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
ms.openlocfilehash: a8ba8a762c56a666c67b25b9ce0420099fce419a
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62044160"
---
# <a name="imetadataemitdefinefield-method"></a><span data-ttu-id="bf7f5-102">IMetaDataEmit::DefineField-Methode</span><span class="sxs-lookup"><span data-stu-id="bf7f5-102">IMetaDataEmit::DefineField Method</span></span>
<span data-ttu-id="bf7f5-103">Erstellt eine Definition für ein Feld mit der angegebenen Metadaten-Signatur und ruft ein Token, Field-Definition ab.</span><span class="sxs-lookup"><span data-stu-id="bf7f5-103">Creates a definition for a field with the specified metadata signature, and gets a token to that field definition.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bf7f5-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="bf7f5-104">Syntax</span></span>  
  
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
  
## <a name="parameters"></a><span data-ttu-id="bf7f5-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="bf7f5-105">Parameters</span></span>  
 `td`  
 <span data-ttu-id="bf7f5-106">[in] Die `mdTypeDef` token für die einschließende Klasse oder Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="bf7f5-106">[in] The `mdTypeDef` token for the enclosing class or interface.</span></span>  
  
 `szName`  
 <span data-ttu-id="bf7f5-107">[in] Der Name des Felds im Unicode-Format.</span><span class="sxs-lookup"><span data-stu-id="bf7f5-107">[in] The field name in Unicode.</span></span>  
  
 `dwFieldFlags`  
 <span data-ttu-id="bf7f5-108">[in] Die Attribute des Felds.</span><span class="sxs-lookup"><span data-stu-id="bf7f5-108">[in] The field attributes.</span></span> <span data-ttu-id="bf7f5-109">Dies ist eine Bitmaske der `CorFieldAttr` Werte.</span><span class="sxs-lookup"><span data-stu-id="bf7f5-109">This is a bitmask of `CorFieldAttr` values.</span></span>  
  
 `pvSigBlob`  
 <span data-ttu-id="bf7f5-110">[in] Die Feldsignatur als BLOB.</span><span class="sxs-lookup"><span data-stu-id="bf7f5-110">[in] The field signature as a BLOB.</span></span>  
  
 `cbSigBlob`  
 <span data-ttu-id="bf7f5-111">[in] Die Anzahl der Bytes im `pvSigBlob`.</span><span class="sxs-lookup"><span data-stu-id="bf7f5-111">[in] The count of bytes in `pvSigBlob`.</span></span>  
  
 `dwCPlusTypeFlag`  
 <span data-ttu-id="bf7f5-112">[in] Die `ELEMENT_TYPE_` *\** für den konstanten Wert.</span><span class="sxs-lookup"><span data-stu-id="bf7f5-112">[in] The `ELEMENT_TYPE_`*\** for the constant value.</span></span> <span data-ttu-id="bf7f5-113">Dies ist eine `CorElementType` Wert.</span><span class="sxs-lookup"><span data-stu-id="bf7f5-113">This is a `CorElementType` value.</span></span> <span data-ttu-id="bf7f5-114">Wenn einen konstanten Wert für das Feld nicht zu definieren, verwenden Sie `ELEMENT_TYPE_END`.</span><span class="sxs-lookup"><span data-stu-id="bf7f5-114">If not defining a constant value for the field, use `ELEMENT_TYPE_END`.</span></span>  
  
 `pValue`  
 <span data-ttu-id="bf7f5-115">[in] Der Konstante Wert für das Feld.</span><span class="sxs-lookup"><span data-stu-id="bf7f5-115">[in] The constant value for the field.</span></span>  
  
 `cchValue`  
 <span data-ttu-id="bf7f5-116">[in] Die Größe in Zeichen (Unicode) der `pValue`.</span><span class="sxs-lookup"><span data-stu-id="bf7f5-116">[in] The size in (Unicode) characters of `pValue`.</span></span>  
  
 `pmd`  
 <span data-ttu-id="bf7f5-117">[out] Die `mdFieldDef` zugewiesene Token.</span><span class="sxs-lookup"><span data-stu-id="bf7f5-117">[out] The `mdFieldDef` token assigned.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bf7f5-118">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="bf7f5-118">Requirements</span></span>  
 <span data-ttu-id="bf7f5-119">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="bf7f5-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bf7f5-120">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="bf7f5-120">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="bf7f5-121">**Bibliothek:** Als Ressource in MSCorEE.dll verwendet</span><span class="sxs-lookup"><span data-stu-id="bf7f5-121">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="bf7f5-122">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bf7f5-122">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bf7f5-123">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="bf7f5-123">See also</span></span>

- [<span data-ttu-id="bf7f5-124">IMetaDataEmit-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="bf7f5-124">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="bf7f5-125">IMetaDataEmit2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="bf7f5-125">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
