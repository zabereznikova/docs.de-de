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
ms.openlocfilehash: 74111a175b0decbc1beef7c8df5ade59d31d845b
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/27/2020
ms.locfileid: "84009144"
---
# <a name="imetadataassemblyemitsetmanifestresourceprops-method"></a><span data-ttu-id="5e8a5-102">IMetaDataAssemblyEmit::SetManifestResourceProps-Methode</span><span class="sxs-lookup"><span data-stu-id="5e8a5-102">IMetaDataAssemblyEmit::SetManifestResourceProps Method</span></span>
<span data-ttu-id="5e8a5-103">Ändert die angegebene `ManifestResource`-Metadatenstruktur.</span><span class="sxs-lookup"><span data-stu-id="5e8a5-103">Modifies the specified `ManifestResource` metadata structure.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5e8a5-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="5e8a5-104">Syntax</span></span>  
  
```cpp  
HRESULT SetManifestResourceProps (  
    [in] mdManifestResource  mr,  
    [in] mdToken             tkImplementation,
    [in] DWORD               dwOffset,  
    [in] DWORD               dwResourceFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5e8a5-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="5e8a5-105">Parameters</span></span>  
 `mr`  
 <span data-ttu-id="5e8a5-106">in Das Token, das die `ManifestResource` zu ändernde Metadatenstruktur angibt.</span><span class="sxs-lookup"><span data-stu-id="5e8a5-106">[in] The token that specifies the `ManifestResource` metadata structure to be modified.</span></span>  
  
 `tkImplementation`  
 <span data-ttu-id="5e8a5-107">in Das Token vom Typ `File` oder, `AssemblyRef` das dem Ressourcenanbieter zugeordnet wird.</span><span class="sxs-lookup"><span data-stu-id="5e8a5-107">[in] The token, of type `File` or `AssemblyRef`, that maps to the resource provider.</span></span>  
  
 `dwOffset`  
 <span data-ttu-id="5e8a5-108">in Der Offset zum Anfang der Ressource innerhalb der Datei.</span><span class="sxs-lookup"><span data-stu-id="5e8a5-108">[in] The offset to the beginning of the resource within the file.</span></span>  
  
 `dwResourceFlags`  
 <span data-ttu-id="5e8a5-109">in Eine bitweise Kombination von Flagwerten, die die Attribute der Ressource angeben.</span><span class="sxs-lookup"><span data-stu-id="5e8a5-109">[in] A bitwise combination of flag values that specify the attributes of the resource.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5e8a5-110">Hinweise</span><span class="sxs-lookup"><span data-stu-id="5e8a5-110">Remarks</span></span>  
 <span data-ttu-id="5e8a5-111">Verwenden Sie zum Erstellen einer `ManifestResource` Metadatenstruktur die [IMetaDataAssemblyEmit::D efinemanifestresource](imetadataassemblyemit-definemanifestresource-method.md) -Methode.</span><span class="sxs-lookup"><span data-stu-id="5e8a5-111">To create a `ManifestResource` metadata structure, use the [IMetaDataAssemblyEmit::DefineManifestResource](imetadataassemblyemit-definemanifestresource-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5e8a5-112">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="5e8a5-112">Requirements</span></span>  
 <span data-ttu-id="5e8a5-113">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5e8a5-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5e8a5-114">**Header:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="5e8a5-114">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="5e8a5-115">**Bibliothek:** Wird als Ressource in Mscoree. dll verwendet.</span><span class="sxs-lookup"><span data-stu-id="5e8a5-115">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="5e8a5-116">**.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5e8a5-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5e8a5-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="5e8a5-117">See also</span></span>

- [<span data-ttu-id="5e8a5-118">IMetaDataAssemblyEmit-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="5e8a5-118">IMetaDataAssemblyEmit Interface</span></span>](imetadataassemblyemit-interface.md)
