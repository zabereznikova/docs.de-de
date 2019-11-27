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
ms.openlocfilehash: 3e470250fa0e86610fcc9a6d6e2ca03569d62b54
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/23/2019
ms.locfileid: "74449449"
---
# <a name="imetadataassemblyimportfindexportedtypebyname-method"></a><span data-ttu-id="0a3f4-102">IMetaDataAssemblyImport::FindExportedTypeByName-Methode</span><span class="sxs-lookup"><span data-stu-id="0a3f4-102">IMetaDataAssemblyImport::FindExportedTypeByName Method</span></span>
<span data-ttu-id="0a3f4-103">Ruft bei Angabe des Namens und des einschließenden Typs einen Zeiger auf einen exportierten Typ ab.</span><span class="sxs-lookup"><span data-stu-id="0a3f4-103">Gets a pointer to an exported type, given its name and enclosing type.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0a3f4-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="0a3f4-104">Syntax</span></span>  
  
```cpp  
HRESULT FindExportedTypeByName (  
    [in]  LPCWSTR           szName,   
    [in]  mdToken           mdtExportedType,   
    [out] mdExportedType    *ptkExportedType  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0a3f4-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="0a3f4-105">Parameters</span></span>  
 `szName`  
 <span data-ttu-id="0a3f4-106">in Der Name des exportierten Typs.</span><span class="sxs-lookup"><span data-stu-id="0a3f4-106">[in] The name of the exported type.</span></span>  
  
 `mdtExportedType`  
 <span data-ttu-id="0a3f4-107">in Das Metadatentoken für die einschließende Klasse des exportierten Typs.</span><span class="sxs-lookup"><span data-stu-id="0a3f4-107">[in] The metadata token for the enclosing class of the exported type.</span></span> <span data-ttu-id="0a3f4-108">Dieser Wert ist `mdExportedTypeNil`, wenn der angeforderte exportierte Typ kein Typ ist.</span><span class="sxs-lookup"><span data-stu-id="0a3f4-108">This value is `mdExportedTypeNil` if the requested exported type is not a nested type.</span></span>  
  
 `ptkExportedType`  
 <span data-ttu-id="0a3f4-109">vorgenommen Ein Zeiger auf das `mdExportedType` Token, das den exportierten Typ darstellt.</span><span class="sxs-lookup"><span data-stu-id="0a3f4-109">[out] A pointer to the `mdExportedType` token that represents the exported type.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="0a3f4-110">Hinweise</span><span class="sxs-lookup"><span data-stu-id="0a3f4-110">Remarks</span></span>  
 <span data-ttu-id="0a3f4-111">Die `FindExportedTypeByName`-Methode verwendet die Standardregeln, die vom Common Language Runtime zum Auflösen von Verweisen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="0a3f4-111">The `FindExportedTypeByName` method uses the standard rules employed by the common language runtime for resolving references.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0a3f4-112">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="0a3f4-112">Requirements</span></span>  
 <span data-ttu-id="0a3f4-113">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0a3f4-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0a3f4-114">**Header:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="0a3f4-114">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="0a3f4-115">**Bibliothek:** Wird als Ressource in Mscoree. dll verwendet.</span><span class="sxs-lookup"><span data-stu-id="0a3f4-115">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="0a3f4-116">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0a3f4-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0a3f4-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="0a3f4-117">See also</span></span>

- [<span data-ttu-id="0a3f4-118">IMetaDataAssemblyImport-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="0a3f4-118">IMetaDataAssemblyImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md)
- [<span data-ttu-id="0a3f4-119">So sucht Common Language Runtime nach Assemblys</span><span class="sxs-lookup"><span data-stu-id="0a3f4-119">How the Runtime Locates Assemblies</span></span>](../../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md)
