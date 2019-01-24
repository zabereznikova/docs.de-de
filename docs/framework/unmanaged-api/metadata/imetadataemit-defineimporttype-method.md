---
title: IMetaDataEmit::DefineImportType-Methode
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.DefineImportType
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::DefineImportType
helpviewer_keywords:
- DefineImportType method [.NET Framework metadata]
- IMetaDataEmit::DefineImportType method [.NET Framework metadata]
ms.assetid: 37fd27af-8062-4904-ace4-51bb78ec600a
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: b7190d2f9d4b64b6a97280914d63c98e505ec70f
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54649439"
---
# <a name="imetadataemitdefineimporttype-method"></a><span data-ttu-id="e4458-102">IMetaDataEmit::DefineImportType-Methode</span><span class="sxs-lookup"><span data-stu-id="e4458-102">IMetaDataEmit::DefineImportType Method</span></span>
<span data-ttu-id="e4458-103">Erstellt einen Verweis auf den angegebenen Typ, der außerhalb des aktuellen Bereichs definiert ist, und definiert ein Token für diesen Verweis.</span><span class="sxs-lookup"><span data-stu-id="e4458-103">Creates a reference to the specified type that is defined outside the current scope, and defines a token for that reference.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e4458-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="e4458-104">Syntax</span></span>  
  
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
  
#### <a name="parameters"></a><span data-ttu-id="e4458-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="e4458-105">Parameters</span></span>  
 `pAssemImport`  
 <span data-ttu-id="e4458-106">[in] Ein [IMetaDataAssemblyImport](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md) -Schnittstelle, die die Assembly darstellt, aus der der Zieltyp importiert wird.</span><span class="sxs-lookup"><span data-stu-id="e4458-106">[in] An [IMetaDataAssemblyImport](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md) interface that represents the assembly from which the target type is imported.</span></span>  
  
 `pbHashValue`  
 <span data-ttu-id="e4458-107">[in] Ein Array, das den Hash für die Assembly, die anhand des enthält `pAssemImport`.</span><span class="sxs-lookup"><span data-stu-id="e4458-107">[in] An array that contains the hash for the assembly specified by `pAssemImport`.</span></span>  
  
 `cbHashValue`  
 <span data-ttu-id="e4458-108">[in] Die Anzahl der Bytes im `pbHashValue`-Array.</span><span class="sxs-lookup"><span data-stu-id="e4458-108">[in] The number of bytes in the `pbHashValue` array.</span></span>  
  
 `pImport`  
 <span data-ttu-id="e4458-109">[in] Ein [IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md) -Schnittstelle, die den Metadatenbereich darstellt, aus der der Zieltyp importiert wird.</span><span class="sxs-lookup"><span data-stu-id="e4458-109">[in] An [IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md) interface that represents the metadata scope from which the target type is imported.</span></span>  
  
 `tdImport`  
 <span data-ttu-id="e4458-110">[in] Ein `mdTypeDef` Token, das den Zieltyp angibt.</span><span class="sxs-lookup"><span data-stu-id="e4458-110">[in] An `mdTypeDef` token that specifies the target type.</span></span>  
  
 `pAssemEmit`  
 <span data-ttu-id="e4458-111">[in] Ein [IMetaDataAssemblyEmit](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md) -Schnittstelle, die die Assembly darstellt, in die der Zieltyp importiert wird.</span><span class="sxs-lookup"><span data-stu-id="e4458-111">[in] An [IMetaDataAssemblyEmit](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md) interface that represents the assembly into which the target type is imported.</span></span>  
  
 `ptr`  
 <span data-ttu-id="e4458-112">[out] Die `mdTypeRef` Token, das im aktuellen Bereich für den Typverweis definiert ist.</span><span class="sxs-lookup"><span data-stu-id="e4458-112">[out] The `mdTypeRef` token that is defined in the current scope for the type reference.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e4458-113">Hinweise</span><span class="sxs-lookup"><span data-stu-id="e4458-113">Remarks</span></span>  
 <span data-ttu-id="e4458-114">Vor dem Aufrufen der [IMetaDataEmit:: DefineImportMember](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-defineimportmember-method.md) -Methode, die Sie verwenden die `DefineImportType` Methode, um einen Typverweis, im aktuellen Bereich, für des Members übergeordnete Klasse oder Schnittstelle zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="e4458-114">Prior to calling the [IMetaDataEmit::DefineImportMember](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-defineimportmember-method.md) method, you can use the `DefineImportType` method to create a type reference, in the current scope, for the member's parent class or parent interface.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e4458-115">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="e4458-115">Requirements</span></span>  
 <span data-ttu-id="e4458-116">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e4458-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e4458-117">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="e4458-117">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="e4458-118">**Bibliothek:** Als Ressource in MSCorEE.dll verwendet</span><span class="sxs-lookup"><span data-stu-id="e4458-118">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="e4458-119">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e4458-119">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e4458-120">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e4458-120">See also</span></span>
- [<span data-ttu-id="e4458-121">IMetaDataEmit-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="e4458-121">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="e4458-122">IMetaDataEmit2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="e4458-122">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
