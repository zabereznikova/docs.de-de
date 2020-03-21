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
ms.openlocfilehash: 8ca5ab70f60de4d783800fb18612a8f04cb9cee1
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79177713"
---
# <a name="imetadataemitdefinefield-method"></a><span data-ttu-id="a0063-102">IMetaDataEmit::DefineField-Methode</span><span class="sxs-lookup"><span data-stu-id="a0063-102">IMetaDataEmit::DefineField Method</span></span>
<span data-ttu-id="a0063-103">Erstellt eine Definition für ein Feld mit der angegebenen Metadatensignatur und ruft ein Token für diese Felddefinition ab.</span><span class="sxs-lookup"><span data-stu-id="a0063-103">Creates a definition for a field with the specified metadata signature, and gets a token to that field definition.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a0063-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="a0063-104">Syntax</span></span>  
  
```cpp  
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
  
## <a name="parameters"></a><span data-ttu-id="a0063-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="a0063-105">Parameters</span></span>  
 `td`  
 <span data-ttu-id="a0063-106">[in] Das `mdTypeDef` Token für die einschließende Klasse oder Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="a0063-106">[in] The `mdTypeDef` token for the enclosing class or interface.</span></span>  
  
 `szName`  
 <span data-ttu-id="a0063-107">[in] Der Feldname in Unicode.</span><span class="sxs-lookup"><span data-stu-id="a0063-107">[in] The field name in Unicode.</span></span>  
  
 `dwFieldFlags`  
 <span data-ttu-id="a0063-108">[in] Die Feldattribute.</span><span class="sxs-lookup"><span data-stu-id="a0063-108">[in] The field attributes.</span></span> <span data-ttu-id="a0063-109">Dies ist eine `CorFieldAttr` Bitmaske von Werten.</span><span class="sxs-lookup"><span data-stu-id="a0063-109">This is a bitmask of `CorFieldAttr` values.</span></span>  
  
 `pvSigBlob`  
 <span data-ttu-id="a0063-110">[in] Die Feldsignatur als BLOB.</span><span class="sxs-lookup"><span data-stu-id="a0063-110">[in] The field signature as a BLOB.</span></span>  
  
 `cbSigBlob`  
 <span data-ttu-id="a0063-111">[in] Die Anzahl der `pvSigBlob`Bytes in .</span><span class="sxs-lookup"><span data-stu-id="a0063-111">[in] The count of bytes in `pvSigBlob`.</span></span>  
  
 `dwCPlusTypeFlag`  
 <span data-ttu-id="a0063-112">[in] Die `ELEMENT_TYPE_` *\** für den konstanten Wert.</span><span class="sxs-lookup"><span data-stu-id="a0063-112">[in] The `ELEMENT_TYPE_`*\** for the constant value.</span></span> <span data-ttu-id="a0063-113">Dies `CorElementType` ist ein Wert.</span><span class="sxs-lookup"><span data-stu-id="a0063-113">This is a `CorElementType` value.</span></span> <span data-ttu-id="a0063-114">Wenn Sie keinen konstanten Wert `ELEMENT_TYPE_END`für das Feld definieren, verwenden Sie .</span><span class="sxs-lookup"><span data-stu-id="a0063-114">If not defining a constant value for the field, use `ELEMENT_TYPE_END`.</span></span>  
  
 `pValue`  
 <span data-ttu-id="a0063-115">[in] Der konstante Wert für das Feld.</span><span class="sxs-lookup"><span data-stu-id="a0063-115">[in] The constant value for the field.</span></span>  
  
 `cchValue`  
 <span data-ttu-id="a0063-116">[in] Die Größe in (Unicode)-Zeichen von `pValue`.</span><span class="sxs-lookup"><span data-stu-id="a0063-116">[in] The size in (Unicode) characters of `pValue`.</span></span>  
  
 `pmd`  
 <span data-ttu-id="a0063-117">[out] Das `mdFieldDef` token zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="a0063-117">[out] The `mdFieldDef` token assigned.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a0063-118">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="a0063-118">Requirements</span></span>  
 <span data-ttu-id="a0063-119">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a0063-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a0063-120">**Kopfzeile:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="a0063-120">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="a0063-121">**Bibliothek:** Wird als Ressource in MSCorEE.dll verwendet</span><span class="sxs-lookup"><span data-stu-id="a0063-121">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="a0063-122">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a0063-122">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a0063-123">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="a0063-123">See also</span></span>

- [<span data-ttu-id="a0063-124">IMetaDataEmit-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="a0063-124">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="a0063-125">IMetaDataEmit2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="a0063-125">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
