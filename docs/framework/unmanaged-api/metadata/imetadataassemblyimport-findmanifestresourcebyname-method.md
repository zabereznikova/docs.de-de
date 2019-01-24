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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: b05c9a75bf870dd3b2316d2df7c50932b26894f3
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54702742"
---
# <a name="imetadataassemblyimportfindmanifestresourcebyname-method"></a><span data-ttu-id="5ca75-102">IMetaDataAssemblyImport::FindManifestResourceByName-Methode</span><span class="sxs-lookup"><span data-stu-id="5ca75-102">IMetaDataAssemblyImport::FindManifestResourceByName Method</span></span>
<span data-ttu-id="5ca75-103">Ruft einen Zeiger auf die Manifestressource mit dem angegebenen Namen ab.</span><span class="sxs-lookup"><span data-stu-id="5ca75-103">Gets a pointer to the manifest resource with the specified name.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5ca75-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="5ca75-104">Syntax</span></span>  
  
```  
HRESULT FindManifestResourceByName (  
    [in]  LPCWSTR                szName,   
    [out] mdManifestResource     *ptkManifestResource  
);   
```  
  
#### <a name="parameters"></a><span data-ttu-id="5ca75-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="5ca75-105">Parameters</span></span>  
 `szName`  
 <span data-ttu-id="5ca75-106">[in] Der Name der Ressource.</span><span class="sxs-lookup"><span data-stu-id="5ca75-106">[in] The name of the resource.</span></span>  
  
 `ptkManifestResource`  
 <span data-ttu-id="5ca75-107">[out] Das Array zum Speichern der `mdManifestResource` Metadatentoken verwendet, von denen jede eine Manifestressource darstellt.</span><span class="sxs-lookup"><span data-stu-id="5ca75-107">[out] The array used to store the `mdManifestResource` metadata tokens, each of which represents a manifest resource.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5ca75-108">Hinweise</span><span class="sxs-lookup"><span data-stu-id="5ca75-108">Remarks</span></span>  
 <span data-ttu-id="5ca75-109">Die `FindManifestResourceByName` -Methode verwendet die Standardregeln, die von der common Language Runtime zum Auflösen von verweisen.</span><span class="sxs-lookup"><span data-stu-id="5ca75-109">The `FindManifestResourceByName` method uses the standard rules employed by the common language runtime for resolving references.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5ca75-110">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="5ca75-110">Requirements</span></span>  
 <span data-ttu-id="5ca75-111">**Plattform:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5ca75-111">**Platform:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5ca75-112">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="5ca75-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="5ca75-113">**Bibliothek:** Als Ressource in MsCorEE.dll verwendet</span><span class="sxs-lookup"><span data-stu-id="5ca75-113">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="5ca75-114">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5ca75-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5ca75-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="5ca75-115">See also</span></span>
- [<span data-ttu-id="5ca75-116">IMetaDataAssemblyImport-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="5ca75-116">IMetaDataAssemblyImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md)
- [<span data-ttu-id="5ca75-117">So sucht Common Language Runtime nach Assemblys</span><span class="sxs-lookup"><span data-stu-id="5ca75-117">How the Runtime Locates Assemblies</span></span>](../../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md)
