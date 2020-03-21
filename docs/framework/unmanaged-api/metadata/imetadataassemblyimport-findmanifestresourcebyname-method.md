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
ms.openlocfilehash: ae9097725aecd21e910e49a78d81951df39e9b2d
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79177779"
---
# <a name="imetadataassemblyimportfindmanifestresourcebyname-method"></a><span data-ttu-id="fc8f7-102">IMetaDataAssemblyImport::FindManifestResourceByName-Methode</span><span class="sxs-lookup"><span data-stu-id="fc8f7-102">IMetaDataAssemblyImport::FindManifestResourceByName Method</span></span>
<span data-ttu-id="fc8f7-103">Ruft einen Zeiger auf die Manifestressource mit dem angegebenen Namen ab.</span><span class="sxs-lookup"><span data-stu-id="fc8f7-103">Gets a pointer to the manifest resource with the specified name.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fc8f7-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="fc8f7-104">Syntax</span></span>  
  
```cpp
HRESULT FindManifestResourceByName (  
    [in]  LPCWSTR                szName,
    [out] mdManifestResource     *ptkManifestResource  
);
```  
  
## <a name="parameters"></a><span data-ttu-id="fc8f7-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="fc8f7-105">Parameters</span></span>  
 `szName`  
 <span data-ttu-id="fc8f7-106">[in] Der Name der Ressource.</span><span class="sxs-lookup"><span data-stu-id="fc8f7-106">[in] The name of the resource.</span></span>  
  
 `ptkManifestResource`  
 <span data-ttu-id="fc8f7-107">[out] Das Array, das `mdManifestResource` zum Speichern der Metadatentoken verwendet wird, von denen jedes eine Manifestressource darstellt.</span><span class="sxs-lookup"><span data-stu-id="fc8f7-107">[out] The array used to store the `mdManifestResource` metadata tokens, each of which represents a manifest resource.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="fc8f7-108">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="fc8f7-108">Remarks</span></span>  
 <span data-ttu-id="fc8f7-109">Die `FindManifestResourceByName` Methode verwendet die Standardregeln, die von der Common Language Runtime zum Auflösen von Verweisen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="fc8f7-109">The `FindManifestResourceByName` method uses the standard rules employed by the common language runtime for resolving references.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fc8f7-110">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="fc8f7-110">Requirements</span></span>  
 <span data-ttu-id="fc8f7-111">**Plattform:** Siehe [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="fc8f7-111">**Platform:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fc8f7-112">**Kopfzeile:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="fc8f7-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="fc8f7-113">**Bibliothek:** Wird als Ressource in MsCorEE.dll verwendet</span><span class="sxs-lookup"><span data-stu-id="fc8f7-113">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="fc8f7-114">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fc8f7-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fc8f7-115">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="fc8f7-115">See also</span></span>

- [<span data-ttu-id="fc8f7-116">IMetaDataAssemblyImport-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="fc8f7-116">IMetaDataAssemblyImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md)
- [<span data-ttu-id="fc8f7-117">So sucht die Laufzeit Assemblys</span><span class="sxs-lookup"><span data-stu-id="fc8f7-117">How the Runtime Locates Assemblies</span></span>](../../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md)
