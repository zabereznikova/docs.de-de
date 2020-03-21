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
ms.openlocfilehash: edfe5de9c9d7ef9607a2eea5146194bbd4393a92
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79175992"
---
# <a name="imetadataassemblyimportfindexportedtypebyname-method"></a><span data-ttu-id="c4033-102">IMetaDataAssemblyImport::FindExportedTypeByName-Methode</span><span class="sxs-lookup"><span data-stu-id="c4033-102">IMetaDataAssemblyImport::FindExportedTypeByName Method</span></span>
<span data-ttu-id="c4033-103">Ruft einen Zeiger auf einen exportierten Typ ab, der seinen Namen und den einschließenden Typ angegeben hat.</span><span class="sxs-lookup"><span data-stu-id="c4033-103">Gets a pointer to an exported type, given its name and enclosing type.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c4033-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="c4033-104">Syntax</span></span>  
  
```cpp  
HRESULT FindExportedTypeByName (  
    [in]  LPCWSTR           szName,
    [in]  mdToken           mdtExportedType,
    [out] mdExportedType    *ptkExportedType  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c4033-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="c4033-105">Parameters</span></span>  
 `szName`  
 <span data-ttu-id="c4033-106">[in] Der Name des exportierten Typs.</span><span class="sxs-lookup"><span data-stu-id="c4033-106">[in] The name of the exported type.</span></span>  
  
 `mdtExportedType`  
 <span data-ttu-id="c4033-107">[in] Das Metadatentoken für die einschließende Klasse des exportierten Typs.</span><span class="sxs-lookup"><span data-stu-id="c4033-107">[in] The metadata token for the enclosing class of the exported type.</span></span> <span data-ttu-id="c4033-108">Dieser Wert `mdExportedTypeNil` ist, wenn der angeforderte exportierte Typ kein geschachtelter Typ ist.</span><span class="sxs-lookup"><span data-stu-id="c4033-108">This value is `mdExportedTypeNil` if the requested exported type is not a nested type.</span></span>  
  
 `ptkExportedType`  
 <span data-ttu-id="c4033-109">[out] Ein Zeiger auf `mdExportedType` das Token, das den exportierten Typ darstellt.</span><span class="sxs-lookup"><span data-stu-id="c4033-109">[out] A pointer to the `mdExportedType` token that represents the exported type.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c4033-110">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="c4033-110">Remarks</span></span>  
 <span data-ttu-id="c4033-111">Die `FindExportedTypeByName` Methode verwendet die Standardregeln, die von der Common Language Runtime zum Auflösen von Verweisen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="c4033-111">The `FindExportedTypeByName` method uses the standard rules employed by the common language runtime for resolving references.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c4033-112">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="c4033-112">Requirements</span></span>  
 <span data-ttu-id="c4033-113">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c4033-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c4033-114">**Kopfzeile:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="c4033-114">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="c4033-115">**Bibliothek:** Wird als Ressource in MsCorEE.dll verwendet</span><span class="sxs-lookup"><span data-stu-id="c4033-115">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="c4033-116">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c4033-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c4033-117">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="c4033-117">See also</span></span>

- [<span data-ttu-id="c4033-118">IMetaDataAssemblyImport-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="c4033-118">IMetaDataAssemblyImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md)
- [<span data-ttu-id="c4033-119">So sucht die Laufzeit Assemblys</span><span class="sxs-lookup"><span data-stu-id="c4033-119">How the Runtime Locates Assemblies</span></span>](../../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md)
