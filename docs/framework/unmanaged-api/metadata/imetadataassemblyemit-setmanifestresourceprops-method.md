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
ms.openlocfilehash: c46a3bc34ba7efa760e50416e9a6c39779727813
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95708919"
---
# <a name="imetadataassemblyemitsetmanifestresourceprops-method"></a><span data-ttu-id="218a2-102">IMetaDataAssemblyEmit::SetManifestResourceProps-Methode</span><span class="sxs-lookup"><span data-stu-id="218a2-102">IMetaDataAssemblyEmit::SetManifestResourceProps Method</span></span>

<span data-ttu-id="218a2-103">Ändert die angegebene `ManifestResource`-Metadatenstruktur.</span><span class="sxs-lookup"><span data-stu-id="218a2-103">Modifies the specified `ManifestResource` metadata structure.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="218a2-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="218a2-104">Syntax</span></span>  
  
```cpp  
HRESULT SetManifestResourceProps (  
    [in] mdManifestResource  mr,  
    [in] mdToken             tkImplementation,
    [in] DWORD               dwOffset,  
    [in] DWORD               dwResourceFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="218a2-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="218a2-105">Parameters</span></span>  

 `mr`  
 <span data-ttu-id="218a2-106">in Das Token, das die `ManifestResource` zu ändernde Metadatenstruktur angibt.</span><span class="sxs-lookup"><span data-stu-id="218a2-106">[in] The token that specifies the `ManifestResource` metadata structure to be modified.</span></span>  
  
 `tkImplementation`  
 <span data-ttu-id="218a2-107">in Das Token vom Typ `File` oder, `AssemblyRef` das dem Ressourcenanbieter zugeordnet wird.</span><span class="sxs-lookup"><span data-stu-id="218a2-107">[in] The token, of type `File` or `AssemblyRef`, that maps to the resource provider.</span></span>  
  
 `dwOffset`  
 <span data-ttu-id="218a2-108">in Der Offset zum Anfang der Ressource innerhalb der Datei.</span><span class="sxs-lookup"><span data-stu-id="218a2-108">[in] The offset to the beginning of the resource within the file.</span></span>  
  
 `dwResourceFlags`  
 <span data-ttu-id="218a2-109">in Eine bitweise Kombination von Flagwerten, die die Attribute der Ressource angeben.</span><span class="sxs-lookup"><span data-stu-id="218a2-109">[in] A bitwise combination of flag values that specify the attributes of the resource.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="218a2-110">Hinweise</span><span class="sxs-lookup"><span data-stu-id="218a2-110">Remarks</span></span>  

 <span data-ttu-id="218a2-111">Verwenden Sie zum Erstellen einer `ManifestResource` Metadatenstruktur die [IMetaDataAssemblyEmit::D efinemanifestresource](imetadataassemblyemit-definemanifestresource-method.md) -Methode.</span><span class="sxs-lookup"><span data-stu-id="218a2-111">To create a `ManifestResource` metadata structure, use the [IMetaDataAssemblyEmit::DefineManifestResource](imetadataassemblyemit-definemanifestresource-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="218a2-112">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="218a2-112">Requirements</span></span>  

 <span data-ttu-id="218a2-113">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="218a2-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="218a2-114">**Header:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="218a2-114">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="218a2-115">**Bibliothek:** Wird als Ressource in MsCorEE.dll verwendet.</span><span class="sxs-lookup"><span data-stu-id="218a2-115">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="218a2-116">**.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="218a2-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="218a2-117">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="218a2-117">See also</span></span>

- [<span data-ttu-id="218a2-118">IMetaDataAssemblyEmit-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="218a2-118">IMetaDataAssemblyEmit Interface</span></span>](imetadataassemblyemit-interface.md)
