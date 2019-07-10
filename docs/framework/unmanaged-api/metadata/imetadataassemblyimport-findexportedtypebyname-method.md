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
ms.openlocfilehash: 8a70c041bc17f58a5e17877dd2e1f2aa2944e689
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67777922"
---
# <a name="imetadataassemblyimportfindexportedtypebyname-method"></a><span data-ttu-id="43132-102">IMetaDataAssemblyImport::FindExportedTypeByName-Methode</span><span class="sxs-lookup"><span data-stu-id="43132-102">IMetaDataAssemblyImport::FindExportedTypeByName Method</span></span>
<span data-ttu-id="43132-103">Ruft einen Zeiger auf einem exportierten Typ, erhält seinen Namen und der einschließende Typ ab.</span><span class="sxs-lookup"><span data-stu-id="43132-103">Gets a pointer to an exported type, given its name and enclosing type.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="43132-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="43132-104">Syntax</span></span>  
  
```cpp  
HRESULT FindExportedTypeByName (  
    [in]  LPCWSTR           szName,   
    [in]  mdToken           mdtExportedType,   
    [out] mdExportedType    *ptkExportedType  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="43132-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="43132-105">Parameters</span></span>  
 `szName`  
 <span data-ttu-id="43132-106">[in] Der Name des exportierten Typs.</span><span class="sxs-lookup"><span data-stu-id="43132-106">[in] The name of the exported type.</span></span>  
  
 `mdtExportedType`  
 <span data-ttu-id="43132-107">[in] Das Metadatentoken für die einschließende Klasse des exportierten Typs.</span><span class="sxs-lookup"><span data-stu-id="43132-107">[in] The metadata token for the enclosing class of the exported type.</span></span> <span data-ttu-id="43132-108">Dieser Wert ist `mdExportedTypeNil` Wenn der angeforderte exportierte Typ nicht geschachtelter Typ ist.</span><span class="sxs-lookup"><span data-stu-id="43132-108">This value is `mdExportedTypeNil` if the requested exported type is not a nested type.</span></span>  
  
 `ptkExportedType`  
 <span data-ttu-id="43132-109">[out] Ein Zeiger auf die `mdExportedType` Token, das den exportierten Typ darstellt.</span><span class="sxs-lookup"><span data-stu-id="43132-109">[out] A pointer to the `mdExportedType` token that represents the exported type.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="43132-110">Hinweise</span><span class="sxs-lookup"><span data-stu-id="43132-110">Remarks</span></span>  
 <span data-ttu-id="43132-111">Die `FindExportedTypeByName` -Methode verwendet die Standardregeln, die von der common Language Runtime zum Auflösen von verweisen.</span><span class="sxs-lookup"><span data-stu-id="43132-111">The `FindExportedTypeByName` method uses the standard rules employed by the common language runtime for resolving references.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="43132-112">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="43132-112">Requirements</span></span>  
 <span data-ttu-id="43132-113">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="43132-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="43132-114">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="43132-114">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="43132-115">**Bibliothek:** Als Ressource in MsCorEE.dll verwendet</span><span class="sxs-lookup"><span data-stu-id="43132-115">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="43132-116">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="43132-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="43132-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="43132-117">See also</span></span>

- [<span data-ttu-id="43132-118">IMetaDataAssemblyImport-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="43132-118">IMetaDataAssemblyImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md)
- [<span data-ttu-id="43132-119">So sucht Common Language Runtime nach Assemblys</span><span class="sxs-lookup"><span data-stu-id="43132-119">How the Runtime Locates Assemblies</span></span>](../../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md)
