---
title: IMetaDataEmit::DefineImportType-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataEmit.DefineImportType
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataEmit::DefineImportType
helpviewer_keywords:
- DefineImportType method [.NET Framework metadata]
- IMetaDataEmit::DefineImportType method [.NET Framework metadata]
ms.assetid: 37fd27af-8062-4904-ace4-51bb78ec600a
topic_type: apiref
caps.latest.revision: "12"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 1fee13c88cc39398808ad1ff481e602d63e8f39f
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="imetadataemitdefineimporttype-method"></a><span data-ttu-id="be72d-102">IMetaDataEmit::DefineImportType-Methode</span><span class="sxs-lookup"><span data-stu-id="be72d-102">IMetaDataEmit::DefineImportType Method</span></span>
<span data-ttu-id="be72d-103">Erstellt einen Verweis auf den angegebenen Typ, der außerhalb des aktuellen Bereichs definiert ist, und ein Token für diesen Verweis definiert.</span><span class="sxs-lookup"><span data-stu-id="be72d-103">Creates a reference to the specified type that is defined outside the current scope, and defines a token for that reference.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="be72d-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="be72d-104">Syntax</span></span>  
  
```  
HRESULT DefineImportType (   
    [in]  IMetaDataAssemblyImport  *pAssemImport,   
    [in]  const void               *pbHashValue,   
    [in]  ULONG                    cbHashValue,    
    [in]  IMetaDataImport          *pImport,   
    [in]  mdTypeDef                tdImport,   
    [in]  IMetaDataAssemblyEmit    *pAssemEmit,   
    [out] mdTypeRef                *ptr  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="be72d-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="be72d-105">Parameters</span></span>  
 `pAssemImport`  
 <span data-ttu-id="be72d-106">[in] Ein [IMetaDataAssemblyImport](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md) Schnittstelle, die die Assembly darstellt, aus dem der Zieltyp importiert wird.</span><span class="sxs-lookup"><span data-stu-id="be72d-106">[in] An [IMetaDataAssemblyImport](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md) interface that represents the assembly from which the target type is imported.</span></span>  
  
 `pbHashValue`  
 <span data-ttu-id="be72d-107">[in] Ein Array, das den Hash für die Assembly gemäß enthält `pAssemImport`.</span><span class="sxs-lookup"><span data-stu-id="be72d-107">[in] An array that contains the hash for the assembly specified by `pAssemImport`.</span></span>  
  
 `cbHashValue`  
 <span data-ttu-id="be72d-108">[in] Die Anzahl der Bytes im `pbHashValue`-Array.</span><span class="sxs-lookup"><span data-stu-id="be72d-108">[in] The number of bytes in the `pbHashValue` array.</span></span>  
  
 `pImport`  
 <span data-ttu-id="be72d-109">[in] Ein [IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md) Schnittstelle, die den Metadatenbereich darstellt, aus dem der Zieltyp importiert wird.</span><span class="sxs-lookup"><span data-stu-id="be72d-109">[in] An [IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md) interface that represents the metadata scope from which the target type is imported.</span></span>  
  
 `tdImport`  
 <span data-ttu-id="be72d-110">[in] Ein `mdTypeDef` Token, das den Zieltyp angibt.</span><span class="sxs-lookup"><span data-stu-id="be72d-110">[in] An `mdTypeDef` token that specifies the target type.</span></span>  
  
 `pAssemEmit`  
 <span data-ttu-id="be72d-111">[in] Ein [IMetaDataAssemblyEmit](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md) Schnittstelle, die die Assembly darstellt, in dem der Zieltyp importiert wird.</span><span class="sxs-lookup"><span data-stu-id="be72d-111">[in] An [IMetaDataAssemblyEmit](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md) interface that represents the assembly into which the target type is imported.</span></span>  
  
 `ptr`  
 <span data-ttu-id="be72d-112">[out] Die `mdTypeRef` Token, das im aktuellen Bereich für den Typverweis definiert ist.</span><span class="sxs-lookup"><span data-stu-id="be72d-112">[out] The `mdTypeRef` token that is defined in the current scope for the type reference.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="be72d-113">Hinweise</span><span class="sxs-lookup"><span data-stu-id="be72d-113">Remarks</span></span>  
 <span data-ttu-id="be72d-114">Vor dem Aufruf der [IMetaDataEmit:: DefineImportMember](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-defineimportmember-method.md) -Methode, die Sie verwenden die `DefineImportType` Methode, um einen Typverweis, im aktuellen Bereich, für des Elements übergeordnete Klasse oder Schnittstelle zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="be72d-114">Prior to calling the [IMetaDataEmit::DefineImportMember](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-defineimportmember-method.md) method, you can use the `DefineImportType` method to create a type reference, in the current scope, for the member's parent class or parent interface.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="be72d-115">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="be72d-115">Requirements</span></span>  
 <span data-ttu-id="be72d-116">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="be72d-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="be72d-117">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="be72d-117">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="be72d-118">**Bibliothek:** als Ressource in MSCorEE.dll verwendet</span><span class="sxs-lookup"><span data-stu-id="be72d-118">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="be72d-119">**.NET Framework-Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="be72d-119">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="be72d-120">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="be72d-120">See Also</span></span>  
 [<span data-ttu-id="be72d-121">IMetaDataEmit-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="be72d-121">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)  
 [<span data-ttu-id="be72d-122">IMetaDataEmit2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="be72d-122">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
