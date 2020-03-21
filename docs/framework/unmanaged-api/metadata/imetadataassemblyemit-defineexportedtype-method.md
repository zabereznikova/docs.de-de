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
ms.openlocfilehash: 388f227377ddf73fe1297e1c777bb1c0607c13d2
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79177880"
---
# <a name="imetadataassemblyemitdefineexportedtype-method"></a><span data-ttu-id="d7f98-102">IMetaDataAssemblyEmit::DefineExportedType-Methode</span><span class="sxs-lookup"><span data-stu-id="d7f98-102">IMetaDataAssemblyEmit::DefineExportedType Method</span></span>
<span data-ttu-id="d7f98-103">Erstellt eine `ExportedType`-Struktur, die Metadaten für den angegebenen exportierten Typ enthält, und gibt das zugeordnete Metadatentoken zurück.</span><span class="sxs-lookup"><span data-stu-id="d7f98-103">Creates an `ExportedType` structure containing metadata for the specified exported type, and returns the associated metadata token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d7f98-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="d7f98-104">Syntax</span></span>  
  
```cpp  
HRESULT DefineExportedType (  
    [in]  LPCWSTR             szName,  
    [in]  mdToken             tkImplementation,
    [in]  mdTypeDef           tkTypeDef,  
    [in]  DWORD               dwExportedTypeFlags,  
    [out] mdExportedType      *pmdct  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d7f98-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="d7f98-105">Parameters</span></span>  
 `szName`  
 <span data-ttu-id="d7f98-106">[in] Der Name des zu exportierenden Typs.</span><span class="sxs-lookup"><span data-stu-id="d7f98-106">[in] The name of type to be exported.</span></span> <span data-ttu-id="d7f98-107">Für Version 1.1 der Common Language Runtime muss der Name des exportierten Typs genau mit dem Namen übereinstimmen, der im für den `TypeDef` Typ angegeben ist.</span><span class="sxs-lookup"><span data-stu-id="d7f98-107">For version 1.1 of the common language runtime, the name of the exported type must exactly match the name given in the `TypeDef` for the type.</span></span>  
  
 `tkImplementation`  
 <span data-ttu-id="d7f98-108">[in] Ein Token, das angibt, wo der exportierte Typ implementiert ist.</span><span class="sxs-lookup"><span data-stu-id="d7f98-108">[in] A token specifying where the exported type is implemented.</span></span> <span data-ttu-id="d7f98-109">Die gültigen Werte und die zugehörigen Bedeutungen sind:</span><span class="sxs-lookup"><span data-stu-id="d7f98-109">The valid values and their associated meanings are:</span></span>  
  
- <span data-ttu-id="d7f98-110">`mdFile`Der Typ wird in einer anderen Datei innerhalb dieser Assembly implementiert.</span><span class="sxs-lookup"><span data-stu-id="d7f98-110">`mdFile` The type is implemented in a different file within this assembly.</span></span>  
  
- <span data-ttu-id="d7f98-111">`mdAssemblyRef`Der Typ wird in einer anderen Assembly implementiert.</span><span class="sxs-lookup"><span data-stu-id="d7f98-111">`mdAssemblyRef` The type is implemented in a different assembly.</span></span>  
  
- <span data-ttu-id="d7f98-112">`mdExportedTYpe`Der Typ ist in einem anderen Typ geschachtelt.</span><span class="sxs-lookup"><span data-stu-id="d7f98-112">`mdExportedTYpe` The type is nested within some other type.</span></span>  
  
- <span data-ttu-id="d7f98-113">`mdFileNil`Der Typ befindet sich in derselben Datei wie das Manifest und ist kein geschachtelter Typ.</span><span class="sxs-lookup"><span data-stu-id="d7f98-113">`mdFileNil` The type is in the same file as the manifest and is not a nested type.</span></span>  
  
 `tkTypeDef`  
 <span data-ttu-id="d7f98-114">[in] Ein Token für die Metadaten, das den zu exportierenden Typ angibt.</span><span class="sxs-lookup"><span data-stu-id="d7f98-114">[in] A token to the metadata that specifies the type to be exported.</span></span> <span data-ttu-id="d7f98-115">Dieser Wert wird `TypeDef` in die Tabelle in der Datei eingegeben, die den Typ implementiert, und ist nur relevant, wenn sich diese Datei in dieser Assembly befindet.</span><span class="sxs-lookup"><span data-stu-id="d7f98-115">This value is entered in the `TypeDef` table in the file that implements the type and is relevant only if that file is in this assembly.</span></span>  
  
 `dwExportedTypeFlags`  
 <span data-ttu-id="d7f98-116">[in] Eine bitweise Kombination von CorTypeAttr-Enumerationswerten, die die Eigenschafteneinstellungen für den exportierten Typ definieren. [CorTypeAttr](../../../../docs/framework/unmanaged-api/metadata/cortypeattr-enumeration.md)</span><span class="sxs-lookup"><span data-stu-id="d7f98-116">[in] A bitwise combination of [CorTypeAttr](../../../../docs/framework/unmanaged-api/metadata/cortypeattr-enumeration.md) enumeration values that define the property settings for the exported type.</span></span>  
  
 `pmdct`  
 <span data-ttu-id="d7f98-117">[out] Ein Zeiger auf das zurückgegebene Metadatentoken, das den exportierten Typ angibt.</span><span class="sxs-lookup"><span data-stu-id="d7f98-117">[out] A pointer to the returned metadata token that indicates the exported type.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d7f98-118">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="d7f98-118">Remarks</span></span>  
 <span data-ttu-id="d7f98-119">Für `ExportedType` jeden Typ, der von dieser Assembly verfügbar gemacht wird und der in einem anderen Modul als dem, das das Manifest enthält, implementiert wird, muss eine Metadatenstruktur definiert werden.</span><span class="sxs-lookup"><span data-stu-id="d7f98-119">An `ExportedType` metadata structure must be defined for each type that is exposed by this assembly and that is implemented in a module other than the one containing the manifest.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d7f98-120">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="d7f98-120">Requirements</span></span>  
 <span data-ttu-id="d7f98-121">**Plattform:** Siehe [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d7f98-121">**Platform:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d7f98-122">**Kopfzeile:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="d7f98-122">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="d7f98-123">**Bibliothek:** Wird als Ressource in MsCorEE.dll verwendet</span><span class="sxs-lookup"><span data-stu-id="d7f98-123">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="d7f98-124">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d7f98-124">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d7f98-125">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="d7f98-125">See also</span></span>

- [<span data-ttu-id="d7f98-126">IMetaDataAssemblyEmit-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="d7f98-126">IMetaDataAssemblyEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md)
