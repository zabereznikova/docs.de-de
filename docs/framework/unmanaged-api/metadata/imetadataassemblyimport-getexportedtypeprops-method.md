---
title: IMetaDataAssemblyImport::GetExportedTypeProps-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataAssemblyImport.GetExportedTypeProps
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataAssemblyImport::GetExportedTypeProps
helpviewer_keywords:
- GetExportedTypeProps method [.NET Framework metadata]
- IMetaDataAssemblyImport::GetExportedTypeProps method [.NET Framework metadata]
ms.assetid: 25ca7623-5a55-4f09-b44a-36b03d142278
topic_type: apiref
caps.latest.revision: "10"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: e142d0c77493ac1e9ab2bf485d8e111af4fb3ddb
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="imetadataassemblyimportgetexportedtypeprops-method"></a><span data-ttu-id="2b4de-102">IMetaDataAssemblyImport::GetExportedTypeProps-Methode</span><span class="sxs-lookup"><span data-stu-id="2b4de-102">IMetaDataAssemblyImport::GetExportedTypeProps Method</span></span>
<span data-ttu-id="2b4de-103">Ruft den Satz von Eigenschaften des exportierten Typs mit der angegebenen Metadatensignatur ab.</span><span class="sxs-lookup"><span data-stu-id="2b4de-103">Gets the set of properties of the exported type with the specified metadata signature.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2b4de-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="2b4de-104">Syntax</span></span>  
  
```  
HRESULT GetExportedTypeProps (  
    [in]  mdExportedType    mdct,   
    [out] LPWSTR            szName,   
    [in]  ULONG             cchName,   
    [out] ULONG             *pchName,   
    [out] mdToken           *ptkImplementation,   
    [out] mdTypeDef         *ptkTypeDef,   
    [out] DWORD             *pdwExportedTypeFlags  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="2b4de-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="2b4de-105">Parameters</span></span>  
 `mdct`  
 <span data-ttu-id="2b4de-106">[in] Ein `mdExportedType` Metadatentoken, das den exportierten Typ darstellt.</span><span class="sxs-lookup"><span data-stu-id="2b4de-106">[in] An `mdExportedType` metadata token that represents the exported type.</span></span>  
  
 `szName`  
 <span data-ttu-id="2b4de-107">[out] Der Name des exportierten Typs.</span><span class="sxs-lookup"><span data-stu-id="2b4de-107">[out] The name of the exported type.</span></span>  
  
 `cchName`  
 <span data-ttu-id="2b4de-108">[in] Die Größe in Breitzeichen von `szName`.</span><span class="sxs-lookup"><span data-stu-id="2b4de-108">[in] The size, in wide characters, of `szName`.</span></span>  
  
 `pchName`  
 <span data-ttu-id="2b4de-109">[out] Die Anzahl der tatsächlich zurückgegebenen Breitzeichen`szName`</span><span class="sxs-lookup"><span data-stu-id="2b4de-109">[out] The number of wide characters actually returned in `szName`</span></span>  
  
 `ptkImplementation`  
 <span data-ttu-id="2b4de-110">[out] Ein `mdFile`, `mdAssemblyRef`, oder `mdExportedType` Metadatentoken, die oder ermöglicht den Zugriff auf die Eigenschaften des exportierten Typ enthält.</span><span class="sxs-lookup"><span data-stu-id="2b4de-110">[out] An `mdFile`, `mdAssemblyRef`, or `mdExportedType` metadata token that contains or allows access to the properties of the exported type.</span></span>  
  
 `ptkTypeDef`  
 <span data-ttu-id="2b4de-111">[out] Ein Zeiger auf ein `mdTypeDef` Token, das einen Typ in der Datei darstellt.</span><span class="sxs-lookup"><span data-stu-id="2b4de-111">[out] A pointer to an `mdTypeDef` token that represents a type in the file.</span></span>  
  
 `pdwExportedTypeFlags`  
 <span data-ttu-id="2b4de-112">[out] Ein Zeiger auf die Flags, die in den exportierten Typ angewendete Metadaten beschreiben.</span><span class="sxs-lookup"><span data-stu-id="2b4de-112">[out] A pointer to the flags that describe the metadata applied to the exported type.</span></span> <span data-ttu-id="2b4de-113">Der Wert des Flags kann eine oder mehrere [CorTypeAttr](../../../../docs/framework/unmanaged-api/metadata/cortypeattr-enumeration.md) Werte.</span><span class="sxs-lookup"><span data-stu-id="2b4de-113">The flags value can be one or more [CorTypeAttr](../../../../docs/framework/unmanaged-api/metadata/cortypeattr-enumeration.md) values.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2b4de-114">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="2b4de-114">Requirements</span></span>  
 <span data-ttu-id="2b4de-115">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2b4de-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2b4de-116">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="2b4de-116">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="2b4de-117">**Bibliothek:** als Ressource in MsCorEE.dll verwendet</span><span class="sxs-lookup"><span data-stu-id="2b4de-117">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="2b4de-118">**.NET Framework-Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2b4de-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2b4de-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="2b4de-119">See Also</span></span>  
 [<span data-ttu-id="2b4de-120">IMetaDataAssemblyImport-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="2b4de-120">IMetaDataAssemblyImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md)
