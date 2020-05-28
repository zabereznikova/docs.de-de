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
ms.openlocfilehash: ac6de9a16fad6ba9d14f3960ddd28c42c111f254
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/27/2020
ms.locfileid: "84009391"
---
# <a name="imetadataassemblyimportfindexportedtypebyname-method"></a><span data-ttu-id="8ba29-102">IMetaDataAssemblyImport::FindExportedTypeByName-Methode</span><span class="sxs-lookup"><span data-stu-id="8ba29-102">IMetaDataAssemblyImport::FindExportedTypeByName Method</span></span>
<span data-ttu-id="8ba29-103">Ruft bei Angabe des Namens und des einschließenden Typs einen Zeiger auf einen exportierten Typ ab.</span><span class="sxs-lookup"><span data-stu-id="8ba29-103">Gets a pointer to an exported type, given its name and enclosing type.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8ba29-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="8ba29-104">Syntax</span></span>  
  
```cpp  
HRESULT FindExportedTypeByName (  
    [in]  LPCWSTR           szName,
    [in]  mdToken           mdtExportedType,
    [out] mdExportedType    *ptkExportedType  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8ba29-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="8ba29-105">Parameters</span></span>  
 `szName`  
 <span data-ttu-id="8ba29-106">in Der Name des exportierten Typs.</span><span class="sxs-lookup"><span data-stu-id="8ba29-106">[in] The name of the exported type.</span></span>  
  
 `mdtExportedType`  
 <span data-ttu-id="8ba29-107">in Das Metadatentoken für die einschließende Klasse des exportierten Typs.</span><span class="sxs-lookup"><span data-stu-id="8ba29-107">[in] The metadata token for the enclosing class of the exported type.</span></span> <span data-ttu-id="8ba29-108">Dieser Wert ist, wenn es sich `mdExportedTypeNil` bei dem angeforderten exportierten Typ nicht um einen Typ handelt.</span><span class="sxs-lookup"><span data-stu-id="8ba29-108">This value is `mdExportedTypeNil` if the requested exported type is not a nested type.</span></span>  
  
 `ptkExportedType`  
 <span data-ttu-id="8ba29-109">vorgenommen Ein Zeiger auf das `mdExportedType` Token, das den exportierten Typ darstellt.</span><span class="sxs-lookup"><span data-stu-id="8ba29-109">[out] A pointer to the `mdExportedType` token that represents the exported type.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8ba29-110">Hinweise</span><span class="sxs-lookup"><span data-stu-id="8ba29-110">Remarks</span></span>  
 <span data-ttu-id="8ba29-111">Die- `FindExportedTypeByName` Methode verwendet die Standardregeln, die vom-Common Language Runtime zum Auflösen von Verweisen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="8ba29-111">The `FindExportedTypeByName` method uses the standard rules employed by the common language runtime for resolving references.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8ba29-112">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="8ba29-112">Requirements</span></span>  
 <span data-ttu-id="8ba29-113">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8ba29-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8ba29-114">**Header:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="8ba29-114">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="8ba29-115">**Bibliothek:** Wird als Ressource in Mscoree. dll verwendet.</span><span class="sxs-lookup"><span data-stu-id="8ba29-115">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="8ba29-116">**.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8ba29-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8ba29-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="8ba29-117">See also</span></span>

- [<span data-ttu-id="8ba29-118">IMetaDataAssemblyImport-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="8ba29-118">IMetaDataAssemblyImport Interface</span></span>](imetadataassemblyimport-interface.md)
- [<span data-ttu-id="8ba29-119">So sucht Common Language Runtime nach Assemblys</span><span class="sxs-lookup"><span data-stu-id="8ba29-119">How the Runtime Locates Assemblies</span></span>](../../deployment/how-the-runtime-locates-assemblies.md)
