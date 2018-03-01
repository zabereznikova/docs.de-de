---
title: IMetaDataAssemblyEmit::SetExportedTypeProps-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
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
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: bebcf827488912431cb0f94f5527d3445fc41125
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="imetadataassemblyemitsetexportedtypeprops-method"></a><span data-ttu-id="688f8-102">IMetaDataAssemblyEmit::SetExportedTypeProps-Methode</span><span class="sxs-lookup"><span data-stu-id="688f8-102">IMetaDataAssemblyEmit::SetExportedTypeProps Method</span></span>
<span data-ttu-id="688f8-103">Ändert die angegebene `ExportedType`-Metadatenstruktur.</span><span class="sxs-lookup"><span data-stu-id="688f8-103">Modifies the specified `ExportedType` metadata structure.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="688f8-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="688f8-104">Syntax</span></span>  
  
```  
HRESULT SetExportedTypeProps (  
    [in] mdExportedType   ct,   
    [in] mdToken          tkImplementation,  
    [in] mdTypeDef        tkTypeDef,  
    [in] DWORD            dwExportedTypeFlags  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="688f8-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="688f8-105">Parameters</span></span>  
 `ct`  
 <span data-ttu-id="688f8-106">[in] Das Metadatentoken, der angibt, die `ExportedType` Metadatenstruktur geändert werden.</span><span class="sxs-lookup"><span data-stu-id="688f8-106">[in] The metadata token that specifies the `ExportedType` metadata structure to be modified.</span></span>  
  
 `tkImplementation`  
 <span data-ttu-id="688f8-107">[in] Das Token des Typs `File`, `AssemblyRef`, oder `ExportedType`, der angibt, wie dieser Typ implementiert wird.</span><span class="sxs-lookup"><span data-stu-id="688f8-107">[in] The token, of type `File`, `AssemblyRef`, or `ExportedType`, that specifies how this type is implemented.</span></span>  
  
 `tkTypeDef`  
 <span data-ttu-id="688f8-108">[in] Die `TypeDef` Token auf, die in der Codedatei verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="688f8-108">[in] The `TypeDef` token referenced in the code file.</span></span>  
  
 `dwExportedTypeFlags`  
 <span data-ttu-id="688f8-109">[in] Eine bitweise Kombination von Werten, die Attribute des Typs angeben.</span><span class="sxs-lookup"><span data-stu-id="688f8-109">[in] A bitwise combination of values that specify attributes of the type.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="688f8-110">Hinweise</span><span class="sxs-lookup"><span data-stu-id="688f8-110">Remarks</span></span>  
 <span data-ttu-id="688f8-111">Zum Erstellen einer `ExportedType` Metadatenstruktur, verwenden die [IMetaDataAssemblyEmit:: DefineExportedType](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-defineexportedtype-method.md) Methode.</span><span class="sxs-lookup"><span data-stu-id="688f8-111">To create an `ExportedType` metadata structure, use the [IMetaDataAssemblyEmit::DefineExportedType](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-defineexportedtype-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="688f8-112">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="688f8-112">Requirements</span></span>  
 <span data-ttu-id="688f8-113">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="688f8-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="688f8-114">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="688f8-114">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="688f8-115">**Bibliothek:** als Ressource in MsCorEE.dll verwendet</span><span class="sxs-lookup"><span data-stu-id="688f8-115">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="688f8-116">**.NET Framework-Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="688f8-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="688f8-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="688f8-117">See Also</span></span>  
 [<span data-ttu-id="688f8-118">IMetaDataAssemblyEmit-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="688f8-118">IMetaDataAssemblyEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md)
