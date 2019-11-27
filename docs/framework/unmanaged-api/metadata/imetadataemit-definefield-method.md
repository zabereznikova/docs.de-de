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
ms.openlocfilehash: 40f24a4ea628ce92a27ab1bfe97fc87a57dfa4f0
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/23/2019
ms.locfileid: "74432544"
---
# <a name="imetadataemitdefinefield-method"></a><span data-ttu-id="67d6a-102">IMetaDataEmit::DefineField-Methode</span><span class="sxs-lookup"><span data-stu-id="67d6a-102">IMetaDataEmit::DefineField Method</span></span>
<span data-ttu-id="67d6a-103">Erstellt eine Definition für ein Feld mit der angegebenen Metadatensignatur und ruft ein Token für diese Felddefinition ab.</span><span class="sxs-lookup"><span data-stu-id="67d6a-103">Creates a definition for a field with the specified metadata signature, and gets a token to that field definition.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="67d6a-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="67d6a-104">Syntax</span></span>  
  
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
  
## <a name="parameters"></a><span data-ttu-id="67d6a-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="67d6a-105">Parameters</span></span>  
 `td`  
 <span data-ttu-id="67d6a-106">in Das `mdTypeDef` Token für die einschließende Klasse oder Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="67d6a-106">[in] The `mdTypeDef` token for the enclosing class or interface.</span></span>  
  
 `szName`  
 <span data-ttu-id="67d6a-107">in Der Feldname in Unicode.</span><span class="sxs-lookup"><span data-stu-id="67d6a-107">[in] The field name in Unicode.</span></span>  
  
 `dwFieldFlags`  
 <span data-ttu-id="67d6a-108">in Die Feld Attribute.</span><span class="sxs-lookup"><span data-stu-id="67d6a-108">[in] The field attributes.</span></span> <span data-ttu-id="67d6a-109">Dies ist eine Bitmaske von `CorFieldAttr` Werten.</span><span class="sxs-lookup"><span data-stu-id="67d6a-109">This is a bitmask of `CorFieldAttr` values.</span></span>  
  
 `pvSigBlob`  
 <span data-ttu-id="67d6a-110">in Die Feld Signatur als BLOB.</span><span class="sxs-lookup"><span data-stu-id="67d6a-110">[in] The field signature as a BLOB.</span></span>  
  
 `cbSigBlob`  
 <span data-ttu-id="67d6a-111">in Die Anzahl der Bytes in `pvSigBlob`.</span><span class="sxs-lookup"><span data-stu-id="67d6a-111">[in] The count of bytes in `pvSigBlob`.</span></span>  
  
 `dwCPlusTypeFlag`  
 <span data-ttu-id="67d6a-112">in Der `ELEMENT_TYPE_` *\** für den konstanten Wert.</span><span class="sxs-lookup"><span data-stu-id="67d6a-112">[in] The `ELEMENT_TYPE_`*\** for the constant value.</span></span> <span data-ttu-id="67d6a-113">Dies ist ein `CorElementType` Wert.</span><span class="sxs-lookup"><span data-stu-id="67d6a-113">This is a `CorElementType` value.</span></span> <span data-ttu-id="67d6a-114">Wenn Sie keinen konstanten Wert für das Feld definieren, verwenden Sie `ELEMENT_TYPE_END`.</span><span class="sxs-lookup"><span data-stu-id="67d6a-114">If not defining a constant value for the field, use `ELEMENT_TYPE_END`.</span></span>  
  
 `pValue`  
 <span data-ttu-id="67d6a-115">in Der Konstante Wert für das Feld.</span><span class="sxs-lookup"><span data-stu-id="67d6a-115">[in] The constant value for the field.</span></span>  
  
 `cchValue`  
 <span data-ttu-id="67d6a-116">in Die Größe in (Unicode)-Zeichen `pValue`.</span><span class="sxs-lookup"><span data-stu-id="67d6a-116">[in] The size in (Unicode) characters of `pValue`.</span></span>  
  
 `pmd`  
 <span data-ttu-id="67d6a-117">vorgenommen Das zugewiesene `mdFieldDef` Token.</span><span class="sxs-lookup"><span data-stu-id="67d6a-117">[out] The `mdFieldDef` token assigned.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="67d6a-118">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="67d6a-118">Requirements</span></span>  
 <span data-ttu-id="67d6a-119">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="67d6a-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="67d6a-120">**Header:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="67d6a-120">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="67d6a-121">**Bibliothek:** Wird als Ressource in Mscoree. dll verwendet.</span><span class="sxs-lookup"><span data-stu-id="67d6a-121">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="67d6a-122">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="67d6a-122">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="67d6a-123">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="67d6a-123">See also</span></span>

- [<span data-ttu-id="67d6a-124">IMetaDataEmit-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="67d6a-124">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="67d6a-125">IMetaDataEmit2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="67d6a-125">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
