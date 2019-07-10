---
title: IMetaDataAssemblyEmit::SetExportedTypeProps-Methode
ms.date: 03/30/2017
api_name:
- IMetaDataAssemblyEmit.SetExportedTypeProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataAssemblyEmit::SetExportedTypeProps
helpviewer_keywords:
- SetExportedTypeProps method [.NET Framework metadata]
- IMetaDataAssemblyEmit::SetExportedTypeProps method [.NET Framework metadata]
ms.assetid: 1c090153-fd5f-46c7-9cff-39a78d992c8f
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: e4be840760782789aa91e5519f60374aca2e3941
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67775267"
---
# <a name="imetadataassemblyemitsetexportedtypeprops-method"></a><span data-ttu-id="e6994-102">IMetaDataAssemblyEmit::SetExportedTypeProps-Methode</span><span class="sxs-lookup"><span data-stu-id="e6994-102">IMetaDataAssemblyEmit::SetExportedTypeProps Method</span></span>
<span data-ttu-id="e6994-103">Ändert die angegebene `ExportedType`-Metadatenstruktur.</span><span class="sxs-lookup"><span data-stu-id="e6994-103">Modifies the specified `ExportedType` metadata structure.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e6994-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="e6994-104">Syntax</span></span>  
  
```cpp  
HRESULT SetExportedTypeProps (  
    [in] mdExportedType   ct,   
    [in] mdToken          tkImplementation,  
    [in] mdTypeDef        tkTypeDef,  
    [in] DWORD            dwExportedTypeFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e6994-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="e6994-105">Parameters</span></span>  
 `ct`  
 <span data-ttu-id="e6994-106">[in] Das Metadatentoken, der angibt, die `ExportedType` Metadatenstruktur geändert werden.</span><span class="sxs-lookup"><span data-stu-id="e6994-106">[in] The metadata token that specifies the `ExportedType` metadata structure to be modified.</span></span>  
  
 `tkImplementation`  
 <span data-ttu-id="e6994-107">[in] Das Token des Typs `File`, `AssemblyRef`, oder `ExportedType`, der angibt, wie dieser Typ implementiert wird.</span><span class="sxs-lookup"><span data-stu-id="e6994-107">[in] The token, of type `File`, `AssemblyRef`, or `ExportedType`, that specifies how this type is implemented.</span></span>  
  
 `tkTypeDef`  
 <span data-ttu-id="e6994-108">[in] Die `TypeDef` Token verwiesen wird, in der Codedatei zu verlassen.</span><span class="sxs-lookup"><span data-stu-id="e6994-108">[in] The `TypeDef` token referenced in the code file.</span></span>  
  
 `dwExportedTypeFlags`  
 <span data-ttu-id="e6994-109">[in] Eine bitweise Kombination der Werte, die Attribute des Typs angeben.</span><span class="sxs-lookup"><span data-stu-id="e6994-109">[in] A bitwise combination of values that specify attributes of the type.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e6994-110">Hinweise</span><span class="sxs-lookup"><span data-stu-id="e6994-110">Remarks</span></span>  
 <span data-ttu-id="e6994-111">Zum Erstellen einer `ExportedType` Metadatenstruktur, verwenden die [IMetaDataAssemblyEmit:: DefineExportedType](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-defineexportedtype-method.md) Methode.</span><span class="sxs-lookup"><span data-stu-id="e6994-111">To create an `ExportedType` metadata structure, use the [IMetaDataAssemblyEmit::DefineExportedType](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-defineexportedtype-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e6994-112">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="e6994-112">Requirements</span></span>  
 <span data-ttu-id="e6994-113">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e6994-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e6994-114">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="e6994-114">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="e6994-115">**Bibliothek:** Als Ressource in MsCorEE.dll verwendet</span><span class="sxs-lookup"><span data-stu-id="e6994-115">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="e6994-116">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e6994-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e6994-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e6994-117">See also</span></span>

- [<span data-ttu-id="e6994-118">IMetaDataAssemblyEmit-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="e6994-118">IMetaDataAssemblyEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md)
