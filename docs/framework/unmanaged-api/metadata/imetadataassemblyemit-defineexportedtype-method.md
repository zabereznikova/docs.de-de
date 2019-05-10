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
ms.openlocfilehash: 5702fac139ba602828bb8722a1e3e25d6f1c58f6
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/28/2019
ms.locfileid: "64625438"
---
# <a name="imetadataassemblyemitdefineexportedtype-method"></a><span data-ttu-id="33a55-102">IMetaDataAssemblyEmit::DefineExportedType-Methode</span><span class="sxs-lookup"><span data-stu-id="33a55-102">IMetaDataAssemblyEmit::DefineExportedType Method</span></span>
<span data-ttu-id="33a55-103">Erstellt eine `ExportedType`-Struktur, die Metadaten für den angegebenen exportierten Typ enthält, und gibt das zugeordnete Metadatentoken zurück.</span><span class="sxs-lookup"><span data-stu-id="33a55-103">Creates an `ExportedType` structure containing metadata for the specified exported type, and returns the associated metadata token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="33a55-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="33a55-104">Syntax</span></span>  
  
```  
HRESULT DefineExportedType (  
    [in]  LPCWSTR             szName,  
    [in]  mdToken             tkImplementation,   
    [in]  mdTypeDef           tkTypeDef,  
    [in]  DWORD               dwExportedTypeFlags,  
    [out] mdExportedType      *pmdct  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="33a55-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="33a55-105">Parameters</span></span>  
 `szName`  
 <span data-ttu-id="33a55-106">[in] Der Name des Typs, der exportiert werden.</span><span class="sxs-lookup"><span data-stu-id="33a55-106">[in] The name of type to be exported.</span></span> <span data-ttu-id="33a55-107">Für Version 1.1 von der common Language Runtime, den Namen des exportierten Typs genau den angegebenen Namen übereinstimmen, muss die `TypeDef` für den Typ.</span><span class="sxs-lookup"><span data-stu-id="33a55-107">For version 1.1 of the common language runtime, the name of the exported type must exactly match the name given in the `TypeDef` for the type.</span></span>  
  
 `tkImplementation`  
 <span data-ttu-id="33a55-108">[in] Ein Token, die angeben, in dem die exportierte Typ implementiert wird.</span><span class="sxs-lookup"><span data-stu-id="33a55-108">[in] A token specifying where the exported type is implemented.</span></span> <span data-ttu-id="33a55-109">Die gültigen Werte und deren jeweilige Bedeutung sind:</span><span class="sxs-lookup"><span data-stu-id="33a55-109">The valid values and their associated meanings are:</span></span>  
  
- <span data-ttu-id="33a55-110">`mdFile` Der Typ wird in einer anderen Datei in dieser Assembly implementiert.</span><span class="sxs-lookup"><span data-stu-id="33a55-110">`mdFile` The type is implemented in a different file within this assembly.</span></span>  
  
- <span data-ttu-id="33a55-111">`mdAssemblyRef` Der Typ wird in einer anderen Assembly implementiert.</span><span class="sxs-lookup"><span data-stu-id="33a55-111">`mdAssemblyRef` The type is implemented in a different assembly.</span></span>  
  
- <span data-ttu-id="33a55-112">`mdExportedTYpe` Der Typ wird in einem anderen Typ geschachtelt.</span><span class="sxs-lookup"><span data-stu-id="33a55-112">`mdExportedTYpe` The type is nested within some other type.</span></span>  
  
- <span data-ttu-id="33a55-113">`mdFileNil` Der Typ befindet sich in derselben Datei wie das Manifest und kein geschachtelter Typ ist.</span><span class="sxs-lookup"><span data-stu-id="33a55-113">`mdFileNil` The type is in the same file as the manifest and is not a nested type.</span></span>  
  
 `tkTypeDef`  
 <span data-ttu-id="33a55-114">[in] Ein Token an den Metadaten, der den zu exportierenden angibt.</span><span class="sxs-lookup"><span data-stu-id="33a55-114">[in] A token to the metadata that specifies the type to be exported.</span></span> <span data-ttu-id="33a55-115">Dieser Wert wird eingegeben die `TypeDef` Tabelle in der Datei, die den Typ implementiert und ist nur relevant, wenn diese Datei in dieser Assembly ist.</span><span class="sxs-lookup"><span data-stu-id="33a55-115">This value is entered in the `TypeDef` table in the file that implements the type and is relevant only if that file is in this assembly.</span></span>  
  
 `dwExportedTypeFlags`  
 <span data-ttu-id="33a55-116">[in] Eine bitweise Kombination von [CorTypeAttr](../../../../docs/framework/unmanaged-api/metadata/cortypeattr-enumeration.md) Enumerationswerte, der die eigenschafteneinstellungen für den exportierten Typ definieren.</span><span class="sxs-lookup"><span data-stu-id="33a55-116">[in] A bitwise combination of [CorTypeAttr](../../../../docs/framework/unmanaged-api/metadata/cortypeattr-enumeration.md) enumeration values that define the property settings for the exported type.</span></span>  
  
 `pmdct`  
 <span data-ttu-id="33a55-117">[out] Ein Zeiger auf die zurückgegebenen Metadaten-Token, das den exportierten Typ angibt.</span><span class="sxs-lookup"><span data-stu-id="33a55-117">[out] A pointer to the returned metadata token that indicates the exported type.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="33a55-118">Hinweise</span><span class="sxs-lookup"><span data-stu-id="33a55-118">Remarks</span></span>  
 <span data-ttu-id="33a55-119">Ein `ExportedType` Metadatenstruktur muss definiert werden, für jeden Typ, der von dieser Assembly verfügbar gemacht wird, und in einem Modul nicht mit dem Manifest implementiert wird.</span><span class="sxs-lookup"><span data-stu-id="33a55-119">An `ExportedType` metadata structure must be defined for each type that is exposed by this assembly and that is implemented in a module other than the one containing the manifest.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="33a55-120">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="33a55-120">Requirements</span></span>  
 <span data-ttu-id="33a55-121">**Plattform:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="33a55-121">**Platform:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="33a55-122">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="33a55-122">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="33a55-123">**Bibliothek:** Als Ressource in MsCorEE.dll verwendet</span><span class="sxs-lookup"><span data-stu-id="33a55-123">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="33a55-124">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="33a55-124">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="33a55-125">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="33a55-125">See also</span></span>

- [<span data-ttu-id="33a55-126">IMetaDataAssemblyEmit-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="33a55-126">IMetaDataAssemblyEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md)
