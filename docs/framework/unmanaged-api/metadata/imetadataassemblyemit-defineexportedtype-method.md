---
title: IMetaDataAssemblyEmit::DefineExportedType-Methode
ms.date: 03/30/2017
api_name:
- IMetaDataAssemblyEmit.DefineExportedType
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataAssemblyEmit::DefineExportedType
helpviewer_keywords:
- IMetaDataAssemblyEmit::DefineExportedType method [.NET Framework metadata]
- DefineExportedType method [.NET Framework metadata]
ms.assetid: fad01d7a-3178-4c8c-9f0a-4641e3701c9b
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: a2eb894a8bac702c30826d1e965c91cae9b259ee
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33448559"
---
# <a name="imetadataassemblyemitdefineexportedtype-method"></a><span data-ttu-id="c675b-102">IMetaDataAssemblyEmit::DefineExportedType-Methode</span><span class="sxs-lookup"><span data-stu-id="c675b-102">IMetaDataAssemblyEmit::DefineExportedType Method</span></span>
<span data-ttu-id="c675b-103">Erstellt eine `ExportedType`-Struktur, die Metadaten für den angegebenen exportierten Typ enthält, und gibt das zugeordnete Metadatentoken zurück.</span><span class="sxs-lookup"><span data-stu-id="c675b-103">Creates an `ExportedType` structure containing metadata for the specified exported type, and returns the associated metadata token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c675b-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="c675b-104">Syntax</span></span>  
  
```  
HRESULT DefineExportedType (  
    [in]  LPCWSTR             szName,  
    [in]  mdToken             tkImplementation,   
    [in]  mdTypeDef           tkTypeDef,  
    [in]  DWORD               dwExportedTypeFlags,  
    [out] mdExportedType      *pmdct  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="c675b-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="c675b-105">Parameters</span></span>  
 `szName`  
 <span data-ttu-id="c675b-106">[in] Der Name des Typs, der exportiert werden.</span><span class="sxs-lookup"><span data-stu-id="c675b-106">[in] The name of type to be exported.</span></span> <span data-ttu-id="c675b-107">Für Version 1.1 von der common Language Runtime den Namen der exportierte Typ muss genau den angegebenen Namen entsprechen den `TypeDef` für den Typ.</span><span class="sxs-lookup"><span data-stu-id="c675b-107">For version 1.1 of the common language runtime, the name of the exported type must exactly match the name given in the `TypeDef` for the type.</span></span>  
  
 `tkImplementation`  
 <span data-ttu-id="c675b-108">[in] Ein Token, die angeben, in denen der exportierte Typ implementiert wird.</span><span class="sxs-lookup"><span data-stu-id="c675b-108">[in] A token specifying where the exported type is implemented.</span></span> <span data-ttu-id="c675b-109">Die gültigen Werte und ihre zugeordneten Bedeutung sind:</span><span class="sxs-lookup"><span data-stu-id="c675b-109">The valid values and their associated meanings are:</span></span>  
  
-   <span data-ttu-id="c675b-110">`mdFile` Der Typ wird in eine andere Datei in dieser Assembly implementiert.</span><span class="sxs-lookup"><span data-stu-id="c675b-110">`mdFile` The type is implemented in a different file within this assembly.</span></span>  
  
-   <span data-ttu-id="c675b-111">`mdAssemblyRef` Der Typ wird in einer anderen Assembly implementiert.</span><span class="sxs-lookup"><span data-stu-id="c675b-111">`mdAssemblyRef` The type is implemented in a different assembly.</span></span>  
  
-   <span data-ttu-id="c675b-112">`mdExportedTYpe` Der Typ wird in einem anderen Typ geschachtelt.</span><span class="sxs-lookup"><span data-stu-id="c675b-112">`mdExportedTYpe` The type is nested within some other type.</span></span>  
  
-   <span data-ttu-id="c675b-113">`mdFileNil` Der Typ befindet sich in der gleichen Datei wie das Manifest und kein geschachtelter Typ ist.</span><span class="sxs-lookup"><span data-stu-id="c675b-113">`mdFileNil` The type is in the same file as the manifest and is not a nested type.</span></span>  
  
 `tkTypeDef`  
 <span data-ttu-id="c675b-114">[in] Ein Token für die Metadaten, die der den zu exportierenden angibt.</span><span class="sxs-lookup"><span data-stu-id="c675b-114">[in] A token to the metadata that specifies the type to be exported.</span></span> <span data-ttu-id="c675b-115">Dieser Wert eingegeben wird, der `TypeDef` Tabelle in der Datei, die den Typ implementiert und ist nur relevant, wenn diese Datei in dieser Assembly ist.</span><span class="sxs-lookup"><span data-stu-id="c675b-115">This value is entered in the `TypeDef` table in the file that implements the type and is relevant only if that file is in this assembly.</span></span>  
  
 `dwExportedTypeFlags`  
 <span data-ttu-id="c675b-116">[in] Eine bitweise Kombination von [CorTypeAttr](../../../../docs/framework/unmanaged-api/metadata/cortypeattr-enumeration.md) Enumerationswerte, der die eigenschafteneinstellungen für den exportierten Typ definieren.</span><span class="sxs-lookup"><span data-stu-id="c675b-116">[in] A bitwise combination of [CorTypeAttr](../../../../docs/framework/unmanaged-api/metadata/cortypeattr-enumeration.md) enumeration values that define the property settings for the exported type.</span></span>  
  
 `pmdct`  
 <span data-ttu-id="c675b-117">[out] Ein Zeiger auf die zurückgegebenen Metadaten-Token, das den exportierten Typ angibt.</span><span class="sxs-lookup"><span data-stu-id="c675b-117">[out] A pointer to the returned metadata token that indicates the exported type.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c675b-118">Hinweise</span><span class="sxs-lookup"><span data-stu-id="c675b-118">Remarks</span></span>  
 <span data-ttu-id="c675b-119">Ein `ExportedType` Metadatenstruktur muss für jeden Typ, der von dieser Assembly verfügbar gemacht wird, und implementiert wird in einem Modul als dem mit dem Manifest, definiert werden.</span><span class="sxs-lookup"><span data-stu-id="c675b-119">An `ExportedType` metadata structure must be defined for each type that is exposed by this assembly and that is implemented in a module other than the one containing the manifest.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c675b-120">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="c675b-120">Requirements</span></span>  
 <span data-ttu-id="c675b-121">**Plattform:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c675b-121">**Platform:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c675b-122">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="c675b-122">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="c675b-123">**Bibliothek:** als Ressource in MsCorEE.dll verwendet</span><span class="sxs-lookup"><span data-stu-id="c675b-123">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="c675b-124">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c675b-124">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c675b-125">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c675b-125">See Also</span></span>  
 [<span data-ttu-id="c675b-126">IMetaDataAssemblyEmit-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="c675b-126">IMetaDataAssemblyEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md)
