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
ms.openlocfilehash: f6b5e12df60663b75e10b04eaa008a75d720d753
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/23/2019
ms.locfileid: "74434433"
---
# <a name="imetadataassemblyemitsetmanifestresourceprops-method"></a><span data-ttu-id="5ae0d-102">IMetaDataAssemblyEmit::SetManifestResourceProps-Methode</span><span class="sxs-lookup"><span data-stu-id="5ae0d-102">IMetaDataAssemblyEmit::SetManifestResourceProps Method</span></span>
<span data-ttu-id="5ae0d-103">Ändert die angegebene `ManifestResource`-Metadatenstruktur.</span><span class="sxs-lookup"><span data-stu-id="5ae0d-103">Modifies the specified `ManifestResource` metadata structure.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5ae0d-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="5ae0d-104">Syntax</span></span>  
  
```cpp  
HRESULT SetManifestResourceProps (  
    [in] mdManifestResource  mr,  
    [in] mdToken             tkImplementation,   
    [in] DWORD               dwOffset,  
    [in] DWORD               dwResourceFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5ae0d-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="5ae0d-105">Parameters</span></span>  
 `mr`  
 <span data-ttu-id="5ae0d-106">[in] The token that specifies the `ManifestResource` metadata structure to be modified.</span><span class="sxs-lookup"><span data-stu-id="5ae0d-106">[in] The token that specifies the `ManifestResource` metadata structure to be modified.</span></span>  
  
 `tkImplementation`  
 <span data-ttu-id="5ae0d-107">[in] The token, of type `File` or `AssemblyRef`, that maps to the resource provider.</span><span class="sxs-lookup"><span data-stu-id="5ae0d-107">[in] The token, of type `File` or `AssemblyRef`, that maps to the resource provider.</span></span>  
  
 `dwOffset`  
 <span data-ttu-id="5ae0d-108">[in] The offset to the beginning of the resource within the file.</span><span class="sxs-lookup"><span data-stu-id="5ae0d-108">[in] The offset to the beginning of the resource within the file.</span></span>  
  
 `dwResourceFlags`  
 <span data-ttu-id="5ae0d-109">[in] A bitwise combination of flag values that specify the attributes of the resource.</span><span class="sxs-lookup"><span data-stu-id="5ae0d-109">[in] A bitwise combination of flag values that specify the attributes of the resource.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5ae0d-110">Hinweise</span><span class="sxs-lookup"><span data-stu-id="5ae0d-110">Remarks</span></span>  
 <span data-ttu-id="5ae0d-111">To create a `ManifestResource` metadata structure, use the [IMetaDataAssemblyEmit::DefineManifestResource](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-definemanifestresource-method.md) method.</span><span class="sxs-lookup"><span data-stu-id="5ae0d-111">To create a `ManifestResource` metadata structure, use the [IMetaDataAssemblyEmit::DefineManifestResource](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-definemanifestresource-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5ae0d-112">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="5ae0d-112">Requirements</span></span>  
 <span data-ttu-id="5ae0d-113">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5ae0d-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5ae0d-114">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="5ae0d-114">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="5ae0d-115">**Library:** Used as a resource in MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="5ae0d-115">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="5ae0d-116">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5ae0d-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5ae0d-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="5ae0d-117">See also</span></span>

- [<span data-ttu-id="5ae0d-118">IMetaDataAssemblyEmit-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="5ae0d-118">IMetaDataAssemblyEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md)
