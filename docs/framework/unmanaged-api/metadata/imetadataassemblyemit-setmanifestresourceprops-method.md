---
title: IMetaDataAssemblyEmit::SetManifestResourceProps-Methode
ms.date: 03/30/2017
api_name:
- IMetaDataAssemblyEmit.SetManifestResourceProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataAssemblyEmit::SetManifestResourceProps
helpviewer_keywords:
- SetManifestResourceProps method [.NET Framework metadata]
- IMetaDataAssemblyEmit::SetManifestResourceProps method [.NET Framework metadata]
ms.assetid: ef77efd1-849c-4e51-ba92-7ee3d2bf0339
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: c6fbc3f41e95730e93bd907762dd8cd4205037c8
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59187303"
---
# <a name="imetadataassemblyemitsetmanifestresourceprops-method"></a><span data-ttu-id="a73a3-102">IMetaDataAssemblyEmit::SetManifestResourceProps-Methode</span><span class="sxs-lookup"><span data-stu-id="a73a3-102">IMetaDataAssemblyEmit::SetManifestResourceProps Method</span></span>
<span data-ttu-id="a73a3-103">Ändert die angegebene `ManifestResource`-Metadatenstruktur.</span><span class="sxs-lookup"><span data-stu-id="a73a3-103">Modifies the specified `ManifestResource` metadata structure.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a73a3-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="a73a3-104">Syntax</span></span>  
  
```  
HRESULT SetManifestResourceProps (  
    [in] mdManifestResource  mr,  
    [in] mdToken             tkImplementation,   
    [in] DWORD               dwOffset,  
    [in] DWORD               dwResourceFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a73a3-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="a73a3-105">Parameters</span></span>  
 `mr`  
 <span data-ttu-id="a73a3-106">[in] Das Token, der angibt, die `ManifestResource` Metadatenstruktur geändert werden.</span><span class="sxs-lookup"><span data-stu-id="a73a3-106">[in] The token that specifies the `ManifestResource` metadata structure to be modified.</span></span>  
  
 `tkImplementation`  
 <span data-ttu-id="a73a3-107">[in] Das Token des Typs `File` oder `AssemblyRef`, der dem Ressourcenanbieter zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="a73a3-107">[in] The token, of type `File` or `AssemblyRef`, that maps to the resource provider.</span></span>  
  
 `dwOffset`  
 <span data-ttu-id="a73a3-108">[in] Der Offset auf den Anfang der Ressource in der Datei.</span><span class="sxs-lookup"><span data-stu-id="a73a3-108">[in] The offset to the beginning of the resource within the file.</span></span>  
  
 `dwResourceFlags`  
 <span data-ttu-id="a73a3-109">[in] Eine bitweise Kombination der Flagwerte, die die Attribute der Ressource angeben.</span><span class="sxs-lookup"><span data-stu-id="a73a3-109">[in] A bitwise combination of flag values that specify the attributes of the resource.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a73a3-110">Hinweise</span><span class="sxs-lookup"><span data-stu-id="a73a3-110">Remarks</span></span>  
 <span data-ttu-id="a73a3-111">Zum Erstellen einer `ManifestResource` Metadatenstruktur, verwenden die [IMetaDataAssemblyEmit:: DefineManifestResource](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-definemanifestresource-method.md) Methode.</span><span class="sxs-lookup"><span data-stu-id="a73a3-111">To create a `ManifestResource` metadata structure, use the [IMetaDataAssemblyEmit::DefineManifestResource](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-definemanifestresource-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a73a3-112">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="a73a3-112">Requirements</span></span>  
 <span data-ttu-id="a73a3-113">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a73a3-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a73a3-114">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="a73a3-114">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="a73a3-115">**Bibliothek:** Als Ressource in MsCorEE.dll verwendet</span><span class="sxs-lookup"><span data-stu-id="a73a3-115">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 **<span data-ttu-id="a73a3-116">.NET Framework-Versionen:</span><span class="sxs-lookup"><span data-stu-id="a73a3-116">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="a73a3-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a73a3-117">See also</span></span>

- [<span data-ttu-id="a73a3-118">IMetaDataAssemblyEmit-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="a73a3-118">IMetaDataAssemblyEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md)
