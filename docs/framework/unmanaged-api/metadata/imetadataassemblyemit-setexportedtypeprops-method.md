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
ms.openlocfilehash: dd1d6f1da6e49837eebd9356500f403c199b011b
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79177850"
---
# <a name="imetadataassemblyemitsetexportedtypeprops-method"></a><span data-ttu-id="3ff78-102">IMetaDataAssemblyEmit::SetExportedTypeProps-Methode</span><span class="sxs-lookup"><span data-stu-id="3ff78-102">IMetaDataAssemblyEmit::SetExportedTypeProps Method</span></span>
<span data-ttu-id="3ff78-103">Ändert die angegebene `ExportedType`-Metadatenstruktur.</span><span class="sxs-lookup"><span data-stu-id="3ff78-103">Modifies the specified `ExportedType` metadata structure.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3ff78-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="3ff78-104">Syntax</span></span>  
  
```cpp  
HRESULT SetExportedTypeProps (  
    [in] mdExportedType   ct,
    [in] mdToken          tkImplementation,  
    [in] mdTypeDef        tkTypeDef,  
    [in] DWORD            dwExportedTypeFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3ff78-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="3ff78-105">Parameters</span></span>  
 `ct`  
 <span data-ttu-id="3ff78-106">[in] Das Metadatentoken, das `ExportedType` die zu ändernde Metadatenstruktur angibt.</span><span class="sxs-lookup"><span data-stu-id="3ff78-106">[in] The metadata token that specifies the `ExportedType` metadata structure to be modified.</span></span>  
  
 `tkImplementation`  
 <span data-ttu-id="3ff78-107">[in] Das Token vom `File` `AssemblyRef`Typ `ExportedType`, oder , das angibt, wie dieser Typ implementiert wird.</span><span class="sxs-lookup"><span data-stu-id="3ff78-107">[in] The token, of type `File`, `AssemblyRef`, or `ExportedType`, that specifies how this type is implemented.</span></span>  
  
 `tkTypeDef`  
 <span data-ttu-id="3ff78-108">[in] Auf `TypeDef` das Token, auf das in der Codedatei verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="3ff78-108">[in] The `TypeDef` token referenced in the code file.</span></span>  
  
 `dwExportedTypeFlags`  
 <span data-ttu-id="3ff78-109">[in] Eine bitweise Kombination von Werten, die Attribute des Typs angeben.</span><span class="sxs-lookup"><span data-stu-id="3ff78-109">[in] A bitwise combination of values that specify attributes of the type.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3ff78-110">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="3ff78-110">Remarks</span></span>  
 <span data-ttu-id="3ff78-111">Um eine `ExportedType` Metadatenstruktur zu erstellen, verwenden Sie die [IMetaDataAssemblyEmit::DefineExportedType-Methode.](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-defineexportedtype-method.md)</span><span class="sxs-lookup"><span data-stu-id="3ff78-111">To create an `ExportedType` metadata structure, use the [IMetaDataAssemblyEmit::DefineExportedType](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-defineexportedtype-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3ff78-112">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="3ff78-112">Requirements</span></span>  
 <span data-ttu-id="3ff78-113">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3ff78-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3ff78-114">**Kopfzeile:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="3ff78-114">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="3ff78-115">**Bibliothek:** Wird als Ressource in MsCorEE.dll verwendet</span><span class="sxs-lookup"><span data-stu-id="3ff78-115">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="3ff78-116">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3ff78-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3ff78-117">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="3ff78-117">See also</span></span>

- [<span data-ttu-id="3ff78-118">IMetaDataAssemblyEmit-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="3ff78-118">IMetaDataAssemblyEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md)
