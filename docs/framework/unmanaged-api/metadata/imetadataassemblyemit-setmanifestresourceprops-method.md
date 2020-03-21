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
ms.openlocfilehash: 9370b27fd385b0223b354365d64aa57048f4ec69
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79177844"
---
# <a name="imetadataassemblyemitsetmanifestresourceprops-method"></a><span data-ttu-id="28d09-102">IMetaDataAssemblyEmit::SetManifestResourceProps-Methode</span><span class="sxs-lookup"><span data-stu-id="28d09-102">IMetaDataAssemblyEmit::SetManifestResourceProps Method</span></span>
<span data-ttu-id="28d09-103">Ändert die angegebene `ManifestResource`-Metadatenstruktur.</span><span class="sxs-lookup"><span data-stu-id="28d09-103">Modifies the specified `ManifestResource` metadata structure.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="28d09-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="28d09-104">Syntax</span></span>  
  
```cpp  
HRESULT SetManifestResourceProps (  
    [in] mdManifestResource  mr,  
    [in] mdToken             tkImplementation,
    [in] DWORD               dwOffset,  
    [in] DWORD               dwResourceFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="28d09-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="28d09-105">Parameters</span></span>  
 `mr`  
 <span data-ttu-id="28d09-106">[in] Das Token, das `ManifestResource` die zu ändernde Metadatenstruktur angibt.</span><span class="sxs-lookup"><span data-stu-id="28d09-106">[in] The token that specifies the `ManifestResource` metadata structure to be modified.</span></span>  
  
 `tkImplementation`  
 <span data-ttu-id="28d09-107">[in] Das Token vom `File` `AssemblyRef`Typ oder , das dem Ressourcenanbieter zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="28d09-107">[in] The token, of type `File` or `AssemblyRef`, that maps to the resource provider.</span></span>  
  
 `dwOffset`  
 <span data-ttu-id="28d09-108">[in] Der Offset zum Anfang der Ressource in der Datei.</span><span class="sxs-lookup"><span data-stu-id="28d09-108">[in] The offset to the beginning of the resource within the file.</span></span>  
  
 `dwResourceFlags`  
 <span data-ttu-id="28d09-109">[in] Eine bitweise Kombination von Flagwerten, die die Attribute der Ressource angeben.</span><span class="sxs-lookup"><span data-stu-id="28d09-109">[in] A bitwise combination of flag values that specify the attributes of the resource.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="28d09-110">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="28d09-110">Remarks</span></span>  
 <span data-ttu-id="28d09-111">Um eine `ManifestResource` Metadatenstruktur zu erstellen, verwenden Sie die [IMetaDataAssemblyEmit::DefineManifestResource-Methode.](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-definemanifestresource-method.md)</span><span class="sxs-lookup"><span data-stu-id="28d09-111">To create a `ManifestResource` metadata structure, use the [IMetaDataAssemblyEmit::DefineManifestResource](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-definemanifestresource-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="28d09-112">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="28d09-112">Requirements</span></span>  
 <span data-ttu-id="28d09-113">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="28d09-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="28d09-114">**Kopfzeile:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="28d09-114">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="28d09-115">**Bibliothek:** Wird als Ressource in MsCorEE.dll verwendet</span><span class="sxs-lookup"><span data-stu-id="28d09-115">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="28d09-116">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="28d09-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="28d09-117">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="28d09-117">See also</span></span>

- [<span data-ttu-id="28d09-118">IMetaDataAssemblyEmit-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="28d09-118">IMetaDataAssemblyEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md)
