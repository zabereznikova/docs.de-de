---
title: IMetaDataAssemblyImport::FindManifestResourceByName-Methode
ms.date: 03/30/2017
api_name:
- IMetaDataAssemblyImport.FindManifestResourceByName
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataAssemblyImport::FindManifestResourceByName
helpviewer_keywords:
- FindManifestResourceByName method [.NET Framework metadata]
- IMetaDataAssemblyImport::FindManifestResourceByName method [.NET Framework metadata]
ms.assetid: 7b72fa11-3866-402b-bdea-2b966b77cfe0
topic_type:
- apiref
ms.openlocfilehash: ef6f7a1a6e86b45acce91792385bc3761dfb4c39
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/27/2020
ms.locfileid: "84009079"
---
# <a name="imetadataassemblyimportfindmanifestresourcebyname-method"></a><span data-ttu-id="e4c02-102">IMetaDataAssemblyImport::FindManifestResourceByName-Methode</span><span class="sxs-lookup"><span data-stu-id="e4c02-102">IMetaDataAssemblyImport::FindManifestResourceByName Method</span></span>
<span data-ttu-id="e4c02-103">Ruft einen Zeiger auf die Manifestressource mit dem angegebenen Namen ab.</span><span class="sxs-lookup"><span data-stu-id="e4c02-103">Gets a pointer to the manifest resource with the specified name.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e4c02-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="e4c02-104">Syntax</span></span>  
  
```cpp
HRESULT FindManifestResourceByName (  
    [in]  LPCWSTR                szName,
    [out] mdManifestResource     *ptkManifestResource  
);
```  
  
## <a name="parameters"></a><span data-ttu-id="e4c02-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="e4c02-105">Parameters</span></span>  
 `szName`  
 <span data-ttu-id="e4c02-106">[in] Der Name der Ressource.</span><span class="sxs-lookup"><span data-stu-id="e4c02-106">[in] The name of the resource.</span></span>  
  
 `ptkManifestResource`  
 <span data-ttu-id="e4c02-107">vorgenommen Das Array, das zum Speichern der `mdManifestResource` Metadatentoken verwendet wird, von denen jedes eine Manifestressource darstellt.</span><span class="sxs-lookup"><span data-stu-id="e4c02-107">[out] The array used to store the `mdManifestResource` metadata tokens, each of which represents a manifest resource.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e4c02-108">Hinweise</span><span class="sxs-lookup"><span data-stu-id="e4c02-108">Remarks</span></span>  
 <span data-ttu-id="e4c02-109">Die- `FindManifestResourceByName` Methode verwendet die Standardregeln, die vom-Common Language Runtime zum Auflösen von Verweisen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="e4c02-109">The `FindManifestResourceByName` method uses the standard rules employed by the common language runtime for resolving references.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e4c02-110">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="e4c02-110">Requirements</span></span>  
 <span data-ttu-id="e4c02-111">**Plattform:** Siehe [System Anforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e4c02-111">**Platform:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e4c02-112">**Header:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="e4c02-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="e4c02-113">**Bibliothek:** Wird als Ressource in Mscoree. dll verwendet.</span><span class="sxs-lookup"><span data-stu-id="e4c02-113">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="e4c02-114">**.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e4c02-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e4c02-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e4c02-115">See also</span></span>

- [<span data-ttu-id="e4c02-116">IMetaDataAssemblyImport-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="e4c02-116">IMetaDataAssemblyImport Interface</span></span>](imetadataassemblyimport-interface.md)
- [<span data-ttu-id="e4c02-117">So sucht Common Language Runtime nach Assemblys</span><span class="sxs-lookup"><span data-stu-id="e4c02-117">How the Runtime Locates Assemblies</span></span>](../../deployment/how-the-runtime-locates-assemblies.md)
