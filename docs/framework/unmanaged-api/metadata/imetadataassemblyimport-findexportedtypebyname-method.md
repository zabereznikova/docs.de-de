---
title: IMetaDataAssemblyImport::FindExportedTypeByName-Methode
ms.date: 03/30/2017
api_name:
- IMetaDataAssemblyImport.FindExportedTypeByName
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataAssemblyImport::FindExportedTypeByName
helpviewer_keywords:
- FindExportedTypeByName method [.NET Framework metadata]
- IMetaDataAssemblyImport::FindExportedTypeByName method [.NET Framework metadata]
ms.assetid: 46264b2c-574d-4dde-aafc-77187a104fdd
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 048c7234fcb2592ea0dade135a32341a6e0f404f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33444918"
---
# <a name="imetadataassemblyimportfindexportedtypebyname-method"></a><span data-ttu-id="c226d-102">IMetaDataAssemblyImport::FindExportedTypeByName-Methode</span><span class="sxs-lookup"><span data-stu-id="c226d-102">IMetaDataAssemblyImport::FindExportedTypeByName Method</span></span>
<span data-ttu-id="c226d-103">Ruft einen Zeiger auf einem exportierten Typ erhält den Namen und den einschließenden Typ.</span><span class="sxs-lookup"><span data-stu-id="c226d-103">Gets a pointer to an exported type, given its name and enclosing type.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c226d-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="c226d-104">Syntax</span></span>  
  
```  
HRESULT FindExportedTypeByName (  
    [in]  LPCWSTR           szName,   
    [in]  mdToken           mdtExportedType,   
    [out] mdExportedType    *ptkExportedType  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="c226d-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="c226d-105">Parameters</span></span>  
 `szName`  
 <span data-ttu-id="c226d-106">[in] Der Name des exportierten Typs.</span><span class="sxs-lookup"><span data-stu-id="c226d-106">[in] The name of the exported type.</span></span>  
  
 `mdtExportedType`  
 <span data-ttu-id="c226d-107">[in] Das Metadatentoken für die einschließende Klasse des exportierten Typs.</span><span class="sxs-lookup"><span data-stu-id="c226d-107">[in] The metadata token for the enclosing class of the exported type.</span></span> <span data-ttu-id="c226d-108">Dieser Wert ist `mdExportedTypeNil` , wenn der angeforderte exportiert ist keines geschachtelten Typs.</span><span class="sxs-lookup"><span data-stu-id="c226d-108">This value is `mdExportedTypeNil` if the requested exported type is not a nested type.</span></span>  
  
 `ptkExportedType`  
 <span data-ttu-id="c226d-109">[out] Ein Zeiger auf die `mdExportedType` Token, das den exportierten Typ darstellt.</span><span class="sxs-lookup"><span data-stu-id="c226d-109">[out] A pointer to the `mdExportedType` token that represents the exported type.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c226d-110">Hinweise</span><span class="sxs-lookup"><span data-stu-id="c226d-110">Remarks</span></span>  
 <span data-ttu-id="c226d-111">Die `FindExportedTypeByName` Methode verwendet die Standardregeln, die von der common Language Runtime zum Auflösen von verweisen.</span><span class="sxs-lookup"><span data-stu-id="c226d-111">The `FindExportedTypeByName` method uses the standard rules employed by the common language runtime for resolving references.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c226d-112">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="c226d-112">Requirements</span></span>  
 <span data-ttu-id="c226d-113">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c226d-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c226d-114">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="c226d-114">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="c226d-115">**Bibliothek:** als Ressource in MsCorEE.dll verwendet</span><span class="sxs-lookup"><span data-stu-id="c226d-115">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="c226d-116">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c226d-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c226d-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c226d-117">See Also</span></span>  
 [<span data-ttu-id="c226d-118">IMetaDataAssemblyImport-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="c226d-118">IMetaDataAssemblyImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md)  
 [<span data-ttu-id="c226d-119">So sucht Common Language Runtime nach Assemblys</span><span class="sxs-lookup"><span data-stu-id="c226d-119">How the Runtime Locates Assemblies</span></span>](../../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md)
